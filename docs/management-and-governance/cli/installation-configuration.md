---
title: KooCLI Installation and Configuration
layout: default
parent: Management and Governance
lang: en
permalink: /docs/management-and-governance/cli/installation-configuration
---
<img width="450px" height="102px" src="https://console-static.huaweicloud.com/static/authui/20210202115135/public/custom/images/logo-en.svg">

# KooCLI - Huawei Cloud Command Line Interface

V1.0 – November 2025

| **Version**       | **Author**                     | **Description**      |
| ----------------- | ------------------------------ | -------------------- |
| V1.0 – 2025-11    | Raul Myron 50054635            | Initial Version      |

## Introduction

This document presents the procedures for installing and configuring KooCLI (Huawei Cloud CLI), the official command-line tool for managing Huawei Cloud resources.

## Installation on Ubuntu/Linux

Refer to the [Official Documentation](https://support.huaweicloud.com/intl/en-us/qs-hcli/hcli_02_003_02.html) for more details.

### Installation Steps

```bash
# Download and install
sudo curl -sSL http://ap-southeast-3-hwcloudcli.obs.ap-southeast-3.myhuaweicloud.com/cli/latest/hcloud_install.sh -o ./hcloud_install.sh && sudo bash ./hcloud_install.sh

# Verify installation
hcloud version

# Start configuration
hcloud configure show
```

### Configuration

During configuration, you will be prompted for:
- **Access Key (AK)**: Your access key
- **Secret Key (SK)**: Your secret key
- **Region**: Huawei Cloud region (for Brazil: `sa-brazil-1`)

### Timeout Adjustments (Recommended for Brazil)

To improve connection stability:

```bash
# Recommended configuration
hcloud configure set --connect-timeout=60 --read-timeout=120 --retry-count=3

# Alternative for more unstable connections
hcloud configure set --connect-timeout=90 --read-timeout=180 --retry-count=5
```

## Installation on Windows

### Download

- [Official Documentation](https://support.huaweicloud.com/intl/en-us/qs-hcli/hcli_02_003_01.html)
- [Direct Download (.exe)](https://ap-southeast-3-hwcloudcli.obs.ap-southeast-3.myhuaweicloud.com/cli/latest/huaweicloud-cli-windows-amd64.zip)

### Environment Variables Configuration

1. Extract the file to a directory (e.g., `C:\huaweicloud-cli`)
2. Add the path to environment variables:
   - Go to **System Settings** → **Environment Variables**
   - Add the path to the user's **Path** variable

### Verification and Configuration

```bash
# Verify installation
hcloud version

# Start configuration
hcloud configure show

# Configure timeouts
hcloud configure set --connect-timeout=60 --read-timeout=120 --retry-count=3
```

## Installation Verification

```bash
# Download service metadata
hcloud meta download

# List all available services
hcloud
```

## Available Services

KooCLI supports over 100 Huawei Cloud services, including:

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

For a complete list of services, run `hcloud` after installation.

## Next Steps

- Explore documentation for each service: `hcloud [service] help`
- Configure multiple profiles for different accounts/regions
- Integrate with automation scripts

## References

- [Official KooCLI Documentation](https://support.huaweicloud.com/intl/en-us/qs-hcli/hcli_02_003.html)