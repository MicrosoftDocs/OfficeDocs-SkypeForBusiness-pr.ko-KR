---
title: Azure Sentinel 및 Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: IT 관리자를 위한 Sentinel을 사용하여 Teams에서 발생할 수 있는 위협을 모니터링하고 헌팅하는 데 대한 보안 자문과 학습입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f13cdd1d62a31178f7aed922b3bc55b87cd59db
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701236"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="c1d2f-103">Azure Sentinel 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c1d2f-103">Azure Sentinel and Microsoft Teams</span></span>

<span data-ttu-id="c1d2f-104">Teams는 Microsoft 365 클라우드의 커뮤니케이션 및 데이터 공유 모두에서 중심 역할을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-104">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="c1d2f-105">Teams 서비스는 클라우드에서 많은 기반 기술을 사용하므로 *로그에서 헌팅* 을 하는 경우 외에 *모임의 실시간 모니터링* 에도 사용자와 자동화된 분석을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-105">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="c1d2f-106">Azure Sentinel은 관리자에게 이러한 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-106">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="c1d2f-107">Azure Sentinel에 대한 복습이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="c1d2f-107">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="c1d2f-108">[이 문서](https://docs.microsoft.com/azure/sentinel/overview)를 참고하시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-108">[This article](https://docs.microsoft.com/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="c1d2f-109">Azure Sentinel 및 Microsoft Teams 활동 로그</span><span class="sxs-lookup"><span data-stu-id="c1d2f-109">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="c1d2f-110">이 문서에서는 Azure Sentinel에서 Teams의 활동 로그 수집에 초점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-110">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="c1d2f-111">관리자가 보안 관리를 하나의 창에(모든 타사 장치, Microsoft Threat Protection 및 기타 Microsoft 365 워크로드) 두는 것 외에, 센티널 통합 문서와 runbook은 보안 모니터링을 체계적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-111">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="c1d2f-112">이 프로세스에서 바람직한 첫 번째 단계는 분석에 필요한 로그를 수집하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-112">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="c1d2f-113">두 개 이상의 Microsoft 365 구독이 동일한 Azure Sentinel 인스턴스에서 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-113">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="c1d2f-114">이는 기록 로그 파일 s에서 위협에 대한 [실시간 모니터링](https://docs.microsoft.com/azure/sentinel/livestream)과 헌팅을 할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-114">This will allow for [realtime monitoring](https://docs.microsoft.com/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="c1d2f-115">관리자는 단일 리소스 그룹 내에서, 여러 리소스 그룹에서 또는 다른 구독에서 [교차 리소스 쿼리](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query)를 사용하여 헌팅을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-115">Administrators will be able to hunt using [cross-resource queries](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="c1d2f-116">1단계: Teams 로그 수집</span><span class="sxs-lookup"><span data-stu-id="c1d2f-116">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="c1d2f-117">이 섹션에는 세 가지 부분이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-117">This section has three parts:</span></span>

1. <span data-ttu-id="c1d2f-118">**Microsoft 365**(M365)에서 감사 로그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-118">Enabling Audit Logs in **Microsoft 365** (M365).</span></span>
2. <span data-ttu-id="c1d2f-119">**Microsoft Azure** 에서 앱을 등록하여 로그 수집에 대한 인증 및 권한을 허용합니다. </span><span class="sxs-lookup"><span data-stu-id="c1d2f-119">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="c1d2f-120">**PowerShell** 을 통해 M365 API를 통해 로그 수집을 허용하는 API 구독을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-120">Registering the API subscription that will allow log collection via M365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-m365"></a><span data-ttu-id="c1d2f-121">M365에서 감사 로그 사용</span><span class="sxs-lookup"><span data-stu-id="c1d2f-121">Enable Audit logs in M365</span></span>

<span data-ttu-id="c1d2f-122">Teams가 M365를 통해 활동을 기록하기 때문에 감사 로그가 기본적으로 수집되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-122">Because Teams logs activity through M365, audit logs aren't collected by default.</span></span> <span data-ttu-id="c1d2f-123">[이러한 단계](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)를 통해 이 기능을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-123">Turn on this feature via [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span></span> <span data-ttu-id="c1d2f-124">Teams 데이터는 *Audit.General* 의 M365 감사에서 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-124">Teams data is collected in the M365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="c1d2f-125">M로그 수집을 위해 Microsoft Azure에서 앱 등록</span><span class="sxs-lookup"><span data-stu-id="c1d2f-125">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="c1d2f-126">시작하기 전에 **응용 프로그램 ID/클라이언트 ID** 와 **테넌트 ID** 를 나중에 사용할 수 있도록 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-126">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="c1d2f-127">아래에서 앱 등록 단계를 안내하는 단계를 수행하면서 이러한 정보를 반드시 캡처하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-127">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="c1d2f-128">두 ID가 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-128">You will see both IDs.</span></span>
>- <span data-ttu-id="c1d2f-129">앱을 만든 후 빠른 실행 사이드바에서 앱 등록 > 새 앱의 표시 이름 찾기 > 응용 프로그램(클라이언트) ID 복사를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-129">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="c1d2f-130">빠른 실행 사이드바에서 개요 > 디렉터리(테넌트) ID 복사를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-130">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="c1d2f-131">API에서 로그 데이터를 수집하기 위해 Azure AD(Active Directory) 앱을 인증하고 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-131">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="c1d2f-132">Azure Portal에서 *Azure AD* 블레이드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-132">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="c1d2f-133">빠른 실행 사이드바에서 *앱 등록* 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-133">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="c1d2f-134">*새 등록* 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-134">Select *New registration*.</span></span>
4. <span data-ttu-id="c1d2f-135">Teams 로그 수집 앱 이름을 지정하고 *등록* 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-135">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="c1d2f-136">다음 경로를 클릭합니다. *API 사용 권한* > *사용 권한 추가* > *Office 365 관리 API* > *응용 프로그램 사용 권한* 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-136">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="c1d2f-137">활동 피드를 확장하고 *ActivityFeed.Read* 를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-137">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="c1d2f-138">여기서 *그랜드 관리자 동의* 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-138">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="c1d2f-139">정말로 선택하기를 원하는지 묻는 메시지가 나타나면 예를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-139">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="c1d2f-140">사이드바에서 *인증서와 암호* > *새 클라이언트 암호* 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-140">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="c1d2f-141">새 클라이언트 암호 창에서 새 클라이언트 암호에 대한 설명을 입력하고, 만료는 '안 함'을 선택하고 *추가* 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-141">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1d2f-142">새 클라이언트 암호를 새로 만든 앱의 이름 아래에 있는 암호 관리자 항목에 복사하는 것은 매우 **중요** 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-142">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="c1d2f-143">Azure 블레이드를 닫은 후에는(*블레이드* 는 창에 대한 Azure 용어) 이 암호를 확인하러 돌아갈 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="c1d2f-143">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="c1d2f-144">Teams 로그 수집을 위해 PowerShell에 API 등록</span><span class="sxs-lookup"><span data-stu-id="c1d2f-144">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="c1d2f-145">설치의 마지막 단계는 로그 데이터를 수집할 수 있도록 API 구독을 수집하고 등록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-145">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="c1d2f-146">M365 관리 활동 API에 대한 PowerShell REST 호출을 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-146">This is done via PowerShell REST calls to the M365 Management Activity API.</span></span>

<span data-ttu-id="c1d2f-147">아래 PowerShell cmdlet에서 **응용 프로그램(클라이언트) ID**, 새 **클라이언트 암호**, **M365에 다한 URL 도메인**, 그리고 **디렉터리(테넌트) ID** 값을 제공할 준비를 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-147">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="c1d2f-148">2단계: Teams 로그를 수집하기 위해 Sentinel 플레이북 배포</span><span class="sxs-lookup"><span data-stu-id="c1d2f-148">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="c1d2f-149">Azure Sentinel 플레이북(논리 앱이라고도 함)은 Azure을 통해 수집한 Teams 데이터를 수집하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-149">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="c1d2f-150">논리 앱은 Office 365를 쿼리하여 Azure Sentinel 작업 영역에 쓰는 감사 데이터를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-150">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="c1d2f-151">[이](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM 템플릿을 이용하여 Sentinel 플레이북을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-151">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="c1d2f-152">주의 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-152">Things to remember:</span></span>

1. <span data-ttu-id="c1d2f-153">ARM 템플릿을 거쳐 특정 값을 사용자 고유의 환경에 맞는 값으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-153">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="c1d2f-154">Azure Sentinel에서 로그 수집 및 결과 확인 작업 사이에 시간을 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-154">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="c1d2f-155">지난 5분 내에 데이터가 없는 경우 오류 메시지가 표시됨을 알고 5~10분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-155">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="c1d2f-156">감사 로그를 확인하고 Teams 정보가 Teams 로그 보다 많은 정보를 수집하는 Audit.General 이벤트에 있기 때문에 사용 중인 시스템에서 5 ~ 10분 이내에 결과과 표시됨을 염두에 둡니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-156">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="c1d2f-157">텍스트 환경을 사용하는 경우에는 로깅을 생성하는 데 반드시 Teams를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-157">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![논리 앱 클래스를 보여주는 그래픽](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="c1d2f-159">그래픽의 작업에 대한 설명:</span><span class="sxs-lookup"><span data-stu-id="c1d2f-159">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="c1d2f-160">• 되풀이는 워크플로를 매시간 실행하도록 하는 논리 앱 트리거입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-160">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="c1d2f-161">• 현재 시간 작업은 매우 기본적인 항목으로 단지 현재 시간을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-161">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="c1d2f-162">• 변수 초기화는 NextPage라는 변수를 만들고 이를 1로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-162">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="c1d2f-163">이는 나중에 O365 API에서 페이지 매김을 처리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-163">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="c1d2f-164">• 변수 2 초기화는 시작 시간이라는 빈 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-164">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="c1d2f-165">• 쿼리 실행 및 결과 나열은 논리 앱에서 입력한 마지막 O365 로그에 대한 작업 영역을 쿼리하는 Azure Monitor 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-165">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="c1d2f-166">• 조건 4는 쿼리 실행 및 결과 나열 쿼리가 반환한 데이터가 있는지를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-166">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="c1d2f-167">이 작업은 논리 앱이 최초로 사용되는 경우인지 확인하기 위해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-167">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="c1d2f-168">데이터가 반환되지 않는 경우 StartTime 변수는 Now(24 시간)로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-168">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="c1d2f-169">데이터가 반환되면 StartTime이 마지막 레코드(TimeGenerated)로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-169">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="c1d2f-170">이는 쿼리가 O365 API를 대상으로 하는 폴링에서 마지막 항목에서 현재까지의 데이터를 가져올 수 있도록 하기 위해 수행됩니다(이번이 최초 실행인 경우 마지막 24시간 이내).</span><span class="sxs-lookup"><span data-stu-id="c1d2f-170">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="c1d2f-171">• 변수 3 초기화는 AvailableUri라는 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-171">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="c1d2f-172">시작 시간과 종료 시간으로 StartTime과 CurrentTime를 각각 사용하여 빌드한 URL이 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-172">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="c1d2f-173">• Until 조건은 논리 앱에서 계속해서 API를 폴링하여 데이터가 더 있는지 확인할 수 있는 루프입니다(페이지 매김).</span><span class="sxs-lookup"><span data-stu-id="c1d2f-173">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="c1d2f-174">NextPage 변수가 1인 한 루프가 계속 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-174">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="c1d2f-175">나중에 더 이상 검색할 페이지가 없으면 이 변수가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-175">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="c1d2f-176">• Until 루프 내에 첫 번째 HTTP 단계가 AvailableURI에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-176">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="c1d2f-177">이 URI는 사용 가능한 콘텐츠 목록과 각 콘텐츠 URI를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-177">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="c1d2f-178">이 URL에서 이 작업이 수행되는 방법에 대한 자세한 내용은 https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-178">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="c1d2f-179">• 다음으로 검사를 실행하여 데이터가 반환되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-179">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="c1d2f-180">이 조건은 본문의 길이가 0인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-180">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="c1d2f-181">0인 경우 로그 분석에 쓸 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-181">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="c1d2f-182">값이 0보다 크면 처리할 데이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-182">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="c1d2f-183">• 데이터가 검색되면 다음에 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-183">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="c1d2f-184">JSON 구문 분석은 반환된 데이터의 스키마를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-184">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="c1d2f-185">이는 이후의 단계에 논리 앱에서 구문 분석된 데이터를 동적 콘텐츠로 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-185">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="c1d2f-186">• 반환되는 사용 가능한 데이터 목록이 배열이므로 For Each 동작은 사용 가능한 콘텐츠 목록에서 루프를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-186">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="c1d2f-187">• 다음은 콘텐츠 가져오기입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-187">• Next is grabbing the content.</span></span>  <span data-ttu-id="c1d2f-188">검색할 데이터의 URL인 contentUri(구문 분석 JSON에서 만든 동적 속성)를 가져오는 데 HTTP가 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-188">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="c1d2f-189">• 구문 분석 JSON은 반환된 데이터를 구문 분석하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-189">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="c1d2f-190">다음 URL에서 일부 샘플 콘텐츠를 찾을 수 있습니다.https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content</span><span class="sxs-lookup"><span data-stu-id="c1d2f-190">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="c1d2f-191">• 반환되는 데이터 또한 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-191">• The data returned is also an array.</span></span> <span data-ttu-id="c1d2f-192">여기에서도 For Each 루프를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-192">A For Each loop can be used here as well.</span></span> <span data-ttu-id="c1d2f-193">이 루프에서는 워크플로가 현재 데이터 항목을 받고 데이터 보내기 동작을 사용하여 데이터를 Log Analytics에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-193">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="c1d2f-194">• 사용 가능한 콘텐츠 페이지가 여러 개 있을 수 있으므로 조건은 NextPageUri가 NULL이 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-194">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="c1d2f-195">NULL이거나 비어있는 경우 NextPage가 0으로 설정되면 Until 루프를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-195">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="c1d2f-196">URL이 포함되어 있는 경우 AvaibleUri 변수는 해당 URL로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-196">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="c1d2f-197">이러한 방식으로 다음에 Until 루프를 실행할 때 시작 URL이 아닌 다음 사용 가능한 URL이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-197">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="c1d2f-198">이러한 로그를 수집하기 위해 대신 *Azure 함수* 를 사용하도록 선택할 수 있고, 선택하는 경우의 배포 방법에 대한 정보는 기본 설정에 따라 [여기](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) 혹은 [여기](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-198">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="c1d2f-199">(사용자가 위에서 선택한 옵션에 상관없이) 커넥터를 실행하는 경우, Azure Sentinel 작업 영역에 O365API_CL이라는 사용자 지정 표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-199">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="c1d2f-200">여기에 Teams 로그가 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-200">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="c1d2f-201">3 단계: Sentinel을 사용하여 Microsoft Teams 모니터링</span><span class="sxs-lookup"><span data-stu-id="c1d2f-201">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="c1d2f-202">ID는 Microsoft Teams와 관련된 경우, 모니터링할 중요한 공격 벡터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-202">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="c1d2f-203">Azure AD(Active Directory)는 Teams를 포함하는 Microsoft 365의 디렉터리의 기반이기에, 인증과 관련된 Azure AD 로그에서 위협을 수집하고 헌팅함은 ID에 대한 의심이 가는 동작을 캡처하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-203">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="c1d2f-204">기본 제공 커넥터를 사용하여 Azure Sentinel로 Azure AD 데이터를 가져오고 이러한 [검색](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) 및 [헌팅](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) 쿼리를 사용하여 문제를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-204">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="c1d2f-205">Microsoft Teams와 관련된 공격, 데이터에 대한 위협과 관련하여, 예를 들어 Azure Sentinel 또한 그들을 모니터링하고 헌팅하는 수단이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-205">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="c1d2f-206">데이터에 대한 파서 만들기</span><span class="sxs-lookup"><span data-stu-id="c1d2f-206">Create a parser for your data</span></span>

<span data-ttu-id="c1d2f-207">수집된 대규모 데이터 집합이 제대로 작성되려면 먼저 수행해야 하는 작업은 구문 분석을 통해 의미를 부여하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-207">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="c1d2f-208">이 작업은 데이터를 더 쉽게 사용할 수 있도록 하는 KQL(Kusto 쿼리 언어) 함수를 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-208">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="c1d2f-209">KQL 함수는 '함수'라는 데이터 형식으로 저장된 KQL 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-209">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="c1d2f-210">KQL 함수는 Sentinel의 쿼리 상자에 입력하여 쿼리를 신속하게 다시 실행할 수 있는 별칭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-210">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="c1d2f-211">KQL 함수 및 파서 함수를 빌드하는 방법에 대한 자세한 내용은 [이 기술 커뮤니티 문서](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-211">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="c1d2f-212">아래 파서는 *Teams* 와 관련된 Office 365 관리 API 필드의 하위 집합을 선택할 목적의 사용자 지정이 가능한 예시입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-212">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="c1d2f-213">또한 제안된 파서 [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)가 있지만 아래의 파서는 다양 한 요구 사항 및 기본 설정에 맞게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-213">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="c1d2f-214">TeamsData의 별칭을 사용하여 이 파서를 KQL 함수로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-214">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="c1d2f-215">따를 쿼리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-215">It will be used for the queries to follow.</span></span> <span data-ttu-id="c1d2f-216">KQL 함수를 구문으로 구성하고 사용하는 방법에 대한 자세한 내용은 이 [기술 커뮤니티 문서](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-216">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="c1d2f-217">유용한 헌팅 KQL 쿼리</span><span class="sxs-lookup"><span data-stu-id="c1d2f-217">Helpful hunting KQL queries</span></span>

<span data-ttu-id="c1d2f-218">이 쿼리를 사용하여 Teams 데이터와 Teams 환경에 익숙해지도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-218">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="c1d2f-219">환경의 모양과 작동 방식을 아는 것은 의심스러운 활동을 인식하는 데 바람직한 첫 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-219">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="c1d2f-220">여기서 위협 헌팅으로 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-220">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="c1d2f-221">페더레이션된 외부 사용자 쿼리</span><span class="sxs-lookup"><span data-stu-id="c1d2f-221">Federated external users query</span></span>

<span data-ttu-id="c1d2f-222">페더레이션된 외부 사용자가 있는 Teams 사이트 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-222">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="c1d2f-223">이들 사용자는 조직에서 소유하지 *않는* 도메인 이름/UPN 접미사를 갖게됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-223">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="c1d2f-224">이 예제 쿼리에서는 조직이 contoso.com를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-224">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="c1d2f-225">Teams의 외부 및 게스트 액세스 유형에 대한 자세한 내용은 [이 문서](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) 또는 [Teams 보안 가이드](https://docs.microsoft.com/microsoftteams/teams-security-guide)의 *참가자 유형* 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-225">To learn more about External and Guest access types in Teams see [this article](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations), or the *Participant Types* section in the [Teams Security Guide](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="c1d2f-226">최근 참가한 사용자/역할이 변경된 사용자</span><span class="sxs-lookup"><span data-stu-id="c1d2f-226">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="c1d2f-227">특정 사용자를 쿼리하여 최근 7일 또는 일주일 이내에 Teams 채널에 추가되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-227">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="c1d2f-228">최근 7일 이내에 Teams에 대한 사용자의 역할이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-228">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="c1d2f-229">알 수 없는 조직이나 새 조직의 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="c1d2f-229">External users from unknown or new organizations</span></span>

<span data-ttu-id="c1d2f-230">Teams에서 사용자 환경이나 채널에 외부 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-230">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="c1d2f-231">조직은 종종 제한된 수의 주요 파트너 관계를 가지고 있으며, 이러한 파트너 들 사이에서 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-231">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="c1d2f-232">이 KQL는 이전에 보이거나 추가되지 않은 조직에서 온 팀에 추가된 외부 사용자를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-232">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="c1d2f-233">추가된 후 제거된 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="c1d2f-233">External users who were added and then removed</span></span>

<span data-ttu-id="c1d2f-234">기존의 어느 정도의 액세스 권한이 있는 공격자는 Teams에 새 외부 계정을 추가하여 데이터에 액세스하고 데이터를 빼낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-234">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="c1d2f-235">또한 액세스한 사실을 숨기기 위해 해당 사용자를 신속히 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-235">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="c1d2f-236">이 쿼리는 Teams에 추가되고 신속히 제거되는 외부 계정을 헌팅하여 의심스러운 동작을 식별하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-236">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="c1d2f-237">새 봇 또는 응용 프로그램이 추가됨</span><span class="sxs-lookup"><span data-stu-id="c1d2f-237">New bot or application added</span></span>

<span data-ttu-id="c1d2f-238">Teams는 팀에 앱 또는 봇을 포함하여 기능 집합을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-238">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="c1d2f-239">여기에는 사용자 지정 앱과 봇이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-239">This includes custom apps and bots.</span></span> <span data-ttu-id="c1d2f-240">경우에 따라 앱 또는 봇을 사용하여 사용자 계정이 없어도 Teams에 지속성을 설정하고 파일 및 기타 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-240">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="c1d2f-241">이 쿼리는 Teams에 새로운 앱이나 봇을 헌팅합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-241">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="c1d2f-242">다수의 Teams의 소유자인 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="c1d2f-242">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="c1d2f-243">자신의 권한을 승격하려는 공격자는 일반적으로 사용자가 특정 항목에 대한 소수의 Teams를 만들고 소유하는 경우, 다수의 다양한 Teams의 소유자 권한을 자신에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-243">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="c1d2f-244">이 KQL 쿼리는 의심스러운 동작을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-244">This KQL query looks for suspicious behavior.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="c1d2f-245">단일 사용자에 의한 다수의 팀 삭제</span><span class="sxs-lookup"><span data-stu-id="c1d2f-245">Many Team deletions by a single user</span></span>

<span data-ttu-id="c1d2f-246">공격자는 여러 팀을 삭제하여 프로젝트와 데이터의 분열을 유발하고 위태롭게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-246">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="c1d2f-247">팀은 일반적으로 개별 소유자에 의해 삭제되기 때문에 많은 팀에 대한 중앙 집중식 삭제는 문제의 징후일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-247">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="c1d2f-248">이 KQL은 여러 팀을 삭제하는 단일 사용자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-248">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="c1d2f-249">스레드 헌팅 기회 확장하기</span><span class="sxs-lookup"><span data-stu-id="c1d2f-249">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="c1d2f-250">Azure AD(Azure Active Directory) 또는 기타 Office 365 워크로드와 같은 리소스의 쿼리를 Teams 쿼리와 결합하여 헌팅을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-250">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="c1d2f-251">한가지 예로는 Teams 소유자를 헌팅하는 동안 Azure AD SigninLogs에서 의심스러운 패턴의 검색과 이러한 정보의 사용을 결합하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-251">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="c1d2f-252">또한 다음을 사용하여 Teams 기반 로그인에 대해서만 필터를 추가하여 Teams와 관련된 SigninLogs를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-252">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="c1d2f-253">`where AppDisplayName starts with "Microsoft Teams"`의 사용을 더욱 상세히 설명하고자 다음의 KQL는 한 IP 주소에서 다양한 IP 주소에서 오류가 발생했지만 Teams 로그인에만 범위가 지정되는 성공적인 로그온을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-253">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="c1d2f-254">중요 정보 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="c1d2f-254">Important information and updates</span></span>

<span data-ttu-id="c1d2f-255">**콘텐츠 공동 작업에 감사드립니다. Pete Bryan, Nicholas DiCola, Matthew Lowe.**</span><span class="sxs-lookup"><span data-stu-id="c1d2f-255">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="c1d2f-256">Pete Bryan씨와 공동 작업을 하는 사용자들은 검색 및 헌팅 쿼리를 계속해서 개발할 것이므로 이 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 리포지토리를 계속 사용하여 업데이트를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-256">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="c1d2f-257">이 문서에서 사용되는 [파서](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) 및 [논리 앱](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)에 대한 업데이트를 모니터링하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-257">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="c1d2f-258">또한 [Azure Sentinel 커뮤니티](https://github.com/Azure/Azure-Sentinel/wiki)에 참가하고 기여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-258">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="c1d2f-259">감사합니다!</span><span class="sxs-lookup"><span data-stu-id="c1d2f-259">Thank you!</span></span> <span data-ttu-id="c1d2f-260">즐거운 헌팅을 하세요.</span><span class="sxs-lookup"><span data-stu-id="c1d2f-260">Happy hunting.</span></span>

[<span data-ttu-id="c1d2f-261">Azure AD에서 응용 프로그램을 등록하기</span><span class="sxs-lookup"><span data-stu-id="c1d2f-261">Registering your application in Azure AD</span></span>](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="c1d2f-262">감사 로그 검색 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="c1d2f-262">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[<span data-ttu-id="c1d2f-263">Azure Sentinel이란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c1d2f-263">What is Azure Sentinel</span></span>](https://docs.microsoft.com/azure/sentinel/overview)
