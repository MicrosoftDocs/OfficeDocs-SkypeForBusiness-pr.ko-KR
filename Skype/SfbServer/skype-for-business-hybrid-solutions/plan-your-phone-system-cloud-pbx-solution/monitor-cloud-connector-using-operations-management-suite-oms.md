---
title: 운영 관리 제품군(OMS)을 사용하여 클라우드 커넥터 모니터링
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 이 항목을 통해 Microsoft Operations Management Suite(OMS)를 사용하여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 55685aae01bdcc3c7c979627dbba910bb33203fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098544"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="87f73-103">운영 관리 제품군(OMS)을 사용하여 클라우드 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="87f73-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="87f73-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="87f73-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="87f73-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="87f73-106">이 항목을 통해 Microsoft Operations Management Suite(OMS)를 사용하여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="87f73-107">이제 Microsoft 클라우드 IT 관리 솔루션인 OMS(Operations Management Suite)를 사용하여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="87f73-108">OMS Log Analytics를 사용하면 물리적 및 가상 컴퓨터를 비롯한 리소스의 가용성 및 성능을 모니터링하고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="87f73-109">OMS 및 Log Analytics에 대한 자세한 내용은 [OMS(Operations Management Suite)란?을 참조하세요.](/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="87f73-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="87f73-110">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="87f73-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="87f73-111">Prerequisites</span></span>

- <span data-ttu-id="87f73-112">OMS를 사용하도록 클라우드 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="87f73-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="87f73-113">OMS 구성</span><span class="sxs-lookup"><span data-stu-id="87f73-113">Configure OMS</span></span>

- <span data-ttu-id="87f73-114">Log Analytics 리포지토리의 경고 분석</span><span class="sxs-lookup"><span data-stu-id="87f73-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="87f73-115">권장 모니터링 집합</span><span class="sxs-lookup"><span data-stu-id="87f73-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87f73-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="87f73-116">Prerequisites</span></span>

