---
title: 팀에 게스트 추가
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: 관리자는 Microsoft Teams 데스크톱 및 웹 클라이언트 및 Azure Active Directory B2B 공동 작업 포털에서 조직에 새 게스트를 추가하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109084"
---
# <a name="add-a-guest-to-a-team"></a>팀에 게스트 추가

비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 Teams에서 게스트로 참여할 수 있습니다.

관리자는 몇 가지 방법으로 조직에 새 게스트를 추가할 수 있습니다.

- 전역 관리자 또는 Teams 관리자와 팀 소유자가 Teams 클라이언트나 Teams 관리 센터에서 팀에 게스트를 추가합니다. 자세한 내용을 보려면 [팀에 게스트 추가](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)를 읽으세요. 아직 게스트 액세스를 설정하지 않은 경우 [팀 내 게스트와의 공동 작업](/microsoft-365/solutions/collaborate-as-team) 단계를 수행합니다.

- Azure AD(Azure Active Directory) B2B 공동 작업을 통해 조직에 게스트를 추가합니다. 자세한 내용은 빠른 [시작: Azure Portal의 디렉터리에 게스트 추가를 참조하세요.](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)

관리자는 게스트 초대자 역할을 할당하여 조직의 다른 사용자에게 게스트를 추가할 수 있는 권한을 위임할 수도 있습니다. 자세한 내용은 [B2B 외부 공동 작업 사용 및 게스트를 초대할 수 있는 사용자 관리하기](/azure/active-directory/external-identities/delegate-invitations)를 참조하세요.

Azure AD B2B 공동 작업을 통해 조직에서는 B2B 사용자에 대한 조건부 액세스 및 MFA(Multi-Factor Authentication) 정책을 적용할 수 있습니다. 조직의 전일제 직원과 구성원에 대해 이러한 정책을 사용하는 것과 같은 방법으로 이러한 정책을 테넌트, 앱 또는 개별 사용자 수준에서 적용할 수 있습니다. 이러한 정책은 리소스 조직에서 적용됩니다. 자세한 내용은 [B2B 공동 작업 사용자에 대한 조건부 액세스](/azure/active-directory/external-identities/conditional-access)를 참조하세요. 개별 게스트를 차단할 수 없습니다.

Azure AD B2B, Microsoft 365 그룹 또는 SharePoint를 통해 이미 추가한 게스트가 준비되었습니다. Microsoft 365 관리자 또는 팀 소유자는 해당 게스트를 해당 팀에 추가할 수 있습니다. 팀과 연결된 Microsoft 365 그룹에 게스트를 직접 추가하면 게스트가 팀에 액세스할 수 있지만 Microsoft 365 그룹은 게스트에 대한 초대 전자 메일을 생성하지 않습니다. 따라서 팀의 다른 사용자가 게스트에게 알릴 수 있습니다.

> [!NOTE]
> 게스트는 [Microsoft 365 또는 Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) 및 [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) 서비스 제한에 영향을 받습니다.

Azure AD 또는 Microsoft 365 보안 센터에서 게스트 추가를 추적할 수 있습니다. Microsoft Teams에서 게스트 추가가 감사되고 Azure AD 그룹 관리 작업 “그룹에 구성원이 추가됨”으로 기록됩니다. 자세한 내용은 [B2B](/azure/active-directory/external-identities/auditing-and-reporting) 공동 작업 사용자 감사 및 보고를 참조하고 준수 센터에서 감사 [로그 검색을 참조합니다.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)


## <a name="related-topics"></a>관련 항목

[Microsoft Teams에서 게스트 액세스 권한 부여](teams-dependencies.md)

[Microsoft Teams에서 게스트 액세스 설정 또는 해제](set-up-guests.md)