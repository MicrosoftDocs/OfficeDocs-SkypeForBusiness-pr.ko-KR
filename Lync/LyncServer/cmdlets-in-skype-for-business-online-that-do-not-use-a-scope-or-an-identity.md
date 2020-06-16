---
title: 범위 또는 id를 사용 하지 않는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that do not use a scope or an identity
ms:assetid: 9c50c732-3c64-4b6a-96fd-8f528eb739ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362824(v=OCS.15)
ms:contentKeyID: 56558839
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ade4dee78fff151530e0d76279fdbfaeade720b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755318"
---
# <a name="cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity"></a>범위 또는 id를 사용 하지 않는 비즈니스용 Skype Online의 cmdlet

 


허용 목록 및 차단 된 목록 (사용자가 통신할 수 있는 외부 조직에 따라 결정 되는 목록)을 수정할 때 사용 되는 cmdlet은 범위 또는 Id를 사용 하지 않습니다. **CsEdgeAllowAllKnownDomains** cmdlet에는 매개 변수가 없는 것이 사실에 해당 합니다. 범위나 Id 중 하나를 사용 하지 않는 cmdlet은 다음과 같습니다.

  - [CsEdgeAllowAllKnownDomains](https://technet.microsoft.com/library/jj994088\(v=ocs.15\))

  - [CsEdgeAllowList](https://technet.microsoft.com/library/jj994023\(v=ocs.15\))

  - [새-CsEdgeDomainPattern](https://technet.microsoft.com/library/jj994040\(v=ocs.15\))

**CsEdgeAllowList** Cmdlet과 **새-CsEdgeDomainPattern** cmdlet을 모두 사용 하 여 Domain 매개 변수를 포함 해야 합니다. 예를 들면 다음과 같습니다.

    $x = New-CsEdgeDomainPattern -Domain "fabrikam.com"

## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

