---
title: 클라우드 자동 전화 교환 설정
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Microsoft 팀에 대 한 클라우드 자동 전화 교환을 설정 하 고 테스트 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bd23262a3b8cd3c50cffbb4be6aa70317d209613
ms.sourcegitcommit: a0df7479662b3bea488c19722ad588981f58a5e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/16/2019
ms.locfileid: "36447944"
---
# <a name="set-up-a-cloud-auto-attendant"></a>클라우드 자동 전화 교환 설정

자동 전화 교환을 통해 조직에 전화를 걸고 메뉴 시스템을 탐색 하 여 올바른 부서, 통화 대기열, 사람, 교환원에 게 얻을 수 있습니다. Microsoft 팀 관리 센터를 사용 하 여 조직의 자동 전화 교환을 만들 수 있습니다. 새 자동 전화 교환을 만들려면 왼쪽 탐색 창에서 **음성** 으로 이동한 다음 **자동 전화 교환** > **새로 추가**를 선택 합니다.

자동 전화 교환에 대해 자세히 알아보려면 [클라우드 자동 전화 교환 기능](/microsoftteams/what-are-phone-system-auto-attendants) 을 참조 하세요.

> [!NOTE]
> 이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.

## <a name="step-1--get-started"></a>1 단계-시작 하기

- 자동 전화 교환은 연결 된 리소스 계정이 있어야 합니다. 리소스 계정 및 필요한 모든 라이선스에 대 한 자세한 내용은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.

> [!TIP]
> **전화 시스템** 라이선스가 있는 온라인 사용자 인 연산자나 메뉴 옵션으로 호출을 리디렉션하려면 엔터프라이즈 음성에 대해 사용 하도록 설정 해야 합니다. [비즈니스용 Skype 라이선스 할당](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) 또는 [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요. Windows PowerShell을 사용할 수도 있습니다. 예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-a-new-auto-attendant"></a>2 단계-새 자동 전화 교환 만들기

> [!IMPORTANT]
> 모든 자동 전화 교환에는 연결 된 [리소스 계정이](manage-resource-accounts.md)있어야 합니다. 먼저 리소스 계정을 만든 다음 자동 전화 교환에 연결할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터 사용

**Microsoft 팀 관리 센터**에서 **음성** > **자동 전화 교환을**클릭 한 다음 **+ 새로 만들기**를 클릭 합니다.

#### <a name="general-info-page"></a>일반 정보 페이지

![내 자동 전화 교환 페이지의 스크린샷](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

**이름** 자동 전화 교환에 대 한 설명 표시 이름을 입력 합니다. 이름은 필수 이며 공백을 포함 하 여 최대 64 자를 포함할 수 있습니다. **자동 전화 교환** 탭의 **이름** 열에 나열 됩니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

**자원 계정** 하나 이상의 리소스 계정을 선택 하 여 새 자동 전화 교환에 연결 하려면이 단추를 클릭 합니다. 모든 자동 전화 교환에는 연결 된 리소스 계정이 있어야 합니다. 리소스 계정은 계정에 연결 된 전화 번호를 가질 수 있지만 전화 번호는 요구 사항이 아닙니다. 일반적으로 최상위 자동 전화 교환에는 할당 된 전화 번호가 있는 리소스 계정이 있지만, 중첩 된 자동 전화 교환 (첫 번째 수준 자동 전화 교환에 연결 되는 수준 2 메뉴로 사용)에는 해당 리소스 계정에 할당 된 전화 번호가 없을 수 있습니다.

* * *

![앞의 스크린샷은 설명선을 참조 하는 숫자 3의 아이콘](media/sfbcallout3.png)

**표준 시간대** 자동 전화 교환에 대 한 표준 시간대를 설정 해야 하지만 조직에 대해 나열 된 기본 주소의 표준 시간대에 해당 하지 않아도 됩니다. 각 자동 전화 교환은 다른 표준 시간대를 가질 수 있으며 자동 전화 교환에 설정 된 업무 시간은 여기서 선택한 표준 시간대에 따라 설정 됩니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 4의 아이콘](media/sfbcallout4.png)

**언어가** 나열 된 사용 가능한 언어 중에서 자동 전화 교환에 사용할 언어를 선택 합니다. 여기서 설정한 언어는 자동 전화 교환이이 자동 전화 교환에 연결 하는 사람들과 상호 작용 하는 데 사용 하는 언어 이며, 모든 시스템 메시지가이 언어로 재생 됩니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 5의 아이콘](media/sfbcallout5.png)

