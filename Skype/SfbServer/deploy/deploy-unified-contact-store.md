---
title: '비즈니스용 Skype 서버에서 통합 연락처 저장소 배포 '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '요약: 비즈니스용 Skype 서버에서 통합 연락처 저장소를 사용하도록 설정하는 것입니다.'
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812558"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="2b18e-103">비즈니스용 Skype 서버에서 통합 연락처 저장소 배포</span><span class="sxs-lookup"><span data-stu-id="2b18e-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="2b18e-104">**요약:** 비즈니스용 Skype 서버에서 통합 연락처 저장소를 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b18e-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="2b18e-105">비즈니스용 Skype 서버에서 통합 연락처 저장소를 사용하도록 설정하는 데는 토폴로지 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="2b18e-106">사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2b18e-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="2b18e-107">통합 연락처 저장소 정책이 사용하도록 설정됩니다(기본값 사용).</span><span class="sxs-lookup"><span data-stu-id="2b18e-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="2b18e-108">사용자가 비즈니스용 Skype를 사용하여 한 번 이상 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="2b18e-109">사용자의 연락처가 마이그레이션된 후 사용자가 비즈니스용 Skype로 로그인할 때 자동으로 수행되며 사용자는 비즈니스용 Skype, Outlook 2013 또는 Outlook Web Access에서 비즈니스용 Skype 연락처에 액세스하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="2b18e-110">사용자는 Outlook 또는 Outlook Web Access에서 연락처를 관리하기 위해 비즈니스용 Skype에 로그인할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2b18e-111">사용자가 마이그레이션 후 비즈니스용 Skype에서 로그인하는 경우 연락처 및 그룹을 사용할 수 있으며 최신 상태이지만 사용자가 해당 연락처를 관리(추가, 삭제, 이동, 태그 지정, 태그 지정 취소 또는 수정)할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="2b18e-112">사용자가 통합 연락처 저장소를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="2b18e-112">Enable users for unified contact store</span></span>

