---
title: 자동 전화 걸기 및 통화 큐 전화 걸기 및 음성 인식 참조
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Teams의 자동 전화 걸기 및 통화 큐 전화 걸기 및 음성 인식 옵션에 대해 자세히 배워 보십시오.
ms.openlocfilehash: 1cb8da2d2e6625de5a1471d1051c1ca51f11bbae
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918964"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>자동 전화 걸기 및 통화 큐 전화 걸기 및 음성 인식 참조

이름으로 전화 걸기 기능은 디렉터리 검색으로도 알려진 자동 전화 접속 기능입니다. 이를 통해 자동 전화 회의에 전화를 걸면 음성(음성 인식) 또는 DTMF(전화 키패드) 응답을 사용하여 전체 또는 부분 이름을 입력하여 회사 디렉터리를 검색하고, 해당 사람을 찾은 다음, 해당 사용자로 통화를 전송할 수 있습니다. 자동 전화 접속에서 통화 흐름 설정을 구성할 때 이름으로 다이얼을 [설정합니다.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>사용자 검색

전화 번호를 사용하여 연결하고 싶은 사용자는 전화 번호가 필요하거나 통화 요금제가 할당되어 있지는 않지만 비즈니스용 Skype 서버 Enterprise Voice 사용하도록 설정되어 있어야 **합니다.** 이름별로 전화를 걸면 여러 국가 또는 지역에서 다국적 조직에 호스트된 Microsoft Teams 사용자에게 전화를 찾아 전송할 수도 있습니다. 관련 구성이 필요한 경우 자동 전화 접속에서 Dial by Name을 명시적으로 사용하도록 설정해야 합니다.

내선 번호로 전화 걸기 기능은 디렉터리 검색의 일부인 자동 전화 접속 기능입니다. 이 기능을 사용하면 자동 전화 번호로 전화를 걸 때 음성(음성 인식) 또는 DTMF(전화 키패드) 응답을 사용하여 전화를 걸고자 하는 사용자의 내선 번호를 입력한 다음 해당 사용자에게 전화를 전송할 수 있습니다. 내선 번호로 전화 걸기를 사용하여 연결하고 싶은 사용자는 전화 번호가 필요하거나 통화 요금제가 할당되어 있지는 않지만 비즈니스용 Skype Server Enterprise Voice 사용하도록 설정되어 있어야 **합니다.** 또한 사용자에 대해 적절하게 구성된 다이얼 플랜이 필요합니다. 내선 번호로 전화를 걸면 여러 국가 또는 지역에서 다국적 조직에 호스트된 Microsoft Teams 사용자에게 전화를 찾아 전송할 수도 있습니다. 관련 구성이 필요한 경우 자동 전화 접속에서 내선 번호로 전화 걸기를 명시적으로 사용하도록 설정해야 합니다.

### <a name="maximum-directory-size"></a>최대 디렉터리 크기

발신자 검색 시 이름별 전화 걸기 및 내선 번호로 전화 걸기 기능으로 지원할 수 있는 Active Directory 사용자 수에는 제한이 없습니다. 호출자는 부분 또는 전체 이름(FirstName + LastName 및 LastName + FirstName)을 입력할 수 있지만 전체 확장 번호가 필요합니다. 단일 자동 참석자가 음성 인식 사용을 지원할 수 있는 최대 이름 목록 크기는 80,000명입니다.
  
|입력 유형|검색 형식|조직의 최대 사용자 수|
|:-----|:-----|:-----|
|DTMF(키패드 항목) |부분  <br/> FirstName + LastName  <br/> LastName + FirstName |제한 없음  |
|음성(음성 입력) |FirstName  <br/> LastName  <br/> FirstName + LastName  <br/> LastName + FirstName  | 사용자 80,000명 |

> [!NOTE]
> 음성 인식으로 Dial by Name을 사용하지만 조직의 Active Directory가 80,000명을 넘고 다이얼 범위 기능을 사용하여 전화로 전화 걸기의 범위를 제한하지 않은 경우 전화기 키패드를 사용하여 발신자에 대해 전화 걸기 기능을 사용할 수 있으며 음성 입력은 다른 모든 시나리오에서 사용할 수 있습니다. 다이얼 범위 기능을 사용하면 특정 자동 전화 접속자에 대한 Dial by Name의 범위를 변경하여 도달 가능한 이름을 좁힐 수 있습니다.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>이름에 의해 전화 걸기 - 키패드(DTMF) 항목
전화를 걸고 있는 사용자는 전화 걸기 이름을 사용하여 연결하려는 사용자의 전체 또는 부분 이름을 지정하여 사용자에게 도달할 수 있습니다. 이름을 입력할 때 사용할 수 있는 다양한 형식이 있습니다.

조직의 디렉터리를 검색할 때 사람들은 '0' 키를 사용하여 이름과 성 또는 성과 이름 사이의 공백을 나타낼 수 있습니다. 이름을 입력하면 #키로 키패드 항목을 종료할지 묻는 요청이 표시됩니다. 예를 들어 "도달하려는 사람의 이름을 입력한 후 #을(를) 누르기"를 입력합니다. 여러 개의 이름이 발견된 경우 통화하는 사람에 선택할 이름 목록이 표시됩니다.
  
휴대폰 키패드에서 다음과 같은 검색 형식을 사용하여 조직의 이름을 검색할 수 있습니다.
  
|이름 형식|검색 유형|예제|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |Full  |Amos0Marble # |Amos Marble |
|LastName + FirstName |Full |Marble0Amos #  |Amos Marble |
|FirstName  |Full   |Amos #   |Amos Marble의 경우 1을 누르기  <br/> Amos Marcus의 경우 2를 누르기 |
|LastName |Full |Marble #  |Amos Marble의 경우 1을 누르기  <br/> Mary Marble에 대해 2를 누르기 |
|FirstName 또는 LastName |부분 |3월 # |Mary Marble에 대해 1을 누르기  <br/> Mary Jones용 2를 누르기  <br/> Amos Marcus의 경우 3을 누르기 |
|FirsName + LastName |부분 |Amos0Mar # |Amos Marble의 경우 1을 누르기  <br/> Amos Marcus의 경우 2를 누르기 |
|LastName + FirstName |부분 |Mar0Am # |Amos Marble의 경우 1을 누르기  <br/> Amos Marcus의 경우 2를 누르기 |

휴대폰 키패드를 사용하는 사람 검색 시 사용되는 몇 가지 특수 문자가 있습니다. 예를 들어 파운드 키(#)를 사용하겠지만 이름 사이의 공백에 0 키가 사용됩니다. 별표(*)를 누르면 일치하는 이름 목록이 해당 사용자에 반복됩니다.
  
|특수 휴대폰 키패드 문자|의미|
|:-----|:-----|
|#   |이름을 입력할 때 끝 문자입니다. |
|0   |이름 사이의 공백입니다. |
|*    |일치하는 이름 목록을 반복합니다. |

### <a name="dial-by-name---name-recognition-with-speech"></a>이름에 의해 전화 걸기 - 음성으로 이름 인식

사람들은 자신의 음성(음성 인식)을 사용하여 조직의 다른 사용자에 대해 검색할 수 있습니다. 또한 찾으려고 하는 사람의 전체 또는 부분 이름을 말하여 Active Directory의 모든 사용자에 도달할 수도 있습니다. 음성 입력을 사용하여 FirstName, LastName, FirstName + LastName 또는 LastName + FirstName을 비롯한 다양한 형식으로 이름을 인식할 수 있습니다.
  
자동 전화 연결에 음성 인식을 사용하도록 설정할 수 있지만 DTMF(휴대폰 키패드 항목)는 사용할 수 없습니다. 자동 전화 연결에서 음성 인식을 사용하도록 설정되어 있는 경우에도 휴대폰 키패드 항목을 사용할 수 있습니다.
  
휴대폰 키패드 항목과 함께 여러 이름이 발견된 경우 통화하는 사람은 선택할 이름 목록을 듣습니다.
  
호출자는 다음과 같은 형식으로 이름을 말할 수 있습니다.
  
|음성이 있는 이름|검색 유형|예제|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |Full |Amos Marble |Amos Marble |
|LastName + FirstName |Full  |Marble Amos |Amos Marble |
|FirstName |Full |Amos |Amos Marble의 경우 1을 누르거나 말하기  <br/> Amos Jones의 경우 2를 누르거나 말하기 |
|LastName |Full |Marble |Amos Marble의 경우 1을 누르거나 말하기  <br/> Ben Marble의 경우 2를 누르거나 말하기 |
|FirstName 또는 LastName |부분 |3월 |Mary Marble의 경우 1을 누르거나 말하기  <br/> Mary Jones의 경우 2를 누르거나 말하기  <br/> Amos Marcus의 경우 3을 누르거나 말하기 |
|FirsName + LastName |부분 |Amos Mar |Amos Marble의 경우 1을 누르거나 말하기  <br/> Amos Marcus의 경우 2를 누르거나 말하기 |


> [!NOTE]
> Active Directory 복제 시간이 지났기 때문에 새 사용자가 음성 인식을 사용하여 Dial by Name 디렉터리에 해당 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.
  
## <a name="language-support"></a>언어 지원

다음 언어는 발신 프롬프트와 함께 사용되는 텍스트 음성을 음성으로 번역하는 데 사용할 수 있습니다.
  
|-|-|-|
|:-----|:-----|:-----|
|아랍어(EG)  |영어(NZ)  |한국어(KO)  |
|중국어(HK)  |영어(영국) |노르웨이어(NO)  |
|중국어(TW) |영어(미국) |폴란드어(PL)  |
|중국어(ZH) |핀란드어(FI) |포르투갈어(BR) |
|덴마크어(DA)  |프랑스어(CA)  |포르투갈어(PT) |
|네덜란드어(NL)   |프랑스어(FR)  |러시아어(RU) |
|영어(AU)  |독일어(DE) |스페인어(ES)  |
|영어(CA)  |이탈리아어(IT) |스페인어(MX)|
|영어(IN)  |일본어(JP) |스웨덴어(SV)|

자동 참석자에 대한 음성 인식 입력은 다음 언어로 사용할 수 있습니다.
  
|-|-|
|:-----|:-----|
|중국어(ZH)  |프랑스어(FR)  |
|영어(AU)  |독일어(DE)  |
|영어(CA)  |이탈리아어(IT)  |
|영어(IN)  |일본어(JP)  |
|영어(영국)  |포르투갈어(BR)  |
|영어(미국)  |스페인어(ES)  |
|프랑스어(CA)   |스페인어(MX)  |

다음 음성 명령은 음성 인식에 지원되는 14개 언어로 제공됩니다.
  
|음성 명령| 해당 |
|:-----|:-----|
|예 | 예에 대해 1을 누르고 있습니다. |
|아니요 | 아니요로 2를 누르고 |
|반복 |옵션 목록을 반복합니다. 키패드에서 *를 눌러 옵션 목록을 반복합니다. |
|연산자 | "연산자"에 대해 0을 누르기 |
|주 메뉴  |발신자가 자동 전화 회의의 주 메뉴로 갑니다. |
|0 | 0을 누르고(기본적으로 "연산자"처럼)|
|One | 1을 누르고 |
|Two | 2를 누르고 있습니다. |
|Three| 3을 누르고 있습니다.|
|4 | 4를 누르고 있습니다. |
|Five | 5를 누르고 있습니다. |
|6  | 6을 누르고 있습니다. |
|7 | 7을 누르고 있습니다.|
|8 |8을 누르고 있습니다.|
|Nine  |9를 누를 수 있습니다.|

## <a name="related-topics"></a>관련 항목

[다음은 전화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기](/microsoftteams/getting-service-phone-numbers)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
