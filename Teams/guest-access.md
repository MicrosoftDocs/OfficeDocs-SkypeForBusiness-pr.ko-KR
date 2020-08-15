---
title: Microsoft Teams의 게스트 액세스
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams의 게스트 액세스를 사용하면 조직의 팀에서 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다.
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761244"
---
# <a name="guest-access-in-microsoft-teams"></a>Microsoft Teams의 게스트 액세스

게스트 액세스를 사용하면 조직의 팀에서 Teams의 기존 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다. Microsoft 365, Outlook, Gmail 등의 비즈니스 또는 소비자 전자 메일 계정을 사용 하는 모든 사용자는 팀 채팅, 모임 및 파일에 대 한 모든 권한을 가진 팀에서 게스트로 참여할 수 있습니다. Teams 관리자는 Teams에서 게스트가 사용할 수 있거나 사용할 수 없는 기능을 제어할 수 있습니다. [게스트 액세스 관리](manage-guests.md)를 확인합니다.

외부 액세스 (페더레이션)와 게스트 액세스를 비교하려면 (어느 것을 사용할 지 결정하려면) [Teams의 다른 조직의 사용자와 커뮤니케이션](communicate-with-users-from-other-organizations.md)을 참조하세요.

게스트 액세스는 Teams에서 기본적으로 비활성화된 조직 전체에 대한 설정입니다. ( [우편물 종류 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)사용 하 여 개별 팀에 대 한 게스트 액세스를 제어할 수 있습니다.)

팀에 게스트 초대를 시작할 준비가 되었으면 다음 중 하나를 읽어 보세요.

- 일반적인 사용을 위해 팀에 대 한 게스트 액세스를 구성 하려면 [팀에서 게스트 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조 하세요.
- Azure Active Directory를 사용 하 고 게스트가 팀 액세스를 자체 등록할 수 있도록 허용 하는 파트너 조직과 공동 작업 하려면 [관리 되는 게스트를 사용 하 여 B2B 엑스트라넷 만들기](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)를 참조 하세요.

게스트 액세스에는 Azure AD 및 Microsoft 365 또는 Office 365 서비스 제한이 적용됩니다.

> [!IMPORTANT]
> 게스트 사용자는 동시 업그레이드 모드를 위해 Temas 조직 전체 설정을 따릅니다. 변경할 수 없습니다.

## <a name="licensing-for-guest-access"></a>게스트 액세스에 대한 라이선스

게스트 액세스는 모든 Microsoft 365 Business Standard, Office 365 Enterprise 및 Office 365 Education 구독에 포함되어 있습니다. Microsoft 365 또는 Office 365 추가 라이선스가 필요하지 않습니다. Teams에서는 추가할 수 있는 게스트 수를 제한하지 않습니다. 그러나 테넌트에 추가 할 수 있는 총 방문자 수는 Azure AD의 유료 기능에 따라 제한될 수 있습니다. 자세한 내용은 [Azure AD B2B 공동 작업 라이선스](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)를 참조하세요.


> [!NOTE]
> Exchange Online Plan 2와 같이 독립실행형 Microsoft 365 또는 Office 365 구독 계획만 보유한 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다. 사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다. 

## <a name="who-is-a-guest"></a>누가 게스트인가요?

게스트는 직원, 학생 또는 조직의 구성원이 아닌 사용자입니다. 조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다. 예를 들어, 게스트에는 파트너, 공급 업체, 공급자 또는 컨설턴트 등이 포함될 수 있습니다. 조직에 속하지 않은 사용자를 Teams에서 게스트로 추가할 수 있습니다. 비즈니스 계정 (즉, Azure Active Directory 계정) 또는 소비자 전자 메일 계정 (Outlook.com, Gmail.com 또는 기타 사용자)이 있는 모든 사용자는 팀과 채널 환경에 대한 모든 액세스 권한을 가지고 Teams에 게스트로 참여할 수 있습니다.

게스트가 수행할 수 있는 작업에 대한 자세한 내용을 알아보려면 [Microsoft Teams의 게스트 액세스 권한](teams-dependencies.md)을 참조하세요. 또는 [팀 구성원 및 게스트 권한 비교](guest-experience.md#comparison-of-team-member-and-guest-capabilities)를 참조하세요. 

마지막으로, 팀의 모든 게스트는 Microsoft 365의 나머지 부분과 동일한 준수 및 감사 보호에 적용 되며, Azure AD 내에서 관리할 수 있습니다.

## <a name="why-use-guest-access"></a>게스트 액세스를 사용하는 이유는 무엇인가요?

게스트 액세스에서 Teams를 사용하는 조직은 회사 데이터를 완전하게 제어하면서 팀, 채널의 문서, 리소스, 채팅 및 응용 프로그램에 대한 액세스 권한을 파트너에게 부여할 수 있습니다. 

## <a name="understand-the-limitations-for-guests"></a>게스트에 대한 제한 사항 이해

게스트 환경에는 디자인별로 제약 사항이 있습니다. 문제를 해결하려면 게스트 환경을 이해하고 있어야 합니다. 다음은 Microsoft 팀에서 게스트에 사용할 수 없는 몇 가지 기능 목록입니다.

- OneDrive
- Teams 외부에서 사용자 검색
- 일정, 예약된 모임 또는 모임 세부 정보
- PSTN
- 조직도
- 팀 만들기 또는 수정
- 팀 찾아보기
- 개인 채팅에 파일 업로드
- 현재 팀 [은 게스트 사용자의 상태 1 및 상태 2 유형만](https://docs.microsoft.com/azure/active-directory/b2b/user-properties) 지원 합니다.

게스트가 Teams에서 수행할 수 있는 작업에 대한 전체 목록을 보려면 [팀 구성원 및 게스트 권한 비교](guest-experience.md#comparison-of-team-member-and-guest-capabilities)를 참조하세요. Microsoft 365 수준에서 게스트 액세스에 대 한 자세한 내용은 [조직 외부 사용자와의 공동](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)작업을 참조 하세요.


## <a name="related-topics"></a>관련 항목

[비즈니스용 제품에 대한 고객 지원 센터 - 관리자 도움말](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[세 가지 보호 계층을 사용 하 여 팀 구성](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
