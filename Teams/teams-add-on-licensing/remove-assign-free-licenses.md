---
title: 조직의 무료 Microsoft Teams(클래식) 사용 중지
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
robots: noindex
description: Teams 무료(클래식) 라이선스를 제거하고 조직의 사용자를 위해 유료 Teams 라이선스를 할당하는 방법을 알아봅니다.
ms.openlocfilehash: 027f84577a50d445eb01bce896417f23e503abb7
ms.sourcegitcommit: 1398c778e46b0d81c9710cd70d3818a2b7af995a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2023
ms.locfileid: "69749162"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>조직의 무료 Microsoft Teams(클래식) 사용 중지

2023년 4월 중순에 Microsoft는 **무료 Microsoft Teams(클래식)** 라이선스를 사용 중지합니다.

이 문서에서는 조직의 **무료 Microsoft Teams(클래식)** 라이선스를 사용 중지하고 유료 Teams 라이선스로 전환하는 방법에 대한 IT 관리자 지침을 제공합니다.

2023년 4월 중순까지 사용자의 무료 Teams 라이선스를 유료 Teams 라이선스로 이동하지 않으면 사용자는 Teams에 대한 액세스 권한을 잃게 됩니다.

이 프로세스를 완료하려면 다음 두 가지 방법 중 하나를 선택할 수 있습니다.

