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
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Microsoft Intune 및 Windows 구성 디자이너를 사용하여 Surface Hub에서 Microsoft Teams 설정 관리
ms.openlocfilehash: 6e99922ebb7bb30db1b5e94fd1a4d30b8ec653b8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272213"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Surface Hub에서 Microsoft Teams 설정 관리

Windows 구성 디자이너 또는 Microsoft Endpoint Manager Microsoft Intune 사용하여 Surface Hub에서 Microsoft Teams 설정을 관리할 수 있습니다. Teams 설정을 변경하려면 Windows 구성 디자이너 또는 Microsoft Intune 대한 지식이 필요합니다. 이러한 옵션에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Windows 10 대한 프로비저닝 패키지 만들기](/windows/configuration/provisioning-packages/provisioning-create-package)
- [Microsoft Intune 디바이스 관리란?](/mem/intune/remote-actions/device-management)

몇 개의 Surface Hub 디바이스만 있고 쉽게 액세스할 수 있는 경우 Windows 구성 디자이너가 좋은 옵션입니다. Surface Hub가 많거나 원격 위치에 있는 경우 조직에 배포된 경우 Microsoft Endpoint Manager Microsoft Intune 사용합니다. 선택한 방법에 관계없이 Surface Hub에서 Teams 설정을 변경하려면 XML 구성 파일을 만들어야 합니다.

## <a name="teams-configuration-file-syntax"></a>Teams 구성 파일 구문

Surface Hub의 Teams 구성은 XML 파일을 사용하여 정의됩니다. XML 파일에는 Teams 작동 방식을 제어하는 데 사용할 수 있는 모든 설정이 포함되어 있습니다. Windows 구성 디자이너와 Microsoft Intune 모두 동일한 XML 구문을 사용합니다. Teams 구성 XML 파일의 예는 다음과 같습니다.

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

