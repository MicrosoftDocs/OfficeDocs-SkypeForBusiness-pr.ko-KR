---
title: 비즈니스용 Skype 서버에서 모니터링 데이터에 액세스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '요약: 비즈니스용 Skype 서버에서 사용되는 모니터링 데이터에 대해 자세히 알아보습니다.'
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826548"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="39321-103">비즈니스용 Skype 서버에서 모니터링 데이터에 액세스</span><span class="sxs-lookup"><span data-stu-id="39321-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="39321-104">**요약:** 비즈니스용 Skype 서버에서 사용되는 모니터링 데이터에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="39321-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="39321-p101">모니터링 데이터는 SQL Server 데이터베이스 쌍에 저장됩니다. 이러한 데이터베이스 쌍은 통화 정보 기록 데이터를 위한 LcsCdr과 체감 품질 데이터를 위한 QoEMetrics입니다. 이러한 두 데이터베이스는 특별한 사항이 없습니다. 즉, 이러한 데이터베이스에 저장되는 데이터는 일반적으로 SQL Server 데이터를 액세스하고 분석하는 데 사용되는 도구를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39321-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="39321-107">모니터링 데이터에 액세스하고 분석할 때 고려해야 하는 도구 중 하나는 비즈니스용 Skype 서버 모니터링 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="39321-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="39321-108">모니터링 보고서는 Microsoft SQL Server Reporting Services에서 게시되는 표준 보고서 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="39321-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="39321-109">웹 브라우저를 통해 액세스할 수 있는 이러한 보고서는 모두 CDR 및 QoE 데이터베이스에 저장된 CDR(통화 정보 기록) 및 QoE(체감 품질) 레코드를 기반으로 사용, 통화 진단 정보 및 미디어 품질 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="39321-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="39321-110">모니터링 보고서는 비즈니스용 Skype 서버와 함께 발송되고 비즈니스용 Skype 서버가 설치되고 모니터링이 구성된 후 비즈니스용 Skype 서버 배포 마법사에서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39321-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="39321-p103">위에서 설명한 것처럼 모니터링 보고서를 위해서는 SQL Server Reporting Services를 사용해야 합니다. SQL Server Reporting Services는 SQL Server를 설치할 때 동시에 설치하거나 SQL Server 자체를 설치한 후 언제라도 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39321-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="39321-113">자세한 내용은 비즈니스용 [Skype 서버에서 모니터링 보고서 설치 항목을 참조하세요.](../../deploy/deploy-monitoring/install-monitoring-reports.md)</span><span class="sxs-lookup"><span data-stu-id="39321-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

