---
title: OAuth (서버 대 서버 인증) 및 파트너 응용 프로그램 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="41d45-102">Lync Server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리</span><span class="sxs-lookup"><span data-stu-id="41d45-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d45-103">_**마지막으로 수정한 주제:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="41d45-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="41d45-104">Microsoft Lync Server 2013는 다른 응용 프로그램 및 서버 제품과 통신 하 고 원활 하 게 통신할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="41d45-105">예를 들어 연락처 데이터 및/또는 보관 데이터가 Microsoft Exchange Server 2013에 저장 되도록 Lync Server 2013을 구성할 수 있습니다. 그러나 Lync Server와 Exchange가 서로 안전 하 게 통신할 수 있는 경우에만이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="41d45-106">마찬가지로 Microsoft SharePoint Server 내에서 Lync 서버 회의를 예약할 수 있습니다. 그러나, 두 서버 (SharePoint 및 Lync Server)가 서로 신뢰 하는 경우에만이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="41d45-107">Lync to Exchange 통신에는 하나의 인증 메커니즘을 사용 하 고 Lync to SharePoint 통신을 위한 별도의 메커니즘을 사용할 수 있지만, 보다 나은 방법으로 모든 서버에서 서버에 대해 표준화 된 메서드를 사용 하는 것이 더 효율적입니다. 인증 및 권한 부여.</span><span class="sxs-lookup"><span data-stu-id="41d45-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="41d45-108">서버 간 인증에 대해 표준화 된 단일 메서드를 사용 하는 방법은 Lync Server 2013에서 수행 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="41d45-109">2013 릴리스의 경우, Lync Server 2013 (Exchange 2013 및 Microsoft SharePoint Server 포함)의 다른 Microsoft 서버 제품은 서버 간 인증 및 권한 부여에 대 한 OAuth (열기 권한 부여) 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="41d45-110">여러 주요 웹사이트에서 사용 되는 OAuth, 표준 인증 프로토콜을 사용 하는 경우 사용자 자격 증명과 암호가 한 컴퓨터에서 다른 컴퓨터로 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="41d45-111">대신 인증 및 권한 부여는 보안 토큰의 교환에 기반을 둔 것입니다. 이러한 토큰은 특정 기간 동안 특정 리소스 집합에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="41d45-112">OAuth 인증은 일반적으로 하나의 인증 서버와 서로 통신 해야 하는 두 개의 영역과 관련 하 여 세 가지를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="41d45-113">(이 문서의 뒷부분에서 설명할 프로세스 인 권한 부여 서버를 사용 하지 않고 서버 간 인증을 수행할 수도 있습니다.) 보안 토큰은 통신 해야 하는 두 개의 영역에 대 한 권한 부여 서버 (보안 토큰 서버 라고도 함)에서 발급 합니다. 이러한 토큰은 한 영역에서 보낸 통신을 다른 영역에서 신뢰 해야 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="41d45-114">예를 들어 권한 부여 서버는 특정 Lync Server 2013 영역의 사용자가 지정 된 Exchange 2013 영역에 액세스할 수 있는지 확인 하는 토큰을 발급할 수 있으며 그 반대의 경우도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="41d45-115">영역은 단순히 보안 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-115">A realm is simply a security container.</span></span> <span data-ttu-id="41d45-116">기본적으로 Lync Server 2013는 기본 SIP 도메인을 OAuth 영역으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="41d45-117">추가 SIP 네임 스페이스는 OAuth 인증서의 주체 대체 이름 목록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="41d45-118">Lync Server 2013는 세 가지 서버 간 인증 시나리오를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="41d45-119">Lync Server 2013를 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="41d45-120">Lync Server 2013의 온-프레미스 설치와 Exchange 2013 및/또는 Microsoft SharePoint Server의 온-프레미스 설치 사이에서 서버 간 인증을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="41d45-121">한 쌍의 Office 365 구성 요소 (예: Microsoft Exchange와 Microsoft Lync Server 간 또는 Microsoft Lync Server와 Microsoft SharePoint 간) 간에 서버 간 인증을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-121">Configure server-to-server authentication between a pair of Office 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="41d45-122">교차 구내 환경에서 서버 간 인증을 구성 합니다 (즉, 온-프레미스 서버와 Office 365 구성 요소 간에 서버 간 인증).</span><span class="sxs-lookup"><span data-stu-id="41d45-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Office 365 component).</span></span>

