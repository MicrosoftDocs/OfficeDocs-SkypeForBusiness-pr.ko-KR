---
title: Microsoft 365 그룹 및 Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 그룹 및 Microsoft 365 구성원 자격이 어떻게 작동하는지 Microsoft Teams.
ms.openlocfilehash: 4e140d50bb16c9ed99f126662545fb026c3df60a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729737"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 그룹 및 Microsoft Teams

Microsoft 365 그룹은 애플리케이션 간 멤버 자격 Microsoft 365. 기본 수준에서 Microsoft 365 그룹은 Azure Active Directory 팀 사이트, 공유 사서함, 플래너 및 Azure Active Directory SharePoint 작업 영역과 같은 관련 워크로드에 Exchange 있는 Power BI 개체입니다. Active Directory의 다른 그룹 기반 보안 개체와 같은 사용자 그룹을 그룹에 추가하거나 제거할 수 있습니다.

![그룹 및 Microsoft 365 서비스를 보여주는 다이어그램입니다.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

기본적으로 Microsoft 365 그룹을 만들고 관리할 수 있습니다. 그룹에 대한 Microsoft 365 자세한 내용은 [](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) [IT](teams-architecture-solutions-posters.md#groups-in-microsoft-365) Microsoft 365 그룹의 Microsoft 365 포스터를 참조하세요.

## <a name="how-microsoft-365-groups-work-with-teams"></a>그룹 Microsoft 365 작업하는 Teams

팀을 만들 때 팀 멤버 자격을 Microsoft 365 그룹이 만들어집니다. 그룹 관련 서비스(예: SharePoint 사이트, Power BI 작업 영역 등)가 동시에 만들어집니다.

팀을 만드는 사람은 해당 그룹의 소유자인 경우 기존 Microsoft 365 그룹을 사용할 수 있습니다. 팀의 각 채널에는 문서 라이브러리에 별도의 폴더가 있습니다. 문서 라이브러리에서 직접 폴더를 만들면 팀에서 채널이 생성되지 않습니다.

그룹 Microsoft 365 또는 Outlook SharePoint 그룹 사서함이 Outlook. 팀을 만들 때 Teams 사서함은 기본적으로 숨겨집니다. **HiddenFromExchangeClientsEnabled** 매개 변수와 함께 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet을 사용하여 사서함을 볼 수 있습니다.

## <a name="group-membership"></a>그룹 멤버 자격

팀 구성원을 제거하면 팀 그룹도 Microsoft 365 제거됩니다. 그룹에서 제거하면 팀 및 채널이 클라이언트에서 Teams 제거됩니다. 그룹을 사용하여 그룹에서 사람을 제거하면 Microsoft 365 관리 센터 온라인 문서 라이브러리, SharePoint 그룹 또는 공유 Yammer 같은 다른 공동 작업 측면에 더 이상 액세스할 수 OneNote. 그러나 약 2시간 동안 팀의 채팅 기능에 액세스할 수 있습니다.

팀 구성원을 관리하는 모범 사례로, 다른 그룹 연결 워크로드에 대한 사용 권한이 Teams 클라이언트에서 추가하고 제거합니다. PowerShell을 사용하여 Teams 외부에서 팀 구성원을 추가하거나 제거하는 경우(Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell을 사용하여) 변경 내용이 변경 내용에 반영되는 데 최대 24시간이 Teams.

## <a name="deleting-groups-and-teams"></a>그룹 및 팀 삭제

Microsoft 365 삭제하면 영구 Outlook/OWA 대화 및 Teams 모임 초대에 대한 사서함 별칭이 제거되고 SharePoint 사이트가 삭제됩니다. 팀을 제거하고 팀에 영향을 미치기까지 약 20분이 Outlook. 팀에서 팀을 Teams 클라이언트는 보기에서 팀 구성원인 모든 사용자로 즉시 제거됩니다. 해당 기능을 사용하도록 Microsoft 365 있는 Teams 그룹의 구성원을 제거하는 경우 팀이 제거된 영향을 받는 Teams 보기에서 팀이 제거되기까지 약 2시간이 지연될 수 있습니다.

수명 주기 옵션의 그룹 및 팀 종료 [](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 옵션에 대한 자세한 내용은 그룹, 팀 및 Yammer 수명 주기 종료 옵션을 참조하고 팀을 [Microsoft Teams.](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>관련 항목

[기본 Microsoft Teams(비디오)](https://aka.ms/teams-foundations)

[삭제된 그룹 복원](/microsoft-365/admin/create-groups/restore-deleted-group)