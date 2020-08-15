---
title: Microsoft 팀 회의실 및 Surface Hub를 사용 하 여 조정 되는 모임 설정
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
description: 하나 이상의 장치 또는 다른 상대방이 모임에 참가할 때 모임에 참가 하도록 팀 대화방 디바이스 및 Surface Hub를 구성 합니다.
ms.openlocfilehash: c1200b4e949cb866440907f8577f61f4528630e2
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761451"
---
# <a name="set-up-coordinated-meetings-with-microsoft-teams-rooms-and-surface-hub"></a>Microsoft 팀 회의실 및 Surface Hub를 사용 하 여 조정 되는 모임 설정

회의실에 하나 이상의 Microsoft 팀 방 장치나 Surface Hub가 있는 경우에는 조정 된 모임을 설정할 수 있습니다. 조정 된 모임을 사용 하면 한 장치에서 모임에 참가할 때 방에 있는 다른 장치도 같은 모임에도 참가 하도록 팀 대화방 장치 및 Surface Hub를 설정할 수 있습니다. 카메라, 스피커, 마이크를 구성 하 여 참가자가 최상의 환경을 제공 하는 경우 다른 사용자가 사용 하지 않도록 설정할 수 있습니다. 이렇게 하면 모임에 여러 장치를 추가할 때 dreaded 반향 및 피드백 잡음 참가자가 경험을 피할 수 있습니다.

조정 된 모임을 설정 하려면 팀 대화방 디바이스 및 Surface Hub가 모임에 참가 하도록 올바르게 구성 되어 있는지 확인 해야 합니다. 가장 중요 한 것은 각 장치에 고유한 Exchange 대화방 사서함이 있어야 한다는 것입니다. 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [Microsoft Teams 룸 배포](../rooms/rooms-deploy.md)
- [Surface Hub 2S 디바이스 계정 만들기](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)

팀 대화방 장치 및 Surface Hub가 모임을 자동으로 수락 하 고 성공적으로 참가 하는 것을 확인 한 후에는 조정 된 모임을 설정할 수 있습니다.

각 회의실에 대해 개별적으로 다음 단계를 완료 해야 합니다. 한 회의실의 디바이스는 다른 회의실에 있는 디바이스와의 공동 모임에 대해 설정 하지 않아야 합니다.

## <a name="step-1-plan-your-coordinated-meeting-experience"></a>1 단계: 통합 모임 환경 계획

구성을 변경 하기 전에 각 회의실에서 어떤 장치가 작업을 수행할 것인지 결정 해야 합니다. 즉, 지정 된 회의실에 대해 활성 마이크, 카메라, 화이트 보드를 사용 하는 디바이스를 결정 해야 합니다. 장치를 구성 하는 방법은 특정 환경에 따라 다르지만 몇 가지 일반적인 권장 사항은 다음과 같습니다.

- **Microphone** 팀 대화방 장치
- **카메라가** 팀 대화방 장치 (기본적으로 설정) 및 Surface Hub (기본적으로 해제 되지만 참가자가 설정할 수 있음)
- **화이트 보드** Surface Hub

> [!IMPORTANT]
> 한 장치 에서만 마이크를 사용할 수 있도록 설정 해야 합니다. 두 개 이상의 장치에서이 기능을 사용 하도록 설정 하는 경우 오디오 에코 및 피드백을 경험할 수 있습니다.

## <a name="step-2-get-your-devices-upns"></a>2 단계: 디바이스의 Upn 가져오기

회의실에서 조정 된 모임 환경을 설정 하는 경우 팀 대화방 장치 및 Surface Hub에 조정할 디바이스를 해당 방에 알려야 합니다. 해당 구성에 맞게 조정 해야 하는 장치의 UPN (사용자 계정 이름)을 추가 하 여이 작업을 수행 합니다. 조정 된 모임에 대해 설정 하려는 각 장치에 대 한 Upn을 모르는 경우 Microsoft 365 관리 센터를 사용 하 여 찾을 수 있습니다. 

Microsoft 365 관리 센터에 액세스 하려면 관리자 역할을 할당 해야 합니다. 자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조 하세요.

팀 방에 디바이스 및 Surface Hub의 Upn을 받으려면 다음을 수행 합니다.

