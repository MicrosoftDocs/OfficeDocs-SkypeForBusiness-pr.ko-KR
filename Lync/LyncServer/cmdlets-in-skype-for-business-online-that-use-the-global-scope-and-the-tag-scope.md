---
title: 전역 범위와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40979061"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="dc715-102">전역 범위와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc715-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="dc715-103">비즈니스용 Skype Online에서 정책을 *전역 범위* 또는 *태그 범위* (또는 *사용자 단위 범위*)에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="dc715-104">**Cs** cmdlet을 사용 하는 경우 범위 또는 id를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="dc715-105">매개 변수 없이 이러한 cmdlet 중 하나를 호출 하면 관련 항목이 모두 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="dc715-106">예를 들어이 명령은 모든 외부 액세스 정책에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="dc715-107">반환 된 데이터를 제한 하려면 Id 매개 변수 또는 Filter 매개 변수만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="dc715-108">예를 들어 글로벌 정책만 반환 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="dc715-109">Id가 "RedmondAccessPolicy" 인 사용자별 정책을 반환 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="dc715-110">사용자별 정책을 참조 하는 경우 태그 <STRONG>접두사</STRONG> 는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="dc715-111">접두사를 포함 하는이 구문도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="dc715-112">Get-CsExternalAccessPolicy – Id "tag: RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="dc715-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="dc715-113">전역 정책 (즉, 모든 사용자 단위 정책)을 제외한 모든 정책을 반환 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="dc715-114">다음 cmdlet은 전역 범위와 사용자 단위 (태그) 범위에 대해 모두 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="dc715-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dc715-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dc715-117">[가져오기-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dc715-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dc715-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dc715-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="dc715-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="dc715-122">이름에 관계 없이 다이얼 플랜은 기능적으로 말하는 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="dc715-123">이전 버전의 Lync Server와 함께 사용 되는 용어를 보존 하기 위해 전화 걸기 정책 등의 경우와 같은 방법으로는 <EM>다이얼 플랜</EM> 을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc715-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="dc715-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc715-124">See Also</span></span>


[<span data-ttu-id="dc715-125">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="dc715-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="dc715-126">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="dc715-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

