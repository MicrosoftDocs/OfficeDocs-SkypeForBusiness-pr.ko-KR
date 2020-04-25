---
title: Microsoft Teams 예비 환경 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams 라이선스가 없는 Microsoft 365 또는 Office 365 사용자는 예비 Teams 라이선스를 시작할 수 있습니다.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4cc744b8cbe9942712857309f061b998957661b4
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780387"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a>Microsoft Teams의 예비 라이선스 관리
=======================================================

Microsoft Teams 예비 환경을 통해 조직에서 AAD (Azure Active Directory)를 사용하고 Teams 라이선스가 없는 사용자는 Teams의 예비 환경을 시작할 수 있습니다. 관리자는 조직의 사용자에 대해 이 기능을 설정 하거나 해제할 수 있습니다. 이전의 [Microsoft 상용 클라우드 평가판](iw-trial-teams.md)은 이제 Teams 예비 환경으로 대체되었습니다.

## <a name="whats-in-the-teams-exploratory-experience"></a>Teams의 예비 환경에는 무엇이 있나요?

관리자가 Teams 예비 환경의 일부로서 보게 될 서비스 계획은 다음과 같습니다.
 - Exchange Online(플랜 1)
 - Office 365용 흐름
 - MyAnalytics의 인사이트
 - Microsoft Forms(플랜 E1)
 - Microsoft Planner
 - Microsoft Search
 - Microsoft StaffHub
 - O365 E1 SKU용 Microsoft Stream
 - Microsoft Teams
 - Office 365용 모바일 장치 관리
 - Office 365용 Office 모바일 앱 
 - Office Online
 - Office 365용 PowerApps
 - SharePoint Online(플랜 1)
 - Sway
 - To-Do(플랜 1)
 - 화이트보드(플랜 1)
 - Yammer Enterprise


## <a name="whos-eligible"></a>사용 자격이 있는 사용자

사용자에게 관리되는 AAD 도메인 전자 메일 주소가 있고 현재 Teams 라이선스가 할당되지 않은 경우 이 환경을 사용할 수 있습니다. 예를 들어 사용자에게 Microsoft 365 앱(Teams가 포함되지 않음)이 있는 경우 Teams 예비 환경을 사용할 수 있습니다.