1. 방문 하 여 Microsoft 365 관리 센터에 로그인 https://admin.microsoft.com
2. **사용자**  >  **활성 사용자** 로 이동
3. **표시 이름** 열에서 팀 대화방 장치 또는 Surface Hub의 이름을 찾습니다 (사용자 수가 많은 경우 **검색** 상자를 사용할 수 있음).
4. **사용자 이름** 열에서 UPN을 찾습니다 (예: alias@contoso.com 또는 alias@contoso.onmicrosoft.com).
5. 조정 된 모임에 참여할 각 장치에 대해이를 반복 합니다.

## <a name="step-3-create-a-deployment-worksheet"></a>3 단계: 배포 워크시트 만들기

통합 된 모임 경험을 계획 하 고 디바이스의 Upn 목록을 수집한 후에는 배포 워크시트를 만드는 것이 좋습니다. 배포 워크시트는 모든 장치에서 설정할 구성을 시각화 하는 데 도움이 되며, 선택 항목의 유효성을 검사 하 고 오류를 확인할 수 있습니다.

스프레드시트 앱에서 첫 번째 열에 다음에 대 한 행을 추가 합니다.

| 설정                | 설명      |
|------------------------|-----------------|
| **오디오 기본값**      | 모임이 시작 될 때 마이크가 활성화 되는 장치를 결정 합니다. 장치 중 일부 (일반적으로 팀 대화방 장치)는 `true` `false` 오디오 에코 및 피드백을 방지 하기 위해이 필드를 설정 해야 하는 경우에만이 필드를 설정할 수 있습니다.          |
| **오디오 사용**      | 모임의 참가자가 마이크를 켜거나 끌 수 있는지 여부를 결정 합니다. **오디오를 기본적** 으로 설정 하는 장치는 `false` 참가자가 `false` 마이크를 실수로 켜고 오디오 반향 또는 피드백이 발생할 수 없도록이 설정이 설정 되어 있어야 합니다.<p>**오디오 기본값이** 로 설정 되어 있으면 `true` 이 설정이 무시 되 고 참가자가 마이크를 음소거 하거나 음소거 해제 할 수 있습니다.          |
| **비디오 기본값**      | 모임이 시작 될 때 카메라가 활성화 될 장치를 결정 합니다. 최상의 환경을 위해서는 다른 모든 장치를 설정 하는 동안 팀 대화방 장치만 설정 하는 것이 좋습니다 `true` `false` .          |
| **비디오 사용**      | 모임의 참가자가 카메라를 켜거나 끌 수 있는지 여부를 결정 합니다. `true`다른 비디오 관점 (예: 참가자가 Surface Hub 화이트 보드를 사용 하는 경우)을 공유 하려는 이벤트 참가자의 다른 모든 장치에서이를 설정할 수 있습니다. 참가자가 장치에서 카메라를 설정 하거나 해제 하지 못하게 하려면 다음을로 설정 `false` 합니다.<p> **비디오 기본값이** 로 설정 된 경우 `true` 이 설정은 무시 되며 참가자는 카메라를 켜거나 끌 수 있습니다.         |
| **화이트 보드 기본값** | 팀 대화방 장치가 모임 참가자 중 하 나와 공유한 화이트 보드를 표시할지 여부를 결정 합니다. Surface Hub를 보유 하 고 있지 않은 경우이를 설정 하는 것이 좋습니다 `false` `true` . Surface Hub에는이 설정이 적용 되지 않습니다. Surface Hub는 항상 모임 참가자가 공유한 화이트 보드를 표시 합니다.         |
| **신뢰할 수 있는 계정**   | 장치에서 모임 참가 요청을 수락 하거나 모임 참가 요청을 보내야 하는 각 팀 대화방 장치 또는 Surface Hub의 쉼표로 구분 된 목록입니다. |

그 다음 열에서 각 팀 객실 장치 및 Surface Hub를 추가 합니다. 각 열에서 회의실에 대해 원하는 환경에 맞는 값을 입력 합니다. 다음은 하나의 팀 대화방 장치와 하나의 Surface Hub를 사용 하는 예입니다.

- 팀 디바이스
  - 모임이 시작 **되 면 오디오 및 비디오가 켜 집니다** . 참가자는 오디오 및 비디오를 켜거나 끌 **수 있습니다** .
  - 공유 된 화이트 보드 표시 기능이 해제 되어 있습니다.
- Surface Hub
  - 모임이 시작 되 면 오디오가 **꺼집니다** . 참가자는 오디오를 켜거나 끌 **수 없습니다** .
  - 모임이 시작 되 면 비디오가 **꺼집니다** . 참가자는 비디오를 켜거나 끌 **수 있습니다** .

