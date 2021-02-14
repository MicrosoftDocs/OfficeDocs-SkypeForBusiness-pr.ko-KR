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
description: '비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자를 새 비즈니스용 Skype 서버 2019 배포로 이동할 수 있습니다. 비즈니스용 Skype 서버 2019로 원활하게 전환하려면 몇 가지 요구 사항을 충족해야 합니다. 이 항목의 절차를 완료하기 위한 선행 구성에 대한 자세한 내용은 마이그레이션을 위해 클라이언트 구성을 참조하십시오. 사용자 이동에 대한 자세한 단계는 4단계: 파일럿 풀로 테스트 사용자 이동을 참조하세요.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753716"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="48947-106">비즈니스용 Skype 서버 2019로 남은 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="48947-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="48947-107">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 사용자를 새 비즈니스용 Skype 서버 2019 배포로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48947-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="48947-108">비즈니스용 Skype 서버 2019로 원활하게 전환하려면 몇 가지 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48947-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="48947-109">이 항목의 절차를 완료하기 위한 선행 구성에 대한 자세한 내용은 마이그레이션을 위해 [클라이언트 구성을 참조하십시오.](configure-clients-for-migration.md)</span><span class="sxs-lookup"><span data-stu-id="48947-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="48947-110">사용자 이동에 대한 자세한 단계는 [4단계: 파일럿](phase-4-move-test-users-to-the-pilot-pool.md)풀로 테스트 사용자 이동을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48947-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="48947-111">Active Directory 사용자 및 컴퓨터 스냅인 또는 레거시 관리 도구를 사용하여 레거시 환경에서 비즈니스용 Skype 서버 2019로 사용자를 이동할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48947-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="48947-112">사용자를 비즈니스용 Skype 서버 2019 풀로 이동하면 사용자의 데이터가 새 풀과 연결된 백 엔드 데이터베이스로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="48947-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="48947-113">여기에는 레거시 사용자가 만든 활성 모임이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="48947-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="48947-114">예를 들어 레거시 사용자가 내  모임 회의를 구성한 경우 사용자를 이동한 후에도 새 비즈니스용 Skype 서버 2019 풀에서 해당 회의를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48947-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="48947-115">이 모임에 액세스하기 위한 세부 정보도 동일한 **회의 URL 및 회의 ID** 가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48947-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="48947-116">유일한 차이점은 이제 회의가 레거시 풀이 아니라 비즈니스용 Skype 서버 2019 풀에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="48947-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48947-117">비즈니스용 Skype 서버 2019에서 사용자를 호미하는 경우 업그레이드된 클라이언트를 동시에 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48947-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="48947-118">새로운 기능은 사용자가 새 클라이언트 소프트웨어로 업그레이드한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48947-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="48947-119">마이그레이션 후 작업</span><span class="sxs-lookup"><span data-stu-id="48947-119">Post migration task</span></span>

1. <span data-ttu-id="48947-120">사용자를 이동한 후에는 사용자에게 지정된 회의 정책을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="48947-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="48947-121">비즈니스용 Skype 서버 2019에 있는 사용자가 구성한 모임이 레거시 설치에 있는 페더링 사용자와 원활하게 작동하도록 하기 위해 마이그레이션된 사용자에게 할당된 회의 정책에서 익명 참가자를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48947-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="48947-122">익명 참가자를 허용하는 회의 정책에는  참가자가 비즈니스용 Skype 서버 2019 제어판에서 선택한 익명 사용자를 초대할 수 있도록 허용하고, 비즈니스용 Skype 서버 관리 셸의 **Get-CsConferencingPolicy** cmdlet 출력에서 **AllowAnonymousParticipantsInMeetings를** **True로** 설정하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="48947-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

