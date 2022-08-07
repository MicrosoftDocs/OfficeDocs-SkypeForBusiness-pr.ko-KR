---
title: Microsoft Teams에서 디바이스 관리
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- m365initiative-deployteams
- Teams_ITAdmin_Devices
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 조직에서 Teams와 함께 사용되는 디바이스를 관리하는 방법을 알아봅니다.
ms.localizationpriority: medium
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc65025ed255dff1685f7aa30a555facdd3f11c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270843"
---
# <a name="microsoft-teams-managing-your-devices"></a>Microsoft Teams: 디바이스 관리 

Microsoft Teams 관리 센터에서 조직의 Microsoft Teams와 함께 사용되는 디바이스를 관리할 수 있습니다. 조직의 디바이스 인벤토리를 보고 관리하고 디바이스에 대한 진단 업데이트, 다시 시작 및 모니터링과 같은 작업을 수행할 수 있습니다. 디바이스 또는 디바이스 그룹에 구성 프로필을 만들고 할당할 수도 있습니다.

디바이스 구성 변경, 디바이스 다시 시작, 업데이트 관리 또는 디바이스 및 주변 장치 상태 보기와 같은 디바이스를 관리하려면 다음 Microsoft 365 관리자 역할 중 하나를 할당해야 합니다.

- Microsoft 365 전역 관리자
- Teams 서비스 관리자
- Teams 디바이스 관리자

Teams의 관리자 역할에 대한 자세한 내용은 [Teams 관리자 역할을 사용하여 Teams를 관리하세요](../using-admin-roles.md).

## <a name="what-devices-can-you-manage"></a>어떤 디바이스를 관리할 수 있나요?

Teams에 대해 인증되고 등록된 모든 디바이스를 관리할 수 있습니다. 사용자가 디바이스에서 Teams에 처음 로그인할 때 디바이스가 자동으로 등록됩니다. 관리할 수 있는 인증된 디바이스 목록은 다음을 참조하세요.

