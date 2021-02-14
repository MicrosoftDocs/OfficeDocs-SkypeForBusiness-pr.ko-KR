---
title: Azure Monitor를 사용하여 Microsoft Teams 회의실 관리 배포
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: 이 문서에서는 Azure Monitor를 사용하여 통합된 종단 방식으로 Microsoft Teams Rooms 디바이스의 관리를 배포하는 방법을 설명합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05c490c157c9f6530ca79ecdd8df19f15d94c68
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662103"
---
# <a name="deploy-no-loc-textmicrosoft-teams-rooms-management-with-no-loc-textazure-monitor"></a><span data-ttu-id="f7f86-103">배포 :::no-loc text="Microsoft Teams Rooms"::: 관리 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-103">Deploy :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>

<span data-ttu-id="f7f86-104">이 문서에서는 다음을 사용하여 통합된 종단식 디바이스 관리를 설정하고 배포하는 :::no-loc text="Microsoft Teams Rooms"::: 방법을 설명하고 :::no-loc text="Azure Monitor"::: 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-104">This article discusses how to set up and deploy integrated, end-to-end management of :::no-loc text="Microsoft Teams Rooms"::: devices by using :::no-loc text="Azure Monitor":::.</span></span>

<span data-ttu-id="f7f86-105">회의실 장치를 관리하는 데 도움이 되는 기본 원격 분석 및 알림을 제공하도록 구성할 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 수 :::no-loc text="Microsoft Teams Rooms"::: 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-105">You can configure :::no-loc text="Log Analytics"::: within :::no-loc text="Azure Monitor"::: to provide basic telemetry and alerts that will help you manage :::no-loc text="Microsoft Teams Rooms"::: meeting room devices.</span></span> <span data-ttu-id="f7f86-106">관리 솔루션이 완성되면 디바이스 가용성 및 성능에 대한 자세한 보기를 만들기 위해 추가 데이터 및 관리 기능을 배포하기로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-106">As your management solution matures, you might decide to deploy additional data and management capabilities to create a more detailed view of device availability and performance.</span></span>

<span data-ttu-id="f7f86-107">이 가이드에 따라 다음 예제와 같은 대시보드를 사용하여 디바이스 가용성, 애플리케이션 및 하드웨어 상태, 애플리케이션 및 운영 체제 버전 배포에 대한 자세한 상태 보고를 얻을 :::no-loc text="Microsoft Teams Rooms"::: 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-107">By following this guide, you can use a dashboard like the following example to get detailed status reporting for device availability, application and hardware health, and :::no-loc text="Microsoft Teams Rooms"::: application and operating system version distribution.</span></span>

<span data-ttu-id="f7f86-108">![Microsoft Teams 회의실에 대한 샘플 Log Analytics 보기 스크린샷](../media/Deploy-Azure-Monitor-1.png "Microsoft Teams 회의실에 대한 샘플 Log Analytics 보기")</span><span class="sxs-lookup"><span data-stu-id="f7f86-108">![Screenshot of sample Log Analytics view for Microsoft Teams Rooms](../media/Deploy-Azure-Monitor-1.png "Sample Log Analytics view for Microsoft Teams Rooms")</span></span>

<span data-ttu-id="f7f86-109">높은 수준에서 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-109">At a high level, you need to perform the following tasks:</span></span>


