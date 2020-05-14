---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. '
ms.openlocfilehash: bed342de3f602499f16b9f27ee0726f10d2c867e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "42048191"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트

SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.

- 트렁크에 미디어 우회를 설정할지 여부
- RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건
- SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부

비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 모음이 만들어집니다. 또한 관리자가 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스 전용)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다. 또한 관리자는 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet을 사용 하 여 트렁크가 사용자에 게 전화를 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 변환할 수 있는지 확인할 수 있습니다.

트렁크 구성 설정은 Windows PowerShell과 Test-CsTrunkConfiguration cmdlet을 사용해서만 테스트할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

**SIP 트렁크 구성 설정을 테스트 하려면**

다음 명령을 실행하면 레드몬드 사이트의 트렁크 구성 설정이 전화 번호(4255551212)를 올바로 변환할 수 있는지 확인할 수 있습니다.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
