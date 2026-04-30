---
title: Creating an IAM Agency delegated to a Cloud service
layout: default
parent: Terraform
permalink: /docs/developer-tools/terraform/creating-iam-agency-delegated-to-cloud-service
---

# Creating an IAM Agency delegated to a Cloud service

V1.0 - April 2026

| Version           | Author                         | Description          |
| ----------------- | ------------------------------ | -------------------- |
| V1.0 - 2026-04-30 | Gabriel Gutierrez 00817435     | Initial version      |

## Introduction

When creating an [IAM agency][iam-agency] in the Huawei Cloud Console, there
are two agency types: **Account**, which delegates access to another Huawei
Cloud account, and **Cloud service**, which delegates access to a cloud
service.

When selecting **Account**, you must specify the account name to which access
will be delegated. However, when selecting **Cloud service**, a dropdown list
is displayed, allowing you to select the cloud service to which access will be
delegated. Each dropdown list item is mapped to an internal account name.

When using the Terraform resource `huaweicloud_identity_agency`
to create an IAM agency, the `delegated_domain_name` attribute requires the
account name to be provided, regardless of whether the agency type is
**Account** or **Cloud service**.

The example code below shows how to create an IAM agency that delegates the
**OBS OperateAccess** permission to the ECS/BMS service:

```hcl
resource "huaweicloud_identity_agency" "example" {
  name                  = "example-agency"
  delegated_domain_name = "op_svc_ecs"
  domain_roles          = ["OBS OperateAccess"]
}
```

In this context, the next section lists the value that must be set for
`delegated_domain_name` for each cloud service to which access can be
delegated.

## Account names for Huawei Cloud services

