---
title: 자동 참석자 및 통화 큐 전화 걸기 및 음성 인식 참조
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 자동 참석자 및 전화 큐 전화 걸기 및 음성 인식 옵션에 대해 Teams.
ms.openlocfilehash: 7ea18f5ca1f9fba619fe00f28e93e245a7a8f074
ms.sourcegitcommit: 38a4d2f41270633479afb3412c749365922554e5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2021
ms.locfileid: "61410679"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>자동 참석자 및 통화 큐 전화 걸기 및 음성 인식 참조

이름 또는 확장으로 전화 걸기 기능은 발신자가 조직의 다른 사용자에게 Teams 수 있는 자동 참석 기능입니다. 음성 또는 전화 키패드 발신자 사용을 통해 도달할 사람의 전체 또는 부분 이름 또는 확장을 말하거나 입력할 수 있습니다. 자동 참석자는 회사 디렉터리를 검색하고, 해당 사람을 찾은 다음 발신자에게 전송합니다.  전화 걸기 또는 전화 걸기 확장은 자동 참석자에서 통화 흐름 설정을 구성할 때 설정한 [옵션입니다.](create-a-phone-system-auto-attendant.md#call-flow)


## <a name="searching-for-users"></a>사용자 검색

Teams 전화 걸기를 사용하여 도달할 수 있는 사용자는 전화 번호가 필요하거나 통화 요금제가 할당되어 있지는 않지만 해당 사용자에게는 전화 번호가 Enterprise Voice 비즈니스용 Skype 서버 **합니다.** 다국적 조직의 경우 전화 걸기 이름으로 전화를 걸면 다른 국가 또는 지역에 Microsoft Teams 사용자로 발신자 수를 찾아 전송합니다.

Teams 다이얼로 확장을 사용하여 도달할 수 있는 사용자에게는 전화 번호가 필요하거나 통화 계획이 할당되어 있지는 않지만 사용자가 전화 번호를 Enterprise Voice **비즈니스용 Skype 서버.** 또한 사용자에 대해 적절히 구성된 다이얼 플랜이 필요합니다. 다국적 조직의 경우 전화 걸기 확장은 다른 국가 또는 지역에 있는 Microsoft Teams 발신자들을 찾아 전송합니다. 

관련된 전제적 구성이 제공되면 자동 참석자 구성 시 이름 또는 확장에 의해 전화 접속을 명시적으로 사용하도록 설정해야 합니다.

### <a name="maximum-directory-size"></a>최대 디렉터리 크기

발신자에서 특정 사용자를 검색할 때 지원할 수 있는 이름별 전화 걸기 및 확장별 전화 걸기 사용자 수에는 제한이 없습니다. 호출자는 부분 또는 전체 이름(FirstName + LastName 및 LastName + FirstName)을 입력할 수 있지만 전체 확장 번호가 필요합니다. 음성 인식을 사용하여 단일 자동 참석자가 지원할 수 있는 최대 이름 목록 크기는 80,000명입니다.
  
|입력 유형|검색 형식|조직의 최대 사용자 수|
|:-----|:-----|:-----|
|DTMF(키패드 항목) |부분  <br/> FirstName + LastName  <br/> LastName + FirstName |제한 없음  |
|음성(음성 입력) |FirstName  <br/> LastName  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80,000명 사용자 |

> [!NOTE]
> 음성 인식을 사용하여 전화 걸기를 사용하지만 조직의 Active Directory가 80,000명보다 크며 전화 걸기 범위를 제한하지 않은 경우 전화 걸기 기능은 전화 키패드를 사용하여 발신자에 대해 여전히 작동하며 음성 입력은 다른 모든 시나리오에서 사용할 수 있습니다. [](create-a-phone-system-auto-attendant.md#dial-scope) 다이얼 범위 기능을 사용하여 특정 자동 참석자에 대한 전화 걸기 이름 범위를 변경하여 도달 가능한 이름을 좁힐 수 있습니다.
 
### <a name="search-considerations"></a>고려 사항 검색 
이름에 의해 전화 접속은 조직의 디렉터리를 검색한 다음, 구성된 다이얼 범위 포함 또는 제외 목록에 대해 결과를 필터합니다. 초기 검색에서 100명 이상의 사용자를 반환하는 경우 다이얼 범위 목록이 적용되지 않습니다. 검색이 실패하고 호출자는 이름이 너무 많았다고 표시됩니다.
 
 
## <a name="dial-by-name---keypad-dtmf-entry"></a>전화 접속 이름 - DTMF(키패드) 항목
전화를 걸고 있는 사용자는 전화 접속 이름을 사용하여 도달하려는 사용자의 전체 또는 부분 이름을 지정하여 사용자에게 도달할 수 있습니다. 이름을 입력할 때 사용할 수 있는 다양한 형식이 있습니다.

조직의 디렉터리를 검색할 때 사람들은 '0' (0) 키를 사용하여 이름과 성, 성 사이의 공백을 나타낼 수 있습니다. 이름을 입력할 때 # 키로 키패드 항목을 종료해야 합니다. 예를 들어 "도달하려는 사람의 이름을 입력한 후 #을 누르겠습니다." 여러 개의 이름이 발견된 경우 호출하는 사용자가 선택할 이름 목록이 표시됩니다.

> [!NOTE]
> 전화 걸기 범위 포함 또는 제외 목록이 적용된 후에 이름이 5개 이상 남아 있는 경우 검색이 실패하고 호출자는 너무 많은 이름이 발견되었다고 표시됩니다. 
  
휴대폰 키패드에서 다음 검색 형식을 사용하여 조직에서 이름을 검색할 수 있습니다.
  
|이름 형식|검색 유형|예제|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |전체  |Amos0Marble # |Amos Marble |
|LastName + FirstName |전체 |Marble0Amos #  |Amos Marble |
|FirstName  |전체   |Amos #   |Amos Marble의 경우 1을 누르기  <br/> Amos Marcus의 경우 2를 누르기 |
|LastName |전체 |대리석 #  |Amos Marble의 경우 1을 누르기  <br/> Mary Marble용 2를 누르기 |
|FirstName 또는 LastName |부분 |3월 # |Mary Marble에 대해 1을 누르기  <br/> Mary Jones에 대해 2를 누르기  <br/> Amos Marcus의 경우 3을 누르기 |
|FirsName + LastName |부분 |Amos0Mar # |Amos Marble의 경우 1을 누르기  <br/> Amos Marcus의 경우 2를 누르기 |
|LastName + FirstName |부분 |Mar0Am # |Amos Marble의 경우 1을 누르기  <br/> Amos Marcus의 경우 2를 누르기 |

휴대폰 키패드를 사용하여 다른 사용자가 검색할 때 사용되는 몇 가지 특수 문자가 있습니다. 예를 들어 파운드 키(#)를 사용하겠지만 이름 사이의 공백에 0(0) 키가 사용됩니다. 별 키(*)를 누르면 해당 사용자와 일치하는 이름 목록을 반복합니다.
  
|특수 전화 키패드 문자|의미|
|:-----|:-----|
|#   |이름을 입력할 때 문자를 종료합니다. |
|0   |이름 사이의 공백입니다. |
|*    |일치하는 이름 목록을 반복합니다. |

### <a name="dial-by-name---name-recognition-with-speech"></a>전화 걸기 이름 - 음성으로 이름 인식

사람들은 자신의 음성(음성 인식)을 사용하여 조직에서 다른 사용자 검색을 할 수 있습니다. 또한 찾을 사람의 전체 또는 부분 이름을 말하여 Active Directory의 모든 사용자에 도달할 수도 있습니다. 음성 입력을 사용하여 FirstName, LastName, FirstName + LastName 또는 LastName + FirstName을 비롯한 다양한 형식의 이름을 인식할 수 있습니다.
  
자동 참석자에 대해 음성 인식을 사용하도록 설정할 수 있지만 DTMF(전화 키패드 항목)는 사용하지 않도록 설정되지 않습니다. 전화 음성 인식을 사용하도록 설정되어 있는 경우에도 키패드 항목을 사용할 수 있습니다.
  
전화 키패드 항목과 함께 여러 이름이 발견된 경우 호출하는 사용자가 선택할 이름 목록을 듣습니다.

> [!NOTE]
> 전화 걸기 범위 포함 또는 제외 목록이 적용된 후에 이름이 5개 이상 남아 있는 경우 검색이 실패하고 호출자는 너무 많은 이름이 발견되었다고 표시됩니다. 
  
발신자는 다음과 같은 형식으로 이름을 말할 수 있습니다.
  
|음성이 있는 이름|검색 유형|예제|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |전체 |Amos Marble |Amos Marble |
|LastName + FirstName |전체  |Marble Amos |Amos Marble |
|FirstName |전체 |Amos |Amos Marble의 경우 1을 누르거나 말하기  <br/> Amos Jones의 경우 2를 누르거나 말하기 |
|LastName |전체 |대리석 |Amos Marble의 경우 1을 누르거나 말하기  <br/> Ben Marble의 경우 2를 누르거나 말하기 |
|FirstName 또는 LastName |부분 |3월 |메리 대리석에 대해 1을 누르거나 말하기  <br/> Mary Jones에 대해 2를 누르거나 말하기  <br/> Amos Marcus에 대해 3을 누르거나 말하기 |
|FirsName + LastName |부분 |Amos Mar |Amos Marble의 경우 1을 누르거나 말하기  <br/> Amos Marcus의 경우 2를 누르거나 말하기 |


> [!NOTE]
> 새 사용자가 Active Directory 복제 시차로 인해 음성 인식을 사용하여 전화 번호의 디렉터리에 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.
  
## <a name="language-support"></a>언어 지원

텍스트 음성 및 음성 인식에 대한 언어 지원은 지원되는 언어 에서 [사용할 수 있습니다.](create-a-phone-system-auto-attendant-languages.md)

음성 인식에는 다음 음성 명령을 사용할 수 있습니다. 
  
|음성 명령| 에 해당합니다. |
|:-----|:-----|
|예 | 예를 위해 1을 누르겠습니다. |
|아니요 | 아니요로 2를 누르고 있습니다. |
|반복 |옵션 목록을 반복합니다. 키패드에서 * 키를 눌러 옵션 목록을 반복합니다. |
|연산자 | "연산자"에 대해 0을 누르기 |
|기본 메뉴  |호출자가 자동 참석자 주 메뉴로 표시됩니다. |
|0 | 0(기본적으로 "연산자")을 누를 수 있습니다.|
|1개 | 1을 누를 수 있습니다. |
|2개 | 2를 누를 수 있습니다. |
|3.| 3을 누를 수 있습니다.|
|4. | 4를 누를 수 있습니다. |
|5개 | 5를 누를 수 있습니다. |
|6  | 6을 누를 수 있습니다. |
|세븐 | 7을 누를 수 있습니다.|
|8개 |8을 누를 수 있습니다.|
|9개  |9를 누를 수 있습니다.|

## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기](./getting-service-phone-numbers.md)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