1. [<span data-ttu-id="f7f86-110">구성 :::no-loc text="Log Analytics"::: 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f7f86-110">Validate :::no-loc text="Log Analytics"::: configuration</span></span>](azure-monitor-deploy.md#validate_LogAnalytics)
2. [<span data-ttu-id="f7f86-111">관리 설정에 대한 :::no-loc text="Log Analytics"::: 테스트 디바이스 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-111">Configure test devices for :::no-loc text="Log Analytics"::: management setup</span></span>](azure-monitor-deploy.md#configure_test_devices)
3. [<span data-ttu-id="f7f86-112">사용자 지정 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="f7f86-112">Map custom fields</span></span>](azure-monitor-deploy.md#Custom_fields)
4. [<span data-ttu-id="f7f86-113">다음에서 :::no-loc text="Microsoft Teams Rooms"::: 보기 정의 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-113">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>](azure-monitor-deploy.md#Define_Views)
5. [<span data-ttu-id="f7f86-114">경고 정의</span><span class="sxs-lookup"><span data-stu-id="f7f86-114">Define alerts</span></span>](azure-monitor-deploy.md#Alerts)
6. [<span data-ttu-id="f7f86-115">모니터링을 위한 모든 디바이스 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-115">Configure all devices for Monitoring</span></span>](azure-monitor-deploy.md#configure_all_devices)
7. [<span data-ttu-id="f7f86-116">추가 솔루션 :::no-loc text="Azure Monitor"::: 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-116">Configure additional :::no-loc text="Azure Monitor"::: solutions</span></span>](azure-monitor-deploy.md#Solutions)

> [!IMPORTANT]
> <span data-ttu-id="f7f86-117">최소한의 구성으로 운영 체제를 실행하는 컴퓨터를 모니터링할 수 있습니다. 하지만 모든 디바이스에 에이전트 배포를 시작하기 전에 몇 가지 –특정 단계를 :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: :::no-loc text="Windows"::: :::no-loc text="Microsoft Teams Rooms"::: 수행해야 :::no-loc text="Microsoft Teams Rooms"::: 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-117">Although with minimal configuration, :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: can monitor a computer running a :::no-loc text="Windows"::: operating system, there are still some :::no-loc text="Microsoft Teams Rooms":::–specific steps that you need to take before you start deploying agents to all :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span>
> <span data-ttu-id="f7f86-118">따라서 제어된 설정 및 구성에 대해 올바른 순서로 모든 구성 단계를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-118">Therefore, we highly recommend you perform all configuration steps in the right order for a controlled setup and configuration.</span></span> <span data-ttu-id="f7f86-119">최종 결과의 품질은 초기 구성의 품질에 따라 매우 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-119">The quality of the end result very much depends on the quality of the initial configuration.</span></span>

## <a name="validate-no-loc-textlog-analytics-configuration"></a><span data-ttu-id="f7f86-120">구성 :::no-loc text="Log Analytics"::: 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f7f86-120">Validate :::no-loc text="Log Analytics"::: configuration</span></span>
<span data-ttu-id="f7f86-121"><a name="validate_LogAnalytics"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f86-121"><a name="validate_LogAnalytics"> </a></span></span>

<span data-ttu-id="f7f86-122">디바이스에서 로그 수집을 시작하려면 작업 :::no-loc text="Log Analytics"::: 영역이 :::no-loc text="Microsoft Teams Rooms"::: 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-122">You need to have a :::no-loc text="Log Analytics"::: workspace to start collecting logs from :::no-loc text="Microsoft Teams Rooms"::: devices.</span></span> <span data-ttu-id="f7f86-123">작업 영역은 자체 데이터 리포지토리, 데이터 원본 및 솔루션이 있는 고유한 :::no-loc text="Log Analytics"::: 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-123">A workspace is a unique :::no-loc text="Log Analytics"::: environment with its own data repository, data sources, and solutions.</span></span> <span data-ttu-id="f7f86-124">기존 작업 영역이 이미 있는 경우 배포를 모니터링하는 데 사용할 수도 있습니다. 또는 모니터링 요구에 특정한 전용 작업 영역도 만들 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 수 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-124">If you already have an existing :::no-loc text="Log Analytics"::: workspace, you might use it to monitor your :::no-loc text="Microsoft Teams Rooms"::: deployment or alternatively, you can create a dedicated :::no-loc text="Log Analytics"::: workspace specific to your :::no-loc text="Microsoft Teams Rooms"::: monitoring needs.</span></span>

<span data-ttu-id="f7f86-125">새 작업 영역 만들기가 필요한 경우 포털에서 작업 영역 만들기 문서의 :::no-loc text="Log Analytics"::: [지침을 :::no-loc text="Log Analytics"::: :::no-loc text="Azure"::: 따릅니다.](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span><span class="sxs-lookup"><span data-stu-id="f7f86-125">If you need to create a new :::no-loc text="Log Analytics"::: workspace, follow the instructions in the article [Create a :::no-loc text="Log Analytics"::: workspace in the :::no-loc text="Azure"::: portal](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)</span></span>

> [!NOTE]
> <span data-ttu-id="f7f86-126">사용하려면 :::no-loc text="Log Analytics"::: :::no-loc text="Azure Monitor"::: 활성 구독이 :::no-loc text="Azure"::: 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-126">To use :::no-loc text="Log Analytics"::: with :::no-loc text="Azure Monitor":::, you need to have an active :::no-loc text="Azure"::: subscription.</span></span> <span data-ttu-id="f7f86-127">구독이 없는 경우 무료 평가판 구독을 시작 :::no-loc text="Azure"::: 지점으로 만들 수 있습니다. [](https://azure.microsoft.com/free)</span><span class="sxs-lookup"><span data-stu-id="f7f86-127">If you don't have an :::no-loc text="Azure"::: subscription, you can create [a free trial subscription](https://azure.microsoft.com/free) as a starting point.</span></span>

### <a name="configure-no-loc-textlog-analytics-to-collect-no-loc-textmicrosoft-teams-rooms-event-logs"></a><span data-ttu-id="f7f86-128">이벤트 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 로그를 수집하도록 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-128">Configure :::no-loc text="Log Analytics"::: to collect :::no-loc text="Microsoft Teams Rooms"::: event logs</span></span>

<span data-ttu-id="f7f86-129">:::no-loc text="Log Analytics"::: 설정에 지정된 이벤트 :::no-loc text="Windows"::: 로그에서만 이벤트를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-129">:::no-loc text="Log Analytics"::: only collects events from the :::no-loc text="Windows"::: event logs that are specified in the settings.</span></span> <span data-ttu-id="f7f86-130">각 로그에 대해 선택한 심각도의 이벤트만 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-130">For each log, only the events with the selected severities are collected.</span></span>

<span data-ttu-id="f7f86-131">디바이스 및 애플리케이션 상태를 모니터링하는 데 필요한 로그를 수집하도록 :::no-loc text="Log Analytics"::: :::no-loc text="Microsoft Teams Rooms"::: 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-131">You need to configure :::no-loc text="Log Analytics"::: to collect the logs required to monitor :::no-loc text="Microsoft Teams Rooms"::: device and application status.</span></span> <span data-ttu-id="f7f86-132">:::no-loc text="Microsoft Teams Rooms"::: 디바이스는 이벤트 **:::no-loc text="Skype Room System":::** 로그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-132">:::no-loc text="Microsoft Teams Rooms"::: devices use the **:::no-loc text="Skype Room System":::** event log.</span></span>

<span data-ttu-id="f7f86-133">이벤트를 :::no-loc text="Log Analytics"::: 수집하도록 :::no-loc text="Microsoft Teams Rooms"::: 구성하려면 [ :::no-loc text="Windows"::: :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="f7f86-133">To configure :::no-loc text="Log Analytics"::: to collect the :::no-loc text="Microsoft Teams Rooms"::: events, see [:::no-loc text="Windows"::: event log data sources in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/data-sources-windows-events)</span></span>

<span data-ttu-id="f7f86-134">![이벤트 로그 설정 스크린샷](../media/Deploy-Azure-Monitor-2.png "이벤트 로그 설정")</span><span class="sxs-lookup"><span data-stu-id="f7f86-134">![Screenshot of event log settings](../media/Deploy-Azure-Monitor-2.png "Event log settings")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7f86-135">이벤트 로그 설정을 구성하고 이벤트 로그 이름으로 입력한 다음 오류, 경고 및 정보 :::no-loc text="Windows"::: **:::no-loc text="Skype Room System":::** 확인란을 선택합니다.   </span><span class="sxs-lookup"><span data-stu-id="f7f86-135">Configure :::no-loc text="Windows"::: Event Log settings and enter **:::no-loc text="Skype Room System":::** as event log name, and then select the **Error**, **Warning**, and **Information** check boxes.</span></span>

## <a name="configure-test-devices-for-azure-monitoring"></a><span data-ttu-id="f7f86-136">Azure 모니터링에 대한 테스트 디바이스 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-136">Configure test devices for Azure Monitoring</span></span>
<span data-ttu-id="f7f86-137"><a name="configure_test_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f86-137"><a name="configure_test_devices"> </a></span></span>

<span data-ttu-id="f7f86-138">관련 이벤트를 :::no-loc text="Log Analytics"::: 모니터링할 수 있게 :::no-loc text="Microsoft Teams Rooms"::: 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-138">You need to prepare :::no-loc text="Log Analytics"::: to be able to monitor :::no-loc text="Microsoft Teams Rooms":::–related events.</span></span> <span data-ttu-id="f7f86-139">먼저 물리적 액세스 권한이 있는 하나 또는 두 개의 디바이스에 에이전트를 배포하고 해당 테스트 디바이스가 일부 데이터를 생성하여 작업 영역으로 푸시하도록 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 해야 :::no-loc text="Log Analytics"::: 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-139">To start with, you need to deploy :::no-loc text="Microsoft Monitoring"::: agents to just one or two :::no-loc text="Microsoft Teams Rooms"::: devices that you have physical access to, and get those test devices generate some data and push it to the :::no-loc text="Log Analytics"::: workspace.</span></span>

### <a name="install-no-loc-textmicrosoft-monitoring-agents-to-test-devices"></a><span data-ttu-id="f7f86-140">디바이스를 :::no-loc text="Microsoft Monitoring"::: 테스트하기 위해 에이전트 설치</span><span class="sxs-lookup"><span data-stu-id="f7f86-140">Install :::no-loc text="Microsoft Monitoring"::: agents to test devices</span></span>

<span data-ttu-id="f7f86-141">서비스에 컴퓨터 연결에 제공된 지침을 사용하여 에이전트를 테스트 :::no-loc text="Microsoft Monitoring"::: [ :::no-loc text="Windows"::: 디바이스에 :::no-loc text="Log Analytics"::: 배포합니다. :::no-loc text="Azure"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)</span><span class="sxs-lookup"><span data-stu-id="f7f86-141">Deploy the :::no-loc text="Microsoft Monitoring"::: agent to the test devices by using the instructions provided in [Connect :::no-loc text="Windows"::: computers to the :::no-loc text="Log Analytics"::: service in :::no-loc text="Azure":::](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows).</span></span> <span data-ttu-id="f7f86-142">이 문서에서는 에이전트를 배포하는 단계, 배포에 연결된 디바이스를 얻기 위한 작업 영역 ID _ 및 기본 키를 얻기 위한 지침 및 인스턴스에 대한 에이전트 연결을 확인하는 단계에 대한 자세한 정보를 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Windows"::: :::no-loc text="Log Analytics":::  \* \*\* _\*\*_ :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitor"::: :::no-loc text="Log Analytics"::: 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-142">This article provides detailed information about the steps for deploying :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows":::, instructions for obtaining the :::no-loc text="Log Analytics"::: **_Workspace ID_* _ and the _*_primary key_\*_ to get :::no-loc text="Microsoft Teams Rooms"::: devices connected to your :::no-loc text="Azure Monitor"::: deployment, and steps to verify agent connectivity to :::no-loc text="Log Analytics"::: instance.</span></span>

### <a name="generate-sample-no-loc-textmicrosoft-teams-rooms-events"></a><span data-ttu-id="f7f86-143">샘플 :::no-loc text="Microsoft Teams Rooms"::: 이벤트 생성</span><span class="sxs-lookup"><span data-stu-id="f7f86-143">Generate sample :::no-loc text="Microsoft Teams Rooms"::: events</span></span>

<span data-ttu-id="f7f86-144">에이전트를 테스트 디바이스에 배포한 후 필요한 이벤트 로그 데이터가 에 :::no-loc text="Microsoft Monitoring"::: 의해 수집되는지 확인 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-144">After the :::no-loc text="Microsoft Monitoring"::: agent is deployed onto the test devices, verify that the required event log data is collected by :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="f7f86-145">에이전트를 설치한 후 디바이스를 다시 시작하고, 이벤트 로그에 새 이벤트를 생성할 수 있도록 모임 앱이 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 시작된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-145">Reboot the device after the installation of the :::no-loc text="Microsoft Monitoring"::: agent, and make sure that :::no-loc text="Microsoft Teams Rooms"::: Meeting app is started, so that it can generate new events into the Event Log.</span></span>

1.  <span data-ttu-id="f7f86-146">포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-146">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2.  <span data-ttu-id="f7f86-147">디바이스에서 생성된 하트비트 이벤트를 :::no-loc text="Microsoft Teams Rooms"::: 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-147">List the heartbeat events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
    1.  <span data-ttu-id="f7f86-148">작업 영역 선택 및 _ *로그*\* 로 이동하고 쿼리를 사용하여 사용자 지정 필드가 있는 하트비트 레코드를 :::no-loc text="Microsoft Teams Rooms"::: 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-148">Select your workspace and go to _ *Logs*\* and use a query to retrieve the heartbeat records that will have the custom fields for :::no-loc text="Microsoft Teams Rooms":::.</span></span>
    2.  <span data-ttu-id="f7f86-149">샘플 쿼리: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="f7f86-149">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3.  <span data-ttu-id="f7f86-150">쿼리가 모임 앱에서 생성된 이벤트를 포함 하는 로그 :::no-loc text="Microsoft Teams Rooms"::: 레코드를 반환하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-150">Make sure that the query returns log records that include events generated by the :::no-loc text="Microsoft Teams Rooms"::: meetings app.</span></span>

4.  <span data-ttu-id="f7f86-151">하드웨어 문제를 생성하고 필요한 이벤트가 로그인되어 있는지 유효성을 :::no-loc text="Azure Log Analytics"::: 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-151">Generate a hardware issue, and validate that the required events are logged in :::no-loc text="Azure Log Analytics":::.</span></span>
    1.  <span data-ttu-id="f7f86-152">테스트 시스템에서 주변 장치 중 하나를 :::no-loc text="Microsoft Teams Rooms"::: 플러그합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-152">Unplug one of the peripheral devices on the test :::no-loc text="Microsoft Teams Rooms"::: system.</span></span> <span data-ttu-id="f7f86-153">카메라, 스피커폰, 마이크 또는 전면 방 디스플레이일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-153">This could be the camera, speakerphone, microphone, or Front Room Display</span></span>
    2.  <span data-ttu-id="f7f86-154">이벤트 로그가 채워지기까지 10분 정도 :::no-loc text="Azure Log Analytics"::: 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-154">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="f7f86-155">쿼리를 사용하여 하드웨어 오류 이벤트를 나열합니다. `Event | where Source == "SRS-App" and EventID == 3001`</span><span class="sxs-lookup"><span data-stu-id="f7f86-155">Use a query to list hardware error events: `Event | where Source == "SRS-App" and EventID == 3001`</span></span>

5.  <span data-ttu-id="f7f86-156">애플리케이션 문제를 생성하고 필요한 이벤트가 기록되어 있는지 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-156">Generate an application issue, and validate that the required events are logged.</span></span>
    1.  <span data-ttu-id="f7f86-157">애플리케이션 :::no-loc text="Microsoft Teams Rooms"::: 구성을 수정하고 잘못된 SIP(세션 시작 프로토콜) 주소/암호 쌍을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-157">Modify :::no-loc text="Microsoft Teams Rooms"::: application configuration, and type an incorrect Session Initiation Protocol (SIP) address/password pair.</span></span>
    2.  <span data-ttu-id="f7f86-158">이벤트 로그가 채워지기까지 10분 정도 :::no-loc text="Azure Log Analytics"::: 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-158">Wait 10 minutes for the event log to be populated in :::no-loc text="Azure Log Analytics":::.</span></span>
    3.  <span data-ttu-id="f7f86-159">쿼리를 사용하여 애플리케이션 오류 이벤트를 나열합니다. `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span><span class="sxs-lookup"><span data-stu-id="f7f86-159">Use a query to list application error events: `Event | where Source == "SRS-App" and EventID == 2001 and EventLevel == 1`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7f86-160">이러한 샘플 이벤트 로그는 사용자 지정 필드를 구성하기 전에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-160">These sample event logs are required before custom fields can be configured.</span></span> <span data-ttu-id="f7f86-161">필요한 이벤트 로그를 수집할 때까지 다음 단계를 진행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-161">Don't proceed to the next step until you have collected the required event logs.</span></span>

## <a name="map-custom-fields"></a><span data-ttu-id="f7f86-162">사용자 지정 필드 매핑</span><span class="sxs-lookup"><span data-stu-id="f7f86-162">Map custom fields</span></span>
<span data-ttu-id="f7f86-163"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f86-163"><a name="Custom_fields"> </a></span></span>

<span data-ttu-id="f7f86-164">사용자 지정 필드를 사용하여 이벤트 로그에서 특정 데이터를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-164">You use custom fields to extract specific data from the event logs.</span></span> <span data-ttu-id="f7f86-165">나중에 타일, 대시보드 보기 및 경고에 사용할 사용자 지정 필드를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-165">You need to define custom fields that will be used later with your tiles, dashboard views, and alerts.</span></span> <span data-ttu-id="f7f86-166">사용자 [지정 :::no-loc text="Log Analytics"::: 필드를 만들기](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) 전에 사용자 지정 필드를 참조하고 개념을 익숙해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-166">See [Custom fields in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/custom-fields) and become familiar with the concepts before you start creating your custom fields.</span></span>

<span data-ttu-id="f7f86-167">캡처된 이벤트 로그에서 사용자 지정 필드를 추출하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-167">To extract your custom fields out of the captured event logs, follow these steps:</span></span>

1.  <span data-ttu-id="f7f86-168">포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-168">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="f7f86-169">디바이스에서 생성된 이벤트를 :::no-loc text="Microsoft Teams Rooms"::: 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-169">List the events generated by a :::no-loc text="Microsoft Teams Rooms"::: device:</span></span>
   1.  <span data-ttu-id="f7f86-170">로그로 **이동하고** 쿼리를 사용하여 사용자 지정 필드가 있는 레코드를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-170">Go to **Logs** and use a query to retrieve the records that will have the custom field.</span></span>
   2.  <span data-ttu-id="f7f86-171">샘플 쿼리: `Event | where Source == "SRS-App" and EventID == 2000`</span><span class="sxs-lookup"><span data-stu-id="f7f86-171">Sample query: `Event | where Source == "SRS-App" and EventID == 2000`</span></span>

3. <span data-ttu-id="f7f86-172">레코드 중 하나를 선택하고 왼쪽에 있는 단추를 선택한 다음 필드 추출 마법사를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="f7f86-172">Select one of the records, select the button to the left, and start the field extraction wizard.</span></span>
4. <span data-ttu-id="f7f86-173">RenderedDescription에서 추출할 데이터를 강조 표시하고 필드 제목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-173">Highlight the data you'd like to extract from the RenderedDescription and provide a Field Title.</span></span> <span data-ttu-id="f7f86-174">사용할 필드 이름은 표 1에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-174">The field names that you should use are provided in Table 1.</span></span>
5. <span data-ttu-id="f7f86-175">표 *1에 표시된 매핑을 사용합니다.*</span><span class="sxs-lookup"><span data-stu-id="f7f86-175">Use the mappings shown in *Table 1*.</span></span> <span data-ttu-id="f7f86-176">:::no-loc text="Log Analytics":::새 필드를 정의할 때 **\_ CF** 문자열이 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-176">:::no-loc text="Log Analytics"::: will automatically append the **\_CF** string when you define the new field.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7f86-177">모든 JSON 및 :::no-loc text="Log Analytics"::: 필드는 대소문자 구분입니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-177">Remember that all JSON and :::no-loc text="Log Analytics"::: fields are case-sensitive.</span></span>
> 
> <span data-ttu-id="f7f86-178">아래 표의 각 사용자 지정 필드에 필요한 쿼리에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-178">Pay attention to the queries required for each custom field in the table below.</span></span> <span data-ttu-id="f7f86-179">사용자 지정 필드 값을 성공적으로 추출하려면 올바른 쿼리를 :::no-loc text="Log Analytics"::: 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-179">You need to use the correct queries for :::no-loc text="Log Analytics"::: to successfully extract custom field values.</span></span>
> 
<span data-ttu-id="f7f86-180">**표 1**</span><span class="sxs-lookup"><span data-stu-id="f7f86-180">**Table 1**</span></span>

| <span data-ttu-id="f7f86-181">**JSON 필드**</span><span class="sxs-lookup"><span data-stu-id="f7f86-181">**JSON field**</span></span>                   | <span data-ttu-id="f7f86-182">**:::no-loc text="Log Analytics"::: 사용자 지정 필드**</span><span class="sxs-lookup"><span data-stu-id="f7f86-182">**:::no-loc text="Log Analytics"::: custom field**</span></span> | <span data-ttu-id="f7f86-183">**이벤트 ID**</span><span class="sxs-lookup"><span data-stu-id="f7f86-183">**Event ID**</span></span> | <span data-ttu-id="f7f86-184">**추출에 사용할 쿼리**</span><span class="sxs-lookup"><span data-stu-id="f7f86-184">**Query to use with the extraction**</span></span>                   |
|:---------------------------------|:-------------------------------|:-------------|:-------------------------------------------------------|
| <span data-ttu-id="f7f86-185">설명</span><span class="sxs-lookup"><span data-stu-id="f7f86-185">Description</span></span>                      | <span data-ttu-id="f7f86-186">SRSEventDescription</span><span class="sxs-lookup"><span data-stu-id="f7f86-186">SRSEventDescription</span></span>         | <span data-ttu-id="f7f86-187">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-187">**2000**</span></span>     | <span data-ttu-id="f7f86-188">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-188">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-189">ResourceState</span><span class="sxs-lookup"><span data-stu-id="f7f86-189">ResourceState</span></span>                    | <span data-ttu-id="f7f86-190">SRSResourceState</span><span class="sxs-lookup"><span data-stu-id="f7f86-190">SRSResourceState</span></span>            | <span data-ttu-id="f7f86-191">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-191">**2000**</span></span>     | <span data-ttu-id="f7f86-192">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-192">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-193">OperationName</span><span class="sxs-lookup"><span data-stu-id="f7f86-193">OperationName</span></span>                    | <span data-ttu-id="f7f86-194">SRSOperationName</span><span class="sxs-lookup"><span data-stu-id="f7f86-194">SRSOperationName</span></span>            | <span data-ttu-id="f7f86-195">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-195">**2000**</span></span>     | <span data-ttu-id="f7f86-196">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-196">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-197">OperationResult</span><span class="sxs-lookup"><span data-stu-id="f7f86-197">OperationResult</span></span>                  | <span data-ttu-id="f7f86-198">SRSOperationResult</span><span class="sxs-lookup"><span data-stu-id="f7f86-198">SRSOperationResult</span></span>          | <span data-ttu-id="f7f86-199">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-199">**2000**</span></span>     | <span data-ttu-id="f7f86-200">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-200">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-201">OS</span><span class="sxs-lookup"><span data-stu-id="f7f86-201">OS</span></span>                               | <span data-ttu-id="f7f86-202">SRSOSVersion</span><span class="sxs-lookup"><span data-stu-id="f7f86-202">SRSOSVersion</span></span>                | <span data-ttu-id="f7f86-203">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-203">**2000**</span></span>     | <span data-ttu-id="f7f86-204">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-204">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-205">OSVersion</span><span class="sxs-lookup"><span data-stu-id="f7f86-205">OSVersion</span></span>                        | <span data-ttu-id="f7f86-206">SRSOSLongVersion</span><span class="sxs-lookup"><span data-stu-id="f7f86-206">SRSOSLongVersion</span></span>            | <span data-ttu-id="f7f86-207">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-207">**2000**</span></span>     | <span data-ttu-id="f7f86-208">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-208">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-209">별칭</span><span class="sxs-lookup"><span data-stu-id="f7f86-209">Alias</span></span>                            | <span data-ttu-id="f7f86-210">SRSAlias</span><span class="sxs-lookup"><span data-stu-id="f7f86-210">SRSAlias</span></span>                    | <span data-ttu-id="f7f86-211">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-211">**2000**</span></span>     | <span data-ttu-id="f7f86-212">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-212">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f7f86-213">DisplayName</span></span>                      | <span data-ttu-id="f7f86-214">SRSDisplayName</span><span class="sxs-lookup"><span data-stu-id="f7f86-214">SRSDisplayName</span></span>              | <span data-ttu-id="f7f86-215">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-215">**2000**</span></span>     | <span data-ttu-id="f7f86-216">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-216">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-217">AppVersion</span><span class="sxs-lookup"><span data-stu-id="f7f86-217">AppVersion</span></span>                       | <span data-ttu-id="f7f86-218">SRSAppVersion</span><span class="sxs-lookup"><span data-stu-id="f7f86-218">SRSAppVersion</span></span>               | <span data-ttu-id="f7f86-219">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-219">**2000**</span></span>     | <span data-ttu-id="f7f86-220">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-220">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-221">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="f7f86-221">IPv4Address</span></span>                      | <span data-ttu-id="f7f86-222">SRSIPv4Address</span><span class="sxs-lookup"><span data-stu-id="f7f86-222">SRSIPv4Address</span></span>              | <span data-ttu-id="f7f86-223">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-223">**2000**</span></span>     | <span data-ttu-id="f7f86-224">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-224">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-225">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="f7f86-225">IPv6Address</span></span>                      | <span data-ttu-id="f7f86-226">SRSIPv6Address</span><span class="sxs-lookup"><span data-stu-id="f7f86-226">SRSIPv6Address</span></span>              | <span data-ttu-id="f7f86-227">**2000**</span><span class="sxs-lookup"><span data-stu-id="f7f86-227">**2000**</span></span>     | <span data-ttu-id="f7f86-228">Source \| == "SRS-App" 및 EventID == 2000인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-228">Event \| where Source == "SRS-App" and EventID == 2000</span></span> |
| <span data-ttu-id="f7f86-229">회의 마이크 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-229">Conference Microphone status</span></span>     | <span data-ttu-id="f7f86-230">SRSConfMicrophoneStatus</span><span class="sxs-lookup"><span data-stu-id="f7f86-230">SRSConfMicrophoneStatus</span></span>     | <span data-ttu-id="f7f86-231">**3001**</span><span class="sxs-lookup"><span data-stu-id="f7f86-231">**3001**</span></span>     | <span data-ttu-id="f7f86-232">Source \| == "SRS-App" 및 EventID == 3001인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-232">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="f7f86-233">컨퍼런스 발표자 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-233">Conference Speaker status</span></span>        | <span data-ttu-id="f7f86-234">SRSConfSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="f7f86-234">SRSConfSpeakerStatus</span></span>        | <span data-ttu-id="f7f86-235">**3001**</span><span class="sxs-lookup"><span data-stu-id="f7f86-235">**3001**</span></span>     | <span data-ttu-id="f7f86-236">Source \| == "SRS-App" 및 EventID == 3001인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-236">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="f7f86-237">기본 발표자 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-237">Default Speaker status</span></span>           | <span data-ttu-id="f7f86-238">SRSDefaultSpeakerStatus</span><span class="sxs-lookup"><span data-stu-id="f7f86-238">SRSDefaultSpeakerStatus</span></span>     | <span data-ttu-id="f7f86-239">**3001**</span><span class="sxs-lookup"><span data-stu-id="f7f86-239">**3001**</span></span>     | <span data-ttu-id="f7f86-240">Source \| == "SRS-App" 및 EventID == 3001인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-240">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="f7f86-241">카메라 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-241">Camera status</span></span>                    | <span data-ttu-id="f7f86-242">SRSCameraStatus</span><span class="sxs-lookup"><span data-stu-id="f7f86-242">SRSCameraStatus</span></span>             | <span data-ttu-id="f7f86-243">**3001**</span><span class="sxs-lookup"><span data-stu-id="f7f86-243">**3001**</span></span>     | <span data-ttu-id="f7f86-244">Source \| == "SRS-App" 및 EventID == 3001인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-244">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="f7f86-245">방 표시 상태 앞</span><span class="sxs-lookup"><span data-stu-id="f7f86-245">Front of Room Display status</span></span>     | <span data-ttu-id="f7f86-246">SRSFORDStatus</span><span class="sxs-lookup"><span data-stu-id="f7f86-246">SRSFORDStatus</span></span>               | <span data-ttu-id="f7f86-247">**3001**</span><span class="sxs-lookup"><span data-stu-id="f7f86-247">**3001**</span></span>     | <span data-ttu-id="f7f86-248">Source \| == "SRS-App" 및 EventID == 3001인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-248">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="f7f86-249">동작 센서 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-249">Motion Sensor status</span></span>             | <span data-ttu-id="f7f86-250">SRSMotionSensorStatus</span><span class="sxs-lookup"><span data-stu-id="f7f86-250">SRSMotionSensorStatus</span></span>       | <span data-ttu-id="f7f86-251">**3001**</span><span class="sxs-lookup"><span data-stu-id="f7f86-251">**3001**</span></span>     | <span data-ttu-id="f7f86-252">Source \| == "SRS-App" 및 EventID == 3001인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-252">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |
| <span data-ttu-id="f7f86-253">HDMI 인제스트 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-253">HDMI Ingest status</span></span>               | <span data-ttu-id="f7f86-254">SRSHDMIIngestStatus</span><span class="sxs-lookup"><span data-stu-id="f7f86-254">SRSHDMIIngestStatus</span></span>         | <span data-ttu-id="f7f86-255">**3001**</span><span class="sxs-lookup"><span data-stu-id="f7f86-255">**3001**</span></span>     | <span data-ttu-id="f7f86-256">Source \| == "SRS-App" 및 EventID == 3001인 이벤트</span><span class="sxs-lookup"><span data-stu-id="f7f86-256">Event \| where Source == "SRS-App" and EventID == 3001</span></span> |


## <a name="define-the-no-loc-textmicrosoft-teams-rooms-views-in-no-loc-textlog-analytics"></a><span data-ttu-id="f7f86-257">다음에서 :::no-loc text="Microsoft Teams Rooms"::: 보기 정의 :::no-loc text="Log Analytics":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-257">Define the :::no-loc text="Microsoft Teams Rooms"::: views in :::no-loc text="Log Analytics":::</span></span>
<span data-ttu-id="f7f86-258"><a name="Define_Views"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f86-258"><a name="Define_Views"> </a></span></span>

<span data-ttu-id="f7f86-259">데이터가 수집되고 사용자 지정 필드가 매핑된 후 뷰 디자이너를 사용하여 이벤트를 모니터링하는 다양한 타일이 포함된 대시보드를 개발할 수 :::no-loc text="Microsoft Teams Rooms"::: 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-259">After data is collected and custom fields are mapped, you can use View Designer to develop a dashboard containing various tiles to monitor :::no-loc text="Microsoft Teams Rooms"::: events.</span></span> <span data-ttu-id="f7f86-260">뷰 디자이너를 사용하여 다음 타일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-260">Use View Designer to create the following tiles.</span></span> <span data-ttu-id="f7f86-261">자세한 내용은 뷰 디자이너를 사용하여 사용자 지정 [보기 만들기를 :::no-loc text="Log Analytics"::: 참조하세요.](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span><span class="sxs-lookup"><span data-stu-id="f7f86-261">For more information, see [Create custom views by using View Designer in :::no-loc text="Log Analytics":::](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)</span></span>

> [!NOTE]
> <span data-ttu-id="f7f86-262">대시보드 타일이 제대로 작동하려면 이 가이드의 이전 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-262">Previous steps in this guide should have been completed for the dashboard tiles to work properly.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method"></a><span data-ttu-id="f7f86-263">가져오기 방법을 사용하여 Microsoft Teams 회의실 대시보드 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-263">Create a Microsoft Teams Rooms dashboard by using the import method</span></span>

<span data-ttu-id="f7f86-264">대시보드를 가져오고 디바이스 :::no-loc text="Microsoft Teams Rooms"::: 모니터링을 빠르게 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-264">You can import an :::no-loc text="Microsoft Teams Rooms"::: dashboard and start monitoring your devices quickly.</span></span> <span data-ttu-id="f7f86-265">대시보드를 가져오는 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-265">Take the following steps to import the dashboard:</span></span>

1.  <span data-ttu-id="f7f86-266">[SkypeRoomSystems_v2.omsview 대시보드 파일을](https://go.microsoft.com/fwlink/?linkid=835675) 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-266">Get the [SkypeRoomSystems_v2.omsview](https://go.microsoft.com/fwlink/?linkid=835675) dashboard file.</span></span>
2.  <span data-ttu-id="f7f86-267">포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-267">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>
3.  <span data-ttu-id="f7f86-268">뷰 **디자이너 열기.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-268">Open **View Designer**.</span></span>
4.  <span data-ttu-id="f7f86-269">가져오기 **및** **SkypeRoomSystems_v2.omsview 파일을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-269">Select **Import**, and then select the **SkypeRoomSystems_v2.omsview** file.</span></span>
5.  <span data-ttu-id="f7f86-270">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-270">Select **Save**.</span></span>

### <a name="create-a-microsoft-teams-rooms-dashboard-manually"></a><span data-ttu-id="f7f86-271">수동으로 Microsoft Teams 회의실 대시보드 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-271">Create a Microsoft Teams Rooms dashboard manually</span></span>

<span data-ttu-id="f7f86-272">또는 사용자 자신의 대시보드를 만들고 모니터링할 타일만 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-272">Alternatively, you can create your own dashboard and add only the tiles that you wish to monitor.</span></span>

#### <a name="configure-the-overview-tile"></a><span data-ttu-id="f7f86-273">개요 타일 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-273">Configure the Overview Tile</span></span>

1.  <span data-ttu-id="f7f86-274">뷰 **디자이너 열기.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-274">Open **View Designer**.</span></span>
2.  <span data-ttu-id="f7f86-275">개요 **타일을** 선택한 다음 갤러리에서 **두** 숫자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-275">Select **Overview Tile**, and then select **Two numbers** from the gallery.</span></span>
3.  <span data-ttu-id="f7f86-276">타일 이름을 **:::no-loc text="Microsoft Teams Rooms":::** 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-276">Name the tile **:::no-loc text="Microsoft Teams Rooms":::**.</span></span>
4.  <span data-ttu-id="f7f86-277">첫 번째 **타일 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-277">Define the **First Tile**:</span></span><br>
    <span data-ttu-id="f7f86-278">**범례:** 지난 달 내에 하트비트가 한 번 이상 전송된 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-278">**Legend:** Devices that sent a heartbeat at least once within the last month</span></span><br>
    <span data-ttu-id="f7f86-279">**쿼리:**```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="f7f86-279">**Query:** ```Event | where EventLog == "Skype Room System" and TimeGenerated > ago(30d) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
5.  <span data-ttu-id="f7f86-280">두 번째 **타일 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-280">Define the **Second Tile**:</span></span><br>
    <span data-ttu-id="f7f86-281">**범례:** 지난 1시간 내에 하트비트가 전송된 활성 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-281">**Legend:** Active devices that sent a heartbeat within the last hour</span></span><br>
    <span data-ttu-id="f7f86-282">**쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span><span class="sxs-lookup"><span data-stu-id="f7f86-282">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(1h) | summarize TotalSRSDevices = dcount(Computer)```</span></span>
6.  <span data-ttu-id="f7f86-283">적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-283">Select **Apply**.</span></span>

### <a name="create-a-tile-that-displays-active-devices"></a><span data-ttu-id="f7f86-284">활성 디바이스를 표시하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-284">Create a tile that displays active devices</span></span>

1.  <span data-ttu-id="f7f86-285">대시보드 **보기를 선택하여** 타일 추가를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="f7f86-285">Select **View Dashboard** to start adding your tiles.</span></span>
2.  <span data-ttu-id="f7f86-286">갤러리에서 **&** 목록 선택</span><span class="sxs-lookup"><span data-stu-id="f7f86-286">Select **Number & list** from the gallery</span></span>
3.  <span data-ttu-id="f7f86-287">일반 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-287">Define the **General** properties:</span></span><br>
    <span data-ttu-id="f7f86-288">**그룹 제목:** 하트비트 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-288">**Group Title:** Heartbeat Status</span></span><br>
    <span data-ttu-id="f7f86-289">**새 그룹:** 선택</span><span class="sxs-lookup"><span data-stu-id="f7f86-289">**New Group:** Selected</span></span>
4.  <span data-ttu-id="f7f86-290">타일 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-290">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="f7f86-291">**범례:** 활성 디바이스(지난 20분 동안 전송된 하트비트)</span><span class="sxs-lookup"><span data-stu-id="f7f86-291">**Legend:** Active devices (heartbeat sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="f7f86-292">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="f7f86-292">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize AggregatedValue = count() by Computer | count```</span></span>
5.  <span data-ttu-id="f7f86-293">목록 속성을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-293">Define the **List** properties:</span></span><br>
    <span data-ttu-id="f7f86-294">**쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="f7f86-294">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" and TimeGenerated > ago(20m) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
6.  <span data-ttu-id="f7f86-295">열 **제목 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-295">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="f7f86-296">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="f7f86-296">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="f7f86-297">**값:** 마지막 하트비트</span><span class="sxs-lookup"><span data-stu-id="f7f86-297">**Value:** Last Heartbeat</span></span>
7.  <span data-ttu-id="f7f86-298">탐색 **쿼리를 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-298">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="f7f86-299">**적용을** 선택한 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-299">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-connectivity-issues"></a><span data-ttu-id="f7f86-300">연결 문제가 있는 디바이스를 표시하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-300">Create a tile that displays devices that have connectivity issues</span></span>

1.  <span data-ttu-id="f7f86-301">갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-301">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="f7f86-302">일반 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-302">Define the **General** properties:</span></span><br>
    <span data-ttu-id="f7f86-303">**그룹 제목:** 비워 두기</span><span class="sxs-lookup"><span data-stu-id="f7f86-303">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="f7f86-304">**새 그룹:** 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-304">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="f7f86-305">타일 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-305">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="f7f86-306">**범례:** 비활성 디바이스(지난 20분 동안 전송된 하트비트 메시지 없음)</span><span class="sxs-lookup"><span data-stu-id="f7f86-306">**Legend:** Inactive Devices (no heartbeat message sent in the last 20 minutes)</span></span><br>
    <span data-ttu-id="f7f86-307">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span><span class="sxs-lookup"><span data-stu-id="f7f86-307">**Tile Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize LastHB = max(TimeGenerated) by Computer | where LastHB < ago(20m) | count```</span></span>
4.  <span data-ttu-id="f7f86-308">목록 속성을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-308">Define the **List** properties:</span></span><br>
    <span data-ttu-id="f7f86-309">**쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="f7f86-309">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize TimeGenerated = max(TimeGenerated) by Computer | where TimeGenerated < ago(20m) | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="f7f86-310">열 **제목 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-310">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="f7f86-311">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="f7f86-311">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="f7f86-312">**값:** 마지막 하트비트</span><span class="sxs-lookup"><span data-stu-id="f7f86-312">**Value:** Last Heartbeat</span></span>
6.  <span data-ttu-id="f7f86-313">탐색 **쿼리 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-313">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="f7f86-314">**적용을** 선택한 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-314">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-a-hardware-error"></a><span data-ttu-id="f7f86-315">하드웨어 오류가 있는 디바이스를 표시하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-315">Create a tile that displays devices that have a hardware error</span></span>

1.  <span data-ttu-id="f7f86-316">갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-316">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="f7f86-317">일반 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-317">Define the **General** properties:</span></span><br>
    <span data-ttu-id="f7f86-318">**그룹 제목:** 하드웨어 상태</span><span class="sxs-lookup"><span data-stu-id="f7f86-318">**Group Title:** Hardware Status</span></span><br>
    <span data-ttu-id="f7f86-319">**새 그룹:** 선택</span><span class="sxs-lookup"><span data-stu-id="f7f86-319">**New Group:** Selected</span></span>
3.  <span data-ttu-id="f7f86-320">타일 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-320">Define the **Tile** properties:</span></span><br>
    <span data-ttu-id="f7f86-321">**범례:** 지난 1시간 동안 하드웨어 오류가 발생한 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-321">**Legend:** Devices that experienced a hardware error in the last hour</span></span><br>
    <span data-ttu-id="f7f86-322">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="f7f86-322">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="f7f86-323">목록 속성을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-323">Define the **List** properties:</span></span><br>
    <span data-ttu-id="f7f86-324">**쿼리 나열:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="f7f86-324">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="f7f86-325">열 **제목 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-325">Define **Column Titles**:</span></span><br>
    <span data-ttu-id="f7f86-326">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="f7f86-326">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="f7f86-327">**값:** 마지막 오류</span><span class="sxs-lookup"><span data-stu-id="f7f86-327">**Value:** Last Error</span></span>
6.  <span data-ttu-id="f7f86-328">탐색 **쿼리 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-328">Define **Navigation Query**:</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 3001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="f7f86-329">**적용을** 선택한 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-329">Select **Apply**, and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-operating-system-versions"></a><span data-ttu-id="f7f86-330">운영 체제 버전을 :::no-loc text="Microsoft Teams Rooms"::: 표시하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-330">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: Operating System versions</span></span>

1.  <span data-ttu-id="f7f86-331">갤러리에서 **도넛형 &** 선택한 다음 새 타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-331">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="f7f86-332">일반 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-332">Define the **General** properties:</span></span><br>
    <span data-ttu-id="f7f86-333">**그룹 제목:** 운영 체제 세부 정보</span><span class="sxs-lookup"><span data-stu-id="f7f86-333">**Group Title:** Operating System details</span></span><br>
    <span data-ttu-id="f7f86-334">**새 그룹:** 선택</span><span class="sxs-lookup"><span data-stu-id="f7f86-334">**New Group:** Selected</span></span>
3.  <span data-ttu-id="f7f86-335">헤더 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-335">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="f7f86-336">**제목:** 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="f7f86-336">**Title:** Operating System versions</span></span><br>
    <span data-ttu-id="f7f86-337">**자막:** 특정 OS 버전을 실행하는 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-337">**Subtitle:** Devices running specific OS versions</span></span>
4.  <span data-ttu-id="f7f86-338">도넛 **속성 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-338">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="f7f86-339">**쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span><span class="sxs-lookup"><span data-stu-id="f7f86-339">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize OS_Version = max(SRSOSLongVersion_CF) by Computer | summarize AggregatedValue = count() by OS_Version | sort by OS_Version asc```</span></span><br>
    <span data-ttu-id="f7f86-340">**텍스트 가운데:** 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-340">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="f7f86-341">**작업:** 합계</span><span class="sxs-lookup"><span data-stu-id="f7f86-341">**Operation:** Sum</span></span>
5.  <span data-ttu-id="f7f86-342">목록 속성을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-342">Define the **List** properties.</span></span><br>
    <span data-ttu-id="f7f86-343">**쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="f7f86-343">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSOSLongVersion_CF = max(SRSOSLongVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="f7f86-344">**그래프 숨기기:** 선택</span><span class="sxs-lookup"><span data-stu-id="f7f86-344">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="f7f86-345">**스파크라인 사용:** 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-345">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="f7f86-346">열 **제목을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-346">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="f7f86-347">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="f7f86-347">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="f7f86-348">**값:** 비워 두기</span><span class="sxs-lookup"><span data-stu-id="f7f86-348">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="f7f86-349">탐색 **쿼리를 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-349">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="f7f86-350">적용을 **선택한** 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-350">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-no-loc-textmicrosoft-teams-rooms-application-versions"></a><span data-ttu-id="f7f86-351">애플리케이션 버전을 표시하는 :::no-loc text="Microsoft Teams Rooms"::: 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-351">Create a tile that displays :::no-loc text="Microsoft Teams Rooms"::: application versions</span></span>

1.  <span data-ttu-id="f7f86-352">갤러리에서 **도넛형 &** 선택한 다음 새 타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-352">Select **Donut & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="f7f86-353">일반 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-353">Define the **General** properties:</span></span><br>
    <span data-ttu-id="f7f86-354">**그룹 제목:** :::no-loc text="Microsoft Teams Rooms"::: 애플리케이션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="f7f86-354">**Group Title:** :::no-loc text="Microsoft Teams Rooms"::: application details</span></span><br>
    <span data-ttu-id="f7f86-355">**새 그룹:** 선택</span><span class="sxs-lookup"><span data-stu-id="f7f86-355">**New Group:** Selected</span></span>
3.  <span data-ttu-id="f7f86-356">헤더 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-356">Define the **Header** properties:</span></span><br>
    <span data-ttu-id="f7f86-357">**제목:** 애플리케이션 버전</span><span class="sxs-lookup"><span data-stu-id="f7f86-357">**Title:** Application versions</span></span><br>
    <span data-ttu-id="f7f86-358">**자막:** 특정 애플리케이션 버전을 실행하는 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-358">**Subtitle:** Devices running specific application versions</span></span>
4.  <span data-ttu-id="f7f86-359">도넛 **속성 정의:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-359">Define the **Donut** properties:</span></span><br>
    <span data-ttu-id="f7f86-360">**쿼리:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span><span class="sxs-lookup"><span data-stu-id="f7f86-360">**Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize App_Version = max(SRSAppVersion_CF) by Computer | summarize AggregatedValue = count() by App_Version | sort by App_Version asc```</span></span><br>
    <span data-ttu-id="f7f86-361">**텍스트 가운데:** 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-361">**Center Text:** Devices</span></span><br>
    <span data-ttu-id="f7f86-362">**작업:** 합계</span><span class="sxs-lookup"><span data-stu-id="f7f86-362">**Operation:** Sum</span></span>
5.  <span data-ttu-id="f7f86-363">목록 속성을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-363">Define the **List** properties.</span></span><br>
    <span data-ttu-id="f7f86-364">**쿼리 나열:**```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span><span class="sxs-lookup"><span data-stu-id="f7f86-364">**List Query:** ```Event | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize SRSAppVersion_CF = max(SRSAppVersion_CF) by Computer | sort by Computer asc```</span></span><br>
    <span data-ttu-id="f7f86-365">**그래프 숨기기:** 선택</span><span class="sxs-lookup"><span data-stu-id="f7f86-365">**Hide Graph:** Selected</span></span><br>
    <span data-ttu-id="f7f86-366">**스파크라인 사용:** 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-366">**Enable Sparklines:** Not selected</span></span>
6.  <span data-ttu-id="f7f86-367">열 **제목을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-367">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="f7f86-368">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="f7f86-368">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="f7f86-369">**값:** 비워 두기</span><span class="sxs-lookup"><span data-stu-id="f7f86-369">**Value:** Leave Empty</span></span>
7.  <span data-ttu-id="f7f86-370">탐색 **쿼리를 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-370">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and SRSOperationName_CF == "Heartbeat" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
8.  <span data-ttu-id="f7f86-371">적용을 **선택한** 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-371">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-an-application-error"></a><span data-ttu-id="f7f86-372">애플리케이션 오류가 있는 디바이스를 표시하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-372">Create a tile that displays devices that have an application error</span></span>

1.  <span data-ttu-id="f7f86-373">갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-373">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="f7f86-374">일반 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-374">Define the **General** properties.</span></span><br>
    <span data-ttu-id="f7f86-375">**그룹 제목:** 비워 두기</span><span class="sxs-lookup"><span data-stu-id="f7f86-375">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="f7f86-376">**새 그룹:** 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-376">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="f7f86-377">타일 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-377">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="f7f86-378">**범례:** 지난 1시간 동안 애플리케이션 오류가 발생한 디바이스</span><span class="sxs-lookup"><span data-stu-id="f7f86-378">**Legend:** Devices that experienced an application error in the last hour</span></span><br>
    <span data-ttu-id="f7f86-379">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="f7f86-379">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="f7f86-380">목록 속성을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-380">Define the **List** properties.</span></span><br>
    <span data-ttu-id="f7f86-381">**쿼리 나열:**```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span><span class="sxs-lookup"><span data-stu-id="f7f86-381">**List Query:** ```Event | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h) | summarize TimeGenerated = max(TimeGenerated) by Computer | order by TimeGenerated```</span></span>
5.  <span data-ttu-id="f7f86-382">열 **제목을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-382">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="f7f86-383">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="f7f86-383">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="f7f86-384">**값:** 마지막 오류</span><span class="sxs-lookup"><span data-stu-id="f7f86-384">**Value:** Last Error</span></span>
6.  <span data-ttu-id="f7f86-385">탐색 **쿼리를 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-385">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == 2001 and EventLevelName == "Error" | summarize arg_max(TimeGenerated, *) by Computer | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF | sort by TimeGenerated desc```
7.  <span data-ttu-id="f7f86-386">적용을 **선택한** 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-386">Select **Apply** and then **Close**.</span></span>

### <a name="create-a-tile-that-displays-devices-that-have-been-restarted"></a><span data-ttu-id="f7f86-387">다시 시작된 디바이스를 표시하는 타일 만들기</span><span class="sxs-lookup"><span data-stu-id="f7f86-387">Create a tile that displays devices that have been restarted</span></span>

1.  <span data-ttu-id="f7f86-388">갤러리에서 **&** 번호 매기기 목록을 선택한 다음 새 타일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-388">Select **Number & list** from the gallery, and then add a new tile.</span></span>
2.  <span data-ttu-id="f7f86-389">일반 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-389">Define the **General** properties.</span></span><br>
    <span data-ttu-id="f7f86-390">**그룹 제목:** 비워 두기</span><span class="sxs-lookup"><span data-stu-id="f7f86-390">**Group Title:** Leave empty</span></span><br>
    <span data-ttu-id="f7f86-391">**새 그룹:** 선택되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-391">**New Group:** Not Selected</span></span>
3.  <span data-ttu-id="f7f86-392">타일 **속성을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-392">Define the **Tile** properties.</span></span><br>
    <span data-ttu-id="f7f86-393">**범례:** 지난 24시간 동안 애플리케이션이 다시 시작된 디바이스 및 다시 시작 횟수</span><span class="sxs-lookup"><span data-stu-id="f7f86-393">**Legend:** Devices where the application was restarted in the last 24 hours, and number of restarts</span></span><br>
    <span data-ttu-id="f7f86-394">**타일 쿼리:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span><span class="sxs-lookup"><span data-stu-id="f7f86-394">**Tile Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | summarize AggregatedValue = count() by Computer | count```</span></span>
4.  <span data-ttu-id="f7f86-395">목록 속성을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-395">Define the **List** properties.</span></span><br>
    <span data-ttu-id="f7f86-396">**쿼리 나열:**```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span><span class="sxs-lookup"><span data-stu-id="f7f86-396">**List Query:** ```Event | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | order by TimeGenerated | summarize AggregatedValue = count(EventID) by Computer```</span></span>
5.  <span data-ttu-id="f7f86-397">열 **제목을 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-397">Define **Column Titles**.</span></span><br>
    <span data-ttu-id="f7f86-398">**이름:** 컴퓨터 이름</span><span class="sxs-lookup"><span data-stu-id="f7f86-398">**Name:** Computer Name</span></span><br>
    <span data-ttu-id="f7f86-399">**값:** 다시 시작 횟수</span><span class="sxs-lookup"><span data-stu-id="f7f86-399">**Value:** Number of Restarts</span></span>
6.  <span data-ttu-id="f7f86-400">탐색 **쿼리를 정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-400">Define **Navigation Query**.</span></span><br>
    ```search {selected item} | where EventLog == "Skype Room System" and EventID == "4000" and TimeGenerated > ago(24h) | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF```
7.  <span data-ttu-id="f7f86-401">적용을 **선택한** 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-401">Select **Apply** and then **Close**.</span></span>
8.  <span data-ttu-id="f7f86-402">**저장을** 선택하여 대시보드를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-402">Select **Save** to save your dashboard.</span></span>

<span data-ttu-id="f7f86-403">이제 보기 만들기를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-403">Now you've completed creating your views.</span></span>

## <a name="configure-alerts-in-no-loc-textazure-monitor"></a><span data-ttu-id="f7f86-404">에서 경고 구성 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-404">Configure Alerts in :::no-loc text="Azure Monitor":::</span></span>
<span data-ttu-id="f7f86-405"><a name="Alerts"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f86-405"><a name="Alerts"> </a></span></span>

<span data-ttu-id="f7f86-406">:::no-loc text="Azure Monitor"::: 콘솔에서 문제가 발생하면 관리자에게 알리기 위해 :::no-loc text="Microsoft Teams Rooms"::: 경고를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-406">:::no-loc text="Azure Monitor"::: can raise alerts to notify the administrators, when a :::no-loc text="Microsoft Teams Rooms"::: console encounters an issue.</span></span>

<span data-ttu-id="f7f86-407">:::no-loc text="Azure Monitor"::: 일정한 간격으로 예약된 로그 검색을 통해 실행되는 기본 제공 경고 메커니즘을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-407">:::no-loc text="Azure Monitor"::: includes a built-in alerting mechanism that runs through scheduled log searches at regular intervals.</span></span> <span data-ttu-id="f7f86-408">로그 검색 결과가 특정 조건과 일치하는 경우 경고 레코드가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-408">If the results of the log search match some particular criteria, an alert record is created.</span></span>

<span data-ttu-id="f7f86-409">그런 다음 규칙은 자동으로 하나 이상의 작업을 실행하여 경고를 사전에 알리거나 다른 프로세스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-409">The rule can then automatically run one or more actions to proactively notify you of the alert or invoke another process.</span></span> <span data-ttu-id="f7f86-410">경고를 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-410">The possible options with alerts are:</span></span>
-   <span data-ttu-id="f7f86-411">전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="f7f86-411">Sending an email</span></span>
-   <span data-ttu-id="f7f86-412">HTTP POST 요청을 통해 외부 프로세스 호출</span><span class="sxs-lookup"><span data-stu-id="f7f86-412">Invoking an external process through an HTTP POST request</span></span>
-   <span data-ttu-id="f7f86-413">서비스에서 Runbook :::no-loc text="Azure Automation"::: 시작</span><span class="sxs-lookup"><span data-stu-id="f7f86-413">Starting a runbook in :::no-loc text="Azure Automation"::: service</span></span>

<span data-ttu-id="f7f86-414">의 [경고에 :::no-loc text="Azure Monitor"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) 대한 자세한 내용은 로그 경고를 참조합니다. :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-414">See [Log alerts in :::no-loc text="Azure Monitor":::](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-unified-log) to learn more about the alerts in :::no-loc text="Azure Monitor":::.</span></span>

> [!NOTE]
> <span data-ttu-id="f7f86-415">다음 예제에서는 디바이스가 하드웨어 또는 애플리케이션 오류를 생성하는 경우 이메일 :::no-loc text="Microsoft Teams Rooms"::: 경고를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-415">The following examples send email alerts when a :::no-loc text="Microsoft Teams Rooms"::: device generates a hardware or an application error.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-hardware-issues"></a><span data-ttu-id="f7f86-416">하드웨어 문제에 대한 전자 메일 :::no-loc text="Microsoft Teams Rooms"::: 경고 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-416">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: hardware issues</span></span>

<span data-ttu-id="f7f86-417">지난 1시간 이내에 하드웨어 문제가 발생하는 디바이스를 검사하는 경고 :::no-loc text="Microsoft Teams Rooms"::: 규칙을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-417">Configure an alert rule that checks for :::no-loc text="Microsoft Teams Rooms"::: devices that have encountered hardware issues within the last hour.</span></span>
1.  <span data-ttu-id="f7f86-418">포털에 [ :::no-loc text="Microsoft Azure"::: 로그인하고](https://portal.azure.com) 작업 영역으로 :::no-loc text="Log Analytics"::: 이동하여 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-418">Sign in to the [:::no-loc text="Microsoft Azure"::: portal](https://portal.azure.com) and go to :::no-loc text="Log Analytics"::: and select your workspace.</span></span>

2. <span data-ttu-id="f7f86-419">작업 :::no-loc text="Log Analytics"::: 영역으로 이동하여 **경고를** 선택한 다음 새 경고 **규칙을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-419">Navigate to your :::no-loc text="Log Analytics"::: workspace and select **Alerts** and then select **New alert rule**</span></span>

3. <span data-ttu-id="f7f86-420">조건 **추가 및** 사용자 지정 로그 검색 **선택**</span><span class="sxs-lookup"><span data-stu-id="f7f86-420">Select **Add condition** and then **Custom log search**</span></span>

4.  <span data-ttu-id="f7f86-421">검색 쿼리 텍스트 상자에 다음 쿼리를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-421">Enter the following query to the Search query text box.</span></span><br>
    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "3001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSConfMicrophoneStatus_CF, SRSConfSpeakerStatus_CF, SRSDefaultSpeakerStatus_CF, SRSCameraStatus_CF, SRSFORDStatus_CF, SRSMotionSensorStatus_CF, SRSHDMIIngestStatus_CF, SRSEventDescription_CF
    |sort by TimeGenerated desc
    ```

5.  <span data-ttu-id="f7f86-422">경고 논리 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-422">Configure the Alert logic settings:</span></span><br>
    <span data-ttu-id="f7f86-423">**기준:** 결과 수</span><span class="sxs-lookup"><span data-stu-id="f7f86-423">**Based on:** Number of results</span></span><br>
    <span data-ttu-id="f7f86-424">**조건:** 다음을 1보다 높게</span><span class="sxs-lookup"><span data-stu-id="f7f86-424">**Condition:** Greater then</span></span><br>
    <span data-ttu-id="f7f86-425">**임계값:** 0</span><span class="sxs-lookup"><span data-stu-id="f7f86-425">**Threshold:** 0</span></span><br>

6. <span data-ttu-id="f7f86-426">평가 설정을 구성하고 **완료:**</span><span class="sxs-lookup"><span data-stu-id="f7f86-426">Configure Evaluation settings and select **Done**:</span></span> <br>
    <span data-ttu-id="f7f86-427">**기간(분):** 60</span><span class="sxs-lookup"><span data-stu-id="f7f86-427">**Period (in minutes):** 60</span></span><br>
    <span data-ttu-id="f7f86-428">**빈도(분):** 60</span><span class="sxs-lookup"><span data-stu-id="f7f86-428">**Frequency (in minutes):** 60</span></span><br>

7. <span data-ttu-id="f7f86-429">작업 그룹을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-429">Configure action groups:</span></span>
    1.  <span data-ttu-id="f7f86-430">새로 **만들기 선택**</span><span class="sxs-lookup"><span data-stu-id="f7f86-430">Select **Create New**</span></span>
    2.  <span data-ttu-id="f7f86-431">작업 그룹 이름  및 짧은 이름 필드에 *적합한 이름을* 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-431">Provide suitable names for the *Action group name* and *Short Name* fields.</span></span>
    3.  <span data-ttu-id="f7f86-432">고유한 작업 *이름을 지정하고* **전자 메일/SMS/푸시/음성을** 선택한 다음 세부 정보 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-432">Specify a unique *Action Name* and select **Email/SMS/Push/Voice**, and then select **Edit details**.</span></span>
    4.  <span data-ttu-id="f7f86-433">전자 메일 **확인란을** 선택하고 알림을 받을 사용자 또는 그룹의 전자 메일 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-433">Select the **Email** checkbox and provide the email address of the person or group that will receive the alerts.</span></span>
    5.  <span data-ttu-id="f7f86-434">SMS, 음성 통화 또는 둘 다로 알림을 받을 전화 번호를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-434">You may also provide your phone number to get notified with SMS, a voice call or both.</span></span>
    6. <span data-ttu-id="f7f86-435">확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-435">Select **OK**.</span></span>

8. <span data-ttu-id="f7f86-436">**경고 전자** 메일의 제목 줄을 다시 정의할 경우 작업을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-436">**Customize Actions** if you like to override the subject line of the alert emails.</span></span>

9. <span data-ttu-id="f7f86-437">규칙 이름 및 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-437">Specify a rule name and description.</span></span><br>
    <span data-ttu-id="f7f86-438">**규칙 이름:** :::no-loc text="Microsoft Teams Rooms"::: 하드웨어 오류 경고</span><span class="sxs-lookup"><span data-stu-id="f7f86-438">**Rule Name:** :::no-loc text="Microsoft Teams Rooms"::: Hardware Failure Alert</span></span><br>
    <span data-ttu-id="f7f86-439">**설명:** 지난 1시간 이내에 하드웨어 문제가 발생한 디바이스 목록</span><span class="sxs-lookup"><span data-stu-id="f7f86-439">**Description:** List of devices that encountered a hardware issue within the last hour</span></span><br>

10. <span data-ttu-id="f7f86-440">의도한 심각도 선택 및 규칙이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-440">Select the intended severity and make sure the rule is enabled.</span></span>

11. <span data-ttu-id="f7f86-441">경고 **규칙 만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-441">Select **Create alert rule**.</span></span>

### <a name="configure-an-email-alert-for-no-loc-textmicrosoft-teams-rooms-application-issues"></a><span data-ttu-id="f7f86-442">애플리케이션 문제에 대한 이메일 :::no-loc text="Microsoft Teams Rooms"::: 경고 구성</span><span class="sxs-lookup"><span data-stu-id="f7f86-442">Configure an email alert for :::no-loc text="Microsoft Teams Rooms"::: application issues</span></span>

<span data-ttu-id="f7f86-443">동일한 절차를 반복하지만 다음 쿼리를 사용하여 지난 1시간 내에 애플리케이션 문제가 발생한 디바이스를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-443">Repeat the same procedure but use the following query to list devices that have encountered application issues within the last hour.</span></span>

    ```
    Event
    | where EventLog == "Skype Room System" and EventLevelName == "Error" and EventID == "2001" and TimeGenerated > ago(1h)
    | summarize arg_max(TimeGenerated, *) by Computer
    | project TimeGenerated, Computer, SRSAlias_CF, SRSAppVersion_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF, SRSOperationName_CF, SRSOperationResult_CF, SRSResourceState_CF, SRSEventDescription_CF
    | sort by TimeGenerated desc
    ```

<span data-ttu-id="f7f86-444">이제 경고 정의를 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-444">Now you've completed defining alerts.</span></span> <span data-ttu-id="f7f86-445">위의 예제를 사용하여 추가 경고를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-445">You can define additional alerts by using the examples above.</span></span>

<span data-ttu-id="f7f86-446">경고가 생성될 때 지난 1시간 이내에 문제가 발생한 디바이스를 나열하는 전자 메일을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-446">When an alert is generated, you'll get an email that lists the devices that encountered an issue within the last hour.</span></span>

<span data-ttu-id="f7f86-447">! [샘플 :::no-loc text="Azure Monitor"::: 경고 전자 메일](.. /media/Deploy-Azure-Monitor-6.png "샘플 :::no-loc text="Azure Monitor"::: 경고 전자 메일")</span><span class="sxs-lookup"><span data-stu-id="f7f86-447">![Sample :::no-loc text="Azure Monitor"::: alert email](../media/Deploy-Azure-Monitor-6.png "Sample :::no-loc text="Azure Monitor"::: alert email")</span></span>

## <a name="configure-all-devices-for-no-loc-textazure-monitoring"></a><span data-ttu-id="f7f86-448">모든 디바이스 구성 :::no-loc text="Azure Monitoring":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-448">Configure all devices for :::no-loc text="Azure Monitoring":::</span></span>
<span data-ttu-id="f7f86-449"><a name="configure_all_devices"></a> 대시보드 및 경고를 구성한 후 모니터링 배포를 완료하도록 모든 디바이스에서 에이전트를 설정하고 :::no-loc text="Microsoft Monitoring"::: :::no-loc text="Microsoft Teams Rooms"::: 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-449"><a name="configure_all_devices"> </a> After the dashboards and alerts are configured, you can set up and configure :::no-loc text="Microsoft Monitoring"::: agent on all :::no-loc text="Microsoft Teams Rooms"::: devices to complete your monitoring deployment.</span></span>

<span data-ttu-id="f7f86-450">각 디바이스에서 에이전트를 수동으로 설치 및 구성할 수 있지만 기존 소프트웨어 배포 도구 및 방법을 :::no-loc text="Microsoft Monitoring"::: 활용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-450">Although you can install and configure the :::no-loc text="Microsoft Monitoring"::: agent manually on each device, we highly recommend you leverage existing software deployment tools and methods.</span></span>

<span data-ttu-id="f7f86-451">처음으로 디바이스를 빌드하는 경우 빌드 프로세스의 일부로 에이전트 설정 및 구성 단계를 포함할 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Microsoft Monitoring"::: 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-451">If you're building your :::no-loc text="Microsoft Teams Rooms"::: devices for the first time, you might want to include the :::no-loc text="Microsoft Monitoring"::: agent setup and configuration steps as part of your build process.</span></span> <span data-ttu-id="f7f86-452">자세한 내용은 명령줄을 사용하여 [에이전트 설치를 참조하세요.](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="f7f86-452">For more information, see [Install the agent using the command line](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-the-agent-using-the-command-line).</span></span>

### <a name="deploying-no-loc-textmicrosoft-monitoring-agent-by-using-a-group-policy-object-gpo"></a><span data-ttu-id="f7f86-453">:::no-loc text="Microsoft Monitoring":::GPO(그룹 정책 개체)를 사용하여 에이전트 배포</span><span class="sxs-lookup"><span data-stu-id="f7f86-453">Deploying :::no-loc text="Microsoft Monitoring"::: agent by using a Group Policy Object (GPO)</span></span>

<span data-ttu-id="f7f86-454">구현하기 전에 디바이스를 이미 배포한 경우 제공된 스크립트를 사용하여 그룹 정책 개체를 사용하여 에이전트를 설정하고 :::no-loc text="Microsoft Teams Rooms"::: :::no-loc text="Azure Monitoring"::: 구성할 :::no-loc text="Active Directory"::: 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-454">If you already deployed your :::no-loc text="Microsoft Teams Rooms"::: devices before you implement :::no-loc text="Azure Monitoring":::, you can use the provided script to set up and configure the agents by using :::no-loc text="Active Directory"::: group policy objects.</span></span>

1.  <span data-ttu-id="f7f86-455">공유 네트워크 경로를 만들고 도메인 컴퓨터 그룹에 대한 읽기 **액세스 권한을 부여합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-455">Create a shared network path and grant read access to **Domain Computers** group.</span></span>

2.  <span data-ttu-id="f7f86-456">다음에서 에이전트의 64비트 :::no-loc text="Microsoft Monitoring"::: 버전을 :::no-loc text="Windows"::: 다운로드합니다. <https://go.microsoft.com/fwlink/?LinkID=517476></span><span class="sxs-lookup"><span data-stu-id="f7f86-456">Download the 64-bit version of the :::no-loc text="Microsoft Monitoring"::: Agent for :::no-loc text="Windows"::: from <https://go.microsoft.com/fwlink/?LinkID=517476></span></span>

3.  <span data-ttu-id="f7f86-457">설치 패키지의 내용을 네트워크 공유에 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-457">Extract the contents of the setup package into the network share.</span></span>
    1.  <span data-ttu-id="f7f86-458">명령 프롬프트 창을 열고 **/c를MMASetup-AMD64.exe 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-458">Open a Command Prompt window, and then execute **MMASetup-AMD64.exe /c**</span></span>
    2.  <span data-ttu-id="f7f86-459">방금 만든 공유를 지정하고 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-459">Specify the share you just created, and extract the content.</span></span>

4.  <span data-ttu-id="f7f86-460">새 그룹 정책 개체를 만들고 컴퓨터 계정이 있는 조직 :::no-loc text="Microsoft Teams Rooms"::: 단위에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-460">Create a new Group Policy Object and assign it to the organizational unit where :::no-loc text="Microsoft Teams Rooms"::: machine accounts are located.</span></span>

5.  <span data-ttu-id="f7f86-461">PowerShell 실행 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-461">Configure PowerShell execution policy:</span></span>
    1.  <span data-ttu-id="f7f86-462">새로 만든 그룹 정책 개체를 편집하고 컴퓨터 구성 정책 관리 템플릿 구성 요소로 \\ \\ \\ :::no-loc text="Windows"::: 이동합니다. \\:::no-loc text="Windows PowerShell":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-462">Edit the newly created Group Policy Object and navigate to Computer Configuration \\ Policies \\ Administrative Templates \\ :::no-loc text="Windows"::: Components \\ :::no-loc text="Windows PowerShell":::</span></span>
    2.  <span data-ttu-id="f7f86-463">스크립트 **실행을 켜고**  로컬 스크립트를 허용하도록 실행 **정책을 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-463">Enable the **Turn on Script Execution** and set **Execution Policy** to **Allow Local Scripts**.</span></span>

6.  <span data-ttu-id="f7f86-464">시작 스크립트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-464">Configure the startup script:</span></span>
    1.  <span data-ttu-id="f7f86-465">다음 스크립트를 복사하고 다음 스크립트로 Install-MMAgent.ps1.</span><span class="sxs-lookup"><span data-stu-id="f7f86-465">Copy the following script and save it as Install-MMAgent.ps1.</span></span>
    2.  <span data-ttu-id="f7f86-466">WorkspaceId, WorkspaceKey 및 SetupPath 매개 변수를 구성과 일치하도록 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-466">Modify WorkspaceId, WorkspaceKey, and SetupPath parameters to match your configuration.</span></span>
    3.  <span data-ttu-id="f7f86-467">동일한 그룹 정책 개체를 편집하고 컴퓨터 구성 정책 \\ \\ :::no-loc text="Windows"::: 설정 \\ 스크립트(시작/종료)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-467">Edit the same Group Policy Object and navigate to Computer Configuration \\ Policies \\ :::no-loc text="Windows"::: Settings \\ Scripts (Startup/Shutdown)</span></span>
    4.  <span data-ttu-id="f7f86-468">시작을 선택하려면 두 번 클릭한 다음 **PowerShell 스크립트를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-468">Double-click to select **Startup**, and then select **PowerShell Scripts**.</span></span>
    5.  <span data-ttu-id="f7f86-469">파일 **표시를** 선택한 다음Install-MMAgent.ps1파일을 해당 **폴더에** 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-469">Select **Show Files**, and then copy the **Install-MMAgent.ps1** file to that folder.</span></span>
    6.  <span data-ttu-id="f7f86-470">**추가를** 선택한 다음 **찾아보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f7f86-470">Select **Add**, and then **Browse**.</span></span>
    7.  <span data-ttu-id="f7f86-471">방금 복사한 ps1 스크립트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-471">Select the ps1 script you just copied.</span></span>

7.  <span data-ttu-id="f7f86-472">:::no-loc text="Microsoft Teams Rooms"::: 디바이스는 두 번째 재부팅을 통해 에이전트를 설치하고 :::no-loc text="Microsoft Monitoring"::: 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-472">:::no-loc text="Microsoft Teams Rooms"::: devices should install and configure the :::no-loc text="Microsoft Monitoring"::: agent with the second reboot.</span></span>

```PowerShell
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
> <span data-ttu-id="f7f86-473">에이전트를 다시 구성하거나, 다른 작업 영역으로 이동하거나, 초기 설치 후 프록시 설정을 수정해야 하는 경우 에이전트 관리 및 유지 관리 문서를 참조할 수 있습니다. [ :::no-loc text="Log Analytics"::: ](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage)</span><span class="sxs-lookup"><span data-stu-id="f7f86-473">You can refer to the article [Managing and maintaining the :::no-loc text="Log Analytics"::: agent](https://docs.microsoft.com/azure/azure-monitor/platform/agent-manage) when you need to reconfigure an agent, move it to a different workspace, or modify proxy settings after the initial installation.</span></span>

## <a name="additional-solutions"></a><span data-ttu-id="f7f86-474">추가 솔루션</span><span class="sxs-lookup"><span data-stu-id="f7f86-474">Additional Solutions</span></span>
<span data-ttu-id="f7f86-475"><a name="Solutions"> </a></span><span class="sxs-lookup"><span data-stu-id="f7f86-475"><a name="Solutions"> </a></span></span>

<span data-ttu-id="f7f86-476">:::no-loc text="Azure Monitor":::환경을 추가로 모니터링할 수 [](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) 있도록 솔루션 갤러리를 통해 기본 제공 관리 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-476">:::no-loc text="Azure Monitor"::: provides built-in management solutions through its [solution gallery](https://docs.microsoft.com/azure/azure-monitor/insights/solutions) to further help you monitor your environment.</span></span> <span data-ttu-id="f7f86-477">작업 영역도 경고 [](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) 관리 및 [ :::no-loc text="Azure Log Analytics"::: 에이전트 상태](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) 솔루션을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-477">We highly recommend that you add [Alert Management](https://docs.microsoft.com/azure/azure-monitor/platform/alert-management-solution) and [:::no-loc text="Azure Log Analytics"::: Agent Health](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth) solutions to your workspace as well.</span></span>

> [!NOTE]
> <span data-ttu-id="f7f86-478">에이전트 상태 솔루션은 사용자 환경 내에서 사용되지 않은 에이전트 또는 손상된 에이전트를 식별하는 데 도움이 될 수 있으며, 경고 관리 솔루션은 특정 기간 내에 발생된 경고에 대한 세부 :::no-loc text="Microsoft Monitoring"::: 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7f86-478">The Agent Health solution can help you identify outdated or broken :::no-loc text="Microsoft Monitoring"::: agents within your environment, and the Alert Management solution provides details about the alerts that have been raised within a given period.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7f86-479">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7f86-479">See also</span></span>

[<span data-ttu-id="f7f86-480">계획 :::no-loc text="Microsoft Teams Rooms"::: 관리 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-480">Plan :::no-loc text="Microsoft Teams Rooms"::: management with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-plan.md)

[<span data-ttu-id="f7f86-481">디바이스를 :::no-loc text="Microsoft Teams Rooms"::: 사용하여 관리 :::no-loc text="Azure Monitor":::</span><span class="sxs-lookup"><span data-stu-id="f7f86-481">Manage :::no-loc text="Microsoft Teams Rooms"::: devices with :::no-loc text="Azure Monitor":::</span></span>](azure-monitor-manage.md)
