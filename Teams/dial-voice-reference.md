---
title: 자동 전화 교환 및 통화 큐 전화 걸기 및 음성 인식 참조
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
description: Teams 자동 전화 교환 및 통화 큐 전화 걸기 및 음성 인식 옵션에 대해 알아봅니다.
ms.openlocfilehash: 784dcbf16c5122c165dc1a949fa237769c9837d3
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124193"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>자동 전화 교환 및 통화 큐 전화 걸기 및 음성 인식 참조

이름으로 전화 걸기 또는 확장은 발신자가 조직의 Teams 사용자에게 연결할 수 있는 자동 전화 교환 기능입니다. 음성 또는 전화 키패드 호출자를 사용하여 전체 또는 부분 이름 또는 연결하려는 사람의 확장을 말하거나 입력할 수 있습니다. 자동 전화 교환은 회사 디렉터리를 검색하고, 사용자를 찾은 다음, 발신자를 전송합니다.  이름으로 전화 걸기 또는 전화 접속은 [자동 전화 교환에서 통화 흐름 설정을 구성할](create-a-phone-system-auto-attendant.md?tabs=call-flow) 때 설정하는 옵션입니다.

## <a name="searching-for-users"></a>사용자 검색

이름으로 전화 걸기 사용하여 연결할 수 있는 Teams 사용자는 **전화 번호를 가지고 있거나 통화 플랜을 할당할 필요는 없지만 비즈니스용 Skype 서버 사용자에 대해 Enterprise Voice 사용하도록 설정해야 합니다**. 다국적 조직의 경우 이름으로 전화 걸기 다른 국가 또는 지역에 있는 Microsoft Teams 사용자에게 발신자를 찾아 전송합니다.

Dial by Extension을 사용하여 연락할 수 있는 Teams 사용자에게 **전화 번호가 있거나 통화 플랜이 할당되지 않아도 되지만 비즈니스용 Skype 서버 사용자에 대해 Enterprise Voice 사용하도록 설정해야 합니다**. 또한 사용자를 위해 적절하게 구성된 다이얼 플랜이 있어야 합니다. 다국적 조직의 경우 Dial by Extension은 다른 국가 또는 지역에 있는 Microsoft Teams 사용자에게 발신자를 찾아 전송합니다.

관련된 필수 구성 요소를 고려할 때 자동 전화 교환을 구성할 때 이름으로 전화 걸기 또는 확장을 명시적으로 사용하도록 설정해야 합니다.

### <a name="maximum-directory-size"></a>최대 디렉터리 크기

호출자가 특정 사용자를 검색할 때 지원 가능한 Active Directory 사용자 수에는 제한이 이름으로 전화 걸기. 호출자는 부분 또는 전체 이름(FirstName + LastName 및 LastName + FirstName)을 입력할 수 있지만 전체 확장 번호가 필요합니다. 단일 자동 전화 교환에서 음성 인식을 사용하여 지원할 수 있는 최대 이름 목록 크기는 80,000명의 사용자입니다.
  
|입력 형식|검색 형식|조직의 최대 사용자 수|
|:-----|:-----|:-----|
|DTMF(키패드 항목) |부분  <br/> FirstName + LastName  <br/> LastName + FirstName |제한 없음  |
|음성(음성 입력) |이름  <br/> 성  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80,000명의 사용자 |

> [!NOTE]
> 음성 인식과 함께 이름으로 전화 걸기 사용하지만 조직의 Active Directory가 80,000명보다 크고 [다이얼 범위](create-a-phone-system-auto-attendant.md?tabs=dial-scope) 기능을 사용하여 이름으로 전화 걸기 범위를 제한하지 않은 경우 이름으로 전화 걸기 여전히 전화 키패드를 사용하여 발신자에게 작동하며 다른 모든 시나리오에서 음성 입력을 사용할 수 있습니다. 다이얼 범위 기능을 사용하여 특정 자동 전화 교환에 대한 이름으로 전화 걸기 범위를 변경하여 연결할 수 있는 이름의 범위를 좁힐 수 있습니다.

### <a name="search-considerations"></a>검색 고려 사항

