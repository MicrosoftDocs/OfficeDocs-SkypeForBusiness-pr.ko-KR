---
title: 관리 단위 기능을 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 관리 단위 기능을 사용하는 방법을 Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 556f220c9ca250f014ae604c96cabf9ef0b0ca0f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636794"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>디바이스 관리에 대한 관리 Teams

관리 센터를 사용하여 디바이스 관리에 대한 보다 세분화된 역할 기반 Microsoft Teams 있습니다. 관리 센터를 통해 디바이스 관리를 위한 관리 단위 Teams 구현했습니다.

관리 단위 개념을 사용하면 전용 관리자에게 특정 리소스 집합에 대한 액세스 권한을 보장합니다. 관리 단위는 모든 리소스에 대한 액세스를 제한합니다. 디바이스 관리에 대해 동일한 Teams 수 있습니다.

> [!NOTE]
> 관리 단위 개념은 현재 디바이스 관리자 역할에 Teams 사용할 수 있습니다.

예를 들어 Contoso에는 다양한 지리에 대한 작업이 있습니다. Alice는 런던의 글로벌 IT 관리자로, Prashant는 인도의 IT 관리자입니다. 현재 Prashant는 디바이스 관리자 Teams 관리자 센터에 로그인하면 전 세계에 걸쳐 디바이스를 볼 수 있습니다. Alice는 인도에 있는 디바이스에만 Prashant의 액세스를 제한하려는 것입니다. 관리 단위 개념은 이 문제를 해결하는 데 도움이 됩니다. 관리 단위 [개념에 대해 자세히 알아보자.](/azure/active-directory/roles/administrative-units)

![시나리오를 보여주는 다이어그램](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>관리 단위 만들기

Azure Portal에서 관리 단위를 만들고 각 관리 단위에 대해 관리자를 할당합니다. 관리 단위 관리에서 관리 [단위를 할당하는 방법을 자세히 알아보습니다.](/azure/active-directory/roles/admin-units-manage)

![회사 관리 단위 예제](media/au-example.png)

글로벌 IT 관리자는 만든 후 해당 관리 단위에 해당하는 디바이스 사용자를 추가할 수 있습니다.

![사용자 미리 보기가 있는 예제 회사](media/au-example2.png)

역할 할당은 [Add-AzureADMSScopedRoleMembership](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0) cmdlet을 사용하여 PowerShell을 통해 수행될 수 있습니다.

관리 단위에 대한 사용자에게 역할을 할당한 후 사용자는 범위가 지정된 디바이스 관리를 Teams 관리 센터에 로그인해야 합니다.

## <a name="experience-for-administrative-unit-admin"></a>관리 단위 관리자 환경

동일한 관리자가 여러 관리 단위의 책임이 할당된 경우 포털에서 로그인하지 않고 관리 단위 간에 전환할 수 있습니다. 변경된 관리 단위 보기에서 새 관리 단위와 연결된 디바이스 집합만 표시됩니다.
