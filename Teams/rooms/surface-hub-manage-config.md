---
title: Microsoft Teams 구성 관리 Surface Hub
ms.author: czawideh
author: cazawideh
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
description: 구성 Microsoft Teams 및 Surface Hub 사용하여 Surface Hub 설정 Microsoft Intune Windows 관리
ms.openlocfilehash: a07751ebf601e665254c1dc6c83eb546592b2e28
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503925"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Microsoft Teams 설정 관리 Surface Hub

구성 디자이너 또는 Microsoft Teams 구성 디자이너를 사용하여 Surface Hub 설정 Windows Microsoft Intune Microsoft Endpoint Manager. 구성 Windows 또는 Microsoft Intune 설정을 변경하려면 Teams 지식이 필요합니다. 이러한 옵션에 대한 자세한 내용은 다음 문서를 참조하세요.

- [프로비전 패키지를 Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package)
- [디바이스 Microsoft Intune 무엇입니까?](/mem/intune/remote-actions/device-management)

Windows 구성 디자이너는 몇 대의 디바이스만 Surface Hub 쉽게 액세스할 수 있는 경우 좋은 옵션입니다. Surface Hubs가 많거나 원격 위치에 있는 경우 조직에 배포된 경우 Microsoft Intune Microsoft Endpoint Manager 사용하세요. 선택한 방법에 관계 없이 XML 구성 파일을 만들어 Teams 설정을 변경해야 Surface Hub.

## <a name="teams-configuration-file-syntax"></a>Teams 파일 구문

Teams 구성은 XML Surface Hub 사용하여 정의됩니다. XML 파일에는 작동 방법을 제어하는 데 사용할 수 있는 모든 Teams 있습니다. 구성 Windows 및 Microsoft Intune 동일한 XML 구문을 사용 합니다. 다음은 XML 구성 Teams 예제입니다.

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

다음 표에서는 구성 파일에서 사용할 수 있는 모든 구성 설정을 설명합니다.

