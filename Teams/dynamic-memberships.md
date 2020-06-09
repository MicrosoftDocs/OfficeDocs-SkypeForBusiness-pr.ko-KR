---
title: 팀의 동적 구성원 개요
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft 팀이 동적 구성원을 사용 하 여 Microsoft 365 그룹과 연결 된 팀을 지 원하는 방법을 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc7e3124ec3ec97e3f3643412ccb4f990ab825cc
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638407"
---
# <a name="overview-of-dynamic-membership-for-teams"></a>팀의 동적 구성원 개요

Microsoft 팀은 *동적 구성원*을 사용 하 여 microsoft 365 그룹과 연결 된 팀을 지원 합니다. 동적 멤버 자격을 사용 하면 Azure Active Directory (Azure AD)의 특정 사용자 특성을 확인 하는 하나 이상의 규칙으로 팀 구성원을 정의할 수 있습니다. 사용자 특성이 변경 되거나 사용자가 테 넌 트에 가입 하 고 나갈 때 사용자가 자동으로 올바른 팀에 추가 또는 제거 됩니다.

동적 구성원 자격을 통해 조직의 특정 cohorts 사용자에 대 한 팀을 설정할 수 있습니다. 사용할 수 있는 시나리오는 다음과 같습니다.
- 병원은 nurses, doctors 및 surgeons에 대 한 고유한 팀을 만들어 브로드캐스트 통신을 할 수 있습니다. 이는 병원이 임시 직원을 사용 하는 경우 특히 중요 합니다.
- 대학은 자주 변경 되는 adjunct 교직원을 포함 하 여 특정 대학 내의 모든 교직원을 위한 팀을 만들 수 있습니다.
- 비행기는 각 비행에 대 한 팀 (예: 시카고에서 애틀랜타 까지의 화요일)을 만들고 필요에 따라 자주 변경 되는 비행 crew을 자동으로 할당 하거나 제거 하려고 합니다.

이 기능을 사용 하면 지정 된 팀의 구성원이 멤버 자격을 수동으로 관리 하는 대신 특정 조건 집합에 따라 자동으로 업데이트 됩니다. 이 작업을 수행 하려면 Azure AD Premium P1 라이선스와 팀 구성원 자격을 테 넌 트 관리자가 사용자의 모든 Azure AD 속성에 [할당할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) 수 있습니다.

Microsoft 팀은 팀의 Microsoft 365 그룹에 영향을 주는 경우 동적 구성원 변경을 반영 하는 데 몇 분에서 최대 2 시간까지 걸릴 수 있습니다.

> [!NOTE]
> - 규칙은 팀 구성원 인 사용자가 아닌 팀 소유자를 정의할 수 있습니다.
> - 팀 및 채널 크기에 대 한 현재 제한에 대 한 [Microsoft 팀의 제한 및 사양을](limits-specifications-teams.md) 참조 하세요.
> - 멤버가 동적 그룹 규칙으로 정의 되므로 소유자는 팀 구성원으로 사용자를 추가 하거나 제거할 수 없습니다.
> -    구성원은 동적 그룹으로 지원 되는 팀에서 나갈 수 없습니다.


## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a>동적 구성원 자격을 사용 하 여 Microsoft 365 그룹 만들기 및 관리
테 넌 트 관리자로 로그인 한 [후 동적 그룹 만들기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)의 지침에 따라 상태를 확인 합니다. 필요에 따라 [Azure Active Directory의 그룹에 대 한 동적 구성원 규칙](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)을 참조 하세요.

## <a name="create-a-new-team-with-your-o365-group"></a>O365 그룹을 사용 하 여 새 팀 만들기

이제 구성원 변경 내용이 적용 되는 시간을 허용 하 고 [Microsoft 팀과 기존 microsoft 365 그룹 향상](enhance-office-365-groups.md)에 설명 된 대로 새 팀을 만듭니다.

## <a name="apply-dynamic-membership-to-an-existing-team"></a>기존 팀에 동적 구성원 자격 적용

또한 기존 팀을 가져와 [정적 그룹 구성원을 Azure Active Directory에서 동적으로 변경](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)하는 방법에 설명 된 것 처럼 동적인 구성원을 포함 하도록 변경할 수 있습니다.

## <a name="changes-in-client-behavior"></a>클라이언트 동작 변경

팀에 대 한 동적 구성원 자격이 활성화 되 면 팀 클라이언트는 더 이상 구성원에 대 한 멤버 관리를 허용 하지 않습니다. 구성원을 추가 하 고, 구성원 역할을 편집 하 고, 참가 요청을 보내고 승인 하며, 팀을 모두 숨길 수 있는 옵션입니다.
