---
title: Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 계획
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
description: 이 문서에서는 비즈니스용 Skype 또는 팀 구현에서 Azure Monitor를 사용 하 여 Microsoft 팀 회의실 장치를 관리 하기 위한 계획 고려 사항에 대해 설명 합니다.
ms.openlocfilehash: 4fdf5d80b88a973cf1a1132775c7b0cc85e5cc18
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826116"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="6a325-103">Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 계획</span><span class="sxs-lookup"><span data-stu-id="6a325-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="6a325-104">이 문서에서는 Azure Monitor를 사용 하 여 Microsoft 팀 또는 비즈니스용 Skype 구현에서 Microsoft 팀 회의실 장치를 관리 하기 위한 계획 고려 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="6a325-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) 는 시작부터 클라우드에서 설계 된 관리 서비스의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="6a325-106">Azure는 온-프레미스 리소스를 배포 및 관리 하는 대신 Azure에서 완전히 호스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="6a325-107">구성은 미미 하 고, 몇 분 내에 문자 그대로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="6a325-108">일부 사용자 지정 작업을 사용 하면 개별 룸 시스템에 대 한 시스템 상태 또는 오류에 대 한 실시간 알림을 제공 하 여 Microsoft 팀 회의실 회의 시스템을 관리 하는 데 도움이 될 수 있으며, 수천 개의 Microsoft 팀을 관리 하는 일이 발생할 수 있습니다. 회의실 회의실.</span><span class="sxs-lookup"><span data-stu-id="6a325-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="6a325-109">이 문서에서는 microsoft 팀 회의실 회의 디바이스의 Azure Monitor 기반 관리를 구현 하는 데 필요한 요구 사항, 디자인/아키텍처 및 구현 모범 사례에 대해 설명 하 고 microsoft 팀 대화방에 대 한 Azure 모니터 구현에 대 한 자세한 문서 링크를 제공 하 고 팀 대화방의 지속적인 모니터링을 위한 중요 참조 정보에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="6a325-110">기능 개요</span><span class="sxs-lookup"><span data-stu-id="6a325-110">Functional overview</span></span>

![Azure 모니터를 사용 하는 Microsoft 팀 회의실 관리 다이어그램](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="6a325-112">콘솔 장치의 Microsoft 팀 대화방 앱은 Windows 이벤트 로그에 이벤트를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="6a325-113">Microsoft Monitoring agent가 설치 된 후에는 해당 정보를 Azure 모니터 서비스에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="6a325-114">올바르게 구성 되 면 로그 분석은 이벤트 설명에 포함 된 JSON 페이로드를 구문 분석 하 여 각 Microsoft 팀 대화방 시스템이 작동 하는 방식과 감지 되는 결함을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="6a325-115">Azure 모니터를 사용 하는 관리자는 오프 라인 상태 이거나 앱, 연결 또는 하드웨어 오류와 시스템을 다시 시작 해야 하는지 여부를 알고 있는 Microsoft 팀 대화방 시스템에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="6a325-116">각 시스템 상태는 자주 업데이트 되므로 이러한 알림은 실시간 업데이트와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="6a325-117">Azure 모니터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a325-117">Azure Monitor requirements</span></span>

<span data-ttu-id="6a325-118">Log Analytics 기능을 사용 하려면 Azure Monitor에 대 한 유효한 Azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="6a325-119">조직에 대 한 구독을 만들려면 [Log Analytics 작업 영역 시작](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a325-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="6a325-120">로그 분석 보기 디자이너를 사용 하는 방법에 대해서는 필요에 따라 숙지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="6a325-121">[로그 분석에서](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) 해당 세부 정보에 대 한 보기를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a325-121">See [Views in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="6a325-122">관련 작업</span><span class="sxs-lookup"><span data-stu-id="6a325-122">Related Tasks</span></span>

1. <span data-ttu-id="6a325-123">Azure 모니터 로그 분석을 구독 한 후에는 Microsoft 팀 대화방 콘솔에서 전송 되는 정보를 구문 분석 하는 데 필요한 사용자 지정 필드 ( [Map 사용자 지정 필드](azure-monitor-deploy.md#Custom_fields)에 설명 된 대로)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="6a325-124">여기에는 [로그 항목을 이해](azure-monitor-manage.md#understand-the-log-entries)하는 데 문서화 된 JSON 스키마에 대 한 이해가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="6a325-125">로그 분석에서 Microsoft 팀 회의실 관리 보기를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="6a325-126">[Import 메서드를 사용 하 여 Microsoft 팀 회의실 대시보드를 만들거나](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) [수동으로 microsoft 팀 대화방 대시보드를 만들](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="6a325-127">개별 Microsoft 팀 공간 콘솔 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a325-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="6a325-128">각 Microsoft 팀 대화방 콘솔은 키오스크 모드의 Surface Pro 장치에서 실행 되는 앱으로, 일반적으로 장치에서 실행할 수 있는 유일한 앱으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="6a325-129">모든 Windows 앱에서와 마찬가지로 Microsoft 팀 대화방 앱은 시작 및 하드웨어 폴트와 같은 이벤트를 Windows 이벤트 로그에 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="6a325-130">Microsoft 팀 대화방 장치에 Microsoft 모니터 에이전트를 추가 하면 이러한 이벤트를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="6a325-131">(자세한 내용은 [Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결을](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="6a325-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="6a325-132">지속적인 관리</span><span class="sxs-lookup"><span data-stu-id="6a325-132">Ongoing management</span></span>

<span data-ttu-id="6a325-133">Azure Monitor를 사용 하 여 Microsoft 팀 공간 장치를 관리 하는 동안 Azure Monitor에서 사용 되는 이벤트 로그에 포함 된 정보를 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a325-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="6a325-134">이러한 상태 메시지에 대 한 자세한 내용은 [로그 항목 이해](azure-monitor-manage.md#understand-the-log-entries) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a325-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="6a325-135">관련 작업</span><span class="sxs-lookup"><span data-stu-id="6a325-135">Related Tasks</span></span>

- <span data-ttu-id="6a325-136">Microsoft 팀 대화방에서 생성 된 알림과이를 해결 하는 방법 이해 ( [로그 항목 이해](azure-monitor-manage.md#understand-the-log-entries)섹션 참조)</span><span class="sxs-lookup"><span data-stu-id="6a325-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a325-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a325-137">See also</span></span>

[<span data-ttu-id="6a325-138">Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 배포</span><span class="sxs-lookup"><span data-stu-id="6a325-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="6a325-139">Azure Monitor를 사용 하 여 Microsoft 팀 회의실 장치 관리</span><span class="sxs-lookup"><span data-stu-id="6a325-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)