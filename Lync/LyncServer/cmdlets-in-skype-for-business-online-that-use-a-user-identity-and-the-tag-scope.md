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
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001443"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="b0607-102">사용자 id와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="b0607-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="b0607-103">사용자에 게 정책을 할당 하는 데 사용 되는 **Cs** cmdlet에는 두 개의 식별자, 즉 사용자 Id (identity 매개 변수)와 사용자별 정책 Id (PolicyName 매개 변수)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="b0607-104">예를 들어 음성 정책 RedmondVoicePolicy를 Ken Myer 사용자에 게 할당 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="b0607-105">사용자에 게 정책을 할당할 때는 두 가지 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="b0607-106">먼저 사용자별 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="b0607-107">전역 정책은 사용자에 게 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="b0607-108">예를 들어 다음 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="b0607-109">전역 정책을 할당할 필요가 없기 때문에이 명령은 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="b0607-110">전역 정책을 사용 하 여 사용자를 관리 하려는 경우에는 해당 사용자에 게 사용자별 정책을 할당 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="b0607-111">사용자에 게 할당 된 사용자별 정책이 없는 경우 사용자는 전역 정책을 사용 하 여 자동으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="b0607-112">사용자에 게 이전에 사용자가 정책을 할당 했 고 해당 정책을 할당 취소 하 고 대신 사용자에 게 글로벌 정책이 관리 되도록 하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="b0607-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="b0607-113">이 경우 먼저 다음 구문을 사용 하 여 해당 사용자에 게 null 정책을 부여 하 여 사용자별 정책을 할당 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="b0607-114">Grant-Set-csvoicepolicy – Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="b0607-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="b0607-115">둘째, 사용자 단위 정책이 태그 범위에 생성 된다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="b0607-116">그러나 정책 이름을 지정할 때는 태그 **접두사** 를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="b0607-117">다음 두 명령은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="b0607-118">모든 사용자별 정책에 대 한 id를 반환 하려면 (또는 최소한 지정 된 유형의 모든 사용자별 정책 (예: 음성 정책)) 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="b0607-119">다음 cmdlet은 사용자 Id와 태그 범위를 모두 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0607-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="b0607-120">[부여-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0607-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b0607-121">[Get-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0607-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b0607-122">[부여-CsDialPlan 플랜](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0607-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b0607-123">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0607-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b0607-124">[Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0607-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="b0607-125">[Set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0607-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="b0607-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0607-126">See Also</span></span>


[<span data-ttu-id="b0607-127">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="b0607-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="b0607-128">[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0607-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

