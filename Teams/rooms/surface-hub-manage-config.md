---
title: Surface Hub에서 Microsoft 팀 구성 관리
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
description: Microsoft Intune 및 Windows 구성 디자이너를 사용 하 여 Surface Hub의 Microsoft 팀 설정 관리
ms.openlocfilehash: 3e254d7f7afbd918e8279d2dc7b100ebbfdc3daf
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761452"
---
# <a name="manage-microsoft-teams-settings-on-surface-hub"></a>Surface Hub에서 Microsoft 팀 설정 관리

Microsoft Endpoint Manager에서 Windows 구성 디자이너 또는 Microsoft Intune을 사용 하 여 Surface Hub의 Microsoft 팀 설정을 관리할 수 있습니다. 팀 설정을 변경 하려면 Windows 구성 디자이너나 Microsoft Intune에 대 한 지식이 필요 합니다. 이러한 옵션에 대 한 자세한 내용은 다음 문서를 참조 하세요.

- [Windows 10 용 프로비저닝 패키지 만들기](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)
- [Microsoft Intune 장치 관리 란?](https://docs.microsoft.com/mem/intune/remote-actions/device-management)

Windows 구성 디자이너는 Surface Hub 장치만 있고 쉽게 액세스할 수 있는 경우에 적합 한 옵션입니다. Surface Hub가 많이 있거나 원격 위치에 있는 경우 조직에서 microsoft Intune Manager를 사용 하 여 배포 하는 경우 선택한 방법에 관계 없이 Surface Hub에서 팀 설정을 변경할 수 있도록 XML 구성 파일을 만들어야 합니다.

## <a name="teams-configuration-file-syntax"></a>팀 구성 파일 구문

Surface Hub의 팀 구성은 XML 파일을 사용 하 여 정의 됩니다. XML 파일에는 팀의 작동 방식을 제어 하는 데 사용할 수 있는 모든 설정이 포함 되어 있습니다. Windows 구성 디자이너와 Microsoft Intune은 모두 동일한 XML 구문을 사용 합니다. 다음은 팀 구성 XML 파일의 예입니다.

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

다음 표에서는 구성 파일에서 사용할 수 있는 모든 구성 설정에 대해 설명 합니다.

| 부모                  | 요소                                   | 특성 | 설명                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|-------------------------|-------------------------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 없음                    | `<SurfaceHubSettings>`                    |           | Surface Hub의 팀 구성에 대 한 모든 구성 요소를 포함 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<SurfaceHubSettings>`  | `<BluetoothAdvertisementEnabled>`         |           | Surface Hub가 Bluetooth 연결에 사용할 수 있도록 알리는 지 여부를 결정 합니다.<br>허용 값: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                         |
| `<SurfaceHubSettings>`  | `<AutoAcceptProximateMeetingInvitations>` |           | 팀이 근접 기반 모임을 자동으로 수락 하는지 여부를 결정 합니다.<br>허용 값: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<SurfaceHubSettings>`  | `<CoordinatedMeetings>`                   |           | 조정 된 모임의 모든 구성 요소를 포함 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|                         |                                           | `enabled` | 팀이 다른 장치와의 통합 된 모임에 참가 하도록 구성 되었는지 여부를 결정 합니다.<br>허용 값: `true` , `false`                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>` | `<TrustedAccounts>`                       |           | 장치에서 모임 참가 요청을 수락 하거나 모임 참가 요청을 보내야 하는 각 팀 대화방 장치 또는 Surface Hub의 쉼표로 구분 된 목록입니다.<br>허용 값: 문자열                                                                                                                                                                                                                                                                                                                         |
| `<CoordinatedMeetings>` | `<Settings>`                              |           | 조정 된 모임에 대 한 구성 오디오 및 비디오 구성 요소가 포함 되어 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<Settings>`            | `<Audio>`                                 |           | Surface Hub의 팀에 대 한 오디오 구성을 제어 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임이 시작 될 때 마이크가 활성화 되는 장치를 결정 합니다. 장치 중 일부 (일반적으로 팀 대화방 장치)는 `true` `false` 오디오 에코 및 피드백을 방지 하기 위해이 필드를 설정 해야 하는 경우에만이 필드를 설정할 수 있습니다.<br>허용 값: `true` , `false`                                                                                                                                                                                                           |
|                         |                                           | `enabled` | 모임의 참가자가 마이크를 켜거나 끌 수 있는지 여부를 결정 합니다. **오디오를 기본적** 으로 설정 하는 장치는 `false` 참가자가 `false` 마이크를 실수로 켜고 오디오 반향 또는 피드백이 발생할 수 없도록이 설정이 설정 되어 있어야 합니다.<p>**오디오 기본값이** 로 설정 되어 있으면 `true` 이 설정이 무시 되 고 참가자가 마이크를 음소거 하거나 음소거 해제 할 수 있습니다.<br>허용 값: `true` , `false`                                                                               |
| `<Settings>`            | `<Video>`                                 |           | Surface Hub의 팀에 대 한 비디오 구성을 제어 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|                         |                                           | `default` | 모임이 시작 될 때 카메라가 활성화 될 장치를 결정 합니다. 최상의 환경을 위해서는 다른 모든 장치를 설정 하는 동안 팀 대화방 장치만 설정 하는 것이 좋습니다 `true` `false` .<br>허용 값: `true` , `false`                                                                                                                                                                                                                                                                  |
|                         |                                           | `enabled` | 모임의 참가자가 카메라를 켜거나 끌 수 있는지 여부를 결정 합니다. `true`다른 비디오 관점 (예: 참가자가 Surface Hub 화이트 보드를 사용 하는 경우)을 공유 하려는 이벤트 참가자의 다른 모든 장치에서이를 설정할 수 있습니다. 참가자가 장치에서 카메라를 설정 하거나 해제 하지 못하게 하려면 다음을로 설정 `false` 합니다.<p> **비디오 기본값이** 로 설정 된 경우 `true` 이 설정은 무시 되며 참가자는 카메라를 켜거나 끌 수 있습니다.<br>허용 값: `true` , `false` |

## <a name="apply-teams-settings-to-surface-hub"></a>Surface Hub에 팀 설정 적용

Microsoft Endpoint Manager에서 Windows 구성 디자이너 또는 Microsoft Intune을 사용 하 여 Surface Hub의 팀 구성 설정을 적용 하거나 업데이트 합니다.

### <a name="use-windows-configuration-designer"></a>Windows 구성 디자이너 사용

Windows 구성 디자이너를 사용 하 여 Surface Hub에 팀 설정을 적용 하는 데 사용할 수 있는 프로비저닝 패키지를 만들 수 있습니다. Windows 구성 디자이너에 만든 XML 파일을 붙여넣어 프로비저닝 패키지를 만듭니다.

> [!IMPORTANT]
> 이미 팀 구성을 배포 패키지를 사용 하 여 Surface Hub에 적용 한 경우 기존 배포 패키지를 먼저 제거 해야 합니다. 자세한 내용은 [Windows 구성 디자이너에서 만든 배포 패키지 제거](#remove-a-provisioning-package-created-by-windows-configuration-designer)를 참조 하세요.

Windows 구성 디자이너에서 배포 패키지를 만들려면 다음을 실행 합니다.

1. 로컬 컴퓨터의 Windows 스토어에서 Windows 구성 디자이너를 설치 하 고 엽니다.
2. **Surface Hub 디바이스 프로 비전** 을 선택한 다음 **고급 편집기로 전환**
3. 다음 화면에서 **WindowsTeamSettings**  >  **팀** 을 확장 하 고 **구성을** 선택 합니다.
4. 가운데 창의 **구성** 옆에 있는 필드에 앞에서 만든 XML의 한 줄을 붙여 넣습니다.
5. **Export**  >  **배포 패키지** 내보내기를 선택 합니다.
6. **이름** 에 프로비저닝 패키지의 이름을 입력 하 고 **다음**을 선택 합니다.  >  **Next**
7. 배포 패키지를 저장할 위치를 지정 하 고 **다음** 을 선택 합니다.
8. **빌드** 를 선택 하 여 프로비저닝 패키지를 만들고 **완료**

마지막으로 프로 비전 패키지를 만든 후 다음을 수행 하 여 Surface Hub에 프로비저닝 패키지를 적용 합니다.

1. 위에 만든 프로비저닝 패키지를 USB 드라이브에 저장
2. Surface Hub에 USB 드라이브를 삽입 합니다.
3. Surface Hub에서 시작 메뉴를 열고 **모든 앱**을 선택한 다음 **설정을** 선택 합니다.
4. 관리자 사용자 이름 및 암호를 입력 한 다음 **예** 를 선택 합니다.
5. **Surface Hub**, **장치 관리**, **프로비저닝 패키지 추가 또는 제거**로 이동한 다음 **패키지 추가**
6. **패키지 선택**에서 프로 비전 패키지 옆에 있는 **추가** 를 선택한 다음 Surface Hub를 다시 시작 합니다.

### <a name="use-microsoft-intune"></a>Microsoft Intune 사용

Microsoft Intune 관리에서 Surface Hub를 사용 하 여 관리 하는 경우에는이를 사용 하 여 Surface Hub에 팀 설정을 적용할 수 있습니다. 새 구성 프로필을 만든 다음 위에서 만든 XML 파일을 붙여넣습니다.

> [!IMPORTANT]
> Surface Hub는 장치 그룹에 있어야 Microsoft Intune이 구성 프로필을 적용할 장치를 식별할 수 있습니다. 장치 그룹을 만드는 방법에 대 한 자세한 내용은 [그룹 추가를 통해 사용자 및 장치 구성을](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)참조 하세요.

팀 설정을 Surface Hub에 적용 하는 구성 프로필을 만들려면 다음을 수행 합니다.

1. 방문 하 여 Microsoft Endpoint Manager에 로그인 https://endpoint.microsoft.com/
2. **장치**  >  **구성 프로필로** 이동 하 고 **프로필 만들기** 를 선택 합니다.
3. **플랫폼**에서 **Windows 10 이상을** 선택 합니다.
4. **프로필**에서 **사용자 지정**을 선택한 다음 **만들기** 를 클릭 합니다.
5. **기본** 탭의 **이름**에 구성 프로필에 대 한 설명 이름을 입력 하 고 **다음** 을 선택 합니다.
6. **구성 설정** 탭에서 **추가** 를 선택 합니다.
7. **행 추가** 창에서 다음을 수행 합니다.
    1. 설명적인 이름을 제공 하 고, 선택적으로 추가 하려는 팀 설정에 대 한 설명을 입력 하세요.
    2. **Oma-uri**에는 다음을 입력 합니다.`./Vendor/MSFT/SurfaceHub/InBoxApps/Teams/Configurations`
    3. **데이터 형식**에서 **문자열 (XML 파일)** 을 선택 합니다.
    4. 파일 브라우저를 열고 위에서 만든 XML 파일을 선택한 다음 **열기**
8. **추가** 를 선택 하 고 **다음** 을 클릭 합니다.
9. **과제** 탭에서 **지정 대상** **그룹이 선택 된 그룹** 으로 설정 되어 있는지 확인 합니다.
10. **선택한 그룹**에서 **포함할 그룹 선택을** 선택 하 고 Surface hub를 포함 하는 그룹을 선택한 다음 **선택을** 선택 합니다.
11. **다음**, **다음** 을 선택 합니다.
12. **검토 + 만들기**에서 **만들기** 를 선택 합니다.

## <a name="remove-teams-settings-from-a-surface-hub"></a>Surface Hub에서 팀 설정 제거

Microsoft Endpoint Manager에서 Windows 구성 디자이너 또는 Microsoft Intune을 사용 하 여 Surface Hub의 팀 구성 설정을 제거 합니다.

### <a name="remove-a-provisioning-package-created-by-windows-configuration-designer"></a>Windows 구성 디자이너에서 만든 배포 패키지 제거

Windows 구성 디자이너에서 만든 배포 패키지를 사용 하 여 팀 설정을 Surface Hub에 적용 한 경우 다음 단계를 사용 하 여 패키지 및 해당 설정을 제거 합니다.

1. Surface Hub에서 시작 메뉴를 열고 **모든 앱**을 선택한 다음 **설정을** 선택 합니다.
2. 관리자 사용자 이름 및 암호를 입력 한 다음 **예** 를 선택 합니다.
3. **Surface Hub**, **장치 관리** 로 이동 하 여 **프로비저닝 패키지 추가 또는 제거**
4. 제거 하려는 프로비저닝 패키지 옆에 있는 **제거** 를 선택 합니다.
5. **Surface Hub** 로 이동한 다음 **앱 & 기능** 으로 이동 합니다.
6. **Surface Hub 용 Microsoft 팀** 을 찾은 다음 **고급 옵션** 을 선택 합니다.
7. **다시 설정을**선택한 다음 다시 **설정** 합니다.
8. Surface Hub 다시 시작

### <a name="remove-settings-applied-by-microsoft-intune"></a>Microsoft Intune에서 적용 한 설정 제거

Microsoft Endpoint Management에서 Microsoft Intune을 사용 하 여 Surface Hub에 팀 설정을 적용 한 경우 다음 단계를 사용 하 여 구성 프로필 및 해당 설정을 제거 합니다.

1. 방문 하 여 Microsoft Endpoint Manager에 로그인 https://endpoint.microsoft.com/
2. **장치**  >  **구성 프로필로** 이동
3. 제거 하려는 조정 된 모임 설정이 포함 된 구성 프로필을 선택 합니다.
4. 구성 프로필 세부 정보 페이지에서 **삭제** 를 선택한 다음 **확인** 을 선택 합니다.

Surface Hub에 대 한 조정 된 모임 설정이 포함 된 구성 프로필을 제거한 후에 다음 단계를 사용 하 여 Surface Hub에서 팀 앱을 다시 설정 합니다.

1. Surface Hub에서 시작 메뉴를 열고 **모든 앱**을 선택한 다음 **설정을** 선택 합니다.
2. 관리자 사용자 이름 및 암호를 입력 한 다음 **예** 를 선택 합니다.
3. **Surface Hub** 로 이동한 다음 **앱 & 기능** 으로 이동 합니다.
4. **Surface Hub 용 Microsoft 팀** 을 찾은 다음 **고급 옵션** 을 선택 합니다.
5. **다시 설정을**선택한 다음 다시 **설정** 합니다.
6. Surface Hub 다시 시작