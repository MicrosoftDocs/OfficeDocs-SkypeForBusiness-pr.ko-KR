---
title: '비즈니스용 Skype 서버: SIP 트렁크 구성 설정 수정'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: '요약: 제어판을 사용하여 SIP 트렁크 구성 설정을 수정하는 비즈니스용 Skype 서버 방법을 설명하는 문서입니다.'
ms.openlocfilehash: ada56be3cb0e9e8d1c1b5b607602cfd4b176beed
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387297"
---
# <a name="skype-for-business-server-modify-sip-trunk-configuration-settings"></a>비즈니스용 Skype 서버: SIP 트렁크 구성 설정 수정 
 
**요약:** 제어판을 사용하여 SIP 트렁크 구성 설정을 수정하는 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
  
SIP 트렁크 구성 설정은 중재 서버와 PSTN(Public Switched Telephone Network) 게이트웨이, 서비스 공급자의 IP-Public Branch eXchange(PBX) 또는 SBC(Session Border Controller) 간의 관계와 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.
  
- 트렁크에 미디어 우회를 설정할지 여부
    
- RTCP(Realtime Transport Control Protocol) 패킷이 전송되는 조건입니다.
    
- 각 트렁크에 SRTP(Secure Realtime Transport Protocol) 암호화가 필요한지 여부
    
설치 비즈니스용 Skype 서버 SIP 트렁크 구성 설정의 전역 컬렉션이 만들어집니다. 또한 관리자가 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스 전용)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다. 이러한 컬렉션은 나중에 제어판 또는 관리 셸을 사용하여 비즈니스용 Skype 서버 수 비즈니스용 Skype 서버 있습니다.
  
제어판을 사용하여 SIP 트렁크 구성 설정을 비즈니스용 Skype 서버 다음 옵션을 사용할 수 있습니다.
  
