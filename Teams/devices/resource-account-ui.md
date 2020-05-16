---
title: Microsoft 365 관리 센터를 사용 하 여 자원 계정 만들기
description: 그래픽 사용자 인터페이스를 사용 하려는 경우 microsoft 365 관리 센터를 사용 하 여 microsoft 팀의 회의실 및 공동 작업 표시줄에 대 한 리소스 계정을 만들 수 있습니다.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 장치 계정 만들기, Microsoft 365 UI, Microsoft 365 관리 센터
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268038"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용 하 여 Microsoft 365 리소스 계정 만들기

Microsoft 365 리소스 계정은 특정 리소스 (예: 회의실, 프로젝터 등)를 전담 하는 사서함 및 팀 계정입니다. 이러한 리소스 계정은 생성 될 때 사용자가 정의한 규칙을 사용 하 여 모임 초대에 자동으로 응답할 수 있습니다. 예를 들어 회의실 같은 공통 리소스가 있는 경우 해당 회의실에 대 한 리소스 계정을 설정 하 여 일정 가용성에 따라 모임 초대를 자동으로 수락 하거나 거절할 수 있습니다.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>라이선싱

Microsoft 365 리소스 계정을 만들기 전에 필요한 라이선스 종류를 확인 합니다. 리소스를 예약 하는 데 리소스 계정만 사용 하는 경우 (즉, 리소스를 모임에 초대 하 고 초대를 자동으로 수락 하거나 거절 하도록 하려면) 라이선스를 리소스 계정에 할당할 필요가 없습니다. 다음과 같은 경우에는 리소스 계정에 라이선스를 할당 해야 합니다.

- **팀 모임** 참석자가 팀 모임에 참가 하는 데 사용할 수 있는 리소스 (예: Microsoft 팀 회의실 콘솔, 공동 작업 모음 등)를 만들려면 모임 채팅방 라이선스가 필요 합니다. 
- **PSTN 통화** 해당 리소스에서 외부 전화 번호로 전화를 걸거나 받을 수 있도록 하려면 (공공 교환 전화 네트워크 또는 PSTN 통화 라고 함) Microsoft 365 전화 시스템 또는 Microsoft 365 Business 음성 라이선스가 필요 합니다.

회의실, 전화 시스템 및 비즈니스 음성 라이선스에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 를 참조 하세요.

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Microsoft 365 관리 센터에서 자원 계정 만들기

1. 방문 하 여 Microsoft 365에 로그인https://admin.microsoft.com
2. Microsoft 365 테 넌 트에 대 한 관리자 자격 증명을 제공 합니다. 이렇게 하면 Microsoft 365 관리 센터로 이동 합니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 관리 센터":::
3. 관리 센터에서 왼쪽 패널의 **리소스로** 이동한 다음 ( **모두 표시** 를 선택 해야 할 수 있음) **채팅방 & 장비**를 선택 합니다.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 관리 센터-리소스":::
4. **리소스 사서함 추가** 를 선택 하 여 새 룸 계정을 만듭니다. 계정의 표시 이름과 전자 메일 주소를 입력 하 고 **추가**를 선택한 다음 **닫기를**선택 합니다. 모든 리소스 계정에 대 한 명명 규칙을 표준화 하는 것이 좋습니다.

> [!NOTE]
> 기본적으로 자원 계정은 다음 설정을 사용 하 여 설정 됩니다. 이를 변경 하려면 **닫기를**선택 하기 전에 **일정 옵션 설정을** 선택 합니다. 나중에 변경 하려는 경우 **리소스**  >  **룸 & 장비**를 탐색 하 고 자원 계정을 선택한 다음 **예약 옵션**에서 **편집** 을 선택 합니다.
>
> - 모임 반복 허용
> - 다음 제한 범위 밖의 모임을 자동으로 거절
>   - 예약 창 (일): 180
>   - 최대 기간 (시간): 24
> - 모임 요청 자동 수락

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 관리 센터-리소스 추가":::
5. 관리 센터의 **사용자** 섹션으로 이동 하 고 **활성 사용자** 목록에 방금 만든 채팅방이 표시 됩니다.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 관리 센터-활성 사용자 참조":::
6. 룸의 이름을 선택 하면 오른쪽에 계정 등록 정보 창이 나타납니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 관리 센터-사용자 속성":::
7. 이제 리소스 계정에 암호를 지정 해야 합니다. 패널에서 계정 속성 및 여러 선택적 작업을 볼 수 있습니다. 사용자 이름 아래의 **암호 키 재설정** 아이콘을 선택 하 여 암호를 변경 합니다. 선택 취소 **이 사용자가 처음 로그인 할 때 암호를 변경 하도록 요구**합니다. 디바이스 로그인 프로세스를 통해 암호를 변경할 수 없습니다. **원래 대로**를 선택 합니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 관리 센터-암호 재설정":::
8. **라이선스 및 앱** 섹션에서 **선택 위치** 를 장치가 설치 될 국가 또는 지역으로 설정 합니다. 아래로 스크롤하여 할당할 라이선스 (예: 회의실) 옆의 확인란을 선택한 다음 **변경 내용 저장**을 선택 합니다. 라이선스는 조직에 따라 다를 수 있습니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 관리 센터-라이선스 할당":::
