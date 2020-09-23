---
title: 자동 전화 교환 및 통화 대기열 전화 걸기와 음성 인식 참조
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
description: 팀의 자동 전화 교환 및 전화 대기열 전화 걸기와 음성 인식 옵션에 대해 알아봅니다.
ms.openlocfilehash: e7e88bc3a2dbb0f4d4e537c96918fb3b7c1bc163
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48209998"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>자동 전화 교환 및 통화 대기열 전화 걸기와 음성 인식 참조

### <a name="searching-for-users"></a>사용자 검색

이름으로 전화 걸기는 디렉터리 검색이 라고도 하는 자동 전화 교환의 기능입니다. 자동 전화 교환 기능을 통해 음성 (음성 인식) 또는 해당 휴대폰 키패드 (DTMF) 응답을 사용 하 여 회사 디렉터리를 검색 하는 전체 또는 일부 이름을 입력 하면 해당 사용자를 찾은 다음 통화가 전달 됩니다. 전화를 걸고 받을 사용자는 전화 번호를 사용 하거나 통화 **요금제를 할당 하지 않아도 되지만, 온라인 사용자 인 경우에는 전화 시스템 라이선스가 필요 하지만, 비즈니스용 Skype 서버 사용자에 게는 Enterprise Voice가 설정 되어 있어야 합니다**. 이름으로 전화 걸기는 여러 국가의 조직에 대해 다른 국가 또는 지역에서 호스팅되는 Microsoft 팀 사용자에 게 전화를 걸고 양도할 수도 있습니다. 관련 된 필수 구성 요소를 사용 하는 경우 자동 전화 교환에서 이름으로 전화 걸기를 명시적으로 설정 합니다.

내선 번호 걸기는 디렉터리 검색의 일부 이기도 한 자동 전화 교환의 기능입니다. 자동 전화 교환 프로그램을 통해 음성 (음성 인식) 또는 해당 전화기 키패드 (DTMF) 응답을 사용 하 여 연결 하려는 사용자의 휴대폰 내선 번호를 입력 하 고 해당 통화를 전달 받을 수 있습니다. 내선 번호로 전화를 걸고 도달 하려는 사용자는  **전화 번호를 사용 하거나 통화 요금제를 할당 하지 않아도 되지만, 온라인 사용자 인 경우에는 전화 시스템 라이선스가 필요 하지만 비즈니스용 Skype 서버 사용자에 게는 Enterprise Voice가 설정 되어 있어야 합니다**. 또한 사용자를 위해 적절 하 게 구성 된 다이얼 플랜이 있어야 합니다. 내선 번호로 전화를 걸려면 다양 한 국가 또는 지역에서 호스팅되는 Microsoft 팀 사용자에 게 전화를 걸고 양도할 수 있습니다. 관련 된 필수 구성 요소를 사용 하 여 자동 전화 교환에서 내선 번호 걸기를 명시적으로 설정 합니다.

#### <a name="maximum-directory-size"></a>최대 디렉터리 크기

사용자가 특정 사람을 검색 하는 경우 이름으로 전화를 걸고 내선 번호로 전화를 걸 수 있는 활성 디렉터리의 수에는 제한이 없습니다. 발신자는 일부 또는 전체 이름 (FirstName + LastName 및 LastName + FirstName)을 입력할 수 있지만, 전체 내선 번호는 필요 합니다. 단일 자동 전화 교환이 음성 인식을 사용 하 여 지원할 수 있는 최대 이름 목록 크기는 8만 사용자입니다.
  
|입력 형식|검색 형식|조직의 최대 사용자 수|
|:-----|:-----|:-----|
|DTMF (키패드 입력) |Partial  <br/> FirstName + LastName  <br/> LastName + FirstName |제한 없음  |
|음성 (음성 입력) |FirstName  <br/> 이름  <br/> FirstName + LastName  <br/> LastName + FirstName  | 8만 사용자 |

