---
title: 'Lync Server 2013: PSTN 연결 계획'
description: 'Lync Server 2013: PSTN 연결을 계획 합니다.'
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
ms.openlocfilehash: 45c0df6aa6dc9d9cc8522223056f1834849e6ddb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549324"
---
# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="47165-103">Lync Server 2013의 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="47165-103">Planning for PSTN connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47165-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="47165-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="47165-105">엔터프라이즈급 VoIP 솔루션은 QoS (서비스 품질)를 제외 하 고는 PSTN (공중 전화망)에 대 한 통화를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47165-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="47165-106">전화를 걸고 받는 사용자는 기본 기술에 대해 알 수 없습니다. 사용자의 관점에서 보면 기업 음성 인프라와 PSTN 간의 통화는 다른 전화 통화 처럼 보일 것으로 생각 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47165-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="47165-107">Lync Server 2013에서는 다음 옵션을 사용 하 여 안정적이 고 확장 가능한 PSTN 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47165-107">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="47165-108">ITSP(인터넷 전화 통신 서비스 공급자)에 대한 **SIP 트렁크**</span><span class="sxs-lookup"><span data-stu-id="47165-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="47165-109">PSTN 게이트웨이에 대한 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="47165-109">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="47165-110">PBX에 대한 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="47165-110">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="47165-111">크기, 포함 지역 및 기존 음성 인프라에 따라 엔터프라이즈는 여러 위치에서 위의 옵션 중 하나 또는 두 개를 사용할 수도 있고 세 옵션을 모두 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47165-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47165-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="47165-112">In This Section</span></span>

  - [<span data-ttu-id="47165-113">Lync Server 2013의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="47165-113">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="47165-114">Lync Server 2013의 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="47165-114">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="47165-115">Lync Server 2013의 M:N 트렁크</span><span class="sxs-lookup"><span data-stu-id="47165-115">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="47165-116">Lync Server 2013의 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="47165-116">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="47165-117">Lync Server 2013의 아웃 바운드 음성 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="47165-117">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

