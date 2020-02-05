---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버 관리 셸을 사용 하 여 SIP 트렁크 구성 설정을 테스트 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a85af538f5729310c75e57313b049dcb14d09542
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766911"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 테스트
 
**요약:** 비즈니스용 Skype 서버 관리 셸을 사용 하 여 SIP 트렁크 구성 설정을 테스트 하는 방법에 대해 알아봅니다.
  
SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. 이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.
  
- Trunks에서 미디어 바이패스를 사용 해야 하는지 여부
    
- RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.
    
- 각 트렁크에서 보안 실시간 전송 프로토콜 (SRTP) 암호화가 필요한 지 여부
    
비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다. 또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다. 또한 관리자는 Set-cstrunkconfiguration cmdlet을 사용 하 여 트렁크가 사용자에 게 전화를 거는 번호를 게이트웨이에서 처리할 수 있는 번호로 변환할 수 있는지 확인할 수 있습니다.
  
트렁크 구성 설정은 Windows PowerShell 및 [테스트 set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet을 사용 하 여 테스트할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 비즈니스용 Skype Server Management Shell의 원격 세션에서 실행할 수 있습니다.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>SIP 트렁크 구성 설정을 테스트 하려면

- 이 명령은 Redmond 사이트의 트렁크 구성 설정이 전화 거는 번호 4255551212를 올바르게 변환할 수 있는지 확인 합니다.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


