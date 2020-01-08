---
title: 사용자 id와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31f6b76b6c63b39bf22f456260f084736d481513
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40984571"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>사용자 id와 태그 범위를 사용 하는 비즈니스용 Skype Online의 cmdlet

 


사용자에 게 정책을 할당 하는 데 사용 되는 **허용-Cs** cmdlet에는 두 개의 식별자 인 사용자 Id (id 매개 변수)와 사용자별 정책 Id (PolicyName 매개 변수)가 필요 합니다. 예를 들어 음성 정책 RedmondVoicePolicy를 사용자: 진구 Myer에 할당 하려면 다음 명령을 사용 합니다.

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

사용자에 게 정책을 할당할 때 염두에 두어야 할 두 가지 사항이 있습니다. 첫째, 사용자별 정책만 할당할 수 있습니다. 전역 정책은 사용자에 게 할당할 수 없습니다. 예를 들어 다음 명령은 실패 합니다.

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

이 명령은 전역 정책을 할당할 필요가 없기 때문에 실패 합니다. 전역 정책을 사용 하 여 사용자를 관리 하려는 경우 해당 사용자에 게 사용자 단위 정책을 할당 하지 않도록 주의 하세요. 사용자에 게 할당 된 사용자별 정책이 없는 경우 사용자는 전역 정책을 사용 하 여 자동으로 관리 됩니다.


> [!NOTE]  
> 사용자가 이전에 사용자 기준 정책을 할당 한 경우 해당 정책을 할당 취소 하 고 사용자가 글로벌 정책에 의해 관리 되도록 하려면 어떻게 하나요? 이 경우 먼저 해당 사용자에 게 null 정책을 부여 하 여 사용자 단위 정책을 할당 취소 하는 다음 구문을 사용 합니다.<BR>Grant-CsVoicePolicy – Id ": 진구 Myer" – PolicyName $Null



두 번째, 사용자 단위 정책이 태그 범위에서 생성 된다는 점에 유의 하세요. 그러나 정책 이름을 지정할 때 태그 **접두사** 를 생략할 수 있습니다. 이러한 두 명령은 동일 합니다.

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

모든 사용자별 정책에 대 한 id를 반환 하려는 경우 (적어도 또는 음성 정책 등 지정 된 형식의 사용자 단위 정책은 모두), 다음과 같은 명령을 사용 합니다.

    Get-CsVoicePolicy -Filter "tag:*"

다음 cmdlet은 사용자 Id와 태그 범위를 모두 사용 합니다.

  - [부여-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [부여-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [부여-CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [부여-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [부여-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [부여-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

