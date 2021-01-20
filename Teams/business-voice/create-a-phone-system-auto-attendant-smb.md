---
title: Microsoft Teams에 대한 자동 참석자 설정 - Small Business 자습서
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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft 365 Business Voice에 대한 자동 attendants를 설정하고 테스트하는 방법을 배워야 합니다.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909638"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a>자동 참석자 설정 - 중소기업 자습서

자동 전화 회의를 통해 다른 사람이 조직에 전화를 걸고 메뉴 시스템을 탐색하여 올바른 부서, 통화 큐, 사람 또는 운영자에게 문의할 수 있습니다. Microsoft Teams 관리 센터를 사용하여 조직의 자동 참석자도 만들 수 있습니다.

#### <a name="before-you-begin"></a>시작하기 전에

조직 외부에서 직접 전화를 걸면 액세스할 수 있는 자동 전화 회의에 필요한 서비스 번호를 얻을 수 있습니다. 여기에는 다른 [공급자의 번호](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 이전 또는 새 서비스 번호 [요청이 포함됩니다.](../getting-service-phone-numbers.md)

전화 시스템 [- 만들](../teams-add-on-licensing/virtual-user.md) 계획인 각 자동 전화 연결에 대한 가상 사용자 라이선스를 얻습니다. 이러한 라이선스는 무료이기 때문에 향후 설정을 변경하기로 결정한 경우 몇 가지 추가 사항을 추가하는 것이 좋습니다.

휴일에 자동 전화 걸기 경로 통화를 다르게 설정하려는 경우 자동 전화 회의를 만들기 전에 사용할 공휴일을 만드시겠어요. [](../set-up-holidays-in-teams.md)

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>다음 단계에 따라 자동 참석자 설정

# <a name="step-1brphone-number"></a>[1단계 <br> 전화 번호](#tab/phone-number)

만드는 각 자동 참석자에는 리소스 계정이 필요합니다. 계정이 개인 대신 자동 전화 걸기 또는 통화 큐와 연결되어 있는 것을 제외하고는 사용자 계정과 비슷합니다. 이 단계에서는 계정을 *만들고, Microsoft 365* 전화 시스템 - 가상 사용자 라이선스를 할당한 다음, 서비스 번호를 할당합니다.

### <a name="create-a-resource-account"></a>리소스 계정 만들기

Teams 관리 센터에서 리소스 계정을 만들 수 있습니다.

1. Teams 관리 센터에서 **전체 설정을** 확장한 다음 리소스 **계정을 클릭합니다.**

2. 추가를 **클릭합니다.**

3. 리소스 계정 추가 **창에서** 표시 **이름,** 사용자 이름을 입력하고 리소스 계정 유형에 대한  **자동** **참석자를 선택하세요.**

    ![리소스 계정 사용자 인터페이스 추가 스크린샷](../media/resource-account-add.png)

4. **저장** 을 클릭합니다.

새 계정이 계정 목록에 표시됩니다.

![리소스 계정 목록의 스크린샷](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>라이선스 할당

리소스 계정에 *Microsoft 365 Phone System - 가상 사용자* 라이선스를 할당해야 합니다.

1. Microsoft 365 관리 센터에서 라이선스를 할당하려는 리소스 계정을 클릭합니다.

2. 라이선스 **및** 앱 탭의 **라이선스** **아래에서 Microsoft 365 전화** 시스템 - 가상 사용자를 선택합니다.

3. 변경 **내용 저장을 클릭합니다.**

    ![Microsoft 365 관리 센터의 라이선스 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a>서비스 번호 할당

이 자동 전화 번호를 전화 번호로 연결하려면 해당 번호를 리소스 계정에 할당합니다.

1. Teams 관리 센터의 리소스  계정 페이지에서 서비스 번호를 할당할 리소스 계정을 선택한 다음 **할당/할당을 클릭합니다.**

2. 전화 번호 **유형 드롭다운에서** 사용할 번호 유형을 선택 합니다.

3. 할당된 **전화 번호** 상자에서 사용할 번호를 검색하고 추가를 **클릭합니다.**

    ![서비스 번호 사용자 인터페이스 할당 스크린샷](../media/resource-account-assign-phone-number.png)

4. **저장** 을 클릭합니다.

> [!div class="nextstepaction"]
> [2단계 - 자동 참석자 일반 정보 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[2단계 <br> 참석자 일반 정보](#tab/general-info)

자동 참석자 설정

1. Teams 관리 센터에서 **음성을** 확장하고 자동 참석을 클릭한 다음 추가를 **클릭합니다.**

2. 맨 위에 있는 상자에 자동 참석자 이름을 입력합니다.

3. 연산자를 지정하려는 경우 연산자에 대한 호출 대상을 지정합니다. 이는 선택 사항입니다(하지만 권장). 발신자가  메뉴를 중단하고 지정된 담당자에게 말할 수 있도록 연산자 옵션을 설정할 수 있습니다.

4. 이 자동 참석자에 대한 표준 시간대를 지정합니다. 표준 시간대는 시간 후 별도의 호출 흐름을 만드는 경우 업무 시간을 계산하는 데 사용됩니다.

5. 이 자동 참석자에 대한 언어를 지정합니다. 시스템 생성 음성 프롬프트에 사용할 언어입니다.

6. 음성 입력을 사용하도록 설정할지 선택 합니다. 사용하도록 설정하면 모든 메뉴 옵션의 이름이 음성 인식 키워드가 됩니다. 예를 들어 발신자는 키 1에 매핑된 메뉴 옵션을 선택하기 위해 "One"이라고 말하거나 "판매"라고 말하여 "판매"라는 메뉴 옵션을 선택할 수 있습니다.

    ![이름, 연산자, 표준 시간대, 언어 및 음성 입력에 대한 자동 Attendant 설정 스크린샷](../media/auto-attendant-general-info-page-new.png)

7. 다음을 **클릭합니다.**

> [!div class="nextstepaction"]
> [3단계 - 호출 흐름 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[3단계 <br> 호출 흐름](#tab/call-flow)

통화 흐름 옵션 선택

1. 자동 전화 문의가 통화에 응답할 때 인사말을 재생할지 선택 합니다.

    오디오 파일 **재생을** 선택하면 파일  업로드 단추를 사용하여 오디오로 저장된 녹화된 인사말 메시지를 업로드할 수 있습니다. WAV, . MP3 또는 . WMA 형식입니다. 기록은 5MB보다 클 수 있습니다.

    인사말  메시지 입력을 선택하면 자동 전화 문의가 전화를 걸 때 입력한 텍스트(최대 1,000자)를 시스템에서 읽습니다.

    ![인사말 메시지 설정 스크린샷](../media/auto-attendant-call-flow-greeting-message.png)

2. 통화를 라우팅할 방법을 선택 합니다.

    연결 **끊기를 선택하면** 자동 전화 연결이 끊어집니다.

    리디렉션 **호출을 선택하는** 경우 통화 라우팅 대상 중 하나를 선택할 수 있습니다.

    재생 **메뉴** 옵션을 선택하는 경우 인사말 메시지에서  오디오 파일 또는 입력을 재생한 다음 메뉴 옵션과 디렉터리 검색을 선택할 수 있습니다. 

    ![통화 라우팅 설정 스크린샷](../media/auto-attendant-call-flow-route-call-message.png)

3. 발신자에서 다이얼 키를 사용하여 탐색할 수 있는 경우 설정 메뉴 옵션에서 발신자 전화 키를 누를 때 발생하려는 항목을 선택합니다. (이 자동 전화 번호를 회사 디렉터리로 만드는 경우 다이얼 키 옵션을 비워 두십시오.)

    다이얼 키를 다음 대상으로 설정할 수 있습니다.

    - **조직의 사람** - 음성 통화를 받을 수 있는 조직의 사람입니다.
    - **음성 앱** - 다른 자동 전화 걸기 또는 통화 큐입니다.
    - **외부 전화 번호** - 모든 전화 번호입니다. +[국가 코드][지역 번호][전화 번호] 형식 사용
    - **음성 메일** - 지정한 Microsoft 365 그룹과 연결된 음성 사서함입니다.
    - **연산자** - 자동 attendant에 대해 정의된 연산자입니다. 연산자 정의는 선택 사항입니다. 연산자는 이 목록의 다른 대상 중 하나로 정의할 수 있습니다.

    연산자에 0 키를 설정하는 것이 좋습니다.

    각 메뉴 옵션에 대해 다음을 지정합니다.

    - **전화기 키** - 이 옵션에 액세스하기 위한 전화 키패드의 키입니다.

    - **음성 명령** - 음성 입력이 활성화된 경우 발신자에서 이 옵션에 액세스하기 위해 부여할 수 있는 음성 명령을 정의합니다. "고객 서비스" 또는 "작업 및 근거"과 같은 여러 단어를 포함할 수 있습니다. 

    - **리디렉션** - 호출자에서 이 옵션을 선택할 때 통화를 이동하려는 위치입니다. 자동 전화 연결 또는 통화 큐로 리디렉션하는 경우 연결된 리소스 계정을 선택하세요.

    ![다이얼 키 옵션 스크린샷](../media/auto-attendant-call-flow-menu-options-complete.png)

4. 이 자동 전화 접속을 회사 디렉터리로 사용하려면 디렉터리 검색 아래에서 **Dial by Name을 선택합니다.** 이 옵션을 사용하도록 설정하면 발신자는 사용자의 이름을 말하거나 전화 키패드에 입력할 수 있습니다. 전화 시스템 라이선스가 있는 모든 온라인 사용자는 적격 사용자로 전화 걸기 이름으로 찾을 수 있습니다. 

    (확장명에 따라 **Dial by를** 선택할 수 있습니다. 하지만 확장은 Azure Active Directory에서 구성해야 합니다.)

5. 디렉터리 검색 옵션을 선택한 **후** 다음을 **클릭합니다.**

> [!div class="nextstepaction"]
> [4단계 - 시간 후 흐름 호출 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[4단계 <br> 시간 후](#tab/after-hours)

각 자동 참석자에 대해 업무 시간을 설정할 수 있습니다. 업무 시간을 설정하지 않은 경우 24/7 일정이 기본적으로 설정되어 있기 때문에 해당 날의 모든 일 및 모든 시간은 업무 시간으로 간주됩니다. 업무 시간은 하루 중 시간의 시간으로 설정할 수 있으며, 근무 시간으로 설정되지 않은 모든 시간은 시간 후로 간주됩니다. 다른 수신 호출 처리 옵션과 인사말을 시간 후의 인사말로 설정할 수 있습니다.

자동 전화 걸기 및 통화 큐를 구성한 방법에 따라 직접 전화 번호가 있는 자동 전화 참석에 대한 시간 후 통화 라우팅만 지정하면 됩니다.

시간 후 발신자에 대해 별도의 통화 라우팅을 원하는 경우 각 날짜의 업무 시간을 지정합니다. 예를 **들어 새 시간 추가를** 클릭하여 특정 날짜에 대해 여러 시간 집합을 지정하여 점심 시간을 지정합니다.

![시간 후 및 시간 설정 스크린샷](../media/auto-attendant-business-hours.png)

업무 시간을 지정한 후 시간 후 통화 라우팅 옵션을 선택합니다. 3단계 - 호출 흐름에서 지정한 업무 시간 통화 라우팅과 동일한 **옵션을 사용할 수 있습니다.**

완료되면 **다음을** 클릭합니다.

> [!div class="nextstepaction"]
> [5단계 - 휴일 호출 흐름 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[5단계 <br> 공휴일](#tab/holidays)

휴일에 다른 날과 다르게 자동 전화 걸기 통화를 라우팅할 수 있습니다. (공휴일에 대해 다른 호출 흐름을 원하지 않는 경우 이 단계를 건너뛸 수 있습니다.)



자동 전화 걸기에는 설정한 각 휴일에 대한 통화 흐름이 설정될 수 있습니다. 각 자동 참석자에 최대 20회의 예정된 공휴일을 추가할 수 있습니다.

1. 휴일 통화 설정 페이지에서 추가를 **클릭합니다.**

2. 이 휴일 설정의 이름을 입력합니다.

3. 휴일 **드롭다운에서** 사용할 공휴일을 선택 합니다.

4. 사용할 인사말 유형을 선택 합니다.

    ![휴일 및 휴일 인사말 설정 스크린샷](../media/auto-attendant-holiday-greeting.png)

5. 통화 연결을 끊거나 **리디렉션할지** 선택 합니다. 

6. 리디렉션을 선택한 경우 통화에 대한 통화 라우팅 대상을 선택하세요.

    ![휴일 통화 작업 설정 스크린샷](../media/auto-attendant-holiday-actions.png)

7. **저장** 을 클릭합니다.

필요에 따라 추가 공휴일마다 절차를 반복합니다.

![공휴일이 나열된 휴일 설정 스크린샷](../media/auto-attendant-holiday-call-settings.png)

모든 공휴일을 추가한 경우 다음을 **클릭합니다.**

> [!div class="nextstepaction"]
> [6단계 - 디렉터리에 있는 사용자 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<br>6단계 디렉터리 멤버](#tab/dial-scope)

다이얼 *범위는* 발신자에서 전화 접속 이름 또는 다이얼로 확장을 사용할 때 디렉터리에서 사용할 수 있는 사용자를 정의합니다. 모든 온라인 사용자의 **기본값에는** 전화 시스템 라이선스가 있는 온라인 사용자인 조직의 모든 사용자가 포함됩니다.

포함 또는 제외에서 사용자 지정 사용자 그룹을  선택하고  하나 이상의 Microsoft 365 그룹, 메일 그룹 또는 보안 그룹을 선택하여 특정 사용자를 포함하거나 제외할 수 있습니다.  예를 들어 조직의 임원을 전화 걸기 디렉터리에서 제외할 수 있습니다. (사용자가 두 목록에 모두 있는 경우 디렉터리에서 제외됩니다.)

![다이얼 범위 포함 및 제외 옵션 스크린샷](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> 새 사용자가 디렉터리에 자신의 이름을 나열하는 데 최대 36시간이 걸릴 수 있습니다.

다이얼 범위 설정을 완료하면 다음을 **클릭합니다.**

> [!div class="nextstepaction"]
> [7단계 - 리소스 계정 할당 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[7단계 <br> 리소스 계정](#tab/resource-accounts)

모든 자동 참석자에는 연결된 리소스 계정이 있어야 합니다.  첫 번째 수준 자동 전화 회의에는 연결된 서비스 번호가 있는 하나 이상의 리소스 계정이 필요합니다. 원하는 경우 각각 별도의 서비스 번호가 있는 자동 전화 회의에 여러 리소스 계정을 할당할 수 있습니다.

리소스 계정을 추가하려면

1. 계정 **추가를** 클릭하고 추가할 계정을 검색합니다. **추가를** 클릭한 다음 추가를 **클릭합니다.**

    ![리소스 계정 계정 추가 패널의 스크린샷](../media/auto-attendant-add-resource-account.png)

2. 서비스 계정 추가를 마쳤을 때 제출을 **클릭합니다.**

    ![서비스 번호가 할당된 리소스 계정을 보여주는 리소스 계정 목록의 스크린샷](../media/auto-attendant-resource-account-assigned.png)

이렇게 하여 자동 attendant 구성이 완료됩니다.

---