<span data-ttu-id="41d45-123">이 시점에서 Exchange 2013, SharePoint Server 및 Lync Server 2013만 서버 간 인증을 지원 한다는 점에 유의 하세요. 이러한 서버 중 하나를 실행 하지 않는 경우에는 OAuth 인증을 완전히 구현할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="41d45-124">또한 서버 간 인증을 사용할 필요가 없다는 것을 지적 하는 것이 좋습니다. Lync Server 2013을 배포 하기 위해 서버와 서버 간의 인증이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="41d45-125">Lync Server 2013가 Exchange 2013 등의 다른 서버와 통신할 필요가 없는 경우 서버 간 인증이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="41d45-126">그러나 일부 Lync Server의 새 기능 (예: "통합 연락처 저장소")을 사용 하려는 경우 서버 간 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="41d45-127">통합 된 대화 상대 저장소에서 Lync Server 2013 연락처 정보는 Lync Server 대신 Exchange 2013에 저장 됩니다. 이를 통해 사용자는 Lync, Microsoft Outlook 또는 Microsoft Outlook Web Access 내에서 쉽게 액세스할 수 있는 단일 연락처 집합을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="41d45-128">통합 된 대화 상대 저장소에는 Exchange 2013와 정보를 공유 하기 위한 Lync Server 2013이 필요 하므로 기능을 배포 하려면 서버 간 인증을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="41d45-129">인스턴트 메시징 세션의 기록이 개별 데이터베이스 레코드가 아닌 Exchange 2013 메일로 저장 되는 Exchange 보관을 사용 하도록 선택한 경우에도 서버와 서버 간 인증이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="41d45-130">Office 365 버전의 Lync Server가 해당 Exchange와 통신 하려면 먼저, Lync Server 2013에서 권한 부여 서버 로부터 보안 토큰을 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-130">For the Office 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="41d45-131">그러면 Lync Server가 해당 보안 토큰을 사용 하 여 자신을 Exchange에 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="41d45-132">Office 365 버전의 Exchange는 Lync Server 2013와 통신 하기 위해 동일한 프로세스를 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-132">The Office 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="41d45-133">그러나 두 Microsoft 서버 간에 온-프레미스 서버 간 인증은 타사 토큰 서버를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="41d45-134">Lync Server 2013 및 Exchange 2013 같은 서버 제품에는 서버에서 서버 간 인증을 지 원하는 다른 Microsoft 서버 (예: SharePoint Server)의 인증 용도로 사용할 수 있는 기본 제공 토큰 서버가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="41d45-135">예를 들어 Lync Server 2013는 보안 토큰 자체에 대 한 발급 및 서명을 할 수 있으며, 해당 토큰을 사용 하 여 Exchange 2013와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="41d45-136">이와 같은 경우에는 타사 토큰 서버를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="41d45-137">Lync Server 2013의 온-프레미스 구현에 대해 서버 간 인증을 구성 하려면 다음 두 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="41d45-138">Lync Server의 기본 제공 토큰 발급자에 게 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="41d45-139">Lync Server 2013가 통신 하는 서버를 "파트너 응용 프로그램"으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="41d45-140">예를 들어 Lync Server 2013에서 Exchange 2013와 통신 해야 하는 경우 Exchange를 파트너 응용 프로그램으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="41d45-141">"파트너 응용 프로그램"은 타사 보안 토큰 서버를 거치지 않고도 Lync Server 2013에서 직접 보안 토큰을 교환할 수 있는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="41d45-142">OAuth는 제품의 핵심 부분이 며 사용 하지 않도록 설정 하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d45-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="41d45-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41d45-143">See Also</span></span>


[<span data-ttu-id="41d45-144">서버 간 인증 인증서를 Microsoft Lync Server 2013에 할당</span><span class="sxs-lookup"><span data-stu-id="41d45-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="41d45-145">교차 프레미스 환경에서 Microsoft Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="41d45-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

