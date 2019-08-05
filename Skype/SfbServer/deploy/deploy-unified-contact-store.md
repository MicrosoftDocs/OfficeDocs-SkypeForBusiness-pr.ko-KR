---
title: '비즈니스용 Skype 서버에서 통합 된 연락처 저장소 배포 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '요약: 비즈니스용 Skype 서버에서 통합 된 연락처 저장소를 사용 하도록 설정 합니다.'
ms.openlocfilehash: 737e9dbdd0dc9e4aae54e454cb558c59004719b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197356"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="58802-103">비즈니스용 Skype 서버에서 통합 된 연락처 저장소 배포</span><span class="sxs-lookup"><span data-stu-id="58802-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="58802-104">**요약:** 비즈니스용 Skype 서버에서 통일 된 연락처 저장소를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="58802-105">비즈니스용 Skype 서버에서 통합 된 대화 상대 저장소를 사용 하도록 설정 하는 것은 토폴로지 설정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="58802-106">사용자를 위해 통합 된 연락처 저장소를 사용 하도록 설정 하려면:</span><span class="sxs-lookup"><span data-stu-id="58802-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="58802-107">통합 된 대화 상대 저장소 정책을 사용할 수 있습니다 (기본값 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="58802-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="58802-108">사용자는 적어도 한 번은 비즈니스용 Skype를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="58802-109">사용자가 비즈니스용 Skype를 사용 하 여 로그인 할 때 자동으로 발생 하는 사용자의 연락처를 마이그레이션한 후에는 사용자가 비즈니스용 skype 연락처, Outlook 2013 또는 Outlook Web Access를 액세스 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="58802-110">사용자는 비즈니스용 Skype에 로그인 하지 않아도 Outlook 또는 Outlook Web Access에서 연락처를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58802-111">사용자가 마이그레이션 후 비즈니스용 Skype에서 로그인 하는 경우에는 연락처 및 그룹을 최신으로 사용할 수 있지만, 사용자는 해당 연락처를 관리 (추가, 삭제, 이동, 태그 지정, untag 또는 수정) 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="58802-112">통합 연락처 저장소에 사용자 사용</span><span class="sxs-lookup"><span data-stu-id="58802-112">Enable users for unified contact store</span></span>

