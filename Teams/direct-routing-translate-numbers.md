---
title: 다이렉트 라우팅에 대 한 전화 번호 번역
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft 전화 시스템 다이렉트 라우팅을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 545d6a77fd9b3ee0462437b5b710d1d4eb782138
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077653"
---
# <a name="translate-phone-numbers-to-an-alternate-format"></a>전화 번호를 대체 형식으로 번역

이 문서에서는 아웃 바운드 및 인바운드 통화에 대 한 숫자를 대체 형식으로 번역 하는 방법을 설명 합니다.  직접 라우팅 구성에 대 한 단계 4는 다음과 같습니다.

- 1 단계. [Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인](direct-routing-connect-the-sbc.md) 
- 2 단계. [사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정](direct-routing-enable-users.md)   
- 3 단계. [음성 라우팅 구성](direct-routing-voice-routing.md)
- **4 단계. 숫자를 대체 형식으로 번역** (이 문서)

직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.

때때로 테 넌 트 관리자가 SBCs (세션 경계 컨트롤러)와의 상호 운용성을 보장 하기 위해 만든 패턴에 따라 아웃 바운드 및/또는 인바운드 호출에 대 한 번호를 변경 하려고 할 수 있습니다. 이 문서에서는 번호 번역 규칙 정책을 지정 하 여 숫자를 대체 형식으로 번역 하는 방법에 대해 설명 합니다. 

숫자 번역 규칙 정책을 사용 하 여 다음에 대 한 숫자를 번역할 수 있습니다.

- 인바운드 통화: PSTN 끝점 (호출자)에서 팀 클라이언트 (피호출자)로 거는 호출
- 아웃 바운드 통화: 팀 클라이언트 (호출자)에서 PSTN 끝점 (호출 수신자)으로 호출

정책은 SBC 수준에서 적용 됩니다. 여러 번역 규칙을 사용자가 PowerShell에 나열할 때 표시 되는 순서 대로 적용 되는 SBC에 할당할 수 있습니다. 또한 정책에서 규칙의 순서를 변경할 수 있습니다.

번호 조작 규칙을 만들고, 수정 하 고, 보고, 삭제 하려면 [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)및 [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) cmdlet을 사용 합니다.

SBCs에 숫자 조작 규칙을 할당, 구성 및 나열 하려면 InboundTeamsNumberTranslationRules, InboundPSTNNumberTranslationRules, OutboundTeamsNumberTranslationRules, OutboundPSTNNumberTranslationRules, InboundTeamsNumberTranslationRulesList, InboundPSTNNumberTranslationRulesList, OutboundTeamsNumberTranslationRulesList, OutboundPSTNNumberTranslationRulesList 매개 변수를 사용 하 여 [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) 및 [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet을 함께 사용 합니다.

>[!NOTE]
> 최대 번역 규칙 수는 400, 최대 번역 매개 변수 이름 길이는 100 기호, 최대 번역 매개 변수 패턴 길이는 1024 기호이 고 최대 번역 매개 변수 번역 길이는 256 기호입니다.


## <a name="example-sbc-configuration"></a>예제 SBC 구성

이 시나리오에서는 cmdlet을 ```New-CsOnlinePSTNGateway``` 실행 하 여 다음 SBC 구성을 만듭니다.

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

SBC에 할당 된 번역 규칙은 다음 표에 요약 되어 있습니다.

|이름  |패턴이 |변환용  |
|---------|---------|---------|
|AddPlus1     |^ (\d {10} ) $          |+ 1 $1          |
|AddE164SeattleAreaCode      |^ (\d {4} ) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d {4} ) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d {10} ) $          | $1         |

다음 예제에는 Alice와 Bob 두 명의 사용자가 있습니다. Alice는 숫자가 + 1 206 555 0100 인 팀 사용자입니다. Bob은 숫자가 + 1 425 555 0100 인 PSTN 사용자입니다.

