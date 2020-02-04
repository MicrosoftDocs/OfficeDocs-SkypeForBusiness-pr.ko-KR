---
title: Lync Server 2013 메신저 및 현재 상태
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f57d4fae488a7d4946a0adb1f8350d02114a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a><span data-ttu-id="8d68a-102">Lync Server 2013의 메신저 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="8d68a-102">IM and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d68a-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8d68a-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="8d68a-104">인스턴트 메시지 (IM) 및 현재 상태는 Lync Server 배포에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-104">Instant messaging (IM) and presence are automatically installed in any Lync Server deployment.</span></span>

<span data-ttu-id="8d68a-105">*현재 상태* 정보를 통해 사용자는 올바른 형태의 통신을 사용 하 여 적절 한 시간에 동료에 게 접근 하 여 생산성 높은 작업 환경을 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-105">*Presence* information enables users to approach colleagues at the right time with the right form of communication, to lead to a more productive work environment.</span></span> <span data-ttu-id="8d68a-106">사용자의 현재 상태는 가용성, 통신 willingness, 추가 메모 (위치 및 상태), 사용자에 게 연락할 수 있는 방법 등을 포함 하는 정보의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-106">A user’s presence is a collection of information that includes availability, willingness to communicate, additional notes (such as location and status), and how the user can be contacted.</span></span> <span data-ttu-id="8d68a-107">Lync Server에서 사진, 위치 정보 및 "사용 중지"가 포함 된 다양 한 현재 상태와 "약속 있음/없음", "다른 용무 중"과 같은 기본 상태 외에 "제공" 및 "진행 중</span><span class="sxs-lookup"><span data-stu-id="8d68a-107">Presence is enhanced in Lync Server with pictures, location information, and a rich set of presence states that includes “Off Work,” “Do Not Disturb,” and “Be Right Back,” in addition to basic states such as “Available,” “Busy,” and “In a Conference.”</span></span> <span data-ttu-id="8d68a-108">관리자는 사용자 지정 된 조직의 특정 현재 상태를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-108">Administrators can also define customized, organization-specific presence states.</span></span>

<span data-ttu-id="8d68a-109">연락처 관리 및 사용자 액세스 옵션을 사용 하 여 다른 사용자가 볼 수 있는 정보를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-109">Contact management and user access options enable users to control what information others can see.</span></span> <span data-ttu-id="8d68a-110">사용자는 각각 다른 수준의 현재 상태 정보를 볼 수 있는 다양 한 수준의 연락처를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-110">Users can set different levels of contacts, each of which can view different levels of presence information.</span></span>

<span data-ttu-id="8d68a-111">연락처 목록을 보면 사용자가 쉽게 알아야 할 모든 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-111">By simply looking at a Contacts list, users can find everything they need to know at a glance.</span></span> <span data-ttu-id="8d68a-112">간단한 색 아이콘은 다른 사용자의 현재 상태를 나타내고 그림 및 위치도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-112">Simple colored icons indicate other users’ presence status, and picture and location are also shown.</span></span>

<span data-ttu-id="8d68a-113">Lync Server와 Outlook 및 SharePoint 등의 다른 제품을 통합 하면 전자 메일 메시지 또는 팀 웹 사이트 등의 대화 상대 이름이 나타날 때마다 상태 및 연락처 정보도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-113">With the integration between Lync Server and other products such as Outlook and SharePoint, whenever a contact’s name appears, such as in an email message or on a team website, the status and contact information is also displayed.</span></span> <span data-ttu-id="8d68a-114">또한 Exchange 2013를 배포 하는 경우 Lync Server와 Exchange 2013는 두 제품 중 하나의 클라이언트에서 액세스할 수 있는 통일 된 연락처 저장소를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-114">Additionally, if you deploy Exchange 2013, Lync Server and Exchange 2013 can share a unified contact store, which can be accessed by clients of either product.</span></span>

<span data-ttu-id="8d68a-115">Lync Server에 인스턴트 메시지를 사용 하면 사용자가 신속 하 게 정보를 주고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-115">With instant messaging in Lync Server, users can quickly message each other with timely information.</span></span> <span data-ttu-id="8d68a-116">원하는 경우 사용자는 MSN/Windows Live, Yahoo\!, AOL 등의 공용 인스턴트 메시징 네트워크 사용자와 통신할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-116">If you prefer, your users can also communicate with users of public IM networks such as MSN/Windows Live, Yahoo\!, and AOL.</span></span> <span data-ttu-id="8d68a-117">Windows Live, AOL 및 Yahoo와의 공용 IM 연결에 별도의 라이선스가 필요할 수 있습니다.\!</span><span class="sxs-lookup"><span data-stu-id="8d68a-117">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo\!</span></span> <span data-ttu-id="8d68a-118">또한 Lync Server에는 XMPP (확장 가능 메시지 및 현재 상태 프로토콜) 호환성이 포함 되므로 사용자는 Google 대화 등의 XMPP 서비스 사용자와 IM 메시지 및 현재 상태 정보를 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-118">Lync Server also includes Extensible Messaging and Presence Protocol (XMPP) compatibility, so your users can exchange IM messages and presence information with users of XMPP services such as Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="8d68a-119">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-119">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="8d68a-120">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-120">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8d68a-121">서비스 종료 날짜가 될 때까지 메신저를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-121">Messenger until the service shut down date.</span></span> <span data-ttu-id="8d68a-122">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="8d68a-122">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8d68a-123">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-123">has been announced.</span></span> <span data-ttu-id="8d68a-124">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d68a-124">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="8d68a-125">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-125">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8d68a-126">받으려면.</span><span class="sxs-lookup"><span data-stu-id="8d68a-126">Messenger.</span></span> <span data-ttu-id="8d68a-127">이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-127">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="8d68a-128">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-128">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8d68a-129">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-129">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8d68a-130">Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-130">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="8d68a-131">사용자는 대화 기록을 사용 하 여 이전 메신저 대화를 추적 하 고 IM 달 전에 통신을 할 수 있는 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-131">Conversation history enables users to keep track of old IM conversations, and retrieve information that may have been communicated by IM months ago.</span></span>

<span data-ttu-id="8d68a-132">영구 채팅 기능을 통해 사용자는 시간에 따라 유지 되는 단체의 항목 기반 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-132">The Persistent Chat feature enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="8d68a-133">채팅방에 게시 된 메시지 (토론 포럼)는 지속적 (즉, 시간이 지남에 따라 가능) 할 수 있으므로, 동시에 온라인 상태가 아닌 경우에도 다른 위치와 부서의 사용자가 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-133">Messages posted to chat rooms (discussion forums) can be persistent (that is, available over time), so that people from different locations and departments can participate, even when they are not all online at the same time.</span></span>

<span data-ttu-id="8d68a-134">조직이 준수 규정을 따라야 하는 경우에는 메시지 보관 기능을 배포 하 여 조직의 모든 사용자 또는 지정 된 특정 사용자에 대 한 인스턴트 메시지의 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-134">If your organization must follow compliance regulations, you can deploy a message archiving feature to archive the content of instant messages for all users in your organization, or for only certain users you specify.</span></span> <span data-ttu-id="8d68a-135">또한 Exchange 2013를 배포 하는 경우, 사용자의 승인에 대 한 단일 관리 환경을 제공 하기 위해 메신저 보관 함이 Exchange의 원본 위치 유지 기능과 통합 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d68a-135">If you also deploy Exchange 2013, your IM archive can be integrated with the In-Place Hold feature of Exchange, to provide a single administration experience for your compliance.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

