---
title: 직접 라우팅을 위해 전화 번호 번역
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft Phone 시스템 직접 라우팅을 구성하는 방법을 알아봅니다.
ms.openlocfilehash: ac6dbd46d525232235d957b7d47f1fe108e3e4a3
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727770"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>전화 번호를 대체 형식으로 변환

이 문서에서는 아웃바운드 및 인바운드 호출의 숫자를 대체 형식으로 변환하는 방법을 설명합니다. 직접 라우팅을 구성하기 위한 다음 단계의 4단계입니다.

- 1단계. [SBC를 Microsoft Phone System에 연결하고 연결의 유효성을 검사합니다.](direct-routing-connect-the-sbc.md) 
- 2단계. [직접 라우팅, 음성 및 음성 메일에 대한 사용자 사용](direct-routing-enable-users.md)   
- 3단계. [음성 라우팅 구성](direct-routing-voice-routing.md)
- **4단계. 숫자를 대체 형식으로 변환**   (이 문서)

직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 [직접 라우팅 구성을 참조하세요](direct-routing-configure.md).

경우에 따라 테넌트 관리자는 SBC(세션 테두리 컨트롤러)와의 상호 운용성을 보장하기 위해 만든 패턴에 따라 아웃바운드 및/또는 인바운드 호출의 수를 변경하려고 할 수 있습니다. 이 문서에서는 숫자 변환 규칙 정책을 지정하여 숫자를 대체 형식으로 변환하는 방법을 설명합니다. 

숫자 변환 규칙 정책을 사용하여 다음의 숫자를 번역할 수 있습니다.

- 인바운드 호출: PSTN 엔드포인트(호출자)에서 Teams 클라이언트(호출 수신자)로 호출
- 아웃바운드 호출: Teams 클라이언트(호출자)에서 PSTN 엔드포인트로 호출(호출 수신자)

정책은 SBC 수준에서 적용됩니다. 여러 번역 규칙을 PowerShell에 나열할 때 나타나는 순서대로 적용되는 SBC에 할당할 수 있습니다. 정책에서 규칙의 순서를 변경할 수도 있습니다.

숫자 조작 규칙을 만들고, 수정하고, 보고, 삭제하려면 [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) 및 [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) cmdlet을 사용합니다.

할당, 구성, SCC의 번호 조작 규칙을 나열하고 [New-CSOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) 및 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet을 InboundTeamsNumberTranslationRules, InboundPSTNumberTranslationRules, OutboundTeamsNumberTranslationRules 및 OutboundPSTNumberTranslationRules 매개 변수와 함께 사용합니다.

> [!NOTE]
> 번역 규칙의 최대 총 수는 400개, 최대 번역 매개 변수 이름 길이는 100개 기호, 최대 번역 매개 변수 패턴 길이는 1024개 기호, 최대 번역 매개 변수 변환 길이는 256개 기호입니다.


## <a name="example-sbc-configuration"></a>예제 SBC 구성

이 시나리오에서는 New-CsOnlinePSTNGateway cmdlet을 실행하여 다음 SBC 구성을 만듭니다.

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

SBC에 할당된 번역 규칙은 다음 표에 요약되어 있습니다.

|이름  |패턴 |번역  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^\+1(\d{10})$          | $1         |

다음 예제에는 Alice와 Bob의 두 사용자가 있습니다. Alice는 숫자가 +1 206 555 0100인 Teams 사용자입니다. Bob은 번호가 +1 425 555 0100인 PSTN 사용자입니다.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>예제 1: 10자리 번호에 대한 인바운드 호출

Bob은 E.164가 아닌 10자리 숫자를 사용하여 Alice를 호출합니다. 밥은 2065550100 전화를 걸어 앨리스에게 연락한다.
SBC는 RequestURI 및 To 헤더의 2065550100 사용하고 From 헤더의 4255550100.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙이 적용됨  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:2065550100@sbc.contoso.com|초대 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|받는 사람    |받는 사람: \<sip:2065550100@sbc.contoso.com>|받는 사람: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|보낸 사람   |보낸 사람: \<sip:4255550100@sbc.contoso.com>|보낸 사람: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>예제 2: 4자리 번호에 대한 인바운드 호출

Bob은 4자리 숫자를 사용하여 Alice를 호출합니다. Bob은 0100으로 전화를 걸어 Alice에게 연락합니다.
SBC는 RequestURI 및 To 헤더에서 0100을 사용하고 From 헤더의 4255550100 사용합니다.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙이 적용됨  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:0100@sbc.contoso.com          |초대 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|받는 사람    |받는 사람: \<sip:0100@sbc.contoso.com>|받는 사람: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|보낸 사람   |보낸 사람: \<sip:4255550100@sbc.contoso.com>|보낸 사람: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>예제 3: E.164가 아닌 10자리 숫자를 사용한 아웃바운드 호출

Alice는 10자리 숫자를 사용하여 Bob을 호출합니다. Alice는 Bob에게 연락하기 위해 425 555 0100으로 전화를 거는 경우
SBC는 Teams 및 PSTN 사용자 모두에 대해 E.164가 아닌 10자리 숫자를 사용하도록 구성됩니다.

이 시나리오에서 다이얼 플랜은 숫자를 직접 라우팅 인터페이스로 보내기 전에 변환합니다. Alice가 Teams 클라이언트에 425 555 0100을 입력하면 번호가 국가 다이얼 플랜에 의해 +14255550100 변환됩니다. 결과 숫자는 다이얼 플랜 규칙 및 Teams 번역 규칙의 누적 정규화입니다. Teams 번역 규칙은 다이얼 플랜에 의해 추가된 "+1"을 제거합니다.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙이 적용됨  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:+14255550100@sbc.contoso.com          |초대 sip:4255550100@sbc.contoso.com       |OutboundPSTNNumberTranlationRules 'StripPlus1'         |
|받는 사람    |받는 사람: \<sip:+14255550100@sbc.contoso.com>|받는 사람: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRules 'StripPlus1'       |
|보낸 사람   |보낸 사람: \<sip:+12065550100@sbc.contoso.com>|보낸 사람: \<sip:2065550100@sbc.contoso.com>|아웃바운드TeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>예제 4: E.164가 아닌 4자리 숫자를 사용한 아웃바운드 호출

Alice는 4자리 숫자를 사용하여 Bob을 호출합니다. Alice는 0100을 사용하여 통화에서 또는 연락처를 사용하여 Bob에 연결합니다.
SBC는 Teams 사용자에 대해 E.164가 아닌 4자리 숫자와 PSTN 사용자에 대해 10자리 숫자를 사용하도록 구성됩니다. 다이얼 플랜은 이 시나리오에서 적용되지 않습니다.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙이 적용됨  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:0100@sbc.contoso.com           |초대 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|받는 사람    |받는 사람: \<sip:0100@sbc.contoso.com>|받는 사람: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|보낸 사람   |보낸 사람: \<sip:+12065550100@sbc.contoso.com>|보낸 사람: \<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
