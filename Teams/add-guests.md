---
title: 팀에 게스트 추가
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: 관리자는 Microsoft Teams 데스크톱 및 웹 클라이언트와 Azure Active Directory B2B 공동 작업 포털의 조직에 새 게스트 사용자를 추가하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60538383021028d043cb47197dd41ee89f8a4d37
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139367"
---
<a name="add-a-guest-to-a-team"></a>팀에 게스트 추가
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 Teams에서 게스트로 참여할 수 있습니다.

관리자는 다음과 같은 두 가지 방법으로 조직에 새 게스트 사용자를 추가할 수 있습니다.
- 전역 관리자 또는 Teams 관리자와 팀 소유자가 Teams 클라이언트나 Teams 관리 센터에서 팀에 게스트를 추가합니다. 자세한 내용을 보려면 [팀에 게스트 추가](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)를 읽으세요. 아직 게스트 액세스를 설정하지 않은 경우 [게스트 액세스 검사 목록](guest-access-checklist.md)의 단계를 진행합니다.

> [!NOTE] 
> **관리자 및 게스트 초대자 역할의 사용자가 초대할 수 있음**을 사용하도록 설정한 경우에는 적용되지 않습니다. 게스트 초대자 역할은 Teams에서 지원되지 않기 때문입니다.

- Azure AD(Azure Active Directory) B2B 공동 작업을 통해 조직에 게스트를 추가합니다. Azure AD B2B 공동 작업에서는 전역 관리자가 쉼표로 구분된 값(CSV) 파일(라인 2,000개 이하)을 B2B 공동 작업 포털에 업로드하여 외부 사용자 집단을 초대하고 권한을 부여할 수 있습니다. 자세한 내용은 [Azure Active Directory B2B 공동 작업](https://go.microsoft.com/fwlink/p/?linkid=826383)을 확인하세요.

Azure AD B2B 공동 작업을 통해 조직에서는 B2B 사용자에 대한 조건부 액세스 및 MFA(Multi-Factor Authentication) 정책을 적용할 수 있습니다. 조직의 전일제 직원과 구성원에 대해 이러한 정책을 사용하는 것과 같은 방법으로 이러한 정책을 테넌트, 앱 또는 개별 사용자 수준에서 적용할 수 있습니다. 이러한 정책은 리소스 조직에서 적용됩니다. 자세한 내용은 [B2B 공동 작업 사용자에 대한 조건부 액세스](https://go.microsoft.com/fwlink/?linkid=857454)를 참조하세요. 개별 게스트 사용자는 차단할 수 없습니다.

Azure AD B2B, Office 365 그룹 또는 SharePoint Online을 통해 이미 추가한 게스트 사용자는 준비가 되어 있습니다. Office 365 관리자 또는 팀 소유자는 해당 게스트를 각 팀에 추가할 수 있습니다. 팀이 이미 Office 365 그룹을 사용하고 있고 게스트가 그룹에 추가되는 경우, 해당 게스트는 팀에 대한 액세스 권한을 얻게 됩니다. Office 365 그룹을 통해 게스트를 추가하는 경우에는 게스트에게 초대 전자 메일이 생성되지 않습니다. 그러므로 팀의 구성원이 게스트에게 알려야 합니다.

> [!NOTE]
> 게스트는 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 서비스 제한에 영향을 받습니다.

Azure AD 또는 Office 365 보안 &amp; 준수 센터에서 게스트 추가를 추적할 수 있습니다. Microsoft Teams에서 게스트 추가가 감사되고 Azure AD 그룹 관리 작업 “그룹에 구성원이 추가됨”으로 기록됩니다. 자세한 내용은 [B2B 공동 작업 사용자 감사 및 보고](https://go.microsoft.com/fwlink/p/?linkid=858884)와 [Office 365 보안 &amp; 준수 센터에서 감사 로그 검색](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)을 참조하세요.


## <a name="more-information"></a>추가 정보

[Microsoft Teams에서 게스트 액세스 권한 부여](teams-dependencies.md)</br>
[Microsoft Teams에서 게스트 액세스 설정 또는 해제](set-up-guests.md)</br>
[PowerShell을 사용하여 팀에 대한 액세스 권한 제어](guest-access-powershell.md)
