---
title: 관리 단위를 사용하여 디바이스 관리
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams에서 관리 단위를 사용하는 방법 알아보기
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ccc079617a1ae58b3881da8ae48c8a993d5863
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269473"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>관리 단위를 사용하여 Teams 관리 센터에서 디바이스 관리

Teams 관리 센터의 관리 단위는 Teams 디바이스를 관리하기 위한 자세한 역할 기반 액세스를 제공합니다. 관리 단위는 Teams 관리자에게 특정 리소스에 대한 액세스 권한을 부여하지만 다른 리소스에 대한 관리자의 액세스를 제한합니다. 이는 다른 국가 또는 지역에 로컬 Teams 관리자가 있는 경우에 특히 유용합니다.

예를 들어 Contoso는 전 세계에 작업을 수행합니다. Alice는 런던에 본사를 둔 글로벌 IT 관리자이며 Prashant는 인도 방갈로르에 본사를 둔 현지 IT 관리자입니다. 현재 Prashant가 디바이스 관리자로 Teams 관리 센터에 로그인하면 전 세계의 Teams 디바이스를 볼 수 있습니다. Alice는 방갈로르에서만 Teams 디바이스에 대한 Prashant의 액세스를 제한하려고 합니다. 관리 단위는 그녀를이 작업을 수행 할 수 있습니다. 자세한 내용은 [Azure Active Directory의 관리 단위를 참조하세요](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> 관리 단위는 현재 Teams 관리 센터에서 Teams 디바이스 관리자 역할에 대해서만 사용할 수 있습니다.

## <a name="add-administrative-units"></a>관리 단위 추가

관리 단위를 추가하려면 전역 관리자여야 합니다. 방법을 알아보려면 [관리 단위 추가를 참조하세요](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>관리자를 관리 단위에 할당

관리 단위를 할당하려면 전역 관리자여야 합니다. Azure Portal, PowerShell 또는 Microsoft Graph API 사용하여 관리 단위를 할당할 수 있습니다. 자세한 내용은 [관리 단위 범위를 사용하여 Azure AD 역할 할당](/azure/active-directory/roles/admin-units-assign-roles)을 참조하세요.

## <a name="select-administrative-units"></a>관리 단위 선택

Teams 디바이스 관리자인 경우 전역 관리자가 관리 단위에 사용자를 할당한 후 Teams 관리 센터에 로그인하여 디바이스를 관리할 수 있습니다. 관리 단위가 하나만 할당된 경우 해당 관리 단위에 할당된 디바이스만 표시됩니다. 여러 관리 단위에 할당된 경우 Teams 관리 센터에서 로그아웃하지 않고 해당 관리 단위 간에 전환할 수 있습니다. 

1. [Teams 관리 센터에 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. **관리 단위** 대화 상자에서 다음 단계 중 하나를 수행합니다.
    - 관리하려는 관리 단위를 선택하거나 
    - 조직의 **모든 디바이스** 를 관리할 수 있는 권한이 있는 경우 모든 디바이스를 선택합니다.

3. **저장** 을 선택합니다.

## <a name="switch-administrative-units"></a>관리 단위 전환

Teams 디바이스 관리자인 경우 Teams 관리 센터에 로그인한 경우 관리 단위 간에 전환할 수 있습니다. 다른 관리 단위로 전환하려면 다음을 수행합니다.

1. [Teams 관리 센터에 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. 왼쪽 탐색 영역에서 **Teams 디바이스를** 선택합니다.

3. 오른쪽 창의 왼쪽 위에서 표시된 관리 단위를 선택합니다.

4. **관리 단위** 대화 상자에서 다음 단계 중 하나를 수행합니다.
    - 관리하려는 관리 단위를 선택하거나 
    - 조직의 **모든 디바이스** 를 관리할 수 있는 권한이 있는 경우 모든 디바이스를 선택합니다.

5. **저장** 을 선택합니다.

## <a name="related-topics"></a>관련 항목

- [관리 단위에 사용자 또는 그룹 추가](/azure/active-directory/roles/admin-units-members-add)
