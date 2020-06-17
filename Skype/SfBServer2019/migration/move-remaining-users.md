---
title: 남은 사용자 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용 하 여 사용자를 새로운 비즈니스용 Skype 서버 2019 배포로 이동할 수 있습니다. 비즈니스용 Skype 서버 2019로 원활 하 게 전환 하려면 몇 가지 요구 사항을 충족 해야 합니다. 이 항목의 절차를 완료 하는 데 필요한 필수 구성 요소에 대 한 자세한 내용은 Configure clients for migration을 참조 하십시오. 사용자 이동에 대 한 자세한 단계는 Phase 4: test users to the 파일럿 풀로 이동을 참조 하십시오.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753716"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="208f1-106">나머지 사용자를 비즈니스용 Skype 서버 2019로 이동</span><span class="sxs-lookup"><span data-stu-id="208f1-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="208f1-107">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용 하 여 사용자를 새로운 비즈니스용 Skype 서버 2019 배포로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="208f1-108">비즈니스용 Skype 서버 2019로 원활 하 게 전환 하려면 몇 가지 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="208f1-109">이 항목의 절차를 완료 하는 데 필요한 필수 구성 요소에 대 한 자세한 내용은 [Configure clients for migration](configure-clients-for-migration.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="208f1-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="208f1-110">사용자 이동에 대 한 자세한 단계는 [Phase 4: test users to the 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="208f1-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="208f1-111">Active Directory 사용자 및 컴퓨터 스냅인 또는 레거시 관리 도구를 사용 하 여 레거시 환경에서 비즈니스용 Skype 서버 2019로 사용자를 이동할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="208f1-112">사용자를 비즈니스용 Skype 서버 2019 풀로 이동 하면 사용자에 대 한 데이터가 새 풀과 연결 된 백 엔드 데이터베이스로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="208f1-113">여기에는 레거시 사용자가 만든 활성 모임이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="208f1-114">예를 들어 레거시 사용자가 **내 모임** 회의를 구성한 경우 해당 회의는 사용자가 이동한 후 새로운 비즈니스용 Skype 서버 2019 풀에서 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="208f1-115">이 모임에 액세스하기 위한 세부 정보도 동일한 **회의 URL 및 회의 ID**가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="208f1-116">유일한 차이점은 현재 회의가 레거시 풀이 아닌 비즈니스용 Skype 서버 2019 풀에 호스트 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="208f1-117">비즈니스용 Skype 서버 2019의 호 사용자는 업그레이드 된 클라이언트를 동시에 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="208f1-118">새로운 기능은 사용자가 새 클라이언트 소프트웨어로 업그레이드한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="208f1-119">마이그레이션 후 작업</span><span class="sxs-lookup"><span data-stu-id="208f1-119">Post migration task</span></span>

1. <span data-ttu-id="208f1-120">사용자를 이동한 후에는 사용자에게 지정된 회의 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="208f1-121">비즈니스용 Skype 서버 2019에 있는 사용자가 구성한 모임이 레거시 설치에 포함 된 페더레이션 사용자와 원활 하 게 작동 하도록 하려면 마이그레이션된 사용자에 게 할당 된 회의 정책에서 익명 참가자를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="208f1-122">익명 참가자가 비즈니스용 Skype 서버 2019 제어판에서 선택한 **익명 사용자를 초대할 수** 있도록 허용 하는 회의 정책으로, **AllowAnonymousParticipantsInMeetings** 는 비즈니스용 Skype 서버 관리 셸에서 **Get-csconferencingpolicy** cmdlet의 출력에서 **True** 로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="208f1-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

