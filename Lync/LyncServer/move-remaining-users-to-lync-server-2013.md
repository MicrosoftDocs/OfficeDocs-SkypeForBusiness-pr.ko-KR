---
title: Lync Server 2013으로 나머지 사용자 이동
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d5c747a216ff5407a3150eb1cdcdfb94a3c73c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978896"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="dc57f-102">Lync Server 2013으로 나머지 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="dc57f-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc57f-103">_**마지막으로 수정한 주제:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="dc57f-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="dc57f-104">Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 사용자를 새 Lync Server 2013 배포로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="dc57f-105">Lync Server 2013의 원활한 전환을 위해 몇 가지 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="dc57f-106">이 항목의 절차를 완료 하기 위한 필수 구성 요소에 대 한 자세한 내용은 [마이그레이션할 클라이언트 구성을](configure-clients-for-migration.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc57f-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="dc57f-107">사용자 이동에 대 한 자세한 내용은 [4 단계: 파일럿 풀로 테스트 사용자 이동을](phase-4-move-test-users-to-the-pilot-pool.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc57f-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dc57f-108">Active Directory 사용자 및 컴퓨터 스냅인 또는 Lync Server 2010 관리 도구를 사용 하 여 사용자를 레거시 환경에서 Lync Server 2013로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="dc57f-109">사용자를 Lync Server 2013 풀로 이동 하면 사용자에 대 한 데이터가 새 풀과 연결 된 백 엔드 데이터베이스로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dc57f-110">여기에는 레거시 사용자가 만든 활성 모임이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="dc57f-111">예를 들어 레거시 사용자가 <STRONG>내 모임</STRONG> 회의를 구성한 경우 해당 회의는 사용자가 이동한 후 새 Lync Server 2013 풀에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="dc57f-112">해당 모임에 액세스 하는 데 대 한 세부 정보는 계속 해 서 동일한 <STRONG>회의 URL 및 전화 회의 ID</STRONG>가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="dc57f-113">유일한 차이점은 현재 회의가 lync server 2010 풀이 아닌 Lync Server 2013 풀에서 호스트 된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dc57f-114">Lync Server 2013의 다른 사용자가 동시에 업그레이드 된 클라이언트를 배포할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="dc57f-115">새로운 기능은 사용자가 새 클라이언트 소프트웨어로 업그레이드 한 경우에만 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="dc57f-116">마이그레이션 이후 작업</span><span class="sxs-lookup"><span data-stu-id="dc57f-116">Post Migration Task</span></span>

1.  <span data-ttu-id="dc57f-117">사용자를 이동한 후에는 자신에 게 할당 된 회의 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="dc57f-118">Lync Server 2013에서 사용자가 구성한 모임이 Lync Server 2010에 있는 페더레이션 사용자와 원활 하 게 작동 하도록 하기 위해, 마이그레이션된 사용자에 게 할당 된 회의 정책은 익명 참가자를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="dc57f-119">익명 참가자를 허용 하는 회의 정책은 참가자가 Lync Server 2013 제어판에서 **익명 사용자를 초대할 수 있도록 허용** 하 고 Lync Server 관리 셸에서 **CsConferencingPolicy** Cmdlet의 출력에서 **AllowAnonymousParticipantsInMeetings** 를 **True** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc57f-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="dc57f-120">Lync Server Management Shell을 사용 하 여 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc57f-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