| 상위                  | 요소                                   | 특성 | 설명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 없음                    | `<SurfaceHubSettings>`                    |           | 에 대한 모든 구성 Teams 구성 요소를 Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | 연결에 Surface Hub 광고할지 여부를 Bluetooth 합니다.<br>수락된 값: 입니다. `true``false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 근접 기반 Teams 자동으로 허용할지 여부를 결정합니다.<br>수락된 값: 입니다. `true``false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 조정된 모임에 대한 모든 구성 요소가 포함되어 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 다른 디바이스와 Teams 조정된 모임에 참가하도록 구성되는지 여부를 결정합니다.<br>수락된 값: 입니다. `true``false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 이 목록은 각 회의실 디바이스 또는 Teams 또는 디바이스에서 모임 조인 요청을 수락해야 하는 Surface Hub 또는 모임 조인 요청을 전송해야 하는 각 디바이스에 대해 콤마로 구분된 UPNS 목록입니다.<br>수락된 값: 문자열                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 조정된 모임에 대한 구성 오디오 및 비디오 구성 요소 포함                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | 오디오 구성을 Teams 오디오 구성을 Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임이 시작될 때 마이크가 활성화될 디바이스를 확인합니다. 하나의 디바이스(일반적으로 Teams 룸 디바이스)만 이 필드를 설정할 수 있으며, 나머지 디바이스에는 오디오 에코 및 피드백 `true` `false` 을 피하기 위해 이 필드가 설정되어 있어야 합니다.<br>수락된 값: 입니다. `true``false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 모임의 참가자가 마이크를 끄거나 해제할 수 있는지 여부를 확인합니다. 오디오 **기본값이** `false` `false` 설정되어 있는 디바이스는 참가자가 실수로 마이크를 켜고 오디오 에코 또는 피드백을 일으킬 수 있도록 이 설정을 설정해야 합니다.<p>**오디오 기본값이** 로 설정`true`되어 있는 경우 이 설정이 무시되고 참가자가 마이크를 음소거하거나 음소거할 수 있습니다.<br>수락된 값: 입니다. `true``false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | 비디오 구성을 Teams 비디오 구성을 Surface Hub.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임이 시작될 때 카메라가 활성화될 디바이스를 확인합니다. 최상의 환경을 위해 `true` 다른 모든 디바이스가 으로 Teams 룸 디바이스만 로 설정하는 것이 좋습니다`false`.<br>수락된 값: 입니다. `true``false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 모임의 참가자가 카메라를 설정하거나 해제할 수 있는지 여부를 결정합니다. 참가자가 `true` 다른 비디오 관점을 공유하려는 경우(예: 참가자가 화이트보드를 사용하는 경우)의 다른 디바이스에 Surface Hub 수 있습니다. 참가자가 디바이스에서 카메라를 켜거나 끄지 못하게 하려는 경우 으로 설정합니다 `false`.<p> 비디오 **기본값이** 로 설정 `true`되어 있는 경우 이 설정은 무시되고 참가자는 카메라를 켜거나 해제할 수 있습니다.<br>수락된 값: 입니다. `true``false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Teams 설정 적용 Surface Hub

구성 Teams 또는 Surface Hub 구성 디자이너를 사용하여 Windows 구성 설정을 Microsoft Intune Microsoft Endpoint Manager.

### <a name="use-windows-configuration-designer"></a>구성 Windows 사용

구성 디자이너 Windows 사용하여 Surface Hubs에 Teams 프로비전 패키지를 만들 수 있습니다. 위에서 만든 XML 파일을 프로비전 패키지를 Windows 구성 디자이너에 붙여넣습니다.

> [!IMPORTANT]
> 프로비전 패키지를 사용하여 Teams 구성을 Surface Hub 변경하려는 경우 먼저 기존 프로비전 패키지를 제거해야 합니다. 자세한 내용은 구성 디자이너에서 만든 프로비[전 Windows 참조하세요](#remove-a-provisioning-package-created-by-windows-configuration-designer).

구성 디자이너에서 프로비전 패키지를 만들 Windows 합니다.

1. 로컬 Windows 저장소에서 Windows 구성 디자이너를 설치하고 을 수 있습니다.
2. 디바이스 **Surface Hub 프로비전을 선택한** 다음 **고급 편집기로 전환**
3. 다음 화면에서 **WindowsTeamSettings** > 를 확장하고 **Teams** 구성을 **선택합니다.**
4. 중간 창의 **구성** 옆에 있는 필드에 위에서 만든 XML의 단일 줄을 붙여넣습니다.
5. **ExportProvisioning**  >  패키지 선택
6. 이름에서 프로비전 패키지의 이름을 제공하고 **NextNext**  >  를 선택합니다.
7. 프로비전 패키지를 저장할 위치를 지정하고 다음을 **선택합니다.**
8. 빌드 **를** 선택하여 프로비전 패키지를 만든 다음 마쳤 **습니다.**

마지막으로 프로비전 패키지를 만든 후 프로비전 패키지를 다음에 적용하여 프로비전 패키지를 Surface Hub.

1. 위에서 만든 프로비전 패키지를 USB 드라이브에 저장
2. USB 드라이브를 사용자 설정에 Surface Hub
3. 사용자 Surface Hub 열고, 시작 메뉴 모든 앱을 선택한 다음, 설정 
4. 관리자 사용자 이름 및 암호를 입력한 다음 예를 **선택합니다.**
5. Surface Hub **관리,** 프로비전 패키지 추가 또는 제거로 **이동한 다음** 패키지 **추가**
6. 패키지 **선택에서** 프로비전  패키지 옆에 추가를 선택한 다음, 패키지를 다시 Surface Hub

### <a name="use-microsoft-intune"></a>Microsoft Intune

Microsoft 엔드포인트 관리에서 Microsoft 엔드포인트 Microsoft Intune 사용하여 Surface Hubs를 관리하는 경우 이 설정을 사용하여 Surface Hubs에 Teams 수 있습니다. 새 구성 프로필을 만든 다음 위에 만든 XML 파일을 붙여넣습니다.

> [!IMPORTANT]
> Surface Hubs는 디바이스 그룹에 Microsoft Intune 구성 프로필을 적용할 디바이스를 식별할 수 있습니다. 디바이스 그룹을 만드는 방법에 대한 자세한 내용은 사용자 및 디바이스를 구성하는 그룹 추가 [를 참조하세요](/mem/intune/fundamentals/groups-add).

다음을 사용하여 Surface Hubs에 Teams 구성 프로필을 만들 수 있습니다.

1. 방문하여 Microsoft Endpoint Manager 로그인https://endpoint.microsoft.com/
2. **DevicesConfiguration**  >  프로필로 이동하고 프로필 **만들기를 선택합니다.**
3. 플랫폼 **에서** Windows 10 **이상을 선택합니다.**
4. 프로필 **에서** **사용자 지정** 을 선택한 다음 만들기 **를 클릭합니다.**
5. 기본 탭 **의** **이름** 에서 구성 프로필에 대한 설명 이름을 제공하고 다음을 **선택합니다.**
6. 구성 **설정 탭에서** 추가를 **선택합니다.**
7. 행 **추가** 창에서 다음을 합니다.
    1. 설명 이름 및 추가할 설정에 Teams 설명 제공
    2. **OMA-URI에서**`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 데이터 **형식에서** **문자열(XML 파일)을 선택합니다.**
    4. 파일 브라우저를 열고 위에서 만든 XML 파일을 선택하고 열 **기**
