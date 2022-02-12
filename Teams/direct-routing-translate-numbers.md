---
title: 직접 라우팅에 대한 전화 번호 번역
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
description: 시스템 직접 라우팅을 Microsoft 전화 방법에 대해 자세히 알아보도록 합니다.
ms.openlocfilehash: 2a9f5c92da348a47f5a6d24389254436f2fd510c
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763293"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>전화 번호가 다른 형식으로 변환

이 문서에서는 아웃바운드 및 인바운드 호출에 대한 숫자를 대체 형식으로 변환하는 방법을 설명합니다. 직접 라우팅을 구성하기 위한 다음 단계의 4단계입니다.

- 1단계. [커넥트 시스템으로 SBC를 Microsoft 전화 연결의 유효성을 검사합니다.](direct-routing-connect-the-sbc.md) 
- 2단계. [직접 라우팅, 음성 및 음성메일에 사용자를 사용하도록 설정](direct-routing-enable-users.md)   
- 3단계. [음성 라우팅 구성](direct-routing-voice-routing.md)
- **4단계. 숫자를 대체 형식으로 변환합니다**   (이 문서)

직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 직접 라우팅 [구성을 참조하세요](direct-routing-configure.md).

경우에 따라 테넌트 관리자는 세션 경계 컨트롤러(SBC)와의 상호운용성을 보장하기 위해 만든 패턴에 따라 아웃바운드 및/또는 인바운드 호출의 수를 변경하려는 경우도 있습니다. 이 문서에서는 숫자 번역 규칙 정책을 지정하여 숫자를 대체 형식으로 변환하는 방법을 설명합니다. 

숫자 번역 규칙 정책을 사용하여 다음에 대한 숫자를 변환할 수 있습니다.

- 인바운드 호출: PSTN 엔드포인트(호출자)에서 Teams 클라이언트(호출자)
- 아웃바운드 호출: Teams 클라이언트(호출자)에서 PSTN 엔드포인트(호출자)로의 호출

이 정책은 SBC 수준에서 적용됩니다. PowerShell에 나열할 때 나타나는 순서대로 적용되는 여러 번역 규칙을 SBC에 할당할 수 있습니다. 정책에서 규칙의 순서를 변경할 수 있습니다.

번호 조작 규칙을 만들고 수정, 보기 및 삭제하려면 [New-CsTeamsTranslationRule](/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](/powershell/module/skype/get-csteamstranslationrule) 및 [Remove-CsTeamsTranslationRule](/powershell/module/skype/remove-csteamstranslationrule) cmdlet을 사용한다.

SBC에 번호 조작 규칙을 할당, 구성 및 나열하기 위해 InboundTeamsNumberTranslationRules, InboundPSTNumberTranslationRules, OutboundTeamsNumberTranslationRules 및 OutboundPSTNumberTranslationRules 매개 변수와 함께 [New-CSOnlinePSTSTNUMBERTranslationRules 매개 변수와 함께 New-CSOnlinePSTSTNUMBERTranslationRules](/powershell/module/skype/new-csonlinepstngateway) 매개 변수를 사용합니다.[](/powershell/module/skype/set-csonlinepstngateway)

> [!NOTE]
> 최대 총 번역 규칙 수는 400개, 최대 번역 매개 변수 이름 길이는 100개 기호, 최대 번역 매개 변수 패턴 길이는 1024개 기호, 최대 번역 매개 변수 변환 길이는 256개 기호입니다.


## <a name="example-sbc-configuration"></a>SBC 구성 예제