| 설정                | 팀 대화방      | Surface Hub      |
|------------------------|-----------------|------------------|
| **오디오 기본값**      | `true`          | `false`          |
| **오디오 사용**      | `true`          | `false`          |
| **비디오 기본값**      | `true`          | `false`          |
| **비디오 사용**      | `true`          | `true`           |
| **화이트 보드 기본값** | `false`         | 해당 사항 없음   |
| **신뢰할 수 있는 계정**   | hub@contoso.com | room@contoso.com |

## <a name="step-4-configure-teams-rooms-device"></a>4 단계: 팀 대화방 장치 구성

장치의 터치 화면을 사용 하 여 팀 대화방 장치에서 조정 된 모임을 설정 하거나, 여러 장치를 설정 해야 하는 경우 중앙 위치에서 수행 하려면 XML 구성 파일을 사용할 수 있습니다.

이전 단계에서 만든 워크시트를 사용 하 여 장치를 설정 하는 데 도움을 줍니다.

### <a name="use-the-teams-rooms-devices-touch-screen"></a>팀 회의실 장치의 터치 화면 사용

장치에서 조정 된 모임을 설정 하려면 다음을 수행 합니다.

1. 선택 **... 기타**  >  **설정**
2. 관리자 암호를 입력 하 고 **예** 를 선택 합니다.
3. **조정 모임** 선택
4. **옵션**에서 **조정 모임을** on으로 설정 합니다.
5. 워크시트의 **오디오 기본** 이 인 경우 `true` **이 디바이스의 마이크 켜기** 를 설정 하 고, 그렇지 않으면 종료
6. 워크시트에서 **오디오를 사용할 수** 있는 경우 `true` **사용자가** **이 디바이스의 마이크를 켜서**모임에 참가할 수 있도록 허용을 선택 합니다. **이 디바이스의 마이크가** on으로 설정 되어 있으면이 옵션을 끌 수 없습니다.
7. 워크시트에 **비디오 기본값이** 있는 경우 `true` **이 장치의 카메라** 설정을 켜 세요. 그렇지 않은 경우 종료 합니다.
8. 워크시트에서 **비디오를 사용 하도록 설정한** 경우 `true` **사용자가** **이 디바이스의 카메라를 켜서**모임에 참가할 수 있도록 허용을 선택 합니다. **이 장치 카메라가** 켜진 상태로 설정 되어 있으면이 옵션을 해제할 수 없습니다.
9. 워크시트의 **화이트 보드 default** 인 경우 `true` **이 장치에서 whiteboarding 켜기** 설정, 종료 하지 않음
10. **신뢰할 수 있는 디바이스 계정**에서 워크시트의 **신뢰할 수 있는 계정** 에 나열 된 각 UPN을 입력 합니다. 여러 Upn을 쉼표로 구분 합니다.
11. **저장 후 끝내기를** 선택 합니다.

**저장 후 종료**를 선택 하면 디바이스가 다시 시작 되 고 조정 된 모임에 참여할 준비가 됩니다.

### <a name="use-the-teams-rooms-xml-configuration-file"></a>팀 대화방 XML 구성 파일 사용

팀 대화방 장치의 XML 구성 파일을 사용 하 여 조정 된 모임을 설정할 수 있습니다 `SkypeSettings.xml` . `SkypeSettings.xml`파일이 정적 파일이 아닙니다. 팀 대화방 장치가 시작 되 면 이름이 지정 된 파일을 체크 인 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` `SkypeSettings.xml` 합니다. 파일이 있으면 장치에서 파일에 지정 된 구성을 읽고 적용 합니다. 구성 적용을 완료 하면 파일이 삭제 됩니다. 파일에 대 한 자세한 내용은 `SkypeSettings.xml` [XML 구성 파일을 사용 하 여 콘솔 설정 관리](../rooms/xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)를 참조 하세요.

다음은 구성 파일에서 조정 된 모임 설정의 구문입니다.

```xml
<CoordinatedMeetings enabled="true">
    <Settings>
        <Audio default="true" enabled="true"/>
        <Video default="true" enabled="true"/>
        <Whiteboard default="false"/>
    </Settings>
    <TrustedAccounts>hub@contoso.com</TrustedAccounts>
