---
title: 'Lync Server 2013: 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 요구 사항 정의'
description: 'Lync Server 2013: 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 요구 사항을 정의 합니다.'
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
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545374"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="f7a2b-103">Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="f7a2b-103">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a2b-104">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f7a2b-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f7a2b-105">IM(인스턴트 메시징) 및 현재 상태를 계획하는 데 수행되는 작업 중 주요 작업은 사용자를 위해 충분한 프런트 엔드 서버를 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-105">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="f7a2b-106">외부 사용자와 통신 사용</span><span class="sxs-lookup"><span data-stu-id="f7a2b-106">Enabling Communication with External Users</span></span>

<span data-ttu-id="f7a2b-107">사용자가 외부 사용자와 정보를 교환할 수 있도록 하 여 Lync Server에 대 한 투자의 이점을 대폭 증대 시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-107">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="f7a2b-108">외부 사용자에는 다음이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-108">External users can include:</span></span>

  - <span data-ttu-id="f7a2b-109">**원격 사용자**     조직의 사용자가 방화벽 외부에서 작업 중 이며 해당 랩톱이 나 기타 Lync Server 장치를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="f7a2b-109">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="f7a2b-110">**페더레이션 사용자**     회사의 사용자는 Lync Server를 실행 하는 사람과 함께 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-110">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="f7a2b-111">조직의 사용자가 이러한 사용자에게 쉽게 연결할 수 있도록 하려면 이러한 회사와 페더레이션 관계를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-111">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="f7a2b-112">**공개 사용자**     Internet services, Yahoo 및 AOL의 Windows Live 네트워크에서 제공 하는 IM 서비스와 같은 공용 IM 서비스 사용자 \! 및 Google 대화 기능과 같은 XMPP (Extensible Messaging And 현재 상태 프로토콜)를 사용 하는 공급자 및 서버 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-112">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7a2b-113">Windows Live, AOL, Yahoo! 등의 공용 IM 연결에는 별도의 라이선스가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-113">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f7a2b-114">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f7a2b-115">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f7a2b-116">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="f7a2b-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="f7a2b-117">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="f7a2b-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f7a2b-118">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-118">has been announced.</span></span> <span data-ttu-id="f7a2b-119">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f7a2b-120">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f7a2b-121">메신저로.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-121">Messenger.</span></span> <span data-ttu-id="f7a2b-122">이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f7a2b-123">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f7a2b-124">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f7a2b-125">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="f7a2b-126">이러한 시나리오를 일부 또는 모두 사용 하도록 설정 하려면 Lync Server 배포와 외부 사용자 간의 보안 통신을 사용 하도록 설정 하는 데 도움이 되는에 지 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-126">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="f7a2b-127">조직의 원격 사용자와 페더레이션 조직의 사용자는 IM을 사용하여 서로의 현재 상태를 확인하고 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-127">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="f7a2b-128">외부 사용자와의 통신을 사용 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-128">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="f7a2b-129">IM 콘텐츠 보관</span><span class="sxs-lookup"><span data-stu-id="f7a2b-129">Archiving IM Content</span></span>

<span data-ttu-id="f7a2b-130">Lync Server에서는 조직이 규정 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-130">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="f7a2b-131">보관을 사용 하 여 조직의 모든 사용자 또는 지정한 특정 사용자에 대 한 IM 메시지의 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-131">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="f7a2b-132">자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-132">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="f7a2b-133">Microsoft Exchange Server 2013도 배포 된 경우에는 Exchange 데이터 보관을 Lync Server 데이터 보관 기능과 통합 하 고 단일 도구를 사용 하 여 두 가지 유형의 보관 데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-133">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="f7a2b-134">자세한 내용은 microsoft [Exchange server 2013 보관을 사용 하도록 Microsoft Lync Server 2013 구성을](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7a2b-134">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

