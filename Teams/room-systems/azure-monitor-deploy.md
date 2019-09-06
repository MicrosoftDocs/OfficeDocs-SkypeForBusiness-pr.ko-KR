---
title: Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 배포
ms.author: v-lanac
author: lanachin
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 이 문서에서는 Azure Monitor를 사용 하 여 통합 된 종단 간 방식으로 Microsoft 팀 회의실 디바이스의 관리를 배포 하는 방법을 설명 합니다.
ms.openlocfilehash: 4be57f97ef3b0813afef2aefd70c551ee50422ee
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774687"
---
# <a name="deploy-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="4aabe-103">Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 배포</span><span class="sxs-lookup"><span data-stu-id="4aabe-103">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>

<span data-ttu-id="4aabe-104">이 문서에서는 Azure Monitor를 사용 하 여 Microsoft 팀 회의실 디바이스의 통합 된 종단간 관리를 설정 하 고 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-104">This article discusses how to set up and deploy integrated, end-to-end management of Microsoft Teams Rooms devices by using Azure Monitor.</span></span>

<span data-ttu-id="4aabe-105">Azure Monitor 내에서 로그 분석을 구성 하 여 Microsoft 팀 회의실 모임 채팅방 장치를 관리 하는 데 도움이 되는 기본 원격 분석 및 알림을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-105">You can configure Log Analytics within Azure Monitor to provide basic telemetry and alerts that will help you manage Microsoft Teams Rooms meeting room devices.</span></span> <span data-ttu-id="4aabe-106">관리 솔루션이 완성 됨에 따라 추가 데이터 및 관리 기능을 배포 하 여 디바이스 가용성 및 성능에 대 한 자세한 뷰를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="4aabe-107">이 가이드를 팔 로우 하는 다음 예제와 같은 대시보드를 사용 하 여 장치 가용성, 응용 프로그램 및 하드웨어 상태, Microsoft 팀 대화방 응용 프로그램 및 운영 체제 버전 배포에 대 한 자세한 상태 보고를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and Microsoft Teams Rooms application and operating system version distribution.</span></span>

