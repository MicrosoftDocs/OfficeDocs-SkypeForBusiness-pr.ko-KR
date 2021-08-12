---
title: Microsoft 365 관리 센터
description: 그래픽 사용자 인터페이스를 사용하려면 Microsoft Teams 룸 센터를 사용하여 사용자 Microsoft Teams 룸 및 공동 작업 Microsoft Teams Microsoft 365 관리 있습니다.
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
ms.openlocfilehash: 014c51182213ec17e940f466ddd5fa0cc13185be561e3670277430ce78a054c2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314094"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Microsoft 365 사용하여 Microsoft 365 관리 센터

Microsoft 365 리소스 계정은 Teams, 프로젝터 등 특정 리소스에 전용인 사서함 및 계정입니다. 이러한 리소스 계정은 사용자가 만들 때 정의한 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. 예를 들어 회의실과 같은 공통 리소스가 있는 경우 일정 가용성에 따라 모임 초대를 자동으로 수락하거나 거부하는 해당 회의실에 대한 리소스 계정을 설정할 수 있습니다.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>라이선싱

리소스 계정을 Microsoft 365 전에 필요한 라이선스 종류를 확인하세요. 리소스 계정을 사용하여 리소스를 예약하는 경우(즉, 모임에 리소스를 초대하고 초대를 자동으로 수락하거나 거부하는 경우) 리소스 계정에 라이선스를 할당할 필요가 없습니다. 다음 상황에서 리소스 계정에 라이선스를 할당해야 합니다.

- **Teams 모임** 리소스(예: Microsoft Teams 룸 콘솔, 공동 작업 표시줄 등)가 모임에 참가하여 참석자들이 해당 Teams 비디오 및 오디오를 표시하는 데 사용할 수 있도록 하려는 경우 미팅룸 라이선스가 필요합니다. 
- **PSTN 호출** 리소스가 외부 전화 번호(공용 전환 전화 네트워크 또는 PSTN 호출)에 대한 통화를 걸거나 받으려 하는 경우 Microsoft 365 전화 시스템 또는 Microsoft 365 Business Voice 라이선스가 필요합니다.

미팅룸, 전화 시스템 및 Business Voice 라이선스에 대한 자세한 내용은 추가 Microsoft Teams 라이선스를 [참조하세요.](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>에서 리소스 계정을 Microsoft 365 관리 센터

1. 방문하여 Microsoft 365 로그인https://admin.microsoft.com
2. 테넌트에 대한 관리자 Microsoft 365 제공합니다. 이렇게 하면 사용자 Microsoft 365 관리 센터.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 관리 센터":::
3. 관리 센터에서 왼쪽  패널의 리소스로 이동한 다음(먼저 모든 표시를 **선택해야 할 수 있습니다)로** 이동한 다음, & 를 선택합니다. 

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 관리 센터 - 리소스":::
4. 리소스 **사서함 추가를 선택하여** 새 룸 계정을 만들 수 있습니다. 계정에 대한 표시 이름 및 전자 메일 주소를 입력하고 **추가를** 선택한 다음 **닫기 를 선택합니다.** 모든 리소스 계정에 대한 이름 규칙을 표준화하는 것이 좋습니다.

> [!NOTE]
> 기본적으로 리소스 계정은 다음 설정으로 설정됩니다. 변경하려는 경우 닫기  를 선택하기 전에 일주 옵션 설정을 **선택합니다.** 나중에 변경하려는 경우 리소스 룸 & 장비로 이동한 다음, 리소스 계정을 선택한 다음 예약 옵션에서  >   **편집을 선택합니다.** 
>
> - 반복 모임 허용
> - 다음 제한을 초과하여 모임을 자동으로 거부합니다.
>   - 예약 기간(일): 180
>   - 최대 기간(시간): 24
> - 모임 요청 자동 수락

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 관리 센터 - 리소스 추가":::
5. 관리 센터의 **사용자** 섹션으로 이동하고 활성 사용자 **목록에서** 방금 만든 방이 표시됩니다.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 관리 센터 - 활성 사용자 보기":::
6. 룸의 이름에서 선택하고 오른쪽에 계정 속성 패널이 표시됩니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 관리 센터 - 사용자 속성":::
7. 이제 리소스 계정에 암호를 할당해야 합니다. 패널에서 계정 속성 및 몇 가지 선택적 작업을 볼 수 있습니다. 암호를  변경하려면 사용자 이름 아래에서 암호 재설정 키 아이콘을 선택합니다. 이 사용자에게 처음 로그인할 때 암호를 **변경하도록 선택을 선택하지 않습니다.** 디바이스 로그인 프로세스를 통해 암호를 변경할 수 없습니다. 다시 **설정 을 선택합니다.**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 관리 센터 - 암호 재설정":::
8. 라이선스 및 **앱 섹션에서**  디바이스가 설치된 국가 또는 지역에 위치 선택을 설정합니다. 아래로 스크롤하여 할당할 라이선스 옆에 있는 상자(예: 미팅룸)를 선택한 다음 변경 내용 저장을 **선택합니다.** 라이선스는 조직에 따라 다를 수 있습니다.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 관리 센터 - 라이선스 할당":::
