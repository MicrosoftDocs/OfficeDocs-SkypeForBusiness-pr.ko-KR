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
description: 이 항목에서는 Microsoft OMS (Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 및 이후 배포를 모니터링 하는 방법을 알아봅니다.
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888637"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="05a90-103">운영 관리 제품군(OMS)을 사용하여 클라우드 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="05a90-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="05a90-104">이 항목에서는 Microsoft OMS (Operations Management Suite)를 사용 하 여 클라우드 커넥터 버전 2.1 및 이후 배포를 모니터링 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="05a90-105">이제 OMS (Operations Management Suite), Microsoft 클라우드 IT 관리 솔루션을 사용 하 여 클라우드 커넥터 버전 2.1 및 이후 배포를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="05a90-106">OMS 로그 분석 기능을 사용 하면 실제 및 가상 컴퓨터를 비롯 한 리소스의 가용성과 성능을 모니터링 하 고 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="05a90-107">OMS 및 로그 분석에 대 한 자세한 내용은 [Operations Management Suite (OMS) 란?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="05a90-108">이 항목에서는 다음 섹션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="05a90-109">필요 조건</span><span class="sxs-lookup"><span data-stu-id="05a90-109">Prerequisites</span></span>

- <span data-ttu-id="05a90-110">OMS를 사용 하도록 클라우드 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="05a90-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="05a90-111">OMS 구성</span><span class="sxs-lookup"><span data-stu-id="05a90-111">Configure OMS</span></span>

- <span data-ttu-id="05a90-112">로그 분석 리포지토리에서 알림 분석</span><span class="sxs-lookup"><span data-stu-id="05a90-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="05a90-113">권장 되는 모니터링 설정</span><span class="sxs-lookup"><span data-stu-id="05a90-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05a90-114">필요 조건</span><span class="sxs-lookup"><span data-stu-id="05a90-114">Prerequisites</span></span>

<span data-ttu-id="05a90-115">OMS를 사용 하 여 클라우드 커넥터 배포를 모니터링할 수 있으려면 먼저 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="05a90-116">**Azure 계정 및 OMS 작업 영역**</span><span class="sxs-lookup"><span data-stu-id="05a90-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="05a90-117">Azure 계정이 없는 경우에는 OMS 로그 분석을 사용 하는 계정 중 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="05a90-118">Azure 계정을 만들고 OMS 작업 영역을 설정 하는 방법에 대 한 자세한 내용은 [로그 분석 작업 영역 시작](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="05a90-119">**클라우드 커넥터 버전 2.1 이상**</span><span class="sxs-lookup"><span data-stu-id="05a90-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="05a90-120">클라우드 커넥터 모니터링을 위해서는 **로그 분석에서 새 로그 검색이** 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="05a90-121">자세한 내용은 [Azure Log Analytics 작업 영역을 새 로그 검색으로 업그레이드를](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="05a90-122">OMS를 사용 하도록 클라우드 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="05a90-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="05a90-123">OMS를 사용 하려면 클라우드 커넥터 온-프레미스 환경을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="05a90-124">이렇게 하려면 oms 포털을 사용 하 여 찾을 수 있는 OMS 작업 영역 ID 및 키가 필요 합니다. 설정--\>연결 된 원본--\> Windows server:</span><span class="sxs-lookup"><span data-stu-id="05a90-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![클라우드 커넥터 OMS에 대 한 스크린샷](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="05a90-126">OMS를 사용 하도록 클라우드 커넥터를 구성 하는 방법은 시나리오에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="05a90-127">**새 클라우드 커넥터 기기를 설치 하거나 기기를 다시 배포 하려는 경우**설치-ccappliance를 실행 하기 전에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="05a90-128">CloudConnector .ini 파일 [일반] 구역에서 OMSEnabled 매개 변수를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="05a90-129">클라우드 커넥터를 배포 하거나 업그레이드할 때마다 자동으로 Vm에 OMS 에이전트를 설치 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="05a90-130">이 기능을 사용 하도록 설정 하면 OMS 에이전트가 클라우드 커넥터 자동 업데이트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="05a90-131">OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="05a90-132">**OMS 에이전트를 기존 클라우드 커넥터 기기에 설치 하는 경우**다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="05a90-133">CloudConnector .ini 파일 [일반] 구역에서 OMSEnabled = true로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="05a90-134">가져오기-CcConfiguration을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-134">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="05a90-135">설치-CcOMSAgent를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-135">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="05a90-136">OMSWorkspace 자격 증명을 설정 하지 않은 경우 CcOMSAgent를 실행할 때 자격 증명을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="05a90-137">**OMS 에이전트를 이미 설치한 클라우드 커넥터 기기에서 OMS 작업 영역 ID 또는 키를 업데이트 하려면 다음을 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05a90-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="05a90-138">OMS ID 및 키를 구성 하려면 Set-CcCredential-AccountType OMSWorkspace를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="05a90-139">업데이트를 적용 하려면 설치-CcOMSAgent를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="05a90-140">**모든 시나리오의 경우 다음과 같이 에이전트가 연결 되어 있는지 확인 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05a90-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="05a90-141">OMS 포털에서 설정-\> 연결 된 원본-\> Windows 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="05a90-142">연결 된 컴퓨터 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="05a90-143">OMS 구성</span><span class="sxs-lookup"><span data-stu-id="05a90-143">Configure OMS</span></span>

<span data-ttu-id="05a90-144">다음에는 OMS 포털을 사용 하 여 OMS 구성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="05a90-145">구체적으로 다음과 같은 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="05a90-146">이벤트 로그 및 성능 카운터에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="05a90-147">알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="05a90-148">이벤트 로그 및 성능 카운터에 대 한 정보 지정</span><span class="sxs-lookup"><span data-stu-id="05a90-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="05a90-149">OMS 포털에서 다음과 같이 이벤트 로그 및 성능 카운터에 대 한 정보를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="05a90-150">설정-\>데이터-\>Windows 이벤트 로그로 이동 하 여 다음에 대 한 이벤트 로그 추가:</span><span class="sxs-lookup"><span data-stu-id="05a90-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="05a90-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="05a90-151">Lync Server</span></span>

   - <span data-ttu-id="05a90-152">응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="05a90-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="05a90-153">텍스트 상자에 Lync Server를 수동으로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="05a90-154">드롭다운 목록에 옵션으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="05a90-155">자세한 내용은 [로그 분석에서 Windows 이벤트 로그 데이터 원본](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="05a90-156">설정-\>데이터-\> Windows 성능 카운터로 이동 하 여 다음에 대 한 성능 카운터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="05a90-157">**OS 수준 카운터**입니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-157">**OS level counters**.</span></span> <span data-ttu-id="05a90-158">프로세서 사용량, 메모리 사용량, 네트워크 사용량 등 OS 수준 카운터를 추가 하거나 카운터를 명시적으로 추가 하지 않고 용량 및 성능, 네트워크 성능 모니터 등의 기존 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="05a90-159">모니터링 하기로 결정 한 방법에 관계 없이 이러한 OS 카운터를 모니터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="05a90-160">**비즈니스용 Skype 카운터**.</span><span class="sxs-lookup"><span data-stu-id="05a90-160">**Skype for Business counters**.</span></span> <span data-ttu-id="05a90-161">비즈니스용 Skype에서 제공 하는 여러 가지 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="05a90-162">중재 서버에 로그온 하 고 성능 모니터를 열면 이러한 카운터를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="05a90-163">이러한 카운터는 "LS:"로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-163">These counters start with "LS:".</span></span> <span data-ttu-id="05a90-164">최소한 다음 용량 카운터를 사용 하 여 작업을 시작 하 고 관심 있는 나머지를 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="05a90-165">총 활성 통화:</span><span class="sxs-lookup"><span data-stu-id="05a90-165">Total active calls:</span></span>

       - <span data-ttu-id="05a90-166">LS: MediationServer-인바운드 통화 (_Total)\- 현재</span><span class="sxs-lookup"><span data-stu-id="05a90-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="05a90-167">LS: MediationServer-아웃 바운드 통화 (_Total\- ) 현재</span><span class="sxs-lookup"><span data-stu-id="05a90-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="05a90-168">총 활성 미디어 바이패스 통화:</span><span class="sxs-lookup"><span data-stu-id="05a90-168">Total active media bypass calls:</span></span>

       - <span data-ttu-id="05a90-169">LS: MediationServer-인바운드 통화 (_Total)\- 액티브 미디어에서 통화 무시</span><span class="sxs-lookup"><span data-stu-id="05a90-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="05a90-170">LS: MediationServer-아웃 바운드 통화 (_Total\- ) 액티브 미디어 건너뛰기 통화</span><span class="sxs-lookup"><span data-stu-id="05a90-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="05a90-171">텍스트 상자에 성능 카운터를 수동으로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="05a90-172">드롭다운 목록에 옵션으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="05a90-173">자세한 내용은 [로그 분석에서 Windows 및 Linux 성능 데이터 원본을](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="05a90-174">알림 만들기</span><span class="sxs-lookup"><span data-stu-id="05a90-174">Create alerts</span></span>

<span data-ttu-id="05a90-175">OMS에는 여러 가지 유형의 경고가 표시 됩니다 (결과 경고 수 및 미터법 단위 알림).</span><span class="sxs-lookup"><span data-stu-id="05a90-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="05a90-176">알림을 만드는 방법에 대 한 자세한 내용은 [로그 분석에서 알림 규칙 작업](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="05a90-177">알림을 만들 때 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="05a90-178">알림이 기본 선택 인 결과를 숫자로 표시 하는 알림 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="05a90-179">데모 쿼리에는 "결과 개수"가 "0 보다 큼"으로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="05a90-180">시간 창과 알림 빈도를 5 분으로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="05a90-181">데모 알림에서 "경고 표시 안 함"을 사용 하도록 설정 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="05a90-182">일반적인 알림 시나리오의 경우 하나의 오류 알림 및 한 번의 재설정 알림을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="05a90-183">오류 경고의 경우 심각도 (위험 수준)를 선택 합니다. 다시 설정 알림에 대해 심각도 수준 정보를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="05a90-184">다음 섹션에서는 예제 알림을 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="05a90-185">**"RTCMEDSRV는 중재 서버에서 실행 되 고 있지 않음" 및 "RTCMEDSRV는 중재 서버에서 실행 되 고 있습니다." 라는 경고 쌍을 만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="05a90-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="05a90-186">이 알림 쌍을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-186">To create this alert pair:</span></span>

- <span data-ttu-id="05a90-187">오류 경고에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-187">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="05a90-188">이 쿼리는 *컴퓨터에 "MediationServer"가 포함* 된 컴퓨터 필터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="05a90-189">필터는 이름에 문자열 "MediationServer"가 포함 되어 있는 컴퓨터만 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="05a90-190">필터를 자신의 컴퓨터 필터로 바꾸거나 제거 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="05a90-191">정규식 없이 복잡 한 문자열 필터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="05a90-192">자세한 내용은 [문자열 연산자](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="05a90-193">정규식을 사용 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="05a90-194">또한 검색 쿼리를 저장 하 고 해당 그룹을 컴퓨터 필터로 사용 하 여 컴퓨터 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="05a90-195">자세한 내용은 [로그 분석 로그 검색의 컴퓨터 그룹](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="05a90-196">각 컴퓨터에 대해 오류 쿼리는 RTCMEDSRV 서비스 시작 및 서비스 중지 모두에 대 한 마지막 이벤트 로그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="05a90-197">마지막 이벤트가 서비스 중지 이벤트 이면 하나의 로그를 반환 합니다. 마지막 이벤트가 서비스 시작 이벤트 인 경우 nothing이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="05a90-198">즉, 쿼리는 시간 창에서 RTCMEDSRV가 중지 된 서버 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="05a90-199">다시 설정 알림에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-199">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="05a90-200">다시 설정 쿼리는 오류 쿼리의 반대 항목을 정확히 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="05a90-201">마지막 이벤트가 서비스 시작 이벤트 이면 각 컴퓨터에 대해 1이 반환 됩니다. 마지막 이벤트가 서비스 중지 이벤트 일 경우 nothing이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="05a90-202">**"중재 서버에 너무 많은 동시 통화" 및 "동시 통화 정상 로드로 전환" 경고 쌍을 만듭니다.**</span><span class="sxs-lookup"><span data-stu-id="05a90-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="05a90-203">알림을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-203">To create this alert:</span></span>

- <span data-ttu-id="05a90-204">오류 경고에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-204">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="05a90-205">각 컴퓨터에 대해 쿼리는 인바운드 통화 및 발신 호출에 대 한 마지막 카운터를 가져오고 이러한 두 값의 합계를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="05a90-206">Sum 값이 500를 초과 하는 경우 1 개의 로그가 반환 됩니다. 그렇지 않으면 아무 것도 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="05a90-207">즉, 쿼리는 시간 창에 동시 호출이 너무 많은 서버 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="05a90-208">다시 설정 알림에 대 한 쿼리는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-208">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="05a90-209">다시 설정 쿼리는 오류 쿼리의 반대 항목을 정확히 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="05a90-210">각 컴퓨터에 대해 쿼리는 인바운드 통화 및 발신 호출에 대 한 마지막 카운터를 가져오고 이러한 두 값의 합계를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="05a90-211">Sum 값이 500 보다 작으면 로그가 1 개 반환 되 고, 그렇지 않으면 아무 작업도 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="05a90-212">**경고 만들기: "CPU 사용 \> 90 또는 RTCMEDIARELAY 중지 됨" 알림**</span><span class="sxs-lookup"><span data-stu-id="05a90-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="05a90-213">이 알림을 만들려면 쿼리는 다음과 같이 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-213">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="05a90-214">쿼리는 모든 컴퓨터에서 모든 프로세서 사용 카운터 및 서비스 중지 이벤트를 받고, 프로세서 사용량이 90%를 초과 하거나 서비스가 중지 된 경우 하나의 로그를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="05a90-215">로그 분석 리포지토리에서 알림 분석</span><span class="sxs-lookup"><span data-stu-id="05a90-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="05a90-216">리포지토리에서 알림을 분석 하려면 알림 관리 솔루션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="05a90-217">자세한 내용은 [OMS (Operations Management Suite)의 Alert Management solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="05a90-218">권장 되는 최소 모니터링 집합</span><span class="sxs-lookup"><span data-stu-id="05a90-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="05a90-219">이벤트 로그 및 성능 카운터의 문제를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="05a90-220">**이벤트 로그.**</span><span class="sxs-lookup"><span data-stu-id="05a90-220">**Event logs.**</span></span> <span data-ttu-id="05a90-221">문제가 발생 하는 경우 어떤 이벤트 집합을 사용 하는 이벤트 쌍이 문제가 되는 반면 나머지는 모든 것이 잘 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="05a90-222">지정 된 기간 동안에는 해당 기간에 대 한 amiss가 표시 될 때까지 마지막으로 기록 된 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="05a90-223">**성능 카운터**</span><span class="sxs-lookup"><span data-stu-id="05a90-223">**Performance Counters.**</span></span> <span data-ttu-id="05a90-224">모니터링 되는 카운터에 대 한 임계값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="05a90-225">다음 표에는 중지 및 시작 이벤트 Id를 나열 하 여 Microsoft에서 모니터링을 권장 하는 서비스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="05a90-226">서비스 이름</span><span class="sxs-lookup"><span data-stu-id="05a90-226">Service Name</span></span>  <br/> |<span data-ttu-id="05a90-227">대상 서버 역할</span><span class="sxs-lookup"><span data-stu-id="05a90-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="05a90-228">중지 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="05a90-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="05a90-229">시작 이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="05a90-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05a90-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="05a90-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="05a90-231">중재 서버</span><span class="sxs-lookup"><span data-stu-id="05a90-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="05a90-232">25003</span><span class="sxs-lookup"><span data-stu-id="05a90-232">25003</span></span>  <br/> |<span data-ttu-id="05a90-233">25002</span><span class="sxs-lookup"><span data-stu-id="05a90-233">25002</span></span>  <br/> |
|<span data-ttu-id="05a90-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="05a90-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="05a90-235">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="05a90-235">Edge Server</span></span>  <br/> |<span data-ttu-id="05a90-236">12289</span><span class="sxs-lookup"><span data-stu-id="05a90-236">12289</span></span>  <br/> |<span data-ttu-id="05a90-237">12288</span><span class="sxs-lookup"><span data-stu-id="05a90-237">12288</span></span>  <br/> |
|<span data-ttu-id="05a90-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="05a90-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="05a90-239">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="05a90-239">Edge Server</span></span>  <br/> |<span data-ttu-id="05a90-240">19003</span><span class="sxs-lookup"><span data-stu-id="05a90-240">19003</span></span>  <br/> |<span data-ttu-id="05a90-241">19002</span><span class="sxs-lookup"><span data-stu-id="05a90-241">19002</span></span>  <br/> |
|<span data-ttu-id="05a90-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="05a90-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="05a90-243">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="05a90-243">Edge Server</span></span>  <br/> |<span data-ttu-id="05a90-244">22003</span><span class="sxs-lookup"><span data-stu-id="05a90-244">22003</span></span>  <br/> |<span data-ttu-id="05a90-245">22002</span><span class="sxs-lookup"><span data-stu-id="05a90-245">22002</span></span>  <br/> |

<span data-ttu-id="05a90-246">다음 표에는 Microsoft에서 모니터링할 때 권장 하는 네트워크 문제가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="05a90-247">모니터 이름</span><span class="sxs-lookup"><span data-stu-id="05a90-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="05a90-248">대상 서버 역할</span><span class="sxs-lookup"><span data-stu-id="05a90-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="05a90-249">성공 이벤트 ID 식</span><span class="sxs-lookup"><span data-stu-id="05a90-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="05a90-250">오류 이벤트 ID 식</span><span class="sxs-lookup"><span data-stu-id="05a90-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="05a90-251">실패 예</span><span class="sxs-lookup"><span data-stu-id="05a90-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="05a90-252">중재 서버에서 게이트웨이 연결에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="05a90-253">중재 서버</span><span class="sxs-lookup"><span data-stu-id="05a90-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="05a90-254">25062</span><span class="sxs-lookup"><span data-stu-id="05a90-254">25062</span></span>                              |                                  | <span data-ttu-id="05a90-255">25002</span><span class="sxs-lookup"><span data-stu-id="05a90-255">25002</span></span>  <br/>           |
| <span data-ttu-id="05a90-256">중재 서버에서 게이트웨이 호출 완료 실패</span><span class="sxs-lookup"><span data-stu-id="05a90-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="05a90-257">중재 서버</span><span class="sxs-lookup"><span data-stu-id="05a90-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="05a90-258">25064</span><span class="sxs-lookup"><span data-stu-id="05a90-258">25064</span></span>                              |                                  | <span data-ttu-id="05a90-259">25002</span><span class="sxs-lookup"><span data-stu-id="05a90-259">25002</span></span>  <br/>           |
| <span data-ttu-id="05a90-260">심각한 네트워크 문제</span><span class="sxs-lookup"><span data-stu-id="05a90-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="05a90-261">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="05a90-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="05a90-262">14353</span><span class="sxs-lookup"><span data-stu-id="05a90-262">14353</span></span>                              |                                  | <span data-ttu-id="05a90-263">12288</span><span class="sxs-lookup"><span data-stu-id="05a90-263">12288</span></span>  <br/>           |

<span data-ttu-id="05a90-264">다음 목록에는 모니터링 해야 하는 통화 용량 카운터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05a90-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="05a90-265">이러한 번호는 클라우드 커넥터 standard edition의 500 미만 이어야 합니다. 클라우드 커넥터 최소 에디션의 50 미만</span><span class="sxs-lookup"><span data-stu-id="05a90-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="05a90-266">LS: MediationServer-인바운드 통화 (_Total)\- 현재</span><span class="sxs-lookup"><span data-stu-id="05a90-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="05a90-267">LS: MediationServer-아웃 바운드 통화 (_Total\- ) 현재</span><span class="sxs-lookup"><span data-stu-id="05a90-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="05a90-268">LS: MediationServer-인바운드 통화 (_Total)\- 액티브 미디어에서 통화 무시</span><span class="sxs-lookup"><span data-stu-id="05a90-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="05a90-269">LS: MediationServer-아웃 바운드 통화 (_Total\- ) 액티브 미디어 건너뛰기 통화</span><span class="sxs-lookup"><span data-stu-id="05a90-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="05a90-270">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05a90-270">See also</span></span>

<span data-ttu-id="05a90-271">OMS 작업에 대 한 자세한 내용은 다음을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="05a90-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="05a90-272">로그 분석에서 로그 검색을 사용 하 여 데이터 찾기</span><span class="sxs-lookup"><span data-stu-id="05a90-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="05a90-273">Azure 로그 분석 언어 참조</span><span class="sxs-lookup"><span data-stu-id="05a90-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="05a90-274">로그 분석의 경고 이해</span><span class="sxs-lookup"><span data-stu-id="05a90-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="05a90-275">Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결</span><span class="sxs-lookup"><span data-stu-id="05a90-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


