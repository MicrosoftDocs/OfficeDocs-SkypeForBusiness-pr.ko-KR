---
title: Microsoft Teams 패널 디바이스를 사용하는 방법
ms.author: dstrome
author: dstrome
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
ms.localizationpriority: medium
description: 이 문서에서는 Teams 패널 디바이스를 사용하는 방법에 대한 지침을 제공합니다.
ms.openlocfilehash: 00d2657179e35e2a5e43cbc0665a6d1533ec70d1
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760910"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Microsoft Teams 패널을 사용하는 방법

Microsoft Teams 패널은 일반적으로 입구 옆에 있는 모임 공간 바로 바깥쪽에 탑재된 소형 디지털 디스플레이 장치입니다. 이러한 터치 스크린 패널은 모임 공간 및 예약된 모임에 대한 한눈에 볼 수 있는 전용 Microsoft Teams 장치입니다. 선명한 색으로 구분된 LED 및 홈 화면 표시기를 사용하여 공간을 원거리에서 사용할 수 있는지 또는 예약되었는지 확인할 수 있습니다. Teams 패널을 사용하여 임시 모임에 사용할 수 있는 모임 공간을 예약할 수 있습니다.

Teams 패널 디바이스는 Microsoft Teams 미리 설치되며 Outlook 또는 Teams 일정을 통해 예약된 모임 세부 정보를 표시합니다.