(Microsoft 365 관리 센터에서) 사용자는 앱과 평가판을 사용할 수 있게 등록하도록 설정을 해야 합니다. 자세한 내용은 이 문서 뒷부분의 [Teams 예비 환경 관리](#manage-the-teams-exploratory-experience)를 참조하십시오. 


## <a name="who-isnt-eligible"></a>사용 자격이 없는 사용자

사용자가 Syndication 파트너 고객이거나 GCC, GCC High, DoD 또는 EDU 고객인 경우 사용자의 조직은 이 서비스를 사용할 수 없습니다.


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a>Teams 예비 환경에 등록하는 방법

적격 사용자는 Teams에 로그인하여 Teams 예비 환경에 등록할 수 있습니다([teams.microsoft.com](https://teams.microsoft.com)). 적격 사용자에게는 자동으로 라이선스가 할당 되고 조직 내 사용자가 Teams 예비 환경을 처음 시작할 때 테넌트 관리자가 전자 메일 알림을 받게 됩니다.

## <a name="manage-the-teams-exploratory-experience"></a>Teams 예비 환경 관리

Teams 예비 환경은 개별 최종 사용자가 시작하고 최종 사용자 직원을 대신해 이 서비스를 시작할 수 없습니다.

Teams 예비 환경은 Exchange Online 라이선스와 함께 제공되지만 관리자가 할당할 때까지 사용자에게 할당되지 않습니다. 사용자에게 아직 Exchange 라이선스가 없으며 관리자가 아직 Exchange Online 라이선스를 할당하지 않은 경우, 사용자는 Teams에서 모임을 예약할 수 없으며 Teams의 다른 기능이 표시되지 않을 수도 있습니다.

관리자는 **평가판 앱 및 서비스** 스위치를 사용하여 조직 내에서 최종 사용자가 Teams 예비 환경을 실행할 수 있는 기능을 해제할 수 있습니다.


### <a name="prevent-users-from-installing-trial-apps-and-services"></a>사용자가 평가판 앱 및 서비스를 설치하지 못하도록 방지

사용자가 평가판 앱 및 서비스를 설치하는 기능을 해제하여 사용자가 Teams 예비 환경을 실행하지 못하도록 할 수 있습니다.

1. [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home)에서 **설정** > **설정**으로 이동하여 **서비스**를 선택한 다음 **사용자 소유 앱 및 서비스**를 선택합니다.

    ![관리 센터의 서비스 페이지 스크린샷](media/iw-trial-services.png)

2. **사용자가 평가판 앱 및 서비스를 설치하도록 허용** 확인란을 해제합니다.

    ![관리 센터의 사용자 소유의 앱과 서비스 페이지 스크린샷](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > 조직에서 Teams 예비 환경을 사용할 수 없는 경우 **사용자가 평가판 앱 및 서비스를 설치하도록 허용** 옵션이 표시되지 않습니다.

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a>Teams를 포함하는 라이선스가 있는 사용자의 상태 관리

Teams를 포함하는 라이선스가 할당된 사용자는 Teams 예비 환경을 사용할 수 없습니다. Teams 서비스 플랜을 사용할 수 있도록 설정한 경우 사용자는 로그인을 하고 Teams를 사용할 수 있습니다. 서비스 플랜을 사용하지 않도록 설정한 경우 사용자가 로그인할 수 없으며 Teams 예비 환경을 사용할 수 없습니다.

Teams로의 액세스를 해제하려면:

1. Microsoft 365 관리 센터에서 **사용자** > **활성 사용자**를 선택합니다.

2. 사용자 이름 옆에 있는 상자를 선택합니다.

3. 우측의 **제품 라이선스** 행에서 **편집**을 선택합니다.

4. **제품 라이선스** 창에서 토글 스위치를 **해제**로 전환합니다.

    ![관리 센터의 제품 라이선스 페이지 스크린샷.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a>Teams 예비 환경을 이미 사용 중인 사용자의 Teams 상태 관리

사용자가 Teams 예비 환경을 실행하고 있는 경우 해당 라이선스 혹은 서비스 플랜을 제거하여이 기능을 해제할 수 있습니다.

Teams 예비 환경 라이선스를 해제하려면 다음을 수행합니다.

1. Microsoft 365 관리 센터에서 **사용자** > **활성 사용자**를 선택합니다.

2. 사용자 이름 옆에 있는 상자를 선택합니다.

3. 우측의 **제품 라이선스** 행에서 **편집**을 선택합니다.

4. **제품 라이선스** 창에서 예비 라이선스 토글 스위치를 **해제**로 전환합니다.
   
    >[!Note]
    >조직에서 첫 번째 사용자가 Teams 예비 환경을 실행한 후 Teams 예비 토글 스위치가 표시됩니다.

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a>Teams 예비 라이선스가 있는 사용자의 Teams 관리

정규 유료 라이선스가 있는 사용자를 관리하는 것과 같은 방식으로 Teams 예비 라이선스가 있는 사용자를 관리할 수 있습니다. 자세한 내용은 [조직에서 Teams 설정 관리](enable-features-office-365.md)를 참조하세요.

### <a name="upgrade-users-from-the-teams-exploratory-license"></a>Teams 예비 라이선스에서 사용자 업그레이드

Teams 예비 라이선스에서 사용자를 업그레이드하려면 다음을 수행합니다.

1. Teams를 포함하는 구독을 구입합니다.

2. 사용자의 Teams 예비 구독을 제거합니다.

3. 새로 구매한 라이선스를 할당합니다.

자세한 내용은 [Microsoft Teams 사용을 위한 Office 365 라이선싱](Office-365-licensing.md)을 참조하세요.

> [!NOTE]
> Teams 예비 라이선스가 종료되고 사용자가 Teams을 포함하는 구독으로 즉시 업그레이드 되지 않는 경우 사용자의 데이터는 제거되지 않습니다. 사용자는 여전히 Azure Active Directory에 존재하고 Teams 내의 모든 데이터는 계속 유지됩니다. Teams의 기능을 다시 사용할 수 있도록 사용자에게 새 라이선스가 할당되면 모든 콘텐츠가 계속 존재하게 됩니다. 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a>레거시 Microsoft Teams 상용 클라우드 평가판 라이선스는 어떻게 되나요?

2020년 2월부로 적격 사용자는 최신 Microsoft Teams 예비 환경을 사용하기 시작할 수 있습니다. 모든 레거시 Teams 상용 클라우드 평가판 라이선스는 평가판이 만료되기 전에 자동으로 신규 서비스로 변환됩니다.

### <a name="remove-a-teams-exploratory-license"></a>Teams 예비 라이선스 제거

- PowerShell을 통해 이 라이선스를 제거하려면 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)를 참조하세요.

- 관리 포털을 통해 이 라이선스를 제거하려면 [비즈니스용 Office 365의 사용자 라이선스 제거](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)를 참조하세요. 

## <a name="how-long-does-the-teams-exploratory-experience-last"></a>Teams 예비 환경은 얼마나 오래 지속되나요?

Microsoft Teams의 예비 환경은 다음 엔터프라이즈 **계약 기념일** 또는 2021년 1월 이후에 **갱신**될 때까지 추가 비용 없이 사용할 수 있습니다. 이 경우 Microsoft 예비 환경 라이선스의 최종 사용자는 Teams가 포함된 유료 라이선스로 전환해야 합니다. 그 이후에 시작된 모든 Microsoft 예비 환경 라이선스는 다음 **기념일** 또는 **갱신** 주기까지 추가 비용 없이 계속 사용할 수 있습니다. 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a>최종 사용자가 기념일 또는 갱신 날짜 직전에 Microsoft Teams 예비 환경을 시작하는 경우 어떻게 되나요?

**계약 기념일** 또는 **갱신** 후 90일 이내에 시작된 Microsoft Teams 예비 환경 라이선스는 다음 기념일 또는 갱신 주기까지 유료 라이선스로 전환할 필요가 없습니다. 