- [Microsoft 365 관리 센터 사용합니다.](#use-microsoft-365-admin-center-to-replace-licenses)
- [Microsoft PowerShell을 사용합니다.](#use-microsoft-powershell-to-replace-licenses)

조직에서 유료 Teams 라이선스로 마이그레이션하지 않기로 결정한 경우 Teams에서 조직의 콘텐츠를 내보낼 수 있습니다. Teams 콘텐츠를 내보내는 방법에 대한 지침은 [Microsoft Teams 내보내기 API를 사용하여 콘텐츠 내보내기를 참조하세요](/microsoftteams/export-teams-content).

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>Microsoft 365 관리 센터 사용하여 라이선스 교체

조직에 **Teams 무료(클래식)** 라이선스를 할당한 사용자가 거의 없는 경우 라이선스를 제거하고 할당하기 위해 Microsoft 365 관리 센터 사용하는 것이 좋습니다.

### <a name="check-users-current-teams-licensing"></a>사용자의 현재 Teams 라이선스 확인

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) 로그인합니다.
1. 왼쪽 메뉴에서 **사용자** > 이동하여 [**활성 사용자를**](https://go.microsoft.com/fwlink/p/?linkid=834822) 선택하여 사용자에게 할당된 라이선스를 봅니다.
    1. 라이선스 열에는 해당 **라이선스** 가 할당된 사용자 옆에 **무료 Microsoft Teams(클래식)** 표시됩니다.
1. 왼쪽 메뉴에서 **청구** > 이동하여 [**라이선스를**](https://go.microsoft.com/fwlink/p/?linkid=842264) 선택하여 유료 Teams 라이선스가 있는지 확인합니다.
    1. 조직에 사용 가능한 라이선스가 있는 경우 [유료 Teams 라이선스 할당](#assign-paid-teams-licenses) 으로 건너뛰어 **Teams 무료(클래식)** 라이선스를 가진 사용자에게 해당 라이선스를 할당합니다.
1. 구매해야 하는 유료 Teams 라이선스(있는 경우)의 수를 결정합니다.

### <a name="purchase-paid-teams-licenses"></a>유료 Teams 라이선스 구매

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) **청구** > 이동하여 **서비스 구매를** 선택합니다.
1. **제품 보기를** 선택하여 사용 가능한 모든 라이선스를 봅니다.
1. **통신 및 공동 작업** 범주 필터를 선택하여 Teams 라이선스를 확인합니다.
1. **Teams 무료(클래식)** 를 대체하려는 유료 Teams 라이선스를 선택합니다.
    1. 최대 300석까지 사용할 수 있는 [**Teams Essentials** 라이선스](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF)를 사용하는 것이 좋습니다.
    1. 300명 이상의 좌석이 필요한 경우 [Microsoft 365 E1 라이선스를 구매하는](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA) 것이 좋습니다.
1. 구매하려는 라이선스 수를 입력한 다음 청구 빈도를 선택합니다.
1. **구매** 단추를 선택하여 구매 프로세스를 완료합니다.

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>관리 센터 Marketplace에서 라이선스 구매

일부 테넌트는 Microsoft 365 관리 센터 Marketplace에 액세스할 수 있습니다. 이러한 테넌트에서는 Marketplace에서 라이선스를 구매합니다.

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) 왼쪽 메뉴에서 **Marketplace** 를 선택합니다.
1. **모든 제품 탭을** 선택합니다.
1. **통신 및 공동 작업** 범주 필터를 선택하여 Teams 라이선스를 확인합니다.
1. **Teams 무료(클래식)** 를 대체하려는 유료 Teams 라이선스를 선택합니다.
1. 구매하려는 라이선스 수를 입력한 다음 청구 빈도를 선택합니다.
1. **구매** 단추를 선택하여 구매 프로세스를 완료합니다.

### <a name="assign-paid-teams-licenses"></a>유료 Teams 라이선스 할당

1. **Teams 무료(클래식)** 라이선스를 대체할 준비가 되면 Microsoft 365 관리 센터 **사용자** > [**활성 사용자**](https://admin.microsoft.com/adminportal/home#/users)로 이동합니다.
1. **라이선스** 열에 나열된 **Teams 무료(클래식)** 라이선스가 있는 모든 사용자를 선택합니다.
1. 관리 센터 맨 위에서 **제품 라이선스 관리** 옵션을 선택합니다.
1. 오른쪽 창에서 **바꾸기** 를 선택합니다.
    1. **바꾸기** 옵션을 선택하려면 해당 사용자에게 할당하려는 모든 라이선스를 다시 선택해야 합니다. 새 유료 Teams 라이선스만 선택하는 경우 해당 사용자가 할당한 다른 라이선스가 사용자에서 제거되고 Teams 라이선스로 대체됩니다.
    1. 사용자에게 라이선스 요구 사항이 다른 경우 사용자를 잘못 라이선스하지 않도록 일괄 처리로 이 프로세스를 완료합니다.
1. 라이드 사이드 창에서 새 유료 Teams 라이선스 및 사용자에게 할당해야 하는 다른 라이선스를 선택한 다음 **변경 내용 저장** 단추를 선택합니다.

## <a name="use-microsoft-powershell-to-replace-licenses"></a>Microsoft PowerShell을 사용하여 라이선스 교체

조직에 **Teams 무료(클래식)** 라이선스가 할당된 사용자가 많은 경우 PowerShell을 사용하여 사용자에게 라이선스를 대량 할당 해제하고 할당하는 것이 좋습니다.

이 프로세스를 완료하려면 Teams **무료(클래식)** 라이선스가 할당된 사용자에 대한 유료 Teams 라이선스가 필요합니다. 해당 사용자에 대한 라이선스를 구입하려면 [유료 Teams 라이선스 구매를 참조하세요](#purchase-paid-teams-licenses).

1. Microsoft 365 테넌트 를 [Microsoft Graph PowerShell SDK에](/powershell/microsoftgraph/get-started) 연결합니다.
1. Microsoft PowerShell 데스크톱 앱을 엽니다.
1. [Graph API 대한 사용자 및 조직 권한을 설정합니다](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk).
1. [사용자 계정에서 **Teams 무료(클래식)** 라이선스를 제거합니다](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts).
1. [사용자에게 유료 Teams 라이선스를 할당합니다](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts).

Graph PowerShell SDK 프로세스에 대한 자세한 내용은 [Microsoft Graph PowerShell SDK 사용을 참조하세요](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell).
