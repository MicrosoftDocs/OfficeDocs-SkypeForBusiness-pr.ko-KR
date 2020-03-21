---
title: 무료 Office 365 E1 평가판 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aytange
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams가 없고 긴급히 필요한 경우 COVID-19(코로나 바이러스) 발생에 대응하여 원격 또는 재택 근무(WFH)가 필요한 사용자를 위해 Office 365 E1 평가판을 배포하십시오.
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 62b4add4e3371604478c8a49cc6690000d699f65
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858773"
---
<a name="manage-the-office-365-e1-trial"></a>Office 365 E1 평가판 관리
==============================

2020년 3월 Microsoft Teams를 포함한 6 개월 무료 Office 365 E1 평가판을 새롭게 사용할 수 있습니다. Microsoft는 COVID-19(코로나 바이러스) 발생에 대응하여 직원들이 재택 근무 (WFH)에 대한 필요성이 증가함에 따라 이 특별 E1 평가판 라이선스를 제공하고 있습니다. 

E1 라이선스로 사용할 수 있는 기능을 알아보려면 [Office 365 E1](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e1-business-software)을 참조하세요.

[Teams로 원격 작업자를 지원](support-remote-work-with-teams.md)하기 위한 모든 지침을 놓치지 마세요.

## <a name="how-to-get-an-e1-trial-license"></a>E1 평가판 라이선스를 얻는 방법

Microsoft 계정 담당자에게 문의하세요. E1 평가판에 등록하는 데 사용할 수 있는 프로모션 코드가 제공됩니다. 

조직이 Microsoft 파트너의 서비스를 받는 경우 파트너와 협의하여 Teams 6개월 무료 평가판을 받으세요. 아직 Microsoft 파트너가 없으나 협력하기를 원하면 [Microsoft 솔루션 공급자](https://www.microsoft.com/solution-providers/home)로 가서 Teams에 대한 전문 지식을 지닌 파트너를 검색하세요.


## <a name="how-to-sign-up-for-e1"></a>E1 가입 방법

계정 담당자가 발송할 이메일에서 프로모션 코드를 클릭하세요. 


## <a name="whos-eligible"></a>사용 자격이 있는 사용자

이 서비스는 Microsoft 계정 담당자가 관리하는 모든 고객을 위한 것입니다. 과거에 다른 Office 365 E1 평가판을 활성화하지 않은 조직(비영리 포함)을 위한 것입니다. 

E1 평가판 프로모션 코드를 사용한 후에는 이 코드를 다시 사용할 수 없으며 다른 E1 평가판 코드를 활성화 할 수 없습니다. 이 경우 직원이 [Teams 예비 라이선스](teams-exploratory.md)를 활성화하도록 할 수 있습니다.

## <a name="who-isnt-eligible"></a>사용 자격이 없는 사용자

- 이 서비스는 GCC, GCC High, DoD 또는 EDU 고객에게는 제공되지 않습니다. 

- GCC의 경우 [Office 365 G1 평가판](g1-trial-license.md)를 확인하세요. 

- EDU 고객은 무료 Office 365 A1 라이선스를 사용해야 합니다.

## <a name="manage-the-e1-trial"></a>E1 평가판 관리

Office 365 E1 평가판을 활성화한 후에는 라이선스가 필요한 모든 용도에 대해 라이선스를 켭니다. 자세한 방법은 [Teams에 대한 사용자 액세스 관리](user-access.md#manage-teams-through-the-microsoft-365-admin-center)를 참조하세요.


E1 평가판이 필요한 사용자에 대해 E1 평가판을 켜면 유료 라이선스를 보유한 사용자를 관리하는 것처럼 이러한 사용자를 관리하게 됩니다. 자세한 내용은 [조직에서 Teams 설정 관리](enable-features-office-365.md)를 참조하세요.



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Office 365 E1 평가판 라이선스에서 사용자 업그레이드

E1 평가판 사용자를 유료 구독으로 업그레이드하려면 다음을 수행 합니다.

1. Teams를 포함하는 구독을 구입합니다.

2. 사용자에서 Office 365 E1 평가판 구독을 제거합니다.

3. 새로 구매한 라이선스를 할당합니다.

자세한 내용은 [Microsoft Teams 사용을 위한 Office 365 라이선싱](Office-365-licensing.md)을 참조하세요.

> [!NOTE]
> E1 평가판 라이선스가 종료되고 사용자가 Teams을 포함하는 구독으로 즉시 업그레이드 되지 않는 경우 사용자의 데이터는 제거되지 않습니다. 사용자는 여전히 Azure Active Directory에 존재하고 Teams 내의 모든 데이터는 계속 유지됩니다. Teams의 기능을 다시 사용할 수 있도록 사용자에게 새 라이선스가 할당되면 모든 콘텐츠가 계속 존재하게 됩니다. 

### <a name="remove-an-office-365-e1-trial-license"></a>Office 365 E1 평가판 라이선스 제거

- PowerShell을 통해 이 라이선스를 제거하려면 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)를 참조하세요.

- 관리 포털을 통해 이 라이선스를 제거하려면 [비즈니스용 Office 365의 사용자 라이선스 제거](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)를 참조하세요. 


## <a name="related-topics"></a>관련 항목

[Teams에 대한 사용자 액세스 관리](user-access.md#manage-teams-through-the-microsoft-365-admin-center)

[조직의 Teams 설정 관리](enable-features-office-365.md)

[Teams 예비 환경 관리](teams-exploratory.md)

[Office 365 Nonprofit](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)