---
title: 전화 접속 액세스 번호 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 전화 접속 액세스 번호를 비즈니스용 Skype 서버 2019로 마이그레이션하면 contact 개체를 마이그레이션하기 위해 CsApplicationEndpoint cmdlet을 실행 해야 합니다. 레거시 설치 및 비즈니스용 Skype Server 2019 공존 기간 동안 비즈니스용 Skype Server 2019에서 만든 전화 접속 액세스 번호가 레거시 설치에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다 (이 문서에서 설명). 여기.
ms.openlocfilehash: 35c1e665f8affdbf84628f9a7d532405779648f0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991143"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="2da52-104">전화 접속 액세스 번호 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2da52-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="2da52-105">전화 접속 액세스 번호를 비즈니스용 Skype 서버 2019로 마이그레이션하면 contact 개체를 마이그레이션하기 위해 **CsApplicationEndpoint** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="2da52-106">레거시 설치 및 비즈니스용 Skype Server 2019 공존 기간 동안 비즈니스용 Skype Server 2019에서 만든 전화 접속 액세스 번호가 레거시 설치에서 만든 전화 접속 액세스 번호와 유사 하 게 작동 합니다 (이 문서에서 설명). 여기.</span><span class="sxs-lookup"><span data-stu-id="2da52-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="2da52-107">이전에 설치 했지만 비즈니스용 Skype Server 2019으로 또는 마이그레이션 도중 또는 마이그레이션하기 이후 비즈니스용 2019 Skype에서 만든 전화 접속 액세스 번호에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="2da52-108">Office Communications Server 2007 R2 모임 초대 및 전화 접속 액세스 번호 페이지에는 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="2da52-109">레거시 설치 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="2da52-110">비즈니스용 Skype 서버 2019 모임 초대 및 전화 접속 액세스 번호 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="2da52-111">Office Communications Server 2007 R2 관리 도구에서 보거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="2da52-112">레거시 설치 제어판 및 레거시 설치 관리 셸에서 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="2da52-113">비즈니스용 Skype Server 2019 제어판 및 비즈니스용 Skype Server 2019 관리 셸에서 보고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="2da52-114">CsDialinConferencingAccessNumber cmdlet을 Priority 매개 변수를 사용 하 여 영역 내에서 다시 시퀀싱 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="2da52-115">레거시 설치 풀의 역할을 해제 하기 전에 레거시 설치 풀을 가리키는 전화 접속 액세스 번호 마이그레이션을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="2da52-116">다음 절차에 설명 된 대로 전화 접속 액세스 번호 마이그레이션을 완료 하지 않은 경우에는 액세스 번호로 수신 되는 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2da52-117">레거시 설치 풀의 역할을 해제 하기 전에이 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="2da52-118">짧은 서비스 중단 기간이 있는 경우 네트워크 사용량이 낮을 때 전화 접속 액세스 번호를 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="2da52-119">전화 접속 액세스 번호를 확인 하 고 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="2da52-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="2da52-120">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="2da52-121">각 전화 접속 액세스 번호를 비즈니스용 Skype Server 2019에서 호스팅하는 풀로 이동 하려면 명령줄 실행에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="2da52-122">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="2da52-123">왼쪽 탐색 모음에서 **회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="2da52-124">**전화 접속 액세스 번호** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="2da52-125">마이그레이션하는 레거시 설치 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2da52-126">모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019 풀을 가리키는 경우에는 레거시 설치 풀을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2da52-127">비즈니스용 Skype Server 제어판을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인</span><span class="sxs-lookup"><span data-stu-id="2da52-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2da52-128">**Csuseradministrator** 역할 또는 **csadministrator** 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="2da52-129">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="2da52-130">왼쪽 탐색 모음에서 **회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="2da52-131">**전화 접속 액세스 번호** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="2da52-132">모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2da52-133">비즈니스용 Skype Server Management Shell을 사용 하 여 전화 접속 액세스 번호 마이그레이션 확인</span><span class="sxs-lookup"><span data-stu-id="2da52-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="2da52-134">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="2da52-135">마이그레이션된 모든 전화 접속 회의 액세스 번호를 명령줄 실행에서 반환 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="2da52-136">모든 전화 접속 액세스 번호가 비즈니스용 Skype 서버 2019에서 호스트 되는 풀로 마이그레이션 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2da52-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


