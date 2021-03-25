---
title: Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 계획
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 이 문서에서는 Azure Monitor를 사용하여 비즈니스용 Skype 또는 Teams 구현에서 Microsoft Teams Rooms 디바이스를 관리하기 위한 계획 고려 사항을 설명합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117586"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="b8ac5-103">Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 계획</span><span class="sxs-lookup"><span data-stu-id="b8ac5-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="b8ac5-104">이 문서에서는 Azure Monitor를 사용하여 Microsoft Teams 또는 비즈니스용 Skype 구현에서 Microsoft Teams Rooms 디바이스를 관리하기 위한 계획 고려 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="b8ac5-105">[Azure Monitor는](/azure/azure-monitor/overview) 시작부터 클라우드에서 디자인된 관리 서비스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-105">[Azure Monitor](/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="b8ac5-106">Azure Monitor 구성 요소는 전적으로 Azure에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="b8ac5-107">구성은 최소화되어 있으며 몇 분 만에 말 그대로 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="b8ac5-108">일부 사용자 지정 작업을 통해 개별 회의실 시스템에 대한 시스템 상태 또는 오류에 대한 실시간 알림을 제공하여 Microsoft Teams Room 회의 시스템을 관리하는 데 도움이 될 수 있으며 수천 개의 Microsoft Teams Room 회의실 회의실 관리로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="b8ac5-109">이 문서에서는 Microsoft Teams Rooms 회의실의 Azure Monitor 기반 관리를 구현하는 데 필요한 요구 사항, 디자인/아키텍처 및 구현 모범 사례에 대해 설명하고 Microsoft Teams Rooms용 Azure Monitor 구현에 대한 자세한 문서와 Microsoft Teams Rooms 회의실의 지속적인 모니터링을 위한 중요한 참조 정보에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="b8ac5-110">기능 개요</span><span class="sxs-lookup"><span data-stu-id="b8ac5-110">Functional overview</span></span>

![Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 다이어그램](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="b8ac5-112">콘솔 디바이스의 Microsoft Teams Rooms 앱은 Windows 이벤트 로그에 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="b8ac5-113">Microsoft Monitoring 에이전트가 설치되면 Azure Monitor 서비스에 정보를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="b8ac5-114">제대로 구성되면 Log Analytics는 이벤트 설명에 포함된 JSON 페이로드를 구문 분석하여 각 Microsoft Teams Rooms 시스템이 작동하는 방식과 감지된 오류에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="b8ac5-115">Azure Monitor를 사용하는 관리자는 오프라인 상태이거나 앱, 연결 또는 하드웨어 오류가 발생하는 Microsoft Teams Rooms 시스템의 알림을 받을 수 있을 뿐만 아니라 시스템을 다시 시작해야 하는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="b8ac5-116">각 시스템 상태가 자주 업데이트되어 이러한 알림은 실시간 업데이트에 가깝습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="b8ac5-117">Azure Monitor 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8ac5-117">Azure Monitor requirements</span></span>

<span data-ttu-id="b8ac5-118">Log Analytics 기능을 사용하려면 Azure Monitor에 대한 유효한 Azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="b8ac5-119">Log [Analytics](/azure/azure-monitor/learn/quick-create-workspace) 작업 영역 시작을 참조하여 조직의 구독을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-119">See [Get started with a Log Analytics workspace](/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="b8ac5-120">Log Analytics 뷰 디자이너를 사용하는 방법에 대해 필요한 경우 익숙해지세요.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="b8ac5-121">자세한 [내용은 Log Analytics의](/azure/azure-monitor/platform/view-designer) 보기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-121">See [Views in Log Analytics](/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="b8ac5-122">관련 작업</span><span class="sxs-lookup"><span data-stu-id="b8ac5-122">Related Tasks</span></span>

1. <span data-ttu-id="b8ac5-123">Azure Monitor Log Analytics를 구독한 후 Microsoft [](azure-monitor-deploy.md#Custom_fields)Teams Rooms 콘솔에서 보낼 정보를 구문 분석하는 데 필요한 사용자 지정 필드(지도 사용자 지정 필드에 설명된 경우)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="b8ac5-124">여기에는 로그 항목 이해 에 설명된 JSON의척도 [이해가 포함됩니다.](azure-monitor-manage.md#understand-the-log-entries)</span><span class="sxs-lookup"><span data-stu-id="b8ac5-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="b8ac5-125">Log Analytics에서 Microsoft Teams Rooms 관리 보기를 개발합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="b8ac5-126">가져오기 메서드를 사용하여 [Microsoft Teams Rooms](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) 대시보드 만들기 또는 Microsoft Teams Rooms 대시보드를 수동으로 만들 수 [있습니다.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)</span><span class="sxs-lookup"><span data-stu-id="b8ac5-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="b8ac5-127">개별 Microsoft Teams Rooms 콘솔 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8ac5-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="b8ac5-128">각 Microsoft Teams Rooms 콘솔은 키오스크 모드에서 Surface Pro 디바이스에서 실행되는 앱입니다(일반적으로 디바이스에서 실행할 수 있는 유일한 앱으로 구성).</span><span class="sxs-lookup"><span data-stu-id="b8ac5-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="b8ac5-129">Windows 앱과 마찬가지로 Microsoft Teams Rooms 앱은 Windows 이벤트 로그에 시작 및 하드웨어 오류와 같은 이벤트를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="b8ac5-130">Microsoft Teams Rooms 디바이스에 Microsoft Monitor 에이전트를 추가하면 이러한 이벤트를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="b8ac5-131">(자세한 내용은 [Azure의 Log Analytics](/azure/azure-monitor/platform/agent-windows) 서비스에 Windows 컴퓨터 연결 을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="b8ac5-131">(See [Connect Windows computers to the Log Analytics service in Azure](/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="b8ac5-132">진행 중 관리</span><span class="sxs-lookup"><span data-stu-id="b8ac5-132">Ongoing management</span></span>

<span data-ttu-id="b8ac5-133">Azure Monitor를 사용하여 Microsoft Teams Rooms 디바이스를 관리하는 동안 Azure Monitor에서 사용하는 이벤트 로그에 포함된 정보를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="b8ac5-134">이러한 [상태 메시지에](azure-monitor-manage.md#understand-the-log-entries) 대한 자세한 내용은 로그 항목 이해를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ac5-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="b8ac5-135">관련 작업</span><span class="sxs-lookup"><span data-stu-id="b8ac5-135">Related Tasks</span></span>

- <span data-ttu-id="b8ac5-136">Microsoft Teams Rooms에서 생성된 경고와 이를 해결하는 방법을 이해합니다(로그 항목 이해 섹션 [참조)](azure-monitor-manage.md#understand-the-log-entries)</span><span class="sxs-lookup"><span data-stu-id="b8ac5-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b8ac5-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8ac5-137">See also</span></span>

[<span data-ttu-id="b8ac5-138">Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 배포</span><span class="sxs-lookup"><span data-stu-id="b8ac5-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="b8ac5-139">Azure Monitor를 사용하여 Microsoft Teams Rooms 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="b8ac5-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)