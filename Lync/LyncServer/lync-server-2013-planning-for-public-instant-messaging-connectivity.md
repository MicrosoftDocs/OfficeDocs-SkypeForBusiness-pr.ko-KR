---
title: 'Lync Server 2013: 공용 인스턴트 메시징 연결 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7885d17e708f2073006131862f06d93d9057fb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="fb909-102">Lync Server 2013에서 공용 인스턴트 메시징 연결 계획</span><span class="sxs-lookup"><span data-stu-id="fb909-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb909-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="fb909-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="fb909-104">공용 인스턴트 메시징 연결은 페더레이션 클래스 이며, 내부 및 외부 Lync Server 2013 사용자가 다음 중 한 곳에서 연락처를 추가할 수 있도록 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="fb909-105">Messenger 연락처</span><span class="sxs-lookup"><span data-stu-id="fb909-105">Messenger contacts</span></span>

  - <span data-ttu-id="fb909-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="fb909-106">Yahoo\!</span></span> <span data-ttu-id="fb909-107">상대가</span><span class="sxs-lookup"><span data-stu-id="fb909-107">contacts</span></span>

  - <span data-ttu-id="fb909-108">아메리카 온라인 (AOL) 연락처</span><span class="sxs-lookup"><span data-stu-id="fb909-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="fb909-109">2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)는 더 이상 신규 또는 갱신 계약을 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="fb909-110">활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="fb909-111">서비스 종료 날짜까지 Messenger.</span><span class="sxs-lookup"><span data-stu-id="fb909-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="fb909-112">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="fb909-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="fb909-113">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-113">has been announced.</span></span> <span data-ttu-id="fb909-114">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fb909-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="fb909-115">PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!에 페더레이션 하는 데 필요한 사용자별, 월별 구독 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="fb909-116">받으려면.</span><span class="sxs-lookup"><span data-stu-id="fb909-116">Messenger.</span></span> <span data-ttu-id="fb909-117">이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!의 지원으로 부과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="fb909-118">이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="fb909-119">Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="fb909-120">Skype 페더레이션은이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 통해 수백만 명에 게 연락할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="fb909-121">이 페더레이션 클래스에는 다음과 같은 계획 고려 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="fb909-122">Windows Live Messenger 사용자는 인스턴트 메시지 외에도 Lync Server 2013 사용자와 피어 투 피어 오디오/시각적 통신을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="fb909-123">Edge 서버는 특정 포트 및 프로토콜 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="fb909-124">자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항을 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="fb909-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="fb909-125">Yahoo 인스턴트 메시징에는 페더레이션을 제공 하는 일반 Edge 서버의 계획 및 배포에 일반적으로 사용 되는 것이 아닌 고유한 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="fb909-126">아메리카 온라인에서 액세스에 지 서비스에 할당 된 Edge 서버 인증서에는 EKU (클라이언트 확장 키 사용)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb909-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb909-127">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fb909-127">In This Section</span></span>

  - [<span data-ttu-id="fb909-128">인증서 요약-Lync Server 2013의 공개 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="fb909-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="fb909-129">포트 요약-Lync Server 2013의 공개 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="fb909-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="fb909-130">[DNS 요약-Lync Server 2013의 공개 인스턴트 메시지 연결](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fb909-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

