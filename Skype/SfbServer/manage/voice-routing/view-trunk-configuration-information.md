---
title: 비즈니스용 Skype 서버에서 트렁크 구성 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186996"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 트렁크 구성 정보 보기

SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.

- Trunks에서 미디어 바이패스를 사용 해야 하는지 여부
- RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.
- 각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부

비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다. 또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.

**비즈니스용 Skype Server 제어판을 사용 하 여 SIP 트렁크 구성 정보를 보려면**

1. 비즈니스용 Skype Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.
2. **트렁크 구성** 탭에 모든 트렁크 구성 설정 모음 목록이 표시 됩니다. 각 컬렉션에 대해 사용자 **이름**, **범위**, **상태**및 **미디어 바이패스** 속성에 대 한 값을 **PSTN**사용 수, **호출 번호 규칙**, 연결 된 **번호 규칙** ()과 함께 표시 됩니다. 컬렉션을 사용 합니다. 트렁크 구성 설정 모음에 대 한 추가 세부 정보를 보려면 원하는 모음을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다. 한 번에 한 개의 트렁크 구성 설정 모음에 대 한 자세한 정보를 볼 수 있습니다.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 SIP 트렁크 구성 정보 보기

비즈니스용 Skype Server PowerShell 및 Set-cstrunkconfiguration cmdlet을 사용 하 여 SIP 트렁크 구성 설정을 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 http://go.microsoft.com/fwlink/p/?linkId=255876사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요. 이 링크를 바꾸거나 제거 합니다.


**SIP 트렁크 구성 정보를 보려면**

모든 SIP 트렁크 구성 설정에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.

`Get-CsTrunkConfiguration`

이는 다음과 같은 정보를 반환 합니다.

```
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [set-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) 을 참조 하세요.



