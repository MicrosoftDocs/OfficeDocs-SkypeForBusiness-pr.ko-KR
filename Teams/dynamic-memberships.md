---
title: 팀의 동적 구성원 개요
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 동적 멤버 자격을 사용하여 Microsoft Teams가 Microsoft 365 그룹과 연결된 팀을 지원하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff6a71978873d723f39a534f876696a0def2f756
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562577"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>팀의 동적 구성원 개요

Microsoft Teams는 *동적 멤버 자격을* 사용하여 Microsoft 365 그룹과 연결된 팀을 지원합니다. 동적 멤버 자격을 사용하면 Azure Active Directory(Azure AD)에서 특정 사용자 특성을 확인하는 하나 이상의 규칙으로 팀의 멤버 자격을 정의할 수 있습니다. 사용자 특성이 변경되거나 사용자가 테넌트에 가입하고 나가면 사용자가 올바른 팀에 자동으로 추가되거나 제거됩니다.

동적 멤버 자격을 사용하면 조직의 특정 사용자 코호트에 대한 팀을 설정할 수 있습니다. 가능한 시나리오는 다음과 같습니다.
- 병원은 간호사, 의사 및 외과 의사가 통신을 방송할 수 있는 고유한 팀을 만들 수 있습니다. 이것은 병원이 임시 직원에 의존하는 경우에 특히 중요합니다.
- 대학은 특정 대학 내의 모든 교직원에 대한 팀을 만들 수 있습니다, 자주 변경 외래 교수를 포함.
- 항공사는 각 항공편(예: 화요일 오후 시카고에서 애틀랜타까지 논스톱)에 대한 팀을 만들고 필요에 따라 자주 변경되는 승무원을 자동으로 할당하거나 제거하려고 합니다.

이 기능을 사용하면 지정된 팀의 구성원이 멤버 자격을 수동으로 관리하는 대신 특정 조건 집합에 따라 자동으로 업데이트됩니다. 이렇게 하려면 [테넌트 관리자가 테넌트 및 관리자](/azure/active-directory/users-groups-roles/groups-dynamic-membership) 계정이 있는 경우 모든 사용자의 Azure AD 속성에 Azure AD Premium P1 라이선스 및 팀 멤버 자격을 할당할 수 있어야 합니다.

Microsoft Teams는 팀의 Microsoft 365 그룹에서 적용되는 동적 멤버 자격 변경 내용을 반영하기 위해 몇 분에서 최대 2시간까지 걸릴 수 있습니다.

동적 그룹이 있는 팀을 사용하는 경우:

- 규칙은 팀 구성원이 누구인지 정의할 수 있지만 팀 소유자는 정의할 수 없습니다.
- 구성원은 동적 그룹 규칙에 의해 정의되므로 소유자는 사용자를 팀의 구성원으로 추가하거나 제거할 수 없습니다.
- Teams 클라이언트는 팀에 대한 멤버 관리를 허용하지 않습니다. 멤버를 추가하고, 멤버 역할을 편집하고, 조인 요청을 보내고 승인하고, 팀을 떠나는 옵션은 모두 숨겨집니다.

동적 멤버 자격을 사용하는 팀을 만들려면 먼저 [동적 Microsoft 365 그룹을 만든](/azure/active-directory/users-groups-roles/groups-create-rule) 다음 [해당 그룹에서 팀을 만듭니](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)다.

동적 멤버 자격을 갖도록 기존 팀을 변경할 수 있습니다. 자세한 내용은 [Azure Active Directory에서 정적 그룹 멤버 자격을 동적으로 변경](/azure/active-directory/users-groups-roles/groups-change-type) 하세요.

## <a name="related-topics"></a>관련 항목

[Microsoft Teams의 제한 사항 및 사양](limits-specifications-teams.md)

[Azure Active Directory의 그룹에 대한 동적 멤버 자격 규칙](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
