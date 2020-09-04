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
description: OMS (Microsoft Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링 하는 방법을 알아보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359094"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="fba6b-103">운영 관리 제품군(OMS)을 사용하여 클라우드 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="fba6b-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="fba6b-104">클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fba6b-105">조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="fba6b-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="fba6b-106">OMS (Microsoft Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링 하는 방법을 알아보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="fba6b-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="fba6b-107">이제 OMS (Operations Management Suite), Microsoft Cloud IT Management solution을 사용 하 여 클라우드 커넥터 버전 2.1 이상 배포를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="fba6b-108">OMS 로그 분석을 사용 하면 실제 및 가상 컴퓨터를 포함 하 여 리소스의 가용성과 성능을 모니터링 하 고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="fba6b-109">OMS 및 로그 분석에 대 한 자세한 내용은 [Operations Management Suite (OMS) 란?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fba6b-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="fba6b-110">이 항목에는 다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="fba6b-111">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fba6b-111">Prerequisites</span></span>

- <span data-ttu-id="fba6b-112">OMS를 사용 하도록 클라우드 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="fba6b-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="fba6b-113">OMS 구성</span><span class="sxs-lookup"><span data-stu-id="fba6b-113">Configure OMS</span></span>

- <span data-ttu-id="fba6b-114">로그 분석 리포지토리에서 경고 분석</span><span class="sxs-lookup"><span data-stu-id="fba6b-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="fba6b-115">권장 되는 모니터링 설정</span><span class="sxs-lookup"><span data-stu-id="fba6b-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fba6b-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fba6b-116">Prerequisites</span></span>

<span data-ttu-id="fba6b-117">OMS를 사용 하 여 클라우드 커넥터 배포를 모니터링 하려면 먼저 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="fba6b-118">**Azure 계정 및 OMS 작업 영역**</span><span class="sxs-lookup"><span data-stu-id="fba6b-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="fba6b-119">아직 Azure 계정이 없는 경우에는 OMS 로그 분석을 사용 하는 계정 만들기를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="fba6b-120">Azure 계정을 만들고 OMS 작업 영역을 설정 하는 방법에 대 한 자세한 내용은 [Log Analytics 작업 영역 시작](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fba6b-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="fba6b-121">**클라우드 커넥터 버전 2.1 이상**</span><span class="sxs-lookup"><span data-stu-id="fba6b-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="fba6b-122">로그 분석 클라우드 커넥터 모니터링에 **새 로그 검색이** 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="fba6b-123">자세한 내용은 [Azure Log Analytics 작업 영역을 새 로그 검색으로 업그레이드를](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fba6b-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="fba6b-124">OMS를 사용 하도록 클라우드 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="fba6b-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="fba6b-125">OMS를 사용 하려면 온-프레미스 환경에서 클라우드 커넥터를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="fba6b-126">이를 위해 oms 포털을 사용 하 여 찾을 수 있는 OMS 작업 영역 ID와 키 (설정-- \> 연결 원본--Windows 서버)가 필요 합니다 \> .</span><span class="sxs-lookup"><span data-stu-id="fba6b-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![클라우드 커넥터 OMS에 대 한 스크린샷](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="fba6b-128">OMS를 사용 하도록 클라우드 커넥터를 구성 하는 방법은 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="fba6b-129">**새 클라우드 커넥터 기기를 설치 하거나 기기를 다시 배포 하려는 경우**에는 설치-ccappliance를 실행 하기 전에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="fba6b-130">CloudConnector.ini 파일 [일반] 섹션에서 OMSEnabled 매개 변수를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="fba6b-131">클라우드 커넥터를 배포 하거나 업그레이드할 때마다 자동으로 해당 Vm에 OMS 에이전트를 설치 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="fba6b-132">이 기능을 사용 하도록 설정 하면 OMS 에이전트가 클라우드 커넥터 자동 업데이트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="fba6b-133">OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="fba6b-134">**OMS 에이전트를 기존 클라우드 커넥터 기기에 설치 하는 경우**다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="fba6b-135">CloudConnector.ini 파일 [일반] 섹션에서 OMSEnabled = true로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="fba6b-136">가져오기-CcConfiguration을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="fba6b-137">CcOMSAgent를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="fba6b-138">OMSWorkspace 자격 증명을 설정 하지 않은 경우에는 CcOMSAgent를 실행할 때 자격 증명을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="fba6b-139">**OMS 에이전트를 이미 설치한 클라우드 커넥터 기기에서 OMS 작업 영역 ID 또는 키를 업데이트 하려면 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fba6b-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="fba6b-140">OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="fba6b-141">업데이트를 적용 하려면 CcOMSAgent를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="fba6b-142">**모든 시나리오에 대해 에이전트가 다음과 같이 연결 되는지 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fba6b-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="fba6b-143">OMS 포털에서 설정- \> 연결 된 원본- \> Windows 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="fba6b-144">연결 된 컴퓨터 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="fba6b-145">OMS 구성</span><span class="sxs-lookup"><span data-stu-id="fba6b-145">Configure OMS</span></span>

<span data-ttu-id="fba6b-146">다음으로, OMS 포털을 사용 하 여 OMS 구성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="fba6b-147">특히 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="fba6b-148">이벤트 로그 및 성능 카운터에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="fba6b-149">알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="fba6b-150">이벤트 로그 및 성능 카운터에 대 한 정보 지정</span><span class="sxs-lookup"><span data-stu-id="fba6b-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="fba6b-151">OMS 포털에서 다음과 같이 이벤트 로그 및 성능 카운터에 대 한 정보를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="fba6b-152">설정- \> 데이터- \> Windows 이벤트 로그로 이동 하 고 다음에 대 한 이벤트 로그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="fba6b-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="fba6b-153">Lync Server</span></span>

   - <span data-ttu-id="fba6b-154">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fba6b-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="fba6b-155">텍스트 상자에 Lync Server를 수동으로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="fba6b-156">드롭다운 목록에 옵션으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="fba6b-157">자세한 내용은 [Log Analytics의 Windows 이벤트 로그 데이터 원본](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fba6b-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="fba6b-158">설정- \> 데이터- \> Windows 성능 카운터로 이동 하 고 다음에 대 한 성능 카운터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="fba6b-159">**OS 수준 카운터**입니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-159">**OS level counters**.</span></span> <span data-ttu-id="fba6b-160">프로세서 사용량, 메모리 사용량, 네트워크 사용 등의 OS 수준 카운터를 추가 하거나, 카운터를 명시적으로 추가 하지 않고 용량 및 성능, 네트워크 성능 모니터와 같은 기존 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="fba6b-161">모니터링을 결정 하는 방법에 관계 없이 이러한 OS 카운터를 모니터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="fba6b-162">**비즈니스용 Skype 카운터**입니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-162">**Skype for Business counters**.</span></span> <span data-ttu-id="fba6b-163">비즈니스용 Skype에서 제공 하는 다양 한 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="fba6b-164">이 카운터는 중재 서버에 로그온 하 고 성능 모니터를 여는 방법으로 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="fba6b-165">이러한 카운터는 "LS:"로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-165">These counters start with "LS:".</span></span> <span data-ttu-id="fba6b-166">최소한 다음 용량 카운터를 사용 하 여 작업을 시작 하 고 관심 있는 다른 항목을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="fba6b-167">총 활성 통화:</span><span class="sxs-lookup"><span data-stu-id="fba6b-167">Total active calls:</span></span>

       - <span data-ttu-id="fba6b-168">LS: MediationServer-Inbound Calls (_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="fba6b-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="fba6b-169">LS: MediationServer-아웃 바운드 호출 (_Total) \- 현재</span><span class="sxs-lookup"><span data-stu-id="fba6b-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="fba6b-170">총 활성 미디어 바이패스 통화:</span><span class="sxs-lookup"><span data-stu-id="fba6b-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="fba6b-171">LS: MediationServer-인바운드 호출 (_Total) \- 활성 미디어 바이패스 통화</span><span class="sxs-lookup"><span data-stu-id="fba6b-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="fba6b-172">LS: MediationServer-아웃 바운드 호출 (_Total) \- 액티브 미디어 바이패스 통화</span><span class="sxs-lookup"><span data-stu-id="fba6b-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="fba6b-173">텍스트 상자에 성능 카운터를 수동으로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="fba6b-174">드롭다운 목록에 옵션으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="fba6b-175">자세한 내용은 [Log Analytics에서 Windows 및 Linux 성능 데이터 원본](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) 참조</span><span class="sxs-lookup"><span data-stu-id="fba6b-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="fba6b-176">알림 만들기</span><span class="sxs-lookup"><span data-stu-id="fba6b-176">Create alerts</span></span>

<span data-ttu-id="fba6b-177">OMS에는 결과 경고의 수와 메트릭 측정 경고의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="fba6b-178">경고를 만드는 방법에 대 한 자세한 내용은 [Log Analytics에서 경고 규칙 작업](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fba6b-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="fba6b-179">알림을 만들 때는 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="fba6b-180">이 경고가 기본 선택 인 결과 수 경고 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="fba6b-181">데모 쿼리를 수행 하려면 "결과 개수"가 "0 보다 큼"으로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="fba6b-182">시간대와 알림 빈도를 모두 5 분으로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="fba6b-183">데모 경고에 대해서는 "경고 표시 안 함"을 사용 하도록 설정 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="fba6b-184">일반적인 경고 시나리오의 경우에는 하나의 오류 경고 및 하나의 리셋 알림과 같은 알림 쌍을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="fba6b-185">오류 경고에 대해 심각도 수준 중요를 선택 합니다. 재설정 알림에 대해 심각도 수준 정보를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="fba6b-186">다음 섹션에서는 예제 알림을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="fba6b-187">**"RTCMEDSRV이 중재 서버에서 실행 되 고 있지 않습니다." 및 "RTCMEDSRV은 중재 서버에서 실행 중입니다." 라는 경고 쌍을 만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="fba6b-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="fba6b-188">이 경고 쌍을 만들려면</span><span class="sxs-lookup"><span data-stu-id="fba6b-188">To create this alert pair:</span></span>

- <span data-ttu-id="fba6b-189">오류 경고에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="fba6b-190">이 쿼리는  *컴퓨터에 "MediationServer"가 포함*  된 컴퓨터 필터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="fba6b-191">필터는 이름에 문자열 "MediationServer"가 포함 된 컴퓨터만 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="fba6b-192">필터를 자체 컴퓨터 필터로 바꾸거나 제거 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="fba6b-193">정규식을 사용 하지 않고 복잡 한 문자열 필터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="fba6b-194">자세한 내용은 [문자열 연산자](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fba6b-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="fba6b-195">정규식을 사용 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="fba6b-196">또한 검색 쿼리를 저장 하 고 해당 그룹을 컴퓨터 필터로 사용 하 여 알림 쿼리의 컴퓨터 그룹을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="fba6b-197">자세한 내용은 [Log Analytics 로그 검색의 컴퓨터 그룹](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fba6b-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="fba6b-198">각 컴퓨터에 대해 오류 쿼리는 RTCMEDSRV 서비스 시작 및 서비스 중지 둘 다에 대 한 마지막 이벤트 로그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="fba6b-199">마지막 이벤트가 서비스 중지 이벤트 인 경우 로그를 하나씩 반환 합니다. 마지막 이벤트가 서비스 시작 이벤트 인 경우 아무 것도 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="fba6b-200">간단히 말해서 쿼리는 RTCMEDSRV가 시간 기간에 중지 된 서버 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="fba6b-201">재설정 경고에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="fba6b-202">다시 설정 쿼리는 오류 쿼리를 정확히 반대 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="fba6b-203">마지막 이벤트가 서비스 시작 이벤트 인 경우 각 컴퓨터에 대해 1을 반환 합니다. 마지막 이벤트가 서비스 중지 이벤트 인 경우 아무 것도 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="fba6b-204">**경고 쌍 만들기: "중재 서버에 너무 많은 동시 호출이 있습니다." 및 "동시 통화를 일반 로드로 대체"**</span><span class="sxs-lookup"><span data-stu-id="fba6b-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="fba6b-205">이 경고를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-205">To create this alert:</span></span>

- <span data-ttu-id="fba6b-206">오류 경고에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="fba6b-207">각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃 바운드 호출에 대 한 마지막 카운터를 가져오고 해당 두 값의 합계를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="fba6b-208">Sum 값이 500을 초과 하는 경우 로그 1 개를 반환 합니다. 그렇지 않으면 아무 것도 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="fba6b-209">간단히 말해서 쿼리는 시간 시간대에 동시 통화가 너무 많은 서버 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="fba6b-210">재설정 경고에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="fba6b-211">다시 설정 쿼리는 오류 쿼리를 정확히 반대 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="fba6b-212">각 컴퓨터에 대해 쿼리는 인바운드 통화 및 아웃 바운드 호출에 대 한 마지막 카운터를 가져오고 해당 두 값의 합계를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="fba6b-213">Sum 값이 500 보다 작으면 로그가 1 개를 반환 하 고, 그렇지 않으면 그렇지 않으면 아무 것도 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="fba6b-214">**경고 만들기: "CPU 사용 \> 90 또는 RTCMEDIARELAY이 (가) 서버에서 중지 되었습니다." 알림**</span><span class="sxs-lookup"><span data-stu-id="fba6b-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="fba6b-215">이 경고를 만들려면 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="fba6b-216">이 쿼리는 모든 컴퓨터에서 모든 프로세서 사용 카운터와 서비스 중지 이벤트를 가져오고, 프로세서 사용량이 90%를 초과 하거나 서비스가 중지 된 경우에는 로그를 하나씩 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="fba6b-217">로그 분석 리포지토리에서 경고 분석</span><span class="sxs-lookup"><span data-stu-id="fba6b-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="fba6b-218">리포지토리에서 알림을 분석 하려면 경고 관리 솔루션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="fba6b-219">자세한 내용은 [OMS (Operations Management Suite)에서 Alert Management solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fba6b-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="fba6b-220">권장 되는 최소 모니터링 설정</span><span class="sxs-lookup"><span data-stu-id="fba6b-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="fba6b-221">이벤트 로그 및 성능 카운터의 문제를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="fba6b-222">**이벤트 로그**</span><span class="sxs-lookup"><span data-stu-id="fba6b-222">**Event logs.**</span></span> <span data-ttu-id="fba6b-223">어떤 문제를 해결 하려면 이벤트 쌍이 있는데, 이러한 이벤트 집합은 잘못 된 것으로 표시 되 고 다른 하나는 모든 것이 정상 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="fba6b-224">지정 된 기간 동안에는 마지막 이벤트가 기록 되어 해당 기간에 대 한 어떤 항목이 amiss 인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="fba6b-225">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="fba6b-225">**Performance Counters.**</span></span> <span data-ttu-id="fba6b-226">모니터링 되는 카운터에 대 한 임계값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="fba6b-227">다음 표에는 stop 및 start 이벤트 Id를 나열 하 여 Microsoft에서 모니터링을 권장 하는 서비스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="fba6b-228">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="fba6b-228">Service Name</span></span>  <br/> |<span data-ttu-id="fba6b-229">대상 서버 역할</span><span class="sxs-lookup"><span data-stu-id="fba6b-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="fba6b-230">Stop 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="fba6b-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="fba6b-231">시작 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="fba6b-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fba6b-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="fba6b-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="fba6b-233">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fba6b-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="fba6b-234">25003</span><span class="sxs-lookup"><span data-stu-id="fba6b-234">25003</span></span>  <br/> |<span data-ttu-id="fba6b-235">25002</span><span class="sxs-lookup"><span data-stu-id="fba6b-235">25002</span></span>  <br/> |
|<span data-ttu-id="fba6b-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="fba6b-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="fba6b-237">에지 서버</span><span class="sxs-lookup"><span data-stu-id="fba6b-237">Edge Server</span></span>  <br/> |<span data-ttu-id="fba6b-238">12289</span><span class="sxs-lookup"><span data-stu-id="fba6b-238">12289</span></span>  <br/> |<span data-ttu-id="fba6b-239">12288</span><span class="sxs-lookup"><span data-stu-id="fba6b-239">12288</span></span>  <br/> |
|<span data-ttu-id="fba6b-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="fba6b-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="fba6b-241">에지 서버</span><span class="sxs-lookup"><span data-stu-id="fba6b-241">Edge Server</span></span>  <br/> |<span data-ttu-id="fba6b-242">19003</span><span class="sxs-lookup"><span data-stu-id="fba6b-242">19003</span></span>  <br/> |<span data-ttu-id="fba6b-243">19002</span><span class="sxs-lookup"><span data-stu-id="fba6b-243">19002</span></span>  <br/> |
|<span data-ttu-id="fba6b-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="fba6b-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="fba6b-245">에지 서버</span><span class="sxs-lookup"><span data-stu-id="fba6b-245">Edge Server</span></span>  <br/> |<span data-ttu-id="fba6b-246">22003</span><span class="sxs-lookup"><span data-stu-id="fba6b-246">22003</span></span>  <br/> |<span data-ttu-id="fba6b-247">22002</span><span class="sxs-lookup"><span data-stu-id="fba6b-247">22002</span></span>  <br/> |

<span data-ttu-id="fba6b-248">다음 표에는 Microsoft에서 모니터링에 권장 되는 네트워크 문제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="fba6b-249">모니터 이름</span><span class="sxs-lookup"><span data-stu-id="fba6b-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="fba6b-250">대상 서버 역할</span><span class="sxs-lookup"><span data-stu-id="fba6b-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="fba6b-251">성공 이벤트 ID 식</span><span class="sxs-lookup"><span data-stu-id="fba6b-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="fba6b-252">오류 이벤트 ID 식</span><span class="sxs-lookup"><span data-stu-id="fba6b-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="fba6b-253">오류 예</span><span class="sxs-lookup"><span data-stu-id="fba6b-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="fba6b-254">중재 서버에서 게이트웨이 연결에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="fba6b-255">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fba6b-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="fba6b-256">25062</span><span class="sxs-lookup"><span data-stu-id="fba6b-256">25062</span></span>                              |                                  | <span data-ttu-id="fba6b-257">25002</span><span class="sxs-lookup"><span data-stu-id="fba6b-257">25002</span></span>  <br/>           |
| <span data-ttu-id="fba6b-258">중재 서버에서 게이트웨이 호출을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="fba6b-259">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fba6b-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="fba6b-260">25064</span><span class="sxs-lookup"><span data-stu-id="fba6b-260">25064</span></span>                              |                                  | <span data-ttu-id="fba6b-261">25002</span><span class="sxs-lookup"><span data-stu-id="fba6b-261">25002</span></span>  <br/>           |
| <span data-ttu-id="fba6b-262">중요 네트워크 문제</span><span class="sxs-lookup"><span data-stu-id="fba6b-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="fba6b-263">에지 서버</span><span class="sxs-lookup"><span data-stu-id="fba6b-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="fba6b-264">14353</span><span class="sxs-lookup"><span data-stu-id="fba6b-264">14353</span></span>                              |                                  | <span data-ttu-id="fba6b-265">12288</span><span class="sxs-lookup"><span data-stu-id="fba6b-265">12288</span></span>  <br/>           |

<span data-ttu-id="fba6b-266">다음 목록에는 모니터링 해야 하는 통화 용량 카운터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="fba6b-267">이 수치는 클라우드 커넥터 standard edition에 500 보다 작아야 합니다. 클라우드 커넥터 최소 버전의 경우 50 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="fba6b-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="fba6b-268">LS: MediationServer-Inbound Calls (_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="fba6b-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="fba6b-269">LS: MediationServer-아웃 바운드 호출 (_Total) \- 현재</span><span class="sxs-lookup"><span data-stu-id="fba6b-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="fba6b-270">LS: MediationServer-인바운드 호출 (_Total) \- 활성 미디어 바이패스 통화</span><span class="sxs-lookup"><span data-stu-id="fba6b-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="fba6b-271">LS: MediationServer-아웃 바운드 호출 (_Total) \- 액티브 미디어 바이패스 통화</span><span class="sxs-lookup"><span data-stu-id="fba6b-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="fba6b-272">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fba6b-272">See also</span></span>

<span data-ttu-id="fba6b-273">OMS 사용에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fba6b-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="fba6b-274">로그 분석에서 로그 검색을 사용 하 여 데이터 찾기</span><span class="sxs-lookup"><span data-stu-id="fba6b-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="fba6b-275">Azure Log Analytics 언어 참조</span><span class="sxs-lookup"><span data-stu-id="fba6b-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="fba6b-276">로그 분석의 경고 이해</span><span class="sxs-lookup"><span data-stu-id="fba6b-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="fba6b-277">Azure의 Log Analytics service에 Windows 컴퓨터 연결</span><span class="sxs-lookup"><span data-stu-id="fba6b-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


