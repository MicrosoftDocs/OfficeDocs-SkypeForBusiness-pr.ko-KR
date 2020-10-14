---
title: Microsoft 365 그룹 및 Microsoft 팀
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
description: Microsoft 365 그룹 및 그룹 구성원이 Microsoft 팀과 어떻게 작동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456082"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 그룹 및 Microsoft 팀

Microsoft 365 그룹은 Microsoft 365의 응용 프로그램 간 구성원 서비스입니다. Microsoft 365 그룹은 기본 수준에서 SharePoint 팀 사이트, 공유 Exchange 사서함, Planner 및 Power BI 작업 영역을 비롯 한 관련 작업에 대 한 결합 및 구성원 목록이 있는 Azure Active Directory의 개체입니다. Active Directory의 다른 그룹 기반 보안 개체와 마찬가지로 그룹에 사용자를 추가 하거나 제거할 수 있습니다.

![Microsoft 365 그룹 및 관련 서비스를 보여 주는 다이어그램](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

기본적으로 Microsoft 365의 사용자는 그룹을 만들고 관리할 수 있습니다. Microsoft 365 그룹에 대 한 자세한 내용은 microsoft [365 그룹](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 및 [IT 설계자 포스터 용 Microsoft 365의 그룹](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 에 대 한 자세한 내용을 참조 하세요.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 그룹이 팀과 공동 작업 하는 방법

팀을 만들 때 팀 구성원을 관리 하기 위해 Microsoft 365 그룹이 만들어집니다. SharePoint 사이트, Power BI 작업 영역 등 그룹의 관련 서비스가 동시에 만들어집니다.

팀을 만든 사용자는 해당 그룹의 소유자 인 경우 기존 Microsoft 365 그룹을 사용 하도록 선택할 수 있습니다. 팀의 각 채널에는 문서 라이브러리에 별도의 폴더가 있습니다. 문서 라이브러리에서 직접 폴더를 만들면 팀에서 채널을 만들 수 없습니다.

Outlook 또는 SharePoint에서 Microsoft 365 그룹을 만들면 Outlook에서 그룹 사서함이 표시 됩니다. 팀에서 팀을 만들 때 그룹 사서함은 기본적으로 숨겨져 있습니다. **HiddenFromExchangeClientsEnabled** 매개 변수와 함께 [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet을 사용 하 여 사서함을 표시할 수 있습니다.

## <a name="group-membership"></a>그룹 구성원

팀 구성원을 제거 하면 Microsoft 365 그룹 에서도 제거 됩니다. 그룹에서 제거 하면 팀 클라이언트에서 팀과 채널이 즉시 제거 됩니다. Microsoft 365 관리 센터를 사용 하 여 그룹에서 사용자를 제거 하는 경우에는 더 이상 SharePoint Online 문서 라이브러리, Yammer 그룹 또는 공유 OneNote와 같은 다른 공동 작업에 액세스할 수 없습니다. 그러나 약 2 시간 동안 팀의 채팅 기능에 계속 액세스할 수 있습니다.

팀 구성원을 관리 하는 가장 좋은 방법으로, 다른 그룹 연결 작업에 대 한 사용 권한 업데이트가 빠르게 발생 하도록 팀 클라이언트에서 추가 하거나 제거 합니다. 팀 클라이언트 (예를 들어 Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell을 사용 하 여)를 추가 하거나 제거 하는 경우 변경 내용이 팀에 반영 되는 데 최대 24 시간이 걸릴 수 있습니다.

## <a name="deleting-groups-and-teams"></a>그룹 및 팀 삭제

Microsoft 365 그룹을 삭제 하면 영구 Outlook/OWA 대화 및 팀 모임 초대에 대 한 사서함 별칭이 제거 되 고 SharePoint 사이트를 삭제 하도록 표시 합니다. 팀을 제거 하는 시간과 Outlook에 미치는 영향 사이에 약 20 분이 걸립니다. 팀 클라이언트에서 팀을 삭제 하면 해당 팀의 구성원 인 모든 사용자가 보기에서 즉시 제거 됩니다. 팀 기능을 사용할 수 있는 Microsoft 365 그룹의 구성원을 제거 하는 경우 팀 클라이언트에서 해당 사용자가 제거 된 영향을 받는 사람을 보기에서 제거 하기 전에 약 2 시간이 지연 될 수 있습니다.

수명 주기 옵션의 그룹 및 팀 종료에 대 한 자세한 내용은  [그룹, 팀 및 Yammer에 대 한 주기 옵션 종료](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 와 [Microsoft 팀에서 팀 보관 또는 삭제](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)를 참고 하세요.

## <a name="related-topics"></a>관련 항목

[Microsoft 팀의 기초 (비디오)](https://aka.ms/teams-foundations)

[삭제 된 그룹 복원](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)