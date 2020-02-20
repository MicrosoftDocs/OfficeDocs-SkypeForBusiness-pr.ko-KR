---
title: Lync Server 2013 전화 접속 회의 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dcdf30ac0fc35f470e74991b2127cd81b05c5c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="1df09-102">Lync Server 2013의 전화 접속 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1df09-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1df09-103">_**마지막으로 수정 된 항목:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="1df09-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="1df09-104">Lync Server 2013 배포 프로세스를 시작 하기 전에 다음 사항에 대 한 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="1df09-105">PSTN(공중 전화망) 연결에 사용할 구성</span><span class="sxs-lookup"><span data-stu-id="1df09-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="1df09-106">전화 접속 회의 지역을 전화 접속 액세스 번호에 할당할 전략</span><span class="sxs-lookup"><span data-stu-id="1df09-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="1df09-107">전화 회의 디렉터리를 만들 전략</span><span class="sxs-lookup"><span data-stu-id="1df09-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="1df09-108">전화 접속 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="1df09-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="1df09-109">전화 접속 회의에는 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="1df09-110">중앙 사이트 또는 분기 사이트에 중재 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="1df09-111">중앙 사이트에서는 프런트 엔드 풀 또는 Standard Edition Server에서 중재 서버를 함께 배치할 하거나 독립 실행형 서버 또는 풀에 배포 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="1df09-112">분기 사이트에서는 중재 서버를 독립 실행형 서버 또는 Sba (survivable Branch 기기의 구성 요소로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="1df09-113">PSTN 게이트웨이는 중앙 사이트나 분기 사이트에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="1df09-114">분기 사이트에서 PSTN 게이트웨이는 독립 실행형 또는 Sba (survivable 분기 기기의 구성 요소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1df09-115">A/V 회의 서버에서는 미디어 바이패스를 지원 하지 않으므로 전화 접속 회의에서 미디어 바이패스를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="1df09-116">전화 접속 회의에 대 한 중재 서버 및 PSTN 게이트웨이의 구성을 계획 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 중재 서버용 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1df09-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="1df09-117">전화 접속 회의 지역 계획</span><span class="sxs-lookup"><span data-stu-id="1df09-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="1df09-p103">전화 접속을 구성할 때 다이얼 플랜 및 전화 접속 회의 액세스 번호를 만들 수 있습니다. 다이얼 플랜은 전화 번호의 번호와 숫자 패턴을 지정하는 정규화 규칙 집합이며, 통화 라우팅을 위해 전화 번호를 표준 E.164 형식으로 변환합니다. 전화 접속 회의 액세스 번호는 참가자가 전화 회의에 참가하기 위해 전화를 거는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-p103">During dial-in configuration, you create dial plans and dial-in conferencing access numbers. Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing. Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="1df09-p104">모든 전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜과 연결되어야 합니다. 전화 접속 회의 지역은 전화 접속 회의 액세스 번호를 해당 다이얼 플랜과 연결합니다. 다이얼 플랜을 설정할 때 해당 다이얼 플랜에 적용할 전화 접속 회의 지역을 지정할 수 있습니다. 그런 다음 전화 접속 액세스 번호를 만들 때 해당 액세스 번호를 적절한 다이얼 플랜과 연결하는 지역을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-p104">Every dial-in conferencing access number must be associated with at least one dial plan. Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans. When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="1df09-p105">또한 다이얼 플랜을 만들 때 다이얼 플랜의 범위를 지정할 수 있습니다. 지정할 수 있는 범위는 사용자 범위, 풀 범위 또는 사이트 범위입니다. 모든 사용자에게는 해당 사용자에게 적용되는 가장 좁은 범위의 다이얼 플랜이 할당됩니다. 예를 들어 사용자 수준 다이얼 플랜이 적용되는 사용자에게는 사용자 수준 다이얼 플랜이 할당됩니다. 그러나 사용자 수준 다이얼 플랜이 적용되지 않는 사용자에게는 풀 수준 다이얼 플랜이 할당되고, 풀 수준 다이얼 플랜이 적용되지 않는 사용자에게는 사이트 수준 다이얼 플랜이 할당됩니다. 또한 사이트 수준 다이얼 플랜이 적용되지 않는 사용자에게는 전역 다이얼 플랜이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-p105">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="1df09-p106">다이얼 플랜을 구성하기 전에 지역 이름 지정 및 사용 방법을 계획해야 합니다. 전화 접속 회의 지역에 대해 고려해야 할 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="1df09-133">지역은 일반적으로 단일 사무실 또는 사무실 그룹과 연관된 지리적 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="1df09-p107">언어는 전화 접속 액세스 번호와 연관됩니다. 여러 언어를 사용하는 지리적 영역을 지원하려면 여러 언어를 지원하도록 지역을 정의할 방법을 결정해야 합니다. 예를 들어 지리적 위치와 언어의 조합에 따라 여러 지역을 정의하거나, 지리적 위치에 따라 단일 지역을 정의하고 각 언어에 대해 서로 다른 전화 접속 액세스 번호를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="1df09-137">사용자가 모임을 예약하면 기본적으로 모임에서 해당 사용자의 다이얼 플랜에 지정된 지역을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="1df09-138">기본적으로 해당 지역의 모든 전화 접속 액세스 번호가 모임 초대에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="1df09-139">지역을 명확히 인식할 수 있도록 이름을 지정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="1df09-140">사용자는 지역 이름을 사용하여 다른 액세스 번호가 초대에 포함되도록 모임 지역을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="1df09-141">사용자가 Outlook을 사용 하 여 모임을 예약할 때 사용자는 Lync 2013의 온라인 모임 추가 기능을 사용 하 여 지역을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="1df09-142">전화 접속을 통해 회의에 참가하려는 모든 초대 대상자가 전화 회의 초대에서 로컬 액세스 번호를 확인할 수 있도록 지역을 설계해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="1df09-143">Lync Server 관리 셸 cmdlet을 사용 하 여 전화 접속 회의 설정 페이지에 있는 지역 내의 액세스 번호가 표시 되는 순서를 구성할 수 있습니다 (즉, 회의 초대에 표시 되는 순서).</span><span class="sxs-lookup"><span data-stu-id="1df09-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="1df09-144">위치에 관계없이 모든 사용자는 표시된 모든 전화 접속 액세스 번호로 전화를 걸어 전화 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="1df09-145">전화 회의 디렉터리 계획</span><span class="sxs-lookup"><span data-stu-id="1df09-145">Planning for Conference Directories</span></span>

<span data-ttu-id="1df09-146">전화 회의 디렉터리는 참가자가 Lync 2013을 사용할 때 회의에 참가 하는 데 사용 하는 영숫자 회의 ID와 전화 접속 회의 참가자가 회의에 참가 하는 데 사용 하는 숫자 전용 회의 ID 간의 매핑을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="1df09-147">전화 접속 ID의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="1df09-p110">전화 회의 디렉터리를 여러 개 만들면 상당히 많은 수의 전화 회의가 만들어질 때까지 전화 회의 ID가 짧게 유지될 수 있습니다. 전화 회의 ID를 약 6자리로 유지하려면 사용자당 전화 회의 수가 보편적인 조직의 경우 풀의 사용자 999명당 하나의 전화 회의 디렉터리를 만드는 것이 좋습니다. 이 지침을 사용하면 대개 전화 회의 ID가 짧게 유지될 수 있습니다. 그러나 회의 디렉터리 수가 풀 전체에서 9개를 초과하면 추가 전화 회의를 지원하기 위해 회의 ID 번호가 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="1df09-p110">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1df09-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1df09-152">See Also</span></span>


[<span data-ttu-id="1df09-153">Lync Server 2013의 중재 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1df09-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="1df09-154">Lync Server 2013의 다이얼 플랜 및 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="1df09-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