<span data-ttu-id="58802-113">비즈니스용 Skype 서버를 배포 하 고 토폴로지를 게시 하면 모든 사용자에 대해 통합 대화 저장소가 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58802-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="58802-114">비즈니스용 Skype 서버를 배포한 후에는 통합 된 대화 상대 저장소를 사용 하도록 설정 하기 위해 추가 조치를 취할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="58802-115">그러나 **Set-Csuser서비스 정책** cmdlet을 사용 하 여 통합 된 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="58802-116">사이트, 테 넌 트 또는 개인 또는 개인 그룹 별로 전역으로이 기능을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="58802-117">통합 된 대화 상대 저장소에 대해 사용자를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="58802-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="58802-118">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="58802-119">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="58802-120">모든 비즈니스용 Skype Server 사용자에 대해 통합 된 연락처 저장소를 전역으로 사용 하도록 설정 하려면 Windows PowerShell 명령줄 인터페이스에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="58802-121">특정 사이트의 사용자에 대해 통합 된 연락처 저장소를 사용 하도록 설정 하려면 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="58802-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="58802-123">테 넌 트에서 통합 된 대화 상대 저장소를 사용 하도록 설정 하려면 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="58802-124">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="58802-125">특정 사용자에 대해 통합 된 대화 상대 저장소를 사용 하도록 설정 하려면 프롬프트에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="58802-126">사용자 표시 이름 대신 사용자 별칭 또는 SIP URI를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="58802-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="58802-128">앞의 예제에서 첫 번째 명령은 UcsAllowed 플래그가 True로 설정 된 UCS를 사용 하는 사용자 별 정책을 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58802-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="58802-129">두 번째 명령은 표시 이름: 진구 Myer를 사용 하 여 사용자에 게 정책을 할당 하며,이는: 진구 Myer이 이제 통합 연락처 저장소에 대해 사용 하도록 설정 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="58802-130">통합 연락처 저장소로 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="58802-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="58802-131">사용자의 연락처가 다음과 같이 자동으로 Exchange 2013 서버로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="58802-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="58802-132">(으)로 지정 된 사용자 서비스 정책에 대 한 모든 권한이 True로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="58802-133">이 (가) Exchange 2013 사서함으로 프로 비전 되었으며 사서함에 한 번 이상 로그인 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="58802-134">비즈니스용 Skype 리치 클라이언트를 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="58802-135">사용자가 Lync 또는 이전 버전의 클라이언트를 사용 하 여 로그인 하거나 사용자가 Exchange 2013 서버에 연결 되어 있지 않으면 사용자 서비스 정책이 무시 되 고 사용자의 연락처가 비즈니스용 Skype 서버에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="58802-136">다음 방법 중 하나를 사용 하 여 사용자의 연락처가 마이그레이션 되었는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="58802-137">클라이언트 컴퓨터에서 다음 레지스트리 키를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="58802-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\ucs</span><span class="sxs-lookup"><span data-stu-id="58802-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="58802-139">사용자의 연락처가 Exchange 2013에 저장 되어 있는 경우이 키에는 2165 값을 사용 하 여 InUCSMode 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58802-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="58802-140">**테스트 CsUnifiedContactStore** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="58802-141">비즈니스용 Skype 서버 관리 셸 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="58802-142">**테스트-CsUnifiedContactStore** 성공 하면 사용자의 연락처가 통일 된 대화 상대 저장소로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="58802-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="58802-143">마이그레이션된 사용자 롤 롤백</span><span class="sxs-lookup"><span data-stu-id="58802-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="58802-144">통합 된 대화 상대 저장소 기능을 롤백해야 하는 경우 사용자를 Exchange 2010 또는 Lync Server 2010로 다시 이동 하는 경우에만 연락처를 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="58802-145">롤백하려면 사용자에 대해 정책을 사용 하지 않도록 설정한 다음 **CsUcsRollback** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="58802-146">정책을 사용 하지 않도록 설정 하면 통합 된 대화 상대 저장소 마이그레이션이 다시 시작 되기 때문에 **CsUcsRollback** 단독으로 실행 하는 것 만으로는 영구 롤백을 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="58802-147">예를 들어 Exchange 2013이 Exchange 2010로 롤백 된 후 사용자의 사서함이 Exchange 2013로 이동 하는 경우, 통합 된 대화 상대 저장소를 사용 하는 한, 통합 대화 저장소 마이그레이션이 롤백 후 7 일이 지난 후에 다시 시작 됩니다. 사용자 서비스 정책에서 계속 해 서 사용자에 게 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="58802-148">다음과 같은 경우에는 **Csuser 사용자** cmdlet이 사용자의 연락처 저장소를 Exchange 2013에서 비즈니스용 Skype 서버로 자동으로 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="58802-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="58802-149">사용자가 비즈니스용 Skype 서버에서 Microsoft Lync Server 2013 또는 Lync Server 2010으로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="58802-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="58802-150">사용자가 비즈니스용 Skype Online에서 비즈니스용 Skype Server 온-프레미스로 이동 하는 경우와 같이 사용자가 상호를 마이그레이션한 경우 또는 그 반대의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="58802-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="58802-151">백업 데이터베이스에서 통합 된 연락처 저장소 데이터를 가져오면 통합 된 대화 상대 저장소 모드가 내보내기와 가져오기 간에 변경 된 경우 사용자 데이터가 손상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-151">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="58802-152">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-152">For example:</span></span>
  
- <span data-ttu-id="58802-153">사용자의 연락처가 Exchange 2013으로 마이그레이션될 때까지 연락처 목록을 내보낸 다음 마이그레이션 후 동일한 데이터를 가져오면 통합 된 연락처 저장소 데이터와 연락처 목록이 손상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58802-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="58802-154">사용자를 Exchange 2013으로 마이그레이션하고 마이그레이션을 마이그레이션한 다음 마이그레이션 후에 데이터를 가져오는 이유 중 일부 이유로 인해 통합 된 연락처 저장소 데이터 및 연락처 목록이 손상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="58802-155">Exchange 사서함을 exchange 2013에서 Exchange 2010로 이동 하기 전에 먼저 비즈니스용 Skype 서버 관리자가 Exchange 2013의 비즈니스용 Skype 서버 사용자 연락처를 Skype로 롤백 해야 합니다. 비즈니스 서버.</span><span class="sxs-lookup"><span data-stu-id="58802-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="58802-156">통합 된 대화 상대 저장소 연락처를 비즈니스용 Skype 서버에 롤백하려면이 섹션의 뒷부분에 있는 "Exchange 2013에서 비즈니스용 Skype 서버에 대 한 통합 된 대화 상대 저장소를 롤백하는 방법" 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58802-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="58802-157">**사용자 대화 상대를 롤백하는 방법:** **이동-csuser** cmdlet을 사용 하 여 비즈니스용 skype Server 2015 및 Lync server 2010 간에 사용자를 이동 하는 경우, 다음 단계를 건너뛸 수 있습니다. **csuser** Cmdlet이 사용자를 skype에서 이동할 때 통합 된 연락처 저장소를 자동으로 롤백합니다. 비즈니스 서버 2015에서 Lync Server 2010로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58802-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="58802-158">**이동-CsUser** 는 통합 된 대화 상대 저장소 정책을 사용 하지 않도록 설정 하지 않으므로 사용자가 비즈니스용 Skype 서버 2015로 다시 이동 하는 경우 통합 된 연락처 저장소로의 마이그레이션이 되풀이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58802-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

