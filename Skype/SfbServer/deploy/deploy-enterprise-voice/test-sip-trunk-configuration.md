---
title: '비즈니스용 Skype 서버: SIP 트렁크 구성 설정 테스트'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '요약: 관리 셸을 사용하여 SIP 트렁크 구성 설정을 테스트하는 비즈니스용 Skype 서버 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 19e0ad72b33d6ebbd5411fb269c3cdcbf2849a18
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772759"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>비즈니스용 Skype 서버: SIP 트렁크 구성 설정 테스트
 
**요약:** 비즈니스용 Skype 서버 관리 셸을 사용하여 SIP 트렁크 구성 설정을 테스트하는 방법을 확인합니다.
  
SIP 트렁크 구성 설정은 중재 서버와 PSTN(Public Switched Telephone Network) 게이트웨이, 서비스 공급자의 IP-Public Branch eXchange(PBX) 또는 SBC(Session Border Controller) 간의 관계와 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.
  
- 트렁크에서 미디어 우회를 사용하도록 설정해야 하는지 여부
    
- RTCP(Realtime Transport Control Protocol) 패킷이 전송되는 조건
    
- 각 트렁크에 SRTP(Secure Realtime Transport Protocol) 암호화가 필요한지 여부
    
설치 비즈니스용 Skype 서버 SIP 트렁크 구성 설정의 전역 컬렉션이 만들어집니다. 또한 관리자는 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다. 관리자는 또한 Test-CsTrunkConfiguration cmdlet을 사용하여 트렁크가 사용자가 전화를 걸 때 번호를 게이트웨이에서 처리할 수 있는 번호로 변환할 수 있는지 확인할 수 있습니다.
  
트렁크 구성 설정은 Windows PowerShell과 [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration) cmdlet을 사용해서만 테스트할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 실행할 비즈니스용 Skype 서버 있습니다.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>SIP 트렁크 구성 설정을 테스트하려면

- 다음 명령을 실행하면 레드몬드 사이트의 트렁크 구성 설정이 전화 번호(4255551212)를 올바로 변환할 수 있는지 확인할 수 있습니다.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