이 시나리오에서는 New-CsOnlinePSTNGateway cmdlet을 실행하여 다음 SBC 구성을 만들 수 있습니다.

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRules ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRules ‘AddPlus1’ -OutboundPSTNNumberTranslationRules ‘AddSeattleAreaCode’,‘StripPlus1’  -OutboundTeamsNumberTranslationRules ‘StripPlus1’
```

SBC에 할당된 번역 규칙은 다음 표에 요약되어 있습니다.

|이름  |패턴 |번역  |
|---------|---------|---------|
|AddPlus1     |^(\d{10})$          |+1$1          |
|AddE164SeattleAreaCode      |^(\d{4})$          | +1206555$1         |
|AddSeattleAreaCode    |^(\d{4})$          | 425555$1         |
|StripPlus1    |^+1(\d{10})$          | $1         |

다음 예제에서는 Alice와 Bob의 두 사용자가 있습니다. Alice는 Teams +1 206 555 0100인 사용자입니다. Bob은 +1 425 555 0100인 PSTN 사용자입니다.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>예제 1: 10자리 숫자에 대한 인바운드 호출

Bob은 E.164가 아닌 10자리 숫자를 사용하여 Alice를 호출합니다. Bob은 Alice에 2065550100 전화를 걸 수 있습니다.
SBC는 requestURI 2065550100 및 To 헤더에서 4255550100 및 시작 헤더에서 4255550100 를 사용 합니다.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙 적용  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:2065550100@sbc.contoso.com|초대 sip:+12065550100@sbc.contoso.com|InboundTeamsNumberTranslationRules 'AddPlus1'|
|받는 사람    |받는 사람: \<sip:2065550100@sbc.contoso.com>|받는 사람: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddPlus1'|
|보낸 사람   |보낸 사람: \<sip:4255550100@sbc.contoso.com>|보낸 사람: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNumberTranslationRules 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>예제 2: 4자리 숫자에 대한 인바운드 호출

Bob은 4자리 숫자를 사용하여 Alice를 호출합니다. Bob은 0100을 다이얼하여 Alice에 도달합니다.
SBC는 RequestURI 및 To 헤더에서 0100을 사용하며 4255550100 헤더에서 4255550100 합니다.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙 적용  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:0100@sbc.contoso.com          |초대 sip:+12065550100@sbc.contoso.com           |InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'        |
|받는 사람    |받는 사람: \<sip:0100@sbc.contoso.com>|받는 사람: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRules 'AddE164SeattleAreaCode'         |
|보낸 사람   |보낸 사람: \<sip:4255550100@sbc.contoso.com>|보낸 사람: \<sip:+14255550100@sbc.contoso.com>|InboundPSTNumberTranlationRules 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>예제 3: 10자리가 아닌 E.164 번호를 사용하는 아웃바운드 호출

Alice는 10자리 숫자를 사용하여 Bob을 호출합니다. Alice는 Bob에 도달하기 위해 425 555 0100을 다이얼합니다.
SBC는 사용자 및 PSTN 사용자 모두에 대해 E.164가 아닌 10자리 Teams 구성됩니다.

이 시나리오에서 다이얼 플랜은 직접 라우팅 인터페이스로 보내기 전에 숫자를 변환합니다. Alice가 클라이언트에서 425 555 0100을 Teams 국가 다이얼 플랜에서 +14255550100 변환됩니다. 결과 숫자는 다이얼 계획 규칙의 누적 정규화 및 Teams 규칙입니다. 이 Teams 규칙은 다이얼 계획에 의해 추가된 "+1"을 제거합니다.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙 적용  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:+14255550100@sbc.contoso.com          |초대 sip:4255550100@sbc.contoso.com       |OutboundPSTNumberTranlationRules 'StripPlus1'         |
|받는 사람    |받는 사람: \<sip:+14255550100@sbc.contoso.com>|받는 사람: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNumberTranlationRules 'StripPlus1'       |
|보낸 사람   |보낸 사람: \<sip:+12065550100@sbc.contoso.com>|보낸 사람: \<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRules 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>예제 4: 4자리가 아닌 E.164 번호를 사용하는 아웃바운드 호출

Alice는 4자리 숫자를 사용하여 Bob을 호출합니다. Alice는 0100을 사용하여 통화 또는 연락처를 사용하여 Bob에 도달합니다.
SBC는 PSTN 사용자의 경우 E.164가 아닌 Teams 10자리 숫자를 사용하도록 구성됩니다. 다이얼 플랜은 이 시나리오에 적용되지 않습니다.


|헤더  |원문 언어 |번역된 헤더 |매개 변수 및 규칙 적용  |
|---------|---------|---------|---------|
|RequestURI  |초대 sip:0100@sbc.contoso.com           |초대 sip:4255550100@sbc.contoso.com       |InboundTeamsNumberTranlationRules 'AddSeattleAreaCode'         |
|받는 사람    |받는 사람: \<sip:0100@sbc.contoso.com>|받는 사람: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'       |
|보낸 사람   |보낸 사람: \<sip:+12065550100@sbc.contoso.com>|보낸 사람: \<sip:2065550100@sbc.contoso.com>| InboundPSTNumberTranlationRules 'StripPlus1' |

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
