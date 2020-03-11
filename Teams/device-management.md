---
title: Microsoft 팀에서 장치 관리
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 조직에서 팀과 함께 사용 되는 장치를 관리 하는 방법을 알아봅니다.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587297"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Microsoft 팀에서 장치 관리

관리자는 Microsoft 팀 관리 센터에서 조직의 팀과 함께 사용 되는 디바이스를 관리할 수 있습니다. 조직의 장치 인벤토리를 보고 관리 하 고 장치에 대 한 업데이트, 다시 시작, 모니터링 등의 작업을 수행할 수 있습니다. 장치 또는 장치 그룹에 구성 프로필을 만들고 할당할 수도 있습니다. 

## <a name="what-devices-can-you-manage"></a>어떤 장치를 관리할 수 있나요?
팀에 대해 인증 되 고 등록 된 모든 장치를 관리할 수 있습니다. 장치는 사용자가 처음으로 장치에서 팀에 로그인 할 때 자동으로 등록 됩니다. 관리할 수 있는 인증 된 디바이스의 목록은 다음을 참조 하세요.

- [전화 회의](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [일반 전화기](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- 공동 작업 표시줄

장치는 [Microsoft 팀 관리 센터](https://admin.teams.microsoft.com) 에서 왼쪽 탐색 모음에 있는 **장치** 아래에 관리 됩니다.

> [!NOTE]
> Microsoft Intune이 있는 경우 장치가 Intune에 자동으로 등록 됩니다. 장치가 등록 되 면 디바이스 호환성이 확인 되 고 조건부 액세스 정책이 장치에 적용 됩니다.

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>팀에서 전화 및 공동 작업 모음 관리

휴대폰 및 공동 작업 모음은 Microsoft 팀 관리 센터에서 동일 하 게 관리 되지만, **장치**아래에 있는 왼쪽 탐색의 각 섹션은 고유 합니다. 이렇게 하면 각 장치 유형을 개별적으로 관리할 수 있습니다.

여기에서 조직의 팀에 등록 된 휴대폰 및 공동 작업 표시줄을 보고 관리할 수 있습니다. 각 디바이스에 대해 표시 되는 정보에는 장치 이름, 제조업체, 모델, 사용자, 상태, 동작, 마지막 표시 및 기록이 포함 됩니다. 보기를 사용자 지정 하 여 요구 사항에 맞는 정보를 표시할 수 있습니다.

다음은 조직의 팀 장치를 관리 하는 방법에 대 한 몇 가지 예입니다.  
    
|이 작업을 수행 하려면  |실행할 작업 |
|---------|---------|
|장치 정보 변경   | 장치 > **편집**을 선택 합니다. 장치 이름, 자산 태그 등의 세부 정보를 편집 하 고 노트를 추가할 수 있습니다.     |
|소프트웨어 업데이트 관리   |장치 > **업데이트**를 선택 합니다. 장치에서 사용할 수 있는 소프트웨어 및 펌웨어 업데이트 목록을 보고 설치할 업데이트를 선택할 수 있습니다.    |
|장치 다시 시작   |장치 > **다시 시작**을 선택 합니다.          |
|장치 기록 보기  | 장치 > **기록을**선택 합니다. 장치에 대 한 업데이트 기록을 볼 수 있습니다.     |
|진단 보기  | 장치 > **진단을**선택 합니다.        |

## <a name="use-configuration-profiles-in-teams"></a>팀에서 구성 프로필 사용

구성 프로필을 사용 하 여 조직의 팀 디바이스에 대 한 설정 및 기능을 관리 합니다. 구성 프로필을 만들거나 업로드 하 여 사용 하거나 사용 하지 않도록 설정할 설정 및 기능을 포함 한 다음 장치 또는 장치 그룹에 프로필을 할당할 수 있습니다. 

### <a name="create-a-configuration-profile"></a>구성 프로필 만들기

1. 왼쪽 탐색 창에서 **장치** > **구성 프로필로**이동 합니다.
2. **추가**를 클릭 합니다.
3. 프로필의 이름을 입력 하 고 원하는 경우 간단한 설명을 추가 합니다.
4. 프로필에 대해 원하는 설정을 지정한 다음 **저장**을 클릭 합니다.

### <a name="assign-a-configuration-profile"></a>구성 프로필 할당

1. 왼쪽 탐색 창에서 **장치** > **구성 프로필로**이동 합니다.
2. 할당 하려는 **구성 프로필** 을 선택한 다음 **장치에 할당**을 클릭 합니다.  
3. **장치를 구성 프로필에 할당** 창에서 할당 하려는 장치를 검색 하 여 선택 합니다.
4. **저장**을 클릭 합니다.