| delegated_domain_name | Cloud Service                                                      |
|-----------------------|--------------------------------------------------------------------|
| op_svc_cad            | Advanced Anti-DDoS (AAD)                                           |
| op_svc_apm            | Application Operations Management (AOM)                            |
| op_svc_cbc            | Billing                                                            |
| op_svc_bcs            | Blockchain Service                                                 |
| op_svc_cce            | Cloud Container Engine (CCE)                                       |
| op_svc_cdm            | Cloud Data Migration (CDM)                                         |
| op_svc_CloudIDE       | CloudIDE                                                           |
| op_svc_CloudMesh      | CloudMesh                                                          |
| op_svc_COC            | Cloud Operations Center (COC)                                      |
| op_svc_cph            | Cloud Phone (CPH)                                                  |
| op_svc_cse            | Cloud Search Engine (CSE)                                          |
| op_svc_usearch        | Cloud Search Service (CSS)                                         |
| op_svc_CloudSite      | CloudSite                                                          |
| op_svc_cs             | Cloud Stream Service (CS)                                          |
| op_svc_cloudtable     | CloudTable                                                         |
| op_svc_CTS            | Cloud Trace Service (CTS)                                          |
| op_svc_CloudBuild     | CodeArts Build                                                     |
| op_svc_CodeCheck      | CodeArts Check                                                     |
| op_svc_CloudDeploy    | CodeArts Deploy                                                    |
| op_svc_DevUC          | CodeArtsDevUC                                                      |
| op_svc_CloudOctopus   | CodeArtsOctopus (CloudOctopus)                                     |
| op_svc_cpts           | CodeArts PerfTest (CPTS)                                           |
| op_svc_CloudPipeline  | CodeArtsPipeline                                                   |
| op_svc_codehub        | CodeArtsRepo                                                       |
| op_svc_eps            | Config (RMS)                                                       |
| op_svc_cdn            | Content Delivery Network (CDN)                                     |
| op_svc_moderation     | Content Moderation (Moderation)                                    |
| op_svc_cs_container1  | CS_gray                                                            |
| op_svc_FABRIC0        | DataArtsFabric                                                     |
| op_svc_rds            | Database Service (DBS)                                             |
| op_svc_bigdata        | Data Ingestion Service (DIS)                                       |
| op_svc_dlv            | Data Intelligence Infrastructure (DII)                             |
| op_svc_dlg            | Data Lake Governance Center (DGC)                                  |
| op_svc_uquery         | Data Lake Insight (DLI)                                            |
| op_svc_SDG            | Data Security Center (DSC)                                         |
| op_svc_dws            | Data Warehouse Service (DWS)                                       |
| op_svc_DWR            | Data Workroom(DWR)                                                 |
| op_svc_dbss           | Database Security Service (DBSS)                                   |
| op_svc_dcs            | Distributed Cache Service                                          |
| op_svc_dms            | Distributed Message Service (DMS)                                  |
| op_svc_dlf            | Data Lake Factory (DLF)                                            |
| op_svc_ecs            | Elastic Cloud Server (ECS) and Bare Metal Server (BMS)             |
| op_svc_evs            | Elastic Volume Service (EVS)                                       |
| op_svc_EG             | EventGrid (EG)                                                     |
| op_svc_cff            | FunctionGraph                                                      |
| op_svc_GeoGenius      | GeoGenius                                                          |
| op_svc_ges            | Graph Engine Service (GES)                                         |
| op_svc_HaydnCSF       | HaydnCSF                                                           |
| op_svc_QuickBuy       | HPC Service                                                        |
| op_svc_IdentityCenter | IAM Identity Center                                                |
| op_svc_ims            | Image Management Service (IMS)                                     |
| op_svc_image          | Image Recognition (Image)                                          |
| op_svc_IDT            | Industrial Digital Thread (IDT)                                    |
| op_svc_IVM            | Industry video management IVM                                      |
| op_svc_ief            | Intelligent EdgeFabric (IEF)                                       |
| op_svc_IoTAnalytics   | IoTA                                                               |
| op_svc_IoTDM          | IoTDA                                                              |
| op_svc_IoTEdge        | IoTEdge                                                            |
| op_svc_KooPhone       | KooPhone service                                                   |
| op_svc_LakeFormation  | LakeFormation                                                      |
| op_svc_mls            | Machine Learning Service (MLS)                                     |
| op_svc_MSGSMS         | Message & SMS                                                      |
| op_svc_MgC            | Migration Center(MgC)                                              |
| op_svc_eiwizard       | ModelArts                                                          |
| op_svc_mrs            | MapReduce Service (MRS)                                            |
| op_svc_obs            | Object Storage Service (OBS)                                       |
| op_svc_Octopus        | Octopus                                                            |
| op_svc_ivehicle       | OCTOPUS                                                            |
| op_svc_maas           | Object Storage Migration Service (OMS)                             |
| op_svc_OROAS          | OptVerse                                                           |
| op_svc_pEDACloud      | PCB-Focused Electronic Design Automation Cloud Service (pEDACloud) |
| op_svc_res            | Recommender System (RES)                                           |
| op_svc_IAC            | Resource Formation Service (RFS)                                   |
| op_svc_romalink       | ROMA                                                               |
| op_svc_ssa            | SA                                                                 |
| op_svc_SDRS           | Business Recovery Service (SDRS)                                   |
| op_svc_servicestage   | ServiceStage                                                       |
| op_svc_OSM            | ServiceTickets                                                     |
| op_svc_smn            | Simple Message Notification (SMN)                                  |
| op_svc_swr            | SoftWare Repository for Container (SWR)                            |
| op_svc_waf            | Web Application Firewall (WAF)                                     |
| op_svc_workspace      | Workspace                                                          |

## References

- Huawei Cloud Identity and Access Management (IAM) - Delegating Another
  Service for Resource Management:
  <https://support.huaweicloud.com/intl/en-us/usermanual-iam/iam_06_0004.html>
- `huaweicloud_identity_agency` Terraform resource documentation:
  <https://registry.terraform.io/providers/huaweicloud/huaweicloud/latest/docs/resources/identity_agency>

[iam-agency]: <https://support.huaweicloud.com/intl/en-us/usermanual-iam/iam_01_0661.html>