**연산자** 선택 사항 이지만 호출자가 메뉴를 차단 하 고 사용자에 게 말할 수 있도록 **연산자** 옵션을 설정할 수 있습니다.

0 키는 기본적으로 교환원에 게 할당 됩니다.

운영자를 설정 하는 경우 **비즈니스 시간 통화 처리** 페이지의 **편집 메뉴 옵션** 에서 해당 옵션에 대해 누가 전화를 하는지도 알려 주어 야 합니다. 자동 전화 교환에 운영자를 설정 하는 경우 **호출자가 듣기** 상자에 해당 프롬프트 텍스트를 입력 하거나이 옵션을 포함 하도록 오디오 파일을 변경 해야 합니다. 예를 들어 연산자의 경우 0을 누릅니다.

다음과 같은 여러 가지 방법으로 연산자를 설정할 수 있습니다.

- Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 요금제를 사용 하도록 설정 된 **전화 시스템** 라이선스가 있는 **회사의 사람** 입니다.

     > [!Note]
     > **회사** 사용자는 비즈니스용 Skype 서버 2015 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.

- **음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.
- 전화를 걸 사람을 음성 메일로 전송 하도록 설정할 수 있습니다. 이렇게 하려면 **회사에서 사람** 을 선택 하 고이 사용자의 통화가 바로 보이스 메일로 착신 전환 되도록 설정 합니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 6 번의 아이콘](media/sfbcallout6.png)

**음성 입력 사용** 이 옵션을 선택 하는 경우 음성 인식을 사용할 수 있습니다. 통화를 하는 사람들은 사용자가 [설정한 언어로](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)음성 입력을 사용할 수 있습니다. 다른 사용자만 전화 키패드를 사용할 수 있도록 하려면 음성 인식을 끄려면 (꺼짐)으로 설정 하 여 해제 하면 됩니다.

* * *

선택이 완료 되 면 **다음**을 클릭 합니다.

#### <a name="business-hours-page"></a>업무 시간 페이지

기본적으로 업무 시간은 월요일 ~ 금요일, 오전 9:00-5:00 pm으로 설정 됩니다. 업무 시간에 포함 되지 않은 모든 시간은 업무 시간 후로 간주 됩니다. **24/7 선택을** 클릭 하 여 업무 시간을 모두 만들 수 있습니다. **24/7 선택** 옵션을 선택 하지 않는 한, **이후 시간 통화 설정** 페이지는 자동 전화 교환에 대 한 업무 시간 후에 통화 처리 규칙을 구성 하는 데 사용 됩니다.

