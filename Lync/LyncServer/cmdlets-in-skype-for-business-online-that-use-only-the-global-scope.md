---
title: 전역 범위만 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210e9116152ebe071ec81d2e0d48ff31b7c20a60
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40983828"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="fdc9e-102">전역 범위만 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="fdc9e-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="fdc9e-103">여러 비즈니스용 Skype Online 설정은 *전역 범위*에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="fdc9e-104">즉, 해당 테 넌 트에 할당 된 모든 사용자에 게 적용 되는 단일 설정 컬렉션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="fdc9e-105">각 테 넌 트에는 고유한 전역 설정 컬렉션이 있습니다. 전역 범위로 제한 되는 cmdlet을 사용 하는 경우 Identity 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="fdc9e-106">예를 들어 모임 구성 설정을 검색 하려면 다음 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="fdc9e-107">또는 Id 매개 변수를 생략 하 고 대신이 간단한 명령을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="fdc9e-108">모임 구성 설정에는 전역 컬렉션이 하나만 있으므로 두 명령은 정확히 동일한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="fdc9e-109">**Set Cs** cmdlet 중 하나를 사용 하는 경우 id 매개 변수를 생략할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="fdc9e-110">이러한 두 명령은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="fdc9e-111">두 명령은 기본적으로 Id 매개 변수를 포함 하지 않는 경우 Windows PowerShell이 전역 컬렉션을 수정 하기 때문에 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="fdc9e-112">다음 cmdlet은 전역 범위 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="fdc9e-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-120">[제거-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fdc9e-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="fdc9e-123">**제거-CsVoicePolicy** cmdlet은 변칙의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="fdc9e-124">먼저,이 cmdlet에서는 Id 매개 변수를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="fdc9e-125">두 번째, **CsVoicePolicy** cmdlet은 전역 음성 정책을 실제로 삭제 하지 않습니다. 비즈니스용 Skype Online에서는 전역 정책 또는 구성 설정을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="fdc9e-126">Cmdlet이 수행 하는 작업은 전역 음성 정책의 모든 속성을 기본값으로 재설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="fdc9e-127">예를 들어 AllowCallForwarding 전환 속성은 기본적으로 False로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="fdc9e-128">그러나 AllowCallForwarding 수정 되었을 수 있으며, 이제 값이 True로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="fdc9e-129">**CsVoicePolicy** cmdlet을 실행 하면 AllowCallForwarding 전환 속성이 기본값으로 전환 됩니다: False.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="fdc9e-130">다음 표에는이 시나리오가 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc9e-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdc9e-131">AllowCallForwarding 전환 값</span><span class="sxs-lookup"><span data-stu-id="fdc9e-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="fdc9e-132">시나리오</span><span class="sxs-lookup"><span data-stu-id="fdc9e-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdc9e-133">해제</span><span class="sxs-lookup"><span data-stu-id="fdc9e-133">False</span></span></p></td>
<td><p><span data-ttu-id="fdc9e-134">기본값</span><span class="sxs-lookup"><span data-stu-id="fdc9e-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdc9e-135">False</span><span class="sxs-lookup"><span data-stu-id="fdc9e-135">True</span></span></p></td>
<td><p><span data-ttu-id="fdc9e-136">전역 정책이 수정 된 후</span><span class="sxs-lookup"><span data-stu-id="fdc9e-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdc9e-137">해제</span><span class="sxs-lookup"><span data-stu-id="fdc9e-137">False</span></span></p></td>
<td><p><span data-ttu-id="fdc9e-138"><strong>Remove-CsVoicePolicy cmdlet을</strong> 실행 한 후</span><span class="sxs-lookup"><span data-stu-id="fdc9e-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="fdc9e-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdc9e-139">See Also</span></span>


[<span data-ttu-id="fdc9e-140">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="fdc9e-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="fdc9e-141">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fdc9e-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

