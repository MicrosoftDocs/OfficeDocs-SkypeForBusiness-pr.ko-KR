---
title: Microsoft Teams 자동 전화 교환 설정
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft Teams 대규모 조직에 대한 자동 전화 교환을 설정하고 테스트하는 방법을 알아봅니다.
ms.openlocfilehash: a0b50a83e54059dca68562c2140ece6253448dd0
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059099"
---
# <a name="set-up-an-auto-attendant"></a>자동 전화 교환 설정

자동 전화 교환을 통해 사용자가 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서, 통화 큐, 사람 또는 운영자에게 문의할 수 있습니다. Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 조직의 자동 전화 교환을 만들 수 있습니다.

> [!TIP]
> 이 문서는 대규모 조직을 위한 것입니다. 조직이 중소기업인 경우 [자동 전화 교환 설정 - 소규모 비즈니스 자습서](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) 를 읽어보세요.

이 문서의 절차를 따르기 전에 [Teams 자동 전화 교환 및 통화 큐에 대한 계획을](plan-auto-attendant-call-queue.md) 읽고 [시작 단계를](plan-auto-attendant-call-queue.md#getting-started) 수행했는지 확인합니다.

자동 전화 교환은 호출자의 입력에 따라 다음 대상 중 하나로 통화를 보낼 수 있습니다. <a name="call-routing-options" ></a>

- **연산자** - 자동 전화 교환에 대해 정의된 연산자입니다. 연산자 정의는 선택 사항입니다. 연산자는 이 목록의 다른 대상으로 정의할 수 있습니다.
- **조직의 사용자** - 음성 통화를 받을 수 있는 조직의 사용자입니다. 이 사용자는 온라인 사용자 또는 비즈니스용 Skype 서버 사용하여 온-프레미스에서 호스트되는 사용자일 수 있습니다.
- **음성 앱** - 다른 자동 전화 교환 또는 통화 큐. (이 대상을 선택할 때 자동 전화 교환 또는 통화 큐와 연결된 리소스 계정을 선택합니다.)
- **음성 메일** - 지정한 Microsoft 365 그룹과 연결된 음성 사서함입니다. 음성 메일 전사를 원하는지, "음색이 나면 메시지를 남겨주세요"를 선택할 수 있습니다. 시스템 프롬프트입니다.
- **외부 전화 번호** - 모든 전화 번호입니다. ( [외부 전송 기술 세부 정보](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 참조).
- **알림(오디오 파일)** - 오디오 파일을 재생합니다. 오디오로 저장된 업로드한 기록된 알림 메시지입니다. WAV, .MP3 또는 . WMA 형식입니다. 녹음/녹화는 5MB를 초과할 수 없습니다. 시스템에서 알림을 재생한 다음 자동 전화 교환 메뉴로 돌아갑니다.
- **알림(형식)** - 메시지를 입력합니다. 시스템에서 읽을 텍스트입니다. 최대 1,000자를 입력할 수 있습니다. 시스템에서 알림을 재생한 다음 자동 전화 교환 메뉴로 돌아갑니다.

자동 전화 교환을 설정할 때 다양한 단계에서 이러한 옵션 중 하나를 선택하라는 메시지가 표시됩니다.

자동 전화 교환을 설정하려면 Teams 관리 센터에서 **음성** 을 확장하고 **자동 전화 교환을** 선택한 다음 **추가** 를 선택합니다.

## <a name="video-demonstration"></a>비디오 데모

이 비디오에서는 Teams 자동 전화 교환을 만드는 방법에 대한 기본 예제를 보여줍니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>일반 정보

![이름, 운영자, 표준 시간대, 언어 및 음성 입력에 대한 자동 전화 교환 설정의 스크린샷](media/auto-attendant-general-info-page-new.png)

1. 맨 위에 있는 상자에 자동 전화 교환의 이름을 입력합니다.

2. 연산자를 지정하려면 연산자에 대한 호출 대상을 지정합니다. 이 지정은 선택 사항이지만 권장됩니다. 호출자가 메뉴를 벗어나 지정된 사람에게 말할 수 있도록 **운영자** 옵션을 설정합니다.

3. 이 자동 전화 교환의 표준 시간대를 지정합니다. 표준 시간대는 시간 [후 별도의 호출 흐름을 만드는](#call-flow-for-after-hours) 경우 업무 시간을 계산하는 데 사용됩니다.

4. 이 자동 전화 교환에 [지원되는 언어](create-a-phone-system-auto-attendant-languages.md) 를 지정합니다. 시스템 생성 음성 프롬프트에 사용되는 언어입니다.

5. 음성 입력을 사용하도록 설정할지 선택합니다. 사용하도록 설정하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다. 예를 들어 호출자는 "One"이라고 말하여 키 1에 매핑된 메뉴 옵션을 선택하거나 "Sales"라고 말하여 "Sales"라는 메뉴 옵션을 선택할 수 있습니다.

   > [!NOTE]
   > 4단계에서 음성 입력을 지원하지 않는 언어를 선택하면 이 옵션이 비활성화됩니다.

6. **다음** 을 선택합니다.

## <a name="call-flow"></a>호출 흐름

![인사말 메시지 설정의 스크린샷.](media/auto-attendant-call-flow-greeting-message.png)

자동 전화 교환이 전화에 응답할 때 인사말을 재생할지 선택합니다.

**오디오 파일 재생을** 선택하는 경우 **업로드 파일** 단추를 사용하여 오디오로 저장된 기록된 인사말 메시지를 업로드할 수 있습니다. WAV, .MP3 또는 . WMA 형식입니다. 녹음/녹화는 5MB를 초과할 수 없습니다.

**인사말 입력을** 선택하면 자동 전화 교환이 통화에 응답할 때 시스템에서 입력한 텍스트(최대 1,000자)를 읽습니다.

![통화 라우팅 설정의 스크린샷.](media/auto-attendant-call-flow-route-call-message.png)

통화를 라우팅하는 방법을 선택합니다.

**연결 끊기를** 선택하면 자동 전화 교환이 전화를 끊습니다.

**리디렉션 통화를** 선택하는 경우 통화 라우팅 대상 중 하나를 선택할 수 있습니다.

**재생 메뉴 옵션을** 선택하는 경우 **오디오 파일을 재생** 하거나 **인사말 메시지에 입력** 하도록 선택한 다음 메뉴 옵션과 디렉터리 검색 중에서 선택할 수 있습니다.

### <a name="menu-options"></a>메뉴 옵션

![다이얼 키 옵션의 스크린샷.](media/auto-attendant-call-flow-menu-options-complete.png)

전화 걸기 옵션의 경우 전화 키패드의 0-9 키를 통화 라우팅 대상 중 하나에 할당합니다. (키 \* (별표) 및 \# (파운드)는 시스템에서 예약되며 다시 할당할 수 없습니다. 이러한 키 중 하나를 누르면 현재 메뉴가 반복됩니다.)

> [!NOTE]
> # 키는 가장 최근의 자동 전화 교환에만 백업됩니다. 경계가 새 자동 전화 교환으로 넘어가면 # 키가 이전 키로 안내할 수 없습니다.

키 매핑은 연속적일 필요가 없습니다. 숫자 2 키는 사용되지 않지만 옵션에 매핑된 키 0, 1 및 3이 있는 메뉴를 만들 수 있습니다.

0 키를 구성한 경우 연산자에 매핑하는 것이 좋습니다. 연산자가 키로 설정되지 않은 경우 음성 명령 "Operator"도 사용하지 않도록 설정됩니다.

각 메뉴 옵션에 대해 다음 설정을 지정합니다.

- **전화 키 -** 이 옵션에 액세스하려면 전화 키패드의 키입니다. 음성 입력을 사용할 수 있는 경우 발신자는 이 번호라고 말하여 옵션에 액세스할 수도 있습니다.

- **음성 명령 - 음성** 입력을 사용하는 경우 호출자가 이 옵션에 액세스하기 위해 제공할 수 있는 음성 명령을 정의합니다. "고객 서비스" 또는 "운영 및 근거"와 같은 여러 단어를 포함할 수 있습니다. 예를 들어 호출자는 2를 누르거나 "2"라고 말하거나 "Sales"라고 말하여 두 키에 매핑된 옵션을 선택할 수 있습니다. 또한 이 텍스트는 서비스 확인 프롬프트에 대한 텍스트 음성 변환으로 렌더링됩니다. 이는 "판매로 통화 전송"처럼 표시될 수 있습니다.

- **리디렉션** - 호출자가 이 옵션을 선택할 때 사용되는 호출 라우팅 대상입니다. 자동 전화 교환 또는 통화 큐로 리디렉션하는 경우 연결된 리소스 계정을 선택합니다.

### <a name="directory-search"></a>디렉터리 검색

대상에 다이얼 키를 할당하는 경우 **디렉터리 검색** 에 대해 **없음** 을 선택하는 것이 좋습니다. 호출자가 특정 대상에 할당된 키를 사용하여 이름 또는 확장 프로그램에 전화를 걸려고 하면 이름 또는 확장 입력을 완료하기 전에 예기치 않게 대상으로 라우팅될 수 있습니다. 디렉터리 검색을 위한 별도의 자동 전화 교환을 만들고 기본 자동 전화 교환 링크를 다이얼 키와 함께 사용하는 것이 좋습니다.

다이얼 키를 할당하지 않은 경우 **디렉터리 검색** 옵션을 선택합니다.

**이름으로 전화 걸기** - 이 옵션을 사용하면 발신자가 사용자의 이름을 말하거나 전화 키패드에 입력할 수 있습니다. 온라인 사용자 또는 비즈니스용 Skype 서버 사용하여 온-프레미스에서 호스트되는 모든 사용자는 적격 사용자이며 이름별로 Dial을 사용하여 찾을 수 있습니다. ( [전화 걸기 범위](#dial-scope) 페이지의 디렉터리에 포함되고 포함되지 않은 사용자를 설정할 수 있습니다.)

**내선 번호로 전화 걸** 기 - 이 옵션을 사용하도록 설정하면 발신자가 전화 확장 프로그램에 전화를 걸어 조직의 사용자와 연결할 수 있습니다. 온라인 사용자 또는 비즈니스용 Skype 서버 사용하여 온-프레미스에서 호스트되는 모든 사용자는 적격 사용자이며 **Dial by Extension** 으로 찾을 수 있습니다. ( [전화 걸기 범위](#dial-scope) 페이지의 디렉터리에 포함되고 포함되지 않은 사용자를 설정할 수 있습니다.)

Dial By Extension에 사용할 수 있도록 하려는 사용자는 Active Directory(Azure AD 커넥트 통해 동기화됨) 또는 Azure Active Directory 정의된 다음 전화 특성 중 하나로 지정된 확장이 있어야 합니다. 자세한 내용은 [개별적으로 또는 대량으로 사용자 추가](/microsoft-365/admin/add-users/add-users) 를 참조하세요.

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

> [!NOTE]
> **다이얼 바이 이름과 내** 선 번호로 **전화 걸** 기 기능을 모두 사용하려는 경우 기본 자동 전화 교환에 다이얼 키를 할당하여 **이름으로 다이얼** 을 사용하도록 설정된 자동 전화 교환에 연결할 수 있습니다. 해당 자동 전화 교환 내에서 1개의 키(문자가 연결되어 있지 않음)를 할당하여 확장 자동 전화 교환 **으로 Dial에** 연결할 수 있습니다.

자세한 내용은 [전화 걸기 및 음성 참조](dial-voice-reference.md) 를 참조하세요.

**디렉터리 검색** 옵션을 선택한 후 **다음** 을 선택합니다.

## <a name="call-flow-for-after-hours"></a>시간 후 통화 흐름

![시간 및 시간 후 설정의 스크린샷.](media/auto-attendant-business-hours.png)

각 자동 전화 교환에 대해 업무 시간을 설정할 수 있습니다. 업무 시간이 설정되지 않은 경우 24/7 일정이 기본적으로 설정되기 때문에 하루의 모든 일 및 모든 시간은 업무 시간으로 간주됩니다. 업무 시간은 낮 시간 휴식 시간으로 설정할 수 있으며 업무 시간으로 설정되지 않은 모든 시간은 근무 시간 후로 간주됩니다. 시간 후 다른 수신 통화 처리 옵션 및 인사말을 설정할 수 있습니다.

자동 전화 교환 및 통화 큐를 구성한 방법에 따라 직접 전화 번호가 있는 자동 전화 교환에 대한 시간 후 통화 라우팅만 지정하면 됩니다.

근무 시간 후 발신자에 대해 별도의 통화 라우팅을 원하는 경우 매일 업무 시간을 지정합니다. **예를 들어 점심 시간을 지정하려면 새 시간 추가** 를 선택하여 지정된 날짜에 대한 여러 시간 집합을 지정합니다.

업무 시간을 지정한 후 몇 시간 후 통화 라우팅 옵션을 선택합니다. 위에서 지정한 업무 시간 통화 라우팅과 동일한 옵션을 사용할 수 있습니다.

완료되면 **다음** 을 선택합니다.

## <a name="call-flows-during-holidays"></a>휴일 동안 통화 흐름

![휴일 및 휴일 인사말 설정의 스크린샷.](media/auto-attendant-holiday-greeting.png)

자동 전화 교환은 [설정한 각 휴일](set-up-holidays-in-teams.md)에 대한 통화 흐름을 가질 수 있습니다. 각 자동 전화 교환에 최대 20개의 예약된 휴일을 추가할 수 있습니다.

1. 휴일 통화 설정 페이지에서 **추가** 를 선택합니다.

2. 이 휴일 설정의 이름을 입력합니다.

3. **휴일** 드롭다운에서 사용하려는 휴일을 선택합니다.

4. 사용할 인사말 유형을 선택합니다.

    ![휴일 통화 작업 설정의 스크린샷.](media/auto-attendant-holiday-actions.png)

5. **연결 끊기**, **리디렉션** 또는 **재생 메뉴 옵션을** 선택할 수 있습니다.

6. 리디렉션하도록 선택한 경우 통화에 대한 통화 라우팅 대상을 선택합니다.

7. 메뉴 옵션을 재생하도록 선택하는 경우 [메뉴 옵션을 구성합니다](#menu-options).

8. **저장** 을 선택합니다.

![휴일이 나열된 휴일 설정의 스크린샷](media/auto-attendant-holiday-call-settings.png)

각 추가 휴가에 대해 필요에 따라 절차를 반복합니다.

모든 휴일을 추가한 경우 **다음** 을 선택합니다.

## <a name="dial-scope"></a>전화 걸기 범위

![다이얼 범위 포함 및 제외 옵션의 스크린샷.](media/auto-attendant-dial-scope.png)

*전화 걸기 범위* 는 호출자가 전화 접속 또는 전화 접속 확장을 사용하는 경우 디렉터리에서 사용할 수 있는 사용자를 정의합니다. **모든 온라인 사용자의** 기본값은 온라인 사용자이거나 비즈니스용 Skype 서버 사용하여 온-프레미스에 호스트된 조직의 모든 사용자를 포함합니다.

**포함** 또는 제외에서 **사용자 지정 사용자 그룹을** 선택하고 하나 이상의 Microsoft 365 그룹, 메일 그룹  또는 보안 그룹을 선택하여 특정 사용자를 포함하거나 제외할 수 있습니다. 예를 들어 전화 걸기 디렉터리에서 조직의 임원을 제외할 수 있습니다. (사용자가 두 목록에 모두 있는 경우 디렉터리에서 제외됩니다.)

> [!NOTE]
> 새 사용자가 디렉터리에 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.

다이얼 범위 설정을 마쳤으면 **다음** 을 선택합니다.

## <a name="resource-accounts"></a>리소스 계정

모든 자동 전화 교환에는 연결된 리소스 계정이 있어야 합니다.  첫 번째 수준 자동 전화 교환에는 연결된 서비스 번호가 있는 하나 이상의 리소스 계정이 필요합니다. 원하는 경우 각 리소스 계정을 별도의 서비스 번호로 자동 전화 교환에 할당할 수 있습니다.

![리소스 계정 계정 추가 계정 패널의 스크린샷.](media/auto-attendant-add-resource-account.png)

리소스 계정을 추가하려면 **계정 추가** 를 선택하고 추가할 계정을 검색합니다. **추가** 를 선택한 다음 **추가** 를 선택합니다.

![할당된 서비스 번호가 있는 리소스 계정을 보여 주는 리소스 계정 목록의 스크린샷](media/auto-attendant-resource-account-assigned.png)

리소스 계정 추가를 마쳤으면 **제출** 을 선택하여 자동 전화 교환 구성을 완료합니다.

자세한 내용은 [Teams 리소스 계정 관리를 참조하세요](manage-resource-accounts.md).

## <a name="external-phone-number-transfers---technical-details"></a>외부 전화 번호 전송 - 기술 세부 정보

자동 전화 교환이 외부에서 통화를 전송할 수 있도록 하려면 [필수 구성 요소를](plan-auto-attendant-call-queue.md#prerequisites) 참조하세요.  또한:

- [통화 플랜 라이선스](calling-plans-for-office-365.md) 또는 [운영자 연결](operator-connect-plan.md) 번호가 있는 리소스 계정의 경우 외부 전송 전화 번호를 E.164 형식(+[국가 코드][지역 코드][전화 번호])으로 입력해야 합니다.

- Microsoft Teams 전화 라이선스 및 직접 라우팅 온라인 음성 라우팅 정책이 있는 리소스 계정의 경우 외부 전송 전화 번호 형식은 [SBC(세션 테두리 컨트롤러)](direct-routing-connect-the-sbc.md) 설정에 따라 달라집니다.

표시되는 아웃바운드 전화 번호는 다음과 같이 결정됩니다.

  - 통화 플랜 및 운영자 연결 번호의 경우 원래 발신자의 전화 번호가 표시됩니다.
  - 직접 라우팅 번호의 경우 보낸 숫자는 다음과 같이 SBC의 P-Asserted-Identity(PAI) 설정을 기반으로 합니다.
    - 사용 안 함으로 설정하면 원래 발신자의 전화 번호가 표시됩니다. 기본 설정이며 권장되는 설정입니다.
    - 사용으로 설정하면 리소스 계정 전화 번호가 표시됩니다.

비즈니스용 Skype 하이브리드 환경에서 자동 전화 교환 호출을 PSTN으로 전송하려면 PSTN 번호로 착신 전환이 설정된 새 온-프레미스 사용자를 만듭니다. 사용자는 Enterprise Voice 사용할 수 있어야 하며 음성 정책이 할당되어 있어야 합니다. 자세한 내용은 [PSTN으로 자동 전화 교환 통화 전송을](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn) 참조하세요.

## <a name="auto-attendant-cmdlets"></a>자동 전화 교환 cmdlet

Windows PowerShell 배치 또는 프로그래밍 방식으로 명령줄을 통해 자동 전화 교환을 만들고 관리할 수 있습니다.

다음 cmdlet을 사용하면 자동 전화 교환을 관리할 수 있습니다.

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

또한 통화 큐에 사용할 사용자, 리소스 계정, Microsoft Teams 전화 라이선스, 전화 번호, 오디오 파일 및 지원되는 언어를 관리하려면 다음과 같은 추가 cmdlet이 필요합니다.

사용자/Teams

- 사용자
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)

리소스 계정:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

가상 Teams 전화 라이선스:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

전화 번호 할당:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

오디오 파일

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

지원 언어 및 표준 시간대

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)

PowerShell을 사용하여 자동 전화 교환을 만드는 단계별 가이드는 [PowerShell cmdlet을 사용하여 자동 전화 교환 만들기를 참조하세요.](create-a-phone-system-auto-attendant-via-cmdlets.md)

## <a name="auto-attendant-diagnostic-tool"></a>자동 전화 교환 진단 도구

관리자인 경우 다음 진단 도구를 사용하여 자동 전화 교환이 전화를 받을 수 있는지 확인할 수 있습니다.

1. 아래의 **테스트 실행** 을 선택하면 Microsoft 365 관리 센터에서 진단이 채워집니다. 

   > [!div class="nextstepaction"]
   > [테스트 실행: 자동 전화 교환 Teams](https://aka.ms/TeamsAADiag)

2. 진단 실행 창의 **사용자 이름 또는 전자 메일** 필드에 리소스 계정을 입력한 다음 **테스트 실행을** 선택합니다.

3. 테스트는 자동 전화 교환이 전화를 받을 수 없도록 하는 테넌트, 정책 또는 리소스 계정 구성을 식별하고 식별된 문제를 해결하는 단계를 제공합니다.

## <a name="related-topics"></a>관련 항목

[Teams 전화](./here-s-what-you-get-with-phone-system.md)

[서비스 통화 번호 가져오기](./getting-service-phone-numbers.md)

[오디오 회의 및 통화 요금제 국가 및 지역 가용성](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell 및 비즈니스용 Skype Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