| 부모                  | 요소                                   | 특성 | 설명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 없음                    | `<SurfaceHubSettings>`                    |           | Surface Hub의 Teams 구성에 대한 모든 구성 요소를 포함합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Surface Hub가 Bluetooth 연결에 사용할 수 있음을 보급하는지 여부를 결정합니다.<br>허용되는 값: `true``false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | Teams에서 근접 기반 모임을 자동으로 수락할지 여부를 결정합니다.<br>허용되는 값: `true``false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 조정된 모임에 대한 모든 구성 요소를 포함합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | Teams가 다른 장치와 함께 조정된 모임에 참여하도록 구성되었는지 여부를 결정합니다.<br>허용되는 값: `true``false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 각 Teams 룸 디바이스 또는 Surface Hub에 대해 쉼표로 구분된 UPN 목록으로, 디바이스가 모임 참가 요청을 수락해야 하거나 모임 참가 요청을 보내야 합니다.<br>허용되는 값: 문자열                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 조정된 모임에 대한 구성 오디오 및 비디오 구성 요소를 포함합니다.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Surface Hub에서 Teams의 오디오 구성을 제어합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임이 시작될 때 마이크가 활성화될 디바이스를 결정합니다. 하나의 디바이스(일반적으로 Teams 룸 디바이스)만 이 필드를 설정할 `true` 수 있지만 나머지 디바이스는 오디오 에코 및 피드백을 방지하기 위해 `false` 이 필드를 설정해야 합니다.<br>허용되는 값: `true``false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 모임 참가자가 마이크를 켜거나 끌 수 있는지 여부를 결정합니다. **오디오 기본값** 이 설정된 `false` 디바이스는 참가자가 실수로 마이크를 `false` 켜고 오디오 에코 또는 피드백을 발생시킬 수 없도록 이 설정을 설정해야 합니다.<p>**오디오 기본값** 이 설정된 `true`경우 이 설정은 무시되며 참가자는 마이크를 음소거하거나 음소거 해제할 수 있습니다.<br>허용되는 값: `true``false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Surface Hub에서 Teams에 대한 비디오 구성을 제어합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임이 시작될 때 카메라가 활성화될 디바이스를 결정합니다. 최상의 환경을 위해 다른 모든 디바이스가 설정된 동안 Teams 룸 디바이스만 설정하는 `true` `false`것이 좋습니다.<br>허용되는 값: `true``false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 모임 참가자가 카메라를 켜거나 끌 수 있는지 여부를 결정합니다. 참가자가 Surface Hub 화이트보드를 `true` 사용하는 경우와 같이 다른 비디오 관점을 공유하려는 이벤트 참가자의 다른 장치에서 이 설정을 지정할 수 있습니다. 참가자가 디바이스에서 카메라를 켜거나 끄지 않도록 하려면 이 옵션을 설정하세요 `false`.<p> **비디오 기본값** 이 설정된 `true`경우 이 설정은 무시되며 참가자는 카메라를 켜거나 끌 수 있습니다.<br>허용되는 값: `true``false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Surface Hub에 Teams 설정 적용

Microsoft Endpoint Manager Windows 구성 디자이너 또는 Microsoft Intune 사용하여 Surface Hub에서 Teams 구성 설정을 적용하거나 업데이트합니다.

### <a name="use-windows-configuration-designer"></a>Windows 구성 디자이너 사용

Windows 구성 디자이너를 사용하여 Surface Hubs에 Teams 설정을 적용하는 데 사용할 수 있는 프로비저닝 패키지를 만들 수 있습니다. 위에서 만든 XML 파일을 Windows 구성 디자이너에 붙여넣어 프로비전 패키지를 만듭니다.

> [!IMPORTANT]
> 프로비전 패키지를 사용하여 Surface Hub에 Teams 구성을 이미 적용하고 변경하려는 경우 먼저 기존 프로비저닝 패키지를 제거해야 합니다. 자세한 내용은 [Windows 구성 디자이너에서 만든 프로비저닝 패키지 제거를 참조하세요](#remove-a-provisioning-package-created-by-windows-configuration-designer).

Windows 구성 디자이너에서 프로비저닝 패키지를 만들려면 다음을 수행합니다.

1. 로컬 컴퓨터의 Windows 스토어에서 Windows 구성 디자이너를 설치하고 엽니다.
2. **Surface Hub 디바이스 프로비저닝** 을 선택한 다음 **고급 편집기로 전환**
3. 다음 화면에서 **WindowsTeamSettings Teams를** >  확장하고 **구성을 선택합니다.**
4. 가운데 창의 **구성** 옆에 있는 필드에 위에서 만든 XML의 한 줄을 붙여넣습니다.
5. **프로비저닝 패키지** **내보내기** >  선택
6. **이름** 에서 프로비저닝 패키지의 이름을 입력하고 **다음을** >  선택합니다.
7. 프로비전 패키지를 저장할 위치를 지정하고 **다음** 을 선택합니다.
8. **빌드** 를 선택하여 프로비저닝 패키지를 만든 다음 **마침**

마지막으로 프로비저닝 패키지를 만든 후 다음을 수행하여 Surface Hub에 프로비저닝 패키지를 적용합니다.

1. 위에서 만든 프로비저닝 패키지를 USB 드라이브에 저장
2. Surface Hub에 USB 드라이브 삽입
3. Surface Hub에서 시작 메뉴를 열고 **모든 앱을** 선택한 다음 **설정을** 선택합니다.
4. 관리자 사용자 이름 및 암호를 입력하고 **[예**]를 선택합니다.
5. **Surface Hub**, **디바이스 관리**, **프로비저닝 패키지 추가 또는 제거** 로 이동한 다음 **패키지 추가**
6. **패키지 선택에서** 프로비전 패키지 옆에 **추가** 를 선택한 다음 Surface Hub를 다시 시작합니다.

### <a name="use-microsoft-intune"></a>Microsoft Intune 사용

Microsoft Endpoint Management에서 Microsoft Intune 사용하여 Surface Hub를 관리하는 경우 이를 사용하여 Surface Hub에 Teams 설정을 적용할 수 있습니다. 새 구성 프로필을 만든 다음 위에서 만든 XML 파일을 붙여넣습니다.

> [!IMPORTANT]
> Surface Hub는 Microsoft Intune 구성 프로필을 적용할 디바이스를 식별할 수 있도록 디바이스 그룹에 있어야 합니다. 디바이스 그룹을 만드는 방법에 대한 자세한 내용은 [사용자 및 디바이스를 구성하는 그룹 추가를 참조하세요](/mem/intune/fundamentals/groups-add).

다음을 수행하여 Surface Hubs에 Teams 설정을 적용하는 구성 프로필을 만듭니다.

1. 방문하여 Microsoft Endpoint Manager 로그인https://endpoint.microsoft.com/
2. **디바이스** > **구성 프로필** 로 이동하고 **프로필 만들기** 를 선택합니다.
3. **플랫폼** 아래에서 **Windows 10 이상을** 선택합니다.
4. **프로필** 에서 **사용자 지정** 을 선택한 다음 **만들기** 를 클릭합니다.
5. **기본 사항** 탭의 **이름** 에서 구성 프로필에 대한 설명이 포함된 이름을 입력하고 **다음** 을 선택합니다.
6. **구성 설정** 탭에서 **추가** 를 선택합니다.
7. **행 추가** 창에서 다음을 수행합니다.
    1. 설명이 포함된 이름과 추가하려는 Teams 설정에 대한 설명(선택 사항)을 제공합니다.
    2. **OMA-URI** 에서`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. **데이터 형식** 에서 **문자열(XML 파일)** 을 선택합니다.
    4. 파일 브라우저를 열고 위에서 만든 XML 파일을 선택한 다음 **열기**
