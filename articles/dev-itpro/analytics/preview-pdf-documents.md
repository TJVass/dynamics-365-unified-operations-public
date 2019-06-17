---
# required metadata

title: Preview PDF documents with an embedded viewer 
description: This topic explains how to use the embedded PDF Preview option to view business documents.
author: tjvass
manager: AnnBe
ms.date: 05/21/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 

# optional metadata

# ms.search.form:
# ROBOTS:
audience: IT Pro
# ms.devlang: 
ms.reviewer: kfend
ms.search.scope: Operations
# ms.tgt_pltfrm: 
# ms.custom:
ms.search.region: Global
# ms.search.industry:
ms.author: tjvass
ms.search.validFrom: 2019-05-21 
ms.dyn365.ops.version: Platform update 28
---

# Preview PDF documents with an embedded viewer

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

You can streamline application experiences that result in the production of business documents by taking advantage of the embedded PDF Preview option. Microsoft Dynamics 365 for Finance and Operations applications deliver a modern experience to preview business documents that are produced by the service. You can use the built-in toolbar to navigate and download the document or to print to locally connected devices.

The embedded viewer offers consistency between the screen presentation and the printed output. In addition, report viewing times are drastically reduced when compared to the legacy experience. The Preview option is available on all supported devices and does not require any additional third-party software. Documents can be easily downloaded and navigated by using the built-in viewer toolbar options.

The following illustration shows a preview of the experience with a modern business document.
![PDF preview form](./media/pdf-document-preview.png)

The legacy HTML-based preview experience is being replaced by a true document preview experience. There are several key advantages in the modern PDF preview experience. These advantages include:

- A fidelity between the screen presentation and the printed output.
- A consistent document report preview experience across devices and platforms, including on-premises deployments.
- The server-side rendering improves the performance when producing the document.
- A built-in tooling that allows users to quickly navigate the contents of the business document.

## Accessing the PDF preview experience
The hosted PDF document viewer control is automatically available in most deployment types. However, for one-box deployments, the PDF preview experience must be enabled on the **Report options** page. Complete the following steps to enable the PDF preview experience. 

1) Go to the **Report options** page by adding "&mi=SysReportAdministration" to the URL in your browser window.
2) Set the **Preview documents using embedded viewer** field to **Yes**.
3) Click **Save**.

## Additional feature information

- Expandable/collapsible sections are only supported when viewing HTML documents. These interactive operations do not function once the report has been rendered as a PDF document.
- Sub-reports are not supported by the PDF Preview experience.  
- The printer drop-down menu allows users to choose from locally connected devices. This list does not include network printers connected through the Finance and Operations service.
- PDF documents are downloaded to the local device using the built-in toolbar actions.
- Application extensions are available to activate embedded drill-thru links in PDF documents.
- Use the **Print destination** options to produce documents in formats other than PDF.