<span data-ttu-id="87f73-117">OMS를 사용하여 클라우드 커넥터 배포를 모니터링하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="87f73-118">**Azure 계정 및 OMS 작업 영역**</span><span class="sxs-lookup"><span data-stu-id="87f73-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="87f73-119">Azure 계정이 아직 없는 경우 OMS 로그 분석을 사용할 계정을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="87f73-120">Azure 계정을 만들고 OMS 작업 영역 설정하는 방법에 대한 자세한 내용은 [Get started with a Log Analytics workspace을 참조하십시오.](/azure/log-analytics/log-analytics-get-started)</span><span class="sxs-lookup"><span data-stu-id="87f73-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="87f73-121">**클라우드 커넥터 버전 2.1 이상**</span><span class="sxs-lookup"><span data-stu-id="87f73-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="87f73-122">**Log Analytics 클라우드 커넥터 모니터링을 위해** 새 로그 검색이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="87f73-123">자세한 내용은 새 로그 검색으로 Azure Log Analytics 작업 [영역 업그레이드를 참조하세요.](/azure/log-analytics/log-analytics-log-search-upgrade)</span><span class="sxs-lookup"><span data-stu-id="87f73-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="87f73-124">OMS를 사용하도록 클라우드 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="87f73-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="87f73-125">OMS를 사용하도록 클라우드 커넥터의 사내 환경을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="87f73-126">이렇게하려면 다음과 같이 OMS 포털을 사용하여 찾을 수 있는 OMS 작업 영역 ID 및 키가 필요합니다. 설정 -- 연결된 원본 \> -- \> Windows Server:</span><span class="sxs-lookup"><span data-stu-id="87f73-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![클라우드 커넥터 OMS 스크린샷](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="87f73-128">OMS를 사용하도록 클라우드 커넥터를 구성하는 방법은 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="87f73-129">**새 Cloud Connector 어플라이언스를** 설치하거나 어플라이언스를 다시 배포하려는 경우 Install-CcAppliance를 실행하기 전에 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="87f73-130">파일 CloudConnector.ini [Common] 섹션에서 OMSEnabled 매개 변수를 True로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="87f73-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="87f73-131">클라우드 커넥터를 배포하거나 업그레이드할 때마다 OMS 에이전트를 VM에 자동으로 설치하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="87f73-132">OMS 에이전트가 클라우드 커넥터 자동 업데이트를 사용할 수 있도록 이 기능을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="87f73-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="87f73-133">OMS ID 및 키를 구성하려면 -AccountType Set-CcCredential OMSWorkspace를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="87f73-134">기존 Cloud Connector Appliance에 **OMS** 에이전트를 설치하는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="87f73-135">[common] CloudConnector.ini 파일에서 OMSEnabled=true를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="87f73-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="87f73-136">Import-CcConfiguration을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="87f73-137">Install-CcOMSAgent를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="87f73-138">OMSWorkspace 자격 증명을 설정하지 않은 경우 install-CcOMSAgent를 실행할 때 자격 증명을 입력하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="87f73-139">**이미 OMS 에이전트를 설치한 Cloud Connector 어플라이언스에서 OMS 작업 영역 ID 또는 키를 업데이트하려는 경우:**</span><span class="sxs-lookup"><span data-stu-id="87f73-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="87f73-140">OMS ID 및 키를 구성하려면 -AccountType Set-CcCredential OMSWorkspace를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="87f73-141">업데이트를 적용하려면 Install-CcOMSAgent를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="87f73-142">**모든 시나리오에서 에이전트가 다음과 같이 연결되어 있는지 확인해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="87f73-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="87f73-143">OMS 포털에서 설정 - 연결된 원본 \> - \> Windows Server로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="87f73-144">연결된 컴퓨터 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="87f73-145">OMS 구성</span><span class="sxs-lookup"><span data-stu-id="87f73-145">Configure OMS</span></span>

<span data-ttu-id="87f73-146">그런 다음 OMS 포털을 사용하여 OMS 구성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="87f73-147">특히 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="87f73-148">이벤트 로그 및 성능 카운터에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="87f73-149">알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="87f73-150">이벤트 로그 및 성능 카운터에 대한 정보 지정</span><span class="sxs-lookup"><span data-stu-id="87f73-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="87f73-151">OMS 포털에서 다음과 같이 이벤트 로그 및 성능 카운터에 대한 정보를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="87f73-152">설정 - 데이터 - Windows 이벤트 로그로 \> \> 이동하고 다음에 대한 이벤트 로그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="87f73-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="87f73-153">Lync Server</span></span>

   - <span data-ttu-id="87f73-154">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="87f73-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="87f73-155">텍스트 상자에 Lync Server를 수동으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="87f73-156">드롭다운 목록에 옵션으로 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="87f73-157">자세한 내용은 [Log Analytics에서 Windows 이벤트 로그 데이터 원본을 참조하세요.](/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="87f73-157">For more information, see [Windows event log data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="87f73-158">설정 - \> 데이터 - \> Windows 성능 카운터로 이동하여 다음에 대한 성능 카운터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="87f73-159">**OS 수준 카운터**.</span><span class="sxs-lookup"><span data-stu-id="87f73-159">**OS level counters**.</span></span> <span data-ttu-id="87f73-160">프로세서 사용량, 메모리 사용량, 네트워크 사용 등의 OS 수준 카운터를 추가하거나 카운터를 명시적으로 추가하지 않고 용량 및 성능, 네트워크 성능 모니터 등의 기존 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="87f73-161">이러한 카운터를 모니터링하기로 결정한 방식에 상관없이 Microsoft는 이러한 OS 카운터를 모니터링하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="87f73-162">**비즈니스용 Skype 카운터**.</span><span class="sxs-lookup"><span data-stu-id="87f73-162">**Skype for Business counters**.</span></span> <span data-ttu-id="87f73-163">비즈니스용 Skype에서 제공하는 다양한 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="87f73-164">중재 서버에 로그온하고 성능 모니터를 열면 이러한 카운터를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="87f73-165">이러한 카운터는 "LS:"로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-165">These counters start with "LS:".</span></span> <span data-ttu-id="87f73-166">최소한 다음 용량 카운터로 시작하고 관심 있는 다른 카운터를 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="87f73-167">총 활성 통화 수:</span><span class="sxs-lookup"><span data-stu-id="87f73-167">Total active calls:</span></span>

       - <span data-ttu-id="87f73-168">LS:MediationServer - 인바운드 통화(_Total) \- 현재</span><span class="sxs-lookup"><span data-stu-id="87f73-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="87f73-169">LS:MediationServer - 아웃바운드 통화(_Total) \- 현재</span><span class="sxs-lookup"><span data-stu-id="87f73-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="87f73-170">총 활성 미디어 우회 통화:</span><span class="sxs-lookup"><span data-stu-id="87f73-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="87f73-171">LS:MediationServer - 인바운드 통화(_Total) \- 활성 미디어 우회 통화</span><span class="sxs-lookup"><span data-stu-id="87f73-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="87f73-172">LS:MediationServer - 아웃바운드 통화(_Total) \- 활성 미디어 우회 통화</span><span class="sxs-lookup"><span data-stu-id="87f73-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="87f73-173">텍스트 상자에 성능 카운터를 수동으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="87f73-174">드롭다운 목록에 옵션으로 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="87f73-175">자세한 내용은 Log Analytics에서 Windows 및 Linux 성능 [데이터 원본을 참조하세요.](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="87f73-175">For more information, see [Windows and Linux performance data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="87f73-176">경고 만들기</span><span class="sxs-lookup"><span data-stu-id="87f73-176">Create alerts</span></span>

<span data-ttu-id="87f73-177">OMS에는 결과 경고 수와 메트릭 측정 경고의 두 가지 유형의 경고가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="87f73-178">경고를 만드는 데 대한 자세한 내용은 Log Analytics에서 경고 [규칙 작업을 참조하세요.](/azure/log-analytics/log-analytics-alerts-creating)</span><span class="sxs-lookup"><span data-stu-id="87f73-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="87f73-179">알림을 만들 때 다음을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="87f73-180">알림이 결과 수 알림(기본 선택)으로 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="87f73-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="87f73-181">데모 쿼리를 사용하려면 "결과 수"를 "0보다 크다"로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="87f73-182">시간 창과 경고 빈도를 모두 5분으로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="87f73-183">데모 경고에 대해 "경고 표시 안 하도록"를 설정하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="87f73-184">일반적인 경고 시나리오의 경우 한 쌍의 경고인 하나의 오류 경고와 한 번의 초기화 경고를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="87f73-185">오류 경고에 대해 심각도 수준 중요를 선택합니다. 다시 설정 경고에 대해 심각도 수준 정보 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="87f73-186">다음 섹션에서는 예제 경고를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="87f73-187">**경고 쌍 만들기: "RTCMEDSRV가 중재 서버에서 실행되고 있지 않습니다." 및 "RTCMEDSRV가 중재 서버에서 다시 실행 중입니다."**</span><span class="sxs-lookup"><span data-stu-id="87f73-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="87f73-188">이 경고 쌍을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-188">To create this alert pair:</span></span>

- <span data-ttu-id="87f73-189">오류 경고에 대한 쿼리는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="87f73-190">쿼리는 컴퓨터 필터를 *사용합니다. 컴퓨터는 "MediationServer"를 가 포함되어 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="87f73-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="87f73-191">필터는 이름에 문자열 "MediationServer"가 포함된 컴퓨터만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="87f73-192">필터를 자체 컴퓨터 필터로 바꾸거나 제거하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="87f73-193">정규식 없이 복잡한 문자열 필터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="87f73-194">자세한 내용은 [문자열 연산자를 참조하세요.](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)</span><span class="sxs-lookup"><span data-stu-id="87f73-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="87f73-195">또한 정규식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="87f73-196">또한 검색 쿼리를 저장하고 해당 그룹을 경고 쿼리의 컴퓨터 필터로 사용하여 컴퓨터 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="87f73-197">자세한 내용은 Log Analytics 로그 검색의 컴퓨터 [그룹을 참조하세요.](/azure/log-analytics/log-analytics-computer-groups)</span><span class="sxs-lookup"><span data-stu-id="87f73-197">For more information, see [Computer groups in Log Analytics log searches](/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="87f73-198">각 컴퓨터에 대해 오류 쿼리는 RTCMEDSRV 서비스 시작 및 서비스 중지 모두에 대한 마지막 이벤트 로그를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="87f73-199">마지막 이벤트가 서비스 중지 이벤트인 경우 로그가 하나 반환됩니다. 마지막 이벤트가 서비스 시작 이벤트인 경우 아무 것도 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="87f73-200">즉, 쿼리는 시간 창에서 RTCMEDSRV가 중지된 서버 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="87f73-201">다시 설정 경고에 대한 쿼리는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="87f73-202">다시 설정 쿼리는 오류 쿼리와 정확히 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="87f73-203">각 컴퓨터에 대해 마지막 이벤트가 서비스 시작 이벤트인 경우 1이 반환됩니다. 마지막 이벤트가 서비스 중지 이벤트인 경우 아무 것도 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="87f73-204">**경고 쌍 만들기: "중재 서버에서 동시 통화가 너무 많지 않습니다." 및 "동시 통화가 정상 부하로 돌아오기"**</span><span class="sxs-lookup"><span data-stu-id="87f73-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="87f73-205">이 경고를 만들 수 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="87f73-205">To create this alert:</span></span>

- <span data-ttu-id="87f73-206">오류 경고에 대한 쿼리는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="87f73-207">각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃바운드 통화에 대한 마지막 카운터를 구하고 이러한 두 값을 합산합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="87f73-208">합계 값이 500을 초과하면 로그가 하나 반환됩니다. 그렇지 않은 경우 아무 것도 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="87f73-209">즉, 쿼리는 동시 호출이 시간 창에 너무 많은 서버 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="87f73-210">다시 설정 경고에 대한 쿼리는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="87f73-211">다시 설정 쿼리는 오류 쿼리와 정확히 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="87f73-212">각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃바운드 통화에 대한 마지막 카운터를 구하고 이러한 두 값을 합산합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="87f73-213">합계 값이 500보다 작은 경우 하나의 로그가 반환됩니다. 그렇지 않으면 아무 것도 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="87f73-214">**경고 만들기: "서버에서 CPU 사용량 \> 90 또는 RTCMEDIARELAY 중지됨" 경고**</span><span class="sxs-lookup"><span data-stu-id="87f73-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="87f73-215">이 경고를 만들 수 있는 쿼리는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="87f73-216">이 쿼리는 모든 컴퓨터에서 모든 프로세서 사용 카운터 및 서비스 중지 이벤트를 발생하고 프로세서 사용량이 90%를 초과하거나 서비스가 중지된 경우 하나의 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="87f73-217">Log Analytics 리포지토리의 경고 분석</span><span class="sxs-lookup"><span data-stu-id="87f73-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="87f73-218">리포지토리의 경고를 분석하기 위해 경고 관리 솔루션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="87f73-219">자세한 내용은 [Operations Management Suite(OMS)의 경고 관리 솔루션을 참조하세요.](/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="87f73-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="87f73-220">권장되는 최소 모니터링 집합</span><span class="sxs-lookup"><span data-stu-id="87f73-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="87f73-221">이벤트 로그 및 성능 카운터와 관련한 문제를 식별하려면</span><span class="sxs-lookup"><span data-stu-id="87f73-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="87f73-222">**이벤트 로그.**</span><span class="sxs-lookup"><span data-stu-id="87f73-222">**Event logs.**</span></span> <span data-ttu-id="87f73-223">모든 문제의 경우 이벤트 쌍이 있을 수 있습니다. 하나의 이벤트 집합을 통해 문제가 있는 것을 나타내고 다른 하나는 모든 것이 양호하다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="87f73-224">특정 기간에 대해 기록된 마지막 이벤트로, 해당 기간에 대해 문제가 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="87f73-225">**성능 카운터.**</span><span class="sxs-lookup"><span data-stu-id="87f73-225">**Performance Counters.**</span></span> <span data-ttu-id="87f73-226">모니터링되는 카운터에 대한 임계값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="87f73-227">다음 표에는 중지 및 시작 이벤트 ID를 나열하여 Microsoft에서 모니터링을 권장하는 서비스가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="87f73-228">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="87f73-228">Service Name</span></span>  <br/> |<span data-ttu-id="87f73-229">대상 서버 역할</span><span class="sxs-lookup"><span data-stu-id="87f73-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="87f73-230">Stop 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="87f73-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="87f73-231">시작 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="87f73-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="87f73-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="87f73-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="87f73-233">중재 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="87f73-234">25003</span><span class="sxs-lookup"><span data-stu-id="87f73-234">25003</span></span>  <br/> |<span data-ttu-id="87f73-235">25002</span><span class="sxs-lookup"><span data-stu-id="87f73-235">25002</span></span>  <br/> |
|<span data-ttu-id="87f73-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="87f73-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="87f73-237">에지 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-237">Edge Server</span></span>  <br/> |<span data-ttu-id="87f73-238">12289</span><span class="sxs-lookup"><span data-stu-id="87f73-238">12289</span></span>  <br/> |<span data-ttu-id="87f73-239">12288</span><span class="sxs-lookup"><span data-stu-id="87f73-239">12288</span></span>  <br/> |
|<span data-ttu-id="87f73-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="87f73-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="87f73-241">에지 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-241">Edge Server</span></span>  <br/> |<span data-ttu-id="87f73-242">19003</span><span class="sxs-lookup"><span data-stu-id="87f73-242">19003</span></span>  <br/> |<span data-ttu-id="87f73-243">19002</span><span class="sxs-lookup"><span data-stu-id="87f73-243">19002</span></span>  <br/> |
|<span data-ttu-id="87f73-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="87f73-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="87f73-245">에지 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-245">Edge Server</span></span>  <br/> |<span data-ttu-id="87f73-246">22003</span><span class="sxs-lookup"><span data-stu-id="87f73-246">22003</span></span>  <br/> |<span data-ttu-id="87f73-247">22002</span><span class="sxs-lookup"><span data-stu-id="87f73-247">22002</span></span>  <br/> |

<span data-ttu-id="87f73-248">다음 표에는 Microsoft에서 모니터링을 권장하는 네트워크 문제가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="87f73-249">모니터 이름</span><span class="sxs-lookup"><span data-stu-id="87f73-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="87f73-250">대상 서버 역할</span><span class="sxs-lookup"><span data-stu-id="87f73-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="87f73-251">Success 이벤트 ID 식</span><span class="sxs-lookup"><span data-stu-id="87f73-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="87f73-252">Error 이벤트 ID 식</span><span class="sxs-lookup"><span data-stu-id="87f73-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="87f73-253">오류 예제</span><span class="sxs-lookup"><span data-stu-id="87f73-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="87f73-254">게이트웨이 연결 오류에 대한 중재 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="87f73-255">중재 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="87f73-256">25062</span><span class="sxs-lookup"><span data-stu-id="87f73-256">25062</span></span>                              |                                  | <span data-ttu-id="87f73-257">25002</span><span class="sxs-lookup"><span data-stu-id="87f73-257">25002</span></span>  <br/>           |
| <span data-ttu-id="87f73-258">게이트웨이 통화 완료 오류에 대한 중재 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="87f73-259">중재 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="87f73-260">25064</span><span class="sxs-lookup"><span data-stu-id="87f73-260">25064</span></span>                              |                                  | <span data-ttu-id="87f73-261">25002</span><span class="sxs-lookup"><span data-stu-id="87f73-261">25002</span></span>  <br/>           |
| <span data-ttu-id="87f73-262">중요한 네트워크 문제</span><span class="sxs-lookup"><span data-stu-id="87f73-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="87f73-263">에지 서버</span><span class="sxs-lookup"><span data-stu-id="87f73-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="87f73-264">14353</span><span class="sxs-lookup"><span data-stu-id="87f73-264">14353</span></span>                              |                                  | <span data-ttu-id="87f73-265">12288</span><span class="sxs-lookup"><span data-stu-id="87f73-265">12288</span></span>  <br/>           |

<span data-ttu-id="87f73-266">다음은 모니터링해야 하는 통화 용량 카운터를 나열하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="87f73-267">이러한 수치는 Cloud Connector Standard Edition의 경우 500보다 작아야 합니다. Cloud Connector 최소 버전은 50 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="87f73-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="87f73-268">LS:MediationServer - 인바운드 통화(_Total) \- 현재</span><span class="sxs-lookup"><span data-stu-id="87f73-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="87f73-269">LS:MediationServer - 아웃바운드 통화(_Total) \- 현재</span><span class="sxs-lookup"><span data-stu-id="87f73-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="87f73-270">LS:MediationServer - 인바운드 통화(_Total) \- 활성 미디어 우회 통화</span><span class="sxs-lookup"><span data-stu-id="87f73-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="87f73-271">LS:MediationServer - 아웃바운드 통화(_Total) \- 활성 미디어 우회 통화</span><span class="sxs-lookup"><span data-stu-id="87f73-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="87f73-272">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87f73-272">See also</span></span>

<span data-ttu-id="87f73-273">OMS 사용에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87f73-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="87f73-274">Log Analytics에서 로그 검색을 사용하여 데이터 찾기</span><span class="sxs-lookup"><span data-stu-id="87f73-274">Find data using log searches in Log Analytics</span></span>](/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="87f73-275">Azure Log Analytics 언어 참조</span><span class="sxs-lookup"><span data-stu-id="87f73-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="87f73-276">Log Analytics의 경고 이해</span><span class="sxs-lookup"><span data-stu-id="87f73-276">Understanding alerts in Log Analytics</span></span>](/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="87f73-277">Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결</span><span class="sxs-lookup"><span data-stu-id="87f73-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](/azure/log-analytics/log-analytics-windows-agents)