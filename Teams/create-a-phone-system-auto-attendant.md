---
title: 자동 참석자 설정 Microsoft Teams
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
description: 조직 내 대규모 조직에 대한 자동 참석자 설정 및 테스트 Microsoft Teams.
ms.openlocfilehash: a17921eee249d8baf10256e0d0ea17d4462494c0
ms.sourcegitcommit: 279ab5236431961c5181e2c01a69e5aa4290d381
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "60462362"
---
# <a name="set-up-an-auto-attendant"></a>자동 참석자 설정

자동 참석자는 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서에 문의하고 큐, 사람 또는 운영자에게 전화를 걸 수 있습니다. 관리자 센터 또는 PowerShell을 사용하여 조직의 자동 Microsoft Teams 만들 수 있습니다.

> [!TIP]
> 이 문서는 대규모 조직을 위한 문서입니다. 조직이 중소기업인 경우 자동 참석자 설정 [-](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) 중소기업 자습서를 대신 읽습니다.

이 문서의 절차를 수행하기 [전에](plan-auto-attendant-call-queue.md) 자동 Teams 대기열에 대한 [](plan-auto-attendant-call-queue.md#getting-started) 계획을 읽고 시작 단계를 따라야 합니다.

자동 참석자는 발신자 입력에 따라 다음 대상 중 하나에 전화를 걸 수 있습니다. <a name="call-routing-options" ></a>

- **연산자** - 자동 참석자에 대해 정의된 연산자입니다. 연산자 정의는 선택 사항입니다. 연산자는 이 목록의 다른 대상 중 하나로 정의할 수 있습니다.
- **조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람입니다. 이 사용자는 온라인 사용자일 수 있습니다. 또는 온라인 사용자를 사용하여 온라인 비즈니스용 Skype 서버.
- **음성 앱** - 다른 자동 참석자 또는 통화 큐입니다. (이 대상을 선택할 때 자동 참석자 또는 호출 큐와 연결된 리소스 계정을 선택하세요.)
- **Voicemail** - 지정한 그룹과 Microsoft 365 음성 사서함입니다. 음성 메일 전사와 "음색 후에 메시지를 남겨 주세요."를 선택할 수 있습니다. 시스템 프롬프트입니다.
- **외부 전화 번호** - 모든 전화 번호입니다. (외부 [전송 기술 세부 정보 참조).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **공지(오디오 파일)** - 오디오 파일을 재생합니다. 업로드한 기록된 공지 메시지는 에서 오디오로 저장됩니다. WAV, .MP3 또는 . WMA 형식입니다. 기록은 5MB보다 클 수 있습니다. 시스템에서 공지 사항을 재생한 다음 자동 참석 메뉴로 돌아갑니다.
- **공지(입력)** - 메시지를 입력합니다. 시스템을 읽을 텍스트입니다. 최대 1000자까지 입력할 수 있습니다. 시스템에서 공지 사항을 재생한 다음 자동 참석 메뉴로 돌아갑니다.

자동 참석자 설정 시 다양한 단계에서 이러한 옵션 중 하나를 선택하라는 메시지가 표시됩니다.

자동 참석을 설정하려면 관리 센터의 Teams **음성을** 확장하고 자동 참석자 선택 **및** 추가를 **선택합니다.**

## <a name="video-demonstration"></a>비디오 데모

이 비디오에서는 자동 참석자 를 만드는 방법에 대한 기본 예제를 Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a>일반 정보

![이름, 연산자, 표준 시간대, 언어 및 음성 입력에 대한 자동 참석자 설정 스크린샷.](media/auto-attendant-general-info-page-new.png)

1. 맨 위에 있는 상자에 자동 참석자 이름을 입력합니다.

2. 연산자를 지정하기 위해 연산자에 대한 호출에 대한 대상을 지정합니다. 이 지정은 선택 사항입니다(하지만 권장). **발신자가** 메뉴에서 끊어지고 지정된 사용자와 통화할 수 있도록 연산자 옵션을 설정합니다.

3. 이 자동 참석자에 대한 표준 시간대를 지정합니다. 표준 시간대는 시간 후 별도 통화 흐름을 만드는 경우 업무 시간을 계산하는 [데 사용됩니다.](#call-flow-for-after-hours)

4. 이 자동 [참석자에](create-a-phone-system-auto-attendant-languages.md) 대해 지원되는 언어를 지정합니다. 시스템 생성 음성 프롬프트에 사용되는 언어입니다.

5. 음성 입력을 사용하도록 설정할지 선택해야 합니다. 이 옵션을 사용하도록 설정하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다. 예를 들어 발신자는 "One"이라고 말하여 키 1에 매핑된 메뉴 옵션을 선택하거나 "Sales"라고 말하여 "Sales"라는 메뉴 옵션을 선택할 수 있습니다.

   > [!NOTE]
   > 음성 입력을 지원하지 않는 4단계에서 언어를 선택하면 이 옵션이 비활성화됩니다.

6. 다음 **을 선택합니다.**

## <a name="call-flow"></a>통화 흐름

![인사말 메시지 설정 스크린샷.](media/auto-attendant-call-flow-greeting-message.png)

자동 참석자가 통화에 응답할 때 인사말을 재생할지 선택해야 합니다.

오디오 파일 **재생을** 선택하면 파일 업로드 단추를 사용하여 에서 오디오로 저장된 기록된 **인사말** 메시지를 업로드할 수 있습니다. WAV, .MP3 또는 . WMA 형식입니다. 기록은 5MB보다 클 수 있습니다.

인사말  메시지 입력을 선택하면 자동 참석자가 통화에 응답할 때 입력하는 텍스트(최대 1000자)를 읽습니다.

![통화 라우팅 설정 스크린샷.](media/auto-attendant-call-flow-route-call-message.png)

호출을 라우팅할 방법을 선택해야 합니다.

연결 **끊기를 선택하면** 자동 참석자가 전화를 끊습니다.

리디렉션 **호출을 선택하면** 통화 라우팅 대상 중 하나를 선택할 수 있습니다.

메뉴 재생 옵션을 선택하는 경우 오디오  파일 재생  또는 인사말 메시지에 입력을 선택한 다음 메뉴 옵션과 디렉터리 검색 사이에서 선택할 수 있습니다. 

### <a name="menu-options"></a>메뉴 옵션

![다이얼 키 옵션 스크린샷.](media/auto-attendant-call-flow-menu-options-complete.png)

전화 걸기 옵션의 경우 전화 키패드의 0-9 키를 통화 라우팅 대상 중 하나에 할당합니다. (키 \* (반복) 및 (뒤로)는 시스템에서 예약되어 있으며 다시할 \# 수 없습니다.)

키 매핑은 연속적일 수 없습니다. 키 0, 1 및 3이 옵션에 매핑된 메뉴를 만들 수 있으며 숫자 2 키는 사용되지 않습니다.

0 키를 구성한 경우 연산자에 0 키를 매핑하는 것이 좋습니다. 연산자가 키로 설정되어 있지 않은 경우 음성 명령 "Operator"도 사용하지 않도록 설정됩니다.

각 메뉴 옵션에 대해 다음 설정을 지정합니다.

- **다이얼 키** - 이 옵션에 액세스하기 위한 전화 키 패드의 키입니다. 음성 입력을 사용할 수 있는 경우 호출자는 이 숫자를 말하여 옵션에 액세스할 수 있습니다.

- **음성 명령** - 음성 입력이 활성화되어 있는 경우 발신자에게 이 옵션에 액세스하기 위해 부여할 수 있는 음성 명령을 정의합니다. "고객 서비스" 또는 "작업 및 근거" 같은 여러 단어를 포함할 수 있습니다. 예를 들어 호출자에서 2를 누르거나 "2"라고 말하거나 "Sales"라고 말하여 두 키에 매핑된 옵션을 선택할 수 있습니다. 이 텍스트는 서비스 확인 프롬프트에 대해 음성으로 텍스트로 렌더링됩니다. "판매로 전화 전송" 같은 메시지가 표시될 수 있습니다.

- **리디렉션** - 호출자에서 이 옵션을 선택할 때 사용되는 호출 라우팅 대상입니다. 자동 참석자 또는 호출 큐로 리디렉션하는 경우 연결된 리소스 계정을 선택하세요.

### <a name="directory-search"></a>디렉터리 검색

대상에 다이얼 키를 할당하는 경우 디렉터리 검색에 대해 **없음을** **선택하는 것이 좋습니다.** 발신자는 특정 대상에 할당된 키를 사용하여 이름 또는 확장에 전화를 걸고자 하는 경우 이름 또는 확장 입력을 완료하기 전에 예기치 않게 대상에 라우팅될 수 있습니다. 디렉터리 검색을 위해 별도의 자동 참석자 를 만들고 다이얼 키로 기본 자동 참석자 링크가 있는 것이 좋습니다.

다이얼 키를 할당하지 않은 경우 디렉터리 검색 옵션을 **선택합니다.**

**전화 걸기** - 이 옵션을 사용하도록 설정하면 발신자는 사용자의 이름을 말하거나 전화 키패드에 입력할 수 있습니다. 온라인 사용자 또는 프레미스를 사용하여 호스팅된 모든 비즈니스용 Skype 서버 적격 사용자로, 전화 걸기 이름으로 찾을 수 있습니다. (전화 걸기 범위 페이지의 디렉터리에 포함되지 않은 사용자 및 포함하지 않는 사용자 를 설정할 [수](#dial-scope) 있습니다.)

**확장으로 전화** 걸기 - 이 옵션을 사용하도록 설정하면 발신자는 해당 전화 확장에 전화를 걸고 조직 내 사용자와 연결할 수 있습니다. 온라인 사용자 또는 프레미스를 사용하여 호스트된 모든 비즈니스용 Skype 서버 적격 사용자로, 전화 걸기 확장 을 **사용하여 찾을 수 있습니다.** (전화 걸기 범위 페이지의 디렉터리에 포함되지 않은 사용자 및 포함하지 않는 사용자 를 설정할 [수](#dial-scope) 있습니다.)

다이얼로 확장에 사용할 수 있도록 설정하려는 사용자는 Active Directory 또는 Azure Active Directory에 정의된 다음 휴대폰 특성 중 일부로 [](/microsoft-365/admin/add-users/add-users) 확장을 지정해야 합니다(자세한 내용은 사용자 추가를 개별적으로 또는 일괄 참조하세요.)

- OfficePhone
- HomePhone
- Mobile/MobilePhone
- PhoneNumber/PhoneNumber
- OtherTelephone

사용자 전화 번호 필드에 확장을 입력하는 데 필요한 형식은 다음 형식 중 하나일 수 있습니다.

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- 예제 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- 예제 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+155555678x5678"
- 예제 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

확장은 Microsoft 365 관리 센터 관리 [](https://admin.microsoft.com/) 센터에서 Azure Active Directory [수 있습니다.](https://aad.portal.azure.com) 자동 참석자 및 통화 큐에서 변경 내용을 사용할 수 있는 데 최대 12시간이 걸릴 수 있습니다.

> [!NOTE]
> 전화 걸기 이름  및 확장  기능 모두를 사용하려는 경우 기본 자동 전화 접속에 다이얼 키를 할당하여 이름에 따라 다이얼을 사용하도록 설정된 자동 참석자에 도달할 **수 있습니다.** 해당 자동 참석자 내에서 1개 키(해당 키와 연결된 문자가 없는)를 할당하여 확장 자동 전화 걸기 전화 접속에 도달할 수 있습니다. 

디렉터리 검색 옵션을 **선택한** 후 다음 을 **선택합니다.**

## <a name="call-flow-for-after-hours"></a>시간 후의 통화 흐름

![시간 및 시간 설정 후의 스크린샷입니다.](media/auto-attendant-business-hours.png)

각 자동 참석자에 대해 업무 시간을 설정할 수 있습니다. 업무 시간이 설정되지 않은 경우 24/7 일정이 기본적으로 설정되어 있기 때문에 하루의 모든 일 및 모든 시간은 영업 시간으로 간주됩니다. 업무 시간은 낮 동안의 휴식 시간으로 설정할 수 있으며, 영업 시간으로 설정되지 않은 모든 시간은 시간 후로 간주됩니다. 시간 이후의 다른 수신 통화 처리 옵션 및 인사말을 설정할 수 있습니다.

자동 참석자 및 통화 큐를 구성한 방법에 따라 직접 전화 번호가 있는 자동 참석자에 대한 시간 후 통화 라우팅만 지정할 수 있습니다.

시간 후 발신자에 대해 별도의 통화 라우팅을 원하는 경우 매일 업무 시간을 지정합니다. 새 **시간** 추가를 선택하여 특정 날짜에 대해 여러 시간 집합을 지정합니다(예: 점심 시간 지정).

업무 시간을 지정한 후 시간 후 통화 라우팅 옵션을 선택합니다. 위에서 지정한 업무 시간 호출 라우팅과 동일한 옵션을 사용할 수 있습니다.

완료되면  다음을 선택합니다.

## <a name="call-flows-during-holidays"></a>공휴일 동안 통화 흐름

![휴일 및 공휴일 인사 설정 스크린샷.](media/auto-attendant-holiday-greeting.png)

자동 참석자가 설정한 각 휴일에 대한 통화 [흐름을 설정할 수 있습니다.](set-up-holidays-in-teams.md) 각 자동 참석자에 최대 20일의 예약된 공휴일을 추가할 수 있습니다.

1. 휴일 통화 설정 페이지에서 추가를 **선택합니다.**

2. 이 휴일 설정의 이름을 입력합니다.

3. 휴일 **드롭다운에서** 사용할 공휴일을 선택해야 합니다.

4. 사용할 인사말 유형을 선택해야 합니다.

    ![휴일 통화 작업 설정 스크린샷.](media/auto-attendant-holiday-actions.png)

5. 통화 연결을 **끊거나** **리디렉션할지** 선택해야 합니다.

6. 리디렉션을 선택한 경우 통화에 대한 통화 라우팅 대상을 선택하세요.

7. **저장** 을 선택합니다.

![공휴일이 나열된 휴일 설정 스크린샷.](media/auto-attendant-holiday-call-settings.png)

추가 휴일마다 필요에 따라 절차를 반복합니다.

모든 공휴일을 추가한 경우 다음 을 **선택합니다.**

## <a name="dial-scope"></a>전화 걸기 범위

![다이얼 범위 스크린샷에는 옵션이 포함 및 제외됩니다.](media/auto-attendant-dial-scope.png)

전화 *걸기 범위는* 발신자에서 전화 접속 또는 전화 걸기 확장을 사용할 때 디렉터리에서 사용할 수 있는 사용자를 정의합니다. 모든 온라인 사용자의 **기본값에는** 조직의 모든 사용자가 온라인 사용자 또는 온라인 사용자를 사용하여 호스팅되는 비즈니스용 Skype 서버.

포함 또는 제외에서 사용자 지정 사용자 그룹을  선택하고  하나 이상의 그룹, 메일 그룹 또는 Microsoft 365 선택하여 특정 사용자를 포함하거나 제외할 수 있습니다.  예를 들어 조직의 임원을 전화 걸기 디렉터리에서 제외할 수 있습니다. (사용자가 두 목록에 있는 경우 디렉터리에서 제외됩니다.)

> [!NOTE]
> 새 사용자가 디렉터리에 자신의 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.

다이얼 범위를 설정하면 다음 을 **선택합니다.**

## <a name="resource-accounts"></a>리소스 계정

모든 자동 참석자는 연결된 리소스 계정이 있어야 합니다.  첫 번째 수준 자동 참석자는 연결된 서비스 번호가 있는 하나 이상의 리소스 계정이 필요합니다. 원하는 경우 별도의 서비스 번호가 있는 자동 참석자에 여러 리소스 계정을 할당할 수 있습니다.

![리소스 계정 추가 패널의 스크린샷.](media/auto-attendant-add-resource-account.png)

리소스 계정을 추가하려면 계정 추가를 **선택하고** 추가할 계정을 검색합니다. 추가 **를** 선택한 다음 추가를 **선택합니다.**

![할당된 서비스 번호가 있는 리소스 계정을 보여주는 리소스 계정 목록의 스크린샷입니다.](media/auto-attendant-resource-account-assigned.png)

리소스 계정 추가를 완료한  경우 제출을 선택하여 자동 참석자 구성을 완료합니다.

자세한 [Teams 리소스 계정 관리를](manage-resource-accounts.md) 참조하세요.

## <a name="external-phone-number-transfers---technical-details"></a>외부 전화 번호 전송 - 기술 세부 정보

자동 참석자가 외부에서 호출을 전송할 수 있도록 허용하기 위해 전제 구성표를 참조합니다. [](plan-auto-attendant-call-queue.md#prerequisites)  또한:

- 통화 계획 라이선스 [](calling-plans-for-office-365.md) 또는 운영자 번호가 있는 리소스 [계정의](operator-connect-plan.md) 경우 커넥트 외부 전송 전화 번호를 E.164 형식으로 입력해야 합니다(+[국가 코드][지역 코드][전화 번호]).

- 라이선스 및 전화 시스템 온라인 음성 라우팅 정책이 있는 리소스 계정의 경우 외부 전송 전화 번호 형식은 [SBC(세션](direct-routing-connect-the-sbc.md) 테두리 컨트롤러) 설정에 따라 달라 습니다.

표시되는 아웃바운드 전화 번호는 다음과 같이 결정됩니다.

  - 통화 계획 및 운영자 커넥트 번호의 경우 원래 발신자의 전화 번호가 표시됩니다.
  - 직접 라우팅 번호의 경우 보낸 숫자는 다음과 같이 SBC의 P-Asserted-Identity(PAI) 설정을 기반으로 합니다.
    - 사용 안 으로 설정하면 원래 발신자 전화 번호가 표시됩니다. 이 설정은 기본 설정 및 권장 설정입니다.
    - 사용하도록 설정하면 리소스 계정 전화 번호가 표시됩니다.

하이브리드 비즈니스용 Skype PSTN에 자동 참석자 호출을 전송하기 위해 PSTN 번호로 통화 전달 집합을 사용하여 새 On-프레미스 사용자를 생성합니다. 사용자가 사용자에 대해 사용하도록 설정해야 Enterprise Voice 음성 정책이 할당되어 있어야 합니다. 자세한 내용은 [PSTN으로 자동 전화 전송을 참조합니다.](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)

### <a name="create-an-auto-attendant-with-powershell"></a>PowerShell을 사용하여 자동 참석자 만들기

PowerShell을 사용하여 자동 참석자 만들기 및 설정할 수 있습니다. 자동 참석자 관리에 필요한 cmdlet은 다음과 같습니다.

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="auto-attendant-diagnostic-tool"></a>자동 전화 교환 진단 도구

관리자인 경우 다음 진단 도구를 사용하여 자동 참석자가 전화를 받을 수 있는지 확인할 수 있습니다.

1. 아래에서 **테스트** 실행을 선택하여 진단 센터에 진단을 Microsoft 365 관리 선택합니다. 

   > [!div class="nextstepaction"]
   > [테스트 실행: Teams 페더연맹](https://aka.ms/TeamsAADiag)

2. 진단 실행 창에서 사용자 이름 또는 전자 메일 필드에 **리소스** 계정을 입력한 다음 테스트 실행 **을 선택합니다.**

3. 테스트는 자동 수행자가 호출을 수신하지 못하게 하는 테넌트, 정책 또는 리소스 계정 구성을 식별하고 식별된 문제를 해결하기 위한 단계를 제공합니다.

## <a name="related-topics"></a>관련 항목

[다음은 사용자와 함께 얻을 Teams 전화](./here-s-what-you-get-with-phone-system.md)

[서비스 통화 번호 가져오기](./getting-service-phone-numbers.md)

[오디오 회의 및 통화 요금제 국가 및 지역 가용성](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Windows PowerShell 및 비즈니스용 Skype Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
