---
title: 비즈니스용 Skype Online의 id, 범위 및 테 넌 트
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b08c459f64a4655ebb4dc670255645f985452aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="ea397-102">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="ea397-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea397-103">_**마지막으로 수정한 주제:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="ea397-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="ea397-104">비즈니스용 Skype Online을 관리 하는 데 사용 되는 많은 Windows PowerShell cmdlet은 관리 하려는 항목에 대 한 구체적인 정보를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="ea397-105">예를 들어, [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet을 실행 하는 경우 관리 하려는 사용자를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="ea397-106">이렇게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-106">This makes sense.</span></span> <span data-ttu-id="ea397-107">관리 하려는 사용자 계정을 명시적으로 지정 하지 않는 한, **Set CsUserAcp** cmdlet은 사용자의 오디오 회의 정보를 수정 해야 하는 것을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="ea397-108">이러한 이유로, **Set CsUserAcp** cmdlet을 실행할 때마다 id 매개 변수를 포함 하 고 수정할 사용자 계정의 id를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="ea397-109">용어 *id* 가 항상 사용자 계정의 id를 참조 하는 경우 혼란이 발생 하는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="ea397-110">사용자, 연락처 등을 처리 하는 경우 Id는 개별 사용자 자체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="ea397-111">그러나 사용자 계정 외의 항목에도 Id가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="ea397-112">비즈니스용 Skype Online 서비스의 구성 요소 (정책, 구성 설정 등)를 처리 하는 경우 Id 라는 용어는 약간 다른 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="ea397-113">예를 들어 다음 명령을 고려해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="ea397-114">이 경우 Id "global"은 모임 구성 설정의 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="ea397-115">*범위* 는 비즈니스용 Skype Online (및 Lync Server)에서 관리 구를 지정 하는 데 사용 되는 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="ea397-116">기본적으로 정책 및 설정에는 항상 전역 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="ea397-117">비즈니스용 Skype Online 계정을 처음 설정 하는 경우, 기본적으로 전역 정책 및 설정 (전역 모임 구성 설정, 전역 외부 액세스 정책, 전역 다이얼 플랜 등)의 모음을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="ea397-118">Microsoft Lync Server 2010에서 이러한 전역 정책과 설정이 도입 되어 모든 사용자와 모든 구성 요소가 항상 관리 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="ea397-119">이는 Microsoft Office Communicator 2007 R2에 반드시 적용 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="ea397-120">시스템에 액세스 한 방법에 따라 일반적으로 그룹 정책을 사용자 계정에 적용할 수 없기 때문에 거의 관리 되지 않는 상태가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="ea397-121">이와 대조적으로 Lync Server와 비즈니스용 Skype Online에서는 아무것도 유지 관리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="ea397-122">이는 다른 방법 대신 전역 정책과 설정이 항상 적용 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="ea397-123">"어떤 것이 든" 말은 무엇을 의미 하나요?</span><span class="sxs-lookup"><span data-stu-id="ea397-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="ea397-124">비즈니스용 Skype Online의 경우 *태그 범위*또는 관리의 구에 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="ea397-125">태그 범위 ( *사용자 단위 범위*라고도 함)에서 만든 정책은 전역 범위에서 만든 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="ea397-126">즉, 사용자 단위 정책은 항상 글로벌 정책에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="ea397-127">예를 들어 외부 사용자 액세스 정책이 두 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="ea397-128">전역 정책은 사용자가 Windows Live와 같은 IM (공용 인스턴트 메시징) 공급자에 계정이 있는 사용자와 통신 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="ea397-129">사용자별 정책, AllowPublicIMCommunication는 공용 IM 공급자와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="ea397-130">또한: 진구 Myer 및 Pilar Ackerman 등 두 명의 사용자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="ea397-131">: 진구 Myer에 사용자 단위 정책이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="ea397-132">Pilar Ackerman에는 사용자 단위 정책이 할당 되지 않았습니다. 즉, 전역 외부 액세스 정책에 의해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="ea397-133">다음 표에는 공용 IM 공급자와 통신할 수 있는 사용자 (있는 경우)가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea397-134">정책 설정</span><span class="sxs-lookup"><span data-stu-id="ea397-134">Policy Settings</span></span></th>
<th><span data-ttu-id="ea397-135">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="ea397-135">Ken Myer</span></span></th>
<th><span data-ttu-id="ea397-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="ea397-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea397-137">공용 IM 공급자에 대 한 전역 정책 설정</span><span class="sxs-lookup"><span data-stu-id="ea397-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="ea397-138">아니요</span><span class="sxs-lookup"><span data-stu-id="ea397-138">No</span></span></p></td>
<td><p><span data-ttu-id="ea397-139">아니요</span><span class="sxs-lookup"><span data-stu-id="ea397-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea397-140">공용 IM 공급자에 대 한 사용자별 정책 설정</span><span class="sxs-lookup"><span data-stu-id="ea397-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="ea397-141">예</span><span class="sxs-lookup"><span data-stu-id="ea397-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="ea397-142">아니요</span><span class="sxs-lookup"><span data-stu-id="ea397-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea397-143">사용자가 공용 IM 공급자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="ea397-144">예</span><span class="sxs-lookup"><span data-stu-id="ea397-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="ea397-145">아니요</span><span class="sxs-lookup"><span data-stu-id="ea397-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ea397-146">본 바와 같이: 진구 Myer는 공용 IM 공급자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="ea397-147">이는 자신에 게 할당 된 사용자별 정책 설정이 전역 정책의 설정을 재정의 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="ea397-148">Pilar Ackerman은 공용 IM 공급자와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="ea397-149">이것은 그녀는 글로벌 정책에 의해 관리 되므로 글로벌 정책은 그러한 통신을 금지 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="ea397-150">사용자 단위 정책은 Office 365 지원에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-150">Per-user policies must be created for you by Office 365 Support.</span></span> <span data-ttu-id="ea397-151">정책을 만든 후에는 적절 한 **허용 Cs** cmdlet (예: [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy))을 사용 하 여 사용자에 게 할당을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="ea397-152">정책 Id는 항상 태그 **접두사로**시작 되므로 사용자 단위 정책은 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="ea397-153">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="ea397-154">태그 <STRONG>접두사</STRONG> 는 Lync Server 2010의 초기 개발 날짜에 날짜를 다시 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="ea397-155">이러한 일 동안 사용자 단위 정책은 <EM>태그 정책</EM> 이라고 하 고 태그 <STRONG>접두사로</STRONG>식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="ea397-156">이러한 정책은 이제 <EM>사용자 단위 정책</EM>보다 정확 하 게 사용 되며 태그 범위는 <EM>사용자 단위 범위</EM>보다 더 정확 하 게 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="ea397-157">그러나 기술적인 이유로 태그 <STRONG>접두사</STRONG> 는 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="ea397-158">비즈니스용 Skype Online 및 Windows PowerShell을 사용할 때 사용 되는 다른 주요 용어는 *테 넌 트*입니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="ea397-159">비즈니스용 Skype Online 계정을 설정 하면 새 배포에 다음과 유사한 전역 고유 식별자 (GUID) 인 테 넌 트 ID 번호가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="ea397-160">비즈니스용 Skype Online cmdlet 중 일부는 cmdlet을 실행할 때마다 테 넌 트 ID를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="ea397-161">테 넌 트에 로그인 한 경우에도 테 넌 트 ID를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="ea397-162">다행히 테 넌 트 ID를 memorize 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="ea397-163">다음 Windows PowerShell 명령을 실행 하 여 언제 든 지 테 넌 트 ID를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="ea397-164">물론 전역 범위와 사용자 단위 범위 (또는 태그 범위) 간의 차이를 알고 있는 경우에만 전투의 반만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="ea397-165">이러한 범위를 사용할 수 있는 경우에는 언제 든 지 아는 것도 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="ea397-166">Id 및 테 넌 트 매개 변수의 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="ea397-167">다음 항목에서는 여러 비즈니스용 Skype Online cmdlet이 Id, 범위 및 테 넌 트 매개 변수를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea397-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="ea397-168">전역 범위만 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea397-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="ea397-169">전역 범위와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea397-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="ea397-170">사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea397-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="ea397-171">사용자 id와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea397-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="ea397-172">테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea397-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="ea397-173">회의 공급자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea397-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="ea397-174">범위 또는 id를 사용 하지 않는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ea397-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

