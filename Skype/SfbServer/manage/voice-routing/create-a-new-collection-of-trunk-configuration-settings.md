---
title: 비즈니스용 Skype 서버에서 새 트렁크 구성 설정 모음 만들기
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
description: SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.
ms.openlocfilehash: 6db4978151bf9b649375adb7a2200710a1a503c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817008"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 새 트렁크 구성 설정 모음 만들기

SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. 이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.
- Trunks에서 미디어 바이패스를 사용 해야 하는지 여부
- RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.
- 각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부

비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다. 또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.

비즈니스 서버 제어판 용 SIP 트렁크 구성 설정 usingSkype를 만들 때 다음 옵션을 사용할 수 있습니다.

|UI 설정 | PowerShell 매개 변수 | 설명 |
|--|--|--|
|이름|Identity|컬렉션의 고유 식별자입니다. 이 속성은 읽기 전용입니다. 트렁크 구성 설정 모음의 Id는 변경할 수 없습니다.|
|설명|설명|관리자가 설정에 대 한 추가 정보 (예: 트렁크 구성의 용도)를 저장할 수 있는 방법을 제공 합니다.|
|지원 되는 최대 빠른 대화 상자|Maxlya 대화 상자|서비스 공급자의 PSTN 게이트웨이, IP PBX 또는 SBC가 조정 서버로 전송 된 초대에 받을 수 있는 분기 응답의 최대 수입니다.|
|암호화 지원 수준|SRTPMode|서비스 공급자에서 중재 서버와 PSTN 게이트웨이, IP PBX 또는 SBC 간의 미디어 트래픽 보호에 대 한 지원 수준을 나타냅니다. 미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다. 미디어 구성은 [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) 및 [CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) cmdlet을 사용 하 여 설정 합니다.<br/>사용 가능한 값은 다음과 같습니다.<br/><br/>**필수**: SRTP 암호화를 사용 해야 합니다.<br/>**선택 사항**: 게이트웨이에서 지 원하는 경우 SRTP가 사용 됩니다.<br/>**지원 되지 않음**: SRTP 암호화가 지원 되지 않으므로 사용 되지 않습니다.<br/><br/>SRTPMode는 게이트웨이가 TLS (전송 계층 보안)를 사용 하도록 구성 된 경우에만 사용 됩니다. 게이트웨이가 TCP (전송 제어 프로토콜)를 전송으로 구성한 경우에는 SRTPMode가 내부적으로 지원 되지 않는 것으로 설정 됩니다.|
|지원 참조|Enable3pccRefer<br/>EnableReferSupport|보내기를 사용 하도록 설정 하는 경우 **게이트웨이를 참조**하는 경우 트렁크가 조정 서버의 수신 참조 요청을 지원함을 나타냅니다.<br/>이 기능을 사용 하도록 설정 하면 **타사 통화 제어를 사용**하는 것이 3pcc 프로토콜을 사용 하 여 호스팅된 사이트를 우회 하도록 할 수 있음을 나타냅니다. 3pcc는 "제3자 제어"라고도 하며, 제3자(예: A 사용자로부터 B 사용자에게 전화를 거는 교환원)를 통해 발신자 쌍을 연결하는 경우에 적용됩니다.|
|미디어 바이패스 사용|EnableBypass|이 트렁크에 미디어 바이패스를 사용 하도록 설정 했는지 여부를 나타냅니다. 미디어 바이패스는 **중앙 집중화 된 미디어 처리** 도 사용할 수 있는 경우에만 사용 가능 합니다.|
|중앙 집중화 된 미디어 처리|ConcentratedTopology|잘 알려진 미디어 종료 지점이 있는지 여부를 나타냅니다. 알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료의 IP와 동일한 PSTN 게이트웨이가 있습니다.|
|RTP latching 사용|EnableRTPLatching|SIP 트렁크가 RTP 래치를 지원하는지 여부를 나타냅니다. RTP 래치는 NAT(Network Address Translator) 장치 또는 방화벽을 통한 RTP/RTCP 연결을 설정하는 기술입니다.|
|착신 통화 기록 사용|ForwardCallHistory|트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.|
|앞으로 P-어설션된-Id 데이터 사용|ForwardPAI|PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다.|
|아웃 바운드 라우팅 장애 조치 타이머 사용|Enablefailovertimer|게이트웨이에서 응답 하지 않은 아웃 바운드 통화가 10 초 이내에 사용 가능한 다음 트렁크로 라우팅되도록 할지 여부를 표시 합니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다. 느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다.|
|연결 된 PSTN 용도|PSTNUsages|트렁크에 할당된 PSTN 사용 컬렉션입니다.|
|테스트를 위해 번역 된 번호|해당 없음|트렁크 구성 설정의 임시 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.|
|연결 된 번역 규칙|OutboundTranslationRulesList|아웃 바운드 라우팅이 처리 하는 통화에 적용 되는 전화 번호 번역 규칙 (PBX 또는 PSTN 대상으로 라우팅된 통화)을 수집 합니다.|
|전화 번호 번역 규칙|OutboundCallingNumberTranslationRulesList|트렁크에 할당된 아웃바운드 호출 번호 변환 규칙 컬렉션입니다.|
|테스트할 전화 번호|해당 없음|번역 규칙의 특별 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.|
|전화 번호|해당 없음|번역 규칙의 특별 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.|
|전화 번호|해당 없음|전화 번호가 통화 중인 사람의 전화 번호 라는 것을 나타냅니다.|
||||

> [!Note]
> 비즈니스용 Skype Server Set-cstrunkconfiguration cmdlet은 비즈니스용 Skype Server 제어판에 표시 되지 않는 추가 속성을 지원 합니다. 자세한 내용은 [새 set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요. 

**비즈니스용 Skype 서버 제어판을 사용 하 여 새 트렁크 구성 설정을 만들려면**

1. 비즈니스용 Skype Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.
2. **트렁크 구성** 탭에서 **새로 만들기**를 클릭 한 다음 **사이트 트렁크** 를 클릭 하 여 사이트 범위에서 새 설정을 만들거나, **풀 트렁크** 에서 서비스 범위에 새 설정을 만듭니다.
3. **사이트 선택** 또는 **서비스 선택** 대화 상자 (표시 되는 대화 상자는 사이트 범위 또는 서비스 범위 설정을 만들지 여부에 따라 달라 짐)에서 새 구성 설정의 위치를 선택 하 고 **확인**을 클릭 합니다. 대화 상자가 비어 있으면 새 설정을 만들 수 있는 위치가 없다는 의미입니다. 예를 들어 **사이트 선택** 대화 상자가 비어 있으면 모든 사이트에 트렁크 구성 사이트 모음이 이미 할당 되었고 각 사이트 (및 각 서비스)는 이러한 컬렉션을 하나만 호스트할 수 있습니다. 이러한 경우 기존 컬렉션을 삭제 하 고 새 컬렉션을 만들거나 기존 컬렉션을 수정할 수 있습니다.
4. **새 트렁크 구성** 대화 상자에서 적절 하 게 선택 하 고 **확인**을 클릭 합니다.
5. 컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다. 변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.
6. 커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.
7. **Skype For 비즈니스용** 제어판 대화 상자에서 **확인**을 클릭 합니다.
