---
# required metadata

title: Software lifecycle policy and on-premises releases
description: This topic outlines the lifecycle and support policies for Microsoft Dynamics 365 for Finance and Operations (on-premises) releases.
author: RyanCCarlson2 
manager: AnnBe
ms.date: 09/05/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 

# optional metadata

ms.search.form: SysAbout
# ROBOTS: 
audience: Developer, IT Pro
# ms.devlang: 
ms.reviewer: josaw
ms.search.scope: Operations
# ms.tgt_pltfrm: 
ms.custom: 69914
ms.search.region: Global
# ms.search.industry: 
ms.author: rcarlson
ms.search.validFrom: 2017-07-15
ms.dyn365.ops.version: Platform update 2

---

# Software lifecycle policy and on-premises releases

[!include [banner](../includes/banner.md)]

This topic outlines the lifecycle and support policies for Microsoft Dynamics 365 for Finance and Operations (on-premises) releases.

## Modern Lifecycle Policy 
Microsoft Dynamics 365 for Finance and Operations (on-premises) software is covered by the Modern Lifecycle Policy. The Modern Lifecycle Policy covers products and services that are serviced and supported continuously. For more information about this policy, see [Modern Lifecycle Policy](https://support.microsoft.com/en-us/help/30881/modern-lifecycle-policy).  

Licensed customers must stay current with updates to the Dynamics 365 for Finance and Operations on-premises software in accordance with the following servicing and system requirements.  This policy requires that the customer maintain Software Assurance (SA) or the Enhancement Plan, and that it deploy updates as noted later in this topic. Customers who want to use the Fixed Support Lifecycle Policy (5+5) must downgrade to Microsoft Dynamics AX 2012 R3. If a customer lapses on SA or the Enhancement Plan, it will be eligible only for the perpetual license rights to Microsoft Dynamics AX 2012 R3 and must uninstall Microsoft Dynamics 365 for Finance and Operations (on-premises) software. 

## On-premises software update policies 
The customer is in full control of its on-premises deployments and must follow this policy. The customer is in control of installing updates in its on-premises environments. Microsoft will support the Dynamics 365 for Finance and Operations (on-premises) software through December 31, 2027, at a minimum, but only if the customer keeps the deployed software current according to this policy.

Critical fixes and non-critical updates are handled in the following way: 
  - **Critical fixes** – Critical fixes include security fixes and any fixes that are required to support reliability and availability. Critical fixes will be made available in the latest platform update version.  
  - **Non-critical updates** – Customers must update to the most current Finance and Operations platform and financial reporter version to deploy non-critical updates.   

## Dynamics 365 for Finance and Operations on-premises release dates
Application and Platform releases expire at the end of the month of their software lifecycle.

### Application Releases

| Release          |Version         | Build number          | Availability | Expiration date  | Product life | 
|------------------|----------------------|------------------|--------------|---------------|-----------------|
|  Dynamics 365 for Finance and Operations, Enterprise edition (on-premises) | 7.3 | 7.3.11971  | March 2018 | April 2020*     | December 2027  |
|  Dynamics 365 for Finance and Operations, Enterprise edition (on-premises) | July 2017 | 7.2.11792 | June 2017 | April 2019     | December 2027  |

\* The only exception to being on the latest version is for customers with unfulfilled [extension requests](../extensibility/extensibility-home-page.md) that have been submitted to Microsoft. For these customers, support for version 7.3 will be available until April 2020.

### Platform Releases

| Release          |Build number         | Availability          | Expiration | End of life  |
|------------------|----------------------|------------------|--------------|---------------|
|  Platform update 15 | 7.0.4841.XXXX  | June 2018  | September 2018 | December 2027     |
|  Platform Update 12 | 7.0.4709.41182  | March 2018  | June 2018 | December 2027     |
|  Platform Update 11 | 7.0.4679.35176 | October 2017 | April 2018 | December 2027     |
|  Platform Update 10 | 7.0.4641.16233 | August 2017 | April 2018 | December 2027     |
|  Platform Update 9 | 7.0.4612.35162 | August 2017 | April 2018 | December 2027     |
|  Platform Update 8 | 7.0.4565.1612 | July 2017 | April 2018 | December 2027     |

  > [!NOTE]
  > Platform releases are cumulative in nature. Any fixes, critical or non-critical, will require customers to take the latest available version of the platform. 

### Downloadable virtual hard drive (VHD) releases
Use of the VHDs is subject to the [Software license terms](https://go.microsoft.com/fwlink/?linkid=851163). 


|                   Release                    |           VHD name           | VHD expiration date |
|----------------------------------------------|------------------------------|---------------------|
| Platform update 12 / Application release 7.2 | FinandOps7.2PlatUpdate12.vhd |    May 24, 2018     |
| Platform update 12 / Application release 7.3 | FinandOps7.3PlatUpdate12.vhd |    June 05, 2018    |
| Platform update 15 / Application release 7.3 | FinandOps7.3withPlatUpdate15 |    December 08, 2018    |

