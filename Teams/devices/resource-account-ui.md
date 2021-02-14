---
title: Microsoft 365 관리 센터를 사용하여 리소스 계정 만들기
description: 그래픽 사용자 인터페이스를 사용하려면 Microsoft 365 관리 센터를 사용하여 Microsoft Teams 회의실 및 Microsoft Teams의 공동 작업 막대에 대한 리소스 계정을 만들 수 있습니다.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 디바이스 계정 만들기, Microsoft 365 UI, Microsoft 365 관리 센터
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터를 사용하여 Microsoft 365 리소스 계정 만들기

Microsoft 365 리소스 계정은 사서함 및 방, 프로젝터 등의 특정 리소스 전용 Teams 계정입니다. 이러한 리소스 계정은 만들 때 정의한 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. 예를 들어 회의실과 같은 공통 리소스가 있는 경우 일정 가용성에 따라 모임 초대를 자동으로 수락하거나 거부하는 해당 회의실에 대한 리소스 계정을 설정할 수 있습니다.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>라이선싱

Microsoft 365 리소스 계정을 만들기 전에 필요한 라이선스 종류를 확인하세요. 리소스 계정만 사용하여 리소스를 예약하는 경우(즉, 모임에 자원을 초대하고 초대를 자동으로 수락하거나 거절하는 경우) 리소스 계정에 라이선스를 할당할 필요가 없습니다. 다음과 같은 상황에서 리소스 계정에 라이선스를 할당해야 합니다.

- **Teams 모임** 리소스(예: Microsoft Teams 회의실 콘솔, 공동 작업 표시줄 등)가 Teams 모임에 참가하여 참석자들이 이를 사용하여 비디오 및 오디오를 발표할 수 있도록 하려는 경우 회의실 라이선스가 필요합니다. 
- **PSTN 통화** 자원이 외부 전화 번호(공용 전환 전화 네트워크 또는 PSTN 통화)에서 전화를 걸거나 받을 수 있도록 하려는 경우 Microsoft 365 전화 시스템 또는 Microsoft 365 Business Voice 라이선스가 필요합니다.

회의실, 전화 시스템 및 Business Voice 라이선스에 대한 자세한 내용은 Microsoft Teams 추가 기능 라이선스를 [참조하세요.](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Microsoft 365 관리 센터에서 리소스 계정 만들기

1. 방문하여 Microsoft 365에 로그인 https://admin.microsoft.com
2. Microsoft 365 테넌트에 대한 관리자 자격 증명을 제공합니다. 그러면 Microsoft 365 관리 센터로 바로 가게 됩니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 관리 센터":::
3. 관리 센터에서 왼쪽  패널의 리소스로 이동한 다음(모두 표시를 먼저 선택해야 할 수 있습니다) 장비의 회의실을 **& 선택합니다.** 

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 관리 센터 - 리소스":::
4. 리소스 **사서함 추가를 선택하여** 새 방 계정을 만들 수 있습니다. 계정의 표시 이름과 전자 메일 주소를 입력하고 추가를 선택한 다음 **닫기를 선택합니다.** 모든 리소스 계정에 대한 이름 규칙을 표준화하는 것이 좋습니다.

> [!NOTE]
> 기본적으로 리소스 계정은 다음 설정으로 설정됩니다. 변경하려면 닫기 를  선택하기 전에 [설정] 옵션을 **선택합니다.** 나중에 변경하려면 장비가 있는 리소스실로 이동하여 & 계정을 선택한 다음  >  Booking **옵션에서 편집을 선택합니다.** 
>
> - 모임 반복 허용
> - 다음 제한을 초과하여 자동으로 모임 거부
>   - 예약 창(일): 180
>   - 최대 기간(시간): 24
> - 모임 요청 자동 수락

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 관리 센터 - 리소스 추가":::
5. 관리 **센터의** 사용자 섹션으로 이동하면  활성 사용자 목록에 방금 만든 방이 표시됩니다.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 관리 센터 - 활성 사용자 보기":::
6. 방 이름을 선택하면 계정 속성 패널이 오른쪽에 표시됩니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 관리 센터 - 사용자 속성":::
7. 이제 리소스 계정에 암호를 할당해야 합니다. 패널에서 계정 속성 및 몇 가지 선택적 작업을 볼 수 있습니다. 사용자 **이름** 아래에서 암호 재설정 키 아이콘을 선택하여 암호를 변경합니다. 이 사용자가 처음 로그인할 때 암호를 **변경하도록 선택을 선택하지 않습니다.** 디바이스 로그인 프로세스를 통해 암호를 변경할 수 없습니다. 재설정을 **선택합니다.**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 관리 센터 - 암호 재설정":::
8. 라이선스 **및 앱 섹션에서** **디바이스를** 설치할 국가 또는 지역으로 선택 위치를 설정합니다. 아래로 스크롤하여 할당할 라이선스 옆에 있는 확인란(예: 회의실)을 선택한 다음 변경 내용 **저장을 선택합니다.** 라이선스는 조직에 따라 달라질 수 있습니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 관리 센터 - 라이선스 할당":::
