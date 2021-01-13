---
title: SQL Server Reporting Services(소개)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
description: 각 프런트 엔드 풀 및 SBA(Survivable Branch Appliance)에는 연결된 모니터링 서버가 하나만 있을 수 있습니다. 사이트에 대해 모니터링을 사용하도록 설정하면 모니터링 서버가 CDR(통화 정보 기록) 및 QoE(체감 품질) 데이터 수집과 보고를 제공합니다.
ms.openlocfilehash: 6a45508c3f95da02df966e4d9905020af1b9f9b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829578"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="b45e2-104">SQL Server Reporting Services(소개)</span><span class="sxs-lookup"><span data-stu-id="b45e2-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="b45e2-p102">각 프런트 엔드 풀 및 SBA(Survivable Branch Appliance)에는 연결된 모니터링 서버가 하나만 있을 수 있습니다. 사이트에 대해 모니터링을 사용하도록 설정하면 모니터링 서버가 CDR(통화 정보 기록) 및 QoE(체감 품질) 데이터 수집과 보고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b45e2-p102">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it. When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="b45e2-107">사이트의 모든 풀 및 여러 중앙 사이트의 풀은 사용량이 모니터링 서버의 용량을 초과하지 않는 경우 동일한 모니터링 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b45e2-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="b45e2-108">모니터링을 지원하기 위한 토폴로지 디자인에 대한 자세한 내용은 배포 설명서의 비즈니스용 [Skype 서버 2015에서](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) 모니터링 저장소를 프런트 엔드 풀과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b45e2-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

