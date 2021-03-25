---
title: 팀의 동적 구성원 개요
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams가 동적 멤버 자격을 사용하여 Microsoft 365 그룹과 연결된 팀을 지원하는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120770"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>팀의 동적 구성원 개요

Microsoft Teams는 동적 멤버 자격을 사용하여 Microsoft 365 그룹과 연결된 *팀을 지원합니다.* 동적 멤버 자격을 사용하면 Azure AD(Azure Active Directory)에서 특정 사용자 특성을 검사하는 하나 이상의 규칙으로 팀 멤버 자격을 정의할 수 있습니다. 사용자 특성이 변경되거나 사용자가 테넌트에 참가하고 나가면 사용자가 자동으로 추가되거나 올바른 팀에 제거됩니다.

동적 멤버 자격을 사용하면 조직의 특정 사용자 코호트에 대한 팀을 설정할 수 있습니다. 가능한 시나리오는 다음과 같습니다.
- 병원은 통신을 브로드캐스트하기 위해 간호사, 의사 및 외과 의사를 위한 고유한 팀을 만들 수 있습니다. 이는 병원에서 임시 직원을 의존하는 경우 특히 중요합니다.
- 대학은 자주 변경되는 2학년 교직원을 포함하여 특정 대학 내의 모든 교직원에 대한 팀을 만들 수 있습니다.
- 항공사는 각 항공편(예: 시카고에서 애틀랜타로의 화요일 오후 논스톱)에 대한 팀을 만들고, 자주 변경되는 승무원이 필요한 경우 자동으로 할당되거나 제거됩니다.

이 기능을 사용하여 특정 팀의 구성원은 수동으로 멤버 자격을 관리하는 대신 특정 조건 집합에 따라 자동으로 업데이트됩니다. 이렇게 하려면 테넌트 및 관리자 계정이 [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) 있는 경우 테넌트 관리자가 Azure AD 프리미엄 P1 라이선스 및 팀 멤버 자격을 사용자의 Azure AD 속성에 할당할 수 있습니다.

Microsoft Teams는 팀의 Microsoft 365 그룹에 적용된 동적 멤버 자격 변경 내용을 반영하기 위해 몇 분에서 최대 2시간까지 걸릴 수 있습니다.

> [!NOTE]
> - 규칙은 팀 구성원을 정의할 수 있지만 팀 소유자는 정의할 수 없습니다.
> - 팀 및 채널 크기에 대한 현재 제한은 [Microsoft Teams의](limits-specifications-teams.md) 제한 및 사양을 참조하세요.
> - 소유자는 구성원이 동적 그룹 규칙으로 정의되어 팀의 구성원으로 사용자를 추가하거나 제거할 수 없습니다.
> -    멤버는 동적 그룹으로 팀을 떠날 수 없습니다.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>동적 멤버 자격을 통해 Microsoft 365 그룹 만들기 및 관리

테넌트 관리자로 로그인하는 동안 동적 그룹 만들기의 지침을 따르고 [상태를 검사합니다.](/azure/active-directory/users-groups-roles/groups-create-rule) 필요한 경우 Azure Active Directory의 그룹에 대한 동적 멤버 [자격 규칙을 참조하세요.](/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Microsoft 365 그룹으로 새 팀 만들기

이제 멤버 자격 변경이 적용될 시간을 허용하고 기존 그룹에서 팀 만들기에 설명된 바와 같이 새 [팀을 만들 수 있습니다.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>기존 팀에 동적 멤버 자격 적용

Azure Active Directory에서 동적으로 정적 그룹 멤버 자격 변경에 설명된 바와 같이 기존 팀을 사용하여 동적 멤버 자격으로 [변경할 수도 있습니다.](/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>클라이언트 동작의 변경 내용

팀에 대해 동적 멤버 자격을 사용하도록 설정하면 Teams 클라이언트는 더 이상 팀에 대한 구성원 관리를 허용하지 않습니다. 멤버를 추가하고, 멤버 역할을 편집하고, 조인 요청을 보내고 승인하고, 팀을 떠나는 옵션은 모두 숨겨져 있습니다.