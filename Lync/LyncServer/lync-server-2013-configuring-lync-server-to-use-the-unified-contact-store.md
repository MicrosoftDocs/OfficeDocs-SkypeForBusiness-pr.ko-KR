---
title: 'Lync Server 2013: 통합 연락처 저장소를 사용 하도록 Lync Server 구성'
description: 'Lync Server 2013: 통합 연락처 저장소를 사용 하도록 Lync Server를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6905d2e393fec36fe5db3e40ee20087c0cca0991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570794"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="c4005-103">통합 연락처 저장소를 사용 하도록 Microsoft Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="c4005-103">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4005-104">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c4005-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c4005-105">통합 연락처 저장소를 사용 하면 사용자가 단일 연락처 목록을 유지 관리 한 다음 Microsoft Lync 2013, Microsoft Outlook 2013 및 Microsoft Outlook Web App 2013을 비롯 한 여러 응용 프로그램에서 해당 연락처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-105">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="c4005-106">사용자에 대해 통합 연락처 저장소를 사용 하도록 설정 하면 사용자의 연락처가 Microsoft Lync Server 2013에 저장 되지 않고 SIP 프로토콜을 사용 하 여 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-106">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="c4005-107">대신 Microsoft Exchange Server 2013에 저장 되 고 Exchange 웹 서비스를 사용 하 여 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-107">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4005-108">기술적으로 연락처 정보는 사용자의 Exchange 2013 사서함에 있는 한 쌍의 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-108">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="c4005-109">연락처는 최종 사용자에 게 표시 되는 Lync 연락처 라는 폴더에 저장 됩니다. 연락처에 대 한 메타 데이터는 최종 사용자에 게 표시 되지 않는 하위 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-109">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="c4005-110">사용자에 대해 통합 연락처 저장소를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c4005-110">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="c4005-111">Lync Server 2013 및 Exchange 2013 간에 서버 간 인증을 이미 구성한 경우에도 통합 연락처 저장소를 사용 하도록 설정 해야 합니다. 추가 서버 구성은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-111">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="c4005-112">그러나 사용자의 연락처를 통합 연락처 저장소로 이동 하려면 추가 사용자 계정 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-112">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="c4005-113">기본적으로 사용자 연락처는 통합 연락처 저장소가 아닌 Lync Server에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-113">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="c4005-114">통합 연락처 저장소에 대 한 액세스는 Lync Server 사용자 서비스 정책을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-114">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="c4005-115">사용자 서버 정책에는 단일 속성 (함께 사용할 수 있음)만 있습니다. 이 속성은 사용자의 연락처가 저장 되는 위치를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-115">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="c4005-116">사용자가 일부를 True ($True)로 설정 된 사용자 서비스 정책에 의해 관리 되는 경우 사용자의 연락처가 통합 연락처 저장소에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-116">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="c4005-117">사용자가 $False으로 설정 된 사용자 서비스 정책을 통해 관리 되는 경우 해당 연락처가 Lync Server에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-117">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="c4005-118">Lync Server 2013을 설치 하면 전역 범위에 구성 된 단일 사용자 서비스 정책도 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-118">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="c4005-119">이 정책에서 c s p 허용 값은 True로 설정 되어 있으므로 기본적으로 사용자 연락처는 통합 연락처 저장소에 저장 됩니다 (이 기능이 배포 및 구성 된 경우).</span><span class="sxs-lookup"><span data-stu-id="c4005-119">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="c4005-120">모든 사용자 연락처를 통합 연락처 저장소로 마이그레이션하려면 별도의 작업을 수행 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-120">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="c4005-121">모든 연락처를 통합 연락처 저장소로 마이그레이션하지 않으려면 전역 정책에서 c u s e n 허용 속성을 False로 설정 하 여 모든 사용자에 대해 통합 연락처 저장소를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-121">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="c4005-122">전역 정책에서 통합 연락처 저장소를 사용 하지 않도록 설정한 후에는 통합 연락처 저장소를 사용 하도록 설정 하는 사용자별 정책을 만들 수 있습니다. 이렇게 하면 다른 사용자가 계속 해 서 Lync Server에 연락처를 유지 하면서 통합 연락처 저장소에서 자신의 연락처를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-122">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="c4005-123">다음과 같은 명령을 사용 하 여 사용자별 사용자 서비스 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-123">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="c4005-124">새 정책을 만든 후에는 통합 연락처 저장소에 액세스 해야 하는 모든 사용자에 게 해당 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-124">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store.</span></span> <span data-ttu-id="c4005-125">다음과 같은 명령을 사용 하 여 사용자에 게 사용자별 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-125">Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="c4005-126">정책이 할당 된 후에는 Lync Server가 사용자의 연락처를 통합 연락처 저장소로 마이그레이션하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-126">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="c4005-127">마이그레이션이 완료 되 면 사용자는 Lync Server가 아닌 Exchange에 연락처를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-127">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="c4005-128">사용자가 마이그레이션 완료 시 Lync 2013에 로그온 되어 있는 경우 메시지 상자가 표시 되 고, 프로세스를 완료 하기 위해 Lync에서 로그 오프 한 다음 다시 로그온 하 라는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-128">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="c4005-129">사용자 단위 정책에 할당 되지 않은 사용자는 연락처를 통합 연락처 저장소로 마이그레이션하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-129">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="c4005-130">해당 사용자는 전역 정책에 의해 관리 되며, 전역 정책에서 통합 연락처 저장소 사용이 사용 하지 않도록 설정 되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-130">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="c4005-131">Lync Server 관리 셸에서 [test-csunifiedcontactstore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet을 실행 하 여 사용자의 대화 상대가 통합 연락처 저장소로 성공적으로 마이그레이션 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-131">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c4005-132">Test-CsUnifiedContactStore에 성공 하면 사용자 sip:kenmyer@litwareinc.com의 연락처가 통합 연락처 저장소로 마이그레이션 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-132">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="c4005-133">통합 연락처 저장소 롤백</span><span class="sxs-lookup"><span data-stu-id="c4005-133">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="c4005-134">통합 연락처 저장소에서 사용자의 연락처를 제거 해야 하는 경우 (예: 사용자가 Microsoft Lync Server 2010를 기반으로 하 여 더 이상 통합 연락처 저장소를 사용할 수 없는 경우) 두 가지 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-134">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="c4005-135">먼저, 통합 연락처 저장소에 연락처를 저장할 수 없도록 하는 새 사용자 서비스 정책을 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-135">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="c4005-136">(즉, c u s 허용 속성이 $False로 설정 된 정책) 이러한 정책이 없는 경우 다음과 같은 명령을 사용 하 여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-136">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="c4005-137">그런 다음 다음과 같은 명령을 사용 하 여이 새로운 사용자별 정책 (NoUnifiedContactStore)을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-137">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="c4005-138">위 명령은 사용자 Ken Myer에 게 새 정책을 할당 하 고 Ken의 연락처가 통합 연락처 저장소로 마이그레이션되는 것을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-138">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4005-139">경우에 따라 사용자의 현재 사용자 서비스 정책에 대 한 할당을 취소 하 여 동일한 네트워크 효과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-139">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy.</span></span> <span data-ttu-id="c4005-140">예를 들어 Ken Myer에 통합 연락처 저장소를 사용 하도록 설정 하는 사용자별 사용자 서비스 정책이 있지만 글로벌 정책에 따라 통합 연락처 저장소를 사용할 수 없는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-140">For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store.</span></span> <span data-ttu-id="c4005-141">이 경우에는 Ken의 사용자별 서비스 정책을 할당 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-141">In that case, you could unassign Ken's per-user services policy.</span></span> <span data-ttu-id="c4005-142">이렇게 하면 Ken가 자동으로 전역 정책으로 관리 되므로 통합 연락처 저장소에 더 이상 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-142">When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="c4005-143">이전에 할당 한 사용자별 정책을 할당 해제 하려면 이전에 표시 된 것과 같은 명령을 사용 하 되, 이번에는 PolicyName 매개 변수를 null 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-143">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="c4005-144">Grant-CsUserServicesPolicy-Id "Ken Myer"-PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="c4005-144">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="c4005-145">"Ken의 연락처가 통합 연락처 저장소로 마이그레이션될 수 없습니다." 라는 용어는 통합 연락처 저장소로 작업할 때 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-145">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="c4005-146">Ken를 새 사용자 서비스 정책으로 할당 하기만 해도 연락처가 통합 연락처 저장소 외부로 이동 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-146">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="c4005-147">사용자가 Lync Server 2013에 로그온 할 때 시스템은 사용자의 사용자 서비스 정책을 검사 하 여 해당 연락처가 통합 연락처 저장소에 보관 되어야 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-147">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="c4005-148">예를 들어, (c 지 허용 속성이 $True로 설정 된 경우) 연락처는 통합 연락처 저장소로 마이그레이션됩니다 (해당 연락처가 아직 통합 연락처 저장소에 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="c4005-148">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="c4005-149">대답이 아니오로 설정 된 경우 Lync Server는 사용자의 연락처를 무시 하 고 다음 작업으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-149">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="c4005-150">즉, Lync Server는 c 지 허용 속성 값에 관계 없이 통합 연락처 저장소에서 사용자의 연락처를 자동으로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-150">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="c4005-151">또한 사용자에 게 새 사용자 서비스 정책을 할당 한 후에는 [invoke-csucsrollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet을 실행 하 여 사용자의 연락처를 Exchange 2013에서 Lync Server 2013로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-151">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="c4005-152">예를 들어 Ken Myer를 새 사용자 서비스 정책에 할당 한 후에는 다음 명령을 사용 하 여 연락처를 통합 연락처 저장소 외부로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-152">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="c4005-153">사용자 서비스 정책을 변경 하지만 Invoke-CsUcsRollback 실행 하지 않으면 Ken의 연락처가 통합 연락처 저장소에서 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-153">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="c4005-154">Invoke-CsUcsRollback를 실행 하지만 Ken Myer의 사용자 서비스 정책을 변경 하지 않는 경우에는 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="c4005-154">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="c4005-155">이 경우 Ken의 연락처가 통합 연락처 저장소에서 일시적으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-155">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="c4005-156">이 제거가 일시적 이라는 사실은 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-156">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="c4005-157">Ken의 연락처가 통합 연락처 저장소에서 제거 된 후 Lync Server 2013는 7 일을 기다린 후 Ken에 할당 된 사용자 서비스 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-157">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="c4005-158">Ken에 통합 연락처 저장소의 사용자를 사용 하도록 설정 하는 정책이 할당 되 면 해당 연락처가 자동으로 연락처 저장소로 다시 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-158">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="c4005-159">통합 연락처 저장소에서 연락처를 영구적으로 제거 하려면 Invoke-CsUcsRollback cmdlet을 실행 하는 것과 함께 사용자 서비스 정책을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-159">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="c4005-160">마이그레이션에 영향을 줄 수 있는 변수가 많기 때문에 계정이 통합 연락처 저장소로 완전히 마이그레이션될 때까지 소요 되는 시간을 예측 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-160">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="c4005-161">일반적으로 마이그레이션은 즉시 적용 되지 않습니다. 소수의 대화 상대를 마이그레이션하는 경우에도 이동이 완료 되기 전에 10 분 이상 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4005-161">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

