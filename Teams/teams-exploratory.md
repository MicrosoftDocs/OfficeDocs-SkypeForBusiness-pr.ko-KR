---
title: Microsoft Teams 예비 환경 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: Microsoft Teams 라이선스가 없는 Microsoft 365 또는 Office 365 사용자는 예비 Teams 라이선스를 시작할 수 있습니다.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 374761a64f64649dba67f9bfb8760f363fa94f2e
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605697"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a>Microsoft Teams의 예비 라이선스 관리

Microsoft Teams Exploratory 환경을 통해 조직에서 Azure AD(Azure Active Directory)를 사용하고 Teams 라이선스가 없는 사용자는 Teams의 탐색 환경을 시작할 수 있습니다. 관리자는 조직의 사용자에 대해 이 기능을 켜거나 끌 수 있습니다.

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams Exploratory 환경에는 무엇이 있나요?

관리자가 Teams 예비 환경의 일부로서 보게 될 서비스 계획은 다음과 같습니다.

- Exchange Online(플랜 1)
- Microsoft 365 혹은 Office 365에 대한 흐름
- MyAnalytics의 인사이트
- Microsoft Forms(플랜 E1)
- Microsoft Planner
- Microsoft Search
- Microsoft StaffHub
- Microsoft 365 및 Office 365 E1 SKU용 Microsoft Stream <sup>1</1>
- Microsoft Teams
- Microsoft 365 혹은 Office 365용 모바일 장치 관리
- Office 365용 Office 모바일 앱
- Office Online
- Microsoft 365 혹은 Office 365용 Power Apps
- SharePoint Online(플랜 1)
- Sway
- To-Do(플랜 1)
- 화이트보드(플랜 1)
- Yammer Enterprise

  <sup>1</sup> Microsoft Stream에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](tmr-meeting-recording-change.md)로의 변경은 단계별로 접근합니다. 시작할 때 이 환경을 옵트인할 수 있습니다. 11월에는 Stream을 계속 사용하는 경우 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 비즈니스용 OneDrive 및 SharePoint를 사용하여 새로운 모임 기록을 작성해야 합니다.

## <a name="whos-eligible"></a>사용 자격이 있는 사용자

사용자는 다음과 같은 경우 Teams 탐색적 경험에 대한 기준을 충족합니다.

- 관리되는 Azure AD 도메인 전자 메일 주소를 포함 니다.
- 유료 구독이 있는 테넌트에 속합니다.
- 활성 Teams 라이선스가 없습니다.
- 라이선스 할당 정책을 만든 테넌트에 없습니다.

