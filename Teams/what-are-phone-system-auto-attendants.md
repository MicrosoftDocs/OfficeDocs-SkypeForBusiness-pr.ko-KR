---
title: 클라우드 자동 전화 교환이란?
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
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
ROBOTS: NOINDEX, NOFOLLOW
description: Cloud 자동 참석자 및 이를 사용하여 발신자가 메뉴 시스템을 통해 이동하여 사용자 또는 부서에 전화를 찾고 배치하거나 전송할 수 있도록 하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100964"
---
# <a name="what-are-cloud-auto-attendants"></a>클라우드 자동 전화 교환이란?

Phone System은 외부 및 내부 발신자가 메뉴 시스템을 통해 이동하여 조직의 사용자 또는 부서에 전화를 찾고 배치하거나 전송할 수 있도록 하는 데 사용할 수 있는 자동 참석자 기능을 제공합니다.
  
자동 참석자는 대부분의 경우 시스템의 노드로, 발신자에게 사람 연산자 대신 듣는 일련의 음성 프롬프트 또는 오디오 파일을 제공합니다. 사용자가 자동 참석자와 연결된 번호를 호출할 때 해당 사용자가 선택한 전화는 사용자로 전화를 리디렉션하거나 조직의 다른 사용자를 찾은 다음 해당 사용자에 연결할 수 있습니다. DTMF(전화 키패드) 또는 음성 인식을 사용하여 선택 항목을 표현하고 메뉴 시스템과 상호 작용할 수 있습니다. 사용자가 선택한 경우 전화를 다른 자동 참석자 또는 호출 큐로 리디렉션할 수도 있습니다.
  
전화 시스템에 대한 자동 참석자 설정은 클라우드 자동 참석자 [설정으로 이동합니다.](create-a-phone-system-auto-attendant.md)
  
Cloud 자동 참석자에는 다음과 같은 기능이 있습니다.
  
- 회사 또는 정보 인사말을 제공할 수 있습니다.
- 사용자 지정 회사 메뉴를 제공할 수 있습니다. 이러한 메뉴를 사용자 지정할 수 있습니다.
- 호출하는 사용자가 이름을 검색할 수 있는 디렉터리 검색을 제공합니다.
- 이렇게 하면 전화를 걸고 조직에 있는 사용자에 대한 메시지에 도달하거나 메시지를 남길 수 있습니다.
- 프롬프트, 텍스트 음성 음성 및 음성 인식에 대한 여러 언어를 지원합니다.
- 공휴일 및 업무 시간 지정을 지원합니다.
- 운영자, 다른 사용자, 호출 큐 및 자동 참석자에게 호출 전송을 지원합니다.
- 호출자는 조직의 메시지를 남길 수 있는 공유 음성 메일이 지원됩니다.

> [!NOTE]
> 이 문서는 Microsoft Teams 및 비즈니스용 Skype Online 모두에 적용됩니다.

## <a name="getting-started"></a>시작

자동 참석자 사용을 시작하기 위해 다음을 기억해야 합니다.

- 연결된 리소스 계정을 사용하려면 자동 참석자가 필요합니다. 리소스 계정에 대한 자세한 내용은 [Teams에서](manage-resource-accounts.md) 리소스 계정 관리를 참조합니다. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- 자동 참석자에 전화 번호를 할당할 때 해당 자동 참석자와 연결된 리소스 계정에 전화 번호를 할당하는 것이 엄밀히 말하면 됩니다. 이렇게 하면 두 개 이상의 전화 번호가 자동 참석자에 액세스하는 방법을 제공합니다. 리소스 계정이 비용 부담 전화 시스템 가상 사용자 라이선스를 사용하는 경우가 대부분입니다. 이 라이선스는 조직 수준에서 전화 번호에 전화 시스템 기능을 제공하며 자동 참석자 및 통화 큐를 만들 수 있습니다.

