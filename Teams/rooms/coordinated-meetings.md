---
title: Microsoft Teams Rooms 및 Surface Hub를 통해 조정된 모임 설정
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 한 디바이스 또는 다른 디바이스가 모임에 참가할 때 모임에 참가하도록 Teams Rooms 디바이스 및 Surface Hub를 구성합니다.
ms.openlocfilehash: 57dc91e4a7d923e218cd1f8f6f0ce22679d550e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117566"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams Rooms 및 Surface Hub를 통해 조정된 모임 설정

회의실에 하나 이상의 Microsoft Teams Rooms 디바이스 또는 Surface Hubs가 있는 경우 조정된 모임을 설정할 수 있습니다. 조정된 모임을 사용하면 Teams Room 디바이스 및 Surface Hubs를 설정할 수 있으므로 한 디바이스에서 모임에 참가할 때 회의실의 다른 디바이스도 동일한 모임에 참가할 수 있습니다. 카메라, 스피커 및 마이크를 구성하여 참가자에게 최상의 환경을 제공한 사용자가 비활성화된 동안 사용하도록 설정할 수 있습니다. 이렇게 하여 모임에 여러 디바이스를 추가할 때 참가자가 경험할 수 있는 두려우는 에코 및 피드백 소음을 방지합니다.

조정된 모임을 설정하려면 Teams Rooms 디바이스 및 Surface Hubs가 모임에 참여하도록 이미 올바르게 구성되어 있는지 확인해야 합니다. 가장 중요한 점은 각 디바이스에 자체 Exchange room 사서함이 필요합니다. 설정 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Microsoft Teams 룸 배포](../rooms/rooms-deploy.md)
- [Surface Hub 2S 디바이스 계정 만들기](/surface-hub/surface-hub-2s-account)

Teams Rooms 디바이스 및 Surface Hubs에서 자동으로 모임을 수락하고 성공적으로 참가할 수 있는 것을 확인한 후 조정된 모임을 설정할 수 있습니다.

각 회의실에 대해 다음 단계를 별도로 완료해야 합니다. 한 회의실의 디바이스는 다른 회의실의 디바이스와 조정된 모임에 대해 설정되어선 안 됩니다.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>1단계: 조정된 모임 환경 계획

구성을 변경하기 전에 각 회의실에서 어떤 장치를 사용할지 결정해야 합니다. 즉, 특정 회의실의 경우 활성 마이크, 카메라 및 화이트보드를 사용할 디바이스를 결정해야 합니다. 디바이스를 구성하는 방법은 특정 환경에 따라 달라지지만 시작하는 몇 가지 일반적인 권장 사항은 다음과 같습니다.

- **마이크** Teams Rooms 디바이스
- **카메라** Teams Rooms 디바이스(기본적으로 설정) 및 Surface Hub(기본적으로 꺼져 있지만 참가자가 설정하도록 허용)
- **화이트보드** Surface Hub

> [!IMPORTANT]
> 마이크를 한 디바이스에서만 사용하도록 설정해야 합니다. 두 개 이상의 장치에서 사용하도록 설정하면 오디오 에코 및 피드백이 표시됩니다.

## <a name="step-2-get-your-devices-upns"></a>2단계: 디바이스의 UPNS를 얻음

회의실에서 조정된 모임 환경을 설정할 때 해당 회의실의 Teams Rooms 디바이스 및 Surface Hubs에 조정할 디바이스를 알려야 합니다. 이는 구성에 조정해야 하는 디바이스의 UPN(사용자 주체 이름)을 추가하여 수행됩니다. 조정된 모임에 대해 설정하려는 각 디바이스에 대한 UPNS를 모르는 경우 Microsoft 365 관리 센터를 사용하여 찾을 수 있습니다. 

Microsoft 365 관리 센터에 액세스하려면 관리자 역할을 할당해야 합니다. 자세한 내용은 관리자 역할 [정보 를 참조하세요.](/microsoft-365/admin/add-users/about-admin-roles)

Teams Rooms 디바이스 및 Surface Hubs의 UPNS를 얻은 경우 다음을 합니다.

