---
title: 비즈니스용 Skype 서버 2019 관리 도구
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 비즈니스용 Skype 서버 2019의 서비스 관리 도구에 대해 알아봅니다.'
ms.openlocfilehash: 2369e6530525d7bfc56c23fab1db2869de688cc0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146281"
---
# <a name="skype-for-business-server-2019-management-tools"></a><span data-ttu-id="76f9f-103">비즈니스용 Skype 서버 2019 관리 도구</span><span class="sxs-lookup"><span data-stu-id="76f9f-103">Skype for Business Server 2019 Management Tools</span></span>
 
<span data-ttu-id="76f9f-104">**요약:** 비즈니스용 Skype 서버 2019의 서비스 관리 도구에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-104">**Summary:** Learn about the service management tools in Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="76f9f-105">비즈니스용 Skype 서버 2019에서는 엔터프라이즈 수준의 공동 작업 요구 사항을 지 원하는 IM (인스턴트 메시징), 현재 상태, 회의 및 전화 통신 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-105">Skype for Business Server 2019 offers instant messaging (IM), presence, conferencing, and telephony solutions that support enterprise-level collaboration requirements.</span></span> <span data-ttu-id="76f9f-106">이러한 서비스를 관리 하는 도구는 유연 하 고도 강력 합니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-106">The tools to manage these services are both flexible and powerful.</span></span>
  
## <a name="skype-for-business-server-2019-tools"></a><span data-ttu-id="76f9f-107">비즈니스용 Skype 서버 2019 도구</span><span class="sxs-lookup"><span data-stu-id="76f9f-107">Skype for Business Server 2019 Tools</span></span>

||<span data-ttu-id="76f9f-108">**콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="76f9f-108">**Content**</span></span>|<span data-ttu-id="76f9f-109">**설명**</span><span class="sxs-lookup"><span data-stu-id="76f9f-109">**Description**</span></span>|
|:-----|:-----|:-----|
|![대시보드 아이콘](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="76f9f-111">통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="76f9f-111">Call Quality Dashboard</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534842) <br/> |<span data-ttu-id="76f9f-112">CQD (통화 품질 대시보드)는 비즈니스용 Skype 환경의 QoE (경력 품질) 데이터를 기반으로 보고서를 신속 하 게 작성 및 구성 하기 위한 웹 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-112">The Call Quality Dashboard (CQD) is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data from your Skype for Business environment.</span></span> <span data-ttu-id="76f9f-113">CQD는 QoEMetrics 데이터베이스의 데이터를 집계 하기 위해 SSAS 큐브를 배포 하며,이를 통해 사용자가 보고서를 만들고 수정 하 고 실시간으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-113">The CQD deploys a SSAS cube to aggregate the data in the QoEMetrics database, which enables users to create and modify reports and see them update in real-time.</span></span> <span data-ttu-id="76f9f-114">또한 CQD는 사용자가 사용자 지정 대시보드에서 사용할 큐브 데이터에 프로그래밍 방식으로 액세스할 수 있도록 하는 웹 Api를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-114">Additionally, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>  <br/> |
|![KHI 아이콘](../SfbServer/media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[<span data-ttu-id="76f9f-116">KHI 리소스</span><span class="sxs-lookup"><span data-stu-id="76f9f-116">KHI Resources</span></span>](https://www.microsoft.com/download/details.aspx?id=57519) <br/> |<span data-ttu-id="76f9f-117">KHI (키 상태 지표)는 사용자 환경에 영향을 줄 수 있는 문제 노출을 위한 권장 임계값을 갖는 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-117">Key Health Indicators (KHI) are Performance Counters with recommended thresholds aimed at revealing problems that can impact the user experience.</span></span> <span data-ttu-id="76f9f-118">KHI 가이드에서는 정상적인 배포를 유지 하기 위한 운영 프로세스 및 업데이트 관리 단계를 간략하게 설명 하 고, khi 데이터 수집기를 구성 하는 데 사용 되는 샘플 PowerShell 스크립트와 KHI 성능 데이터를 분석할 수 있는 분석 및 정의 통합 문서를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-118">The KHI Guide outlines the operational process and remediation steps to maintain a healthy deployment, and includes a sample PowerShell script used to configure KHI Data Collectors and an Analysis and Definitions Workbook which can analyze KHI performance data.</span></span>  <br/> |
|![대시보드 아이콘](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="76f9f-120">비즈니스용 Skype 서버 2015에 대 한 통계 관리자</span><span class="sxs-lookup"><span data-stu-id="76f9f-120">Statistics Manager for Skype for Business Server 2015</span></span>](../SfbServer/management-tools/statistics-manager/statistics-manager.md) <br/> |<span data-ttu-id="76f9f-121">StatsMan은 실시간으로 KHI를 보고, 인프라에서 집계 된 성능 카운터를 그래프로 표시 하는 대시보드 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-121">StatsMan is a dashboard solution for viewing KHI calculations in real-time as well as graphed performance counters aggregated across your infrastructure.</span></span> <span data-ttu-id="76f9f-122">대시보드를 사용 하 여 진행 중인 성능 문제를 파악 하 고, 환경에 대 한 계획 된 변경 결과를 확인 하 고, 작동 중단 문제를 추적 하 고, 더 많은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-122">The dashboard can be used to pinpoint ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="76f9f-123">이 상자는 KHI 리소스의 KHI 임계값을 사용 하 여 구성 되며, 배포의 고유한 요구 사항에 맞게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-123">Out of the box, it is configured with KHI thresholds from the KHI Resources, and can be customized to suit your deployment's unique needs.</span></span>  <br/> |
|![SCOM 아이콘](../SfbServer/media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[<span data-ttu-id="76f9f-125">SCOM 관리 팩을 사용 하 여 비즈니스용 Skype 서버 2019 관리</span><span class="sxs-lookup"><span data-stu-id="76f9f-125">Manage Skype for Business Server 2019 using SCOM Management pack</span></span>](tools/scom-management-pack-use-2019.md) <br/> |<span data-ttu-id="76f9f-126">비즈니스용 Skype 서버 2019 관리 팩을 사용 하 여 잠재적 문제를 사전에 파악 하 고 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-126">By using Skype for Business Server 2019 Management Packs, you can identify and address potential issues proactively.</span></span> <span data-ttu-id="76f9f-127">이런 식으로 비즈니스용 Skype 서버 2019 관리 팩은 System Center Operations Manager의 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-127">In this way, the Skype for Business Server 2019 Management Packs extend the capabilities of System Center Operations Manager.</span></span>  <br/> |
|![대시보드 아이콘](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="76f9f-129">비즈니스용 Skype 서버 용량 계획 계산기</span><span class="sxs-lookup"><span data-stu-id="76f9f-129">Skype for Business Server Capacity Planning Calculator</span></span>](../SfbServer/management-tools/capacity-planning-calculator.md) <br/> |<span data-ttu-id="76f9f-130">비즈니스용 Skype 서버 2015/2019 용량 계획 계산기는 조직의 요구 사항에 맞는 토폴로지를 모델링 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76f9f-130">The Skype for Business Server 2015/2019 Capacity Planning Calculator helps you model a topology for your organization's needs.</span></span>  <br/> |
||
