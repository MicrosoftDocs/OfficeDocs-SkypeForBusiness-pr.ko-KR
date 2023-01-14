---
title: Microsoft Teams 룸 관리
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 사용자가 Microsoft Teams 룸 시스템을 사용할 수 있도록 지속적인 유지 관리 및 작업을 개발하고 실행하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36145202e12cd9b987b50efd6de3efe636c86ac2
ms.sourcegitcommit: 1934c4803b5b6ae9b9ccd49e695944446d5d5810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2023
ms.locfileid: "69806373"
---
# <a name="manage-microsoft-teams-rooms-and-surface-hubs"></a>Microsoft Teams 룸 및 Surface Hub 관리

조직에 Microsoft Teams 룸 장치 또는 Surface Hub가 있는 경우 유연한 관리 옵션이 있습니다.  모든 Teams 솔루션인 Microsoft Teams 관리 센터를 관리하는 동일한 중앙 위치에서 디바이스를 직접 관리할 수 있습니다.

Microsoft Teams 관리 센터를 사용하면 다음을 수행할 수 있습니다.

- 디바이스 다시 시작 및 디바이스 로그 다운로드와 같은 디바이스 관리 수행
- Teams별 설정 적용
- 카메라, 디스플레이, 마이크 등 Microsoft Teams 룸 주변 장치 상태 확인
- 현재 및 과거 모임 활동(예: 통화 품질, 네트워크 상태 및 연결, 참가자 수에 대한 세부 정보)을 검토합니다.
- Microsoft Teams 룸 연결된 주변 장치(예: 카메라 및 프로젝터)를 참조하세요(Windows의 Teams 룸 경우에만).

