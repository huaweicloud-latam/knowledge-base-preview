---
title: Instalação e Configuração do KooCLI
layout: default
parent: Management and Governance
lang: pt
permalink: /docs/management-and-governance/cli/installation-configuration
---
<img width="450px" height="102px" src="https://console-static.huaweicloud.com/static/authui/20210202115135/public/custom/images/logo-en.svg">

# KooCLI - Interface de Linha de Comando da Huawei Cloud

V1.0 – Novembro 2025

| **Versão**        | **Autor**                      | **Descrição**        |
| ----------------- | ------------------------------ | -------------------- |
| V1.0 – 2025-11    | Raul Myron 50054635            | Versão Inicial       |

## Introdução

Este documento apresenta os procedimentos para instalação e configuração do KooCLI (Huawei Cloud CLI), a ferramenta de linha de comando oficial para gerenciamento de recursos na Huawei Cloud.

## Instalação no Ubuntu/Linux

Consulte a [Documentação Oficial](https://support.huaweicloud.com/intl/en-us/qs-hcli/hcli_02_003_02.html) para mais detalhes.

### Passos de Instalação

```bash
# Fazer download e instalar
sudo curl -sSL http://ap-southeast-3-hwcloudcli.obs.ap-southeast-3.myhuaweicloud.com/cli/latest/hcloud_install.sh -o ./hcloud_install.sh && sudo bash ./hcloud_install.sh

# Verificar instalação
hcloud version

# Iniciar configuração
hcloud configure show
```

### Configuração

Durante a configuração, será solicitado:
- **Access Key (AK)**: Sua chave de acesso
- **Secret Key (SK)**: Sua chave secreta
- **Region**: Região da Huawei Cloud (para Brasil: `sa-brazil-1`)

### Ajustes de Timeout (Recomendado para Brasil)

Para melhorar a estabilidade da conexão:

```bash
# Configuração recomendada
hcloud configure set --connect-timeout=60 --read-timeout=120 --retry-count=3

# Alternativa para conexões mais instáveis
hcloud configure set --connect-timeout=90 --read-timeout=180 --retry-count=5
```

## Instalação no Windows

### Download

- [Documentação Oficial](https://support.huaweicloud.com/intl/en-us/qs-hcli/hcli_02_003_01.html)
- [Download Direto (.exe)](https://ap-southeast-3-hwcloudcli.obs.ap-southeast-3.myhuaweicloud.com/cli/latest/huaweicloud-cli-windows-amd64.zip)

### Configuração de Variáveis de Ambiente

1. Extraia o arquivo para um diretório (ex: `C:\huaweicloud-cli`)
2. Adicione o caminho às variáveis de ambiente:
   - Vá em **Configurações do Sistema** → **Variáveis de Ambiente**
   - Adicione o caminho no **Path** do usuário

### Verificação e Configuração

```bash
# Verificar instalação
hcloud version

# Iniciar configuração
hcloud configure show

# Configurar timeouts
hcloud configure set --connect-timeout=60 --read-timeout=120 --retry-count=3
```

## Verificação da Instalação

```bash
# Download de metadados dos serviços
hcloud meta download

# Listar todos os serviços disponíveis
hcloud
```

## Serviços Disponíveis

O KooCLI oferece suporte a mais de 100 serviços da Huawei Cloud, incluindo:

|           |                  |                     |                     |              |
|-----------|------------------|---------------------|---------------------|--------------|
|    AAD    |        CSS       |         DSC         | IdentityCenterStore |     ROMA     |
|    AOM    |        CTS       |         DWS         |        Image        |   RabbitMQ   |
|    AOS    |    CloudBuild    |    DataArtsStudio   |        IoTDA        |   RocketMQ   |
|    APIG   |     CloudRTC     |         ECS         |        IoTDM        |      SCM     |
|     AS    |     CloudTest    |         EIP         |         KMS         |   SFSTurbo   |
| Anti-DDoS | CodeArtsArtifact |         ELB         |         KPS         |      SIS     |
|    BMS    |   CodeArtsBuild  |         EPS         |        Kafka        |      SMN     |
|  BSSINTL  |   CodeArtsCheck  |          ER         |         LTS         |      SMS     |
|    CBH    |  CodeArtsDeploy  |         EVS         |         Live        |      STS     |
|    CBR    | CodeArtsPipeline |       EdgeSec       |         MPC         |      SWR     |
|    CBS    |     CodeCheck    |         FRS         |         MRS         |   SecMaster  |
|     CC    |      CodeHub     |    FunctionGraph    |       Meeting       | ServiceStage |
|    CCE    |      Config      |          GA         |      ModelArts      |      TMS     |
|    CCI    |        DAS       |         GES         |      Moderation     |      UGO     |
|    CCM    |       DBSS       |       GaussDB       |         NAT         |      VOD     |
|    CDM    |        DC        |   GaussDBforNoSQL   |         OCR         |      VPC     |
|    CDN    |        DCS       | GaussDBforopenGauss |         OMS         |     VPCEP    |
|    CES    |        DDM       |         HSS         |    Organizations    |      VPN     |
|    CFW    |        DDS       |         IAM         |      ProjectMan     |      WAF     |
|    COC    |        DIS       |         IMS         |         RAM         |   Workspace  |
|    CPTS   |        DLI       |    IdentityCenter   |         RDS         |              |
|    CSE    |        DNS       |  IdentityCenterOIDC |         RGC         |              |
|    CSMS   |        DRS       |  IdentityCenterSCIM |         RMS         |              |

Para lista completa de serviços, execute `hcloud` após a instalação.

## Próximos Passos

- Explore a documentação de cada serviço: `hcloud [service] help`
- Configure perfis múltiplos para diferentes contas/regiões
- Integre com scripts de automação

## Referências

- [Documentação Oficial KooCLI](https://support.huaweicloud.com/intl/en-us/qs-hcli/hcli_02_003.html)