> [!NOTE]
> 음성 인식을 사용 하 여 이름으로 전화 걸기를 사용 하지만 조직의 Active Directory가 8만 사용자 보다 크므로 전화 접속 범위 기능을 사용 하 여 이름으로 전화 걸기 범위를 제한 하지 않은 경우에는 전화로 전화를 사용 하 여 해당 사용자가 전화를 걸고 다른 모든 시나리오에서 음성 입력을 사용할 수 있습니다. 전화 걸기 범위 기능을 사용 하 여 특정 자동 전화 교환의 이름으로 전화 걸기 범위를 변경 하 여 연결 가능한 이름을 좁힐 수 있습니다.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>이름-키패드 (DTMF) 항목으로 전화 걸기
전화를 거는 사람들은 상대방의 전체 이름 또는 일부 이름을 지정 하 여 사용자에 게 연락할 수 있습니다. 이름을 입력할 때 사용할 수 있는 다양 한 형식이 있습니다.

조직의 디렉터리를 검색 하는 경우 사용자는 ' 0 ' (영) 키를 사용 하 여 성과 이름 사이에 공백을 표시할 수 있습니다. 이름을 입력할 때 # key를 사용 하 여 키패드 입력을 종료 하 라는 메시지가 표시 됩니다. 예를 들어, 연락 하려는 사람의 이름을 입력 한 후 # 키를 누릅니다. 여러 이름이 있는 경우 전화를 거는 사람에 게 선택할 이름 목록이 제공 됩니다.
  
사용자는 휴대폰 키패드의 다음 검색 형식을 사용 하 여 조직에서 이름을 검색할 수 있습니다.
  
|이름 형식|검색 형식|예|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |수준의  |Amos0Marble # |Amos 대리석 |
|LastName + FirstName |수준의 |Marble0Amos #  |Amos 대리석 |
|FirstName  |수준의   |Amos #   |Amos 대리석의 경우 1 번 누름  <br/> Amos 용 2를 누르세요: Cus |
|이름 |수준의 |Marble #  |Amos 대리석의 경우 1 번 누름  <br/> Mary 대리석으로 2 누르기 |
|이름 또는 성 |Partial |최종 # |Mary 대리석에 대해 1을 누릅니다.  <br/> Mary Jones에 대해 2를 누릅니다.  <br/> Amos 용 3을 누릅니다. |
|FirsName + LastName |Partial |Amos0Mar # |Amos 대리석의 경우 1 번 누름  <br/> Amos 용 2를 누르세요: Cus |
|LastName + FirstName |Partial |Mar0Am # |Amos 대리석의 경우 1 번 누름  <br/> Amos 용 2를 누르세요: Cus |

