---
title: Usando o OBS como servidor de armazenamento do Veritas NetBackup
layout: default
parent: Object Storage Service (OBS)
grand_parent: Armazenamento
lang: pt
permalink: /docs/storage/obs/using-obs-as-veritas-netbackup-storage-server
---

# Usando o OBS como servidor de armazenamento do Veritas NetBackup

V1.2 - 2024-09-03

| Versão            | Autoria                     | Descrição                                                                                   |
| ----------------- | --------------------------- | ------------------------------------------------------------------------------------------- |
| V1.0 - 2023-07-20 | Gabriel Gutierrez g00817435 | Versão inicial                                                                              |
| V1.1 - 2024-06-05 | Gabriel Gutierrez g00817435 | Alterada a configuração "Endpoint access style" de "Path style" para "Virtual Hosted style" |
| V1.2 - 2024-09-03 | Gabriel Gutierrez g00817435 | Atualizadas as capturas de tela da configuração do OBS.                                     |

## Introdução

Este documento detalha o processo de como usar o Huawei Cloud Object Storage Service (OBS) como um volume do Veritas NetBackup, utilizando o protocolo AWS S3. O NetBackup v10.2 é usado como referência.

## Preparação

Crie um usuário IAM apenas com acesso programático e tipo de credencial "Access key". Não adicione o usuário IAM a nenhum grupo e também não conceda nenhuma permissão no console IAM. Baixe o arquivo de credenciais (`credentials.csv`), que contém a AK e a SK do usuário.

{% include image.html post=page.path file="iam-user-programmatic.png" %}

Crie um bucket OBS com a classe de armazenamento padrão desejada (Standard, Infrequent Access ou Archive) e com a policy do bucket definida como "Private".

{% include image.html post=page.path file="new-obs-bucket.png" %}

No bucket OBS, adicione uma policy para permitir leitura/escrita pelo usuário IAM criado anteriormente.

{% include image.html post=page.path file="obs-bucket-new-policy.png" %}

{% include image.html post=page.path file="obs-bucket-policy-config.png" %}

{% include image.html post=page.path file="obs-bucket-policy.png" %}

## Configuração do NetBackup

O Veritas NetBackup 10.2 está sendo usado como exemplo.

{% include image.html post=page.path file="netbackup-version.png" %}

Ao adicionar um volume, escolha "Amazon S3" como provedor de armazenamento em nuvem:

{% include image.html post=page.path file="netbackup-cloud-storage-provider.png" %}

{% include image.html post=page.path file="netbackup-aws-s3.png" %}

Selecione a classe de armazenamento desejada, considerando a seguinte correspondência:

| S3 class    | HWC OBS class     |
| ----------- | ----------------- |
| Standard    | Standard          |
| Standard-IA | Infrequent Access |
| Glacier     | Archive           |

{% include image.html post=page.path file="netbackup-storage-class.png" %}

Na seção Region, clique em "+ Add" no lado direito.

{% include image.html post=page.path file="netbackup-add-region.png" %}

Configure os seguintes parâmetros (usando LA-Sao Paulo1 como exemplo), utilizando a página "Regions and Endpoints" (<https://developer.huaweicloud.com/intl/en-us/endpoint>) como referência:

- **Region Name**: sa-brazil-1 ou LA-Sao Paulo1 (nome da região)
- **Location Constraint**: sa-brazil-1 (código da região)
- **Service URL**: obs.sa-brazil-1.myhuaweicloud.com (endpoint OBS da região escolhida)
- **Endpoint access style:** Virtual Hosted style
- Mantenha as portas HTTP e HTTPS com os valores padrão (80 e 443)

{% include image.html post=page.path file="netbackup-add-region-configuration.png" %}

Em Access details, configure a AK e a SK obtidas do arquivo `credentials.csv` baixado durante a criação do usuário IAM.

{% include image.html post=page.path file="netbackup-ak-sk.png" %}

Em Advanced Settings > Security, mantenha a opção "Use SSL" marcada e **desmarque/desative** a opção "Check certificate revocation".

{% include image.html post=page.path file="netbackup-certificate-revocation.png" %}

Informe o nome do bucket OBS que foi criado anteriormente:

{% include image.html post=page.path file="netbackup-bucket-name.png" %}

Confirme as configurações realizadas nas etapas anteriores.

{% include image.html post=page.path file="netbackup-configuration-summary.png" %}

Após concluir a configuração do NetBackup, se as classes de armazenamento Standard ou Infrequent Access (Standard-IA) forem selecionadas, os objetos no bucket OBS serão criados com essas respectivas classes de armazenamento. Se a classe Archive for selecionada durante a configuração do volume, no entanto, o NetBackup armazenará os metadados como classe Standard no bucket OBS, enquanto os dados de backup serão armazenados como classe Archive. Os algoritmos internos do NetBackup decidem qual classe de armazenamento será usada para os objetos OBS quando Archive/Glacier for selecionado.
