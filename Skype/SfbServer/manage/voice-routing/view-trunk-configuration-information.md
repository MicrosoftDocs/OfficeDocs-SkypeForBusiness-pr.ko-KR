---
title: 트렁크 구성 비즈니스용 Skype 서버 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다.
ms.openlocfilehash: 204f6f17387499719cf3b4bbe33638a849a4e363
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614068"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a>트렁크 구성 비즈니스용 Skype 서버 정보 보기

SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다.

- 트렁크에 미디어 우회를 설정할지 여부
- RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건
- SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부

설치 비즈니스용 Skype 서버 SIP 트렁크 구성 설정의 전역 컬렉션이 만들어집니다. 또한 관리자가 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스 전용)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다.

**제어판을 사용하여 SIP 트렁크 구성 정보를 비즈니스용 Skype 서버**

1. 비즈니스용 Skype 서버 제어판에서 음성 라우팅 **을** 클릭한 다음 트렁크 구성 **을 클릭합니다.**
2. **트렁크 구성 탭에는** 모든 트렁크 구성 설정 컬렉션 목록이 표시됩니다.  각 컬렉션에 대해 **이름,** **범위,** 상태 및 **미디어** 우회 속성에 대한 값과 컬렉션에 연결된 **PSTN** 사용법, 호출 번호 규칙 및 호출된 번호 규칙의 수가 표시됩니다. 트렁크 구성 설정 컬렉션에 대한 추가 세부 정보를 보려면 관심 있는 컬렉션을 클릭하고 편집을 **클릭한** 다음 자세한 정보 표시를 **클릭합니다.** 트렁크 구성 설정 컬렉션 하나에 대해 한 번만 자세한 정보를 볼 수 있습니다.

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 SIP 트렁크 Windows PowerShell 보기

SIP 트렁크 구성 설정은 PowerShell 및 비즈니스용 Skype 서버 cmdlet을 사용하여 볼 Get-CsTrunkConfiguration 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션에서 실행할 수 Windows PowerShell. 원격 Windows PowerShell 사용하여 비즈니스용 Skype 서버 대한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를 참조하십시오. https://go.microsoft.com/fwlink/p/?linkId=255876 이 링크를 바꾸거나 제거합니다.


**SIP 트렁크 구성 정보를 확인하려면**

모든 SIP 트렁크 구성 설정에 대한 정보를 확인하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누르고 있습니다.

```powershell
Get-CsTrunkConfiguration
```

그러면 다음과 같은 정보가 반환됩니다.

```console
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
자세한 내용은 [Get-CsTrunkConfiguration](/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet에 대한 도움말 항목을 참조하십시오.