> [!NOTE]
> 자동 참석자 및 호출 큐에 대한 직접 라우팅 서비스 번호는 Microsoft Teams 사용자 및 호출 에이전트에만 지원됩니다.

   > [!TIP]
   > 전화 시스템 라이선스가 있는 Online 사용자인 운영자  또는 메뉴 옵션에 대한 호출을 리디렉션하려면 해당 계정을 사용하도록 설정하거나 통화 요금제에 Enterprise Voice 할당해야 합니다. Microsoft Teams 추가 기능 라이선스 할당 [을 참조합니다.](teams-add-on-licensing/assign-teams-add-on-licenses.md) 또한 이 기능을 사용할 Windows PowerShell. 예를 들어 실행:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- 자동 참석자에 대한 무료 서비스 번호를 얻고 사용하려면 Communications 크레딧을 설정해야 합니다. 이를 위해 통신 [크레딧이란?](what-are-communications-credits.md) 및 조직에 대한 통신 크레딧 설정 을 [참조하세요.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > 사용자(구독자) 전화 번호는 자동 전화 번호에 할당할 수 없습니다. 서비스 전화 번호 또는 무료 전화 번호만 사용할 수 있습니다.

- 전체 자동 참석 시스템은 일반적으로 여러 자동 참석자가 관련됩니다.
- 입력 수준 자동 참석자에 두 개 이상의 전화 번호를 적용할 수 있습니다.
- 전체 시스템의 비 진입 수준 자동 참석자 또는 통화 큐는 아웃바운드 PSTN 호출을 하는 경우 전화 번호만 필요합니다.
  
## <a name="feature-overview"></a>기능 개요

### <a name="searching-for-users"></a>사용자 검색

전화 걸기 이름은 디렉터리 검색으로도 알려진 자동 참석자 기능입니다. 이 기능을 사용하면 자동 참석자에게 음성(음성 인식) 또는 해당 전화 키패드(DTMF) 응답을 사용하여 전체 또는 부분 이름을 입력하여 회사의 디렉터리를 검색하고, 해당 사람을 찾은 다음 통화를 전송할 수 있습니다. 전화 걸기를 사용하여 전화 접속을 하고자 하는 사용자는 전화 번호가 필요하거나 통화 요금제가 할당되어 있지는 않지만, 온라인 사용자인 경우 전화 시스템 라이선스를 Enterprise Voice 비즈니스용 Skype 서버 사용자에 대해 Enterprise Voice 있어야 **합니다.** 이름별로 전화를 걸면 다국적 조직에 대해 다른 국가 또는 지역에서 호스트된 Microsoft Teams 사용자에게 전화를 찾아 전송할 수도 있습니다. 관련 구성이 필요한 경우 자동 참석자에서 전화 걸기 이름을 명시적으로 사용하도록 설정합니다.

전화 걸기 확장은 디렉터리 검색의 일부인 자동 참석자 기능입니다. 이 기능을 사용하면 자동 참석자를 호출하는 사용자가 음성(음성 인식) 또는 DTMF(전화 키패드) 응답을 사용하여 도달하려는 사용자의 전화 확장을 입력한 다음 해당 사용자에게 전화를 전송할 수 있습니다. 전화 걸기를 사용하여 전화 접속을 하고자 하는 사용자는 전화 번호가 필요하거나 전화 요금제가 할당되어 있지는 않지만, 온라인 사용자인 경우 전화 시스템 라이선스를 Enterprise Voice 비즈니스용 Skype 서버 사용자에 대해 Enterprise Voice 있어야 **합니다.** 또한 사용자에 대해 적절히 구성된 다이얼 플랜이 필요합니다. 확장별로 전화를 걸면 다국적 조직에 대해 다른 국가 또는 지역에서 호스트된 Microsoft Teams 사용자에게 전화를 찾아 전송할 수도 있습니다. 관련 구성이 필요한 경우 자동 참석자에서 전화 걸기 확장을 명시적으로 사용하도록 설정합니다.

#### <a name="maximum-directory-size"></a>최대 디렉터리 크기

발신자에서 특정 사용자를 검색할 때 지원할 수 있는 이름별 전화 걸기 및 전화 걸기 확장으로 Active Directory 사용자 수에는 제한이 없습니다. 호출자는 부분 또는 전체 이름(FirstName + LastName 및 LastName + FirstName)을 입력할 수 있지만 전체 확장 번호가 필요합니다. 음성 인식을 사용하여 단일 자동 참석자가 지원할 수 있는 최대 이름 목록 크기는 80,000명입니다.
  
|입력 유형|검색 형식|조직의 최대 사용자 수|
|:-----|:-----|:-----|
|DTMF(키패드 항목) |부분  <br/> FirstName + LastName  <br/> LastName + FirstName |제한 없음  |
|음성(음성 입력) |FirstName  <br/> LastName  <br/> FirstName + LastName  <br/> LastName + FirstName  | 80,000명 사용자 |

> [!NOTE]
> 음성 인식을 사용하여 전화 걸기를 사용하지만 조직의 Active Directory가 80,000명보다 크며 전화 걸기 범위를 제한하지 않은 경우 전화 걸기 기능은 전화 키패드를 사용하여 발신자에 대해 여전히 작동하며 음성 입력은 다른 모든 시나리오에서 사용할 수 있습니다. 다이얼 범위 기능을 사용하여 특정 자동 참석자에 대한 전화 걸기 이름 범위를 변경하여 도달 가능한 이름을 좁힐 수 있습니다.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>전화 접속 이름 - DTMF(키패드) 항목

전화를 걸고 있는 사용자는 전화 접속 이름을 사용하여 도달하려는 사용자의 전체 또는 부분 이름을 지정하여 사용자에게 도달할 수 있습니다. 이름을 입력할 때 사용할 수 있는 다양한 형식이 있습니다.

조직의 디렉터리를 검색할 때 사람들은 '0' (0) 키를 사용하여 이름과 성, 성 사이의 공백을 나타낼 수 있습니다. 이름을 입력할 때 # 키로 키패드 항목을 종료해야 합니다. 예를 들어 "도달하려는 사람의 이름을 입력한 후 #을 누르겠습니다." 여러 개의 이름이 발견된 경우 호출하는 사용자가 선택할 이름 목록이 표시됩니다.
  
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

#### <a name="dial-by-name---name-recognition-with-speech"></a>전화 걸기 이름 - 음성으로 이름 인식

사람들은 자신의 음성(음성 인식)을 사용하여 조직에서 다른 사용자 검색을 할 수 있습니다. 또한 찾고자 하는 사람의 이름을 말하여 Active Directory의 모든 사용자에 도달할 수 있습니다. 음성 입력을 사용하여 FirstName, LastName, FirstName + LastName 또는 LastName + FirstName을 비롯한 다양한 형식의 이름을 인식할 수 있습니다.
  
자동 참석자에 대해 음성 인식을 사용하도록 설정할 수 있지만 DTMF(전화 키패드 항목)는 사용하지 않도록 설정되지 않습니다. 전화 키패드 항목은 자동 참석자에서 음성 인식을 사용하도록 설정되어 있는 경우에도 사용할 수 있습니다.
  
전화 키패드 항목과 함께 여러 이름이 발견된 경우 호출하는 사용자가 선택할 이름 목록을 듣습니다.
  
발신자는 다음과 같은 형식으로 이름을 말할 수 있습니다.
  
|음성이 있는 이름|검색 유형|예제|검색 결과|
|:-----|:-----|:-----|:-----|
|FirstName + LastName |전체 |Amos Marble |Amos Marble |
|LastName + FirstName |전체  |Marble Amos |Amos Marble |
|FirstName |전체 |Amos |Amos Marble의 경우 1을 누르거나 말하기  <br/> Amos Jones의 경우 2를 누르거나 말하기 |
|LastName |전체 |대리석 |Amos Marble의 경우 1을 누르거나 말하기  <br/> Ben Marble의 경우 2를 누르거나 말하기 |

> [!NOTE]
> 새 사용자가 Active Directory 복제 시차로 인해 음성 인식을 사용하여 전화 번호의 디렉터리에 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.
  
### <a name="language-support"></a>언어 지원

다음 언어는 발신 프롬프트와 함께 사용되는 텍스트 음성 음성을 사용할 수 있습니다.
  
|A-E|E-J|K-Z|
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
  
|A-F|F-Z|
|:-----|:-----|
|중국어(ZH)  |프랑스어(FR)  |
|영어(AU)  |독일어(DE)  |
|영어(CA)  |이탈리아어(IT)  |
|영어(IN)  |일본어(JP)  |
|영어(영국)  |포르투갈어(BR)  |
|영어(미국)  |스페인어(ES)  |
|프랑스어(CA)   |스페인어(MX)  |

다음 음성 명령은 음성 인식에 지원되는 14개 언어로 제공됩니다.
  
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

### <a name="the-operator-option"></a>연산자 옵션

선택적으로 자동 출석을 설정하여 발신자에게 사용자 연산자에게 말할 수 있는 선택을 제공 할 수 있습니다.
  
키 0 및 음성 명령 "연산자"는 기본적으로 지정된 연산자로 호출을 지시합니다. 음성 인식에 지원되는 모든 언어의 경우입니다. 설정 메뉴 옵션을 **사용하여** 연산자에 대한 사용자 지정 값을 설정할 수도 있습니다.
  
연산자를 다음으로 설정할 수 있습니다.
  
- 사용할 수 있는 Microsoft Teams 사용자 또는 비즈니스용 Skype Enterprise Voice 사용자입니다.
- 조직에 대해 설정된 또 다른 자동 참석자입니다.
- 조직에서 설정한 기존 호출 큐입니다. 호출 큐에 대한 자세한 내용은 클라우드 호출 큐 [만들기 를 참조합니다.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>업무 시간 및 통화 처리

업무 시간은 각 자동 참석자에 설정할 수 있습니다. 업무 시간이 설정되지 않은 경우 24/7 일정이 기본적으로 설정되어 있기 때문에 하루의 모든 일 및 모든 시간은 영업 시간으로 간주됩니다. 업무 시간은 낮 동안의 휴식 시간으로 설정할 수 있으며, 영업 시간으로 설정되지 않은 모든 시간은 시간 후로 간주됩니다. 업무 시간 및 시간 후의 다른 수신 통화 처리 옵션 및 다른 인사말(선택 사항)을 설정할 수 있습니다.
  
각 자동 참석자에는 몇 가지 가능한 호출 처리 옵션이 있습니다.
  
- 인사말이 재생된 후에 통화가 연결이 끊어지기 수 있습니다.
- 다음을 할 수 있습니다.
  - 통화를 사용하도록 설정되어 있는 전화  시스템 라이선스가 Enterprise Voice 할당된 Microsoft Teams 사용자로 리디렉션합니다. 음성 메일로 전화를 걸 수 있도록 설정할 수 있습니다. 이렇게하려면 회사의 사람을 **선택하고** 이 사람의 통화를 음성사서로 자동으로 전달할 수 있도록 설정합니다.

  - 호출을 호출 큐로 리디렉션합니다. 호출 큐에 대한 자세한 내용은 클라우드 호출 큐 [만들기 를 참조합니다.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - 호출을 다른 자동 참석자로 리디렉션합니다.

이러한 옵션은 메뉴 프롬프트를 재생할 때 자동 참석자가 발신자에 표시됩니다. 예: "판매용 1을 누르고 서비스에 대해 2를 누르겠습니다. 운영자에게 말하기 위해 0을 누르면 됩니다."

### <a name="set-menu-options"></a>메뉴 옵션 설정

클라우드 자동 참석자를 사용하면 메뉴 프롬프트("판매용 1 누르기, 서비스용 2")를 만들고 사용자 선택에 따라 호출을 라우팅하는 메뉴 옵션을 설정할 수 있습니다. 자동 참석자에 대한 메뉴 옵션을 통해 조직은 들어오는 호출을 처리하기 위해 사람 연산자에 의하지 않고 발신자가 목적지로 더 빠르게 이동하는 일련의 선택을 제공할 수 있습니다. 메뉴 프롬프트는 텍스트 음성(시스템 생성 프롬프트)을 사용하거나 녹음된 오디오 파일을 업로드하여 만들 수 있습니다. 음성 인식은 핸즈 프리 탐색을 위해 음성 명령을 수락하지만, 전화 키패드를 사용하여 메뉴를 탐색할 수도 있습니다.
  
비즈니스용 Skype 관리 센터를 사용하여 자동 전화 걸기 키에 0~9 키를 할당할 수 있습니다. 업무 시간 및 시간 이후의 메뉴 옵션 집합을 만들 수 있으며 메뉴 옵션에서 전화 걸기 이름 지정을 사용하도록 설정하거나 사용하지 **않도록 설정할 수 있습니다.** 키를 매핑하여 호출을 다음으로 전송할 수 있습니다.
  
- 기본적으로 키 0에 매핑되는 연산자입니다. 그러나 다른 키로 다시 재배치하거나 메뉴에서 제거할 수 있습니다.
- 호출 큐입니다.
- 다른 자동 참석자입니다. 하나의 자동 참석자에 메뉴 옵션을 "중첩된" 자동 참석자라고 하는 자체 메뉴 옵션 집합을 사용하여 다른 자동 참석자에 메뉴 옵션을 표시하여 다단계 메뉴를 설정할 수 있습니다. 
- 전화 시스템 라이선스가  Enterprise Voice 또는 통화 계획이 할당된 Microsoft Teams 사용자입니다. 음성 메일로 전화를 걸 수 있도록 설정할 수 있습니다. 이렇게하려면 회사의 사람을 **선택하고** 이 사람의 통화를 음성사서로 자동으로 전달할 수 있도록 설정합니다.
  
모든 메뉴 옵션의 이름은 음성 인식을 사용하도록 설정한 경우 음성 인식 키워드가 됩니다. 예를 들어 발신자는 "One"이라고 말하여 키 1에 매핑된 메뉴 옵션을 선택하거나 "Sales"라고 말하여 "Sales"라는 동일한 메뉴 옵션을 선택할 수 있습니다.
  
자동 참석자 및 메뉴 옵션을 설정하고 클라우드 자동 참석자 [설정 을 이동하세요.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>자동 참석자에 대한 전화 번호 할당

Microsoft 서비스 번호, 직접 라우팅 번호 또는 하이브리드 번호를 자동 참석자의 연결된 리소스 계정에 할당할 수 있습니다(전화 번호가 두 개 이상 필요한 경우 여러 리소스 계정에). 자세한 [내용은 직접](direct-routing-plan.md) 라우팅 계획 을 참조합니다.

서비스 번호를 할당하려면 기존 무료 서비스 번호를 얻거나 포트해야 합니다. 무료 서비스 전화 번호가 도착하면 **비즈니스용 Skype** 관리 센터 음성 전화 번호 에  >    >  **표시됩니다.** **번호 형식은** **서비스 - 무료 으로 나열됩니다.** 서비스 번호를 얻은 경우 비즈니스용 Skype 및 [Microsoft Teams에](./getting-service-phone-numbers.md) 대한 서비스 전화 번호 보기를 참조하거나 기존 서비스 번호를 이전하려는 경우 Teams로 전화 번호 전송을 [참조하세요.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> 미국 외의 경우 Microsoft Teams 관리 센터를 사용하여 서비스 번호를 얻을 수 없습니다. 대신 [조직의](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 전화 번호 관리로 이동하여 해당 작업을 하는 방법을 참조하세요.
  
## <a name="related-topics"></a>관련 주제

[다음은 통화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

[비즈니스용 Skype 및 Microsoft Teams의 서비스 전화 번호 받기](./getting-service-phone-numbers.md)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)