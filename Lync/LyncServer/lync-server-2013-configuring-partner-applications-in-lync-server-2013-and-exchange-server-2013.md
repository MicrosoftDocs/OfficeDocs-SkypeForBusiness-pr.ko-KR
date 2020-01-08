---
title: Lync Server 2013 및 Exchange Server 2013에서 파트너 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="dedff-102">Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013에서 파트너 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="dedff-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dedff-103">_**마지막으로 수정한 주제:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="dedff-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="dedff-104">서버 간 인증에는 일반적으로 서로 통신 해야 하는 두 개의 서버와 타사 보안 토큰 서버 등 세 가지 엔터티가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-104">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="dedff-105">두 서버 (예: 서버 A와 서버 B)가 통신 해야 하는 경우 일반적으로 두 서버 모두 토큰 서버에 접속 하 고 상호 신뢰할 수 있는 보안 토큰을 가져오는 방법으로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-105">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="dedff-106">그런 다음 서버 A는 해당 신뢰성과 신뢰성을 보장 하는 방법으로 보안 토큰을 서버 B에 제공 합니다 (그 반대의 경우도 마찬가지).</span><span class="sxs-lookup"><span data-stu-id="dedff-106">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="dedff-107">그러나 일반 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-107">However, that's a general rule.</span></span> <span data-ttu-id="dedff-108">Lync Server 2013, Microsoft Exchange Server 2013, Microsoft SharePoint Server 2013는 서로 통신할 때 타사 토큰 서버를 사용할 필요가 없습니다. 이는 이러한 서버 제품이 별도의 토큰 서버 없이 다른 사람이 수락할 수 있는 보안 토큰을 만들 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="dedff-109">(이 접근 권한 값은 Lync Server 2013, Exchange 2013 및 SharePoint Server 2013 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="dedff-110">다른 Microsoft server 제품을 포함 하 여 다른 서버와 서버 간 인증을 설정 해야 하는 경우 타사 토큰 서버를 사용 하 여이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="dedff-111">Lync Server와 Exchange 간에 서버 간 인증을 설정 하려면 다음 두 가지 작업을 수행 해야 합니다. 1) 각 서버에 적절 한 인증서를 할당 해야 합니다. and, 2) 각 서버를 다른 서버의 파트너 응용 프로그램으로 구성 해야 합니다. 즉, Lync Server 2013을 Exchange 2013의 파트너 응용 프로그램으로 구성 해야 하며, Lync Server 2013에 대 한 파트너 응용 프로그램이 되도록 Exchange 2013을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="dedff-112">Lync Server 2013을 Exchange 2013 용 파트너 응용 프로그램으로 구성</span><span class="sxs-lookup"><span data-stu-id="dedff-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="dedff-113">Exchange 2013을 사용 하 여 Lync Server 2013을 파트너 응용 프로그램으로 구성 하는 가장 쉬운 방법은 Exchange 2013과 함께 제공 되는 Windows PowerShell 스크립트인 Configure-EnterprisePartnerApplication 스크립트를 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="dedff-114">이 스크립트를 실행 하려면 Lync Server 인증 메타 데이터 문서에 대 한 URL을 제공 해야 합니다. 이는 일반적으로 Lync Server 2013 풀의 정규화 된 도메인 이름이 고 그 뒤에는 접미사가/metadata/json/1.입니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="dedff-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="dedff-116">Lync Server를 파트너 응용 프로그램으로 구성 하려면 Exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다 (C: 드라이브에 Exchange가 설치 되어 있고 기본 폴더 경로를 사용 하 고 있다고 가정).</span><span class="sxs-lookup"><span data-stu-id="dedff-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="dedff-117">파트너 응용 프로그램을 구성한 후에는 Exchange 사서함 및 클라이언트 액세스 서버에서 IIS (인터넷 정보 서비스)를 중지 하 고 다시 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="dedff-118">컴퓨터 atl-exchange-001에서 서비스를 다시 시작 하는 다음과 같은 명령을 사용 하 여 IIS를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="dedff-119">이 명령은 Exchange 관리 셸 내에서 또는 관리자 권한으로 실행 되는 다른 명령 창에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="dedff-120">Lync Server 2013 용 파트너 응용 프로그램으로 Exchange 2013 구성</span><span class="sxs-lookup"><span data-stu-id="dedff-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="dedff-121">Lync Server 2013을 Exchange 2013 용 파트너 응용 프로그램으로 구성한 후에는 Lync Server에 대 한 파트너 응용 프로그램이 되도록 Exchange를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="dedff-122">Lync Server 관리 셸을 사용 하 고 Exchange에 대 한 인증 메타 데이터 문서를 지정 하 여이 작업을 수행할 수 있습니다. 이는 일반적으로 Exchange 자동 검색 서비스의 URI이 고 그 뒤에 접미사/metadata/json/1. 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="dedff-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="dedff-124">Lync Server에서 파트너 응용 프로그램은 [New CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) cmdlet을 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="dedff-125">메타 데이터 URI를 지정 하는 것 외에도 응용 프로그램 신뢰 수준을 Full로 설정 해야 합니다. 이를 통해 Exchange는 자신 및 영역에 있는 권한 있는 모든 사용자를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="dedff-126">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="dedff-127">또는 Lync Server 2013 서버 간 인증 설명서에 있는 스크립트 코드를 복사 하 여 수정 하 여 파트너 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="dedff-128">자세한 내용은 [Lync server 2013의 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dedff-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="dedff-129">Lync Server와 Exchange 둘 다에 대해 파트너 응용 프로그램을 성공적으로 구성한 경우 두 제품 간에 서버 간 인증을 성공적으로 구성 했음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="dedff-130">Lync Server 2013에는 서버 간 인증이 올바르게 구성 되었는지 확인 하 고 Lync Server 저장소 서비스에서 Exchange 2013에 연결할 수 있도록 하는 Windows PowerShell cmdlet 인 [Test CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="dedff-131">Cmdlet은 Exchange 2013 사용자의 사서함에 연결 하 고 해당 사용자의 대화 내용 폴더에 항목을 쓴 다음 선택적으로 해당 항목을 삭제 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="dedff-132">Lync Server 2013 및 Exchange 2013의 통합을 테스트 하려면 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="dedff-133">앞의 명령에서 SipUri는 Exchange 2013에 계정이 있는 사용자의 SIP 주소를 나타냅니다. 이 명령은 올바른 사용자 계정이 아닌 경우에는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="dedff-134">테스트가 성공 하 고 연결이 설정 되 면 계속 진행 하 여 보관 통합 및 통합 된 연락처 저장소와 같은 선택적 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dedff-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

