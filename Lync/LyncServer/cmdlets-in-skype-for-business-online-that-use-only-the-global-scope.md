---
title: 전역 범위만 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4a894c4a9c6e2913abb003c49094bc6d6868483
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001253"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>전역 범위만 사용 하는 비즈니스용 Skype Online의 cmdlet

 


여러 비즈니스용 Skype 온라인 설정은 *전역 범위*에서만 사용할 수 있습니다. 즉, 해당 테 넌 트에 할당 된 모든 사용자에 게 적용 되는 단일 설정 컬렉션이 있습니다. 각 테 넌 트에는 고유한 전역 설정 컬렉션이 있습니다. 전역 범위로 제한 되는 cmdlet을 사용 하는 경우 Identity 매개 변수는 선택 사항입니다. 예를 들어 다음과 같은 명령을 사용 하 여 모임 구성 설정을 검색할 수 있습니다.

    Get-CsMeetingConfiguration -Identity "global"

또는 Identity 매개 변수를 생략 하 고 대신 보다 간단한이 명령을 사용할 수도 있습니다.

    Get-CsMeetingConfiguration

모임 구성 설정의 전역 컬렉션은 하나만 있으므로 두 명령은 정확히 같은 정보를 반환 합니다. 또한 **Set-Cs** cmdlet 중 하나를 사용 하는 경우 Identity 매개 변수를 생략할 수 있습니다. 다음 두 명령은 동일 합니다.

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

Identity 매개 변수를 포함 하지 않으면 기본적으로 Windows PowerShell이 전역 컬렉션을 수정 하기 때문에 두 명령이 동일 합니다.

다음 cmdlet은 전역 범위 에서만 작동 합니다.

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))

  - [Get-csprivacyconfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))

  - [CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))

  - [CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))

  - [CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))

  - [Get-Csten앤틸리스 공급자](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))

  - [Set-csvoicepolicy을 제거 합니다.](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))

  - [Get-csprivacyconfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))

**Set-csvoicepolicy** cmdlet은 변칙 항목에 해당 합니다. 먼저,이 cmdlet은 Identity 매개 변수를 포함 해야 합니다.

    Remove-CsVoicePolicy -Identity "global"

둘째로, **set-csvoicepolicy** cmdlet은 실제로 전역 음성 정책을 삭제 하지 않습니다. 비즈니스용 Skype Online에서는 전역 정책 또는 구성 설정을 삭제할 수 없습니다. Cmdlet이 수행 하는 작업을 통해 전역 음성 정책의 모든 속성을 기본값으로 다시 설정할 수 있습니다. 예를 들어 기본적으로 AllowCallForwarding 속성은 False로 설정 됩니다. 그러나 AllowCallForwarding이 수정 되었을 수 있으며 값이 True로 설정 됩니다. **Set-csvoicepolicy** cmdlet을 실행 하면 AllowCallForwarding 속성은 기본값으로, False로 돌아갑니다. 다음 표에서는이 시나리오를 요약 하 여 설명 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding 값</th>
<th>시나리오</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>False</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="even">
<td><p>참</p></td>
<td><p>글로벌 정책이 수정 된 후</p></td>
</tr>
<tr class="odd">
<td><p>False</p></td>
<td><p><strong>Set-csvoicepolicy cmdlet을</strong> 실행 한 후</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

