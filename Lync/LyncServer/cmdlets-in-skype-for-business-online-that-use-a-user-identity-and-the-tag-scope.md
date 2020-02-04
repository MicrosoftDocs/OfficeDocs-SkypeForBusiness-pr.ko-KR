---
title: 사용자 id와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727568"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="d54d1-102">사용자 id와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d54d1-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="d54d1-103">사용자에 게 정책을 할당 하는 데 사용 되는 **허용-Cs** cmdlet에는 두 개의 식별자 인 사용자 Id (id 매개 변수)와 사용자별 정책 Id (PolicyName 매개 변수)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="d54d1-104">예를 들어 음성 정책 RedmondVoicePolicy를 사용자: 진구 Myer에 할당 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="d54d1-105">사용자에 게 정책을 할당할 때 염두에 두어야 할 두 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="d54d1-106">첫째, 사용자별 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="d54d1-107">전역 정책은 사용자에 게 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="d54d1-108">예를 들어 다음 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="d54d1-109">이 명령은 전역 정책을 할당할 필요가 없기 때문에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="d54d1-110">전역 정책을 사용 하 여 사용자를 관리 하려는 경우 해당 사용자에 게 사용자 단위 정책을 할당 하지 않도록 주의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54d1-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="d54d1-111">사용자에 게 할당 된 사용자별 정책이 없는 경우 사용자는 전역 정책을 사용 하 여 자동으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="d54d1-112">사용자가 이전에 사용자 기준 정책을 할당 한 경우 해당 정책을 할당 취소 하 고 사용자가 글로벌 정책에 의해 관리 되도록 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="d54d1-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="d54d1-113">이 경우 먼저 해당 사용자에 게 null 정책을 부여 하 여 사용자 단위 정책을 할당 취소 하는 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="d54d1-114">Grant-CsVoicePolicy – Id ": 진구 Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="d54d1-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="d54d1-115">두 번째, 사용자 단위 정책이 태그 범위에서 생성 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54d1-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="d54d1-116">그러나 정책 이름을 지정할 때 태그 **접두사** 를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="d54d1-117">이러한 두 명령은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="d54d1-118">모든 사용자별 정책에 대 한 id를 반환 하려는 경우 (적어도 또는 음성 정책 등 지정 된 형식의 사용자 단위 정책은 모두), 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="d54d1-119">다음 cmdlet은 사용자 Id와 태그 범위를 모두 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54d1-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="d54d1-120">[부여-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d54d1-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d54d1-121">[부여-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d54d1-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d54d1-122">[부여-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d54d1-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d54d1-123">[부여-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d54d1-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d54d1-124">[부여-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d54d1-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d54d1-125">[부여-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d54d1-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="d54d1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d54d1-126">See Also</span></span>


[<span data-ttu-id="d54d1-127">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="d54d1-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="d54d1-128">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d54d1-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

