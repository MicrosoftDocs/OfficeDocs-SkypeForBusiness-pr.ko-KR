---
title: Microsoft Teams 패널 디바이스를 사용하는 방법
ms.author: v-mdhiman
author: ManikaDhiman
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 이 문서에서는 Teams 패널 디바이스를 사용하는 방법에 대한 지침을 제공합니다.
ms.openlocfilehash: eba450b42bb66dfbe202290cdd235a0d4db9e710
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395330"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Microsoft Teams 패널을 사용하는 방법

Microsoft Teams 패널은 모임 공간 바로 바깥에 탑재되는 소형 디지털 디스플레이 디바이스로, 일반적으로 입구 옆에 있습니다. 이러한 터치 스크린 패널은 모임 공간 및 예약된 모임에 대한 한눈에 보기를 제공하는 전용 Microsoft Teams 디바이스입니다. 선명한 색으로 코딩된 LED 및 홈 화면 표시기를 사용하여 거리에서 공간을 사용할 수 있는지 또는 예약할지 확인할 수 있습니다. Teams 패널을 사용하여 그 자리에서 애드워즈 모임에 사용할 수 있는 모임 공간을 예약할 수 있습니다.

Teams 패널 디바이스는 Microsoft Teams로 미리 설치하고 Outlook 또는 Teams 일정을 통해 예약된 모임 세부 정보를 표시합니다.

