---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 수정
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
ms.openlocfilehash: 5d87c9be3cbc609713f9ee8184cfe750ba5180b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036246"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정 수정

SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.

- 트렁크에 미디어 우회를 설정할지 여부
- RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건
- SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부

비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 모음이 만들어집니다. 또한 관리자가 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스 전용)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다. 이러한 컬렉션은 나중에 비즈니스용 Skype 서버 제어판 또는 Windows PowerShell을 사용 하 여 수정할 수 있습니다.

비즈니스용 Skype 서버 서버 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정할 때는 다음 옵션을 사용할 수 있습니다.

|UI 설정 |PowerShell 매개 변수 |설명 |
|--|--|--|
|이름|ID|컬렉션에 대한 고유 식별자입니다. 이 속성은 읽기 전용이며 트렁크 구성 설정의 컬렉션에 대한 Identity를 변경할 수 없습니다.|
|설명|설명|관리자가 설정에 대한 추가 정보를 저장할 수 있는 방법을 제공합니다(예: 트렁크 구성 용도).|
|지원되는 최대 초기 대화 상자|MaxEarlyDialogs|서비스 공급자의 PSTN 게이트웨이, IP-PBX 또는 SBC(세션 경계 컨트롤러)가 Invite로 수신하여 중재 서버로 보낼 수 있는 분기 응답의 최대 개수입니다.|
|암호화 지원 수준|SRTPMode|중재 서버와 서비스 공급자 쪽 PSTN 게이트웨이, IP-PBX 또는 SBC 간의 미디어 트래픽을 보호하는 지원 수준을 나타냅니다. 미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다. 미디어 구성은 Get-csmediaconfiguration 및 Get-csmediaconfiguration cmdlet을 사용 하 여 설정 됩니다.<br/>사용 가능한 값은 다음과 같습니다.<br/><br/>**필수**: SRTP 암호화를 사용 해야 합니다.<br/>**선택**: 게이트웨이가 지 원하는 경우 SRTP가 사용 됩니다.<br/>**지원 되지 않음**: SRTP 암호화가 지원 되지 않으므로 사용 되지 않습니다.<br/><br/>SRTPMode는 게이트웨이가 TLS(전송 계층 보안)를 사용하도록 구성된 경우에만 사용됩니다. 게이트웨이가 TCP(Transmission Control Protocol)를 전송 프로토콜로 사용하여 구성된 경우 SRTPMode는 내부적으로 지원되지 않음으로 설정됩니다.|
|참조 지원|Enable3pccRefer<br/>EnableReferSupport|**게이트웨이에 대한 참조 전송 사용**으로 설정된 경우 트렁크가 중재 서버에서 참조 요청 수신을 지원합니다.<br/>**타사 통화 제어를 사용하여 참조 사용**으로 설정된 경우 3pcc 프로토콜을 사용해서 전송 통화가 호스팅된 사이트를 우회하도록 허용할 수 있음을 나타냅니다. 3pcc는 "타사 제어"라고도 부르며, 발신자 쌍에 연결하기 위해 타사를 사용할 때 발생합니다(예: 교환이 사용자 A에서 사용자 B로의 통화를 연결할 때).|
|미디어 바이패스 사용|EnableBypass|이 트렁크에 대해 미디어 바이패스가 설정되었는지 여부를 나타냅니다. 미디어 바이패스는 **중앙 집중식 미디어 처리**가 설정된 경우에만 설정할 수 있습니다.|
|중앙 집중식 미디어 처리|ConcentratedTopology|알려진 미디어 종료 지점이 있는지 여부를 나타냅니다. 알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료와 동일한 IP를 갖는 PSTN 게이트웨이를 들 수 있습니다.|
|RTP 래칭 사용|EnableRTPLatching|SIP 트렁크가 RTP 래칭을 지원하는지 여부를 나타냅니다. RTP 래칭은 NAT(네트워크 주소 변환기) 장치 또는 방화벽을 통해 RTP/RTCP 연결을 설정하는 기술입니다.|
|통화 기록 전달 사용|ForwardCallHistory|트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.|
|P-Asserted-Identity 데이터 전달 사용|ForwardPAI|통화와 함께 PAI(P-Asserted-Identity) 헤더를 전달할지 여부를 나타냅니다. PAI 헤더는 발신자의 ID를 확인하기 위한 방법을 제공합니다.|
|아웃바운드 라우팅 장애 조치(failover) 타이머 사용|EnableFastFailoverTimer|10초 내에 게이트웨이에서 응답되지 않은 아웃바운드 통화를 사용 가능한 다음 트렁크로 라우팅할지 여부를 나타냅니다. 추가 트렁크가 없으면 통화가 자동으로 삭제됩니다. 네트워크 및 게이트웨이 응답 속도가 느린 조직에서는 불필요하게 통화가 삭제될 가능성이 있습니다.|
|연결된 PSTN 사용|PSTNUsages|트렁크에 지정된 PSTN 사용 컬렉션입니다.|
|테스트할 변환 번호|해당 없음|트렁크 구성 설정에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.|
|연결된 변환 규칙|OutboundTranslationRulesList|아웃바운드 라우팅에서 처리하는 통화(PBX 또는 PSTN 대상으로 라우팅되는 통화)에 적용되는 전화 번호 변환 규칙 컬렉션입니다.|
|호출된 번호 변환 규칙|OutboundCallingNumberTranslationRulesList|트렁크에 지정된 아웃바운드 통화 번호 변환 규칙의 컬렉션입니다.|
|테스트할 전화 번호|해당 없음|변환 규칙에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.|
|호출 중인 번호|해당 없음|테스트할 전화 번호가 발신자의 전화 번호인지를 나타냅니다.|
|호출된 번호|해당 없음|테스트할 전화 번호가 수신 중인 사용자의 전화 번호인지를 나타냅니다.|
|||

> [!Note]
> 비즈니스용 Skype 서버 Get-cstrunkconfiguration cmdlet은 비즈니스용 Skype 서버 제어판에 표시 되지 않는 추가 속성을 지원 합니다. 자세한 내용은 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오. 

**비즈니스용 Skype 서버 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하려면**

1. 비즈니스용 Skype 서버 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.
2. **트렁크 구성** 탭에서 수정할 트렁크 구성 설정을 두 번 클릭합니다. 설정 컬렉션은 한 번에 하나만 편집할 수 있습니다. 여러 컬렉션에서 동일 항목을 변경하려면 Windows PowerShell을 대신 사용하십시오.
3. **트렁크 구성 편집** 대화 상자에서 적절 한 항목을 선택 하 고 **확인**을 클릭 합니다.
4. 컬렉션의 상태 속성은 커밋되지 않음으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을**클릭 하 고 **모두 커밋을**클릭 합니다.
5. 커밋되지 않은 **음성 구성 설정**s 대화 상자에서 **확인**을 클릭 합니다.
6. **비즈니스용 Skype 서버 제어판** 대화 상자에서 **확인**을 클릭 합니다.
