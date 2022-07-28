---
title: Microsoft Teams 룸 및 Surface Hub를 사용하여 조정된 모임 설정
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
ms.localizationpriority: medium
description: 한 장치 또는 다른 디바이스가 모임에 참가할 때 모임에 참가하도록 Teams 룸 디바이스 및 Surface Hub를 구성합니다.
ms.openlocfilehash: 1f249e9bd0321c9e8afd984aca90f902ad80d444
ms.sourcegitcommit: 644374fcad6372494e87d729de690af4c060f635
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2022
ms.locfileid: "67054939"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Microsoft Teams 룸 및 Surface Hub를 사용하여 조정된 모임 설정

회의실에 하나 이상의 Microsoft Teams 룸 디바이스 또는 Surface Hub가 있는 경우 조정된 모임을 설정할 수 있습니다. 조정된 모임을 사용하면 한 장치에서 모임에 참가할 때 회의실의 다른 장치도 동일한 모임에 참가하도록 Teams 룸 장치 및 Surface Hub를 설정할 수 있습니다. 카메라, 스피커 및 마이크를 구성하여 참가자에게 최상의 환경을 제공하는 카메라, 스피커 및 마이크를 다른 사용자가 사용하지 않도록 설정할 수 있습니다. 이렇게 하면 모임에 여러 장치를 추가할 때 공포의 에코 및 피드백 노이즈 참가자가 경험할 수 있는 피드백을 방지할 수 있습니다.

조정된 모임을 설정하려면 Teams 룸 장치와 Surface Hub가 이미 모임에 참여하도록 올바르게 구성되어 있는지 확인해야 합니다. 가장 중요한 것은 각 디바이스에 자체 Exchange Room 사서함이 있어야 한다는 것입니다. 설정하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Microsoft Teams 룸 배포](../rooms/rooms-deploy.md)
- [Surface Hub 2S 디바이스 계정 만들기](/surface-hub/surface-hub-2s-account)

Teams 룸 장치와 Surface Hub가 자동으로 모임을 수락하고 성공적으로 참가할 수 있음을 확인한 후에는 조정된 모임을 설정할 수 있습니다.

각 회의실에 대해 다음 단계를 별도로 완료해야 합니다.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>1단계: 조정된 모임 환경 계획

구성을 변경하기 전에 각 회의실에서 수행할 작업을 수행할 디바이스를 결정해야 합니다. 즉, 지정된 회의실의 경우 활성 마이크, 카메라 및 화이트보드가 있는 장치를 결정해야 합니다. 디바이스를 구성하는 방법은 특정 환경에 따라 달라지지만 다음은 몇 가지 일반적인 권장 사항입니다.

- **마이크** Teams 룸 디바이스
- **카메라** Teams 룸 디바이스(기본적으로 켜기) 및 Surface Hub(기본적으로 꺼져 있지만 참가자가 켤 수 있음)
- **화이트 보드** Surface Hub

> [!IMPORTANT]
> 하나의 장치에서만 마이크를 사용하도록 설정해야 합니다. 둘 이상의 장치에서 사용하도록 설정하면 오디오 에코 및 피드백이 발생합니다.

## <a name="step-2-get-your-devices-upns"></a>2단계: 디바이스의 UPN 가져오기

회의실에서 조정된 모임 환경을 설정할 때 해당 회의실의 Teams 룸 디바이스 및 Surface Hub에 조정할 디바이스를 알려야 합니다. 이 작업은 구성과 조정해야 하는 디바이스의 UPN(사용자 계정 이름)을 추가하여 수행됩니다. 조정된 모임에 대해 설정하려는 각 디바이스의 UPN을 모르는 경우 Microsoft 365 관리 센터 사용하여 찾을 수 있습니다. 

Microsoft 365 관리 센터 액세스하려면 관리자 역할이 할당되어야 합니다. 자세한 내용은 [관리자 역할 정보를 참조하세요](/microsoft-365/admin/add-users/about-admin-roles).

Teams 룸 디바이스 및 Surface Hub의 UPN을 얻으려면 다음을 수행합니다.

