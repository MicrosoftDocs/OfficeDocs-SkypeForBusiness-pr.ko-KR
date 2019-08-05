---
title: 보관된 비즈니스용 Skype 데이터를 검색하도록 SharePoint Server 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: '요약: Exchange Server 및 비즈니스용 Skype 서버에서 보관 한 데이터를 검색 하도록 SharePoint Server를 구성 합니다.'
ms.openlocfilehash: 2fb4b601e594ca48105afcf2e0c75107b2c6bceb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188124"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="079d3-103">보관된 비즈니스용 Skype 데이터를 검색하도록 SharePoint Server 구성</span><span class="sxs-lookup"><span data-stu-id="079d3-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="079d3-104">**요약:** SharePoint Server에서 Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에서 보관 한 데이터를 검색 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="079d3-105">비즈니스용 Skype Server 대신 Exchange Server에 인스턴트 메시징 및 웹 회의 기록 저장을 하는 주요 이점 중 하나는 같은 위치에 데이터를 저장 하면 관리자가 단일 도구를 사용 하 여 보관 된 Exchange 데이터를 검색할 수 있다는 것입니다. 비즈니스용 Skype 서버 데이터를 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="079d3-106">모든 데이터가 같은 위치에 저장 되므로 (Exchange) 보관 된 Exchange 데이터를 검색할 수 있는 모든 도구가 비즈니스용 Skype 서버 데이터를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="079d3-107">보관 된 데이터를 쉽게 검색할 수 있는 한 가지 도구는 Microsoft SharePoint Server 2013입니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="079d3-108">SharePoint를 사용 하 여 비즈니스용 Skype 서버 데이터를 검색 하려면 비즈니스용 Skype 서버에서 Exchange 보관을 구성 하는 것과 관련 된 모든 단계를 먼저 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="079d3-109">Exchange Server 및 비즈니스용 Skype 서버가 성공적으로 통합 된 후에는 SharePoint Server에 Exchange [Web Services 관리 API](https://go.microsoft.com/fwlink/p/?LinkId=258305) 를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="079d3-110">다운로드 한 파일 (EWSManagedAPI)을 SharePoint 서버의 모든 폴더에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="079d3-111">파일을 다운로드 한 후 SharePoint 서버에서 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="079d3-112">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**을 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 하 여 명령 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="079d3-113">명령 창에서 cd 명령을 사용 하 여 현재 디렉터리를 EWSManagedAPI 파일이 저장 된 폴더로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="079d3-114">예를 들어 C:\Downloads 다운로드에 파일을 저장 한 경우 명령 창에 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="079d3-115">API를 설치 하려면 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="079d3-116">API가 설치 되 면 다음 명령을 입력 하 고 Enter 키를 눌러 IIS를 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="079d3-117">Exchange Web Services가 설치 된 후 SharePoint Server와 Exchange Server 간에 서버 간 인증을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="079d3-118">이렇게 하려면 먼저 SharePoint 관리 셸을 열고 다음 명령 집합을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="079d3-119">자동 검색 서비스에 대 한 URI를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="079d3-120">샘플 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="079d3-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="079d3-121">토큰 발급자를 만들고 토큰 서비스를 구성한 후에는이 명령을 실행 하 여 샘플 URL에 대 한 SharePoint 사이트의 URL을 대체 하세요.http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="079d3-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="079d3-122">Exchange Server에 대해 서버 간 인증을 구성 하려면 exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다 (C: 드라이브에 Exchange가 설치 되어 있고 기본 폴더 경로를 사용 하 고 있다고 가정).</span><span class="sxs-lookup"><span data-stu-id="079d3-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="079d3-123">파트너 응용 프로그램을 구성한 후에는 모든 Exchange 사서함 및 클라이언트 액세스 서버에서 IIS (인터넷 정보 서비스)를 중지 하 고 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="079d3-124">컴퓨터 atl-exchange-001에서 서비스를 다시 시작 하는 다음과 같은 명령을 사용 하 여 IIS를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="079d3-125">이 명령은 Exchange 관리 셸 또는 다른 명령 창 내에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="079d3-126">다음으로, 다음과 비슷한 명령을 실행 하 여 Exchange에서 검색을 수행할 수 있는 권한을 지정 된 사용자 (이 예제에서는 kenmyer)에 게 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="079d3-127">Exchange와 SharePoint 간에 서버 간 인증이 설정 된 후 다음 단계는 SharePoint에서 eDiscovery 사이트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="079d3-128">이 작업은 SharePoint 관리 셸에서와 비슷한 명령으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="079d3-129">"eDiscovery"은 "전자적 검색"에 대해 짧고 일반적으로 "admissible 증명을 받을 수 있는 항목"이 법률의 법정에서 "적절 하 게 계산 되어"는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="079d3-130">새 사이트를 사용할 준비가 되 면 다음 단계는 SharePoint의 결과 원본 역할을 하도록 Exchange Server를 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="079d3-131">SharePoint 중앙 관리 페이지에서 다음 절차를 완료 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="079d3-132">중앙 관리 페이지에서 **서비스 응용 프로그램 관리** 를 클릭 한 다음 **검색 서비스 응용 프로그램**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="079d3-133">Search Service 응용 프로그램: 관리 페이지 검색 **결과 원본을** 클릭 한 다음 **새 결과 원본을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="079d3-134">**새 결과 원본** 창에서 **이름** 상자에 새 결과 원본 (예: **Microsoft Exchange**)의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="079d3-135">**Exchange** 를 결과 원본 **프로토콜로**선택한 다음 exchange **원본 url** 상자에 EXCHANGE server의 웹 서비스 원본 url을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="079d3-136">원본 URL은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="079d3-137">**자동 검색 사용** 이 선택 되어 있지 않은지 확인 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="079d3-138">마지막으로, SharePoint 검색 사이트에서 다음 절차를 완료 하 여 새 eDiscovery 사례와 새 eDiscovery 집합을 만듭니다 (예:https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="079d3-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="079d3-139">사이트 콘텐츠 페이지에서 **새 사례 만들기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="079d3-140">사이트 콘텐츠: 새 SharePoint 사이트 페이지에서 **제목** 상자에 사용자의 전자 메일 별칭 (예: **kenmyer**)을 입력 한 다음 같은 URL을 **웹 사이트 주소** 상자에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-140">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box.</span></span> <span data-ttu-id="079d3-141">그러면 다음과 같은 URL이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-141">That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="079d3-142">**만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="079d3-143">EDiscovery 설정 페이지가 나타나면 Id 아래에서 **새 항목** 을 클릭 **하 고 유지: 검색 집합**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="079d3-144">새: 검색 집합 페이지의 **검색 집합 이름** 상자에 사용자의 전자 메일 별칭을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="079d3-145">**필터** 상자에 \*\*eDiscovery Lync\\*\*\*를 입력 한 다음 **원본 관리 &amp; 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-145">Enter **eDiscovery Lync\\**\* in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="079d3-146">원본 관리 추가 &amp; 페이지의 **사서함**아래 첫 번째 텍스트 상자에 사용자의 전자 메일 별칭을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="079d3-147">교재 옆에 있는 사서함 확인 아이콘을 클릭 하 여 SharePoint가 지정 된 사서함에 연결할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="079d3-148">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="079d3-149">EDiscovery 설정 페이지에서 **저장** 을 클릭 하 여 새 ediscovery 집합을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="079d3-150">이 시점에서 다른 SharePoint 콘텐츠 또는 결과 원본에 대해 사용 하는 것과 동일한 방법으로 지정 된 사서함 (kenmyer) 및/또는 In 위치 유지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="079d3-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

