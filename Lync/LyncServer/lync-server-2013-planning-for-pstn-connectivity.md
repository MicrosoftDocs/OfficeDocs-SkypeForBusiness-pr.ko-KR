---
title: 'Lync Server 2013: PSTN 연결 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec12aa5e579aed30e61c7cd34eab444e807c628f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="c3735-102">Lync Server 2013의 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="c3735-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3735-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c3735-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c3735-104">엔터프라이즈급 VoIP 솔루션은 서비스 품질 (QoS)에 동의 하지 않고 PSTN (공공 교환 전화 네트워크)에 대 한 통화를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3735-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="c3735-105">전화를 걸고 받는 사용자는 기본 기술을 인식 하지 못합니다. 사용자 관점에서 보면 엔터프라이즈 음성 인프라와 PSTN 간의 통화는 다른 전화 통화 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3735-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="c3735-106">Lync Server 2013는 다음 옵션을 사용 하 여 안정적이 고 확장 가능한 PSTN 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3735-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="c3735-107">**SIP Trunks** 인터넷 통신 서비스 공급자 (itsp)</span><span class="sxs-lookup"><span data-stu-id="c3735-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="c3735-108">PSTN 게이트웨이에 대 한 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="c3735-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="c3735-109">PBX로 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="c3735-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="c3735-110">해당 크기, 지역 및 기존 음성 인프라에 따라 엔터프라이즈는 다양 한 위치에서 하나, 두 가지 또는 세 가지 옵션을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3735-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3735-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="c3735-111">In This Section</span></span>

  - [<span data-ttu-id="c3735-112">Lync Server 2013의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="c3735-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="c3735-113">Lync Server 2013에서 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="c3735-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="c3735-114">M:N-Lync Server 2013의 트렁크</span><span class="sxs-lookup"><span data-stu-id="c3735-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="c3735-115">Lync Server 2013의 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="c3735-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="c3735-116">Lync Server 2013에서 아웃바운드 음성 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="c3735-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