1. 을 방문하여 Microsoft 365 관리 센터 로그인합니다https://admin.microsoft.com.
2. **사용자** > **활성 사용자** 로 이동합니다.
3. **표시 이름** 열에서 Teams 룸 디바이스 또는 Surface Hub의 이름을 찾습니다(사용자가 많은 경우 **검색** 상자를 사용할 수 있음).
4. **사용자 이름** 열에서 UPN을 찾습니다(alias@contoso.com 또는 alias@contoso.onmicrosoft.com 같이 표시됨).
5. 조정된 모임에 참여할 각 디바이스에 대해 이 작업을 반복합니다.

## <a name="step-3-create-a-deployment-worksheet"></a>3단계: 배포 워크시트 만들기

조정된 모임 환경을 계획하고 디바이스의 UPN 목록을 수집한 후에는 배포 워크시트를 만드는 것이 좋습니다. 배포 워크시트를 사용하면 모든 디바이스에서 설정하려는 구성을 시각화하여 선택 항목의 유효성을 검사하고 오류를 확인할 수 있습니다.

스프레드시트 앱의 첫 번째 열에 다음 행을 추가합니다.

| 설정                | 설명      |
|------------------------|-----------------|
| **오디오 기본값**      | 모임이 시작될 때 마이크가 활성화될 디바이스를 결정합니다. 하나의 디바이스(일반적으로 Teams 룸 디바이스)만 이 필드를 설정할 `true` 수 있지만 나머지 디바이스는 오디오 에코 및 피드백을 방지하기 위해 `false` 이 필드를 설정해야 합니다.          |
| **오디오 사용**      | 모임 참가자가 마이크를 켜거나 끌 수 있는지 여부를 결정합니다. **오디오 기본값** 이 설정된 `false` 디바이스는 참가자가 실수로 마이크를 `false` 켜고 오디오 에코 또는 피드백을 발생시킬 수 없도록 이 설정을 설정해야 합니다.<p>**오디오 기본값** 이 설정된 `true`경우 이 설정은 무시되며 참가자는 마이크를 음소거하거나 음소거 해제할 수 있습니다.          |
| **비디오 기본값**      | 모임이 시작될 때 카메라가 활성화될 디바이스를 결정합니다. 최상의 환경을 위해 다른 모든 디바이스가 설정된 동안 Teams 룸 디바이스만 설정하는 `true` `false`것이 좋습니다.          |
| **비디오 사용**      | 모임 참가자가 카메라를 켜거나 끌 수 있는지 여부를 결정합니다. 참가자가 Surface Hub 화이트보드를 `true` 사용하는 경우와 같이 다른 비디오 관점을 공유하려는 이벤트 참가자의 다른 장치에서 이 설정을 지정할 수 있습니다. 참가자가 디바이스에서 카메라를 켜거나 끄지 않도록 하려면 이 옵션을 설정하세요 `false`.<p> **비디오 기본값** 이 설정된 `true`경우 이 설정은 무시되며 참가자는 카메라를 켜거나 끌 수 있습니다.         |
| **화이트보드 기본값** | Teams 룸 장치에서 모임 참가자 중 한 명이 공유하는 화이트보드를 표시할지 여부를 결정합니다. Surface Hub가 있고 Surface Hub `true` 가 없는 경우 이를 `false` 설정하는 것이 좋습니다. 이 설정은 Surface Hubs에 영향을 주지 않습니다. Surface Hubs는 항상 모임 참가자가 공유하는 화이트보드를 표시합니다.         |
| **화이트보드 사용** | 모임 참가자가 화이트보드를 켜거나 끌 수 있는지 여부를 결정합니다. 참가자가 디바이스에서 화이트보드를 켜거나 끄지 않으려면 이 옵션을 설정하세요 `false`. <p>**화이트보드 기본값** 이 설정된 `true`경우 이 설정은 무시되며 참가자는 화이트보드를 켜거나 끌 수 있습니다.
| **신뢰할 수 있는 계정**   | 각 Teams 룸 디바이스 또는 Surface Hub에 대해 쉼표로 구분된 UPN 목록으로, 디바이스가 모임 참가 요청을 수락해야 하거나 모임 참가 요청을 보내야 합니다. |

후속 열에서 각 Teams 룸 디바이스 및 Surface Hub를 추가합니다. 각 열에서 회의실에 대해 원하는 환경에 해당하는 값을 입력합니다. 다음은 하나의 Teams 룸 디바이스와 하나의 Surface Hub를 사용하는 예제입니다.

