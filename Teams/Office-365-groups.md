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
description: Microsoft 365 그룹 및 그룹 멤버 자격이 Microsoft Teams 작동하는 방법에 대해 알아봅니다.
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125433"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 그룹 및 Microsoft Teams

Microsoft 365 그룹 Microsoft 365 애플리케이션 간 멤버 자격 서비스입니다. 기본 수준에서 Microsoft 365 그룹은 구성원 목록과 SharePoint 팀 사이트, 공유 Exchange 사서함, Planner 및 OneNote Notebook을 포함한 관련 워크로드에 결합된 Azure Active Directory 개체입니다. Active Directory의 다른 그룹 기반 보안 개체와 마찬가지로 그룹에 사용자를 추가하거나 제거할 수 있습니다.

![Microsoft 365 그룹 및 관련 서비스를 보여 주는 다이어그램](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

기본적으로 Microsoft 365 사용자는 그룹을 만들고 관리할 수 있습니다. Microsoft 365 그룹 대한 자세한 내용은 [IT 설계자](teams-architecture-solutions-posters.md#groups-in-microsoft-365)용 [Microsoft 365 Microsoft 365 그룹 및 그룹에 대한 자세한 내용을 참조하세요](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

## <a name="how-microsoft-365-groups-work-with-teams"></a>Microsoft 365 그룹 Teams 작동하는 방법

팀을 만들 때 팀 멤버 자격을 관리하기 위해 Microsoft 365 그룹이 만들어집니다. SharePoint 사이트, 사서함 등과 같은 그룹의 관련 서비스가 동시에 만들어집니다.

팀을 만드는 사용자는 해당 그룹의 소유자인 경우 기존 Microsoft 365 그룹을 사용하도록 선택할 수 있습니다. 팀의 각 채널에는 문서 라이브러리에 별도의 폴더가 있습니다. 문서 라이브러리에서 직접 폴더를 만들면 팀에서 채널을 만들지 않습니다.

Outlook 또는 SharePoint Microsoft 365 그룹을 만들 때 그룹 사서함은 Outlook 표시됩니다. Teams 팀을 만들 때 그룹 사서함은 기본적으로 숨겨집니다. **HiddenFromExchangeClientsEnabled** 매개 변수와 함께 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet을 사용하여 사서함을 표시할 수 있습니다.

## <a name="group-membership"></a>그룹 멤버 자격

팀의 구성원을 제거하면 Microsoft 365 그룹에서도 제거됩니다. 그룹에서 제거하면 Teams 클라이언트에서 팀과 채널이 즉시 제거됩니다. Microsoft 365 관리 센터 사용하여 그룹에서 사용자를 제거하는 경우 SharePoint Online 문서 라이브러리, Yammer 그룹 또는 공유 OneNote 같은 다른 공동 작업 측면에 더 이상 액세스할 수 없습니다. 그러나 약 2시간 동안 팀의 채팅 기능에 액세스할 수 있습니다.

팀 구성원을 관리하는 모범 사례로 Teams 클라이언트에서 추가 및 제거하여 다른 그룹 연결 워크로드에 대한 권한 업데이트가 신속하게 수행되도록 합니다. Microsoft 365 관리 센터, Azure AD 또는 Exchange Online PowerShell을 사용하여 Teams 클라이언트 외부에서 팀 구성원을 추가하거나 제거하는 경우 변경 내용이 Teams 반영되는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="deleting-groups-and-teams"></a>그룹 및 팀 삭제

Microsoft 365 그룹을 삭제하면 영구 Outlook/OWA 대화 및 Teams 모임 초대에 대한 사서함 별칭이 제거되고 SharePoint 사이트에서 삭제됩니다. 팀을 제거하고 Outlook 미치는 영향까지 약 20분이 걸립니다. Teams 클라이언트에서 팀을 삭제하면 팀의 구성원인 모든 사용자에게 즉시 제거됩니다. Teams 기능을 사용하도록 설정한 Microsoft 365 그룹의 구성원을 제거하면 팀이 제거된 영향을 받는 사용자에 대한 Teams 클라이언트에서 보기에서 제거되기까지 약 2시간 정도 지연될 수 있습니다.

그룹 및 팀 수명 주기 종료 옵션에 대한 자세한 내용은 [그룹, 팀 및 Yammer 수명 주기 종료 옵션을](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) 참조하고 [Microsoft Teams 팀을 보관하거나 삭제](./archive-or-delete-a-team.md)합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft Teams 기초(동영상)](https://aka.ms/teams-foundations)

[삭제된 그룹 복원](/microsoft-365/admin/create-groups/restore-deleted-group)
