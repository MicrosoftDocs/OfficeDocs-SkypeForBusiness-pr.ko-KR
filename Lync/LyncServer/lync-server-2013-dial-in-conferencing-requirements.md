---
title: Lync Server 2013 전화 접속 회의 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="940be-102">Lync Server 2013의 전화 접속 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="940be-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="940be-103">_**마지막으로 수정한 주제:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="940be-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="940be-104">Lync Server 2013 배포 프로세스를 시작 하기 전에 다음을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="940be-105">PSTN (공개 교환 전화 네트워크)에 연결 하는 데 사용할 구성</span><span class="sxs-lookup"><span data-stu-id="940be-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="940be-106">전화 접속 로그인 회의 영역을 전화 접속 액세스 번호에 배정 하는 전략</span><span class="sxs-lookup"><span data-stu-id="940be-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="940be-107">회의 디렉터리 만들기 전략</span><span class="sxs-lookup"><span data-stu-id="940be-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="940be-108">전화 접속 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="940be-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="940be-109">전화 접속 회의에는 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="940be-110">중앙 사이트 또는 지점 사이트에 중재 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="940be-111">중앙 사이트에서는 프런트 엔드 풀 또는 스탠더드 버전 서버에서 중재 서버를 collocate 하거나 독립 실행형 서버 또는 풀에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="940be-112">지점 사이트에서는 독립 실행형 서버나 Survivable Branch 기기의 구성 요소로 중재 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="940be-113">중앙 사이트 또는 지점 사이트에 PSTN 게이트웨이를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="940be-114">지점 사이트에서 PSTN 게이트웨이는 독립형 또는 Survivable Branch 기기의 구성 요소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="940be-115">A/V 회의 서버는 미디어 바이패스를 지원 하지 않으므로 전화 접속 회의는 미디어 바이패스를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="940be-116">중재 서버 및 전화 접속 회의를 위한 PSTN 게이트웨이의 구성을 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버용 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="940be-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="940be-117">전화 접속 회의 지역 계획</span><span class="sxs-lookup"><span data-stu-id="940be-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="940be-118">전화 접속 구성 중에 다이얼 플랜 및 전화 접속 회의 액세스 번호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="940be-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="940be-119">다이얼 플랜은 전화 번호의 숫자와 패턴을 지정 하 고 전화 번호를 표준 전자 164 형식으로 변환 하는 정규화 규칙 집합으로, 통화 라우팅을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="940be-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="940be-120">전화 접속 회의 액세스 번호는 참가자가 전화 회의에 참가 하기 위해 전화를 거는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="940be-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="940be-121">모든 전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="940be-122">전화 접속 회의 지역에서는 전화 접속 회의 액세스 번호와 다이얼 플랜을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="940be-123">다이얼 플랜을 설정할 때 다이얼 플랜에 적용 되는 전화 접속 회의 영역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="940be-124">전화 접속 액세스 번호를 만들 때 적절 한 다이얼 플랜에 액세스 번호를 연결 하는 지역을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="940be-125">다이얼 플랜을 만들 때 사용자 범위, 풀 범위 또는 사이트 범위 등 다이얼 플랜의 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="940be-126">모든 사용자는 사용자에 게 적용 되는 가장 좁은 범위에서 다이얼 플랜을 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="940be-127">예를 들어 사용자에 게 적용 되는 경우 사용자 수준 다이얼 플랜을 할당 받습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="940be-128">사용자 수준 다이얼 플랜이 적용 되지 않으면 사용자에 게 풀 수준 다이얼 플랜을 할당 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="940be-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="940be-129">풀 수준 다이얼 플랜이 적용 되지 않으면 사용자에 게 사이트 수준 다이얼 플랜을 할당 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="940be-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="940be-130">사이트 수준 다이얼 플랜이 적용 되지 않으면 사용자에 게 전역 다이얼 플랜을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="940be-131">다이얼 플랜을 구성 하기 전에 지역을 이름 및 사용 하는 방법을 계획 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-131">Before you configure the dial plans, is it important to plan how you want to name and use regions.</span></span> <span data-ttu-id="940be-132">전화 접속 회의 지역에는 다음 고려 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="940be-132">The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="940be-133">영역은 일반적으로 office 또는 사무실 그룹과 연결 된 지리적 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="940be-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="940be-134">언어는 전화 접속 액세스 번호와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="940be-134">Languages are associated with dial-in access numbers.</span></span> <span data-ttu-id="940be-135">여러 언어를 사용 하는 지리 영역을 지 원하는 경우 여러 언어를 지 원하는 지역을 정의 하는 방법을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-135">If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages.</span></span> <span data-ttu-id="940be-136">예를 들어 지역 및 언어의 조합에 따라 여러 지역을 정의 하거나, 지리를 기준으로 단일 지역을 정의 하 고 각 언어에 대 한 다른 전화 접속 액세스 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-136">For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="940be-137">사용자가 모임을 예약 하면 기본적으로 해당 사용자의 다이얼 플랜에 지정 된 영역이 모임에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="940be-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="940be-138">기본적으로 해당 지역의 모든 전화 접속 액세스 번호는 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="940be-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="940be-139">분명 하 게 인식할 수 있도록 지역 이름을 구분 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="940be-140">사용자는 다른 액세스 번호가 초대에 포함 되도록 지역 이름을 사용 하 여 모임 지역을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="940be-141">사용자가 Outlook을 사용 하 여 모임을 예약할 때 사용자는 Lync 2013의 온라인 모임 추가 기능을 사용 하 여 지역을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="940be-142">전화를 걸고 싶어 하는 모든 초대 대 상자가 회의 초대에서 로컬 액세스 번호를 볼 수 있도록 지역을 디자인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="940be-143">Lync Server 관리 셸 cmdlet을 사용 하 여 전화 접속 회의 설정 페이지에 있는 지역 내의 액세스 번호가 표시 되는 순서를 구성할 수 있습니다 (즉, 회의 초대에 표시 되는 순서).</span><span class="sxs-lookup"><span data-stu-id="940be-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="940be-144">모든 위치의 사용자는 전화 접속 액세스 번호를 호출 하 여 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="940be-145">컨퍼런스 디렉터리 계획</span><span class="sxs-lookup"><span data-stu-id="940be-145">Planning for Conference Directories</span></span>

<span data-ttu-id="940be-146">회의 디렉터리는 참가자가 Lync 2013을 사용할 때 회의에 참가 하는 데 사용 하는 영숫자 모임 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="940be-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="940be-147">전화 회의 ID의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="940be-148">여러 회의 디렉터리를 만들면 회의 Id가 매우 많은 회의를 만들 때까지 짧은 시간 동안 유지 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="940be-149">사용자 당 일반적인 회의 수가 있는 조직에서 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="940be-150">이 지침을 사용 하 여 회의 Id를 일반적으로 작게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940be-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="940be-151">그러나, 풀 전체의 회의 디렉터리 수가 9 개를 초과 하면 추가 회의를 지원 하기 위해 회의 ID 번호가 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="940be-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="940be-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="940be-152">See Also</span></span>


[<span data-ttu-id="940be-153">Lync Server 2013의 중재 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="940be-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="940be-154">Lync Server 2013의 다이얼 플랜 및 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="940be-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