- Teams 디바이스
  - 모임이 시작되면 오디오 및 비디오가 **켜** 집니다. 참가자는 오디오 및 비디오를 켜거나 끌 **수 있습니다** .
  - 공유 화이트보드 표시가 꺼져 있습니다.
- Surface Hub
  - 모임이 시작되면 오디오가 **꺼** 집니다. 참가자는 오디오를 켜거나 끌 **수 없습니다** .
  - 모임이 시작되면 비디오가 **꺼** 집니다. 참가자는 비디오를 켜거나 끌 **수 있습니다** .

| 설정                | Teams 룸      | Surface Hub      |
|------------------------|-----------------|------------------|
| **오디오 기본값**      | `true`          | `false`          |
| **오디오 사용**      | `true`          | `false`          |
| **비디오 기본값**      | `true`          | `false`          |
| **비디오 사용**      | `true`          | `true`           |
| **화이트보드 기본값** | `false`         | `false`          |
| **신뢰할 수 있는 계정**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>4단계: Teams 룸 디바이스 구성

디바이스의 터치 스크린을 사용하여 Teams 룸 디바이스에서 조정된 모임을 설정하거나, 많은 디바이스를 설정해야 하고 중앙 위치에서 조정된 모임을 설정하려는 경우 XML 구성 파일을 사용할 수 있습니다.

이전 단계에서 만든 워크시트를 사용하여 디바이스를 설정할 수 있습니다.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>Teams 룸 디바이스의 터치 스크린 사용

장치에서 조정된 모임을 설정하려면 다음을 수행합니다.

1. ...를 선택합니다 **. 추가** > **설정**.
2. 관리자 암호를 입력하고 **예를** 선택합니다.
3. **조정된 모임을** 선택합니다.
4. **옵션** 아래에서 **조정된 모임을** _켜_ 도록 설정합니다.
5. 워크시트의 **오디오 기본값** 이 `true`면 **이 장치의 마이크를 켜도록** 설정하고, 그렇지 않으면 _끕니다_.
6. 워크시트에서 오디오를 `true`**사용할 수** 있는 경우 **이 장치의 마이크 켜기** 에서 **모임에 참가할 때 사용자가 활성화** 하도록 허용을 선택합니다. **이 장치의 마이크** 를 켜면 이 옵션을 끌 수 없습니다.
7. 워크시트의 **비디오 기본값** 이 `true`면 **이 장치의 카메라를 켜도록** 설정하고, 그렇지 않으면 _끕니다_.
8. 워크시트`true`에서 **비디오가 활성화된** 경우 **이 장치의 카메라 켜기** 에서 **모임에 참가할 때 사용자가 사용하도록 설정** 하도록 허용을 선택합니다. **이 장치의 카메라를** 켜면 이 옵션을 끌 수 _없습니다._
9. 워크시트의 **화이트보드 기본값** 이 `true`면 **이 디바이스에서 화이트보드 켜기를** _켜_ 도록 설정하고, 그렇지 않으면 _해제_ 합니다.
10. **신뢰할 수 있는 디바이스 계정** 에서 워크시트의 신뢰할 수 있는 계정에 나열 **된** 각 UPN을 입력합니다. 여러 UPN을 쉼표로 구분합니다.
11. 신뢰할 수 있는 디바이스에서 근접 및 회의실 원격을 끕니다. 
12. **저장을 선택하고 종료합니다**.

**저장 및 종료** 를 선택하면 디바이스가 다시 시작되고 조정된 모임에 참여할 준비가 됩니다.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>Teams 룸 XML 구성 파일 사용

조정된 모임은 Teams 룸 디바이스의 `SkypeSettings.xml` XML 구성 파일을 사용하여 설정할 수 있습니다. 파일이 `SkypeSettings.xml` 정적 파일이 아닙니다. Teams 룸 디바이스가 시작되면 이름이 지정된 `SkypeSettings.xml`파일을 체크 인 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 합니다. 파일이 있는 경우 디바이스는 파일에 지정된 구성을 읽고 적용합니다. 구성 적용이 완료되면 파일이 삭제됩니다. 파일에 대한 `SkypeSettings.xml` 자세한 내용은 [XML 구성 파일을 사용하여 콘솔 설정 관리를](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) 참조하세요.

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

