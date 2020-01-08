---
title: 'Lync Server 2013: 모임 초대 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014a42597e3df416d9e502eaaa90e2f1e71e35ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="2ee13-102">Lync Server 2013에서 모임 초대 구성</span><span class="sxs-lookup"><span data-stu-id="2ee13-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ee13-103">_**마지막으로 수정한 주제:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="2ee13-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="2ee13-104">모임 초대의 본문에 다음 선택 항목을 포함 하 여 Lync 2013의 온라인 모임 추가 기능에서 보낸 모임 초대를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="2ee13-105">**조직의 로고** 로고 URL 옵션을 사용 하 여 모임 초대에 조직의 로고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="2ee13-106">조직 외부의 사용자에 게 모임 초대를 보내는 경우 이미지가 공개적으로 사용할 수 있는 URL에 위치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="2ee13-107">지원 되는 이미지 형식은 GIF 및 JPG입니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="2ee13-108">Lync Server 2013에서 이미지에 크기 제한이 없는 URL을 저장 하는 경우 최상의 결과를 위해 이미지의 최대 크기는 너비가 각각 30 픽셀, 높이 188 픽셀 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="2ee13-109">**사용자 지정 도움말 또는 지원 링크** 조직의 도움말 또는 지원 팀 웹 사이트에 대 한 URL을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="2ee13-110">조직 외부의 사용자에 게 모임 초대를 보내는 경우 URL을 공개적으로 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="2ee13-111">최대 URL 길이는 1kb입니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="2ee13-112">**법적 고 지 사항 텍스트** 모든 모임 초대에 표시 되는 법적 고 지 사항 또는 내용에 대 한 URL을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="2ee13-113">조직 외부의 사용자에 게 모임 초대를 보내는 경우 URL을 공개적으로 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="2ee13-114">최대 URL 길이는 1kb입니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="2ee13-115">**사용자 지정 바닥글 텍스트** 초대에 사용자 지정 바닥글로 렌더링할 텍스트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="2ee13-116">추가할 수 있는 최대 텍스트 길이는 2kb입니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="2ee13-117">Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 이러한 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="2ee13-118">**Lync Server 제어판을 사용 하 여 모임 초대를 사용자 지정 하려면**</span><span class="sxs-lookup"><span data-stu-id="2ee13-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="2ee13-119">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="2ee13-120">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ee13-121">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ee13-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ee13-122">왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **모임 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="2ee13-123">**모임 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="2ee13-124">사이트 수준 정책을 만들려면 **사이트 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-124">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="2ee13-125">사이트 검색 **선택** 필드에 모임 참가 설정을 정의할 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-125">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="2ee13-126">사이트 결과 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-126">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2ee13-127">풀 수준 정책을 만들려면 **풀 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-127">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="2ee13-128">서비스 검색 **선택** 필드에 모임 참가 설정을 정의할 풀 서비스 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-128">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="2ee13-129">결과 서비스 목록에서 원하는 풀을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-129">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="2ee13-130">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="2ee13-131">**로고 url** 필드에 조직의 로고 이미지에 대 한 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="2ee13-132">**도움말 url** 필드에 조직의 도움말 또는 지원 사이트에 대 한 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="2ee13-133">**법적** 고 지 사항 필드에 약관에 대 한 URL을 입력 하 고 모임 초대에 포함할 법률 또는 책임의 텍스트</span><span class="sxs-lookup"><span data-stu-id="2ee13-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="2ee13-134">**사용자 지정 바닥글 텍스트** 필드에 바닥글 텍스트 (최대 2kb)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="2ee13-135">**Lync Server Management Shell을 사용 하 여 모임 초대를 사용자 지정 하려면**</span><span class="sxs-lookup"><span data-stu-id="2ee13-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="2ee13-136">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2ee13-137">**새 CsMeetingConfiguration** 또는 **Set-CsMeetingConfiguration** cmdlet을 실행 하 여 모임 초대 옵션을 만들거나 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="2ee13-138">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2ee13-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

