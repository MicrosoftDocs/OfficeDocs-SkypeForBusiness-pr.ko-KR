---
title: Microsoft 365 그룹 및 Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Microsoft 365 그룹 및 그룹 멤버 자격이 Microsoft Teams와 함께 작동 하는 방법에 대해 자세히 배워야 합니다.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456082"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 그룹 및 Microsoft Teams

Microsoft 365 그룹은 Microsoft 365의 애플리케이션 간 멤버 자격 서비스입니다. 기본 수준에서 Microsoft 365 그룹은 구성원 목록이 있는 Azure Active Directory의 개체로, SharePoint 팀 사이트, 공유 Exchange 사서함, Planner 및 Power BI 작업 영역과 같은 관련 워크로드와의 연관이 있습니다. Active Directory의 다른 그룹 기반 보안 개체와 같은 사용자도 그룹에 추가하거나 제거할 수 있습니다.

![Microsoft 365 그룹 및 관련 서비스를 보여주는 다이어그램](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

기본적으로 Microsoft 365의 사용자는 그룹을 만들고 관리할 수 있습니다. Microsoft 365 그룹에 대한 자세한 내용은 [Microsoft 365 그룹](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 및 IT 설계자 포스터용 [Microsoft 365의](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 그룹에 대해 자세히 참조하세요.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 그룹이 Teams와 함께 작동 하는 방법

팀을 만들면 팀 멤버 자격을 관리하기 위해 Microsoft 365 그룹이 만들어집니다. SharePoint 사이트, Power BI 작업 영역 등 그룹의 관련 서비스가 동시에 만들어집니다.

팀을 만드는 사람은 해당 그룹의 소유자인 경우 기존 Microsoft 365 그룹을 사용할 수 있습니다. 팀의 각 채널에는 문서 라이브러리에 별도의 폴더가 있습니다. 문서 라이브러리에서 직접 폴더를 만들면 팀에서 채널이 생성되지 않습니다.

Outlook 또는 SharePoint에서 Microsoft 365 그룹을 만들 때 Outlook에 그룹 사서함이 표시됩니다. Teams에서 팀을 만들 때 그룹 사서함은 기본적으로 숨겨져 있습니다. **HiddenFromExchangeClientsEnabled** 매개 변수와 [함께 Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet을 사용하여 사서함을 볼 수 있습니다.

## <a name="group-membership"></a>그룹 멤버 자격

팀 구성원을 제거하면 Microsoft 365 그룹에서 제거됩니다. 그룹에서 제거하면 Teams 클라이언트에서 팀 및 채널이 즉시 제거됩니다. Microsoft 365 관리 센터를 사용하여 그룹에서 사람을 제거하면 더 이상 SharePoint Online 문서 라이브러리, Yammer 그룹 또는 공유 OneNote와 같은 다른 공동 작업 측면에 액세스할 수 없습니다. 그러나 약 2시간 동안 팀의 채팅 기능에 계속 액세스할 수 있습니다.

팀 구성원을 관리하는 모범 사례로 Teams 클라이언트에서 추가 및 제거하여 다른 그룹 연결 워크로드에 대한 사용 권한 업데이트가 신속하게 진행되도록 합니다. Teams 클라이언트 외부에서 팀 구성원을 추가하거나 제거하는 경우(Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell 사용) 변경 내용이 Teams에 반영되는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="deleting-groups-and-teams"></a>그룹 및 팀 삭제

Microsoft 365 그룹을 삭제하면 영구적인 Outlook/OWA 대화 및 Teams 모임 초대에 대한 사서함 별칭이 제거되고 SharePoint 사이트를 삭제로 표시하게 됩니다. 팀을 제거하고 Outlook에 영향을 미치기까지 약 20분이 걸립니다. Teams 클라이언트에서 팀을 삭제하면 팀의 구성원이 모두 볼 수 있는 팀이 즉시 제거됩니다. Teams 기능을 사용하도록 설정한 Microsoft 365 그룹의 구성원을 제거하는 경우 팀이 제거된 영향을 받는 사용자에 대한 Teams 클라이언트의 보기에서 팀이 제거되기까지 약 2시간이 지연될 수 있습니다.

그룹 및 팀의 수명 주기 종료 옵션에 대한 자세한 내용은 Microsoft Teams에서 [그룹,](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 팀 및 Yammer 및 보관 또는 삭제에 대한 수명 주기 종료 옵션을 [참조하세요.](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)

## <a name="related-topics"></a>관련 항목

[Microsoft Teams의 기초(비디오)](https://aka.ms/teams-foundations)

[삭제된 그룹 복원](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)