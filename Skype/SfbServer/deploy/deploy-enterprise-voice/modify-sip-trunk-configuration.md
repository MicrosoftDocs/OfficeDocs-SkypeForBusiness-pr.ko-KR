---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: '요약: 비즈니스용 Skype 서버 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 6db2ddcf0155a599d8604bce2e3d5b5d34d6df20
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240511"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 수정
 
**요약:** 비즈니스용 Skype 서버 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하는 방법에 대해 알아봅니다.
  
SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. 이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.
  
- Trunks에서 미디어 바이패스를 사용 해야 하는지 여부
    
- RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.
    
- 각 트렁크에서 보안 실시간 전송 프로토콜 (SRTP) 암호화가 필요한 지 여부
    
비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다. 또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다. 나중에 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용 하 여 이러한 컬렉션을 수정할 수 있습니다.
  
비즈니스용 Skype Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하는 경우 다음 옵션을 사용할 수 있습니다.
  
|**UI 설정**|**PowerShell 매개 변수**|**설명**|
|:-----|:-----|:-----|
|이름  <br/> |Identity  <br/> |컬렉션의 고유 식별자입니다. 이 속성은 읽기 전용입니다. 트렁크 구성 설정 모음의 Id는 변경할 수 없습니다.  <br/> |
|설명  <br/> |설명  <br/> |관리자가 설정에 대 한 추가 정보 (예: 트렁크 구성의 용도)를 저장할 수 있는 방법을 제공 합니다.  <br/> |
|지원 되는 최대 빠른 대화 상자  <br/> |Maxlya 대화 상자  <br/> |서비스 공급자의 PSTN 게이트웨이, IP PBX 또는 SBC가 조정 서버로 전송 된 초대에 받을 수 있는 분기 응답의 최대 수입니다.  <br/> |
|암호화 지원 수준  <br/> |SRTPMode  <br/> | 서비스 공급자에서 중재 서버와 PSTN 게이트웨이, IP PBX 또는 SBC 간의 미디어 트래픽 보호에 대 한 지원 수준을 나타냅니다. 미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다. 미디어 구성은 [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) 및 [CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) cmdlet을 사용 하 여 설정 합니다. <br/>  사용 가능한 값은 다음과 같습니다. <br/>  필수: SRTP 암호화를 사용 해야 합니다. <br/>  선택 사항: 게이트웨이에서 지 원하는 경우 SRTP가 사용 됩니다. <br/>  지원 되지 않음: SRTP 암호화가 지원 되지 않으므로 사용 되지 않습니다. <br/>  SRTPMode는 게이트웨이가 TLS (전송 계층 보안)를 사용 하도록 구성 된 경우에만 사용 됩니다. 게이트웨이가 TCP (전송 제어 프로토콜)를 전송으로 구성한 경우에는 SRTPMode가 내부적으로 지원 되지 않는 것으로 설정 됩니다. <br/> |
|지원 참조  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |보내기를 사용 하도록 설정 하는 경우 **게이트웨이를 참조**하는 경우 트렁크가 조정 서버의 수신 참조 요청을 지원함을 나타냅니다.  <br/> 이 기능을 사용 하도록 설정 하면 **타사 통화 제어를 사용**하는 것이 3pcc 프로토콜을 사용 하 여 호스팅된 사이트를 우회 하도록 할 수 있음을 나타냅니다. 3pcc는 "제3자 제어"라고도 하며, 제3자(예: A 사용자로부터 B 사용자에게 전화를 거는 교환원)를 통해 발신자 쌍을 연결하는 경우에 적용됩니다.  <br/> |
|미디어 바이패스 사용  <br/> |EnableBypass  <br/> |이 트렁크에 미디어 바이패스를 사용 하도록 설정 했는지 여부를 나타냅니다. 미디어 바이패스는 **중앙 집중화 된 미디어 처리** 도 사용할 수 있는 경우에만 사용 가능 합니다. <br/> |
|중앙 집중화 된 미디어 처리  <br/> |ConcentratedTopology  <br/> |잘 알려진 미디어 종료 지점이 있는지 여부를 나타냅니다. 알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료의 IP와 동일한 PSTN 게이트웨이가 있습니다.  <br/> |
|RTP latching 사용  <br/> |EnableRTPLatching  <br/> |SIP 트렁크가 RTP 래치를 지원하는지 여부를 나타냅니다. RTP 래치는 NAT(Network Address Translator) 장치 또는 방화벽을 통한 RTP/RTCP 연결을 설정하는 기술입니다.  <br/> |
|착신 통화 기록 사용  <br/> |ForwardCallHistory  <br/> |트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.  <br/> |
|앞으로 P-어설션된-Id 데이터 사용  <br/> |ForwardPAI  <br/> |PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다.  <br/> |
|아웃 바운드 라우팅 장애 조치 타이머 사용  <br/> |Enablefailovertimer  <br/> |게이트웨이에서 응답 하지 않은 아웃 바운드 통화가 10 초 이내에 사용 가능한 다음 트렁크로 라우팅되도록 할지 여부를 표시 합니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다. 느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다.  <br/> |
|연결 된 PSTN 용도  <br/> |PSTNUsages  <br/> |트렁크에 할당된 PSTN 사용 컬렉션입니다.  <br/> |
|테스트를 위해 번역 된 번호  <br/> |해당 없음  <br/> |트렁크 구성 설정의 임시 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.  <br/> |
|연결 된 번역 규칙  <br/> |OutboundTranslationRulesList  <br/> |아웃 바운드 라우팅이 처리 하는 통화에 적용 되는 전화 번호 번역 규칙 (PBX 또는 PSTN 대상으로 라우팅된 통화)을 수집 합니다.  <br/> |
|전화 번호 번역 규칙  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |트렁크에 할당된 아웃바운드 호출 번호 변환 규칙 컬렉션입니다.  <br/> |
|테스트할 전화 번호  <br/> |해당 없음  <br/> |번역 규칙의 특별 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.  <br/> |
|전화 번호  <br/> |해당 없음  <br/> |테스트 하려는 전화 번호가 발신자의 전화 번호 임을 나타냅니다.  <br/> |
|전화 번호  <br/> |해당 없음  <br/> |전화 번호가 통화 중인 사람의 전화 번호 라는 것을 나타냅니다.  <br/> |
   
> [!NOTE]
> Lync Server Set-cstrunkconfiguration cmdlet은 Lync Server 제어판에 표시 되지 않는 추가 속성을 지원 합니다. 자세한 내용은 [Set-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하려면

1. 비즈니스용 Skype 서버 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.
    
2. **트렁크 구성** 탭에서 수정할 트렁크 구성 설정을 두 번 클릭 합니다. 한 번에 하나의 설정 컬렉션만 편집할 수 있습니다. 여러 컬렉션에서 동일한 변경 작업을 수행 하려면 Windows PowerShell을 대신 사용 합니다.
    
3. **트렁크 구성 편집** 대화 상자에서 적절 하 게 선택 하 고 **확인**을 클릭 합니다.
    
4. 컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다. 변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.
    
5. 커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.
    
6. **비즈니스용 Skype Server 제어판** 대화 상자에서 **확인을**클릭 합니다.
    