이름으로 전화 걸기 구성된 다이얼 범위 포함 또는 제외 목록을 적용하기 전에 먼저 전체 조직의 디렉터리를 검색합니다. 전체 디렉터리에 대한 초기 검색에서 100명 이상의 사용자를 반환하는 경우 전화 걸기 범위 목록이 적용되지 않고 검색이 실패하고 호출자에게 너무 많은 이름이 발견되었음을 알 수 있습니다.

## <a name="dial-by-name---keypad-dtmf-entry"></a>이름으로 전화 걸기 - 키패드(DTMF) 항목

통화하는 사용자는 이름으로 전화 걸기 사용하여 연결하려는 사람의 전체 또는 부분 이름을 지정하여 사용자에게 연결할 수 있습니다. 이름을 입력할 때 사용할 수 있는 다양한 형식이 있습니다.

조직의 디렉터리를 검색할 때 사용자는 '0' 키를 사용하여 이름과 성 또는 성 사이의 공백을 나타낼 수 있습니다. 이름을 입력할 때 # 키로 키패드 항목을 종료하라는 메시지가 표시됩니다. 예를 들어 "도달하려는 사람의 이름을 입력한 후 #키를 누릅니다." 이름이 여러 개인 경우 호출하는 사용자에게 선택할 이름 목록이 제공됩니다.

> [!NOTE]
> 다이얼 범위 포함 또는 제외 목록이 적용된 후에도 이름이 5개 이상 남아 있으면 검색이 실패하고 호출자에게 너무 많은 이름이 발견되었다는 알림이 표시됩니다.
  
사용자는 전화 키패드에서 다음 검색 형식을 사용하여 조직에서 이름을 검색할 수 있습니다.
  
|이름 형식|검색 유형|예제|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |전체  |Amos0Marble # |아모스 대리석 |
|LastName + FirstName |전체 |Marble0Amos #  |아모스 대리석 |
|이름  |전체   |아 모스 #   |Amos Marble의 경우 1을 누릅니다.  <br/> 아모스 마커스의 경우 2 키를 누릅니다. |
|성 |전체 |대리석 #  |Amos Marble의 경우 1을 누릅니다.  <br/> 메리 대리석에 대해 2 키를 누릅니다. |
|FirstName 또는 LastName |부분 |3월 # |메리 대리석에 대해 1을 누릅니다.  <br/> 메리 존스에 대한 프레스 2  <br/> 아모스 마커스의 경우 3 키를 누릅니다. |
|FirsName + LastName |부분 |Amos0Mar # |Amos Marble의 경우 1을 누릅니다.  <br/> 아모스 마커스의 경우 2 키를 누릅니다. |
|LastName + FirstName |부분 |Mar0Am # |Amos Marble의 경우 1을 누릅니다.  <br/> 아모스 마커스의 경우 2 키를 누릅니다. |