(Microsoft 365 관리 센터에서) 사용자는 앱과 평가판을 사용할 수 있게 등록하도록 설정을 해야 합니다. 자세한 내용은 이 문서 뒷부분의 [Teams 예비 환경 관리](#manage-the-teams-exploratory-experience)를 참조하십시오.

## <a name="who-isnt-eligible"></a>사용 자격이 없는 사용자

다음과 같은 경우 사용자는 기준에 맞지 않습니다.

- 현재 Teams 유료 라이선스 또는 평가판 라이선스가 있거나 이전에 평가판 라이선스가 있었음
- 하나 이상의 특별 COVID 제안을 사용하거나 받은 테넌트에 있습니다.

사용자가 Syndication 파트너 고객이거나 GCC, GCC High, DoD 또는 EDU 고객인 경우 사용자의 조직은 이 서비스를 사용할 수 없습니다.

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Teams 예비 환경에 등록하는 방법

적격 사용자는 데스크톱 또는 웹 Teams에 로그인하여 Teams 예비 환경에 등록할 수 있습니다([teams.microsoft.com](https://teams.microsoft.com)). 현재 모바일을 통한 탐색 기능은 지원되지 않습니다. 로그인 시, 자동으로 라이선스가 할당 되고 조직 내 사용자가 Teams 예비 환경을 처음 시작할 때 테넌트 관리자가 전자 메일 알림을 받게 됩니다.

## <a name="manage-the-teams-exploratory-experience"></a>Teams 예비 환경 관리

Teams 예비 환경은 개별 최종 사용자가 시작하고 최종 사용자 직원을 대신해 이 서비스를 시작할 수 없습니다.

Teams 예비 환경은 Exchange Online 라이선스와 함께 제공되지만 관리자가 할당할 때까지 사용자에게 할당되지 않습니다. 사용자에게 아직 Exchange 라이선스가 없으며 관리자가 아직 Exchange Online 라이선스를 할당하지 않은 경우, 사용자는 Teams에서 모임을 예약할 수 없으며 Teams의 다른 기능이 표시되지 않을 수도 있습니다.

관리자는 **평가판 앱 및 서비스** 스위치를 사용하여 조직 내에서 최종 사용자가 Teams 예비 환경을 실행할 수 있는 기능을 해제할 수 있습니다.

### <a name="prevent-users-from-installing-trial-apps-and-services"></a>사용자가 평가판 앱 및 서비스를 설치하지 못하도록 방지

사용자가 평가판 앱 및 서비스를 설치하는 기능을 해제하여 사용자가 Teams 예비 환경을 실행하지 못하도록 할 수 있습니다.

1. Microsoft 365 관리 센터에서 **설정** > **조직 설정** 으로 이동하여 **서비스** 를 선택한 다음 **사용자 소유 앱 및 서비스** 를 선택합니다.

    ![관리 센터의 서비스 페이지입니다.](media/iw-trial-services.png)

2. **사용자가 평가판 앱 및 서비스를 설치하도록 허용** 확인란을 해제합니다.

    ![관리 센터의 사용자 소유 앱 및 서비스 페이지입니다.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 조직에서 Teams 예비 환경을 사용할 수 없는 경우 **사용자가 평가판 앱 및 서비스를 설치하도록 허용** 옵션이 표시되지 않습니다.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Teams를 포함하는 라이선스가 있는 사용자의 상태 관리

Teams를 포함하는 라이선스가 할당된 사용자는 Teams 예비 환경을 사용할 수 없습니다. Teams 서비스 플랜을 사용할 수 있도록 설정한 경우 사용자는 로그인을 하고 Teams를 사용할 수 있습니다. 서비스 플랜을 사용하지 않도록 설정한 경우 사용자가 로그인할 수 없으며 Teams 예비 환경을 사용할 수 없습니다. 관리자 권한이 있어야 합니다.

Teams로의 액세스를 해제하려면:

1. Microsoft 365 관리 센터에서 **사용자** > **활성 사용자** 를 선택합니다.

2. 사용자 이름 옆에 있는 상자를 선택합니다.

3. **제품 라이선스** 행에서 **편집** 을 선택합니다.

4. **제품 라이선스** 창에서 토글 스위치를 **해제** 로 전환합니다.

    ![관리 센터의 제품 라이선스 페이지](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Teams 예비 환경을 이미 사용 중인 사용자의 Teams 상태 관리

Teams Exploratory 환경을 실행하고 있는 경우 해당 라이선스 혹은 서비스 플랜을 제거하여 이 기능을 해제할 수 있습니다. 관리자 권한이 있어야 합니다.

Teams 예비 환경 라이선스를 해제하려면 다음을 수행합니다.

1. Microsoft 365 관리 센터에서 **사용자** > **활성 사용자** 를 선택합니다.

2. 사용자 이름 옆에 있는 상자를 선택합니다.

3. **제품 라이선스** 행에서 **편집** 을 선택합니다.

4. **제품 라이선스** 창에서 예비 라이선스 토글 스위치를 **해제** 로 전환합니다.

    > [!NOTE]
    > 조직에서 첫 번째 사용자가 Teams 예비 환경을 실행한 후 Teams 예비 토글 스위치가 표시됩니다.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Teams 예비 라이선스가 있는 사용자의 Teams 관리

정규 유료 라이선스가 있는 사용자를 관리하는 것과 같은 방식으로 Teams 예비 라이선스가 있는 사용자를 관리할 수 있습니다. 자세한 내용은 [조직에서 Teams 설정 관리](enable-features-office-365.md)를 참조하세요.

### <a name="upgrade-users-from-teams-exploratory"></a>Teams Exploratory에서 사용자 업그레이드

Teams Exploratory에서 사용자를 업그레이드하려면 관리자 권한이 있어야 합니다. 자세한 내용은 [Teams Exploratory 평가판에서 사용자 업그레이드](upgrade-from-teams-exploratory.md)를 참조하세요.

> [!NOTE]
> Teams Exploratory 라이선스가 종료되고 사용자가 Teams를 포함하는 구독으로 즉시 업그레이드되지 않으면 30일의 유예 기간 후에 Teams에 액세스할 수 없게 됩니다. 그 후 30일이 지나면 데이터가 삭제됩니다. 사용자가 여전히 Azure Active Directory에 있습니다. Teams 기능을 다시 활성화하기 위해 사용자에게 새 라이선스를 할당하더라도 사용자가 유예 기간 내에 추가되더라도 모든 콘텐츠는 계속 유지됩니다.

### <a name="remove-a-teams-exploratory-license"></a>Teams 예비 라이선스 제거

- PowerShell을 통해 이 라이선스를 제거하려면 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)를 참조하세요.

- 관리 포털을 통해 이 라이선스를 제거하려면 [조직에서 사용자 제거](/microsoft-365/admin/add-users/delete-a-user)를 참조하세요.

## <a name="what-is-the-data-retention-policy"></a>데이터 보존 정책이란 무엇인가요?

[Microsoft 365 구독 정보](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)를 참조하세요.

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Teams Exploratory 환경은 얼마나 오래 지속되나요?

Teams Exploratory는 모든 신규 고객에게 12개월 구독(초기 사용자 등록부터)으로 제공됩니다. 새 Teams Exploratory 구독은 조직의 첫 번째 사용자가 Teams 탐색에 등록할 때 시작되고 12개월 후에 만료됩니다. 동일한 테넌트의 모든 사용자에게 만료 날짜가 적용되며, 첫 번째 사용자의 구독 날짜부터 12개월 기간이 시작됩니다.

> [!NOTE]
> 환경의 종료 날짜는 조직 수준에서 구성됩니다. 즉, 동일한 조직의 모든 사용자에게 적용됩니다. 예를 들어 사용자 1은 2021년 1월 1일 구독에 등록합니다. 그러면 2021년 12월 31일의 구독 종료 날짜가 시작됩니다. 다른 사용자인 사용자 2는 2021년 10월 1일에 구독에 등록합니다. 사용자 2는 조직이 사용자 1과 동일한 구독을 사용 중이기 때문에 종료 날짜가 2021년 12월 31일이 되고 두 달 동안 Teams Exploratory를 사용할 수 있습니다.

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a>12개월 동안의 Teams Exploratory가 끝나면 관리자가 어떤 작업을 해야 하는지

12개월 구독이 종료되는 경우 관리자는 모든 Teams Exploratory 사용자를 Teams가 포함된 유료 라이선스로 변환해야 합니다. 사용자의 환경 중단을 방지하기 위해 Teams Exploratory 구독이 만료되기 전에 이 작업을 완료하는 것이 중요합니다.


> [!NOTE]
> 고객은 이전 탐색 평가판 라이선스가 만료된 후 3개월 동안 새로운 탐색 평가판 라이선스를 시작할 수 없으며 사용할 수 없게 됩니다.

자세한 내용은 이 문서에서 [Teams Exploratory 라이선스의 사용자 업그레이드](#upgrade-users-from-teams-exploratory)를 참조하세요.
