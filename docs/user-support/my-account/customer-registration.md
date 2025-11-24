---
title: Customer Registration
layout: default
parent: My Account
grand_parent: User Support
permalink: /docs/user-support/my-account/customer-registration
---

# Customer Registration

V1.0 – Nov 2025

| **Version**       | **Author**                          | **Description**      |
| ----------------- | ----------------------------------- | -------------------- |
| V1.0 – 2025-11-24 | Fernando Gabriel Chacon  50037923   | Initial Version      |
| V1.0 – 2025-11-24 | Gabriel Gutierrez  00817435         | Document Review      |

1. Index
{:toc}

## Introduction

Huawei Cloud provides a global and secure cloud platform. Before accessing cloud
services, customers must create and activate their accounts through the official
registration portal. This guide provides a complete and structured walkthrough
for new customers to complete the registration process successfully.

## Registration Flow

<pre class="mermaid">
flowchart TD
    %% Main Flow
    A["1️⃣ Home page"] --> B["2️⃣ Register page"]

    subgraph Z[" "]
        B -.-> B1["Fill in:<br>- Country<br>- Email<br>- Password"]
    end

    subgraph ZA[" "]
        B1 --> C["3️⃣ Email/phone verification"]
        C -.-> C1["Receive and fill in<br>verification code"]
        C1 -.-> C2["Authorize and login, agree with <b>Huawei Cloud Customer Agreement and Privacy Statement</b>"]
    end

    C2 --> D["Registration info display"]
    D --> E["4️⃣ Complete information"]

    subgraph ZB[" "]
        E -.-> E1["Phone verification"]
        E1 -.-> E3["Fill in:<br>- CNPJ<br>- Contact Name<br>- Designation<br>- Industry"]
    end

    E3 --> F["✅ Done"]

    classDef main fill:#cce5ff,stroke:#336699,stroke-width:1px;
    classDef gray fill:#f0f0f0,stroke:#aaa;
    classDef red fill:#fff,stroke:#000,color:#a00,font-weight:bold;
    classDef white fill:#fff,stroke:#000,color:#000;

    class A,B,C,E,F main;
    class D gray;
    class B1,C1,C2,E1,E3 white;
</pre>

## Steps

### 1. Enter the Home Page and Sign Up

Access the official Huawei Cloud website: [https://www.huaweicloud.com/intl/en-us/](https://www.huaweicloud.com/intl/en-us/)

{% include image.html post=page.path file="step1-huawei-cloud-home-page.png" alt="Huawei Cloud Home Page" %}

Click the **Sign Up** button in the top-right corner to open the registration
portal.

{% include image.html post=page.path file="step2-register-page.png" alt="Register Page" %}

Provide your email, click **Get Code**, enter the verification code received in
your inbox, set a password, and click the **Register** button.

### 2. Complete the Verification

This step is optional. If you want to set a security phone number, enter your
mobile number, click **Get Code**, enter the SMS verification code, and click
**OK**. Otherwise, click **Skip**.

{% include image.html post=page.path file="step3-set-security-phone-number.png" alt="Set Security Phone Number" %}

### 3. Authorize and Log In

Confirm the authorization request by clicking the **Authorize** button.

{% include image.html post=page.path file="step4-authorize-and-log-in.jpg" alt="Authorize and Log-in" %}

### 4. Enable Huawei Cloud Services

Proceed to enable Huawei Cloud services. Accept the customer agreement and the
privacy statement, and optionally select the option to receive updates about
discounts and promotions. Then click **Enable**

{% include image.html post=page.path file="step5-enable-huawei-cloud-services.jpg" alt="Enable Huawei Cloud Services" %}

### 5. Bind Mobile Number

Bind a valid mobile number for account security and identity confirmation. Enter
your phone number, click **Send Code**, enter the SMS verification code, and
then click **Next**.

{% include image.html post=page.path file="step6-bind-mobile-number.png" alt="Bind Mobile Phone Number" %}

### 6. Complete Account Information

Fill in the required information. Enter the CNPJ and the remaining fields
requested and click **Next**.

{% include image.html post=page.path file="step7-complete-account-information.png" alt="Complete Account Information 1" %}

### 7. Activate Your Account

Choose the option that best suits your case.

{% include image.html post=page.path file="step8-enable-your-account.png" alt="Enable your account" %}
