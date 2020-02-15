---
title: 'Lync Server 2013: 보관 된 Lync Server 2013 데이터를 검색 하도록 Microsoft SharePoint Server 2013 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8debab39073bf31f509ec504f944c8e4c7a9dfc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="ff604-102">보관 된 Microsoft Lync Server 2013 데이터를 검색 하도록 Microsoft SharePoint Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="ff604-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff604-103">_**마지막으로 수정 된 항목:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="ff604-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="ff604-104">Microsoft Lync Server 2013 대신 Microsoft Exchange Server 2013에서 인스턴트 메시징 및 웹 회의 성적 증명서를 저장 하는 주요 이점 중 하나는 데이터를 같은 위치에 저장 하면 관리자가 단일 도구를 사용 하 여 보관 된 Exchange 데이터 및/또는 아카이브된 Lync Server 데이터를 검색할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="ff604-105">모든 데이터가 같은 위치에 저장 되므로 보관 된 Exchange 데이터를 검색할 수 있는 도구를 통해 아카이브된 Lync Server 데이터를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="ff604-106">보관 된 데이터를 쉽게 검색할 수 있도록 하는 한 가지 도구는 Microsoft SharePoint Server 2013입니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="ff604-107">SharePoint를 사용 하 여 Lync Server 데이터를 검색 하려면 먼저 Lync Server에서 Exchange 보관을 구성 하는 데 관련 된 모든 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="ff604-108">Exchange 2013 및 Lync Server 2013이 통합 된 후에는 SharePoint 서버에 Exchange 웹 서비스 관리 API 버전 2.0을 설치 해야 합니다. 해당 API의 설치 프로그램은 Microsoft 다운로드 센터 ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305))에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="ff604-109">다운로드 한 파일 (EWSManagedAPI)은 SharePoint server의 모든 폴더에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="ff604-110">파일을 다운로드한 후 SharePoint 서버에서 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="ff604-111">**시작**, **모든 프로그램**, **보조 프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭하여 명령 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="ff604-112">명령 창에서 **cd** 명령을 사용하여 현재 디렉터리를 EWSManagedAPI.msi 파일이 저장된 폴더로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="ff604-113">예를 들어 파일을 C:\\다운로드에 저장 한 경우 명령 창에 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="ff604-114">API를 설치하려면 다음 명령을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="ff604-115">API가 설치되고 나면 다음 명령을 입력하고 Enter 키를 눌러 IIS를 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="ff604-116">Exchange 웹 서비스를 설치한 후 SharePoint Server 2013 및 Exchange 2013 간에 서버 간 인증을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="ff604-117">이렇게 하려면 먼저 SharePoint 2013 관리 셸을 열고 다음 명령 집합을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="ff604-118">이때 자동 검색 서비스의 URI를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="ff604-119">샘플 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ff604-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="ff604-120">토큰 발급자를 만들고 토큰 서비스를 구성한 후에는 이러한 명령을 실행 하 여 샘플 URL에 대 한 SharePoint 사이트의 URL로 대체 해야 합니다.http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="ff604-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="ff604-121">Exchange 2013에 대해 서버 간 인증을 구성 하려면 exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다 (Exchange가 C: 드라이브에 설치 되었고 기본 폴더 경로를 사용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="ff604-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="ff604-122">파트너 응용 프로그램을 구성한 후에는 모든 Exchange 사서함 및 클라이언트 액세스 서버에서 IIS (인터넷 정보 서비스)를 중지 하 고 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="ff604-123">다음과 같은 명령을 사용하여 IIS를 다시 시작할 수 있으며, 이 명령은 atl-exchange-001 컴퓨터에서 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="ff604-124">이 명령은 Exchange 관리 셸 또는 다른 명령 창 내에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="ff604-125">그런 다음 다음과 같은 명령을 실행 하 여 지정 된 사용자 (이 예에서 kenmyer)에 게 Exchange에서 검색을 수행할 수 있는 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="ff604-126">Exchange와 SharePoint 간에 서버 간 인증을 설정한 후에는 SharePoint에서 eDiscovery 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="ff604-127">이 작업은 SharePoint 관리 셸에서와 비슷한 명령을 실행 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="ff604-128">"eDiscovery"는 "electronic discovery(전자 검색)"의 줄임말로, 보통 법정에서 "적절하게 계산하여 채택될 수 있는 증거가 될 수 있는" 항목을 전자 보관 파일에서 찾는 프로세스를 지칭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="ff604-129">새 사이트가 준비 되 면 다음 단계는 SharePoint에 대 한 결과 원본으로 작동 하도록 Exchange 2013을 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="ff604-130">이 작업은 SharePoint 2013 중앙 관리 페이지에서 다음 절차를 완료 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="ff604-131">중앙 관리 페이지에서 **서비스 응용 프로그램 관리**를 클릭한 다음 **Search Service 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="ff604-132">Search Service 응용 프로그램: 검색 관리 페이지에서 **결과 원본**을 클릭하고 **새 결과 원본**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="ff604-133">**새 결과 원본** 창의 **이름** 상자에 새 결과 원본의 이름을 **Microsoft Exchange**와 같이 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="ff604-134">결과 원본 **프로토콜로** **exchange** 를 선택한 다음 exchange **원본 URL** 상자에 exchange server에 대 한 웹 서비스 원본 url을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="ff604-135">원본 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="ff604-136">**자동 검색 사용**이 선택되어 있지 않은지 확인하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="ff604-137">마지막으로 SharePoint 검색 사이트에서 다음 절차를 완료 하 여 새 eDiscovery 사례와 새 eDiscovery 집합을 만듭니다 (예:https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="ff604-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="ff604-138">사이트 콘텐츠 페이지에서 **새 사례 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="ff604-p110">사이트 콘텐츠: 새 SharePoint 사이트 페이지에서 사용자의 전자 메일 별칭(예: **kenmyer**)을 **제목**상자에 입력하고 동일한 URL을 **웹 사이트 주소** 상자에 추가합니다. 그러면 다음과 같은 URL이 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="ff604-141">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-141">Click **Create**.</span></span>

4.  <span data-ttu-id="ff604-142">eDiscovery 설정 페이지가 나타나면 **식별 및 보존: 검색 설정**에서 **새 항목**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="ff604-143">새로 만들기: 검색 설정 페이지의 **검색 설정 이름** 상자에 사용자의 전자 메일 별칭을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="ff604-144">**필터** 상자에 \*\*eDiscovery Lync\* \*\* 를 입력 한 다음 **추가 & 원본 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="ff604-p112">원본 추가 및 관리 페이지에서 **사서함** 아래 첫 번째 텍스트 상자에 사용자 전자 메일 별칭을 입력합니다. 해당 텍스트 상자 옆의 사서함 확인 아이콘을 클릭하여 SharePoint에서 지정된 사서함에 연결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="ff604-147">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-147">Click **OK**.</span></span>

8.  <span data-ttu-id="ff604-148">eDiscovery 설정 페이지에서 **저장**을 클릭하여 새 eDiscovery 집합을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="ff604-149">이때 지정 된 사서함 (kenmyer) 및/또는 원본 위치 유지를 검색 하려면 다른 SharePoint 콘텐츠 또는 결과 원본을 사용 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff604-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

