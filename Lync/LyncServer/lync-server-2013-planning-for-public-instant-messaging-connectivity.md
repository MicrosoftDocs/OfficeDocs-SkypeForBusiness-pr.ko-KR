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
ms.openlocfilehash: 52bc8a563a45e75b01932ee716df90f1cf2ca7da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="b89ba-102">Lync Server 2013의 공용 인스턴트 메시징 연결 계획</span><span class="sxs-lookup"><span data-stu-id="b89ba-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b89ba-103">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b89ba-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b89ba-104">공용 인스턴트 메시징 연결은 페더레이션 클래스 이며 내부 및 외부 Lync Server 2013 사용자가 다음 중 하나에서 연락처를 추가할 수 있도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="b89ba-105">메신저 대화 상대</span><span class="sxs-lookup"><span data-stu-id="b89ba-105">Messenger contacts</span></span>

  - <span data-ttu-id="b89ba-106">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="b89ba-106">Yahoo\!</span></span> <span data-ttu-id="b89ba-107">연락처만</span><span class="sxs-lookup"><span data-stu-id="b89ba-107">contacts</span></span>

  - <span data-ttu-id="b89ba-108">북아메리카 온라인 (AOL) 연락처</span><span class="sxs-lookup"><span data-stu-id="b89ba-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="b89ba-109">2012 년 9 월 1 일부 터 신규 또는 갱신 계약에 대 한 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="b89ba-110">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b89ba-111">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="b89ba-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="b89ba-112">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="b89ba-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b89ba-113">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-113">has been announced.</span></span> <span data-ttu-id="b89ba-114">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b89ba-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="b89ba-115">PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!과 페더레이션 하는 데 필요한 사용자별 구독 라이선스 (매달)입니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b89ba-116">메신저로.</span><span class="sxs-lookup"><span data-stu-id="b89ba-116">Messenger.</span></span> <span data-ttu-id="b89ba-117">이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="b89ba-118">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b89ba-119">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b89ba-120">Lync 사용자가 IM 및 음성을 통해 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="b89ba-121">이 페더레이션 클래스를 사용 하려면 다음과 같은 계획 고려 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="b89ba-122">Windows Live Messenger 사용자는 인스턴트 메시징과 함께 Lync Server 2013 사용자와 피어 투 피어 오디오/시각적 통신을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="b89ba-123">에 지 서버는 특정 포트 및 프로토콜 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="b89ba-124">자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b89ba-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="b89ba-125">Yahoo 인스턴트 메시징의 경우에는 페더레이션을 제공 하는 일반에 지 서버를 계획 및 배포 하는 데 주로 사용 되는 것과는 다른 고유한 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="b89ba-126">아메리카 온라인에서 액세스에 지 서비스에 할당 된에 지 서버 인증서에는 클라이언트 EKU (확장 된 키 사용)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b89ba-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b89ba-127">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b89ba-127">In This Section</span></span>

  - [<span data-ttu-id="b89ba-128">인증서 요약-Lync Server 2013의 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="b89ba-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="b89ba-129">포트 요약-Lync Server 2013의 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="b89ba-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="b89ba-130">[Lync Server 2013의 DNS 요약-공용 인스턴트 메시징 연결](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b89ba-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