8. **추가** 를 선택한 다음 **, 다음** 을 선택합니다.
9. 할당 탭에서 **할당** 이 **선택한 그룹으로** 설정되어 있는지 확인 **합니다**.
10. **선택한 그룹에서** **포함할 그룹 선택을** 선택하고 Surface Hub가 포함된 그룹을 선택한 다음 선택을 **선택합니다**.
11. **다음**, **다음** 선택
12. **검토 + 만들기** 에서 **만들기** 를 선택합니다.

## <a name="remove-teams-settings-from-a-surface-hub"></a>Surface Hub에서 Teams 설정 제거

Microsoft Endpoint Manager Windows 구성 디자이너 또는 Microsoft Intune 사용하여 Surface Hub에서 Teams 구성 설정을 제거합니다.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Windows 구성 디자이너에서 만든 프로비저닝 패키지 제거

Windows 구성 디자이너에서 만든 프로비저닝 패키지를 사용하여 Surface Hub에 Teams 설정을 적용한 경우 다음 단계를 사용하여 패키지 및 해당 설정을 제거합니다.

1. Surface Hub에서 시작 메뉴를 열고 **모든 앱을** 선택한 다음 **설정을** 선택합니다.
2. 관리자 사용자 이름 및 암호를 입력하고 **[예**]를 선택합니다.
3. **Surface Hub**, **디바이스 관리** 로 이동한 다음 **프로비저닝 패키지 추가 또는 제거**
4. 제거하려는 프로비저닝 패키지 옆에 있는 **제거** 를 선택합니다.
5. **Surface Hub** 로 이동한 다음 **앱 & 기능**
6. **Surface Hub용 Microsoft Teams를** 찾은 다음 **고급 옵션을** 선택합니다.
7. **다시 설정을** 선택한 다음 다시 **설정**
8. Surface Hub 다시 시작

### <a name="remove-settings-applied-by-microsoft-intune"></a>Microsoft Intune 적용된 설정 제거

Microsoft Endpoint Management에서 Microsoft Intune 사용하여 Surface Hub에 Teams 설정을 적용한 경우 다음 단계를 사용하여 구성 프로필 및 해당 설정을 제거합니다.

1. 방문하여 Microsoft Endpoint Manager 로그인https://endpoint.microsoft.com/
2. **디바이스** > **구성 프로필로** 이동
3. 제거할 조정된 모임 설정이 포함된 구성 프로필을 선택합니다.
4. 구성 프로필 세부 정보 페이지에서 **삭제** 를 선택한 다음 **확인을** 선택합니다.

Surface Hub에 대한 조정된 모임 설정이 포함된 구성 프로필을 제거한 후 다음 단계를 사용하여 Surface Hub에서 Teams 앱을 다시 설정합니다.

1. Surface Hub에서 시작 메뉴를 열고 **모든 앱을** 선택한 다음 **설정을** 선택합니다.
2. 관리자 사용자 이름 및 암호를 입력하고 **[예**]를 선택합니다.
3. **Surface Hub** 로 이동한 다음 **앱 & 기능**
4. **Surface Hub용 Microsoft Teams를** 찾은 다음 **고급 옵션을** 선택합니다.
5. **다시 설정을** 선택한 다음 다시 **설정**
6. Surface Hub 다시 시작