<span data-ttu-id="2b18e-113">비즈니스용 Skype 서버를 배포하고 토폴로지 게시하면 기본적으로 모든 사용자에 대해 통합 연락처 저장소가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="2b18e-114">비즈니스용 Skype 서버를 배포한 후 통합 연락처 저장소를 사용하도록 설정하기 위해 추가 작업을 수행하지 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="2b18e-115">하지만 **Set-CsUserServicesPolicy** cmdlet을 사용해서 통합 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="2b18e-116">이 기능은 전역, 사이트별, 테넌트별 또는 개인이나 개인 그룹별로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="2b18e-117">통합 연락처 저장소에 대해 사용자를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2b18e-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="2b18e-118">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2b18e-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2b18e-119">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="2b18e-120">모든 비즈니스용 Skype 서버 사용자에 대해 통합 연락처 저장소를 전역적으로 사용하도록 설정하려면 Windows PowerShell 명령줄 인터페이스에서 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="2b18e-121">특정 사이트의 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="2b18e-122">예제:</span><span class="sxs-lookup"><span data-stu-id="2b18e-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="2b18e-123">테넌트에서 통합 연락처 저장소를 사용하도록 설정하려면 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="2b18e-124">예제:</span><span class="sxs-lookup"><span data-stu-id="2b18e-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="2b18e-125">특정 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="2b18e-126">또한 사용자 표시 이름 대신 사용자의 별칭 또는 SIP URI를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="2b18e-127">예:</span><span class="sxs-lookup"><span data-stu-id="2b18e-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="2b18e-128">위의 예제에서 첫 번째 명령은 UcsAllowed 플래그가 True로 설정된 UCS Enabled Users라는 새 사용자당 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="2b18e-129">두 번째 명령은 표시 이름이 Ken Myer인 사용자에게 정책을 할당합니다. 즉, Ken Myer가 통합 연락처 저장소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="2b18e-130">통합 연락처 저장소로 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2b18e-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="2b18e-131">사용자가 다음을 수행하면 사용자의 연락처가 Exchange 2013 서버로 자동으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="2b18e-132">UcsAllowed가 True로 설정된 사용자 서비스 정책을 할당한 경우</span><span class="sxs-lookup"><span data-stu-id="2b18e-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="2b18e-133">Exchange 2013 사서함으로 프로비전되고 사서함에 한 번 이상 로그인한 경우</span><span class="sxs-lookup"><span data-stu-id="2b18e-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="2b18e-134">비즈니스용 Skype 리치 클라이언트를 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="2b18e-135">사용자가 Lync 또는 이전 클라이언트로 로그인하거나 사용자가 Exchange 2013 서버에 연결되어 있지 않은 경우 사용자 서비스 정책이 무시되고 사용자의 연락처가 비즈니스용 Skype 서버에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="2b18e-136">다음 방법 중 하나를 사용하여 사용자 연락처가 마이그레이션되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="2b18e-137">클라이언트 컴퓨터에서 다음 레지스트리 키를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="2b18e-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ SIP URL \> \UCS</span><span class="sxs-lookup"><span data-stu-id="2b18e-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="2b18e-139">사용자의 연락처가 Exchange 2013에 저장되어 있는 경우 이 키에는 InUCSMode의 값이 2165로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="2b18e-140">**Test-CsUnifiedContactStore** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="2b18e-141">비즈니스용 Skype 서버 관리 셸 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="2b18e-142">**Test-CsUnifiedContactStore** 가 정상적으로 실행되면 사용자 연락처가 통합 연락처 저장소로 마이그레이션된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="2b18e-143">마이그레이션된 사용자 롤백</span><span class="sxs-lookup"><span data-stu-id="2b18e-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="2b18e-144">통합 연락처 저장소 기능을 롤백해야 하는 경우 사용자를 Exchange 2010 또는 Lync Server 2010으로 다시 이동하는 경우 연락처만 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="2b18e-145">롤백하기 위해 사용자에 대한 정책을 사용하지 않도록 설정한 다음 **Invoke-CsUcsRollback** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="2b18e-146">**Invoke-CsUcsRollback만** 실행하면 영구 롤백을 보장하기에 충분하지 않습니다. 정책을 사용하지 않도록 설정하지 않은 경우 통합 연락처 저장소 마이그레이션이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="2b18e-147">예를 들어 Exchange 2013이 Exchange 2010으로 롤백되어 사용자가 롤백된 후 사용자의 사서함이 Exchange 2013으로 이동되면 사용자 서비스 정책에서 사용자에 대해 통합 연락처 저장소를 사용하도록 설정한 경우 통합 연락처 저장소 마이그레이션이 롤백 후 7일 후에 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="2b18e-148">**Move-CsUser** cmdlet은 다음과 같은 상황에서 사용자의 연락처 저장소를 Exchange 2013에서 비즈니스용 Skype 서버로 자동으로 롤백합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="2b18e-149">사용자가 비즈니스용 Skype 서버에서 Microsoft Lync Server 2013 또는 Lync Server 2010으로 이동되는 경우</span><span class="sxs-lookup"><span data-stu-id="2b18e-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="2b18e-150">사용자가 비즈니스용 Skype Online에서 비즈니스용 Skype 서버에서 비즈니스용 Skype 서버로 이동되는 경우와 같이 사용자가 크로스 프레미스로 마이그레이션되는 경우 또는 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="2b18e-p107">백업 데이터베이스에서 통합 연락처 저장소 데이터를 가져올 경우 통합 연락처 저장소 모드가 내보내기와 가져오기 간에 변경되면 통합 연락처 저장소 데이터 및 사용자 데이터가 손상될 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="2b18e-153">사용자의 연락처가 Exchange 2013으로 마이그레이션되기 전에 연락처 목록을 내보낼 경우 마이그레이션 후에 동일한 데이터를 가져오면 통합 연락처 저장소 데이터 및 연락처 목록이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="2b18e-154">사용자를 Exchange 2013으로 마이그레이션한 후 사용자 데이터를 내보낼 경우 마이그레이션을 롤백한 다음 마이그레이션 후 데이터를 가져오면 통합 연락처 저장소 데이터 및 연락처 목록이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="2b18e-155">Exchange 사서함을 Exchange 2013에서 Exchange 2010으로 이동하기 전에 Exchange 관리자는 비즈니스용 Skype 서버 관리자가 먼저 비즈니스용 Skype 서버 사용자 연락처를 Exchange 2013에서 비즈니스용 Skype 서버로 롤백하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="2b18e-156">통합 연락처 저장소 연락처를 비즈니스용 Skype 서버로 롤백하기 위해 이 섹션의 뒷부분에 있는 "Exchange 2013에서 비즈니스용 Skype 서버로 통합 연락처 저장소 연락처를 롤백하는 절차"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b18e-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="2b18e-157">**사용자 연락처를 롤백하는 방법:** **Move-CsUser** cmdlet을 사용하여 비즈니스용 Skype 서버 2015와 Lync Server 2010 간에 사용자를 이동하는 경우 **Move-CsUser** cmdlet은 사용자를 비즈니스용 Skype 서버 2015에서 Lync Server 2010으로 이동할 때 통합 연락처 저장소를 자동으로 롤백하기 때문에 이러한 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="2b18e-158">**Move-CsUser는** 통합 연락처 저장소 정책을 사용하지 않도록 설정하지 않습니다. 따라서 사용자가 비즈니스용 Skype 서버 2015로 다시 이동하면 통합 연락처 저장소로의 마이그레이션이 되돌아가게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b18e-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