이 문서에서는 최종 사용자와 관리자 모두에게 Teams 패널 디바이스를 사용하는 방법에 대한 지침을 제공합니다. 또한 이러한 디바이스 사용에 대한 질문과 [대답](#frequently-asked-questions) 을 제공합니다.

패널 디바이스의 개요 및 조직에서 이를 계획, 제공 및 관리하는 방법에 대한 지침은 [Microsoft Teams 배포 패널을 참조하세요](teams-panels.md).

빠른 시작을 위해 [Teams 패널로 시작 확인하세요](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Teams 패널 최종 사용자 환경

Teams 패널 장치의 [홈 화면을](#explore-teams-panels-home-screen) 탐색하여 모임 공간 및 모임 세부 정보를 봅니다. 또는 터치 스크린 패널을 탭하고 스크롤하여 다른 작업을 수행합니다.

Teams 패널 디바이스를 사용하여 다음을 수행합니다.

- [모임 공간 세부 정보 및 가용성, 모임 세부 정보, 예정된 예약 보기](#explore-teams-panels-home-screen)
- [사용 가능한 모임 공간 예약](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [문제 보고](#report-a-problem)
- [디바이스 설정 보기 또는 업데이트](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Teams 패널 홈 화면 탐색

홈 화면은 Teams 패널 디바이스의 기본 시각적 인터페이스입니다.  

홈 화면에서 위치 및 모임 세부 정보를 보고, 공간을 예약하고, 예정된 예약을 보고, 현재 가용성 상태를 식별할 수 있습니다.

다음 스크린샷은 Teams 패널 홈 화면의 여러 파트 또는 타일을 보여 줍니다.

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="이 스크린샷은 Teams 패널 홈 화면에 여러 영역을 표시합니다.":::

각 타일에 대한 설명은 다음 표를 참조하세요.

타일 | 설명
:---|:---
**1-현재 시간, 일, 날짜 및 모임 공간 세부 정보** | 현재 시간, 일, 날짜 및 모임 공간 이름을 표시합니다. 모임 공간 이름은 패널에 로그인한 리소스 계정의 이름입니다.
**2-모임 공간 가용성 및 모임 세부 정보** | 모임 공간 가용성을 나타내고 모임 세부 정보를 표시합니다. [모임 공간 가용성 및 모임 세부 정보 타일](#meeting-space-availability-and-meeting-details-tile)을 참조하세요.
**3-예정된 일정** | 현재 시간에서 최대 24시간 동안의 모임 공간 일정 및 가용성을 표시합니다. 위쪽 또는 아래로 스크롤하여 사용 가능한 시간 슬롯과 예약된 시간 슬롯을 확인합니다.
**4-설정** | **설정** 아이콘을 표시합니다. 탭하여 문제를 보고하거나 사용 가능한 디바이스 설정을 업데이트합니다.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>모임 공간 가용성 및 모임 세부 정보 타일

이 타일의 모양과 해당 기능은 모임 공간 가용성 및 예약 유형에 따라 달라집니다.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>예약된 모임을 위해 예약된 모임 공간

타일은 예약된 모임(Outlook 또는 Teams 통해 예약된) 모임 공간에 대해 자주색으로 표시됩니다. 모임 제목을 눈에 띄는 텍스트, 모임 시작 및 종료 시간 및 모임 이끌이의 이름으로 표시합니다. Teams 모임의 경우 Teams 로고도 표시됩니다. 모임 세부 정보가 눈에 띄게 표시되면 참석자가 적절한 모임 공간, 적절한 시간에 적절한 모임에 있는지 쉽게 확인할 수 있습니다.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams 패널 홈 화면에서 모임 공간이 예약된 모임에 예약되어 있음을 보여 줍니다.":::

> [!NOTE]
>
> - 모임을 예약한 후 일정이 동기화되어 패널 화면에 반영되는 데 최대 90초가 걸릴 수 있습니다.
> - [비공개로 표시된 예약된 모임의](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d) 경우 실제 모임 제목 대신 **비공개 모임** 이 표시됩니다.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>임시 모임을 위해 예약된 모임 공간

임시 [모임을 위해 예약된](#reserve-meeting-spaces-for-ad-hoc-meetings) 모임 공간에 대해 타일이 자주색으로 표시됩니다. 모임 시작 및 종료 시간과 함께 **예약된** 내용을 눈에 띄는 텍스트로 표시합니다. 임시 모임은 Teams 모임으로 자동으로 예약되므로 Teams 로고가 항상 화면에 표시됩니다.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams 패널 홈 화면은 임시 모임을 위해 모임 공간이 예약되어 있음을 보여 줍니다.":::

#### <a name="meeting-space-is-available"></a>모임 공간 사용 가능

타일은 사용 가능한 모임 공간에 대해 녹색으로 표시됩니다. 눈에 띄는 텍스트로 **사용 가능** 을 표시하고 임시 [모임을 위해 모임 공간을 예약하기 위해](#reserve-meeting-spaces-for-ad-hoc-meetings) 탭할 수 있는 **예약** 단추도 나타납니다. 예정된 모임 공간 일정(오른쪽 아래 타일)을 확인하여 임시 모임의 종료 시간을 결정할 수 있습니다.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="이 스크린샷은 모임 공간을 사용할 수 있을 때 Teams 패널 홈 화면이 표시되는 방식을 보여 줍니다.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>임시 모임을 위한 모임 공간 예약

임시 모임을 위해 패널에서 직접 [사용 가능한 모임 공간을](#meeting-space-is-available) 예약할 수 있습니다. 모든 임시 모임은 자동으로 Teams 모임으로 예약됩니다. 그러나 예약된 후에는 패널을 통해 해당 모임 공간을 해제하거나 예약할 수 없습니다. 디바이스의 리소스 계정 관리자만 임시 모임(Outlook 또는 Teams 일정을 통해)을 취소하여 공간을 예약하지 않을 수 있습니다.

패널에서 직접 예약한 임시 모임의 경우:

- 시작 시간은 항상 현재 시간이므로 나중에 예약할 수 없습니다.
- 종료 시간은 다음 예약된 모임까지 또는 현재 시간에서 최대 24시간(이전 시간)까지일 수 있습니다. 홈 화면에서 **예정된 일정 타일을** 확인하여 모임 공간을 사용할 수 있거나 예약하는 시간 슬롯을 확인합니다.

임시 모임에 사용 가능한 모임 공간을 예약하려면 다음을 수행합니다.

1. 홈 화면에서 **예약** 단추를 탭합니다.
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams 패널 홈 화면에 예약 단추가 표시됩니다.":::
2. **임시 모임** 화면에서 사용 가능한 종료 시간 선택을 검토합니다. 오른쪽 또는 왼쪽 화살표를 사용하여 사용 가능한 종료 시간 선택을 찾아볼 수 있습니다.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="종료 시간 슬롯을 보여 주는 임시 모임 화면입니다.":::

    > [!Note]
    >
    > - 종료 시간 선택은 1시간의 15분 간격으로 표시됩니다.
    > - 종료 시간은 현재 시간 이후 최소 5분인 다음 15분 간격으로 기본 설정됩니다. 예를 들어 현재 시간이 오후 1시 57분인 경우 기본 종료 시간은 오후 2시가 아닌 오후 2시 15분으로 표시됩니다. 이렇게 하면 사용자가 5분 이하의 공간을 예약할 수 없습니다. 위의 스크린샷에서 기본 종료 시간은 현재 시간(오후 1시 53분) 이후 5분 이상인 다음 15분 간격인 오후 2:00로 표시됩니다.
    > - 위의 규칙에 대한 예외는 다음 모임의 시작 시간이 현재 시간으로부터 5분 이내인 경우입니다. 이러한 경우 다음 모임 시작 시간까지 공간을 예약할 수 있습니다. 예를 들어 현재 시간이 오후 1시 57분이고 다음 모임 시작 시간이 오후 2시인 경우 오후 2:00이 유일한 종료 시간 옵션으로 표시되고 3분 동안 공간을 예약할 수 있습니다.

3. 원하는 종료 시간 간격을 탭한 다음 **예약** 을 탭합니다.

    확인 창에는 엄지 손가락으로 이모지, 모임 시작 및 종료 시간, 모임 공간 이름이 표시됩니다.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="임시 모임 확인 메시지입니다.":::
이제 홈 화면의 오른쪽 타일이 자주색으로 표시되고 **예약** 텍스트와 Teams 로고가 표시됩니다. 이는 이제 임시 Teams 모임을 위해 모임 공간이 예약되었음을 나타냅니다.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="임시 모임을 위해 모임 공간이 예약되어 있음을 보여 주는 홈 화면입니다.":::

    > [!NOTE]
    > 모임 공간이 Microsoft Teams 회의실인 경우 이 Teams 모임에 회의실 Microsoft Teams 또는 Surface Hub 장치와 _참가_ 할 수 있습니다.

### <a name="report-a-problem"></a>문제 보고

장치 또는 모임 공간에 문제를 보고하거나, 기능 업데이트를 요청하거나, 피드백을 제공하려면 홈 화면의 **설정** 아이콘을 사용합니다.

1. 홈 화면에서 **설정** 기어 아이콘을 탭합니다.

2. **문제 보고** 옵션을 탭합니다.

    **피드백 보내기** 화면이 양식 형식으로 표시됩니다.
3. **형식** 드롭다운에서 요청 유형을 선택합니다.
4. **문제** 드롭다운에서 범주를 선택합니다.
5. **제목** 텍스트 필드에 패널 키패드를 사용하여 제목을 입력합니다.
6. **제목** 아래 텍스트 필드에 필요한 경우 추가 세부 정보를 입력합니다.

    > [!NOTE]
    > 개인 식별 가능한 정보는 포함하지 마세요.

7. 항목을 검토하고 **보내기** 를 탭합니다.

### <a name="view-or-update-a-device-setting"></a>디바이스 설정 보기 또는 업데이트

패널에서 직접 보거나 업데이트할 수 있는 정보, 접근성, 다시 부팅 및 개인 정보 취급 방침과 같은 여러 디바이스 설정이 있습니다. 사용 가능한 디바이스 설정은 디바이스의 OEM(원본 장비 제조업체)에 따라 다를 수 있습니다. 디바이스 관련 설정에 대한 자세한 내용은 OEM 설명서를 참조하세요.

디바이스 설정을 보거나 업데이트하려면 다음을 수행합니다.

1. 홈 화면에서 **설정** 아이콘을 탭합니다.
2. **설정** 화면에서 **디바이스 설정을 탭합니다**.
3. **디바이스 설정** 화면에서 보거나 업데이트하려는 설정을 탭합니다.
4. 화면의 프롬프트에 따라 설정을 보거나 업데이트합니다.

## <a name="teams-panels-admin-experience"></a>Teams 패널 관리자 환경

[Teams 패널 리소스 계정의](teams-panels.md\#resource-account-provisioning) 관리자인 경우 디바이스의 **Panels 앱** 관리자이기도 합니다. **Panels 앱** 관리자는 디바이스에서 **Panels 앱** 설정을 관리하는 것 외에도 [최종 사용자 환경](#teams-panels-end-user-experience) 섹션에 언급된 모든 기능을 수행할 수 있습니다.

패널 디바이스는 두 가지 유형의 관리자 설정을 제공합니다. 사용 가능한 관리자 설정에 액세스하려면 디바이스 관리자여야 합니다. 최종 사용자는 이러한 설정에 액세스할 수 없습니다.

- 디스플레이, 시간 및 날짜, 언어, bluetooth, WiFi 등과 같은 장치에 특정한 설정을 관리. 이러한 설정에 대한 자세한 내용은 OEM 설명서를 참조하세요.
- 배경 화면 및 LED 표시기 색과 같은 디바이스 **의 패널 앱** 과 관련된 설정을 관리. **Panels 앱** 의 관리자만 이러한 설정에 액세스할 수 있습니다. **Panels 앱** 설정은 관리자 설정의 일부로 사용할 수 있으므로 **Panels 앱** 설정에 액세스하려면 디바이스 및 **패널 앱** 모두에 대한 관리자 로그인 자격 증명이 있어야 합니다.

> [!NOTE]
> 디바이스를 통해 수행된 **Panels 앱** 설정에 대한 모든 업데이트는 해당 특정 디바이스에만 적용됩니다. 이러한 업데이트는 조직의 다른 패널 디바이스에 영향을 주지 않습니다. 예를 들어 **패널 앱** 설정에서 홈 화면 배경 화면 이미지를 변경하는 경우 배경 화면 이미지는 해당 특정 디바이스에 대해서만 변경됩니다.

### <a name="access-panels-app-settings"></a>액세스 패널 앱 설정

관리자 설정에서 **Panels 앱** 설정 옵션을 사용하여 **패널 앱** 별 설정에 액세스할 수 있습니다. **Panels 앱 설정** 액세스하는 단계는 디바이스의 OEM에 따라 다를 수 있습니다.

**Panels 앱 설정** 옵션에 액세스하려면 다음을 수행합니다.

1. 홈 화면에서 **설정** 아이콘을 탭합니다.
2. **설정** 화면에서 **디바이스 설정을 탭합니다**.
3. **관리 설정** 탭합니다.

    > [!NOTE]
    > 디바이스의 OEM에 따라 지금 또는 다음 단계 후에 디바이스 관리자 암호를 입력해야 할 수 있습니다.

4. 아래로 스크롤하여 **패널 앱 설정** 옵션을 찾습니다. 탭합니다.
5. 오른쪽 화면에서 **패널 앱 설정** 단추를 탭합니다.
    사용 가능한 **패널 앱 설정이** 있는 화면이 표시됩니다.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="이 스크린샷은 사용 가능한 패널 앱 설정이 있는 화면을 표시합니다.":::

    이 화면을 사용하여 디바이스에 대한 다음 **Panels 앱** 설정을 업데이트합니다.

    - [벽지](#update-the-wallpaper)
    - [LED 표시기](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Android Microsoft Teams 룸과 Teams 패널 페어링

Android Teams 패널 및 Teams Room을 페어링하려면 두 디바이스를 모두 동일한 리소스 계정에 로그인해야 합니다.

Teams 패널 관리자 자격 증명을 사용하여 로그인합니다.

1. **설정 > 디바이스 설정 > 관리 설정 > 패널 앱 설정 > 모임 > 디바이스 페어링으로 이동합니다.**

2. Teams 룸 Android 전면에 6자리 코드가 표시됩니다. Teams 패널에 코드를 입력합니다.  

#### <a name="meeting-check-in-and-room-release"></a>모임 체크인 및 회의실 릴리스

체크 인 및 회의실 릴리스 설정을 사용하면 사용자가 모임 시작 시 예약한 회의실의 Teams 패널에서 모임에 체크 인할 수 있습니다. 사용자가 모임 시작 시간 이후에 설정된 시간 내에 체크 인하지 않으면 회의실이 해제되고 다른 사용자가 예약할 수 있게 됩니다.

Teams 패널이 Android Microsoft Teams 회의실과 페어링되면 모임이 늦게 실행될 때 회의실 전면 디스플레이에 체크 인 알림을 표시하도록 설정할 수 있습니다.

체크 인 및 객실 릴리스를 사용하도록 설정하려면 [Microsoft Teams 패널에서 체크인 및 객실 릴리스를 참조하세요](check-in-and-room-release.md).

#### <a name="room-capacity-warning"></a>회의실 용량 경고

Android Teams 회의실과 쌍을 이루는 Teams 패널은 회의실이 용량을 초과하거나 초과할 때 경고 메시지를 표시할 수 있습니다. 이 기능을 사용하려면 Teams 룸에는 사람들이 계산할 수 있도록 지원하는 카메라가 있어야 합니다. Teams 패널 없이 Android 지원실 용량 경고에 대한 Teams 룸.

객실 용량 경고는 기본적으로 꺼져 있습니다. Teams 패널 설정을 켜려면 먼저 [Teams 패널 Android Microsoft Teams Room과 페어링](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android)합니다. 패널과 Teams 룸은 동일한 리소스 계정에 로그인해야 합니다.

 그런 다음, **설정 > 디바이스 설정 > 관리 설정 > 패널 앱 설정** 으로 이동합니다. 그런 다음 **모임** 에서 **최대 회의실 점유율 알림을** 켭니다.

#### <a name="view-room-equipment"></a>회의실 장비 보기

이 기능이 켜지면 최종 사용자는 Teams 패널 공간에서 사용할 수 있는 장비를 볼 수 있습니다.

이 기능은 기본적으로 꺼져 있으며 디바이스별로 사용하도록 설정할 수 있습니다. 이 기능을 켜려면 PowerShell에서 [Set-Place](/powershell/module/exchange/set-place?view=exchange-ps)를 사용하여 , `DisplayDeviceName`, `VideoDeviceName``Tags`및 `IsWheelChairAccessible`에 대한 `AudioDeviceName`표시 이름을 구성합니다.

또는 Exchange 관리 센터에서 이 기능을 사용하도록 설정할 수 있습니다. 자세한 내용은 [리소스 편집](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) 을 참조하세요.



#### <a name="update-the-wallpaper"></a>배경 화면 업데이트

홈 화면 배경 화면 이미지를 변경합니다.

1. [액세스 **패널 앱 설정**](#access-panels-app-settings).
2. **배경 화면을 탭합니다**.
3. **이미지 선택** 에서 홈 화면 배경 이미지로 설정할 이미지를 선택합니다. 배경 아래에서 선택한 이미지를 미리 봅니 **다**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="이 스크린샷은 배경 화면 설정 화면을 표시합니다.":::
4. 홈 화면으로 돌아가기 배경 화면이 업데이트되었는지 확인합니다.

#### <a name="change-the-busy-state-led-color"></a>사용 중인 상태 LED 색 변경

관리자는 모임 공간이 사용 중이거나 예약되어 있음을 나타내기 위해 빨간색 또는 자주색을 LED 색으로 선택할 수 있습니다. 사용 가능한 공간을 나타내는 LED 색은 항상 녹색이며 변경할 수 없습니다.

1. [액세스 **패널 앱 설정**](#access-panels-app-settings).
2. **LED 설정** 탭합니다.
3. **LED 색 선택** 에서 원하는 색을 선택합니다.
:::image type="content" source="../media/panels-led-settings.png" alt-text="이 스크린샷은 LED 색 사용 중 상태 설정을 표시합니다.":::
4. 홈 화면으로 돌아가기 사용 중인 상태의 LED 색이 업데이트되었는지 확인합니다. 모임 공간을 현재 사용할 수 있는 경우 테스트 모임을 예약하여 사용 중인 상태의 LED 색 변경을 확인합니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

Teams 패널 디바이스에 대한 질문과 대답을 찾습니다.

**앞으로 모임 공간의 일정 세부 정보를 얼마나 볼 수 있나요?**  
홈 화면의 **예정된 일정** 타일(오른쪽 아래)에서 현재 시간부터 최대 24시간 동안 모임 공간의 일정 세부 정보를 볼 수 있습니다.

**Teams 패널 장치에서 나중에 모임 공간을 예약할 수 있나요?**  
아니요, 향후 패널에서 모임 공간을 예약할 수 없습니다. 시작 시간은 항상 패널에서 예약된 임시 모임의 현재 시간입니다.

**임시 모임을 위해 사용 가능한 모임 공간을 얼마나 예약할 수 있나요?**  
현재 시간부터 다음 예약된 모임 시간까지 사용 가능한 모임 공간을 예약하거나 현재 시간에서 최대 24시간(이전 시간)까지 예약할 수 있습니다. 예를 들어 현재 시간이 오전 10시이고 다음 모임 시작 시간이 오후 2시인 경우 오전 10시부터 오후 2시까지 모임 공간을 예약할 수 있습니다.
