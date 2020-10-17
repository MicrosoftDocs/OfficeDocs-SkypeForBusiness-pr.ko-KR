---
title: 'Lync Server 2013: 공용 인스턴트 메시징 지원'
description: 'Lync Server 2013: 공용 인스턴트 메시징 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public instant messaging support
ms:assetid: 1f45163b-52c6-4a78-b9c8-dfe3abe4e5eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204732(v=OCS.15)
ms:contentKeyID: 48183582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e071e8b79be82d865a85a9488e48dd0a4264c7f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565574"
---
# <a name="public-instant-messaging-support-in-lync-server-2013"></a><span data-ttu-id="d76f1-103">Lync Server 2013의 공용 인스턴트 메시징 지원</span><span class="sxs-lookup"><span data-stu-id="d76f1-103">Public instant messaging support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d76f1-104">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="d76f1-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="d76f1-105">Lync Server 2013에서는 lync 2013 클라이언트를 사용 하 여 Lync Server가 구성 된 XMPP 도메인 파트너에 액세스할 수 있게 해 주는 특수 한 유형의 페더레이션을 구현 하는 데 사용 되는 공용 IM (인스턴트 메시징) 연결 공급자의 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-105">Lync Server 2013 supports the use of licensed public instant messaging (IM) connectivity providers, as well as the use of eXtensible Messaging and Presence Protocol (XMPP) to implement a special type of federation that enables a Lync Server to access configured XMPP domain partners by using the Lync 2013 client.</span></span>

<div>

## <a name="public-im-connectivity-provider-support"></a><span data-ttu-id="d76f1-106">공용 IM 연결 공급자 지원</span><span class="sxs-lookup"><span data-stu-id="d76f1-106">Public IM Connectivity Provider Support</span></span>

<span data-ttu-id="d76f1-107">현재 지원되는 공용 인스턴트 메시징 연결 파트너는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-107">The currently supported public instant messaging connectivity partners are:</span></span>

  - <span data-ttu-id="d76f1-108">America Online</span><span class="sxs-lookup"><span data-stu-id="d76f1-108">America Online</span></span>

  - <span data-ttu-id="d76f1-109">Windows Live</span><span class="sxs-lookup"><span data-stu-id="d76f1-109">Windows Live</span></span>

  - <span data-ttu-id="d76f1-110">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="d76f1-110">Yahoo\!</span></span>

<span data-ttu-id="d76f1-111">Windows Live 사용자와 통신 하는 경우 Lync Server 2013는 피어 투 피어 IM 및 오디오 및 비디오 통화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-111">For communications with Windows Live users, Lync Server 2013 supports peer-to-peer IM and audio and video calls.</span></span> <span data-ttu-id="d76f1-112">AOL 및 Yahoo와의 통신의 경우 \! Lync Server 2013는 피어 투 피어 IM을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-112">For communications with AOL and Yahoo\!, Lync Server 2013 supports peer-to-peer IM.</span></span> <span data-ttu-id="d76f1-113">별도의 라이선스가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-113">A separate license may be required.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d76f1-114">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d76f1-115">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d76f1-116">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="d76f1-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="d76f1-117">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="d76f1-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d76f1-118">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-118">has been announced.</span></span> <span data-ttu-id="d76f1-119">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d76f1-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d76f1-120">PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d76f1-121">메신저로.</span><span class="sxs-lookup"><span data-stu-id="d76f1-121">Messenger.</span></span> <span data-ttu-id="d76f1-122">이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="d76f1-123">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d76f1-124">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d76f1-125">Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d76f1-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="xmpp-federation-support"></a><span data-ttu-id="d76f1-126">XMPP 페더레이션 지원</span><span class="sxs-lookup"><span data-stu-id="d76f1-126">XMPP Federation Support</span></span>

<span data-ttu-id="d76f1-p105">XMPP 페더레이션은 GTalk 등의 공용 공급자를 사용하는 구성된 XMPP 도메인 사용자와 Lync 사용자의 통신을 지원합니다. 이러한 사용자와의 통신</span><span class="sxs-lookup"><span data-stu-id="d76f1-p105">XMPP federation supports Lync users communication with configured XMPP domain users who use a public provider, such as GTalk. Communications with these users can include the following:</span></span>

  - <span data-ttu-id="d76f1-129">피어 투 피어 IM 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="d76f1-129">Peer-to-peer IM and presence</span></span>

  - <span data-ttu-id="d76f1-130">Lync 클라이언트에서 XMPP 페더레이션 대화 상대 만들기</span><span class="sxs-lookup"><span data-stu-id="d76f1-130">Creation of XMPP federated contacts in the Lync client</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

