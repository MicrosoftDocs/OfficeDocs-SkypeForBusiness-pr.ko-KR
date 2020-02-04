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

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>비즈니스용 Skype Online의 id, 범위 및 테 넌 트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-03-09_

비즈니스용 Skype Online을 관리 하는 데 사용 되는 많은 Windows PowerShell cmdlet은 관리 하려는 항목에 대 한 구체적인 정보를 필요로 합니다. 예를 들어, [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet을 실행 하는 경우 관리 하려는 사용자를 표시 해야 합니다. 이렇게 하는 것이 좋습니다. 관리 하려는 사용자 계정을 명시적으로 지정 하지 않는 한, **Set CsUserAcp** cmdlet은 사용자의 오디오 회의 정보를 수정 해야 하는 것을 알 수 없습니다. 이러한 이유로, **Set CsUserAcp** cmdlet을 실행할 때마다 id 매개 변수를 포함 하 고 수정할 사용자 계정의 id를 입력 해야 합니다.

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

용어 *id* 가 항상 사용자 계정의 id를 참조 하는 경우 혼란이 발생 하는 경우는 거의 없습니다. 사용자, 연락처 등을 처리 하는 경우 Id는 개별 사용자 자체를 가리킵니다. 그러나 사용자 계정 외의 항목에도 Id가 있습니다. 비즈니스용 Skype Online 서비스의 구성 요소 (정책, 구성 설정 등)를 처리 하는 경우 Id 라는 용어는 약간 다른 의미입니다. 예를 들어 다음 명령을 고려해 보겠습니다.

    Get-CsMeetingConfiguration -Identity "global"

이 경우 Id "global"은 모임 구성 설정의 범위를 나타냅니다. *범위* 는 비즈니스용 Skype Online (및 Lync Server)에서 관리 구를 지정 하는 데 사용 되는 용어입니다. 기본적으로 정책 및 설정에는 항상 전역 범위가 있습니다. 비즈니스용 Skype Online 계정을 처음 설정 하는 경우, 기본적으로 전역 정책 및 설정 (전역 모임 구성 설정, 전역 외부 액세스 정책, 전역 다이얼 플랜 등)의 모음을 갖게 됩니다.

Microsoft Lync Server 2010에서 이러한 전역 정책과 설정이 도입 되어 모든 사용자와 모든 구성 요소가 항상 관리 되는 것을 방지할 수 있습니다. 이는 Microsoft Office Communicator 2007 R2에 반드시 적용 되는 것은 아닙니다. 시스템에 액세스 한 방법에 따라 일반적으로 그룹 정책을 사용자 계정에 적용할 수 없기 때문에 거의 관리 되지 않는 상태가 될 수 있습니다. 이와 대조적으로 Lync Server와 비즈니스용 Skype Online에서는 아무것도 유지 관리 되지 않습니다. 이는 다른 방법 대신 전역 정책과 설정이 항상 적용 되기 때문입니다.

"어떤 것이 든" 말은 무엇을 의미 하나요? 비즈니스용 Skype Online의 경우 *태그 범위*또는 관리의 구에 정책을 만들 수 있습니다. 태그 범위 ( *사용자 단위 범위*라고도 함)에서 만든 정책은 전역 범위에서 만든 정책 보다 우선 합니다. 즉, 사용자 단위 정책은 항상 글로벌 정책에 우선 합니다. 예를 들어 외부 사용자 액세스 정책이 두 개 있을 수 있습니다. 전역 정책은 사용자가 Windows Live와 같은 IM (공용 인스턴트 메시징) 공급자에 계정이 있는 사용자와 통신 하지 못하도록 합니다. 사용자별 정책, AllowPublicIMCommunication는 공용 IM 공급자와의 통신을 허용 합니다.

또한: 진구 Myer 및 Pilar Ackerman 등 두 명의 사용자가 있을 수 있습니다. : 진구 Myer에 사용자 단위 정책이 할당 되었습니다. Pilar Ackerman에는 사용자 단위 정책이 할당 되지 않았습니다. 즉, 전역 외부 액세스 정책에 의해 관리 됩니다. 다음 표에는 공용 IM 공급자와 통신할 수 있는 사용자 (있는 경우)가 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>정책 설정</th>
<th>: 진구 Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>공용 IM 공급자에 대 한 전역 정책 설정</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>공용 IM 공급자에 대 한 사용자별 정책 설정</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>사용자가 공용 IM 공급자와 통신할 수 있습니다.</p></td>
<td><p>예</p></td>
<td><p>아니요</p></td>
</tr>
</tbody>
</table>


본 바와 같이: 진구 Myer는 공용 IM 공급자와 통신할 수 있습니다. 이는 자신에 게 할당 된 사용자별 정책 설정이 전역 정책의 설정을 재정의 하기 때문입니다. Pilar Ackerman은 공용 IM 공급자와 통신할 수 없습니다. 이것은 그녀는 글로벌 정책에 의해 관리 되므로 글로벌 정책은 그러한 통신을 금지 하기 때문입니다.

사용자 단위 정책은 Office 365 지원에서 만들어야 합니다. 정책을 만든 후에는 적절 한 **허용 Cs** cmdlet (예: [CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy))을 사용 하 여 사용자에 게 할당을 할당할 수 있습니다. 정책 Id는 항상 태그 **접두사로**시작 되므로 사용자 단위 정책은 쉽게 식별할 수 있습니다. 예를 들면 다음과 같습니다.

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> 태그 <STRONG>접두사</STRONG> 는 Lync Server 2010의 초기 개발 날짜에 날짜를 다시 지정 합니다. 이러한 일 동안 사용자 단위 정책은 <EM>태그 정책</EM> 이라고 하 고 태그 <STRONG>접두사로</STRONG>식별 되었습니다. 이러한 정책은 이제 <EM>사용자 단위 정책</EM>보다 정확 하 게 사용 되며 태그 범위는 <EM>사용자 단위 범위</EM>보다 더 정확 하 게 간주 됩니다. 그러나 기술적인 이유로 태그 <STRONG>접두사</STRONG> 는 변경 되지 않았습니다.



</div>

비즈니스용 Skype Online 및 Windows PowerShell을 사용할 때 사용 되는 다른 주요 용어는 *테 넌 트*입니다. 비즈니스용 Skype Online 계정을 설정 하면 새 배포에 다음과 유사한 전역 고유 식별자 (GUID) 인 테 넌 트 ID 번호가 할당 됩니다.

    bf19b7db-6960-41e5-a139-2aa373474354

비즈니스용 Skype Online cmdlet 중 일부는 cmdlet을 실행할 때마다 테 넌 트 ID를 입력 해야 합니다. 테 넌 트에 로그인 한 경우에도 테 넌 트 ID를 입력 해야 합니다. 다행히 테 넌 트 ID를 memorize 필요가 없습니다. 다음 Windows PowerShell 명령을 실행 하 여 언제 든 지 테 넌 트 ID를 검색할 수 있습니다.

    Get-CsTenant | Select-Object TenantId

물론 전역 범위와 사용자 단위 범위 (또는 태그 범위) 간의 차이를 알고 있는 경우에만 전투의 반만 사용 됩니다. 이러한 범위를 사용할 수 있는 경우에는 언제 든 지 아는 것도 중요 합니다. Id 및 테 넌 트 매개 변수의 경우에도 마찬가지입니다. 다음 항목에서는 여러 비즈니스용 Skype Online cmdlet이 Id, 범위 및 테 넌 트 매개 변수를 사용 하는 방법을 설명 합니다.

  - [전역 범위만 사용 하는 비즈니스용 Skype Online의 cmdlet](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [전역 범위와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [사용자 id와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [테 넌 트 매개 변수를 사용 하는 비즈니스용 Skype Online의 cmdlet](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [회의 공급자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [범위 또는 id를 사용 하지 않는 비즈니스용 Skype Online의 cmdlet](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