전화 키패드를 사용하여 사용자를 검색할 때 사용되는 몇 가지 특수 문자가 있습니다. 예를 들어 사용자에게 파운드 키(#)를 사용하라는 메시지가 표시되고 0(0) 키는 이름 사이의 공백에 사용됩니다. 별 키(*)를 누르면 일치하는 이름 목록이 사람에게 반복됩니다.
  
|특수 전화 키패드 문자|의미|
|:-----|:-----|
|#   |이름을 입력할 때의 끝 문자입니다. |
|0   |이름 사이의 간격입니다. |
|*    |일치하는 이름 목록을 반복합니다. |

### <a name="dial-by-name---name-recognition-with-speech"></a>이름으로 전화 걸기 - 음성을 사용하여 이름 인식

사용자는 음성(음성 인식)을 사용하여 조직의 다른 사용자를 검색할 수 있습니다. 또한 찾으려는 사람의 전체 또는 부분 이름을 말함으로써 Active Directory의 모든 사용자에게 연결할 수 있습니다. 음성 입력을 사용하면 FirstName, LastName, FirstName + LastName 또는 LastName + FirstName 등 다양한 형식으로 이름을 인식할 수 있습니다.
  
자동 전화 교환에 음성 인식을 사용하도록 설정할 수 있지만 DTMF(전화 키패드 항목)는 사용하지 않도록 설정되지 않습니다. 자동 전화 교환에서 음성 인식을 사용하도록 설정한 경우에도 전화 키패드 항목을 언제든지 사용할 수 있습니다.
  
전화 키패드 항목과 마찬가지로 여러 이름이 발견되면 호출하는 사람이 선택할 이름 목록을 듣습니다.

> [!NOTE]
> 다이얼 범위 포함 또는 제외 목록이 적용된 후에도 이름이 5개 이상 남아 있으면 검색이 실패하고 호출자에게 너무 많은 이름이 발견되었다는 알림이 표시됩니다.
  
호출자는 다음 형식으로 이름을 말할 수 있습니다.
  
|음성이 있는 이름|검색 유형|예제|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |전체 |아모스 대리석 |아모스 대리석 |
|LastName + FirstName |전체  |Marble Amos |아모스 대리석 |
|이름 |전체 |아 모스 |아모스 대리석에 대해 1을 누르거나 말  <br/> 아모스 존스에 대한 누르거나 말 2 |
|성 |전체 |대리석 |아모스 대리석에 대해 1을 누르거나 말  <br/> 벤 대리석에 대한 누르거나 말 2 |
|FirstName 또는 LastName |부분 |3월 |메리 대리석에 대한 누르거나 말 1  <br/> 메리 존스에 대한 누르거나 말 2  <br/> 아모스 마커스의 경우 3을 누르거나 말 |
|FirsName + LastName |부분 |아모스 3월 |아모스 대리석에 대해 1을 누르거나 말  <br/> 아모스 마커스에 대한 누르거나 말 2 |

> [!NOTE]
> 새 사용자가 Active Directory 복제 지연으로 인해 음성 인식을 사용하여 이름으로 전화 걸기 디렉터리에 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.

### <a name="dial-by-extension"></a>확장으로 전화 걸기

**Dial By Extension** 에 사용할 수 있도록 하려는 사용자는 Active Directory에 정의되고 Azure AD 커넥트 통해 동기화된 다음 전화 특성 중 하나로 지정된 확장이 있거나 Azure Active Directory 합니다. 자세한 내용은 [개별적으로 또는 대량으로 사용자 추가](/microsoft-365/admin/add-users/add-users) 를 참조하세요.

- OfficePhone/TelephoneNumber(AD 및 Azure AD)
- HomePhone(AD)
- Mobile/MobilePhone(AD 및 Azure AD)
- OtherTelephone(AD)

사용자 전화 번호 필드에 확장을 입력하는 데 필요한 형식은 다음 형식 중 하나일 수 있습니다.

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- 예제 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- 예제 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- 예제 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

[Microsoft 365 관리 센터 또는 Azure Active Directory](https://admin.microsoft.com/) [관리 센터에서](https://aad.portal.azure.com) 확장을 설정할 수 있습니다. 자동 전화 교환 및 통화 큐에서 변경 내용을 사용할 수 있는 데 최대 12시간이 걸릴 수 있습니다.

## <a name="language-support"></a>언어 지원

텍스트 음성 변환 및 음성 인식에 대한 언어 지원은 [지원되는](create-a-phone-system-auto-attendant-languages.md) 언어로 제공됩니다.

음성 인식에 사용할 수 있는 음성 명령은 다음과 같습니다.
  
|음성 명령| 에 해당 |
|:-----|:-----|
|예 | 예의 경우 1을 누릅니다. |
|아니요 | 아니요의 경우 2를 누릅니다. |
|반복 |옵션 목록을 반복합니다. 키패드에서 *를 눌러 옵션 목록을 반복합니다. |
|연산자 | "연산자"에 대해 0을 누릅니다. |
|주 메뉴  |호출자를 자동 전화 교환의 주 메뉴로 가져옵니다. |
|0 | 0을 누릅니다(기본적으로 "연산자"와 동일).|
|하나 | 1을 누릅니다. |
|두 | 2 키를 누릅니다. |
|3개| 3을 누릅니다.|
|4개 | 4 키를 누릅니다. |
|5개 | 5 키를 누릅니다. |
|6개  | 6을 누릅니다. |
|세븐 (7) | 7을 누릅니다.|
|8개 |8을 누릅니다.|
|나인 ()  |9 키를 누릅니다.|

## <a name="related-topics"></a>관련 주제

[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기](./getting-service-phone-numbers.md)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