전화 키패드를 사용 하 여 사용자를 검색할 때 사용할 수 있는 특수 문자가 몇 가지 있습니다. 예를 들어 사용자에 게 파운드 키 (#)를 사용 하 라는 메시지가 표시 되는 반면, 영 (0) 키는 이름 사이의 공백에 사용 됩니다. 별표 키 (*)를 누르면 일치 하는 이름 목록이 해당 사용자에 게 반복 됩니다.
  
|특수 전화 키패드 문자|의미|
|:-----|:-----|
|#   |이름을 입력할 때 끝 문자 |
|0   |이름 사이의 간격 |
|*    |일치 하는 이름 목록을 반복 합니다. |

#### <a name="dial-by-name---name-recognition-with-speech"></a>음성으로 이름-이름 인식으로 전화 걸기

사용자는 자신의 음성 (음성 인식)을 사용 하 여 조직의 다른 사용자를 검색할 수 있습니다. 또한 사용자가 찾으려고 하는 사용자의 이름을 말하여 Active Directory의 모든 사람에 게 연락할 수 있습니다. 음성 입력을 사용 하면 FirstName, LastName, FirstName + LastName 또는 LastName + FirstName을 비롯 한 다양 한 형식의 이름을 인식할 수 있습니다.
  
자동 전화 교환에 대 한 음성 인식을 사용 하도록 설정할 수 있지만 DTMF (휴대폰 키패드 입력)는 사용 하지 않도록 설정 됩니다. 전화 키패드 항목은 자동 전화 교환에서 음성 인식이 설정 된 경우에도 언제 든 지 사용할 수 있습니다.
  
전화 키패드 항목과 마찬가지로 여러 이름이 있으면 전화를 거는 사용자가 선택할 수 있는 이름 목록을 듣습니다.
  
발신자는 다음 형식의 이름을 말할 수 있습니다.
  
|음성으로 이름 사용|검색 형식|예|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |수준의 |Amos 대리석 |Amos 대리석 |
|LastName + FirstName |수준의  |대리석 무늬 Amos |Amos 대리석 |
|FirstName |수준의 |Amos |Amos 대리석의 경우 1을 누르거나 말을 누릅니다.  <br/> Amos Jones는 2를 누르거나 말을 누릅니다. |
|이름 |수준의 |Marble |Amos 대리석의 경우 1을 누르거나 말을 누릅니다.  <br/> 이혜준 씨의 경우 2를 누르거나 말을 누릅니다. |

> [!NOTE]
> Active Directory 복제 지연으로 인해 음성 인식이 있는 이름으로 전화를 걸기 위해 디렉터리에 이름을 나열 하는 데 새 사용자에 게 최대 36 시간이 걸릴 수 있습니다.
  
### <a name="language-support"></a>언어 지원

다음 언어는 발신 프롬프트에 사용 되는 텍스트 읽어주기에 사용할 수 있습니다.
  
||||
|:-----|:-----|:-----|
|아랍어 (예:)  |영어 (NZ)  |한국어 (KO-KR)  |
|중국어 (HK)  |영어 (영국) |노르웨이어 (NO)  |
|중국어 (hy 얕은 샘물 a) |영어 (미국) |폴란드어 (PL)  |
|중국어 (ZH-CN) |핀란드어 (FI) |포르투갈어 (BR) |
|덴마크어 (DA)  |프랑스어 (CA)  |포르투갈어 (PT) |
|네덜란드어 (NL)   |프랑스어 (FR)  |러시아어 (가) |
|영어 (AU)  |독일어 (DE) |스페인어 (ES)  |
|영어 (CA)  |이탈리아어 (IT) |스페인어 (MX)|
|영어 (IN)  |일본어 (JP) |스웨덴어 (SV)|

자동 전화 교환에 대 한 음성 인식 입력은 다음 언어로 제공 됩니다.
  
|||
|:-----|:-----|
|중국어 (ZH-CN)  |프랑스어 (FR)  |
|영어 (AU)  |독일어 (DE)  |
|영어 (CA)  |이탈리아어 (IT)  |
|영어 (IN)  |일본어 (JP)  |
|영어 (영국)  |포르투갈어 (BR)  |
|영어 (미국)  |스페인어 (ES)  |
|프랑스어 (CA)   |스페인어 (MX)  |

음성 인식에 지원 되는 14 가지 언어로 다음 음성 명령을 사용할 수 있습니다.
  
|음성 명령| 에 해당 |
|:-----|:-----|
|예 | 예를 보려면 1을 누릅니다. |
|아니요 | 아니요를 보려면 2를 누릅니다. |
|도 |옵션 목록을 반복 합니다. 키패드에서 *를 눌러 옵션 목록을 반복 합니다. |
|작동 | "연산자"에 대해 0을 누릅니다. |
|주 메뉴  |자동 전화 교환의 주 메뉴에 발신자를 가져옵니다. |
|이면 | 0 (기본적으로 "연산자"와 같음)을 누릅니다.|
|번째 | 1을 누릅니다. |
|두 | 2를 누릅니다. |
|두세| 3을 누릅니다.|
|24 | 4를 누릅니다. |
|6 | 5를 누릅니다. |
|식스  | 6을 누릅니다. |
|내내 | 7을 누릅니다.|
|번 |8을 누릅니다.|
|까지의  |9를 누릅니다.|

## <a name="related-topics"></a>관련 항목

[다음은 전화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기](/microsoftteams/getting-service-phone-numbers)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[소규모 기업 예제 - 자동 전화 교환 설정](/microsoftteams/tutorial-org-aa)
