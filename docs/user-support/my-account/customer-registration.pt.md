---
title: Criação de Conta
layout: default
parent: Minha Conta
grand_parent: Suporte ao Usuário
lang: pt
permalink: /docs/user-support/my-account/customer-registration
---

# Criação de Conta

V1.0 – Nov 2025

| **Versão**        | **Autor**                           | **Descrição**       |
| ----------------- | ----------------------------------- | --------------------|
| V1.0 – 2025-11-24 | Fernando Gabriel Chacon  50037923   | Versão Inicial      |
| V1.0 – 2025-11-24 | Gabriel Gutierrez  00817435         | Revisão do Documento|

1. Índice
{:toc}

## Introdução

A Huawei Cloud fornece uma plataforma de nuvem global e segura. Antes de acessar
os serviços de nuvem, os clientes devem criar e ativar suas contas por meio do
portal oficial de registro. Este guia oferece um passo a passo completo e
estruturado para que novos clientes concluam com sucesso o processo de registro.

## Fluxo de Registro

<pre class="mermaid">
flowchart TD
    %% Main Flow
    A["1️⃣ Página Inicial"] --> B["2️⃣ Página de Registro"]

    subgraph Z[" "]
        B -.-> B1["Preencha:<br>- País<br>- Email<br>- Senha"]
    end

    subgraph ZA[" "]
        B1 --> C["3️⃣ Email/telefone de verificação"]
        C -.-> C1["Receba e preencha o código de verificação"]
        C1 -.-> C2["Autorize e faça Log in, concorde com o  <b>Acordo do cliente e a Declaração de privacidade</b>"]
    end

    C2 --> D["Tela de Registro"]
    D --> E["4️⃣ Complete as informações"]

    subgraph ZB[" "]
        E -.-> E1["Verifique o telefone"]
        E1 -.-> E3["Preencha:<br>- CNPJ<br>- Nome do contato<br>- Cargo<br>- Setor"]
    end

    E3 --> F["✅ Concluído"]

    classDef main fill:#cce5ff,stroke:#336699,stroke-width:1px;
    classDef gray fill:#f0f0f0,stroke:#aaa;
    classDef red fill:#fff,stroke:#000,color:#a00,font-weight:bold;
    classDef white fill:#fff,stroke:#000,color:#000;

    class A,B,C,E,F main;
    class D gray;
    class B1,C1,C2,E1,E3 white;
</pre>

## Etapas

### 1. Acessar a Página Inicial e registrar-se

Acesse o site oficial da Huawei Cloud: [https://www.huaweicloud.com/intl/pt-br/](https://www.huaweicloud.com/intl/pt-br/)

{% include image.html post=page.path file="step1-huawei-cloud-home-page_pt.jpg" alt="Huawei Cloud Home Page" %}

Clique no botão **Inscrever-se** no canto superior direito para abrir o portal
de registro.

{% include image.html post=page.path file="step2-register-page_pt.png" alt="Register Page" %}

Informe seu e-mail, clique em **Obter Código**, insera o código de verificação
recebido em sua caixa de entrada, defina uma senha e clique no botão
**Registro**.

### 2. Completar a Verificação

Nesta etapa opcional, você pode adicionar um número de telefone para aumentar a
segurança da conta. Se desejar configurá-lo, insira seu número de celular,
clique em **Obter Código**, informe o código recebido por SMS e clique em OK.
Caso contrário, clique em **Pular**.

{% include image.html post=page.path file="step3-set-security-phone-number_pt.png" alt="Set Security Phone Number" %}

### 3. Autorizar e Fazer Login

Confirme a solicitação de autorização clicando no botão **Autorizar**.

{% include image.html post=page.path file="step4-authorize-and-log-in_pt.jpg" alt="Authorize and Log-in" %}

### 4. Ativar os Serviços da Huawei Cloud

Prossiga para ativar os serviços da Huawei Cloud. Aceite o acordo do cliente e a
declaração de privacidade, e opcionalmente selecione a opção para receber
atualizações sobre descontos e promoções. Em seguida, clique em **Habilitar**.

{% include image.html post=page.path file="step5-enable-huawei-cloud-services_pt.jpg" alt="Enable Huawei Cloud Services" %}

### 5. Vincular Número de Celular

Vincule um número de celular válido para a segurança da conta e verificação de
identidade. Insera seu número de telefone, clique em **Enviar Código**, insera o
código de verificação recebido por SMS e clique em **Próximo**.

{% include image.html post=page.path file="step6-bind-mobile-number_pt.png" alt="Bind Mobile Phone Number" %}

### 6. Completar as Informações da Conta

Preencha as informações solicitadas. Informe o CNPJ e os demais campos
solicitados e clique em **Próximo**.

{% include image.html post=page.path file="step7-complete-account-information_pt.png" alt="Complete Account Information 1" %}

### 7. Ativar Sua Conta

Escolha a opção que melhor se adequa ao seu caso.

{% include image.html post=page.path file="step8-enable-your-account_pt.png" alt="Enable your account" %}
