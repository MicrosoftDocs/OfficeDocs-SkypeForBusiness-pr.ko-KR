---
title: 'Lync Server 2013: 응급 서비스 계획(E9-1-1)'
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
ms.openlocfilehash: 11c6116cc3ad63674acd65e7d2de863e7911bcf8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-emergency-services-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="6ee90-102">Lync Server 2013의 응급 서비스 계획(E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="6ee90-102">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ee90-103">_**마지막으로 수정한 주제:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="6ee90-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="6ee90-104">Lync Server 2013는 엔터프라이즈 음성 배포의 일부로 미국 내에서 향상 된 9-1-1 (E9-1) 서비스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ee90-104">Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) services within the United States as part of an Enterprise Voice deployment.</span></span> <span data-ttu-id="6ee90-105">E9-1-1은 9-1-1 통화를 ERL (비상 응답 위치)에 연결 하는 긴급 파견 기능으로, 사무실 건물의 통화에 대 한 도심 (즉, 거리) 주소와 기타 특정 위치 정보 (예: 바닥 번호)로 구성 됩니다. 기타 다중 테 넌 트 시설.</span><span class="sxs-lookup"><span data-stu-id="6ee90-105">E9-1-1 is an emergency dispatch feature that associates a 9-1-1 call with an Emergency Response Location (ERL) that consists of civic (that is, street) addresses and other more specific location information, such as floor numbers, for calls from office buildings and other multitenant facilities.</span></span> <span data-ttu-id="6ee90-106">제공 된 ERL를 사용 하 여 공개 안전 응답 시점 (PSAP)은 이용해에서 호출자에 대 한 첫 번째 응답자를 즉시 발송 하 여 잘못 된 위치 또는 모호한 위치로 응답을 보내는 위험을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ee90-106">By using the provided ERL, a Public Safety Answering Point (PSAP) can immediately dispatch first responders to the caller in distress with reduced risk of inadvertently directing the responder to an incorrect or ambiguous location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ee90-107">Lync Server에는 세 가지 고급 엔터프라이즈 음성 기능 (통화 허용 제어, 응급 서비스 (E9-1-1), 미디어 바이패스)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ee90-107">Lync Server has three advanced Enterprise Voice features: call admission control, emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="6ee90-108">이러한 세 가지 기능에 모두 공통적으로 제공 되는 계획 정보에 대 한 개요는 <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ee90-108">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6ee90-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6ee90-109">In This Section</span></span>

  - [<span data-ttu-id="6ee90-110">Lync Server 2013의 E9-1-1 개요</span><span class="sxs-lookup"><span data-stu-id="6ee90-110">Overview of E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-overview-of-e9-1-1.md)

  - [<span data-ttu-id="6ee90-111">Lync Server 2013에서 응급 전화에 대한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="6ee90-111">Defining your requirements for emergency calls in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-emergency-calls.md)

  - [<span data-ttu-id="6ee90-112">Lync Server 2013의 E9-1-1에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="6ee90-112">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-e9-1-1.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

