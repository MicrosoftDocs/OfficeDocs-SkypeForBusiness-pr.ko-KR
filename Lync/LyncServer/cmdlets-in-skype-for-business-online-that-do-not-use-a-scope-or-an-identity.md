---
title: 범위 또는 id를 사용 하지 않는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7f6632640277a6a99626c18f458100f6a8cea0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985625"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a><span data-ttu-id="d68aa-102">범위 또는 id를 사용 하지 않는 비즈니스용 Skype Online의 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d68aa-102">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>

 


<span data-ttu-id="d68aa-103">허용 목록 및 차단 된 목록을 수정할 때 사용 되는 cmdlet (사용자가 통신 하도록 허용 된 외부 조직에 따라 결정 되는 목록)은 범위 또는 Id를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d68aa-103">The cmdlets used when modifying the allowed lists and blocked lists (lists that determine which outside organizations your users are allowed to communicate with) do not use either a scope or an Identity.</span></span> <span data-ttu-id="d68aa-104">사실, **CsEdgeAllowAllKnownDomains** cmdlet에는 매개 변수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d68aa-104">In fact, the **New-CsEdgeAllowAllKnownDomains** cmdlet does not have any parameters whatsoever.</span></span> <span data-ttu-id="d68aa-105">범위 또는 Id 중 하나를 사용 하지 않는 cmdlet은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d68aa-105">The cmdlets that do not use either a scope or an Identity are:</span></span>

  - <span data-ttu-id="d68aa-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d68aa-106">[New-CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/en-us/library/jj994088\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d68aa-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d68aa-107">[New-CsEdgeAllowList](https://technet.microsoft.com/en-us/library/jj994023\(v=ocs.15\))</span></span>

  - <span data-ttu-id="d68aa-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d68aa-108">[New-CsEdgeDomainPattern](https://technet.microsoft.com/en-us/library/jj994040\(v=ocs.15\))</span></span>

<span data-ttu-id="d68aa-109">**새 CsEdgeAllowList** Cmdlet 및 **새-CsEdgeDomainPattern** cmdlet을 모두 사용 하 여 Domain 매개 변수를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68aa-109">Note that, with both the **New-CsEdgeAllowList** cmdlet and the **New-CsEdgeDomainPattern** cmdlet, you must include the Domain parameter.</span></span> <span data-ttu-id="d68aa-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d68aa-110">For example:</span></span>

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a><span data-ttu-id="d68aa-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d68aa-111">See Also</span></span>


[<span data-ttu-id="d68aa-112">비즈니스용 Skype Online의 id, 범위 및 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="d68aa-112">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="d68aa-113">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="d68aa-113">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

