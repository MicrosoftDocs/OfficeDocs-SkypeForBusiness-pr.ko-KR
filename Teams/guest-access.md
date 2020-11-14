---
title: Microsoft Teams의 게스트 액세스
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Microsoft Teams의 게스트 액세스를 사용하면 조직의 팀에서 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다.
ms.openlocfilehash: cab51fd9cf0a81c849a0baf379150ccb2e08d818
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030284"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams의 게스트 액세스

게스트 액세스를 사용 하면 조직 외부의 사용자에 게 팀, 채널, 리소스, 채팅, 응용 프로그램에 대 한 액세스를 제공 하 여 회사 데이터에 대 한 제어를 유지할 수 있습니다.

게스트는 직원, 학생 또는 조직의 구성원이 아닌 사용자입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다. 예를 들어, 게스트에는 파트너, 공급 업체, 공급자 또는 컨설턴트 등이 포함될 수 있습니다. 조직에 속하지 않은 사용자를 Teams에서 게스트로 추가할 수 있습니다. 즉, 비즈니스 계정 (즉, Azure Active Directory 계정) 또는 소비자 전자 메일 계정 (Outlook.com, Gmail.com 등)을 사용 하는 모든 사용자가 팀에서 게스트로 참여할 수 있으며,이에 따라 팀과 채널 환경에 대 한 액세스 권한이 있습니다.

팀 관리자는 [게스트가 팀에 사용할 수 있는 기능을 제어](manage-guests.md)합니다. 팀의 게스트는 Microsoft 365의 나머지와 동일한 준수 및 감사 보호를 통해 다루고 있으며, Azure AD 내에서 관리할 수 있습니다. 게스트 액세스에는 Azure AD 및 Microsoft 365 또는 Office 365 서비스 제한이 적용됩니다.

게스트 환경에는 디자인별로 제약 사항이 있습니다. 게스트가 팀에서 수행할 수 있는 작업에 대 한 전체 목록은 [팀 구성원 및 게스트 기능 비교](guest-experience.md#comparison-of-team-member-and-guest-capabilities)를 참조 하세요.

> [!IMPORTANT]
> 게스트 사용자는 동시 업그레이드 모드를 위해 Temas 조직 전체 설정을 따릅니다. 변경할 수 없습니다.

외부 액세스 (페더레이션)와 게스트 액세스를 비교하려면 (어느 것을 사용할 지 결정하려면) [Teams의 다른 조직의 사용자와 커뮤니케이션](communicate-with-users-from-other-organizations.md)을 참조하세요.

## <a name="set-up-guest-access"></a>게스트 액세스 설정

팀에서 게스트 액세스를 사용 하려면 Azure AD, Microsoft 365 그룹, SharePoint의 설정을 포함 하 여 Microsoft 365의 다른 설정을 구성 해야 합니다. 팀에 게스트 초대를 시작할 준비가 되었으면 다음 중 하나를 읽어 보세요.

- 일반적인 사용을 위해 팀에 대 한 게스트 액세스를 구성 하려면 [팀에서 게스트 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조 하세요.
- Azure Active Directory를 사용 하 고 게스트가 팀 액세스를 자체 등록할 수 있도록 허용 하는 파트너 조직과 공동 작업 하려면 [관리 되는 게스트를 사용 하 여 B2B 엑스트라넷 만들기](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)를 참조 하세요.

팀에서 게스트 액세스는 조직 전체에서 설정 되며 기본적으로 꺼져 있습니다. [민감도 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)사용 하 여 개별 팀에 대 한 게스트 액세스를 제어할 수 있습니다.

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>게스트가 팀 구성원이 되는 방법

1. 팀 소유자나 Microsoft 365 관리자가 [팀에 게스트를 추가](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)합니다.
2. 게스트는 팀에 대한 정보와 구성원이 되었으므로 기대할 수 있는 내용이 포함된 팀 소유자의 환영 전자 메일을 받게 됩니다. 
3. 게스트가 초대를 수락합니다.
  Azure Active Directory에서 회사 또는 학교 계정이 있는 게스트 사용자는 초대를 수락 하 고 직접 인증할 수 있습니다. 다른 사용자는 1 회 통과 코드를 보내 id의 유효성을 검사 합니다 ([일회성 암호 인증](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) 필요).
4. 초대를 수락하면 게스트는 [팀과 채널에 참여](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), 채널 메시지 받기 및 응답, [채널에서 파일에 액세스](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), 채팅에 참여, 모임에 참여, 문서 공동 작업 등을 할 수 있습니다. 

Teams에서는 게스트를 명확하게 식별합니다. 게스트 사용자 이름에는 레이블 **(게스트)** 이 포함되고, 채널에는 팀에 게스트가 있음을 나타내는 아이콘이 포함됩니다. 자세한 내용은 [게스트 환경의 모습](guest-experience.md)을 참조하세요.
  
게스트는 Teams 내에서 언제든지 팀을 떠날 수 있습니다. 자세한 내용은 [팀에서 나가는 방법](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)을 참조하세요.

> [!NOTE]
> 팀에서 나가면 조직의 디렉터리에서 게스트 계정이 제거 되지 않습니다. Microsoft 365 전역 관리자 또는 Azure AD 관리자가이 작업을 수행 해야 합니다.

## <a name="licensing-for-guest-access"></a>게스트 액세스에 대한 라이선스

게스트 액세스는 모든 Microsoft 365 비즈니스 표준, Microsoft 365 Enterprise 및 Microsoft 365 교육 구독에 포함 됩니다. Microsoft 365 라이선스가 추가로 필요 하지 않습니다. Teams에서는 추가할 수 있는 게스트 수를 제한하지 않습니다. 그러나 테넌트에 추가 할 수 있는 총 방문자 수는 Azure AD의 유료 기능에 따라 제한될 수 있습니다. 자세한 내용은 [AZURE AD External id에 대 한 청구 모델](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)을 참조 하세요.

> [!NOTE]
> 독립 실행형 Microsoft 365 구독 계획 (예: Exchange Online 계획 2)만 있는 조직의 사용자는 해당 사용자가 동일한 조직에 속해 있는 것으로 간주 되므로 조직에 게스트로 초대 될 수 없습니다. 사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다. 

## <a name="guest-access-reviews"></a>게스트 액세스 검토

Azure AD를 사용 하 여 그룹 구성원 또는 응용 프로그램에 할당 된 사용자에 대 한 액세스 검토를 만들 수 있습니다. 되풀이 되는 access 리뷰를 만들면 시간을 절약할 수 있습니다. 응용 프로그램, 팀 또는 그룹의 구성원에 대 한 액세스 권한이 있는 사용자를 정기적으로 검토 해야 하는 경우 이러한 검토의 빈도를 정의할 수 있습니다. 

게스트 액세스 검토를 수행 하거나, 게스트에 게 자신의 구성원을 검토 하도록 요청 하거나, 응용 프로그램 소유자나 비즈니스 의사 결정권자에 게 액세스 검토를 수행 하도록 요청 합니다. Azure 포털을 사용 하 여 게스트 액세스 검토를 수행 합니다. 자세한 내용은 [AZURE AD access 리뷰를 사용 하 여 게스트 액세스 관리](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)를 참조 하세요.

## <a name="related-topics"></a>관련 주제

[조직 외부의 사용자와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[특정 Microsoft 365 그룹 또는 Microsoft 팀 팀의 게스트 사용자 차단](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[안전한 게스트 공유 환경 만들기](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[비즈니스용 제품에 대한 고객 지원 센터 - 관리자 도움말](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[세 가지 보호 계층을 사용 하 여 팀 구성](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