Teams 룸 디바이스를 관리하려면 [Microsoft Teams 관리 센터를](https://admin.teams.microsoft.com) 열고 Windows 또는 **Surface Hubs** 의 **Teams 디바이스** > **Teams 룸** 로 이동합니다.

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams 관리 센터의 요약 페이지 Teams 룸.":::


> [!IMPORTANT]
> Teams 관리 센터를 사용하여 디바이스를 관리하려면 전역 관리자, Teams 관리자 또는 Teams 디바이스 관리자 역할이 할당되어야 합니다.

## <a name="make-changes-to-teams-rooms-devices-or-surface-hubs"></a>Teams 룸 디바이스 또는 Surface Hub를 변경합니다.

둘 이상의 Teams 룸 또는 Surface Hub 디바이스가 있는 경우 여러 디바이스에서 동시에 대부분의 작업을 수행할 수 있습니다. 예를 들어 모든 Teams 룸 Teams 앱 설정을 동시에 설정할 수 있습니다.

### <a name="device-settings"></a>디바이스 설정

조직에서 하나 이상의 Teams 룸 또는 Surface Hubs에 대한 설정을 변경할 수 있습니다. 설정을 변경하려면 관리하려는 디바이스 또는 디바이스를 선택한 다음 **설정 편집** 을 선택합니다. 변경할 수 있는 모든 설정이 포함된 새 창이 열립니다. 다음 표에서는 Teams 관리 센터를 사용하여 변경할 수 있는 설정을 나열합니다. 일부 설정은 단일 Teams 룸 선택하는 경우에만 사용할 수 있습니다.

둘 이상을 선택하는 경우 대량 편집을 지원하는 설정에는 다음 두 가지 옵션이 표시됩니다.

- **기존 값 유지** 이 옵션을 선택하면 선택한 Teams 룸 설정이 변경되지 않습니다.
- **기존 값을 로 바꾸기** 이 옵션을 선택하면 선택한 Teams 룸 설정을 제공한 값으로 업데이트할 수 있습니다.
    > [!CAUTION]
    > 업데이트하도록 선택한 설정의 기존 값이 사용자가 제공한 값으로 바뀝니다. 기존 값 목록에 추가하려면 기존 값을 추가할 값과 함께 포함해야 합니다. 예를 들어 설정에 의 기존 도메인 목록이 `contoso.com, fabrikam.com`있고 를 추가 `northwindtraders.com`하려는 경우 제공해야 하는 값은 입니다 `contoso.com, fabrikam.com, northwindtraders.com`.
    >
    > 여러 Teams 룸 선택하면 선택한 모든 디바이스의 설정이 사용자가 제공한 값으로 변경됩니다. Teams 룸 설정에 대한 값이 다른 경우 모두 동일한 값으로 업데이트됩니다.

| 설정                                                      | 허용되는 값                                        | 대량 편집 지원 | 지원되는 디바이스 유형 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|------------------------|
| *계정*                                                    |                                                        |                    | Windows에서 Teams 룸 |
| **Email**                                                    | Email 주소                                          | 아니요                 | Windows에서 Teams 룸 |
| **지원되는 모임 모드**                                   | Microsoft Teams만<br>비즈니스용 Skype(기본값) 및 Microsoft Teams<br>비즈니스용 Skype 및 Microsoft Teams(기본값)<br>비즈니스용 Skype 전용|예| Windows에서 Teams 룸 |
| **최신 인증**                                    | 설정<br>해제                                              | 예                | Windows에서 Teams 룸 |
| **Exchange 주소**                                         | Email 주소                                          | 아니요                 | Windows에서 Teams 룸 |
| **Domain\username(선택 사항)**                               | 계정 도메인 및 사용자 이름                           | 아니요                 | Windows에서 Teams 룸 |
| **도메인 구성**                                         | 쉼표로 구분된 목록                                   | 예                | Windows에서 Teams 룸 |
| *모임*                                                   |                                                        |                    | Windows, Surface Hubs의 Teams 룸 |
| **자동 화면 공유**                                 | 설정<br>해제                                              | 예                | Windows에서 Teams 룸 |
| **HDMI 수집 오디오 공유**                                 | 설정<br>해제                                              | 예                | Windows에서 Teams 룸 |
| **모임 이름 표시**                                       | 설정<br>해제                                              | 예                | Windows에서 Teams 룸 |
| **다른 사람이 모임을 떠난 경우 자동 나가기**                 | 설정<br>해제                                              | 예                | Windows에서 Teams 룸 |
| **타사 모임 참가**                 | Cisco Webex<br>확대 / 축소                                              | 예                | Windows, Surface Hubs의 Teams 룸 |
| **회의실 정보로 조인**                 | 선택한<br>하지 않은                                              | 예                | Windows, Surface Hubs의 Teams 룸 |
| **사용자 지정 정보로 조인**                 | 선택한<br>하지 않은                                              | 예                | Windows에서 Teams 룸 |
| **이름(필수)**                 | 방 또는 공간의 이름                                              | 예                | Windows에서 Teams 룸 |
| **Email(필수)**                 | Email 주소                                              | 예                | Windows에서 Teams 룸 |
| *장치*                                                     |                                                        |                    | Windows에서 Teams 룸 |
| **이중 모니터 모드**                                        | 설정<br>해제                                              | 예                | Windows에서 Teams 룸 |
| **콘텐츠 복제 허용** | 선택한<br>하지 않은                                 | 예                | Windows에서 Teams 룸 |
| **Bluetooth 비콘**                                      | 설정<br>해제                                              | 예                | Windows, Surface Hubs의 Teams 룸 |
| **근접 기반 모임 초대 자동 수락** | 선택한<br>하지 않은                                 | 예                | Windows, Surface Hubs의 Teams 룸 |
| **피드백을 사용하여 로그 보내기**                                  | 설정<br>해제                                              | 예                | Windows에서 Teams 룸 |
| **로그 및 피드백에 대한 Email 주소**                      | Email 주소                                          | 예                | Windows에서 Teams 룸 |
| *모임 조정*                                                     |                                                        |                    | Windows에서 Teams 룸 |
| **조정된 모임** | 설정<br>해제                                 | 아니요                | Windows, Surface Hubs의 Teams 룸 |
| **이 장치의 마이크 켜기** | 설정<br>해제                                 | 아니요                | Windows, Surface Hubs의 Teams 룸 |
| **모임에 참가할 때 사용자가 사용하도록 설정** | 선택한<br>하지 않은                                 | 아니요                | Windows, Surface 허브의 Teams 룸 |
| **이 장치의 카메라 켜기** | 설정<br>해제                                 | 아니요                | Windows, Surface Hubs의 Teams 룸 |
| **모임에 참가할 때 사용자가 사용하도록 설정** | 선택한<br>하지 않은                                 | 아니요                | Windows, Surface Hubs의 Teams 룸 |
| **이 디바이스에 대한 화이트보딩 켜기** | 설정<br>해제                                 | 아니요                | Windows, Surface Hubs의 Teams 룸 |
| **신뢰할 수 있는 디바이스 계정(쉼표로 구분)** | 디바이스 목록                              | 아니요                | Windows, Surface Hubs의 Teams 룸 |
| *주변*                                                |                                                        |                    | Windows에서 Teams 룸 |
| **회의 마이크**                                  | 사용 가능한 마이크 목록                          | 아니요                 | Windows에서 Teams 룸 |
| **회의 화자**                                     | 사용 가능한 스피커 목록                             | 아니요                 | Windows에서 Teams 룸 |
| **기본 볼륨**                                           | 0-100                                                  | 아니요                 | Windows에서 Teams 룸 |
| **기본 스피커**                                          | 사용 가능한 스피커 목록                             | 아니요                 | Windows에서 Teams 룸 |
| **기본 볼륨**                                           | 0-100                                                  | 아니요                 | Windows에서 Teams 룸 |
| **콘텐츠 카메라**                                           | 사용 가능한 카메라 목록                              | 아니요                 | Windows에서 Teams 룸 |
| **콘텐츠 카메라 향상된 기능**                              | 설정<br>해제                                              | 아니요                 | Windows에서 Teams 룸 |
| **콘텐츠 카메라 180도 회전**                        | 설정<br>해제                                              | 아니요                 | Windows에서 Teams 룸 |
| *테마*                                                    |                                                        |                    | Windows에서 Teams 룸 |
|                                                              | 기본<br>테마 없음<br>주문<br>기본 제공 테마 목록   | 예                | Windows에서 Teams 룸 |

[Surface Hub를 구성하는 추가 옵션은 Surface Hubs에서 Microsoft Teams 구성 관리를](surface-hub-manage-config.md) 참조하세요.

### <a name="cortana-settings"></a>Cortana 설정

_Cortana for Voice Activation_ 또는 _Push를_ 사용하도록 설정하여 조직의 모든 디바이스 또는 각 디바이스에 대해 PowerShell을 사용하여 개별적으로 대화할 수 있습니다.

"Teams의 Cortana 음성 지원" 문서에서 [Windows의 Microsoft Teams 룸](../cortana-in-teams.md) 참조하세요.

### <a name="front-row-layout-settings"></a>앞줄 레이아웃 설정

앞줄은 Windows에서 Teams 룸 대한 모임 보기 레이아웃 옵션입니다.

| Teams 디바이스 | 앱 버전 | 방 전면 디스플레이 |
|--------------|-------------|-----------------------|
|Windows에서 Microsoft Teams 룸 | 4.11.12.0 이상(최신 버전 권장) | 단일 및 이중 디스플레이를 지원합니다. 최소 크기: 46인치; 가로 세로 비율 16:9 및 1920x1080 해상도, 2560x1080 해상도의 21:9 모든 디스플레이는 Windows 설정에서 100% 크기 조정으로 설정해야 합니다. |

앞줄의 요구 사항에 맞게 디스플레이 설정을 조정하려면 [Microsoft Teams 룸 유지 관리 및 작업을](rooms-operations.md#scale-and-resolution) 참조하세요.

앞줄을 회의실의 기본 레이아웃으로 설정하거나 해제하는 방법을 알아보려면 [XML 구성 파일을 사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리를](xml-config-file.md#set-front-row-as-the-default-layout) 참조하세요.

앞줄 관리에 대한 자세한 내용은 [알려진 문제를](known-issues.md#Limits) 참조하세요.

## <a name="device-restart-options"></a>디바이스 다시 시작 옵션

디바이스 설정 변경 내용은 디바이스를 다시 시작한 후에만 적용됩니다. 다시 시작해야 하는 변경을 수행할 때 즉시 다시 시작할지 아니면 다시 시작을 예약할지 선택할 수 있습니다. 사용 가능한 다시 시작 옵션은 다음과 같습니다.

- **즉시 다시 시작** 이 옵션을 선택하면 이 옵션을 선택하는 즉시 변경하려는 모든 디바이스가 다시 시작됩니다.
- **예약된 다시 시작** 이 옵션을 선택하면 변경하려는 디바이스를 조직에 방해가 덜 되는 시간에 다시 시작할 수 있습니다.
  - **날짜 및 시간 선택** - 디바이스를 다시 시작할 특정 날짜 및 시간을 선택합니다. 선택한 날짜와 시간은 다시 시작하는 디바이스에 대한 로컬입니다. 
  - **야간 재부팅 업데이트를 그대로 둡니다.** 유지 관리를 수행하기 위해 디바이스가 야간에 다시 시작됩니다. 디바이스에 대한 변경 내용은 이 다시 시작하는 동안 적용됩니다.

> [!CAUTION]
> 다시 시작 시 사용 중인 Teams 룸 및 Surface Hub는 다시 시작 프로세스 기간 동안 사용할 수 없게 됩니다. 진행 중인 모임의 연결이 끊어지며 디바이스를 다시 시작하는 동안에는 새 모임에 참가할 수 없습니다.

## <a name="remove-device"></a>디바이스 제거

장치를 제거하면 디바이스가 조직에서 제거되고 Teams 관리 센터의 Windows 또는 Surface Hubs의 Teams 룸 목록에 더 이상 표시되지 않습니다.

장치를 제거하고 유효한 사용자 이름 및 암호로 구성된 경우 Microsoft 365에 다시 연결하는 경우 Teams 룸 또는 Surface Hubs 목록에 자동으로 다시 추가됩니다.

하나 이상의 디바이스를 제거하려면 다음을 수행합니다.

1. **Teams 디바이스** > **Teams 룸 Windows** 또는 **Surface Hubs** 로 이동하여 제거할 디바이스를 선택합니다.
2. **제거** 를 선택합니다.

## <a name="download-device-logs"></a>디바이스 로그 다운로드

Microsoft 지원에서 요청하면 디바이스의 진단 로그 파일 복사본을 다운로드할 수 있습니다. 로그 파일은 Teams 관리 센터에서 다운로드할 수 있는 zip 파일로 압축됩니다.

Teams 룸 디바이스에서 컴퓨터로 로그를 다운로드하려면 다음을 수행합니다.

1. Windows 또는 **Surface Hubs** 의 **Teams 디바이스** > **Teams 룸** 로 이동하여 로그를 다운로드할 디바이스의 이름을 선택합니다.
1. **디바이스 로그 다운로드를** 선택합니다. 디바이스 로그를 사용할 수 있게 되는 데 몇 분 정도 걸릴 수 있습니다.
1. **기록** 탭을 선택한 다음 진단 파일에서 로그 **파일** 링크를 선택합니다. 디바이스의 진단 로그 파일이 포함된 zip 파일이 브라우저의 기본 다운로드 폴더에 다운로드됩니다.

## <a name="view-device-information"></a>디바이스 정보 보기

Teams 관리 센터에서 조직의 모든 디바이스의 전체 상태를 보고 각 디바이스의 세부 정보를 개별적으로 볼 수 있습니다.

### <a name="teams-rooms-system-dashboard"></a>Teams 룸 시스템 대시보드

Teams 룸 시스템 대시보드는 모든 디바이스의 상태와 상태를 한눈에 보여줍니다.

### <a name="device-details-view"></a>디바이스 세부 정보 보기

디바이스에 대한 자세한 정보를 보려면 디바이스 목록에서 해당 이름을 선택합니다. 세부 정보 보기에서 디바이스에 대한 다음 정보를 볼 수 있습니다.

- **상태** Teams 룸 또는 Surface Hub 디바이스의 전반적인 상태를 표시합니다. 상태는 **정상**, **긴급하지 않은** 상태, **위험** 또는 **오프라인** 상태일 수 있습니다.
- **이후 오프라인** Microsoft 365가 디바이스와 마지막으로 통신할 수 있었던 시간을 보여줍니다.
- **사용 현황 상태** 디바이스의 현재 상태( **유휴**, **사용 중** 또는 **사용할 수 없음**)를 표시합니다. Windows의 Teams 룸 경우에만 해당됩니다.
- **주변** Teams 룸 디바이스에 연결된 주변 장치와 해당 상태를 표시합니다. 상태는 **연결** 됨 또는 **연결 끊김** 일 수 있습니다. Windows의 Teams 룸 경우에만 해당됩니다.
- **건강** Teams 룸 디바이스에 연결된 주변 장치에 대한 자세한 정보, 네트워크 연결, 필요한 서비스에 로그인 상태 및 소프트웨어 버전 정보를 표시합니다.
- **세부 정보** 제조업체 정보, 네트워크 IP 주소 및 Teams 룸 디바이스 직렬/MAC 주소를 표시합니다.
- **활동** 모임 날짜 및 시간, 참가자 수, 기간 및 오디오 품질을 포함한 과거 모임 세부 정보를 표시합니다. 모임 세부 정보에 대한 자세한 내용은 이 문서의 뒷부분에 [있는 모임 활동 세부 정보](#meeting-activity-details) 섹션을 참조하세요.
- **역사** 구성 업데이트, 디바이스 다시 시작 및 디바이스 로그 다운로드 링크를 포함하여 Teams 룸 또는 Surface Hub 디바이스의 관리 활동 기록을 보여 줍니다.

#### <a name="meeting-activity-details"></a>모임 활동 세부 정보

디바이스 세부 정보의 **활동** 탭에는 시간이 지남에 따라 디바이스가 참여한 모든 모임에 대한 개략적이고 자세한 정보가 표시됩니다. **활동** 탭에서 모임이 열린 시기, 모임에 참석한 참가자 수, 모임 중 오디오 품질을 확인할 수 있습니다.

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="Teams 룸 디바이스 활동 요약 목록입니다.":::

특정 모임에 대한 세부 정보를 보려면 자세한 정보를 원하는 모임의 날짜와 시간을 선택합니다. 모임에 참가자가 두 명뿐인 경우 참가자 세부 정보 페이지가 표시되며, 그렇지 않으면 참가자 요약 페이지가 표시됩니다.

##### <a name="participant-summary"></a>참가자 요약

참가자 요약 페이지에는 모임에 참석한 모든 참가자가 표시됩니다. 각 참가자가 모임에 참가한 시기, 해당 이름, 오디오 품질 및 세션 중에 사용된 기능을 확인할 수 있습니다. 참가자 세션의 세부 정보를 보려면 해당 참가자의 세션 시작 시간을 선택합니다.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="디바이스 회의 세부 정보를 Teams 룸.":::

##### <a name="participant-details"></a>참가자 세부 정보

참가자 세부 정보 페이지에는 해당 참가자 세션에 대한 엔드 투 엔드 진단 정보가 표시됩니다. 다음 그래픽과 같이 참가자 및 Teams 룸 디바이스에 대한 **디바이스**, **시스템** 및 **연결** 정보가 제공됩니다. 참가자와 Teams 룸 디바이스 간의 **네트워크** 진단 정보도 제공됩니다. 자세한 정보를 원하는 컨텍스트의 아이콘을 선택합니다. 추가 진단 정보는 **고급** 탭을 선택합니다.

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="디바이스 호출 세부 정보를 Teams 룸.":::