</CoordinatedMeetings>
```

장치에서 조정 된 모임을 설정 하려면 다음을 수행 합니다.

1. Visual Studio 코드나 메모장과 같은 텍스트 파일 편집기에서 위의 XML을 새 파일에 붙여 넣습니다.
2. 각 XML 요소를 `true` 스프레드시트의 해당 or 값으로 설정 합니다 `false` . 예를 들어, **오디오 기본값이** `true` 설정 된 경우 `<Audio default="true">`
3. Upn 목록으로 변경 해야 합니다. `TrustedAccounts`
4. 이름을 사용 하 여 파일 저장 `SkypeSettings.xml`
5. 파일을 팀 공간 장치의 폴더에 배치 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 합니다. 다음과 같은 몇 가지 방법으로이 작업을 수행할 수 있습니다.
    - **팀 대화방 장치에 파일 복사** 파일을 장치에 복사 하려면 먼저 파일 공유를 사용 하도록 설정 하 고 네트워크 공유를 만들어야 합니다. 이 작업을 수행한 후에는 네트워크 공유에 연결 하 고 파일을 장치에 복사할 수 있습니다. 자세한 내용은 [Microsoft 팀 대화방 유지 관리 및 운영](../rooms/rooms-operations.md)을 참조 하세요.
    - **그룹 정책 사용** 그룹 정책을 만들어 파일을 장치에 복사 합니다. 자세한 내용은 [그룹 정책 개요](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831791(v=ws.11))를 참조 하세요.
    - **팀 대화방 장치에서 파일 다운로드** 관리 모드를 사용 하 여 장치에 로그인 한 다음 네트워크 공유 또는 USB 드라이브에서 파일을 장치에 복사할 수 있습니다. 자세한 내용은 [관리 모드로 전환을](../rooms/rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)참조 하세요.
6. 장치를 다시 시작 합니다. 다음과 같은 몇 가지 방법으로이 작업을 수행할 수 있습니다.
    - **원격 PowerShell** 원격 PowerShell을 사용 하 여 장치에서 종료 명령을 실행할 수 있습니다. 자세한 내용은 [PowerShell을 사용 하 여 원격 관리](../rooms/rooms-operations.md)를 참조 하세요.
    - **컴퓨터 다시 시작** `Restart-Computer` 로컬 컴퓨터에서 cmdlet을 실행 하 고 다시 시작 하려는 장치의 컴퓨터 이름을 지정할 수 있습니다. 자세한 내용은 [컴퓨터 다시 시작](https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-7)을 참조 하세요.

## <a name="step-5-configure-surface-hub"></a>5 단계: Surface Hub 구성

Windows 구성 디자이너를 사용 하 여 Surface Hub에 조정 모임 설정을 적용 하는 데 사용할 수 있는 프로비저닝 패키지를 만들 수 있습니다. Windows 구성 디자이너에 만든 XML 파일을 붙여넣어 프로비저닝 패키지를 만듭니다.

### <a name="create-coordinated-meetings-xml-configuration-file-for-surface-hub"></a>Surface Hub 용 통합 모임 만들기 XML 구성 파일

Windows 구성 디자이너와 Microsoft Intune은 모두 Surface Hub에 조정 된 모임 구성을 적용 하는 데 사용 됩니다. 이 구성은 XML을 사용 하 여 정의 됩니다. 계속 진행 하기 전에 적용 되는 XML을 만들어야 합니다.

다음은 통합 된 모임 XML 구성 파일의 구문입니다.

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

Windows 용 XML 구성 디자이너 또는 Microsoft Intune을 준비 하려면 다음을 실행 합니다.

1. Visual Studio 코드나 메모장과 같은 텍스트 파일 편집기에서 위의 XML을 새 파일에 붙여 넣습니다.
2. 각 XML 요소를 `true` 스프레드시트의 해당 or 값으로 설정 합니다 `false` . 예를 들어, **오디오 기본값이** `true` 설정 된 경우 `<Audio default="true">`
3. Upn 목록으로 변경 해야 합니다. `TrustedAccounts`
4. Windows 구성 디자이너에서는 XML이 한 줄에 있어야 합니다. XML이 다음과 같이 표시 되도록 각 줄 사이의 줄 바꿈을 모두 제거 합니다.

    ```xml
    <SurfaceHubSettings><BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>...
    ```

5. 컴퓨터에 파일 저장

XML 구성 파일을 만든 후 [Surface Hub에서 Microsoft 팀 설정 관리](surface-hub-manage-config.md) 의 단계를 사용 하 여 surface Hubs에 적용 합니다.