- [Microsoft Teams Rooms](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [전화 회의](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [책상 전화](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 디스플레이](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=34)
- [Teams 패널](teams-panels.md)

디바이스를 관리하려면 [Microsoft Teams 관리 센터의](https://admin.teams.microsoft.com) 왼쪽 탐색 영역에서 **Teams 디바이스** 로 이동한 다음 디바이스 유형을 선택합니다. 디바이스의 각 유형에는 개별적으로 관리할 수 있는 고유한 섹션이 있습니다.

## <a name="manage-teams-rooms-on-windows-devices"></a>Windows 디바이스에서 Teams 룸 관리

Teams 관리 센터를 사용하여 조직 전체의 Windows 디바이스에서 Teams 룸 보고 원격으로 관리할 수 있습니다. Teams 관리 센터를 사용하면 어떤 디바이스가 정상이고 어떤 디바이스에 주의가 필요한지 한눈에 쉽게 확인할 수 있으며, 특정 디바이스에 집중하여 디바이스 상태, 모임 성능, 통화 품질 및 주변 장치에 대한 자세한 정보를 볼 수 있습니다. 

다음은 Teams 룸 디바이스를 관리하기 위해 수행할 수 있는 몇 가지 작업입니다. Teams 룸 디바이스는 Windows의 **Teams 디바이스** > **Teams 룸** 아래에 있는 [Microsoft Teams 관리 센터에서](https://admin.teams.microsoft.com) 찾을 수 있습니다.

Teams 룸 디바이스를 관리하는 방법에 대한 자세한 내용은 [Microsoft Teams 룸 관리를](../rooms/rooms-manage.md) 참조하세요.

| 이렇게 하려면...                          | 이 작업을 수행합니다.                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 하나 이상의 디바이스에서 설정 변경 | **설정 편집** 을 > 하나 이상의 디바이스를 선택합니다. 여러 디바이스를 선택하면 변경한 값이 선택한 모든 디바이스의 값을 대체합니다.                                                                                                                                                                                                                       |
| 디바이스 다시 시작                        | **다시 시작할** > 하나 이상의 디바이스를 선택합니다. 디바이스를 다시 시작할 때 디바이스를 즉시 다시 시작할지 또는 일정 **다시** 시작을 선택하여 특정 날짜 및 시간에 디바이스를 다시 시작할지 선택할 수 있습니다. 선택한 날짜와 시간은 다시 시작하는 디바이스의 로컬입니다.                                                                                            |
| 모임 활동 보기                  | 디바이스 이름을 선택하여 디바이스 세부 정보 > **작업을** 엽니다. **활동** 탭을 열면 디바이스가 참가한 모든 모임을 볼 수 있습니다. 이 요약 보기는 모임 시작 시간, 참가자 수, 해당 기간 및 전체 통화 품질을 보여줍니다.                                                                                        |
| 모임 세부 정보 보기                   | 디바이스 이름을 선택하여 디바이스 세부 정보 > **활동** > 모임을 선택합니다. 모임의 세부 정보를 열면 모임의 모든 참가자, 통화 기간, Teams 세션 유형 및 개별 통화 품질을 볼 수 있습니다. 참가자의 통화에 대한 기술 정보를 보려면 참가자의 통화 시작 시간을 선택합니다. |

## <a name="manage-phones-teams-rooms-on-android-teams-displays-and-teams-panels"></a>Android, Teams 디스플레이 및 Teams 패널에서 휴대폰, Teams 룸 관리 

Teams 관리 센터에서는 Android에서 휴대폰, Teams 룸, Teams 디스플레이 및 조직의 Teams에 등록된 Teams 패널을 보고 관리할 수 있습니다. 각 디바이스에 대해 표시되는 정보에는 디바이스 이름, 제조업체, 모델, 사용자, 상태, 작업, 마지막으로 본 내용 및 기록이 포함됩니다. 보기를 사용자 지정하여 요구 사항에 맞는 정보를 표시할 수 있습니다.

Android에서 휴대폰, Teams 룸, Teams 디스플레이 및 Teams 패널을 등록한 경우 Microsoft Intune 자동으로 등록됩니다. 디바이스가 등록되면 디바이스 준수가 확인되고 조건부 액세스 정책이 디바이스에 적용됩니다.

다음은 조직의 Android, Teams 디스플레이 및 Teams 패널에서 휴대폰, Teams 룸 관리하는 방법의 몇 가지 예입니다.  

| 이렇게 하려면...                           | 이 작업을 수행합니다.                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 디바이스 정보 변경               | **디바이스 > 편집** 을 선택합니다. 디바이스 이름, 자산 태그 등의 세부 정보를 편집하고 메모를 추가할 수 있습니다.                                                                                                                                                                                                              |
| 소프트웨어 업데이트 관리                 | **디바이스 > 업데이트를** 선택합니다. 디바이스에 사용할 수 있는 소프트웨어 및 펌웨어 업데이트 목록을 보고 설치할 업데이트를 선택할 수 있습니다. 디바이스 업데이트에 대한 자세한 내용은 [원격으로 Teams 디바이스 업데이트를](remote-update.md) 참조하세요.                                                          |
| Teams 휴대폰을 Teams 디스플레이로 업그레이드  | **IP 휴대폰** 페이지에서 **업그레이드** 를 > 하나 이상의 Teams 휴대폰을 선택합니다. 이 옵션은 Teams 디스플레이로 업그레이드를 지원하는 휴대폰에서만 사용할 수 있습니다. 자세한 내용은 [Teams 휴대폰을 Teams 디스플레이로 업그레이드를 참조하세요](upgrade-phones-to-displays.md).                                                      |
| 구성 정책 할당 또는 변경 | **구성 할당** 을 > 하나 이상의 디바이스를 선택합니다.                                                                                                                                                                                                                                                       |
| 디바이스 태그 추가 또는 제거               | **태그 관리를** > 하나 이상의 디바이스를 선택합니다. 디바이스 태그에 대한 자세한 내용은 [Teams 디바이스 태그 관리를 참조하세요](manage-device-tags.md).                                                                                                                                                                 |
| 디바이스 다시 시작                         | **다시 시작할** > 하나 이상의 디바이스를 선택합니다.                                                                                                                                                                                                                                                                    |
| 디바이스 태그를 사용하여 디바이스 필터링        | 필터 아이콘을 선택하고, **태그** 필드를 선택하고, 필터링할 디바이스 태그를 지정하고, **적용** 을 선택합니다. 디바이스 태그를 사용하여 디바이스를 필터링하는 방법에 대한 자세한 내용은 [필터를 사용하여 특정 태그가 있는 디바이스를 반환합니다](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag). |
| 디바이스 기록 및 진단 보기     | **기록** 열 아래에서 디바이스에 대한 **보기** 링크를 클릭하여 업데이트 기록 및 진단 세부 정보를 봅니다.                                                                                                                                                                                         |

### <a name="use-configuration-profiles-in-teams"></a>Teams에서 구성 프로필 사용

구성 프로필을 사용하여 Android의 Teams 룸, Teams 디스플레이, Teams 휴대폰 및 Teams 패널을 포함하여 조직의 여러 Teams 디바이스에 대한 설정 및 기능을 관리할 수 있습니다. 사용하거나 사용하지 않도록 설정하려는 설정 및 기능을 포함하도록 구성 프로필을 만들거나 업로드한 다음 디바이스 또는 디바이스 집합에 프로필을 할당할 수 있습니다. 

#### <a name="create-a-configuration-profile"></a>구성 프로필 만들기

Teams 디바이스 유형에 대한 구성 프로필을 만들려면 다음을 수행합니다.

1. 왼쪽 탐색 창에서 **Teams 디바이스** 로 이동한 > Teams 디바이스 유형 > **구성 프로필을** 선택합니다. 예를 들어 **Teams 디바이스** > **Teams 패널****구성 프로필을** 선택하여 Teams 패널  >  에 대한 새 구성 프로필을 만듭니다.
2. **추가** 를 클릭합니다.
3. 프로필의 이름을 입력하고 필요에 따라 친숙한 설명을 추가합니다.
4. 프로필에 대해 원하는 설정을 지정하고 **저장** 을 클릭합니다.
   새로 만든 구성 프로필이 프로필 목록에 표시됩니다.

#### <a name="assign-a-configuration-profile"></a>구성 프로필 할당
Teams 디바이스 유형에 대한 구성 프로필을 만든 후 하나 이상의 디바이스에 할당합니다.

1. 왼쪽 탐색 창에서 **Teams 디바이스로 이동하여 Teams 디바이스** 유형을 > 선택합니다. 예를 들어 Teams 패널 디바이스에 구성 프로필을 할당하려면 **Teams 디바이스** > **Teams 패널을** 선택합니다.
2. 하나 이상의 디바이스를 선택한 다음 **구성 할당** 을 클릭합니다.  
3. **구성 할당** 창에서 선택한 디바이스에 할당할 구성 프로필을 검색합니다.
4. **적용** 을 클릭합니다.
   구성 정책을 적용한 디바이스의 경우 **작업** 열에 **구성 업데이트** 가 표시되고 **구성 프로필 열에 구성 프로필** 이름이 표시됩니다.
