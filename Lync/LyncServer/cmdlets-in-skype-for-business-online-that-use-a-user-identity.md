---
title: 사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use a user identity
ms:assetid: be87409f-6372-4c70-91ac-6ef13dfbe65a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362842(v=OCS.15)
ms:contentKeyID: 56558859
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce46e700a65f00625aeebad1032c54a5affeaa19
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40983138"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity"></a>사용자 id를 사용 하는 비즈니스용 Skype Online의 cmdlet

 


비즈니스용 Skype Online에는 개별 사용자 Id를 참조 하는 여러 가지 방법이 있습니다.

  - 사용자의 Active Directory 도메인 서비스 표시 이름을 사용 합니다. 예를 들면 다음과 같습니다.
    
        -Identity "Ken Myer"

  - 사용자의 SIP 주소를 사용 합니다. 예를 들면 다음과 같습니다.
    
        -Identity "sip:kenmyer@litwareinc.com"

  - 사용자의 UPN을 사용 합니다. 예를 들면 다음과 같습니다.
    
        -Identity " kenmyer@litwareinc.com"

  - 사용자의 Active Directory 도메인 서비스 고유 이름을 사용 합니다. 예를 들면 다음과 같습니다.
    
        -Identity "CN=48ebd1ba-95d4-460c-b751-811ebf0c4611,OU=fa8226f5-14fa-46da-8 236-039b25bc7a27,OU=Lync Online Tenants,DC=litwareinc,DC=com"

다음 cmdlet은 사용자 Id를 받아들입니다.

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204723\(v=ocs.15\))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205062\(v=ocs.15\))

  - [Get-C(Um연락처)](https://technet.microsoft.com/en-us/library/gg412725\(v=ocs.15\))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj205277\(v=ocs.15\))

  - [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/jj994026\(v=ocs.15\))

  - [Get-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398978\(v=ocs.15\))

  - [신규-C또는 Um연락처](https://technet.microsoft.com/en-us/library/gg398139\(v=ocs.15\))

  - [제거-C간 Umcontact](https://technet.microsoft.com/en-us/library/gg398946\(v=ocs.15\))

  - [제거-CsUserAcp](https://technet.microsoft.com/en-us/library/gg398982\(v=ocs.15\))

  - [Set-C간 Umcontact](https://technet.microsoft.com/en-us/library/gg412944\(v=ocs.15\))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/jj204831\(v=ocs.15\))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/gg413018\(v=ocs.15\))

**Cs** cmdlet 중 하나를 호출할 때 사용자 id를 지정 하지 않아도 된다는 점에 유의 하세요. 이 경우 cmdlet은 지정 된 항목의 모든 인스턴스를 반환 합니다. 예를 들어이 명령은 비즈니스용 Skype Online에 대해 사용 하도록 설정 된 모든 사용자에 대 한 정보를 반환 합니다.

    Get-CsOnlineUser

Id 매개 변수는 특정 사용자에 대 한 정보를 반환 하려는 경우에만 필요 합니다.

    Get-CsOnlineUser -Identity "Ken Myer"

## <a name="see-also"></a>참고 항목


[비즈니스용 Skype Online의 id, 범위 및 테 넌 트](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

