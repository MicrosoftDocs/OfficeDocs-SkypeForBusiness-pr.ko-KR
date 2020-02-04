---
title: SQL Server Reporting Services (소개)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
description: 각 프런트 엔드 풀 및 Survivable Branch 기기는 연결 된 모니터링 서버를 하나만 가질 수 있습니다. 사이트에 대해 모니터링을 사용할 수 있는 경우 모니터링 서버는 CDR (통화 정보 기록), 체감 품질 (환경 품질) 데이터 수집 및 보고 기능을 제공 합니다.
ms.openlocfilehash: f9b838ee474fce848dc4d8f1511a5061d5f8cfe2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687302"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="930b3-104">SQL Server Reporting Services (소개)</span><span class="sxs-lookup"><span data-stu-id="930b3-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="930b3-105">각 프런트 엔드 풀 및 Survivable Branch 기기는 연결 된 모니터링 서버를 하나만 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930b3-105">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it.</span></span> <span data-ttu-id="930b3-106">사이트에 대해 모니터링을 사용할 수 있는 경우 모니터링 서버는 CDR (통화 정보 기록), 체감 품질 (환경 품질) 데이터 수집 및 보고 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="930b3-106">When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="930b3-107">사용 현황이 모니터링 서버의 용량을 초과 하지 않는 경우 사이트의 모든 풀과 여러 중앙 사이트의 풀은 동일한 모니터링 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="930b3-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="930b3-108">모니터링을 지원 하기 위해 토폴로지를 디자인 하는 방법에 대 한 자세한 내용은 배포 설명서의 [비즈니스용 Skype 서버 2015에서 모니터링 저장소를 프런트 엔드 풀에 연결](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="930b3-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

