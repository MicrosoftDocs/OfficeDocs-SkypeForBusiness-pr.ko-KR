---
title: 무료 Office 365 E1 평가판 관리
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 6146b6d4a7ca3d988c5dc1042a7f75848cf4fc7b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092666"
---
<a name="manage-the-office-365-e1-trial"></a>Office 365 E1 평가판 관리
==============================

2020년 7월 1일부터 Office 365 E1 평가판 라이선스를 더 이상 사용할 수 없습니다. 사용자에게 Microsoft Teams의 라이선스를 설정해야 하는 경우 Teams를 포함한 유료 구독 목록의 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 참조하세요. 또는 적격 조직의 경우 **[무료 버전의 Teams](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)** 를 사용하거나 직원들이 **[Teams 예비](teams-exploratory.md)** 환경을 활성화할 수 있습니다.


교육용 Teams 고객이라면 무료 [Office 365 A1 라이선스](teams-edu-licensing.md)를 확인하세요.

이 문서의 안내에 따라 [유료 구독으로 업그레이드](#upgrade-users-from-the-office-365-e1-trial-license)를 포함하여 기존 Office 365 E1 평가판 라이선스를 관리합니다.

[Teams로 원격 작업자 지원](support-remote-work-with-teams.md)을 위한 모든 Microsoft 지침을 놓치지 마세요.

## <a name="manage-the-e1-trial"></a>E1 평가판 관리

Office 365 E1 평가판을 활성화한 후에는 라이선스가 필요한 모든 용도에 대해 라이선스를 켭니다. 자세한 방법은 [Teams에 대한 사용자 액세스 관리](user-access.md)를 참조하세요.


E1 평가판이 필요한 사용자에 대해 E1 평가판을 켜면 유료 라이선스를 보유한 사용자를 관리하는 것처럼 이러한 사용자를 관리하게 됩니다. 자세한 내용은 [조직에서 Teams 설정 관리](enable-features-office-365.md)를 참조하세요.



### <a name="upgrade-users-from-the-office-365-e1-trial-license"></a>Office 365 E1 평가판 라이선스에서 사용자 업그레이드

E1 평가판 사용자를 유료 구독으로 업그레이드하려면 다음을 수행 합니다.

1. Teams를 포함하는 구독을 구입합니다.

2. 사용자에서 Office 365 E1 평가판 구독을 제거합니다.

3. 새로 구매한 라이선스를 할당합니다.

자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 참조하세요.

> [!NOTE]
> E1 평가판 라이선스가 종료되고 사용자가 Teams을 포함하는 구독으로 즉시 업그레이드 되지 않는 경우 사용자의 데이터는 제거되지 않습니다. 사용자는 여전히 Azure Active Directory에 존재하고 Teams 내의 모든 데이터는 계속 유지됩니다. Teams의 기능을 다시 사용할 수 있도록 사용자에게 새 라이선스가 할당되면 모든 콘텐츠가 계속 존재하게 됩니다. 

### <a name="remove-an-office-365-e1-trial-license"></a>Office 365 E1 평가판 라이선스 제거

- PowerShell을 통해 이 라이선스를 제거하려면 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)를 참조하세요.

- 관리 포털을 통해 이 라이선스를 제거하려면 [조직에서 사용자 제거](/microsoft-365/admin/add-users/delete-a-user)를 참조하세요.

## <a name="related-topics"></a>관련 항목

[Teams에 대한 사용자 액세스 관리](user-access.md)

[조직의 Teams 설정 관리](enable-features-office-365.md)

[Teams 예비 환경 관리](teams-exploratory.md)

[Microsoft 365 또는 Office 365 Nonprofit](https://www.microsoft.com/microsoft-365/nonprofit/office-365-nonprofit)

[Teams 배포 지원 받기](https://go.microsoft.com/fwlink/?linkid=780698)