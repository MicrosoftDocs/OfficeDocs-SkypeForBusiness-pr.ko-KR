---
title: 'Lync Server 2013: 응급 서비스 계획 (E9-1-1)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for emergency services (E9-1-1)
ms:assetid: 0a76f97b-474a-4bc1-8cd3-28c7e2bb57b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398154(v=OCS.15)
ms:contentKeyID: 48183363
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c642fefb7fcaf17422bc292f3ed56516ede206bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-emergency-services-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="b690a-102">Lync Server 2013의 응급 서비스 계획 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="b690a-102">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b690a-103">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="b690a-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="b690a-104">Lync Server 2013는 Enterprise Voice 배포의 일부로 미국 내에서 E9-1-1 (고급 9-1-1) 서비스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b690a-104">Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) services within the United States as part of an Enterprise Voice deployment.</span></span> <span data-ttu-id="b690a-105">E9-1-1은 구/군/시 주소와 더 구체적인 기타 위치 정보(예: 사무실 건물 및 다가구 시설에서 거는 전화의 경우 층 번호)로 구성되는 ERL(Emergency Response Location)과 9-1-1 전화를 연결하는 응급 발송 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b690a-105">E9-1-1 is an emergency dispatch feature that associates a 9-1-1 call with an Emergency Response Location (ERL) that consists of civic (that is, street) addresses and other more specific location information, such as floor numbers, for calls from office buildings and other multitenant facilities.</span></span> <span data-ttu-id="b690a-106">PSAP(Public Safety Answering Point)는 제공된 ERL을 사용하여 응급 상황에 처한 발신자에게 최초 대응 인원을 즉시 파견할 수 있으며, 모호하거나 잘못된 위치로 대응 인원을 실수로 파견할 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b690a-106">By using the provided ERL, a Public Safety Answering Point (PSAP) can immediately dispatch first responders to the caller in distress with reduced risk of inadvertently directing the responder to an incorrect or ambiguous location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b690a-107">Lync Server에는 세 가지 고급 Enterprise Voice 기능인 통화 허용 제어, 응급 서비스 (E9-1-1) 및 미디어 바이패스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b690a-107">Lync Server has three advanced Enterprise Voice features: call admission control, emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="b690a-108">이러한 세 가지 기능에 공통적으로 제공 되는 계획 정보에 대 한 개요는 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013의 Advanced Enterprise Voice 기능에 대 한 네트워크 설정을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b690a-108">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b690a-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b690a-109">In This Section</span></span>

  - [<span data-ttu-id="b690a-110">Lync Server 2013의 E9-1-1 개요</span><span class="sxs-lookup"><span data-stu-id="b690a-110">Overview of E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-overview-of-e9-1-1.md)

  - [<span data-ttu-id="b690a-111">Lync Server 2013의 응급 전화에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="b690a-111">Defining your requirements for emergency calls in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-emergency-calls.md)

  - [<span data-ttu-id="b690a-112">Lync Server 2013의 E9-1-1에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="b690a-112">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-e9-1-1.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

