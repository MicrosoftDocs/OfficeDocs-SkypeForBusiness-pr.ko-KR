---
title: 사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet
description: 사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet입니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f838317f8b2779de862eb2df82ae1b348871e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545654"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet

 


비즈니스용 Skype Online에서 개별 사용자 Id를 참조 하는 방법에는 여러 가지가 있습니다.

  - 사용자의 Active Directory 도메인 서비스 표시 이름을 사용 합니다. 예제:
    
        -Identity "Ken Myer"

  - 사용자의 SIP 주소를 사용 합니다. 예제:
    
        -Identity "sip:kenmyer@litwareinc.com"

  - 사용자의 UPN을 사용 합니다. 예제:
    
        -Identity " kenmyer@litwareinc.com"

  - 사용자의 Active Directory 도메인 서비스 고유 이름을 사용 합니다. 예제:
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

사용자 Id를 허용 하는 cmdlet은 다음과 같습니다.

  - [사용 안 함-Enable-csmeetingroom](https://technet.microsoft.com/library/jj204723\(v=ocs.15\))

  - [Enable-Enable-csmeetingroom](https://technet.microsoft.com/library/jj205062\(v=ocs.15\))

  - [Get-CsExUmContact](https://technet.microsoft.com/library/gg412725\(v=ocs.15\))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/jj205277\(v=ocs.15\))

  - [Get-csonlineuser](https://technet.microsoft.com/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/library/gg398978\(v=ocs.15\))

  - [새 전자 메일 주소](https://technet.microsoft.com/library/gg398139\(v=ocs.15\))

  - [제거-CsExUmContact](https://technet.microsoft.com/library/gg398946\(v=ocs.15\))

  - [제거-CsUserAcp](https://technet.microsoft.com/library/gg398982\(v=ocs.15\))

  - [Set-CsExUmContact](https://technet.microsoft.com/library/gg412944\(v=ocs.15\))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/jj204831\(v=ocs.15\))

  - [설정-CsUserAcp](https://technet.microsoft.com/library/gg413018\(v=ocs.15\))

사용자 Id를 지정 하지 않아도 되는 경우에는 **Cs** cmdlet 중 하나를 호출할 수 있습니다. 이 경우 cmdlet은 지정 된 항목의 모든 인스턴스를 반환 합니다. 예를 들어이 명령은 비즈니스용 Skype 온라인을 사용할 수 있도록 설정 된 모든 사용자에 대 한 정보를 반환 합니다.

    Get-CsOnlineUser

Identity 매개 변수는 특정 사용자에 대 한 정보를 반환 하려는 경우에만 필요 합니다.

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[비즈니스용 Skype 온라인 cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