이 문서에서는 Teams 패널 디바이스를 사용하는 방법에 대한 최종 사용자와 관리자 모두에게 지침을 제공합니다. 또한 이러한 디바이스 사용에 대해 자주 묻는 질문에 [대한](#frequently-asked-questions) 답변도 제공합니다.

패널 디바이스에 대한 개요 및 조직에서 해당 디바이스를 계획, 배달 및 관리하는 방법에 대한 지침은 Microsoft Teams 패널 배포를 [참조하세요.](teams-panels.md)

빠른 시작은 Teams 패널 시작 [을 체크 아웃합니다.](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

## <a name="teams-panels-end-user-experience"></a>팀 패널 최종 사용자 환경

Teams [패널](#explore-teams-panels-home-screen) 디바이스의 홈 화면을 탐색하여 모임 공간 및 모임 세부 정보를 확인합니다. 또는 터치 스크린 패널에서 탭하고 스크롤하여 다른 작업을 수행할 수 있습니다.

Teams 패널 디바이스를 사용하여 다음을 합니다.

- [모임 공간 세부 정보 및 가용성, 모임 세부 정보, 예정된 예약 보기](#explore-teams-panels-home-screen)
- [사용 가능한 모임 공간 예약](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [문제 보고](#report-a-problem)
- [디바이스 설정 보기 또는 업데이트](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Teams 패널 홈 화면 탐색

홈 화면은 Teams 패널 디바이스의 기본 시각적 인터페이스입니다.  

홈 화면에서 위치 및 모임 세부 정보를 보고, 공간을 예약하고, 예정된 예약을 보고, 현재 가용성 상태를 확인할 수 있습니다.

다음 스크린샷은 Teams 패널 홈 화면에 서로 다른 부분 또는 타일을 보여줍니다.

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="이 스크린샷은 Teams 패널 홈 화면에 다른 영역을 표시합니다.":::

각 타일에 대한 설명은 다음 표를 참조하세요.

타일 | 설명
:---|:---
**1-현재 시간, 일, 날짜 및 모임 공간 세부 정보** | 현재 시간, 날짜, 날짜 및 모임 공간 이름을 표시됩니다. 모임 공간 이름은 패널에 로그인한 리소스 계정의 이름입니다.
**2-모임 공간 가용성 및 모임 세부 정보** | 모임 공간 가용성을 나타내고 모임 세부 정보를 표시합니다. 모임 [공간 가용성 및 모임 세부 정보 타일을 참조합니다.](#meeting-space-availability-and-meeting-details-tile)
**3-예정된 일정** | 현재 시간에서 최대 24시간 동안 모임 공간 일정 및 가용성을 표시합니다. 사용할 수 있는 시간 슬롯과 예약된 시간을 확인하려면 위로 또는 아래로 스크롤합니다.
**4-설정** | 설정 **아이콘을** 표시됩니다. 문제를 보고하거나 사용 가능한 디바이스 설정을 업데이트하려면 탭합니다.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>모임 공간 가용성 및 모임 세부 정보 타일

이 타일의 모양과 해당 기능은 모임 공간 가용성 및 예약 유형에 따라 다릅니다.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>모임 공간은 예약된 모임에 예약되어 있습니다.

타일은 예약된 모임에 예약된 모임 공간에 대해 자주색으로 표시됩니다(Outlook 또는 Teams를 통해 예약). 모임 제목을 두드러진 텍스트, 모임 시작 및 종료 시간 및 모임 이끌이의 이름으로 표시됩니다. Teams 모임의 경우 Teams 로고도 표시됩니다. 모임 세부 정보가 두드러진 경우 참석자들은 올바른 모임 공간, 올바른 시간 및 올바른 모임에 대해 쉽게 확인할 수 있습니다.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="모임 공간이 예약된 모임에 예약되어 있는 경우를 보여주는 Teams 패널 홈 화면":::

> [!NOTE]
>
> - 모임을 예약한 후 일정을 동기화하고 패널 화면에 반영하는 데 최대 90초가 걸릴 수 있습니다.
> - 비공개로 [](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)표시된 예약된 모임의  경우 실제 모임 제목 대신 비공개 모임이 표시됩니다.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>모임 공간은 비정기 모임에 예약되어 있습니다.

이 타일은 모임 공간에 대해 자주색으로 [표시됩니다.](#reserve-meeting-spaces-for-ad-hoc-meetings) 두드러진 텍스트로 **예약을** 표시하고 모임 시작 및 종료 시간을 표시합니다. 패널에서 (Outlook 또는 Teams 일정 대신) 모임을 예약하는 경우 실제로 해당 모임 공간의 일정을 예약합니다. 이러한 모임은 Teams 모임으로 자동으로 예약되며, 따라서 Teams 로고는 항상 화면에 표시됩니다.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="모임 공간이 Ad Hoc 모임에 예약되어 있는 경우를 보여주는 Teams 패널 홈 화면":::

#### <a name="meeting-space-is-available"></a>모임 공간을 사용할 수 있습니다.

타일이 사용 가능한 모임 공간에 대해 녹색으로 표시됩니다. 두드러진 텍스트로 사용 가능이 표시되어 있으며, 예약 단추를 탭하여 모임 공간을 예약할 [수](#reserve-meeting-spaces-for-ad-hoc-meetings)있습니다.   모임 공간의 예정된 일정(오른쪽 아래 타일)을 확인하여 모임의 종료 시간을 결정할 수 있습니다.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="이 스크린샷은 모임 공간을 사용할 수 있는 경우 Teams 패널 홈 화면이 나타나는 방법을 보여줍니다.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>비정기 모임을 위한 모임 공간 예약

추가 모임을 [](#meeting-space-is-available) 위해 패널에서 직접 사용 가능한 모임 공간을 예약할 수 있습니다. 모든 ad hoc 모임은 Teams 모임으로 자동으로 예약됩니다. 그러나 예약된 경우 패널을 통해 해당 모임 공간을 릴리스하거나 예약할 수 없습니다. 디바이스의 리소스 계정 관리자만(Outlook 또는 Teams 일정을 통해) 모임을 취소하여 공간을 예약할 수 있습니다.

패널에서 직접 예약된 추가 모임의 경우:

- 시작 시간은 항상 현재 시간으로 향후 시간으로 예약할 수 없습니다.
- 종료 시간은 다음 예약된 모임까지 또는 현재 시간에서 최대 24시간까지 될 수 있습니다. 홈 **화면에서** 예정된 일정 타일을 확인하여 모임 공간을 사용할 수 또는 예약하는 시간 슬롯을 확인할 수 있습니다.

추가 모임에 사용할 수 있는 모임 공간을 예약하는 경우:

1. 홈 화면에서 예약 **단추를 탭합니다.**
    :::image type="content" source="../media/panels-reserve.png" alt-text="예약 단추를 보여주는 팀 패널 홈 화면":::
2. Ad **Hoc 모임** 화면에서 사용 가능한 종료 시간 선택을 검토합니다. 오른쪽 또는 왼쪽 화살표를 사용하여 사용 가능한 종료 시간 선택을 찾아볼 수 있습니다.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="종료 시간 슬롯을 표시하는 모임 화면":::

    > [!Note]
    >
    > - 종료 시간 선택은 1시간의 15분 간격으로 표시됩니다.
    > - 종료 시간은 현재 시간 이후 5분 이상인 다음 15분 간격으로 기본값을 지정합니다. 예를 들어 현재 시간이 오후 1:57인 경우 기본 종료 시간은 오후 2시 15분이 아니라 오후 2시 15분으로 표시됩니다. 이렇게 하면 사용자가 5분 이하로 공간을 예약할 수 없습니다. 위의 스크린샷에서 기본 종료 시간은 2:00 PM으로 표시되어 현재 시간(오후 1:53) 이후 5분 이상인 다음 15분 간격입니다.
    > - 위의 규칙에 대한 예외는 다음 모임의 시작 시간이 현재 시간에서 5분 이내인 경우입니다. 이러한 경우 다음 모임 시작 시간까지 공간을 예약할 수 있습니다. 예를 들어 현재 시간이 오후 1:57이고 다음 모임 시작 시간이 오후 2:00인 경우 오후 2:00이 유일한 종료 시간 옵션으로 표시되어 3분 동안 공간을 예약할 수 있습니다.

3. 원하는 종료 시간 간격을 탭한 다음 예약을 **탭합니다.**

    확인 창에는 엄지 손가락으로 이모티콘, 모임 시작 및 종료 시간 및 모임 공간 이름이 표시됩니다.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="모임 확인 메시지":::
이제 홈 화면의 오른쪽 타일이 자주색으로 표시되어 예약된 **텍스트와** Teams 로고가 표시됩니다. 이제 모임 공간이 Ad Hoc Teams 모임에 예약되어 있습니다.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="모임 공간이 Ad Hoc 모임에 예약되어 있는 경우를 보여주는 홈 화면":::

    > [!NOTE]
    > 모임 공간이 Microsoft Teams Room인 경우  이 Teams 모임에 회의실 내 Microsoft Teams Room 또는 Surface Hub 디바이스에 참가할 수 있습니다.

### <a name="report-a-problem"></a>문제 보고

디바이스 또는 모임 공간에 대한 문제를 보고하거나, 기능 업데이트를 요청하거나 피드백을  제공하려면 홈 화면의 설정 아이콘을 사용합니다.

1. 홈 **화면에서 설정** 기어 아이콘을 탭합니다.

2. 문제 **보고 옵션을 탭합니다.**

    피드백 **보내기** 화면이 양식 형식으로 표시됩니다.
3. 형식 **드롭다운에서** 요청 유형을 선택합니다.
4. 문제 **드롭다운에서** 범주를 선택합니다.
5. 제목 **텍스트** 필드에 패널 키패드를 사용하여 타이틀을 입력합니다.
6. 제목 아래 텍스트 **필드에** 필요한 경우 추가 세부 정보를 입력합니다.

    > [!NOTE]
    > 개인 식별 가능한 정보는 포함하지 않습니다.

7. 항목을 검토하고 보내기 를 **탭합니다.**

### <a name="view-or-update-a-device-setting"></a>디바이스 설정 보기 또는 업데이트

패널에서 직접 보거나 업데이트할 수 있는 정보, 접근성, 재부팅, 개인 정보 보호 정책과 같은 여러 디바이스 설정이 있습니다. 사용 가능한 디바이스 설정은 장치의 OEM(원래 장비 제조업체)에 따라 다를 수 있습니다. 디바이스에 대한 설정에 대한 자세한 내용은 OEM 설명서를 참조하세요.

디바이스 설정을 보거나 업데이트하려면:

1. 홈 **화면에서 설정** 아이콘을 탭합니다.
2. 설정 **화면에서** **디바이스 설정을 탭합니다.**
3. 디바이스 설정 **화면에서** 보거나 업데이트할 설정을 탭합니다.
4. 화면의 프롬프트에 따라 설정을 보거나 업데이트합니다.

## <a name="teams-panels-admin-experience"></a>Teams 패널 관리자 환경

Teams 패널의 리소스 [](teams-panels.md\#resource-account-provisioning)계정 관리자인 경우 디바이스의 패널 앱 **관리자도** 됩니다. 패널 **앱** 관리자로, 디바이스의 패널 앱 설정을 관리하는 것 [](#teams-panels-end-user-experience) 외에도 최종 사용자 환경 섹션에  언급된 모든 함수를 할 수 있습니다.

패널 디바이스는 두 가지 유형의 관리자 설정을 제공합니다. 사용 가능한 관리자 설정에 액세스하려면 디바이스 관리자가 되어야 합니다. 최종 사용자는 이러한 설정에 액세스할 수 없습니다.

- 디바이스에 특정되는 관리자 설정(예: 표시, 시간 및 날짜, 언어, Bluetooth, WiFi 등)입니다. 이러한 설정에 대한 자세한 내용은 OEM 설명서를 참조하세요.
- 배경 화면 및 LED 표시기 색과 같은 디바이스의 **패널** 앱에 특정되는 관리자 설정입니다. 패널 앱의 **관리자만** 이러한 설정에 액세스할 수 있습니다. **패널 앱 설정을** 관리자 설정의 일부로 사용할 수 있습니다. 패널 앱 설정에 액세스하려면 디바이스 및 패널 앱 모두에 대한 관리자 로그인 자격 **증명이 있어야** 합니다. 

> [!NOTE]
> 디바이스를 통해 수행된 **패널** 앱 설정에 대한 모든 업데이트는 해당 특정 디바이스에만 적용할 수 있습니다. 이러한 업데이트는 조직의 다른 패널 디바이스에 영향을주지 않습니다. 예를 들어 패널 앱 설정에서 홈  화면 배경 화면 이미지를 변경하면 배경 화면 이미지는 해당 특정 디바이스에 대해만 변경됩니다.

### <a name="access-panels-app-settings"></a>액세스 패널 앱 설정

관리자 **설정에서** 패널 앱 설정 옵션을 사용하여 **패널** 앱 -특정 설정에 액세스할 수 있습니다. 패널 앱 **설정에** 액세스하는 단계는 디바이스의 OEM에 따라 다를 수 있습니다.

패널 앱 설정 **옵션에 액세스하려면** 다음을 실행합니다.

1. 홈 **화면에서 설정** 아이콘을 탭합니다.
2. 설정 **화면에서** **디바이스 설정을 탭합니다.**
3. 관리자 **설정을 탭합니다.**

    > [!NOTE]
    > 디바이스의 OEM에 따라 지금 또는 다음 단계 후에 디바이스 관리자 암호를 입력해야 할 수 있습니다.

4. 아래로 스크롤하여 패널 앱 **설정 옵션을 찾습니다.** 탭합니다.
5. 오른쪽 **화면에서 패널 앱 설정** 단추를 탭합니다.
    사용 가능한 패널 앱 설정이 **있는 화면이** 표시됩니다.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="이 스크린샷에는 사용 가능한 패널 앱 설정이 있는 화면이 표시됩니다.":::

    이 화면을 사용하여 디바이스에 대한 **다음 패널 앱 설정을** 업데이트합니다.

    - [배경 화면](#update-the-wallpaper)
    - [LED 표시기](#change-the-busy-state-led-color)

#### <a name="update-the-wallpaper"></a>배경 화면 업데이트

홈 화면 배경 화면 이미지를 변경합니다.

1. [액세스 **패널 앱 설정 입니다.**](#access-panels-app-settings)
2. 배경 **화면을 탭합니다.**
3. 이미지 **선택에서** 홈 화면 배경 이미지로 설정할 이미지를 선택합니다. 배경 에서 선택한 이미지를 **미리 니다.**
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="이 스크린샷에는 배경 화면 설정 화면이 표시됩니다.":::
4. 홈 화면으로 돌아가서 배경 화면이 업데이트되어 있는지 확인합니다.

#### <a name="change-the-busy-state-led-color"></a>사용 중 상태 LED 색 변경

관리자는 모임 공간이 사용 중 또는 예약되어 있는 것을 나타내기 위해 LED 색으로 빨간색 또는 보라색을 선택할 수 있습니다. 사용 가능한 공간을 나타내는 LED 색은 항상 녹색이기 때문에 변경할 수 없습니다.

1. [액세스 **패널 앱 설정 입니다.**](#access-panels-app-settings)
2. **LED 설정을 탭합니다.**
3. LED **색 선택에서** 원하는 색을 선택합니다.
:::image type="content" source="../media/panels-led-settings.png" alt-text="이 스크린샷에는 LED 색 사용 중 상태 설정이 표시됩니다.":::
4. 홈 화면으로 돌아가 사용 중 상태의 LED 색이 업데이트되어 있는지 확인합니다. 모임 공간을 현재 사용할 수 있는 경우 테스트 모임을 예약하여 사용 중인 상태의 LED 색 변경을 확인하려고 합니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

Teams 패널 디바이스에 대해 자주 묻는 질문에 대한 답변을 찾을 수 있습니다.

**앞으로 모임 공간의 계획 세부 정보를 얼마나 볼 수 있나요?**  
홈 **화면의** 예정 일정 타일(오른쪽 아래)에서 현재 시간에서 향후 최대 24시간 동안 모임 공간의 일정 세부 정보를 볼 수 있습니다.

**Teams 패널 장치에서 향후 모임 공간을 예약할 수 있나요?**  
아니요, 패널에서 향후 모임 공간을 예약할 수 없습니다. 시작 시간은 항상 패널에서 예약된 모임의 현재 시간입니다.

**추가 모임을 위해 사용 가능한 모임 공간을 예약할 수 있는 기간은 얼마나 하나요?**  
현재 시간부터 다음 예정된 모임 시간까지 또는 현재 시간에서 최대 24시간까지 사용할 수 있는 모임 공간을 예약할 수 있습니다. 예를 들어 현재 시간이 오전 10시이고 다음 모임 시작 시간이 오후 2시인 경우 오전 10시부터 오후 2시까지 모임 공간을 예약할 수 있습니다.