1. 를 방문하여 Microsoft 365 관리 센터에 https://admin.microsoft.com 로그인합니다.
2. 사용자 활성  >  **사용자로 이동**
3. 표시 이름 열에서 Teams Rooms 디바이스  또는 Surface Hub의 이름을  찾을 수 있습니다(사용자가 많은 경우 검색 상자를 사용할 수 있습니다).
4. 사용자 이름 열에서  UPN을 찾을 수 있습니다(사용자 이름 또는 alias@contoso.com alias@contoso.onmicrosoft.com.
5. 조정된 모임에 참가할 각 디바이스에 대해 이 작업을 반복합니다.

## <a name="step-3-create-a-deployment-worksheet"></a>3단계: 배포 워크시트 만들기

조정된 모임 환경을 계획하고 디바이스의 UPNS 목록을 수집한 후 배포 워크시트를 만드는 것이 좋습니다. 배포 워크시트는 모든 디바이스에서 설정할 구성을 시각화하는 데 도움이 되므로 선택의 유효성을 검사하고 오류를 확인할 수 있습니다.

스프레드시트 앱에서 첫 번째 열에 다음에 대한 행을 추가합니다.

| 설정                | 설명      |
|------------------------|-----------------|
| **오디오 기본값**      | 모임이 시작될 때 마이크가 활성화될 디바이스를 확인합니다. 하나의 디바이스(일반적으로 Teams Rooms 디바이스)만 이 필드를 설정할 수 있으며, 나머지 디바이스에는 오디오 에코 및 피드백을 방지하기 위해 이 필드가 `true` `false` 설정되어 있어야 합니다.          |
| **오디오 사용**      | 모임의 참가자가 마이크를 끄거나 해제할 수 있는지 여부를 확인합니다. 오디오 **기본값이** 설정되어 있는 디바이스는 참가자가 실수로 마이크를 켜고 오디오 에코 또는 피드백을 일으킬 수 있도록 이 설정을 설정해야 `false` `false` 합니다.<p>**오디오 기본값이** 로 설정되어 있는 경우 이 설정이 무시되고 참가자가 마이크를 음소거하거나 `true` 음소거할 수 있습니다.          |
| **비디오 기본값**      | 모임이 시작될 때 카메라가 활성화될 디바이스를 확인합니다. 최상의 환경을 위해 다른 모든 디바이스가 으로 설정되는 동안 Teams Rooms 디바이스만 로 `true` 설정하는 것이 `false` 좋습니다.          |
| **비디오 사용**      | 모임의 참가자가 카메라를 설정하거나 해제할 수 있는지 여부를 결정합니다. 참가자가 다른 비디오 관점을 공유하려는 경우(예: 참가자가 Surface Hub 화이트보드를 사용하는 경우)의 다른 디바이스에서 이 기능을 설정할 `true` 수 있습니다. 참가자가 디바이스에서 카메라를 켜거나 끄지 못하게 하려는 경우 으로 `false` 설정합니다.<p> 비디오 **기본값이** 로 설정되어 있는 경우 이 설정은 무시되고 참가자는 카메라를 켜거나 `true` 해제할 수 있습니다.         |
| **화이트보드 기본값** | Teams Rooms 디바이스가 모임 참가자 중 하나에서 공유하는 화이트보드를 표시할지 여부를 확인합니다. Surface Hub가 있는 경우 및 이 허브가 없는 경우로 설정하는 `false` `true` 것이 좋습니다. 이 설정은 Surface Hubs에 영향을주지 않습니다. Surface Hubs는 항상 모임 참가자가 공유하는 화이트보드를 표시합니다.         |
| **화이트보드 사용** | 모임의 참가자가 화이트보드를 설정 또는 해제할 수 있는지 여부를 결정합니다. 참가자가 디바이스에서 화이트보드를 켜거나 끄지 못하게 하려는 경우 으로 `false` 설정합니다. <p>**화이트보드 기본값이** 로 설정되어 있는 경우 이 설정은 무시되고 참가자는 화이트보드를 켜거나 해제할 `true` 수 있습니다.
| **신뢰할 수 있는 계정**   | 이 목록은 디바이스가 모임 참가 요청을 수락해야 하는 각 Teams Room 디바이스 또는 Surface Hub에 대해 콤마로 구분된 UPNS 목록입니다. |

후속 열에서 각 Teams Rooms 디바이스 및 Surface Hubs를 추가합니다. 각 열에서 회의실에 대해 원하는 경험에 해당하는 값을 입력합니다. Teams Rooms 디바이스 1개와 Surface Hub 1개가 있는 예제는 다음과 같습니다.

- Teams 디바이스
  - 모임이 시작되면 오디오 및 **비디오가** 켜져 있습니다. 참가자는 **오디오** 및 비디오를 끄거나 해제할 수 있습니다.
  - 공유 화이트보드 표시가 해제됩니다.
- Surface Hub
  - 모임이 **시작되면** 오디오가 꺼집니다. 참가자는 **오디오를** 끄거나 해제할 수 없습니다.
  - 모임이 **시작되면** 비디오가 꺼집니다. 참가자는 **비디오를** 끄거나 해제할 수 있습니다.

| 설정                | Teams Room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **오디오 기본값**      | `true`          | `false`          |
| **오디오 사용**      | `true`          | `false`          |
| **비디오 기본값**      | `true`          | `false`          |
| **비디오 사용**      | `true`          | `true`           |
| **화이트보드 기본값** | `false`         | `false`          |
| **신뢰할 수 있는 계정**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>4단계: Teams Rooms 디바이스 구성

디바이스의 터치 스크린을 사용하여 Teams Rooms 디바이스에서 조정된 모임을 설정할 수도 있으며, 여러 디바이스를 설정해야 하고 중앙 위치에서 이를 원할 경우 XML 구성 파일을 사용할 수 있습니다.

이전 단계에서 만든 워크시트를 사용하여 디바이스를 설정하는 데 도움이 됩니다.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Teams Rooms 디바이스의 터치 스크린 사용

디바이스에서 조정된 모임을 설정하려면 다음을 합니다.

1. ...를 **선택합니다. 추가**  >  **설정** 입니다.
2. 관리자 암호를 입력하고 예 **를 선택합니다.**
3. 조정된 **모임을 선택합니다.**
4. **옵션에서** **조정된 모임을** 으로 _설정합니다._
5. **워크시트의** 오디오 기본값인 경우 이 디바이스의 마이크 켜기 를 켜고, 그렇지 않으면 `true` 을 끄면 _됩니다._ 
6. **워크시트에서** 오디오를 사용하도록 설정한 경우 이 디바이스의 마이크 켜기에서 모임에 참가할 때 사용자가 사용하도록 설정하도록 `true`  **를 선택합니다.** 이 장치의 마이크를 켜기로 설정한 경우 이 옵션을 해제할 수 없습니다. 
7. **워크시트의** 비디오 기본값인 경우 이 디바이스의 카메라 켜기 를 켜고 그렇지 않으면 `true` 을 끄면 _됩니다._ 
8. **워크시트에서** 사용하도록 설정된 비디오가 있는 경우 이 디바이스의 카메라 켜기에서 모임에 참가할 때 사용자가 사용하도록 설정하도록 `true`  **를 선택합니다.** 이 장치의 카메라를 으로  설정한 경우 이 옵션을 해제할 수 _없습니다._
9. **워크시트의 화이트보드** 기본값이 인 경우 이 디바이스에서 화이트보드 켜기 설정 을 으로 설정하고, 그렇지 않으면 `true` 을 끄면 _됩니다._  
10. 신뢰할 **수 있는 디바이스 계정 아래에서** 워크시트의 **신뢰할** 수 있는 계정에 나열된 각 UPN을 입력합니다. 여러 UPNS를 콤마로 구분합니다.
11. 저장 **및 종료를 선택합니다.**

저장 및 종료를 **선택하면** 디바이스가 다시 시작되어 조정된 모임에 참가할 준비가 됩니다.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Teams Rooms XML 구성 파일 사용

Teams Rooms 디바이스의 XML 구성 파일을 사용하여 조정된 `SkypeSettings.xml` 모임을 설정할 수 있습니다. 파일이 `SkypeSettings.xml` 정적 파일이 아니기 때문에 Teams Rooms 디바이스가 시작하면 이라는 파일을 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 체크 `SkypeSettings.xml` 인합니다. 파일이 있는 경우 디바이스는 파일에 지정된 구성을 읽고 적용합니다. 구성 적용이 완료되면 파일이 삭제됩니다. 파일에 대한 자세한 내용은 XML 구성 파일을 사용하여 콘솔 설정 관리를 `SkypeSettings.xml` [참조하세요.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

다음은 구성 파일의 조정된 모임 설정의 구문입니다.

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false" enabled="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

디바이스에서 조정된 모임을 설정하려면 다음을 합니다.

1. 코드 또는 메모장과 같은 텍스트 Visual Studio 파일 편집기에서 위의 XML을 새 파일에 붙여넣습니다.

2. 각 XML 요소를 스프레드시트의 해당 또는 `true` `false` 값으로 설정합니다. 예를 들어 오디오 **기본값이 인** `true` 경우 를 설정합니다. `<Audio default="true">`

3. UPNS `TrustedAccounts` 목록으로 변경해야 합니다.

4. 을 이름으로 `SkypeSettings.xml` 저장합니다.

5. Teams Rooms 디바이스의 폴더에 파일을 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 배치합니다. 이 작업을 몇 가지 방법으로 할 수 있습니다.

    - **Teams Rooms 디바이스에 파일 복사** 디바이스에 파일을 복사하려면 먼저 파일 공유를 사용하도록 설정하고 네트워크 공유를 만들어야 합니다. 그런 다음 네트워크 공유에 연결하고 디바이스에 파일을 복사할 수 있습니다. 자세한 내용은 [Microsoft Teams Rooms 유지 관리 및 작업을 참조하세요.](../rooms/rooms-operations.md)
    - **그룹 정책 사용** 디바이스에 파일을 복사하는 그룹 정책을 생성합니다. 자세한 내용은 그룹 정책 [개요 를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Teams Rooms 디바이스에서 파일 다운로드** 관리자 모드를 사용하여 디바이스에 로그인한 다음 네트워크 공유 또는 USB 드라이브에서 디바이스에 파일을 복사할 수 있습니다. 자세한 내용은 관리자 [모드로 전환을 참조하세요.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. 디바이스를 다시 시작합니다. 이 작업을 몇 가지 방법으로 할 수 있습니다.

    - **원격 PowerShell** 원격 PowerShell을 사용하여 디바이스에서 종료 명령을 실행할 수 있습니다. 자세한 내용은 [PowerShell을 사용하여 원격 관리를 참조하세요.](../rooms/rooms-operations.md)
    - **다시 시작-컴퓨터 실행** 로컬 컴퓨터에서 cmdlet을 실행하고 다시 시작할 디바이스의 컴퓨터 `Restart-Computer` 이름을 지정할 수 있습니다. 자세한 내용은 [다시 시작-컴퓨터 를 참조하세요.](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>5단계: Surface Hub 구성

Windows 구성 디자이너를 사용하여 Surface Hubs에 모임 조정 설정을 적용하는 데 사용할 수 있는 프로비전 패키지를 만들 수 있습니다. 위에서 만든 XML 파일을 Windows 구성 디자이너에 붙여넣어 프로비전 패키지를 만들 수 있습니다.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Surface Hub에 대한 조정된 모임 XML 구성 파일 만들기

Windows 구성 디자이너와 Microsoft Intune은 모두 Surface Hubs에 조정된 모임 구성을 적용하는 데 사용됩니다. 구성은 XML을 사용하여 정의됩니다. 더 나아가기 전에 적용될 XML을 만들어야 합니다.

다음은 조정된 모임 XML 구성 파일의 구문입니다.

```xml
<SurfaceHubSettings>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
    <CoordinatedMeetings enabled="true"> 
        <TrustedAccounts>room@contoso.com</TrustedAccounts>
        <Settings> 
            <Audio default="false" enabled="false" />
            <Video default="false" enabled="true" /> 
        </Settings> 
    </CoordinatedMeetings>
</SurfaceHubSettings>
```

Windows 구성 디자이너 또는 Microsoft Intune용 XML을 준비하려면 다음을 실행합니다.

1. 코드 또는 메모장과 같은 텍스트 Visual Studio 파일 편집기에서 위의 XML을 새 파일에 붙여넣습니다.

2. 각 XML 요소를 스프레드시트의 해당 또는 `true` `false` 값으로 설정합니다. 예를 들어 오디오 **기본값이 인** `true` 경우 를 설정합니다. `<Audio default="true">`

3. UPNS `TrustedAccounts` 목록으로 변경해야 합니다.

4. Windows 구성 디자이너는 XML이 한 줄에 있을 수 있습니다. XML이 다음과 같이 있도록 각 줄 사이의 모든 줄 끊기를 제거합니다.

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 컴퓨터에 파일을 저장합니다.

XML 구성 파일을 만든 후 [Surface Hub에서 Microsoft Teams](surface-hub-manage-config.md) 설정 관리의 단계를 사용하여 Surface Hubs에 적용합니다.