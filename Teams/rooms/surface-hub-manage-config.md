---
title: Surface Hub에서 Microsoft Teams 구성 관리
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
description: Microsoft Intune 및 Windows 구성 디자이너를 사용하여 Surface Hub에서 Microsoft Teams 설정 관리
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761452"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Surface Hub에서 Microsoft Teams 설정 관리

Microsoft Endpoint Manager에서 Windows 구성 디자이너 또는 Microsoft Intune을 사용하여 Surface Hub에서 Microsoft Teams 설정을 관리할 수 있습니다. Teams 설정을 변경하려면 Windows 구성 디자이너 또는 Microsoft Intune에 대한 지식이 필요합니다. 이러한 옵션에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Windows 10용 프로비전 패키지 만들기](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [Microsoft Intune 디바이스 관리란?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

Windows 구성 디자이너는 Surface Hub 디바이스가 몇 개만 있으며 쉽게 액세스할 수 있는 경우 좋은 옵션입니다. Surface Hub가 많거나 원격 위치에 있는 경우 조직에 배포된 경우 Microsoft Endpoint Manager에서 Microsoft Intune을 사용합니다. 선택한 방법에 관계없이 Surface Hub에서 Teams 설정을 변경하려면 XML 구성 파일을 만들어야 합니다.

## <a name="teams-configuration-file-syntax"></a>Teams 구성 파일 구문

Surface Hub의 Teams 구성은 XML 파일을 사용하여 정의됩니다. XML 파일에는 Teams 작동 방법을 제어하는 데 사용할 수 있는 모든 설정이 포함되어 있습니다. Windows 구성 디자이너와 Microsoft Intune 모두 동일한 XML 구문을 사용 합니다. Teams 구성 XML 파일의 예는 다음과 같습니다.

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

다음 표에서는 구성 파일에서 사용할 수 있는 모든 구성 설정을 설명하고 있습니다.

| 부모                  | 요소                                   | 특성 | 설명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 없음                    | `<SurfaceHubSettings>`                    |           | Surface Hub의 Teams 구성에 대한 모든 구성 요소를 포함 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Surface Hub가 네트워크 연결에 사용할 수 있도록 광고하는지 Bluetooth 확인합니다.<br>허용되는 `true` 값: `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Teams에서 근접성 기반 모임을 자동으로 수락할지 여부를 판단합니다.<br>허용되는 `true` 값: `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 조정된 모임에 대한 모든 구성 요소를 포함 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Teams가 다른 장치와의 협정 모임에 참가하도록 구성되어 있는지 여부를 판단합니다.<br>허용되는 `true` 값: `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 이 목록은 장치가 모임 참가 요청을 수락해야 하는 각 Teams 회의실 장치 또는 Surface Hub에 대한 콤마로 구분된 UPNS 목록입니다.<br>허용되는 값: string                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 조정된 모임에 대한 구성 오디오 및 비디오 구성 요소를 포함                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Surface Hub에서 Teams에 대한 오디오 구성을 제어합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임이 시작될 때 마이크가 활성화될 장치를 확인합니다. 하나의 장치(일반적으로 Teams 회의실 장치)만 이 필드를 설정할 수 있는 반면 나머지 디바이스는 오디오 에코 및 피드백을 피하기 위해 이 필드를 `true` `false` 설정해야 합니다.<br>허용되는 `true` 값: `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 모임 참가자가 마이크를 설정 또는 해제할 수 있는지 여부를 확인합니다. 오디오 **기본값이** 설정되어 있는 장치에는 참가자가 실수로 마이크를 켜고 오디오 에코 또는 피드백을 유발하지 않도록 이 설정을 `false` `false` 설정해야 합니다.<p>오디오 **기본값이** 설정되어 있는 경우 이 설정은 무시되고 참가자는 마이크를 음소거하거나 `true` 음소거를 음소거할 수 있습니다.<br>허용되는 `true` 값: `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Surface Hub에서 Teams에 대한 비디오 구성을 제어합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임을 시작할 때 카메라가 활성화될 장치를 확인합니다. 최상의 환경을 위해 다른 모든 장치가 설정된 동안 Teams 회의실 `true` 장치만 설정하는 것이 `false` 좋습니다.<br>허용되는 `true` 값: `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 모임 참가자가 카메라를 설정 또는 해제할 수 있는지 여부를 판단합니다. 참가자가 다른 비디오 관점을 공유하려는 경우(예: 참가자가 Surface Hub 화이트보드를 사용하는 경우) 다른 모든 장치에서 설정할 `true` 수 있습니다. 참가자가 장치에서 카메라를 켜거나 끄지 못하게 하려는 경우 이 기능을 으로 `false` 설정하세요.<p> 비디오 **기본값이** 설정되어 있는 경우 이 설정은 무시되고 참가자는 카메라를 `true` 켜거나 끄면 됩니다.<br>허용되는 `true` 값: `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Surface Hub에 Teams 설정 적용

Microsoft Endpoint Manager에서 Windows 구성 디자이너 또는 Microsoft Intune을 사용하여 Surface Hub에서 Teams 구성 설정을 적용하거나 업데이트합니다.

### <a name="use-windows-configuration-designer"></a>Windows 구성 디자이너 사용

Windows 구성 디자이너를 사용하여 Teams 설정을 Surface Hub에 적용하는 데 사용할 수 있는 프로비전 패키지를 만들 수 있습니다. 위에서 만든 XML 파일을 Windows 구성 디자이너에 붙여넣어 프로비전 패키지를 만들게 됩니다.

> [!IMPORTANT]
> 프로비전 패키지를 사용하여 Surface Hub에 Teams 구성을 이미 적용한 경우 이를 변경하려면 먼저 기존 프로비전 패키지를 제거해야 합니다. 자세한 내용은 Windows 구성 디자이너에서 만든 프로비전 패키지 [제거를 참조하세요.](#remove-a-provisioning-package-created-by-windows-configuration-designer)

다음을 실행하여 Windows 구성 디자이너에서 프로비전 패키지를 만들 수 있습니다.

1. 로컬 컴퓨터의 Windows 스토어에서 Windows 구성 디자이너 설치 및 열기
2. **Surface Hub 디바이스** 프로비전을 선택한 다음 고급 편집기로 **전환**
3. 다음 화면에서 **WindowsTeamSettings**  >  **Teams를 확장하고** **구성을 선택합니다.**
4. 가운데 창의  구성 옆에 있는 필드에 위에서 만든 XML의 한 줄을 붙여넣습니다.
5.   >  **프로비전 패키지 내보내기 선택**
6. 이름에서 프로비전 패키지의  이름을 제공하고 **다음을**  >  **선택합니다.**
7. 프로비전 패키지를 저장할 위치를 지정하고 **다음을 선택합니다.**
8. **빌드를** 선택하여 프로비전 패키지를 만든 다음 마쳤습니다. 

마지막으로 프로비전 패키지를 만든 후 다음을 통해 프로비전 패키지를 Surface Hub에 적용합니다.

1. 위에서 만든 프로비전 패키지를 USB 드라이브에 저장
2. Surface Hub에 USB 드라이브 삽입
3. Surface Hub에서 시작 메뉴를 열고 모든 앱을 선택한 다음 **설정을** **선택합니다.**
4. 관리자 사용자 이름 및 암호를 입력한 다음 예 **선택**
5. Surface **Hub,** **디바이스 관리,** 프로비전 패키지 추가 또는 **제거로** 이동한 다음 패키지 **추가**
6. 패키지 **선택에서** 프로비전 패키지 옆에 추가를 선택한 다음 Surface Hub를 다시 시작합니다. 

### <a name="use-microsoft-intune"></a>Microsoft Intune 사용

Microsoft Endpoint Management에서 Microsoft Intune을 사용하여 Surface Hub를 관리하는 경우 이를 사용하여 Surface Hubs에 Teams 설정을 적용할 수 있습니다. 새 구성 프로필을 만든 다음 위에서 만든 XML 파일을 붙여넣습니다.

> [!IMPORTANT]
> Microsoft Intune에서 구성 프로필을 적용할 디바이스를 식별할 수 있도록 Surface Hub가 디바이스 그룹에 있을 수 있습니다. 디바이스 그룹을 만드는 방법에 대한 자세한 내용은 사용자 및 디바이스를 구성하는 그룹 [추가를 참조하세요.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

다음을 통해 Surface Hubs에 Teams 설정을 적용하는 구성 프로필을 만들 수 있습니다.

1. 방문하여 Microsoft Endpoint Manager에 로그인 https://endpoint.microsoft.com/
2. **디바이스** 구성  >  **프로필로 이동하고** 프로필 **만들기 선택**
3. 플랫폼에서 **Windows 10 이상 선택** 
4. **프로필에서** 사용자 **지정을** 선택한 다음 **만들기를 클릭합니다.**
5. 기본 **탭의** **이름에서** 구성 프로필에 대한 설명이 있는 이름을 입력하고 **다음을 선택합니다.**
6. 구성 설정 **탭에서** 추가 **선택**
7. 행 **추가 창에서** 다음을 합니다.
    1. 설명이 필요한 이름 및 선택적으로 추가하는 Teams 설정에 대한 설명을 제공합니다.
    2. **OMA-URI에서**`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. 데이터 **형식에서** **문자열(XML 파일)을 선택합니다.**
    4. 파일 브라우저를 열고 위에서 만든 XML 파일을 선택한 다음 **열기**
8. 추가 **및** 다음 **선택**
9. 과제 **탭에서** 할당을  선택한 그룹으로 **설정해야 합니다.**
10. 선택한 **그룹에서**  포함할 그룹 선택을 선택하고 Surface Hub가 포함된 그룹을  선택한 다음
11. **다음,** **다음 선택**
12. 검토 **+ 만들기에서** 만들기 **선택**

## <a name="remove-teams-settings-from-a-surface-hub"></a>Surface Hub에서 Teams 설정 제거

Microsoft Endpoint Manager에서 Windows 구성 디자이너 또는 Microsoft Intune을 사용하여 Surface Hub에서 Teams 구성 설정을 제거합니다.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Windows 구성 디자이너에서 만든 프로비전 패키지 제거

Windows 구성 디자이너에서 만든 프로비전 패키지를 사용하여 Surface Hub에 Teams 설정을 적용한 경우 다음 단계를 사용하여 패키지 및 해당 설정을 제거합니다.

1. Surface Hub에서 시작 메뉴를 열고 모든 앱을 선택한 다음 **설정을** **선택합니다.**
2. 관리자 사용자 이름 및 암호를 입력한 다음 예 **선택**
3. Surface **Hub,** 디바이스 **관리로** 이동한 다음 프로비전 패키지 추가 **또는 제거**
4. 제거하려는 프로비전 패키지 옆에 있는 **제거를 선택합니다.**
5. Surface **Hub로 이동한** 다음 앱 & **이동**
6. **Surface Hub용 Microsoft Teams를 찾은** 다음 고급 **옵션 선택**
7. 다시 **설정** 및 **다시** 설정 선택
8. Surface Hub 다시 시작

### <a name="remove-settings-applied-by-microsoft-intune"></a>Microsoft Intune에서 적용한 설정 제거

Microsoft Endpoint Management에서 Microsoft Intune을 사용하여 Surface Hub에 Teams 설정을 적용한 경우 다음 단계를 사용하여 구성 프로필 및 해당 설정을 제거합니다.

1. 방문하여 Microsoft Endpoint Manager에 로그인 https://endpoint.microsoft.com/
2. **디바이스** 구성  >  **프로필로 이동**
3. 제거하려는 조정된 모임 설정이 포함된 구성 프로필 선택
4. 구성 프로필 세부 정보 페이지에서 **삭제를** 선택한 다음 **확인을 선택합니다.**

Surface Hub에 대한 조정된 모임 설정이 포함된 구성 프로필을 제거한 후 다음 단계를 사용하여 Surface Hub에서 Teams 앱을 다시 설정합니다.

1. Surface Hub에서 시작 메뉴를 열고 모든 앱을 선택한 다음 **설정을** **선택합니다.**
2. 관리자 사용자 이름 및 암호를 입력한 다음 예 **선택**
3. Surface **Hub로 이동한** 다음 앱 & **이동**
4. **Surface Hub용 Microsoft Teams를 찾은** 다음 고급 **옵션 선택**
5. 다시 **설정** 및 **다시** 설정 선택
6. Surface Hub 다시 시작