<span data-ttu-id="4aabe-108">![Microsoft 팀 대화방에 대 한 샘플 로그 분석 보기 스크린샷] (../media/Deploy-Azure-Monitor-1.png "Microsoft 팀 대화방에 대 한 예제 로그 분석 보기")</span><span class="sxs-lookup"><span data-stu-id="4aabe-108">![Screen shot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="4aabe-109">상위 수준에서 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="4aabe-110">로그 분석 구성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4aabe-110">Validate Log Analytics configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="4aabe-111">로그 분석 관리 설정에 맞게 테스트 장치 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-111">Configure test devices for Log Analytics management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="4aabe-112">사용자 지정 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="4aabe-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="4aabe-113">로그 분석에서 Microsoft 팀 회의실 보기 정의</span><span class="sxs-lookup"><span data-stu-id="4aabe-113">Define the Microsoft Teams Rooms views in Log Analytics</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="4aabe-114">알림 정의</span><span class="sxs-lookup"><span data-stu-id="4aabe-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="4aabe-115">모든 장치에서 모니터링 하도록 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="4aabe-116">추가 Azure Monitor 솔루션 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-116">Configure additional Azure Monitor solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="4aabe-117">최소 구성으로 Azure 모니터 로그 분석을 사용 하면 Windows 운영 체제를 실행 하는 컴퓨터를 모니터링할 수 있지만, 모든 Microsoft 팀에 에이전트 배포를 시작 하기 전에 수행 해야 하는 일부 Microsoft 팀 대화방 관련 단계가 남아 있습니다. 채팅방 장치.</span><span class="sxs-lookup"><span data-stu-id="4aabe-117">Although with minimal configuration, Azure Monitor Log Analytics can monitor a computer running a Windows operating system, there are still some Microsoft Teams Rooms–specific steps that you need to take before you start deploying agents to all Microsoft Teams Rooms devices.</span></span>
> <span data-ttu-id="4aabe-118">따라서 제어 된 설정 및 구성에 대 한 올바른 순서 대로 모든 구성 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="4aabe-119">최종 결과의 품질은 초기 구성의 품질에 따라 크게 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-log-analytics-configuration"></a><span data-ttu-id="4aabe-120">로그 분석 구성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4aabe-120">Validate Log Analytics configuration</span></span>
<span data-ttu-id="4aabe-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="4aabe-121"></span></span>

<span data-ttu-id="4aabe-122">Microsoft 팀 대화방 장치에서 로그 수집을 시작 하려면 로그 분석 작업 영역이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-122">You need to have a Log Analytics workspace to start collecting logs from Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="4aabe-123">작업 영역은 고유한 데이터 리포지토리, 데이터 원본 및 솔루션이 있는 고유한 로그 분석 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-123">A workspace is a unique Log Analytics environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="4aabe-124">기존 로그 분석 작업 영역이 이미 있는 경우이를 사용 하 여 Microsoft 팀 회의실 배포를 모니터링 하거나 Microsoft 팀 회의실 모니터링 요구 사항에 따라 전용 로그 분석 작업 영역을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-124">If you already have an existing Log Analytics workspace, you might use it to monitor your Microsoft Teams Rooms deployment or alternatively, you can create a dedicated Log Analytics workspace specific to your Microsoft Teams Rooms monitoring needs.</span></span>

<span data-ttu-id="4aabe-125">새 Log Analytics 작업 영역을 만들어야 하는 경우 [Azure 포털에서 로그 분석 작업 영역 만들기](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 문서의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-125">If you need to create a new Log Analytics workspace, follow the instructions in the article [Create a Log Analytics workspace in the Azure portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="4aabe-126">Azure 모니터에서 로그 분석을 사용 하려면 활성 Azure 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-126">To use Log Analytics with Azure Monitor, you need to have an active Azure subscription.</span></span> <span data-ttu-id="4aabe-127">Azure 구독이 없는 경우에는 [무료 평가판 구독을](https://azure.microsoft.com/free) 시작 점으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-127">If you don’t have an Azure subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-log-analytics-to-collect-microsoft-teams-rooms-event-logs"></a><span data-ttu-id="4aabe-128">Microsoft 팀 대화방 이벤트 로그를 수집 하도록 로그 분석 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-128">Configure Log Analytics to collect Microsoft Teams Rooms event logs</span></span>

<span data-ttu-id="4aabe-129">로그 분석은 설정에 지정 된 Windows 이벤트 로그 에서만 이벤트를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-129">Log Analytics only collects events from the Windows event logs that are specified in the settings.</span></span> <span data-ttu-id="4aabe-130">각 로그에는 선택한 심각도의 이벤트만 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="4aabe-131">Microsoft 팀 대화방 장치 및 응용 프로그램 상태를 모니터링 하는 데 필요한 로그를 수집 하도록 로그 분석을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-131">You need to configure Log Analytics to collect the logs required to monitor Microsoft Teams Rooms device and application status.</span></span> <span data-ttu-id="4aabe-132">Microsoft 팀 대화방 장치는 **Skype 대화방 시스템** 이벤트 로그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-132">Microsoft Teams Rooms devices use the **Skype Room System** event log.</span></span>

<span data-ttu-id="4aabe-133">Microsoft 팀 대화방 이벤트를 수집 하도록 로그 분석을 구성 하려면 [Azure 모니터의 Windows 이벤트 로그 데이터 원본](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4aabe-133">To configure Log Analytics to collect the Microsoft Teams Rooms events, see [Windows event log data sources in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="4aabe-134">![이벤트 로그 설정] 스크린샷 (../media/Deploy-Azure-Monitor-2.png "이벤트 로그 설정")</span><span class="sxs-lookup"><span data-stu-id="4aabe-134">![Screen shot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4aabe-135">Windows 이벤트 로그 설정을 구성 하 고 **Skype 대화방 시스템** 을 이벤트 로그 이름으로 입력 한 다음 **오류**, **경고**및 **정보** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-135">Configure Windows Event Log settings and enter **Skype Room System** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="4aabe-136">Azure 모니터링을 위한 테스트 장치 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="4aabe-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="4aabe-137"></span></span>

<span data-ttu-id="4aabe-138">Microsoft 팀 대화방 관련 이벤트를 모니터링 하려면 로그 분석을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-138">You need to prepare Log Analytics to be able to monitor Microsoft Teams Rooms–related events.</span></span> <span data-ttu-id="4aabe-139">먼저, 물리적으로 액세스할 수 있는 Microsoft 팀 회의실 장치 하나 또는 두 개에 Microsoft Monitoring agent를 배포 하 고 해당 테스트 장치에서 일부 데이터를 생성 하 고 로그 분석 작업 영역에 푸시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-139">To start with, you need to deploy Microsoft Monitoring agents to just one or two Microsoft Teams Rooms devices that you have physical access to, and get those test devices generate some data and push it to the Log Analytics workspace.</span></span>

### <a name="install-microsoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="4aabe-140">Microsoft Monitoring agent를 설치 하 여 장치 테스트</span><span class="sxs-lookup"><span data-stu-id="4aabe-140">Install Microsoft Monitoring agents to test devices</span></span>

<span data-ttu-id="4aabe-141">[Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)에 제공 된 지침을 사용 하 여 Microsoft Monitoring agent를 테스트 디바이스에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-141">Deploy the Microsoft Monitoring agent to the test devices by using the instructions provided in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="4aabe-142">이 문서에서는 Windows 용 Microsoft Monitoring Agent를 ***배포 하는*** 단계, 로그 분석 ***작업 영역 ID*** 를 구하는 방법, microsoft 팀 대화방 장치를 가져오는 방법에 대 한 자세한 내용 Azure 모니터 배포 및 로그 분석 인스턴스에 대 한 에이전트 연결을 확인 하는 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-142">This article provides detailed information about the steps for deploying Microsoft Monitoring Agent for Windows, instructions for obtaining the Log Analytics ***Workspace ID*** and the ***primary key*** to get Microsoft Teams Rooms devices connected to your Azure Monitor deployment, and steps to verify agent connectivity to Log Analytics instance.</span></span>

### <a name="generate-sample-microsoft-teams-rooms-events"></a><span data-ttu-id="4aabe-143">샘플 Microsoft 팀 대화방 이벤트 생성</span><span class="sxs-lookup"><span data-stu-id="4aabe-143">Generate sample Microsoft Teams Rooms events</span></span>

<span data-ttu-id="4aabe-144">Microsoft Monitoring agent가 테스트 장치에 배포 된 후에는 필요한 이벤트 로그 데이터가 Azure Monitor에서 수집 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-144">After the Microsoft Monitoring agent is deployed onto the test devices, verify that the required event log data is collected by Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="4aabe-145">Microsoft Monitoring agent를 설치한 후 장치를 다시 부팅 하 고 Microsoft 팀 대화방 모임 앱이 시작 되었는지 확인 하 여 이벤트 로그에 새 이벤트를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-145">Reboot the device after the installation of the Microsoft Monitoring agent, and make sure that Microsoft Teams Rooms Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="4aabe-146">[Microsoft Azure 포털](https://portal.azure.com) 에 로그인 하 고 로그 분석으로 이동 하 여 작업 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-146">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2.  <span data-ttu-id="4aabe-147">Microsoft 팀 대화방 장치에서 생성 된 하트 비트 이벤트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-147">List the heartbeat events generated by a Microsoft Teams Rooms device:</span></span>
    1.  <span data-ttu-id="4aabe-148">작업 영역을 선택 하 고 **로그** 로 이동한 다음 쿼리를 사용 하 여 Microsoft 팀 대화방에 대 한 사용자 지정 필드가 포함 된 하트 비트 레코드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-148">Select your workspace and go to **Logs** and use a query to retrieve the heartbeat records that will have the custom fields for Microsoft Teams Rooms.</span></span>
    2.  <span data-ttu-id="4aabe-149">쿼리 예제:`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="4aabe-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="4aabe-150">쿼리가 Microsoft 팀 회의실 모임 앱에서 생성 된 이벤트를 포함 하는 로그 레코드를 반환 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-150">Make sure that the query returns log records that include events generated by the Microsoft Teams Rooms meetings app.</span></span>

4.  <span data-ttu-id="4aabe-151">하드웨어 문제를 생성 하 고 필수 이벤트가 Azure 로그 분석에 기록 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-151">Generate a hardware issue, and validate that the required events are logged in Azure Log Analytics.</span></span>
    1.  <span data-ttu-id="4aabe-152">Microsoft 팀 대화방 테스트 시스템에서 주변 장치 중 하나를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-152">Unplug one of the peripheral devices on the test Microsoft Teams Rooms system.</span></span> <span data-ttu-id="4aabe-153">카메라, 스피커폰, 마이크 또는 프론트 실 디스플레이로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="4aabe-154">Azure 로그 분석에서 이벤트 로그가 채워질 때까지 10 분간 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-154">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="4aabe-155">쿼리를 사용 하 여 하드웨어 오류 이벤트 나열:`Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="4aabe-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="4aabe-156">응용 프로그램 문제를 생성 하 고 필요한 이벤트가 기록 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="4aabe-157">Microsoft 팀 대화방 응용 프로그램 구성을 수정 하 고 잘못 된 SIP (세션 초기화 프로토콜) 주소/암호 쌍을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-157">Modify Microsoft Teams Rooms application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="4aabe-158">Azure 로그 분석에서 이벤트 로그가 채워질 때까지 10 분간 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-158">Wait 10 minutes for the event log to be populated in Azure Log Analytics.</span></span>
    3.  <span data-ttu-id="4aabe-159">쿼리를 사용 하 여 응용 프로그램 오류 이벤트 나열:`Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="4aabe-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4aabe-160">사용자 지정 필드를 구성 하려면이 샘플 이벤트 로그가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="4aabe-161">필요한 이벤트 로그를 수집할 때까지 다음 단계로 진행 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4aabe-161">Don’t proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="4aabe-162">사용자 지정 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="4aabe-162">Map custom fields</span></span>
<span data-ttu-id="4aabe-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="4aabe-163"></span></span>

<span data-ttu-id="4aabe-164">사용자 지정 필드를 사용 하 여 이벤트 로그에서 특정 데이터를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="4aabe-165">나중에 타일, 대시보드 보기 및 알림과 함께 사용 될 사용자 지정 필드를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="4aabe-166">사용자 지정 필드 만들기를 시작 하기 전에 [로그 분석에서 사용자 지정 필드](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) 를 확인 하 고 개념을 익힙니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-166">See [Custom fields in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="4aabe-167">캡처한 이벤트 로그에서 사용자 지정 필드의 압축을 풀려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="4aabe-168">[Microsoft Azure 포털](https://portal.azure.com) 에 로그인 하 고 로그 분석으로 이동 하 여 작업 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-168">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="4aabe-169">Microsoft 팀 대화방 장치에서 생성 된 이벤트를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-169">List the events generated by a Microsoft Teams Rooms device:</span></span>
   1.  <span data-ttu-id="4aabe-170">**로그** 로 이동 하 여 쿼리를 사용 하 여 사용자 정의 필드를 포함 하는 레코드를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="4aabe-171">쿼리 예제:`Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="4aabe-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="4aabe-172">레코드 중 하나를 선택 하 고 왼쪽에 있는 단추를 선택한 다음 필드 추출 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="4aabe-173">RenderedDescription에서 추출 하려는 데이터를 강조 표시 하 고 필드 제목을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-173">Highlight the data you’d like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="4aabe-174">사용 해야 하는 필드 이름은 표 1에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-174">The field names that you should use are provided in Table 1.</span></span>

   <span data-ttu-id="4aabe-175">![사용자 지정 필드 정의] (../media/Deploy-Azure-Monitor-4.png "사용자 지정 필드 정의")</span><span class="sxs-lookup"><span data-stu-id="4aabe-175">![Custom field definition](../media/Deploy-Azure-Monitor-4.png "Custom field definition")</span></span>

5. <span data-ttu-id="4aabe-176">*표 1*에 표시 된 매핑을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-176">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="4aabe-177">새 필드를 정의할 때 로그 분석에서 \*\* \_CF\*\* 문자열이 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-177">Log Analytics will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4aabe-178">모든 JSON 및 Log Analytics 필드는 대/소문자를 구분 한다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-178">Remember that all JSON and Log Analytics fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="4aabe-179">아래 표의 각 사용자 정의 필드에 필요한 쿼리를 주의 해 서 살펴 보세요.</span><span class="sxs-lookup"><span data-stu-id="4aabe-179">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="4aabe-180">사용자 지정 필드 값을 성공적으로 추출 하려면 Log Analytics 용 올바른 쿼리를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-180">You need to use the correct queries for Log Analytics to successfully extract custom field values.</span></span>
> 
 <span data-ttu-id="4aabe-181">![사용자 지정 필드 정의] (../media/Deploy-Azure-Monitor-5.png "사용자 지정 필드 정의")</span><span class="sxs-lookup"><span data-stu-id="4aabe-181">![Custom field definition](../media/Deploy-Azure-Monitor-5.png "Custom field definition")</span></span>

<span data-ttu-id="4aabe-182">**표 1**</span><span class="sxs-lookup"><span data-stu-id="4aabe-182">**Table 1**</span></span>

| <span data-ttu-id="4aabe-183">**JSON 필드**</span><span class="sxs-lookup"><span data-stu-id="4aabe-183">**JSON field**</span></span>                   | <span data-ttu-id="4aabe-184">**로그 분석 사용자 지정 필드**</span><span class="sxs-lookup"><span data-stu-id="4aabe-184">**Log Analytics custom field**</span></span> | <span data-ttu-id="4aabe-185">**이벤트 ID**</span><span class="sxs-lookup"><span data-stu-id="4aabe-185">**Event ID**</span></span> | <span data-ttu-id="4aabe-186">**추출에 사용할 쿼리**</span><span class="sxs-lookup"><span data-stu-id="4aabe-186">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="4aabe-187">설명</span><span class="sxs-lookup"><span data-stu-id="4aabe-187">Description</span></span>                      | <span data-ttu-id="4aabe-188">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="4aabe-188">SRSEventDescription</span></span>         | <span data-ttu-id="4aabe-189">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-189">**2000**</span></span>     | <span data-ttu-id="4aabe-190">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-190">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-191">ResourceState</span><span class="sxs-lookup"><span data-stu-id="4aabe-191">ResourceState</span></span>                    | <span data-ttu-id="4aabe-192">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="4aabe-192">SRSResourceState</span></span>            | <span data-ttu-id="4aabe-193">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-193">**2000**</span></span>     | <span data-ttu-id="4aabe-194">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-194">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-195">OperationName</span><span class="sxs-lookup"><span data-stu-id="4aabe-195">OperationName</span></span>                    | <span data-ttu-id="4aabe-196">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="4aabe-196">SRSOperationName</span></span>            | <span data-ttu-id="4aabe-197">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-197">**2000**</span></span>     | <span data-ttu-id="4aabe-198">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-198">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-199">OperationResult</span><span class="sxs-lookup"><span data-stu-id="4aabe-199">OperationResult</span></span>                  | <span data-ttu-id="4aabe-200">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="4aabe-200">SRSOperationResult</span></span>          | <span data-ttu-id="4aabe-201">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-201">**2000**</span></span>     | <span data-ttu-id="4aabe-202">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-202">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-203">변경할</span><span class="sxs-lookup"><span data-stu-id="4aabe-203">OS</span></span>                               | <span data-ttu-id="4aabe-204">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="4aabe-204">SRSOSVersion</span></span>                | <span data-ttu-id="4aabe-205">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-205">**2000**</span></span>     | <span data-ttu-id="4aabe-206">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-206">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-207">OSVersion</span><span class="sxs-lookup"><span data-stu-id="4aabe-207">OSVersion</span></span>                        | <span data-ttu-id="4aabe-208">Srsos# 버전</span><span class="sxs-lookup"><span data-stu-id="4aabe-208">SRSOSLongVersion</span></span>            | <span data-ttu-id="4aabe-209">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-209">**2000**</span></span>     | <span data-ttu-id="4aabe-210">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-210">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-211">별칭인</span><span class="sxs-lookup"><span data-stu-id="4aabe-211">Alias</span></span>                            | <span data-ttu-id="4aabe-212">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="4aabe-212">SRSAlias</span></span>                    | <span data-ttu-id="4aabe-213">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-213">**2000**</span></span>     | <span data-ttu-id="4aabe-214">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-214">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-215">이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-215">DisplayName</span></span>                      | <span data-ttu-id="4aabe-216">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="4aabe-216">SRSDisplayName</span></span>              | <span data-ttu-id="4aabe-217">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-217">**2000**</span></span>     | <span data-ttu-id="4aabe-218">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-218">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-219">AppVersion</span><span class="sxs-lookup"><span data-stu-id="4aabe-219">AppVersion</span></span>                       | <span data-ttu-id="4aabe-220">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="4aabe-220">SRSAppVersion</span></span>               | <span data-ttu-id="4aabe-221">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-221">**2000**</span></span>     | <span data-ttu-id="4aabe-222">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-222">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-223">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="4aabe-223">IPv4Address</span></span>                      | <span data-ttu-id="4aabe-224">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="4aabe-224">SRSIPv4Address</span></span>              | <span data-ttu-id="4aabe-225">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-225">**2000**</span></span>     | <span data-ttu-id="4aabe-226">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-226">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-227">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="4aabe-227">IPv6Address</span></span>                      | <span data-ttu-id="4aabe-228">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="4aabe-228">SRSIPv6Address</span></span>              | <span data-ttu-id="4aabe-229">**2000**</span><span class="sxs-lookup"><span data-stu-id="4aabe-229">**2000**</span></span>     | <span data-ttu-id="4aabe-230">Source \| = = "SRS-App" 및 EventID = = 2000 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-230">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="4aabe-231">회의 마이크 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-231">Conference Microphone status</span></span>     | <span data-ttu-id="4aabe-232">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="4aabe-232">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="4aabe-233">**3001**</span><span class="sxs-lookup"><span data-stu-id="4aabe-233">**3001**</span></span>     | <span data-ttu-id="4aabe-234">Source \| = = "SRS-App" 및 EventID = = 3001 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-234">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="4aabe-235">컨퍼런스 스피커 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-235">Conference Speaker status</span></span>        | <span data-ttu-id="4aabe-236">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="4aabe-236">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="4aabe-237">**3001**</span><span class="sxs-lookup"><span data-stu-id="4aabe-237">**3001**</span></span>     | <span data-ttu-id="4aabe-238">Source \| = = "SRS-App" 및 EventID = = 3001 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-238">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="4aabe-239">기본 스피커 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-239">Default Speaker status</span></span>           | <span data-ttu-id="4aabe-240">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="4aabe-240">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="4aabe-241">**3001**</span><span class="sxs-lookup"><span data-stu-id="4aabe-241">**3001**</span></span>     | <span data-ttu-id="4aabe-242">Source \| = = "SRS-App" 및 EventID = = 3001 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-242">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="4aabe-243">카메라 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-243">Camera status</span></span>                    | <span data-ttu-id="4aabe-244">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="4aabe-244">SRSCameraStatus</span></span>             | <span data-ttu-id="4aabe-245">**3001**</span><span class="sxs-lookup"><span data-stu-id="4aabe-245">**3001**</span></span>     | <span data-ttu-id="4aabe-246">Source \| = = "SRS-App" 및 EventID = = 3001 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-246">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="4aabe-247">방 표시 상태 앞</span><span class="sxs-lookup"><span data-stu-id="4aabe-247">Front of Room Display status</span></span>     | <span data-ttu-id="4aabe-248">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="4aabe-248">SRSFORDStatus</span></span>               | <span data-ttu-id="4aabe-249">**3001**</span><span class="sxs-lookup"><span data-stu-id="4aabe-249">**3001**</span></span>     | <span data-ttu-id="4aabe-250">Source \| = = "SRS-App" 및 EventID = = 3001 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-250">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="4aabe-251">동작 센서 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-251">Motion Sensor status</span></span>             | <span data-ttu-id="4aabe-252">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="4aabe-252">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="4aabe-253">**3001**</span><span class="sxs-lookup"><span data-stu-id="4aabe-253">**3001**</span></span>     | <span data-ttu-id="4aabe-254">Source \| = = "SRS-App" 및 EventID = = 3001 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-254">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="4aabe-255">HDMI 수집 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-255">HDMI Ingest status</span></span>               | <span data-ttu-id="4aabe-256">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="4aabe-256">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="4aabe-257">**3001**</span><span class="sxs-lookup"><span data-stu-id="4aabe-257">**3001**</span></span>     | <span data-ttu-id="4aabe-258">Source \| = = "SRS-App" 및 EventID = = 3001 이벤트</span><span class="sxs-lookup"><span data-stu-id="4aabe-258">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-microsoft-teams-rooms-views-in-log-analytics"></a><span data-ttu-id="4aabe-259">로그 분석에서 Microsoft 팀 회의실 보기 정의</span><span class="sxs-lookup"><span data-stu-id="4aabe-259">Define the Microsoft Teams Rooms views in Log Analytics</span></span>
<span data-ttu-id="4aabe-260"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="4aabe-260"></span></span>

<span data-ttu-id="4aabe-261">데이터를 수집 하 고 사용자 지정 필드를 매핑한 후에는 보기 디자이너를 사용 하 여 Microsoft 팀 대화방 이벤트를 모니터링 하는 다양 한 타일이 포함 된 대시보드를 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-261">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor Microsoft Teams Rooms events.</span></span> <span data-ttu-id="4aabe-262">보기 디자이너를 사용 하 여 다음 타일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-262">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="4aabe-263">자세한 내용은 [로그 분석에서 뷰 디자이너를 사용 하 여 사용자 지정 보기 만들기](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4aabe-263">For more information, see [Create custom views by using View Designer in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="4aabe-264">대시보드 타일이 제대로 작동 하려면이 가이드의 이전 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-264">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="4aabe-265">Import 메서드를 사용 하 여 Microsoft 팀 회의실 대시보드 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-265">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="4aabe-266">Microsoft 팀 회의실 대시보드를 가져와 장치 모니터링을 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-266">You can import an Microsoft Teams Rooms dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="4aabe-267">대시보드를 가져오려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-267">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="4aabe-268">[SkypeRoomSystems_v2 omsview](https://go.microsoft.com/fwlink/?linkid=835675) 대시보드 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-268">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="4aabe-269">[Microsoft Azure 포털](https://portal.azure.com) 에 로그인 하 고 로그 분석으로 이동 하 여 작업 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-269">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>
3.  <span data-ttu-id="4aabe-270">**뷰 디자이너**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-270">Open **View Designer**.</span></span>
4.  <span data-ttu-id="4aabe-271">**가져오기를**선택 하 고 **SkypeRoomSystems_v2 omsview** 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-271">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="4aabe-272">**저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-272">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="4aabe-273">수동으로 Microsoft 팀 대화방 대시보드 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-273">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="4aabe-274">또는 직접 대시보드를 만들어 모니터링할 타일만 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-274">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="4aabe-275">개요 타일 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-275">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="4aabe-276">**뷰 디자이너**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-276">Open **View Designer**.</span></span>
2.  <span data-ttu-id="4aabe-277">**개요 타일**을 선택 하 고 갤러리에서 **두 숫자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-277">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="4aabe-278">타일의 이름을 **Microsoft 팀 회의실**으로 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-278">Name the tile **Microsoft Teams Rooms**.</span></span>
4.  <span data-ttu-id="4aabe-279">**첫 번째 타일**을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-279">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="4aabe-280">**범례:** 지난 달에 하트 비트를 한 번 이상 보낸 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-280">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="4aabe-281">**쿼리:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="4aabe-281">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="4aabe-282">**두 번째 타일**을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-282">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="4aabe-283">**범례:** 지난 시간 내에 하트 비트를 보낸 활성 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-283">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="4aabe-284">**쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="4aabe-284">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="4aabe-285">**적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-285">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="4aabe-286">활성 장치를 표시 하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-286">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="4aabe-287">**대시보드 보기** 를 선택 하 여 타일 추가를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-287">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="4aabe-288">갤러리에서 **번호 & 목록을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-288">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="4aabe-289">**일반** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-289">Define the **General** properties:</span></span><br>
    <span data-ttu-id="4aabe-290">**그룹 제목:** 하트 비트 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-290">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="4aabe-291">**새 그룹:** 선택한</span><span class="sxs-lookup"><span data-stu-id="4aabe-291">**New Group:** Selected</span></span>
4.  <span data-ttu-id="4aabe-292">**타일** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-292">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="4aabe-293">**범례:** 활성 장치 (지난 20 분 동안 보낸 하트 비트)</span><span class="sxs-lookup"><span data-stu-id="4aabe-293">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="4aabe-294">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="4aabe-294">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="4aabe-295">**목록** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-295">Define the **List** properties:</span></span><br>
    <span data-ttu-id="4aabe-296">**목록 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="4aabe-296">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="4aabe-297">**열 제목**정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-297">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="4aabe-298">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-298">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="4aabe-299">**값:** 마지막 하트 비트</span><span class="sxs-lookup"><span data-stu-id="4aabe-299">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="4aabe-300">**탐색 쿼리**를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-300">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="4aabe-301">**적용**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-301">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="4aabe-302">연결 문제가 있는 장치를 표시 하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-302">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="4aabe-303">갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-303">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="4aabe-304">**일반** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-304">Define the **General** properties:</span></span><br>
    <span data-ttu-id="4aabe-305">**그룹 제목:** 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-305">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="4aabe-306">**새 그룹:** 선택 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4aabe-306">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="4aabe-307">**타일** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-307">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="4aabe-308">**범례:** 비활성 장치 (지난 20 분 동안 보낸 하트 비트 메시지가 없음)</span><span class="sxs-lookup"><span data-stu-id="4aabe-308">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="4aabe-309">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="4aabe-309">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="4aabe-310">**목록** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-310">Define the **List** properties:</span></span><br>
    <span data-ttu-id="4aabe-311">**목록 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="4aabe-311">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="4aabe-312">**열 제목**정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-312">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="4aabe-313">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-313">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="4aabe-314">**값:** 마지막 하트 비트</span><span class="sxs-lookup"><span data-stu-id="4aabe-314">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="4aabe-315">**탐색 쿼리**정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-315">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="4aabe-316">**적용**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-316">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="4aabe-317">하드웨어 오류가 있는 장치를 표시 하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-317">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="4aabe-318">갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-318">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="4aabe-319">**일반** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-319">Define the **General** properties:</span></span><br>
    <span data-ttu-id="4aabe-320">**그룹 제목:** 하드웨어 상태</span><span class="sxs-lookup"><span data-stu-id="4aabe-320">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="4aabe-321">**새 그룹:** 선택한</span><span class="sxs-lookup"><span data-stu-id="4aabe-321">**New Group:** Selected</span></span>
3.  <span data-ttu-id="4aabe-322">**타일** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-322">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="4aabe-323">**범례:** 지난 시간에 하드웨어 오류가 발생 한 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-323">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="4aabe-324">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="4aabe-324">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="4aabe-325">**목록** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-325">Define the **List** properties:</span></span><br>
    <span data-ttu-id="4aabe-326">**목록 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="4aabe-326">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="4aabe-327">**열 제목**정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-327">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="4aabe-328">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-328">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="4aabe-329">**값:** 마지막 오류</span><span class="sxs-lookup"><span data-stu-id="4aabe-329">**Value:** Last Error</span></span>
6.  <span data-ttu-id="4aabe-330">**탐색 쿼리**정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-330">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="4aabe-331">**적용**을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-331">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="4aabe-332">Microsoft 팀 방에 운영 체제 버전을 표시 하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-332">Create a tile that displays Microsoft Teams Rooms Operating System versions</span></span>

1.  <span data-ttu-id="4aabe-333">갤러리에서 **도넛 & 목록을** 선택한 다음 새 타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-333">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="4aabe-334">**일반** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-334">Define the **General** properties:</span></span><br>
    <span data-ttu-id="4aabe-335">**그룹 제목:** 운영 체제 세부 정보</span><span class="sxs-lookup"><span data-stu-id="4aabe-335">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="4aabe-336">**새 그룹:** 선택한</span><span class="sxs-lookup"><span data-stu-id="4aabe-336">**New Group:** Selected</span></span>
3.  <span data-ttu-id="4aabe-337">**헤더** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-337">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="4aabe-338">**제목:** 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="4aabe-338">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="4aabe-339">**자막:** 특정 OS 버전을 실행 하는 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-339">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="4aabe-340">**도넛** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-340">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="4aabe-341">**쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="4aabe-341">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="4aabe-342">**텍스트 가운데 맞춤:** 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-342">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="4aabe-343">**작업:** 총계</span><span class="sxs-lookup"><span data-stu-id="4aabe-343">**Operation:** Sum</span></span>
5.  <span data-ttu-id="4aabe-344">**목록** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-344">Define the **List** properties.</span></span><br>
    <span data-ttu-id="4aabe-345">**목록 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="4aabe-345">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="4aabe-346">**그래프 숨기기:** 선택한</span><span class="sxs-lookup"><span data-stu-id="4aabe-346">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="4aabe-347">**스파크 라인 사용:** 선택 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4aabe-347">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="4aabe-348">**열 제목을**정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-348">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="4aabe-349">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-349">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="4aabe-350">**값:** 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-350">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="4aabe-351">**탐색 쿼리**를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-351">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="4aabe-352">**적용** 을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-352">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-microsoft-teams-rooms-application-versions"></a><span data-ttu-id="4aabe-353">Microsoft 팀 대화방 응용 프로그램 버전을 표시 하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-353">Create a tile that displays Microsoft Teams Rooms application versions</span></span>

1.  <span data-ttu-id="4aabe-354">갤러리에서 **도넛 & 목록을** 선택한 다음 새 타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-354">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="4aabe-355">**일반** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-355">Define the **General** properties:</span></span><br>
    <span data-ttu-id="4aabe-356">**그룹 제목:** Microsoft 팀 대화방 응용 프로그램 세부 정보</span><span class="sxs-lookup"><span data-stu-id="4aabe-356">**Group Title:** Microsoft Teams Rooms application details</span></span><br>
    <span data-ttu-id="4aabe-357">**새 그룹:** 선택한</span><span class="sxs-lookup"><span data-stu-id="4aabe-357">**New Group:** Selected</span></span>
3.  <span data-ttu-id="4aabe-358">**헤더** 속성 정의:</span><span class="sxs-lookup"><span data-stu-id="4aabe-358">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="4aabe-359">**제목:** 응용 프로그램 버전</span><span class="sxs-lookup"><span data-stu-id="4aabe-359">**Title:** Application versions</span></span><br>
    <span data-ttu-id="4aabe-360">**자막:** 특정 응용 프로그램 버전을 실행 하는 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-360">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="4aabe-361">**도넛** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-361">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="4aabe-362">**쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="4aabe-362">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="4aabe-363">**텍스트 가운데 맞춤:** 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-363">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="4aabe-364">**작업:** 총계</span><span class="sxs-lookup"><span data-stu-id="4aabe-364">**Operation:** Sum</span></span>
5.  <span data-ttu-id="4aabe-365">**목록** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-365">Define the **List** properties.</span></span><br>
    <span data-ttu-id="4aabe-366">**목록 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="4aabe-366">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="4aabe-367">**그래프 숨기기:** 선택한</span><span class="sxs-lookup"><span data-stu-id="4aabe-367">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="4aabe-368">**스파크 라인 사용:** 선택 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4aabe-368">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="4aabe-369">**열 제목을**정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-369">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="4aabe-370">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-370">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="4aabe-371">**값:** 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-371">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="4aabe-372">**탐색 쿼리**를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-372">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="4aabe-373">**적용** 을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-373">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="4aabe-374">응용 프로그램 오류가 있는 장치를 표시 하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-374">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="4aabe-375">갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-375">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="4aabe-376">**일반** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-376">Define the **General** properties.</span></span><br>
    <span data-ttu-id="4aabe-377">**그룹 제목:** 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-377">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="4aabe-378">**새 그룹:** 선택 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4aabe-378">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="4aabe-379">**타일** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-379">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="4aabe-380">**범례:** 지난 시간에 응용 프로그램 오류가 발생 한 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-380">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="4aabe-381">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="4aabe-381">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="4aabe-382">**목록** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-382">Define the **List** properties.</span></span><br>
    <span data-ttu-id="4aabe-383">**목록 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="4aabe-383">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="4aabe-384">**열 제목을**정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-384">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="4aabe-385">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-385">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="4aabe-386">**값:** 마지막 오류</span><span class="sxs-lookup"><span data-stu-id="4aabe-386">**Value:** Last Error</span></span>
6.  <span data-ttu-id="4aabe-387">**탐색 쿼리**를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-387">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="4aabe-388">**적용** 을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-388">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="4aabe-389">다시 시작 된 장치를 표시 하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4aabe-389">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="4aabe-390">갤러리에서 **번호 & 목록을** 선택한 다음 새 타일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-390">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="4aabe-391">**일반** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-391">Define the **General** properties.</span></span><br>
    <span data-ttu-id="4aabe-392">**그룹 제목:** 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-392">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="4aabe-393">**새 그룹:** 선택 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4aabe-393">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="4aabe-394">**타일** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-394">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="4aabe-395">**범례:** 지난 24 시간 동안 응용 프로그램을 다시 시작 하 고 다시 시작할 수 있는 장치</span><span class="sxs-lookup"><span data-stu-id="4aabe-395">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="4aabe-396">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="4aabe-396">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="4aabe-397">**목록** 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-397">Define the **List** properties.</span></span><br>
    <span data-ttu-id="4aabe-398">**목록 쿼리:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="4aabe-398">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="4aabe-399">**열 제목을**정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-399">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="4aabe-400">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="4aabe-400">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="4aabe-401">**값:** 다시 시작 횟수</span><span class="sxs-lookup"><span data-stu-id="4aabe-401">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="4aabe-402">**탐색 쿼리**를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-402">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="4aabe-403">**적용** 을 선택한 다음 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-403">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="4aabe-404">**저장** 을 선택 하 여 대시보드를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-404">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="4aabe-405">이제 보기 만들기를 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-405">Now you’ve completed creating your views.</span></span>

## <a name="configure-alerts-in-azure-monitor"></a><span data-ttu-id="4aabe-406">Azure 모니터에서 알림 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-406">Configure Alerts in Azure Monitor</span></span>
<span data-ttu-id="4aabe-407"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="4aabe-407"></span></span>

<span data-ttu-id="4aabe-408">Microsoft 팀 회의실 콘솔에 문제가 발생할 경우 Azure 모니터는 알림을 발생 시켜 관리자에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-408">Azure Monitor can raise alerts to notify the administrators, when a Microsoft Teams Rooms console encounters an issue.</span></span>

<span data-ttu-id="4aabe-409">Azure 모니터에는 정기적인 간격으로 예약 된 로그 검색을 통해 실행 되는 기본 제공 경고 메커니즘이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-409">Azure Monitor includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="4aabe-410">로그 검색 결과가 특정 조건에 일치 하는 경우에는 경고 레코드가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-410">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="4aabe-411">그런 다음 규칙은 자동으로 하나 이상의 작업을 실행 하 여 사용자에 게 경고를 사전에 알리거나 다른 프로세스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-411">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="4aabe-412">알림과 관련 하 여 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-412">The possible options with alerts are:</span></span>
-   <span data-ttu-id="4aabe-413">전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="4aabe-413">Sending an email</span></span>
-   <span data-ttu-id="4aabe-414">HTTP POST 요청을 통해 외부 프로세스 호출</span><span class="sxs-lookup"><span data-stu-id="4aabe-414">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="4aabe-415">Azure Automation 서비스에서 runbook 시작</span><span class="sxs-lookup"><span data-stu-id="4aabe-415">Starting a runbook in Azure Automation service</span></span>

<span data-ttu-id="4aabe-416">Azure 모니터의 알림에 대 한 자세한 내용은 [Azure 모니터의 경고 로그](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4aabe-416">See [Log alerts in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in Azure Monitor.</span></span>

> [!NOTE]
> <span data-ttu-id="4aabe-417">다음 예제에서는 Microsoft 팀 대화방 장치에서 하드웨어 또는 응용 프로그램 오류를 생성할 때 전자 메일 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-417">The following examples send email alerts when a Microsoft Teams Rooms device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-hardware-issues"></a><span data-ttu-id="4aabe-418">Microsoft 팀 대화방 하드웨어 문제에 대 한 전자 메일 알림 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-418">Configure an email alert for Microsoft Teams Rooms hardware issues</span></span>

<span data-ttu-id="4aabe-419">지난 시간 내에 하드웨어 문제가 발생 한 Microsoft 팀 공간 장치를 확인 하는 알림 규칙을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-419">Configure an alert rule that checks for Microsoft Teams Rooms devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="4aabe-420">[Microsoft Azure 포털](https://portal.azure.com) 에 로그인 하 고 로그 분석으로 이동 하 여 작업 영역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-420">Sign in to the [Microsoft Azure portal](https://portal.azure.com) and go to Log Analytics and select your workspace.</span></span>

2. <span data-ttu-id="4aabe-421">로그 분석 작업 영역으로 이동 하 여 **알림을** 선택한 다음 **새 알림 규칙** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-421">Navigate to your Log Analytics workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="4aabe-422">**조건 추가** 를 선택 하 고 **사용자 지정 로그 검색**</span><span class="sxs-lookup"><span data-stu-id="4aabe-422">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="4aabe-423">검색 쿼리 텍스트 상자에 다음 쿼리를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-423">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="4aabe-424">경고 논리 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-424">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="4aabe-425">**기준:** 결과 수</span><span class="sxs-lookup"><span data-stu-id="4aabe-425">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="4aabe-426">**조건:** 더 크게</span><span class="sxs-lookup"><span data-stu-id="4aabe-426">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="4aabe-427">**Treshold:** 0</span><span class="sxs-lookup"><span data-stu-id="4aabe-427">**Treshold:** 0</span></span><br>

6. <span data-ttu-id="4aabe-428">평가 설정을 구성 하 고 **완료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-428">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="4aabe-429">**기간 (분):** 60</span><span class="sxs-lookup"><span data-stu-id="4aabe-429">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="4aabe-430">**빈도 (분):** 60</span><span class="sxs-lookup"><span data-stu-id="4aabe-430">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="4aabe-431">작업 그룹 구성:</span><span class="sxs-lookup"><span data-stu-id="4aabe-431">Configure action groups:</span></span>
    1.  <span data-ttu-id="4aabe-432">**새로 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-432">Select **Create New**</span></span>
    2.  <span data-ttu-id="4aabe-433">*작업 그룹 이름* 및 *약식 이름* 필드에 적합 한 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-433">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="4aabe-434">고유한 *작업 이름을* 지정 하 고 **전자 메일/SMS/푸시/음성을**선택한 다음 **세부 정보 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-434">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="4aabe-435">전자 메일 확인란을 선택 하 고 알림을 받을 사용자 또는 그룹의 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-435">Select the Email checkbox and provide the email address of the person or group that will recieve the alerts.</span></span>
    5.  <span data-ttu-id="4aabe-436">또한 전화 번호를 입력 하 여 SMS, 음성 통화 또는 두 가지 모두에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-436">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="4aabe-437">**확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-437">Select **OK**.</span></span>

8. <span data-ttu-id="4aabe-438">알림 전자 메일의 제목 줄을 재정의 하려면 **작업을 사용자 지정** 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-438">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="4aabe-439">규칙 이름 및 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-439">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="4aabe-440">**규칙 이름:** Microsoft 팀 대화방 하드웨어 오류 알림</span><span class="sxs-lookup"><span data-stu-id="4aabe-440">**Rule Name:** Microsoft Teams Rooms Hardware Failure Alert</span></span><br>
    <span data-ttu-id="4aabe-441">**설명:** 지난 시간 내에 하드웨어 문제가 발생 한 장치 목록</span><span class="sxs-lookup"><span data-stu-id="4aabe-441">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="4aabe-442">원하는 심각도를 선택 하 고 규칙을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-442">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="4aabe-443">**알림 규칙 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-443">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-microsoft-teams-rooms-application-issues"></a><span data-ttu-id="4aabe-444">Microsoft 팀 대화방 응용 프로그램 문제에 대 한 전자 메일 알림 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-444">Configure an email alert for Microsoft Teams Rooms application issues</span></span>

<span data-ttu-id="4aabe-445">마지막 시간 내에 응용 프로그램 문제가 발생 한 장치 목록을 표시 하려면 같은 절차를 반복 하 되 다음 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-445">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="4aabe-446">이제 알림 정의를 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-446">Now you’ve completed defining alerts.</span></span> <span data-ttu-id="4aabe-447">위의 예제를 사용 하 여 추가 알림을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-447">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="4aabe-448">경고가 생성 되 면 지난 시간 내에 문제가 발생 한 장치를 나열 하는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-448">When an alert is generated, you’ll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="4aabe-449">![샘플 Azure 모니터 알림 전자 메일] (../media/Deploy-Azure-Monitor-6.png "샘플 Azure 모니터 알림 전자 메일")</span><span class="sxs-lookup"><span data-stu-id="4aabe-449">![Sample Azure Monitor alert email](../media/Deploy-Azure-Monitor-6.png "Sample Azure Monitor alert email")</span></span>

## <a name="configure-all-devices-for-azure-monitoring"></a><span data-ttu-id="4aabe-450">모든 Azure 모니터링 장치 구성</span><span class="sxs-lookup"><span data-stu-id="4aabe-450">Configure all devices for Azure Monitoring</span></span>
<span data-ttu-id="4aabe-451"><a name="configure_all_devices"></a> 대시보드와 알림을 구성한 후에는 모든 Microsoft 팀 대화방 장치에서 microsoft monitoring agent를 설정 하 고 구성 하 여 모니터링 배포를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-451"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure Microsoft Monitoring agent on all Microsoft Teams Rooms devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="4aabe-452">각 장치에 Microsoft Monitoring agent를 수동으로 설치 하 고 구성할 수 있지만, 기존 소프트웨어 배포 도구 및 방법을 활용할 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-452">Although you can install and configure the Microsoft Monitoring agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="4aabe-453">Microsoft 팀 공간 장치를 처음으로 작성 하는 경우에는 빌드 프로세스의 일부로 Microsoft Monitoring agent 설정 및 구성 단계를 포함 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-453">If you’re building your Microsoft Teams Rooms devices for the first time, you might want to include the Microsoft Monitoring agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="4aabe-454">자세한 내용은 [명령줄을 사용 하 여 에이전트 설치](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4aabe-454">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-microsoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="4aabe-455">GPO (그룹 정책 개체)를 사용 하 여 Microsoft Monitoring agent 배포</span><span class="sxs-lookup"><span data-stu-id="4aabe-455">Deploying Microsoft Monitoring agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="4aabe-456">Azure 모니터링을 구현 하기 전에 Microsoft 팀 회의실 장치를 이미 배포한 경우 제공 된 스크립트를 사용 하 여 Active Directory 그룹 정책 개체를 사용 하 여 에이전트를 설정 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-456">If you already deployed your Microsoft Teams Rooms devices before you implement Azure Monitoring, you can use the provided script to set up and configure the agents by using Active Directory group policy objects.</span></span>

1.  <span data-ttu-id="4aabe-457">공유 네트워크 경로를 만들고 **도메인 컴퓨터** 그룹에 대 한 읽기 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-457">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="4aabe-458">64 비트 버전의 Windows 용 Microsoft Monitoring Agent 다운로드<https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="4aabe-458">Download the 64-bit version of the Microsoft Monitoring Agent for Windows from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="4aabe-459">네트워크 공유에 설치 패키지의 콘텐츠를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-459">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="4aabe-460">명령 프롬프트 창을 연 다음 **MMASetup-AMD64 실행/c**</span><span class="sxs-lookup"><span data-stu-id="4aabe-460">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="4aabe-461">방금 만든 공유를 지정 하 고 콘텐츠를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-461">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="4aabe-462">새 그룹 정책 개체를 만들고 Microsoft 팀 대화방 컴퓨터 계정이 있는 조직 구성 단위에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-462">Create a new Group Policy Object and assign it to the organizational unit where Microsoft Teams Rooms machine accounts are located.</span></span>

5.  <span data-ttu-id="4aabe-463">PowerShell 실행 정책 구성:</span><span class="sxs-lookup"><span data-stu-id="4aabe-463">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="4aabe-464">새로 만든 그룹 정책 개체를 편집 하 고 컴퓨터 \\ 구성 정책 \\ 으로 이동 합니다 \\ . 관리 \\ 템플릿 windows 구성 요소 windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4aabe-464">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ Windows Components \\ Windows PowerShell</span></span>
    2.  <span data-ttu-id="4aabe-465">**스크립트 실행** 을 설정 하 고 **로컬 스크립트를 허용**하도록 **실행 정책을** 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-465">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="4aabe-466">시작 스크립트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-466">Configure the startup script:</span></span>
    1.  <span data-ttu-id="4aabe-467">다음 스크립트를 복사 하 여 Install-MMAgent로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-467">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="4aabe-468">WorkspaceId, WorkspaceKey 및 SetupPath 매개 변수를 구성에 맞게 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-468">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="4aabe-469">동일한 그룹 정책 개체를 편집 하 고 컴퓨터 구성 \\ 정책 \\ Windows 설정 \\ 스크립트 (시작/종료)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-469">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ Windows Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="4aabe-470">**시작**을 두 번 클릭 하 여 선택 하 고 **PowerShell 스크립트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-470">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="4aabe-471">**파일 표시**를 선택한 다음 **Install-MMAgent** 파일을 해당 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-471">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="4aabe-472">**추가**를 선택한 다음 **찾아보기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-472">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="4aabe-473">방금 복사한 ps1 스크립트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-473">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="4aabe-474">Microsoft 팀 대화방 장치는 두 번째 재부팅을 사용 하 여 Microsoft Monitoring agent를 설치 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-474">Microsoft Teams Rooms devices should install and configure the Microsoft Monitoring agent with the second reboot.</span></span>

```
# Install-MMAgent.ps1
<#
Date:        04/20/2018
Script:      Install-MMAgent.ps1
Version:     1.0
#>

# Set the parameters
$WorkspaceId = "<your workspace id>"
$WorkspaceKey = "<your workspace key>"
$SetupPath = "\\Server\Share"

$SetupParameters = "/qn NOAPM=1 ADD_OPINSIGHTS_WORKSPACE=1 OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE=0 OPINSIGHTS_WORKSPACE_ID=$WorkspaceId OPINSIGHTS_WORKSPACE_KEY=$WorkspaceKey AcceptEndUserLicenseAgreement=1"

# $SetupParameters = $SetupParameters + " OPINSIGHTS_PROXY_URL=<Proxy server URL> OPINSIGHTS_PROXY_USERNAME=<Proxy server username> OPINSIGHTS_PROXY_PASSWORD=<Proxy server password>"

# Start PowerShell logging
Start-Transcript -Path C:\Temp\MMA-Install.Log

# Check if the Microsoft Monitoring Agent is installed
$mma = New-Object -ComObject 'AgentConfigManager.MgmtSvcCfg'

# Check if the Microsoft Monitoring agent is installed
if (!$mma)
{
    #Install agent
    Start-Process -FilePath "$SetupPath\Setup.exe" -ArgumentList $SetupParameters -ErrorAction Stop -Wait
}

# Check if the agent has a valid configuration
$CheckMMA = $mma.GetCloudWorkspace($WorkspaceId).AgentId
if (!$CheckMMA)
{
    # Apply new configuration
    $mma.AddCloudWorkspace($WorkspaceId, $WorkspaceKey)
    $mma.ReloadConfiguration()
}

Stop-Transcript
```

> [!NOTE]
> <span data-ttu-id="4aabe-475">에이전트를 다시 구성 하거나 다른 작업 영역으로 이동 하거나 초기 설치 후 프록시 설정을 수정 해야 하는 경우 [로그 분석 에이전트를 관리 하 고 유지 관리 하는](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) 문서를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-475">You can refer to the article [Managing and maintaining the Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="4aabe-476">추가 해결 방법</span><span class="sxs-lookup"><span data-stu-id="4aabe-476">Additional Solutions</span></span>
<span data-ttu-id="4aabe-477"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="4aabe-477"></span></span>

<span data-ttu-id="4aabe-478">Azure Monitor는 [솔루션 갤러리](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) 를 통해 기본 제공 관리 솔루션을 제공 하 여 환경을 모니터링 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-478">Azure Monitor provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="4aabe-479">또한 [알림 관리](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) 및 [Azure 로그 분석 에이전트 상태](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) 솔루션도 작업 영역에 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-479">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [Azure Log Analytics Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="4aabe-480">에이전트 상태 솔루션은 환경 내에서 오래 되거나 손상 된 Microsoft 모니터링 에이전트를 식별 하는 데 도움이 될 수 있으며, 알림 관리 솔루션은 지정 된 기간 내에 발생 한 경고에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aabe-480">The Agent Health solution can help you identify outdated or broken Microsoft Monitoring agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="4aabe-481">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4aabe-481">See also</span></span>

[<span data-ttu-id="4aabe-482">Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 계획</span><span class="sxs-lookup"><span data-stu-id="4aabe-482">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="4aabe-483">Azure Monitor를 사용 하 여 Microsoft 팀 회의실 장치 관리</span><span class="sxs-lookup"><span data-stu-id="4aabe-483">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)