장치에서 조정된 모임을 설정하려면 다음을 수행합니다.

1. Visual Studio Code 또는 메모장과 같은 텍스트 파일 편집기에서 위의 XML을 새 파일에 붙여넣습니다.

2. 각 XML 요소를 스프레드시트의 해당 `true` 또는 `false` 값으로 설정합니다. For example, if **Audio default** is `true`, set `<Audio default="true">`.

3. UPN 목록으로 변경 `TrustedAccounts` 해야 합니다.

4. 이름으로 `SkypeSettings.xml`파일을 저장합니다.

5. 파일을 Teams 룸 디바이스의 폴더에 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 배치합니다. 이 작업은 다음과 같은 몇 가지 방법으로 수행할 수 있습니다.

    - **파일을 Teams 룸 디바이스에 복사** 하려면 파일 공유를 사용하도록 설정하고 네트워크 공유를 만들어야 디바이스에 파일을 복사할 수 있습니다. 이렇게 하면 네트워크 공유에 연결하고 디바이스에 파일을 복사할 수 있습니다. 자세한 내용은 [Microsoft Teams 룸 유지 관리 및 작업을 참조하세요](../rooms/rooms-operations.md).
    - **그룹 정책 사용하여** 그룹 정책을 만들어 파일을 디바이스에 복사합니다. 자세한 내용은 [그룹 정책 개요](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))를 참조하세요.
    - **Teams 룸 디바이스에서 파일을 다운로드** 하면 관리 모드를 사용하여 디바이스에 로그인한 다음 네트워크 공유 또는 USB 드라이브에서 디바이스에 파일을 복사할 수 있습니다. 자세한 내용은 [관리 모드로 전환을](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running) 참조하세요.
    
6. 디바이스를 다시 시작합니다. 이 작업은 다음과 같은 몇 가지 방법으로 수행할 수 있습니다.

    - **원격 PowerShell** 원격 PowerShell을 사용하여 디바이스에서 Shutdown 명령을 실행할 수 있습니다. 자세한 내용은 [PowerShell을 사용한 원격 관리를](../rooms/rooms-operations.md) 참조하세요.
    - **Restart-Computer 실행** 로컬 컴퓨터에서 cmdlet을 `Restart-Computer` 실행하고 다시 시작하려는 디바이스의 컴퓨터 이름을 지정할 수 있습니다. 자세한 내용은 [Restart-Computer](/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)를 참조하세요.

## <a name="step-5-configure-surface-hub"></a>5단계: Surface Hub 구성

Windows 구성 디자이너를 사용하여 Surface Hubs에 모임 조정 설정을 적용하는 데 사용할 수 있는 프로비저닝 패키지를 만들 수 있습니다. 위에서 만든 XML 파일을 Windows 구성 디자이너에 붙여넣어 프로비전 패키지를 만듭니다.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Surface Hub에 대한 조정된 모임 XML 구성 파일 만들기

Windows 구성 디자이너와 Microsoft Intune 모두 Surface Hub에 조정된 모임 구성을 적용하는 데 사용됩니다. 구성은 XML을 사용하여 정의됩니다. 더 나아가기 전에 적용할 XML을 만들어야 합니다.

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

Windows 구성 디자이너 또는 Microsoft Intune 대한 XML을 준비하려면 다음을 수행합니다.

1. Visual Studio Code 또는 메모장과 같은 텍스트 파일 편집기에서 위의 XML을 새 파일에 붙여넣습니다.

2. 각 XML 요소를 스프레드시트의 해당 `true` 또는 `false` 값으로 설정합니다. For example, if **Audio default** is `true`, set `<Audio default="true">`.

3. UPN 목록으로 변경 `TrustedAccounts` 해야 합니다.

4. Windows 구성 디자이너를 사용하려면 XML이 한 줄에 있어야 합니다. XML이 다음과 같이 보이도록 각 줄 사이의 모든 줄 바꿈을 제거합니다.

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 컴퓨터에 파일을 저장합니다.

XML 구성 파일을 만든 후 [Surface Hub에서 Microsoft Teams 설정 관리의 단계를 사용하여 Surface Hubs에](surface-hub-manage-config.md) 적용합니다.