## <a name="example-1-inbound-call-to-a-ten-digit-number"></a>예제 1:10 자리 숫자에 대 한 인바운드 호출

Bob은 E 10의 164 자리 숫자를 사용 하 여 Alice를 호출 합니다. Bob이 2065550100으로 전화를 걸어 Alice에 도달 합니다.
SBC는 Urirequesturi에서 2065550100을 사용 하 고 From 헤더에는 To 헤더 및 4255550100를 사용 합니다.


|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:2065550100@sbc.contoso.com 초대|Sip:+12065550100@sbc.contoso.com 초대|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|받는 사람    |받는 사람:\<sip:2065550100@sbc.contoso.com>|받는 사람:\<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|보낸 사람   |보낸 사람:\<sip:4255550100@sbc.contoso.com>|보낸 사람:\<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

## <a name="example-2-inbound-call-to-a-four-digit-number"></a>예제 2:4 자리 숫자에 대 한 인바운드 호출

Bob은 네 자리 숫자를 사용 하 여 Alice를 호출 합니다. Bob이 0100으로 전화를 걸어 Alice에 도달 합니다.
SBC는 Urirequesturi에서 0100을 사용 하 고 From 헤더에는 To 헤더 및 4255550100를 사용 합니다.


|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:0100@sbc.contoso.com 초대          |Sip:+12065550100@sbc.contoso.com 초대           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|받는 사람    |받는 사람:\<sip:0100@sbc.contoso.com>|받는 사람:\<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|보낸 사람   |보낸 사람:\<sip:4255550100@sbc.contoso.com>|보낸 사람:\<sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

## <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>예제 3:10 자리 비 E 1-64 번호를 사용 하는 아웃 바운드 통화

Alice가 10 자리 숫자를 사용 하 여 Bob을 호출 합니다. Alice는 425 555 0100으로 Bob에 게 전화를 겁니다.
SBC는 팀과 PSTN 사용자 모두에 대해 비 E 164 10 자리 숫자를 사용 하도록 구성 되어 있습니다.

이 시나리오에서 다이얼 플랜은 직접 라우팅 인터페이스에 전송 하기 전에 번호를 변환 합니다. Alice가 팀 클라이언트에 425 555 0100를 입력 하면 해당 번호는 국가 다이얼 플랜에 따라 + 14255550100로 변환 됩니다. 결과 번호는 다이얼 플랜 규칙 및 팀 번역 규칙의 누적 정규화입니다. 팀 번역 규칙은 다이얼 플랜에 추가 된 "+ 1"을 제거 합니다.


|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:+14255550100@sbc.contoso.com 초대          |Sip:4255550100@sbc.contoso.com 초대       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|받는 사람    |받는 사람:\<sip:+14255550100@sbc.contoso.com>|받는 사람:\<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|보낸 사람   |보낸 사람:\<sip:+12065550100@sbc.contoso.com>|보낸 사람:\<sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

## <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>예제 4:4 자리 비 E 1-64 번호를 사용 하는 아웃 바운드 통화

Alice는 네 자리 숫자를 사용 하 여 Bob을 호출 합니다. Alice는 0100을 사용 하 여 Bob이 통화를 하거나 연락처를 사용 하 여 연락을 주고 받을 수 있습니다.
SBC 사용자의 경우 팀 사용자 및 10 자리 숫자에 대해 비 E 164 개의 4 자리 숫자를 사용 하도록 SBC를 구성 합니다. 다이얼 플랜은이 시나리오에서 적용 되지 않습니다.


|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:0100@sbc.contoso.com 초대           |Sip:4255550100@sbc.contoso.com 초대       |InboundTeamsNumberTranlationRulesList ' AddSeattleAreaCode '         |
|받는 사람    |받는 사람:\<sip:0100@sbc.contoso.com>|받는 사람:\<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList ' AddSeattleAreaCode '       |
|보낸 사람   |보낸 사람:\<sip:+12065550100@sbc.contoso.com>|보낸 사람:\<sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
