---
title: 'Lync Server 2013: Exchange Server 2013과 통합 하기 위한 선행 조건'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51bc3ce48756f746b2f2f5c0ce65d08567fea74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="1a5ff-102">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 통합을 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1a5ff-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a5ff-103">_**마지막으로 수정한 주제:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="1a5ff-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="1a5ff-104">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013를 통합 하려면 먼저 모든 필수 단계가 완료 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="1a5ff-105">예상 대로 Exchange 2013 및 Lync Server 2013가 모두 설치 되 고 실행 될 때까지 통합을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="1a5ff-106">Exchange 설치에 대 한 자세한 내용은의 [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)Exchange 2013 계획 및 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="1a5ff-107">Lync Server 2013 설치에 대 한 자세한 내용은의 [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)계획 및 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="1a5ff-108">서버가 작동 중이 되 고 나면 서버 간 인증 인증서를 Lync Server 2013 및 Exchange 2013 둘 다에 할당 해야 합니다. 이러한 인증서를 통해 Lync Server와 Exchange에서 정보를 교환 하 고 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="1a5ff-109">Exchange 2013을 설치 하면 Microsoft Exchange Server 인증 인증서 이름을 가진 자체 서명 된 인증서가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="1a5ff-110">로컬 컴퓨터 인증서 저장소에서 찾을 수 있는이 인증서는 Exchange 2013에서 서버 간 인증에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="1a5ff-111">Exchange 2013에서 인증서를 할당 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)"메일 흐름 및 클라이언트 액세스 구성"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="1a5ff-112">Lync Server 2013의 경우 기존 Lync Server 인증서를 서버 간 인증 인증서로 사용할 수 있습니다. 예를 들어 기본 인증서는 OAuthTokenIssuer 인증서로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="1a5ff-113">Lync Server 2013를 사용 하면 다음과 같은 경우에 서버 간 인증의 인증서로 모든 웹 서버 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="1a5ff-114">인증서는 제목 필드에 SIP 도메인의 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="1a5ff-115">동일한 인증서가 모든 프런트 엔드 서버에서 OAuthTokenIssuer 인증서로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="1a5ff-116">인증서의 길이는 최소 2048 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="1a5ff-117">Microsoft Lync Server 2013의 서버 간 인증 인증서에 대 한 자세한 내용은 [Microsoft Lync server 2013에 서버에서 서버에 대 한 인증 인증서 지정](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="1a5ff-118">인증서를 할당 한 후에는 Exchange 2013에서 자동 검색 서비스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="1a5ff-119">Exchange 2013에서 자동 검색 서비스는 사용자 프로필을 구성 하 고 사용자가 시스템에 로그온 할 때 Exchange 서비스에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="1a5ff-120">사용자가 전자 메일 주소와 암호를 사용 하 여 자동 검색 서비스를 제공 합니다. 그런 다음 서비스는 사용자에 게 다음과 같은 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="1a5ff-121">Exchange 2013에 대 한 내부 및 외부 연결 모두에 대 한 연결 정보.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="1a5ff-122">사용자 사서함 서버의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="1a5ff-123">약속 있음/없음 정보, 통합 메시징, 오프 라인 주소록과 같은 Outlook 기능에 대 한 Url입니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="1a5ff-124">Outlook Anywhere 서버 설정</span><span class="sxs-lookup"><span data-stu-id="1a5ff-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="1a5ff-125">Lync Server 2013 및 Exchange 2013을 통합 하려면 자동 검색 서비스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="1a5ff-126">Exchange 관리 셸에서 다음 명령을 실행 하 고 AutoDiscoverServiceInternalUri 속성 값을 확인 하 여 자동 검색 서비스가 구성 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="1a5ff-127">이 값이 비어 있으면 자동 검색 서비스에 URI를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-127">If this value is blank, you must assign a URI to the autodiscover service.</span></span> <span data-ttu-id="1a5ff-128">일반적으로이 URI는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-128">Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="1a5ff-129">다음과 같은 명령을 실행 하 여 자동 검색 URI를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="1a5ff-130">자동 검색 서비스에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)"자동 검색 서비스 이해"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="1a5ff-131">자동 검색 서비스를 구성한 후에는 Lync Server OAuth 구성 설정을 수정 해야 합니다. 이렇게 하면 Lync Server에서 자동 검색 서비스를 찾을 수 있는 위치를 인식 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="1a5ff-132">Lync Server 2013의 OAuth 구성 설정을 수정 하려면 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="1a5ff-133">이 명령을 실행 하는 경우 Exchange server에서 실행 되는 자동 검색 서비스에 대 한 URI를 지정 하 고 서비스에서 사용 하는 XML 파일을 **가리키는 자동 검색** 을 사용 하 여 서비스 위치를 가리키는 방법을 선택 **해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="1a5ff-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="1a5ff-134">앞의 명령에서 Identity 매개 변수는 선택 사항입니다. 이는 Lync Server 에서만 OAuth 구성 설정의 단일 전역 컬렉션을 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="1a5ff-135">즉, 다음과 같이 약간 더 간단한 명령을 사용 하 여 자동 검색 URL을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="1a5ff-136">Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="1a5ff-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="1a5ff-137">기술에 익숙하지 않은 경우 OAuth는 여러 주요 웹 사이트에서 사용 하는 표준 인증 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-137">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites.</span></span> <span data-ttu-id="1a5ff-138">OAuth를 사용 하는 경우 사용자 자격 증명과 암호가 한 컴퓨터에서 다른 컴퓨터로 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-138">With OAuth, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="1a5ff-139">대신 인증 및 권한 부여는 보안 토큰의 교환에 기반을 둔 것입니다. 이러한 토큰은 특정 기간 동안 특정 리소스 집합에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-139">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="1a5ff-140">자동 검색 서비스를 구성 하는 것 외에도 Exchange server를 가리키는 서비스에 대 한 DNS 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a5ff-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="1a5ff-141">예를 들어 자동 검색 서비스가 autodiscover.litwareinc.com에 있는 경우 Exchange 서버의 정규화 된 도메인 이름으로 확인 되는 autodiscover.litwareinc.com에 대 한 DNS 레코드를 만들어야 합니다 (예: atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="1a5ff-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