8. 추가 **를** 선택한 다음 **다음**
9. 과제 **탭에서** 할당을 선택한 **그룹으로** **설정되어 있는지 확인**
10. 선택한 **그룹에서** 포함할 그룹 선택을 **선택하고** Surface Hubs가 포함된 그룹을 선택한 다음 선택 **을 선택합니다**.
11. 다음 **,** **다음을 선택합니다.**
12. 검토 **+ 만들기에서** 만들기 **를 선택합니다.**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Teams 설정 제거 Surface Hub

구성 Teams 또는 Surface Hub 구성 디자이너를 사용하여 Windows 구성 설정을 Microsoft Intune Microsoft Endpoint Manager.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>구성 디자이너에서 만든 프로비전 Windows 제거

구성 디자이너에서 Teams 프로비전 패키지를 사용하여 Surface Hub 설정에 Windows 경우 다음 단계를 사용하여 패키지 및 해당 설정을 제거합니다.

1. 사용자 Surface Hub 열고, 시작 메뉴 모든 앱을 선택한 다음, 설정 
2. 관리자 사용자 이름 및 암호를 입력한 다음 예를 **선택합니다.**
3. Surface Hub **,** **디바이스** 관리로 이동한 다음 프로비전 패키지 추가 **또는 제거**
4. 제거할 프로비전 패키지 옆에 있는 제거를 **선택합니다.**
5. 앱 **Surface Hub** **다음 Apps & 기능으로 이동**
6. 자세한 **Microsoft Teams 찾기 Surface Hub** 고급 옵션을 **선택합니다.**
7. 재설정 **을** **선택한 다음 다시** 재설정을 선택합니다.
8. 다시 시작 Surface Hub

### <a name="remove-settings-applied-by-microsoft-intune"></a>사용자에 의해 적용된 Microsoft Intune

Microsoft 엔드포인트 Teams 사용하여 Surface Hub Microsoft Intune 설정에 적용한 경우 다음 단계를 사용하여 구성 프로필 및 해당 설정을 제거합니다.

1. 방문하여 Microsoft Endpoint Manager 로그인https://endpoint.microsoft.com/
2. **DevicesConfiguration**  >  프로필로 이동합니다.
3. 제거할 조정된 모임 설정이 포함된 구성 프로필 선택
4. 구성 프로필 세부 정보 페이지에서 삭제를 **선택한 다음** **확인을 선택합니다.**

사용자에 대한 조정 모임 설정이 포함된 구성 프로필을 제거한 Surface Hub 다음 단계를 사용하여 Teams 앱을 다시 Surface Hub.

1. 사용자 Surface Hub 열고, 시작 메뉴 모든 앱을 선택한 다음, 설정 
2. 관리자 사용자 이름 및 암호를 입력한 다음 예를 **선택합니다.**
3. 앱 **Surface Hub** **다음 Apps & 기능으로 이동**
4. 자세한 **Microsoft Teams 찾기 Surface Hub** 고급 옵션을 **선택합니다.**
5. 재설정 **을** **선택한 다음 다시** 재설정을 선택합니다.
6. 다시 시작 Surface Hub