![업무 시간 페이지 스크린샷](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

기본적으로 업무 시간은 월요일 ~ 금요일, 오전 9:00-5:00 pm으로 설정 됩니다. **모든 시간 지우기** 옵션을 선택 하 여 일정에서 모든 시간의 선택을 취소 합니다. **기본값으로 재설정**을 선택 하면 업무 시간이 월요일에서 금요일, 오전 9:00은 5:00 pm으로 다시 설정 됩니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

업무 시간을 변경 하려면 일정에서 설정 하려는 업무 시간을 강조 표시 합니다. 달력을 사용 하면 30 분 간격으로 업무 시간을 선택 하 고 여기에서 선택한 업무 시간은 **일반 정보** 페이지에서 설정한 표준 시간대를 기준으로 합니다. 나누기를 설정 하려면 (예: 점심 작업 나누기) 일정에서 시간을 선택 취소 하거나 끌어서 선택 취소 합니다. 업무 시간 내에 여러 휴식을 설정할 수 있습니다.

* * *

선택이 완료 되 면 **다음**을 클릭 합니다.

#### <a name="business-hours-call-settings"></a>업무 시간 통화 설정

> [!TIP]
> 사용자 지정 업무 시간 일정을 사용 하는 경우에는 업무 시간 통화 **처리** 페이지를 사용 하 여 근무 시간 후에도 통화 연결을 설정 해야 하며,이 경우 **업무 시간 통화 설정과**동일한 옵션을 제공 합니다.

업무 시간 중 조직의 자동 전화 교환에 연결 된 전화 번호로 전화할 때 들리는 인사말, 메시지 및 메뉴를 설정할 수 있습니다.

![비즈니스 시간 통화 처리](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![페이지 업무 시간 호출 처리 페이지 동작 섹션 스크린샷의 스크린샷](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

**인사말이** 업무 시간 인사말은 선택 사항이 며 **인사말 없음으로**설정할 수 있습니다. 이 경우 호출자는 사용자가 선택한 작업 중 하나에서 호출을 처리 하기 전에 메시지 또는 인사말이 들리지 않습니다. 오디오 파일 (.wav, mp3 또는 .wma 형식)을 업로드 하거나 텍스트 읽어주기를 사용 하 여 사용자 지정 인사말을 만들 수도 있습니다.
- **오디오 파일 업로드** 이를 선택 하는 경우 인사말을 녹음 한 다음 오디오 파일 (.wav,. mp3 또는 .wma 형식)을 업로드 합니다.
- **인사말 메시지 입력** 이 옵션을 선택 하는 경우 시스템에서 읽을 텍스트를 입력 합니다 (최대 1000 자). 예를 들어 "Contoso 시작 '을 입력할 수 있습니다. 귀하의 전화는 귀하에 게 중요 합니다. " **발신자가 들립니다** 상자를 말합니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

업무 시간 동안 도착 하는 전화를 선택할 수 있습니다. 다음 작업 중에서 선택할 수 있습니다.

- **연결 해제** 이를 선택 하면 업무 시간 인사말이 들릴 때 전화를 거는 사용자의 연결이 끊어집니다.
- **통화 리디렉션** 이를 사용 하 여 자동으로 통화를 보낼 수 있습니다.
  - Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 요금제를 사용 하도록 설정 된 **전화 시스템** 라이선스가 있는 **회사의 사람** 입니다. 전화를 걸 사람을 보이스 메일로 보낼 수 있도록 설정할 수 있습니다. 이렇게 하려면 **회사에서 사람** 을 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.

    > [!Note]
    > **회사 사용자** 는 비즈니스용 Skype 서버 2015 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.

   - 다른 **자동 전화 교환**

   기존 자동 전화 교환을 사용 하 여 하위 메뉴를 포함 하는 두 번째 수준의 메뉴 옵션을 만들 수 있습니다. 이를 중첩 된 자동 전화 교환 이라고 합니다. 중첩 된 자동 전화 교환으로 통화를 보내려면 **회사에서 사용자** 를 선택 하 고 이미 연결 된 자동 전화 교환이 있는 리소스 계정이 나이 자동 전화 교환 만들기가 완료 되 면 자동 전화 교환에 연결 되도록 할당 합니다.

- **재생 메뉴 옵션** 을 사용 하 여 재생 하려는 메시지를 설정할 수도 있습니다.

* * *

![앞의 스크린샷은 설명선을 참조 하는 숫자 3의 아이콘](media/sfbcallout3.png)

**메뉴 프롬프트** 주 메뉴 프롬프트를 만들려면 텍스트 음성 변환 또는 오디오 파일 업로드 (.wav,. mp3 또는 .wma)를 사용할 수 있습니다. **호출자의 메뉴 탐색 설정** 상자에 프롬프트를 입력 하거나 오디오 파일을 녹음/녹화할 수 있습니다 (예: "판매를 위해"). 서비스의 경우 2를 누르거나 말을 누릅니다. 고객 지원이 필요한 경우에는 3을 누르거나 말합니다. 연산자의 경우 0을 누르거나 말을 누릅니다. 이 메뉴를 다시 들으려면 star 키를 누르거나 "반복" 이라고 말 하세요. " **인사말 메시지 입력** 이를 선택한 경우에는 시스템에서 읽을 텍스트 (최대 1000 자)를 입력 해야 합니다. **오디오 파일 업로드** 이를 선택한 경우에는 인사말을 녹음 한 다음 오디오 파일 (.wav, mp3 또는 .wma 형식)을 업로드 해야 합니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 4의 아이콘](media/sfbcallout4.png)

**메뉴 옵션 설정** 키패드의 키 단추를 사용 하 여 메뉴 옵션을 추가 하거나 제거할 수 있습니다. 메뉴 옵션을 추가 하려면 **+ 다이얼 키 할당**을 누릅니다. 해당 하는 옵션 행이 아래에 표시 됩니다. 메뉴 옵션을 삭제 하려면 키패드 컨트롤에서 해당 키의 왼쪽을 클릭 하 고 위의 삭제 아이콘을 클릭 하면 됩니다. 키 매핑 행이 제거 됩니다.

> [!TIP]
> 기존 메뉴 프롬프트에 대해 자동으로 수행 되지 않으므로 제거 옵션에 추가 하는 경우 메뉴 프롬프트 텍스트를 업데이트 하거나 오디오를 개별적으로 다시 기록 해야 합니다.  
>
>모든 메뉴 옵션을 순서에 관계 없이 추가 하 고 제거할 수 있으며 키 매핑도 연속적으로 사용할 필요가 없습니다. 예를 들어 옵션에 매핑된 키가 0, 1, 3 인 메뉴를 만들 수 있지만 키 2는 사용 되지 않습니다.

> [!NOTE]
> 키 \* (반복)와 \# (뒤로)는 시스템에 예약 되어 있으므로 다시 할당할 수 없습니다. 음성 인식 기능을 사용 하는 경우 *를 누르면 "Repeat"와 #이 "뒤로" 음성 명령에 해당 합니다.

메뉴 옵션을 설정 하려면 다이얼 키를 선택한 후 다음을 수행 해야 합니다.

- 옵션의 **음성 명령을** 입력 합니다. 이는 최대 64 자를 입력할 수 있으며 "고객 서비스" 또는 "작업 및 Grounds" 같은 여러 단어를 포함할 수 있습니다. 음성 인식 기능을 사용 하는 경우 자동으로 이름이 인식 되 고, 통화를 하는 사용자는 3을 눌러 "3" 이라고 말할 수 있으며, "고객 서비스" 라고 말할 때 키 3에 매핑된 옵션을 선택 하 게 됩니다.
- 해당 키를 누르거나 음성 인식을 사용 하 여 옵션을 선택한 경우 통화를 보낼 위치를 선택 합니다. 통화는 다음으로 전송 될 수 있습니다.

  - **연산자** If 연산자가 이미 설정 되어 있으면 키 0에 자동으로 매핑되지만, 삭제 하거나 다른 키에 다시 할당할 수도 있습니다. If 연산자를 아무 키로 설정 하지 않으면 음성 명령 "교환원"도 비활성화 됩니다.
  - **회사에서** 엔터프라이즈 음성에 대해 사용 하도록 설정 되거나 Office 365에서 호출 계획을 할당 한 **전화 시스템** 라이선스가 있는 사람입니다. 전화를 걸 사람을 보이스 메일로 보낼 수 있도록 설정할 수 있습니다. 이렇게 하려면 **회사에서 사람** 을 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.

    > [!Note]
    > **회사** 사용자는 비즈니스용 Skype 서버 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.
    - 다른 **자동 전화 교환**

       기존 자동 전화 교환을 사용 하 여 하위 메뉴를 포함 하는 두 번째 수준의 메뉴 옵션을 만들 수 있습니다. 이를 중첩 된 자동 전화 교환 이라고 합니다. 중첩 된 자동 전화 교환으로 통화를 보내려면 **회사에서 사용자** 를 선택 하 고 이미 연결 된 자동 전화 교환이 있는 리소스 계정이 나이 자동 전화 교환 만들기가 완료 되 면 자동 전화 교환에 연결 되도록 할당 합니다.

        > [!Note]
        > 설치 된 다른 자동 전화 교환에서 보내는 통화를 포함 하 여 중첩 (또는 두 번째 수준) 자동 전화의 **업무 시간이** 함께 사용 됩니다.

       - **음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 5의 아이콘](media/sfbcallout5.png)

**이름으로 전화 걸기** 이 옵션을 선택 하면에서 전화를 거는 사용자가 디렉터리 검색을 사용 하 여 조직 내 사용자를 검색할 수 있게 됩니다. **전화 걸기 범위** 페이지에서 해당 옵션을 설정 하 여 전화를 걸 수 있거나 이름으로 사용할 수 없는 사람을 선택할 수 있습니다. **전화 시스템** 라이선스가 있는 모든 온라인 사용자 또는 비즈니스용 Skype 서버 또는 Lync server 2013을 사용 하 여 온-프레미스에 호스팅되는 사용자는 이름으로 전화 걸기를 찾을 수 있습니다.

* * *

선택이 완료 되 면 **다음**을 클릭 합니다.

#### <a name="holiday-call-settings"></a>명절 통화 설정

각 자동 전화 교환에 최대 20 개의 예정 휴일을 추가할 수 있습니다.

> [!TIP]
> **조직도** > **** 에서 화면을 진행 하 여 공휴일을 만들거나 새 통화 처리기를 만드는 과정에서 만들 수 있습니다.

![명절 통화 설정 페이지 스크린샷](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

이미 자동 전화 교환을 만든 경우에는이 목록에서 필요한 항목을 사용 하거나 편집할 수 있는 옵션이 표시 될 수 있습니다. 그렇지 않은 경우 새 통화 처리기를 만들어야 합니다.

새 호출 처리기를 추가 하려면 **+ 새 통화 처리기**를 클릭 합니다.

* * *

![새 통화 처리기 추가를 보여주는 스크린샷](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![이전 스크린샷의 설명선을 참조 하는 숫자 1의 아이콘](media/sfbcallout1.png)

새 창에서 화면 맨 위에 새 통화 처리기의 이름을 입력 합니다.

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

명절의 이름이 **휴일** 풀 다운 목록에 이미 있는 경우 사용할 수 있습니다. 필요한 휴일 이름이 없는 경우에는 풀 다운 목록에서 **새 공휴일 만들기** 를 선택 하 고 새 공휴일이 표시 되는 새 명절에 대 한 이름과 날짜를 지정 합니다. 준비가 되 면 **저장** 을 클릭 합니다.

공휴일 이름은 최대 64 자로 구성 될 수 있으며 동일한 자동 전화 교환에 대해 고유 해야 합니다. 예를 들어 같은 자동 전화 교환에서 "추수 감사절" 이라는 두 개의 공휴일을 사용할 수 없습니다.

![앞의 스크린샷은 설명선을 참조 하는 숫자 3의 아이콘](media/sfbcallout3.png)

**인사말이** 인사말은 선택 사항이 며 **인사말 없음으로**설정할 수 있습니다. 이 경우 발신자는 사용자가 선택 하는 옵션 중 하나에서 통화를 처리 하기 전에 메시지나 인사말이 들리지 않습니다. 오디오 파일 (.wav, mp3 또는 .wma 형식)을 업로드 하거나 텍스트 읽어주기를 사용 하 여 사용자 지정 인사말을 만들 수도 있습니다.

- **인사말 없음** 다른 사용자가 자동 전화 교환 전화 번호로 전화를 걸 때 인사말이 재생 되지 않습니다.
- **오디오 파일 업로드** 이를 선택 하는 경우 명절 인사말을 기록 하 고 오디오 파일 (.wav,. mp3 또는 .wma 형식)을 업로드 합니다.
- **인사말 메시지 입력** 이 옵션을 선택 하는 경우 시스템에서 읽을 텍스트를 입력 합니다 (최대 1000 자). 예를 들어 "새 해 아침에 행복!"를 입력할 수 있습니다. 현재 사무실이 닫혔습니다. " **인사말 메시지 입력** 상자에

![이전 스크린샷의 설명선을 참조 하는 숫자 4의 아이콘](media/sfbcallout4.png)

**작업** 이 휴일 동안 도착 하는 통화에 대 한 진행 상황을 선택할 수 있습니다. 다음 옵션 중에서 선택할 수 있습니다.

- **연결 해제** 명절 인사말이 들릴 때 전화를 거는 사람이 연결 해제 됩니다.
- **통화 리디렉션** 이를 사용 하 여 자동으로 통화를 보낼 수 있습니다.
  - Office 365에서 엔터프라이즈 음성 또는 할당 된 통화 요금제를 사용 하도록 설정 된 **전화 시스템** 라이선스가 있는 **회사의 사람** 입니다. 전화를 걸 사람을 보이스 메일로 보낼 수 있도록 설정할 수 있습니다. 이렇게 하려면 **회사에서 사람**을 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.

    > [!Note]
    > **회사** 사용자는 비즈니스용 Skype 서버 2015 또는 Lync server 2013을 사용 하 여 온-프레미스 사용자 또는 온라인 사용자가 될 수 있습니다.

   - **음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.

    > [!Note]
    > 기본적으로 휴일 기간 중에 도착 하는 모든 통화는 인사말 이후 연결 해제로 설정 되므로 다른 동작이 필요 하면 리디렉션을 지정 해야 합니다.

#### <a name="select-dial-scope-page"></a>전화 걸기 범위 페이지 선택

이 페이지에서 조직에 속한 사용자가 디렉터리에 나열 되 고 조직에 전화를 거는 사용자가 이름으로 다이얼을 사용할 수 있도록 설정할 수 있습니다.

![전화 걸기 범위 페이지를 보여 주는 스크린샷](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![](media/sfbcallout1.png) **포함** 옵션을 사용 하 여 이전 화면의 설명선을 참조 하는 숫자 1의 아이콘은 다음 두 가지 옵션을 사용할 수 있습니다.

- **모든 온라인 사용자** 이 옵션을 사용 하면 조직 내 모든 사용자가 디렉터리 검색에 포함 될 수 있습니다. **휴대폰 시스템** 라이선스가 있는 모든 온라인 사용자는 물론 비즈니스용 Skype를 사용 하 여 온-프레미스를 호스트 하는 사용자와 Office 365에서 호출 계획이 있는 Lync server 2013이 나열 됩니다.
- 사용자 **지정 사용자 그룹** 이 옵션을 사용 하는 경우 조직에서 만든 Office 365 그룹, 메일 그룹 또는 보안 그룹을 검색 하 고,이 Office 365 그룹, 메일 그룹 또는 사용자가 추가 된 온라인 사용자를 포함 하는 개인을 검색할 수 있습니다. ** **Skype server 2015 또는 Lync server 2013를 사용 하 여 온-프레미스로 전화 시스템 라이선스 또는 호스팅 여러 개의 Office 365 그룹, 배포 목록, 보안 그룹을 추가할 수 있습니다.

* * *

![이전 스크린샷의 설명선을 참조 하는 숫자 2의 아이콘](media/sfbcallout2.png)

**Exclude** 옵션을 사용 하 여 다음 두 가지 옵션을 사용할 수 있습니다.

- **없음** 이 옵션을 사용 하면 디렉터리 검색에서 온라인 사용자가 제외 됨이 표시 됩니다.
- 사용자 **지정 사용자 그룹** 이 옵션을 사용 하는 경우 조직에서 만든 Office 365 그룹, 메일 그룹 또는 보안 그룹을 검색할 수 있으며,이 Office 365 그룹, 메일 그룹 또는 보안 그룹에 추가 된 모든 사용자는 디렉터리 검색에서 제외 됩니다. 여러 개의 Office 365 그룹, 배포 목록, 보안 그룹을 추가할 수 있습니다.

> [!NOTE]
> 사용자가 음성 인식을 사용 하 여 이름으로 전화 걸기를 사용할 때 새 사용자가 디렉터리에 이름을 나열 하는 데 최대 36 시간이 걸릴 수 있습니다.

필요한 모든 필드를 입력 하 고 통화 처리 메뉴 및 옵션을 설정한 후 **제출을**클릭 합니다.

## <a name="editing-and-testing-auto-attendants"></a>자동 전화 교환 편집 및 테스트

자동 전화 교환을 저장 하면 **자동 전화 교환** 페이지에 나열 됩니다. 이렇게 하면 이름, 전화 번호, 언어, 상태 등 설정한 일부 옵션을 빠르게 확인할 수 있습니다.

자동 전화 교환을 변경 하려는 경우 자동 전화 교환을 선택 하 고 작업 창에서 **편집**을 클릭 합니다.

또한 작업 창의 **테스트** 단추를 사용 하 여 자동 전화 교환에 테스트 통화를 빠르게 배치할 수 있습니다.

## <a name="auto-attendant-cmdlets"></a>자동 전화 교환 cmdlet

Windows PowerShell을 사용 하 여 자동 전화 교환을 만들고 설정할 수도 있습니다. 자동 전화 교환을 관리 하는 데 필요한 cmdlet은 다음과 같습니다.

- [신규-CsAutoAttendant 전화 교환](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant 전화 교환](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendant 전화 교환](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [-CsAutoAttendant 전화 교환 제거](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [새로운 CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [새로운 CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [새로운 CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [새로운 CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [새로운 CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [새로운 CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [새로운 CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [가져오기-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [새로운 CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 Microsoft 팀을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

  - [Windows PowerShell 및 Lync Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell을 사용 해야 하는 이유](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.

  - [Office 365 PowerShell을 사용 하 여 Office 365 관리](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>관련 항목

[Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[서비스 전화 번호 가져오기](/microsoftteams/getting-service-phone-numbers)

[오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능 여부](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[새로운 CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[클라우드 자동 전화 교환 이란?](what-are-phone-system-auto-attendants.md)

[Small business 예-자동 전화 교환 설정](/microsoftteams/tutorial-org-aa)  
