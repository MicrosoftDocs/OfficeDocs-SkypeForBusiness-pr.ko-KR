---
title: 관리 단위를 사용하여 디바이스 관리
author: mahoffman
ms.author: serdars
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 관리 단위를 사용하는 방법을 Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
  - NOCSH
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>관리 단위를 사용하여 Teams 관리 센터에서 디바이스 관리

관리 센터의 관리 Teams 디바이스를 관리하기 위한 세부적인 역할 기반 Teams 제공합니다. 관리 단위는 Teams 관리자에게 액세스 권한을 부여하지만 해당 관리자의 다른 리소스에 대한 액세스를 제한합니다. 이는 다른 국가 또는 지역에 Teams 로컬 관리자를 보유하고 있는 경우 특히 유용합니다.

예를 들어 Contoso에는 전 세계 작업이 있습니다. Alice는 런던에 기반을 두는 글로벌 IT 관리자로, Prashant는 인도 방가로에 기반을 두는 로컬 IT 관리자입니다. 현재 Prashant가 디바이스 관리자로 Teams 관리 센터에 로그인하면 전 세계 Teams 볼 수 있습니다. Alice는 Bangalore에서만 Teams 디바이스에 대한 Prashant의 액세스를 제한하려는 것입니다. 관리 단위를 통해 이 작업을 할 수 있습니다. 자세한 내용은 에 있는 관리 [단위를 Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> 관리 단위는 현재 Teams 관리자 역할에 Teams 관리 센터에서 사용할 수 있습니다.

## <a name="add-administrative-units"></a>관리 단위 추가

관리 단위를 추가하려면 전역 관리자가 해야 합니다. 방법을 알아보고자 하는 경우 관리 단위 [추가를 참조합니다](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>관리 단위에 관리자 할당

또한 관리 단위를 할당하려면 전역 관리자로 지정해야 합니다. Azure Portal, PowerShell 또는 Microsoft Graph 있습니다. 자세한 내용은 관리 단위 범위가 [있는 Azure AD 역할 할당을 참조하세요](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>관리 단위 선택

디바이스 관리자인 Teams 전역 관리자가 관리자 단위에 할당한 후 관리자 센터에 Teams 관리 센터에 로그인하여 디바이스를 관리할 수 있습니다. 하나의 관리 단위에만 할당된 경우 해당 관리 단위에 할당된 디바이스만 표시됩니다. 여러 관리 단위에 할당된 경우 관리 센터에서 로그인하지 않고 관리 단위 간에 전환할 Teams 있습니다. 

1. 관리 센터에 [Teams 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. 관리 단위 **대화** 상자에서 다음 단계 중 하나를 따릅니다.
    - 관리하려는 관리 단위를 선택하거나 
    - 조직의 **모든** 디바이스를 관리할 수 있는 권한이 있는 경우 모든 디바이스를 선택합니다.

3. **저장** 을 선택합니다.

## <a name="switch-administrative-units"></a>관리 단위 전환

디바이스 관리자인 Teams 관리 센터에 로그인한 경우 관리 단위 간에 전환할 Teams 있습니다. 다른 관리 단위로 전환하는 경우:

1. 관리 센터에 [Teams 로그인합니다](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. 왼쪽 탐색에서 디바이스 Teams **선택합니다**.

3. 오른쪽 창의 왼쪽 위에서 표시된 관리 단위를 선택합니다.

4. 관리 단위 **대화** 상자에서 다음 단계 중 하나를 따릅니다.
    - 관리하려는 관리 단위를 선택하거나 
    - 조직의 **모든** 디바이스를 관리할 수 있는 권한이 있는 경우 모든 디바이스를 선택합니다.

5. **저장** 을 선택합니다.