|**UI 설정**|**PowerShell 매개 변수**|**설명**|
|:-----|:-----|:-----|
|이름  <br/> |ID  <br/> |컬렉션에 대한 고유 식별자입니다. 이 속성은 읽기 전용이며 트렁크 구성 설정의 컬렉션에 대한 Identity를 변경할 수 없습니다.  <br/> |
|설명  <br/> |설명  <br/> |관리자가 설정에 대한 추가 정보를 저장할 수 있는 방법을 제공합니다(예: 트렁크 구성 용도).  <br/> |
|지원되는 최대 초기 대화 상자  <br/> |MaxEarlyDialogs  <br/> |서비스 공급자의 PSTN 게이트웨이, IP-PBX 또는 SBC(세션 경계 컨트롤러)가 Invite로 수신하여 중재 서버로 보낼 수 있는 분기 응답의 최대 개수입니다.  <br/> |
|암호화 지원 수준  <br/> |SRTPMode  <br/> | 중재 서버와 서비스 공급자 쪽 PSTN 게이트웨이, IP-PBX 또는 SBC 간의 미디어 트래픽을 보호하는 지원 수준을 나타냅니다. 미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다. 미디어 구성은 [New-CsMediaConfiguration](/powershell/module/skype/new-csmediaconfiguration) 및 [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration) cmdlet을 사용하여 설정됩니다. <br/>  허용되는 값은 다음과 같습니다. <br/>  필수: SRTP 암호화를 사용해야 합니다. <br/>  선택: 게이트웨이가 지원하는 경우 SRTP가 사용됩니다. <br/>  지원되지 않음: SRTP 암호화가 지원되지 않으므로 사용되지 않습니다. <br/>  SRTPMode는 게이트웨이가 TLS(전송 계층 보안)를 사용하도록 구성된 경우에만 사용됩니다. 게이트웨이가 TCP(Transmission Control Protocol)를 전송 프로토콜로 사용하여 구성된 경우 SRTPMode는 내부적으로 지원되지 않음으로 설정됩니다.<br/> |
|참조 지원  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |**게이트웨이에 대한 참조 전송 사용** 으로 설정된 경우 트렁크가 중재 서버에서 참조 요청 수신을 지원합니다.  <br/> **타사 통화 제어를 사용하여 참조 사용** 으로 설정된 경우 3pcc 프로토콜을 사용해서 전송 통화가 호스팅된 사이트를 우회하도록 허용할 수 있음을 나타냅니다. 3pcc는 "타사 제어"라고도 부르며, 발신자 쌍에 연결하기 위해 타사를 사용할 때 발생합니다(예: 교환이 사용자 A에서 사용자 B로의 통화를 연결할 때).<br/> |
|미디어 바이패스 사용  <br/> |EnableBypass  <br/> |이 트렁크에 대해 미디어 바이패스가 설정되었는지 여부를 나타냅니다. 미디어 바이패스는 **중앙 집중식 미디어 처리** 가 설정된 경우에만 설정할 수 있습니다.<br/> |
|중앙 집중식 미디어 처리  <br/> |ConcentratedTopology  <br/> |알려진 미디어 종료 지점이 있는지 여부를 나타냅니다. 알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료와 동일한 IP를 갖는 PSTN 게이트웨이를 들 수 있습니다.  <br/> |
|RTP 래칭 사용  <br/> |EnableRTPLatching  <br/> |SIP 트렁크가 RTP 래칭을 지원하는지 여부를 나타냅니다. RTP 래칭은 NAT(네트워크 주소 변환기) 장치 또는 방화벽을 통해 RTP/RTCP 연결을 설정하는 기술입니다.  <br/> |
|통화 기록 전달 사용  <br/> |ForwardCallHistory  <br/> |트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.  <br/> |
|P-Asserted-Identity 데이터 전달 사용  <br/> |ForwardPAI  <br/> |통화와 함께 PAI(P-Asserted-Identity) 헤더를 전달할지 여부를 나타냅니다. PAI 헤더는 발신자의 ID를 확인하기 위한 방법을 제공합니다.  <br/> |
|아웃바운드 라우팅 장애 조치(failover) 타이머 사용  <br/> |EnableFastFailoverTimer  <br/> |10초 내에 게이트웨이에서 응답되지 않은 아웃바운드 통화를 사용 가능한 다음 트렁크로 라우팅할지 여부를 나타냅니다. 추가 트렁크가 없으면 통화가 자동으로 삭제됩니다. 네트워크 및 게이트웨이 응답 속도가 느린 조직에서는 불필요하게 통화가 삭제될 가능성이 있습니다.  <br/> |
|연결된 PSTN 사용  <br/> |PSTNUsages  <br/> |트렁크에 지정된 PSTN 사용 컬렉션입니다.  <br/> |
|테스트할 변환 번호  <br/> |해당 없음  <br/> |트렁크 구성 설정에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.  <br/> |
|연결된 변환 규칙  <br/> |OutboundTranslationRulesList  <br/> |아웃바운드 라우팅에서 처리하는 통화(PBX 또는 PSTN 대상으로 라우팅되는 통화)에 적용되는 전화 번호 변환 규칙 컬렉션입니다.  <br/> |
|호출된 번호 변환 규칙  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |트렁크에 지정된 아웃바운드 통화 번호 변환 규칙의 컬렉션입니다.  <br/> |
|테스트할 전화 번호  <br/> |해당 없음  <br/> |변환 규칙에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.  <br/> |
|호출 중인 번호  <br/> |해당 없음  <br/> |테스트할 전화 번호가 발신자의 전화 번호인지를 나타냅니다.  <br/> |
|호출된 번호  <br/> |해당 없음  <br/> |테스트할 전화 번호가 수신 중인 사용자의 전화 번호인지를 나타냅니다.  <br/> |
   
> [!NOTE]
> Lync Server CsTrunkConfiguration cmdlet은 Lync Server 제어판에 나와 있지 않은 추가 속성을 지원합니다. 자세한 내용은 [Set-CsTrunkConfiguration](/powershell/module/skype/set-cstrunkconfiguration) cmdlet에 대한 도움말 항목을 참조하십시오.
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 SIP 트렁크 구성 설정을 비즈니스용 Skype 서버

1. 비즈니스용 Skype 서버 제어판에서 음성 라우팅을 **클릭** 한 다음 트렁 **크 구성을 클릭합니다**.
    
2. **트렁크 구성** 탭에서 수정할 트렁크 구성 설정을 두 번 클릭합니다. 설정 컬렉션은 한 번에 하나만 편집할 수 있습니다. 여러 컬렉션에서 동일 항목을 변경하려면 Windows PowerShell을 대신 사용하십시오.
    
3. 트 **렁크 구성 편집** 대화 상자에서 적절한 선택을 한 다음 확인을 **클릭합니다**.
    
4. 컬렉션의 **상태** 속성은 **커밋되지 않음** 으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제하려면 **커밋** 을 클릭한 후 **모두 커밋** 을 클릭합니다.
    
5. **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인** 을 클릭합니다.
    
6. 제어 **판 비즈니스용 Skype 서버 확인** 을 **클릭합니다**.
