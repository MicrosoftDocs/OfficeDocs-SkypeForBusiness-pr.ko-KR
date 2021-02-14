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
description: Microsoft Teams에서 동적 멤버 자격을 사용하여 Microsoft 365 그룹과 연결된 팀을 지원하는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583927"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>팀의 동적 구성원 개요

Microsoft Teams는 동적 멤버 자격을 사용하여 Microsoft 365 그룹과 연결된 *팀을 지원합니다.* 동적 멤버 자격을 사용하면 Azure AD(Azure Active Directory)에서 특정 사용자 특성을 검사하는 하나 이상의 규칙으로 팀 멤버 자격을 정의할 수 있습니다. 사용자 특성이 변경되거나 사용자가 테넌트에 가입하고 나가면 사용자가 올바른 팀에 자동으로 추가되거나 제거됩니다.

동적 멤버 자격을 사용하면 조직의 특정 코호트에 대한 팀을 설정할 수 있습니다. 가능한 시나리오는 다음과 같습니다.
- 병원은 간호사, 의사 및 외과의사와 통신을 브로드캐스트할 수 있는 고유한 팀을 만들 수 있습니다. 이 방법은 병원에서 임시 직원을 고용하는 경우 특히 중요합니다.
- 대학은 자주 변경되는 부재 중 교직원을 포함하여 특정 대학 내의 모든 교직원을 위한 팀을 만들 수 있습니다.
- 항공사는 각 플라이트에 대한 팀을 만들고(예: 화요일 오후 시카고에서 애틀랜타로의 출발이 아닌 화요일 오후) 자주 변경되는 플라이트 승무원을 자동으로 할당하거나 제거합니다.

이 기능을 사용하면 특정 팀의 구성원이 멤버 자격을 수동으로 관리하는 대신 특정 조건 집합에 따라 자동으로 업데이트됩니다. 이렇게 하려면 테넌트 및 관리자 계정이 [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) 있는 경우 테넌트 관리자가 Azure AD Premium P1 라이선스 및 팀 멤버 자격을 사용자의 Azure AD 속성에 할당할 수 있습니다.

Microsoft Teams는 팀의 Microsoft 365 그룹에 적용된 동적 멤버 자격 변경 내용을 반영하는 데 몇 분에서 최대 2시간까지 걸릴 수 있습니다.

> [!NOTE]
> - 규칙은 팀 소유자가 아닌 팀 구성원을 정의할 수 있습니다.
> - 팀 및 채널 크기에 대한 현재 제한은 [Microsoft Teams의](limits-specifications-teams.md) 제한 및 사양을 참조하세요.
> - 구성원은 동적 그룹 규칙에 의해 정의되어 팀의 구성원으로 사용자를 추가하거나 제거할 수 없습니다.
> -    구성원은 동적 그룹에서 팀을 떠날 수 없습니다.

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>동적 멤버 자격을 통해 Microsoft 365 그룹 만들기 및 관리

테넌트 관리자로 로그인하는 동안 동적 그룹 만들기의 지침을 따르고 [상태를 검사합니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) 필요한 경우 Azure Active Directory의 그룹에 대한 동적 [멤버 자격 규칙을 참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

## <a name="create-a-new-team-with-your-microsoft-365-group"></a>Microsoft 365 그룹을 사용하여 새 팀 만들기

이제 멤버 자격 변경이 적용될 시간을 허용하고 기존 그룹에서 팀 만들기에 설명된 새 [팀을 만들 수 있습니다.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)

## <a name="apply-dynamic-membership-to-an-existing-team"></a>기존 팀에 동적 멤버 자격 적용

Azure Active Directory에서 정적 그룹 멤버 자격 변경에 설명된 바와 같이 기존 팀을 사용하여 동적 멤버 자격을 가지게 변경할 [수도 있습니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)

## <a name="changes-in-client-behavior"></a>클라이언트 동작의 변경 내용

팀에 대해 동적 멤버 자격을 사용하도록 설정하면 Teams 클라이언트는 더 이상 팀에 대한 구성원 관리를 허용하지 않습니다. 구성원을 추가하고, 구성원 역할을 편집하고, 참가 요청을 보내고 승인하고, 팀에서 나가는 옵션은 모두 숨겨져 있습니다.
