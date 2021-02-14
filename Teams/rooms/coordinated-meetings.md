---
title: Microsoft Teams 회의실 및 Surface Hub를 통해 조정된 모임 설정
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
description: Teams 회의실 장치와 Surface Hub를 구성하여 한 장치 또는 다른 장치가 모임에 참가할 때 모임에 참가하도록 합니다.
ms.openlocfilehash: cfd8bd423d8f7765a973d55e42d64773a06bba32
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803940"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams 회의실 및 Surface Hub를 통해 조정된 모임 설정

하나 이상의 Microsoft Teams 회의실 장치 또는 Surface Hub가 회의실에 있는 경우 조정된 모임을 설정할 수 있습니다. 조정된 모임을 사용하면 Teams 회의실 장치와 Surface Hub를 설정하여 한 장치에서 모임에 참가할 때 회의실의 다른 장치도 동일한 모임에 참가할 수 있습니다. 다른 사용자가 비활성화된 동안 참가자에게 최상의 환경을 제공하도록 카메라, 스피커 및 마이크를 구성할 수 있습니다. 이렇게 하여 모임에 여러 장치를 추가할 때 에코 및 피드백 노이즈 참가자가 경험할 수 있는 에코를 방지합니다.

조정된 모임을 설정하려면 Teams 회의실 장치 및 Surface Hubs가 모임에 참가하도록 올바르게 구성되어 있는지 확인해야 합니다. 가장 중요한 점은 각 장치에 자체 Exchange Room 사서함이 필요합니다. 설정 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Microsoft Teams 룸 배포](../rooms/rooms-deploy.md)
- [Surface Hub 2S 디바이스 계정 만들기](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

Teams 회의실 장치 및 Surface Hubs에서 자동으로 모임을 수락하고 성공적으로 참가할 수 있는 것을 확인한 후 조정된 모임을 설정할 수 있습니다.

각 회의실에 대해 다음 단계를 별도로 완료해야 합니다. 한 회의실의 장치는 다른 회의실의 장치를 통해 조정된 모임에 대해 설정하면 안 됩니다.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>1단계: 조정된 모임 환경 계획

구성을 변경하기 전에 각 회의실에서 어떤 장치를 사용할지 결정해야 합니다. 즉, 주어진 회의실의 경우 활성 마이크, 카메라 및 화이트보드를 사용할 장치를 결정해야 합니다. 디바이스를 구성하는 방법은 특정 환경에 따라 달라지지만 다음은 몇 가지 일반적인 권장 사항입니다.

- **마이크** Teams 회의실 장치
- **카메라** Teams 회의실 장치(기본적으로 설정) 및 Surface Hub(기본적으로 해제되어 있지만 참가자가 켜져 있을 수 있습니다.)
- **화이트보드** Surface Hub

> [!IMPORTANT]
> 한 장치에서만 마이크를 사용하도록 설정해야 합니다. 두 개 이상의 장치에서 사용하도록 설정하면 오디오 에코 및 피드백이 표시됩니다.

## <a name="step-2-get-your-devices-upns"></a>2단계: 디바이스의 UPNS를 얻음

회의실에서 조정된 모임 환경을 설정할 때 해당 회의실의 Teams 회의실 장치와 Surface Hubs에 조정해야 합니다. 구성에 조정해야 하는 디바이스의 UPN(사용자 계정 이름)을 추가하여 수행됩니다. 조정된 모임에 대해 설정하려는 각 장치에 대한 UPNS를 모르는 경우 Microsoft 365 관리 센터를 사용하여 찾을 수 있습니다. 

Microsoft 365 관리 센터에 액세스하려면 관리자 역할이 할당되어야 합니다. 자세한 내용은 관리자 역할 [정보를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

Teams 회의실 장치 및 Surface Hub의 UPNS를 얻습니다. 다음을 합니다.

1. 을 방문하여 Microsoft 365 관리 센터에 https://admin.microsoft.com 로그인합니다.
2. 사용자 **활성**  >  **사용자로 이동**
3. 표시 이름 열에서 Teams 회의실 장치  또는 Surface Hub의 이름을  찾을 수 있습니다(사용자가 많은 경우 검색 상자를 사용할 수 있습니다).
4. 사용자 이름 열에서 UPN을 찾을 **수** 있습니다(예: alias@contoso.com 또는 alias@contoso.onmicrosoft.com.
5. 조정된 모임에 참가할 각 장치에 대해 이 작업을 반복합니다.

## <a name="step-3-create-a-deployment-worksheet"></a>3단계: 배포 워크시트 만들기

조정된 모임 환경을 계획하고 장치의 UPNS 목록을 수집한 후 배포 워크시트 만들기를 하는 것이 좋습니다. 배포 워크시트는 모든 디바이스에서 설정하려는 구성을 시각화하는 데 도움이 되므로 선택의 유효성을 검사하고 오류를 확인할 수 있습니다.

스프레드시트 앱에서 첫 번째 열에 다음 행을 추가합니다.

| 설정                | 설명      |
|------------------------|-----------------|
| **오디오 기본값**      | 모임이 시작될 때 마이크가 활성화될 장치를 확인합니다. 하나의 장치(일반적으로 Teams 회의실 장치)만 이 필드를 설정할 수 있는 반면 나머지 디바이스는 오디오 에코 및 피드백을 피하기 위해 이 필드를 `true` `false` 설정해야 합니다.          |
| **오디오 사용**      | 모임 참가자가 마이크를 설정 또는 해제할 수 있는지 여부를 확인합니다. 오디오 **기본값이** 설정되어 있는 장치에는 참가자가 실수로 마이크를 켜고 오디오 에코 또는 피드백을 유발하지 않도록 이 설정을 `false` `false` 설정해야 합니다.<p>오디오 **기본값이** 설정되어 있는 경우 이 설정은 무시되고 참가자는 마이크를 음소거하거나 `true` 음소거를 음소거할 수 있습니다.          |
| **비디오 기본값**      | 모임을 시작할 때 카메라가 활성화될 장치를 확인합니다. 최상의 환경을 위해 다른 모든 장치가 설정된 동안 Teams 회의실 `true` 장치만 설정하는 것이 `false` 좋습니다.          |
| **비디오 사용**      | 모임 참가자가 카메라를 설정 또는 해제할 수 있는지 여부를 판단합니다. 참가자가 다른 비디오 관점을 공유하려는 경우(예: 참가자가 Surface Hub 화이트보드를 사용하는 경우) 다른 모든 장치에서 설정할 `true` 수 있습니다. 참가자가 장치에서 카메라를 켜거나 끄지 못하게 하려는 경우 이 기능을 으로 `false` 설정하세요.<p> 비디오 **기본값이** 설정되어 있는 경우 이 설정은 무시되고 참가자는 카메라를 `true` 켜거나 끄면 됩니다.         |
| **화이트보드 기본값** | Teams 회의실 장치에서 모임 참가자 중 한 명과 공유한 화이트보드를 표시할지 여부를 확인합니다. Surface Hub가 있는 경우 및 Surface Hub가 없는 경우 설정하는 `false` `true` 것이 좋습니다. 이 설정은 Surface Hubs에 영향을 주지 않습니다. Surface Hubs는 항상 모임 참가자가 공유한 화이트보드를 표시합니다.         |
| **화이트보드 사용** | 모임 참가자가 화이트보드를 설정/해제할 수 있는지 여부를 판단합니다. 참가자가 장치에서 화이트보드를 켜거나 끄지 못하게 하려는 경우 이 기능을 으로 `false` 설정하세요. <p>Whiteboard **기본값을** 설정하면 이 설정이 무시되고 참가자가 화이트보드를 `true` 켜거나 끄면 됩니다.
| **신뢰할 수 있는 계정**   | 이 목록은 장치가 모임 참가 요청을 수락해야 하는 각 Teams 회의실 장치 또는 Surface Hub에 대한 콤마로 구분된 UPNS 목록입니다. |

후속 열에서 Teams 회의실 장치와 Surface Hubs를 각각 추가합니다. 각 열에서 회의실에 대해 원하는 경험에 해당하는 값을 입력합니다. Teams Rooms 장치 1개와 Surface Hub 1개가 있는 예제는 다음과 같습니다.

- Teams 장치
  - 모임이 시작되면 오디오 및 **비디오가** 켜져 있습니다. 참가자는 **오디오** 및 비디오를 전환하거나 해제할 수 있습니다.
  - 공유 화이트보드 표시가 꺼져 있습니다.
- Surface Hub
  - 모임이 **시작되면** 오디오가 꺼집니다. 참가자는 **오디오를** 전환하거나 해제할 수 없습니다.
  - 모임이 **시작되면** 비디오가 꺼집니다. 참가자는 **비디오를** 토글하거나 해제할 수 있습니다.

| 설정                | Teams Room      | Surface Hub      |
|------------------------|-----------------|------------------|
| **오디오 기본값**      | `true`          | `false`          |
| **오디오 사용**      | `true`          | `false`          |
| **비디오 기본값**      | `true`          | `false`          |
| **비디오 사용**      | `true`          | `true`           |
| **화이트보드 기본값** | `false`         | `false`          |
| **신뢰할 수 있는 계정**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>4단계: Teams 회의실 장치 구성

장치의 터치 스크린을 사용하여 Teams 회의실 장치에서 조정된 모임을 설정할 수도 있으며, 여러 장치를 설정해야 하고 중앙 위치에서 설정하려는 경우 XML 구성 파일을 사용할 수 있습니다.

이전 단계에서 만든 워크시트에서 디바이스를 설정하는 데 도움이 됩니다.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Teams 회의실 장치의 터치 스크린 사용

장치에서 조정된 모임을 설정하려면 다음을 합니다.

1. **...를 선택합니다. 추가**  >  **설정.**
2. 관리자 암호를 입력하고 [예]를 **선택합니다.**
3. 조정된 **모임을 선택합니다.**
4. **옵션에서** **조정된 모임을 으로** _설정_
5. **워크시트의** 오디오 기본값이면 이 장치의 마이크를 켜고, 그렇지 않으면 `true` _끄면 됩니다._ 
6. **워크시트에서** 오디오를 사용하도록 설정한 경우 이 장치의 마이크 켜기 아래에서 모임에 참가할 때 다른 사용자가 사용하도록 `true`  **설정하도록 설정합니다.** 이 장치의 마이크를 켜면  이 옵션을 해제할 수 없습니다.
7. **워크시트의** 비디오 기본값이 설정되어 있는 경우 이 장치의 카메라를 켜고, 그렇지 않으면 `true` _끄면 됩니다._ 
8. **워크시트에서** 비디오를 사용하도록 설정한 경우 이 장치의 카메라 켜기 아래에서 모임에 참가할 때 다른 사용자가 사용하도록 설정하도록 `true` **설정합니다.**  이 장치의 카메라를 켜면 이 옵션을 해제할 **수** _없습니다._
9. **워크시트의 화이트보드** 기본값이 설정되어 있는 경우 이 장치의 화이트보드 켜기 설정, 설정하지 않은 경우 `true` _해제합니다._  
10. 신뢰할 **수 있는 디바이스 계정 아래에서** 워크시트의 신뢰할 수 있는 계정에 나열된 각 UPN을 입력합니다.  여러 UPNS를 콤마로 구분합니다.
11. 저장을 **선택하고 종료합니다.**

저장을 **선택하고** 종료하면 장치가 다시 시작되어 조정된 모임에 참가할 준비가 됩니다.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Teams 회의실 XML 구성 파일 사용

Teams 회의실 장치의 XML 구성 파일을 사용하여 조정된 모임을 설정할 `SkypeSettings.xml` 수 있습니다. 파일이 `SkypeSettings.xml` 정적 파일이 아닌 경우 Teams Rooms 디바이스가 시작되는 경우 이름이 .인된 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 파일을 `SkypeSettings.xml` 확인합니다. 파일이 있는 경우 디바이스는 파일에 지정된 구성을 읽고 적용합니다. 구성 적용이 완료되면 파일이 삭제됩니다. 파일에 대한 자세한 내용은 XML 구성 파일을 사용하여 콘솔 `SkypeSettings.xml` [설정 관리를 참조하세요.](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)

다음은 구성 파일의 조정된 모임 설정 구문입니다.

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

장치에서 조정된 모임을 설정하려면 다음을 합니다.

1. 코드 또는 메모장과 같은 텍스트 Visual Studio 편집기에서 위의 XML을 새 파일에 붙여넣습니다.

2. 각 XML 요소를 스프레드시트의 해당 또는 값으로 `true` `false` 설정합니다. 예를 들어 오디오 **기본값인 경우** `true` . `<Audio default="true">`

3. UPNS 목록으로 `TrustedAccounts` 변경해야 합니다.

4. 파일을 이름으로 `SkypeSettings.xml` 저장합니다.

5. Teams 회의실 장치의 폴더에 파일을 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 배치합니다. 이 작업을 몇 가지 방법으로 할 수 있습니다.

    - **Teams 회의실 장치에 파일 복사** 디바이스에 파일을 복사하려면 먼저 파일 공유를 사용하도록 설정하고 네트워크 공유를 만들어야 합니다. 그런 후 네트워크 공유에 연결하고 파일을 디바이스에 복사할 수 있습니다. 자세한 내용은 Microsoft Teams Rooms 유지 관리 [및 작업을 참조하세요.](../rooms/rooms-operations.md)
    - **그룹 정책 사용** 디바이스에 파일을 복사하는 그룹 정책을 생성합니다. 자세한 내용은 그룹 정책 [개요를 참조하세요.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))
    - **Teams 회의실 장치에서 파일 다운로드** 관리 모드를 사용하여 디바이스에 로그인한 다음 네트워크 공유 또는 USB 드라이브에서 디바이스에 파일을 복사할 수 있습니다. 자세한 내용은 관리자 [모드로 전환을 참조하세요.](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)
    
6. 디바이스를 다시 시작합니다. 이 작업을 몇 가지 방법으로 할 수 있습니다.

    - **원격 PowerShell** 원격 PowerShell을 사용하여 디바이스에서 종료 명령을 실행할 수 있습니다. 자세한 내용은 [PowerShell을 사용하여 원격 관리를 참조하세요.](../rooms/rooms-operations.md)
    - **Restart-Computer 실행** 로컬 컴퓨터에서 cmdlet을 실행하고 다시 시작하려는 디바이스의 컴퓨터 `Restart-Computer` 이름을 지정할 수 있습니다. 자세한 내용은 [Restart-Computer를 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)

## <a name="step-5-configure-surface-hub"></a>5단계: Surface Hub 구성

Windows 구성 디자이너를 사용하여 Surface Hubs에 모임 조정 설정을 적용하는 데 사용할 수 있는 프로비전 패키지를 만들 수 있습니다. 위에서 만든 XML 파일을 Windows 구성 디자이너에 붙여넣어 프로비전 패키지를 만들게 됩니다.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Surface Hub에 대한 조정된 모임 XML 구성 파일 만들기

Windows 구성 디자이너와 Microsoft Intune은 모두 Surface Hubs에 조정된 모임 구성을 적용하는 데 사용됩니다. 구성은 XML을 사용하여 정의됩니다. 더 진행하기 전에 적용할 XML을 만들어야 합니다.

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

1. 코드 또는 메모장과 같은 텍스트 Visual Studio 편집기에서 위의 XML을 새 파일에 붙여넣습니다.

2. 각 XML 요소를 스프레드시트의 해당 또는 값으로 `true` `false` 설정합니다. 예를 들어 오디오 **기본값인 경우** `true` . `<Audio default="true">`

3. UPNS 목록으로 `TrustedAccounts` 변경해야 합니다.

4. Windows 구성 디자이너에서는 XML이 한 줄에 표시되어야 합니다. XML이 다음과 같게 각 줄 사이에 있는 줄을 모두 제거합니다.

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 컴퓨터에 파일을 저장합니다.

XML 구성 파일을 만든 후 [Surface Hub에서 Microsoft Teams](surface-hub-manage-config.md) 설정 관리의 단계를 사용하여 Surface Hubs에 적용합니다.
