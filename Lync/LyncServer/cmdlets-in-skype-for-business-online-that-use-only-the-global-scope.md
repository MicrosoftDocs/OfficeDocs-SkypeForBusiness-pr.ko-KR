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
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a>전역 범위만 사용 하는 비즈니스용 Skype Online의 cmdlet

 


여러 비즈니스용 Skype Online 설정은 *전역 범위*에서만 사용할 수 있습니다. 즉, 해당 테 넌 트에 할당 된 모든 사용자에 게 적용 되는 단일 설정 컬렉션이 있습니다. 각 테 넌 트에는 고유한 전역 설정 컬렉션이 있습니다. 전역 범위로 제한 되는 cmdlet을 사용 하는 경우 Identity 매개 변수는 선택 사항입니다. 예를 들어 모임 구성 설정을 검색 하려면 다음 명령을 사용할 수 있습니다.

    Get-CsMeetingConfiguration -Identity "global"

또는 Id 매개 변수를 생략 하 고 대신이 간단한 명령을 사용할 수도 있습니다.

    Get-CsMeetingConfiguration

모임 구성 설정에는 전역 컬렉션이 하나만 있으므로 두 명령은 정확히 동일한 정보를 반환 합니다. **Set Cs** cmdlet 중 하나를 사용 하는 경우 id 매개 변수를 생략할 수도 있습니다. 이러한 두 명령은 동일 합니다.

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

두 명령은 기본적으로 Id 매개 변수를 포함 하지 않는 경우 Windows PowerShell이 전역 컬렉션을 수정 하기 때문에 동일 합니다.

다음 cmdlet은 전역 범위 에서만 작동 합니다.

  - [Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))

  - [Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))

  - [Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))

  - [Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))

  - [Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))

  - [Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))

  - [Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))

  - [제거-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))

**제거-CsVoicePolicy** cmdlet은 변칙의 일부입니다. 먼저,이 cmdlet에서는 Id 매개 변수를 포함 해야 합니다.

    Remove-CsVoicePolicy -Identity "global"

두 번째, **CsVoicePolicy** cmdlet은 전역 음성 정책을 실제로 삭제 하지 않습니다. 비즈니스용 Skype Online에서는 전역 정책 또는 구성 설정을 삭제할 수 없습니다. Cmdlet이 수행 하는 작업은 전역 음성 정책의 모든 속성을 기본값으로 재설정할 수 있도록 합니다. 예를 들어 AllowCallForwarding 전환 속성은 기본적으로 False로 설정 됩니다. 그러나 AllowCallForwarding 수정 되었을 수 있으며, 이제 값이 True로 설정 됩니다. **CsVoicePolicy** cmdlet을 실행 하면 AllowCallForwarding 전환 속성이 기본값으로 전환 됩니다: False. 다음 표에는이 시나리오가 요약 되어 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>AllowCallForwarding 전환 값</th>
<th>시나리오</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>해제</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="even">
<td><p>False</p></td>
<td><p>전역 정책이 수정 된 후</p></td>
</tr>
<tr class="odd">
<td><p>해제</p></td>
<td><p><strong>Remove-CsVoicePolicy cmdlet을</strong> 실행 한 후</p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

