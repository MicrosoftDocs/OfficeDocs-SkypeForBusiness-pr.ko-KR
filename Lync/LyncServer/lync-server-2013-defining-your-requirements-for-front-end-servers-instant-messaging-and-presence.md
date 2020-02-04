---
title: 'Lync Server 2013: 프런트 엔드 서버, 메신저 및 현재 상태에 대한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="e987f-102">Lync Server 2013에서 프런트 엔드 서버, 메신저 및 현재 상태에 대한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="e987f-102">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e987f-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="e987f-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="e987f-104">IM (인스턴트 메시징) 및 현재 상태 계획의 주요 작업은 사용자에 게 충분 한 프런트 엔드 서버가 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-104">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="e987f-105">외부 사용자와의 통신 설정</span><span class="sxs-lookup"><span data-stu-id="e987f-105">Enabling Communication with External Users</span></span>

<span data-ttu-id="e987f-106">사용자가 외부 사용자와 통신할 수 있도록 하 여 Lync Server에 대 한 투자의 이점을 대폭 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-106">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="e987f-107">외부 사용자는 다음을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-107">External users can include:</span></span>

  - <span data-ttu-id="e987f-108">\*\*\*\*   조직의 사용자에 게 방화벽 외부에서 작업 중 이며 해당 랩톱이 나 다른 Lync Server 장치를 사용 하는 경우 원격 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-108">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="e987f-109">\*\*\*\*   사용자가 Lync Server를 실행 하는 회사의 페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="e987f-109">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="e987f-110">사용자가 이러한 사용자에 게 쉽게 연락할 수 있도록 이러한 회사와의 페더레이션 관계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-110">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="e987f-111">\*\*\*\*   인터넷 서비스, Yahoo\!및 AOL의 Windows Live 네트워크에서 제공 하는 im 서비스와 같은 공용 im 서비스 사용자, 그리고 Google 대화 등의 xmpp (확장 가능 메시지 및 현재 상태 프로토콜)를 사용 하는 공급자 및 서버의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-111">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e987f-112">Windows Live, AOL 및 Yahoo!와의 공용 IM 연결에 별도의 라이선스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-112">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="e987f-113">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-113">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="e987f-114">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-114">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="e987f-115">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-115">Messenger until the service shut down date.</span></span> <span data-ttu-id="e987f-116">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="e987f-116">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="e987f-117">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-117">has been announced.</span></span> <span data-ttu-id="e987f-118">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e987f-118">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e987f-119">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-119">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="e987f-120">받으려면.</span><span class="sxs-lookup"><span data-stu-id="e987f-120">Messenger.</span></span> <span data-ttu-id="e987f-121">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-121">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e987f-122">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-122">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e987f-123">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-123">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="e987f-124">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-124">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="e987f-125">이러한 시나리오 중 하나 또는 모두를 사용 하도록 설정 하려면 사용자의 Lync Server 배포와 외부 사용자 간의 보안 통신을 사용 하도록 지원 하기 위해 Edge 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-125">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="e987f-126">조직의 원격 사용자 및 페더레이션된 조직의 사용자는 서로의 현재 상태를 확인 하 고 IM을 사용 하 여 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-126">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="e987f-127">외부 사용자와 통신을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 외부 사용자 액세스 계획 수립](lync-server-2013-planning-for-external-user-access.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e987f-127">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="e987f-128">IM 콘텐츠 보관</span><span class="sxs-lookup"><span data-stu-id="e987f-128">Archiving IM Content</span></span>

<span data-ttu-id="e987f-129">Lync Server는 조직이 규정 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-129">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="e987f-130">보관을 사용 하 여 조직의 모든 사용자 또는 지정 된 특정 사용자에 대 한 IM 메시지의 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-130">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="e987f-131">자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e987f-131">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="e987f-132">Microsoft Exchange Server 2013을 배포한 경우에는 Lync Server 데이터 보관을 사용 하 여 Exchange 데이터 보관을 통합 하 고 단일 도구를 사용 하 여 보관 된 데이터의 두 가지 유형을 모두 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e987f-132">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="e987f-133">자세한 내용은 [Microsoft Exchange server 2013 보관을 사용 하도록 Microsoft Lync Server 2013 구성을](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e987f-133">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

