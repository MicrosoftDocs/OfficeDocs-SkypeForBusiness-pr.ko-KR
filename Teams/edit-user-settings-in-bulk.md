---
title: Microsoft 팀 사용자 설정을 대량으로 편집
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft 팀 관리 센터에서 Microsoft 팀 사용자 설정을 대량으로 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fec2338e1a7e518e90b2a5fbed716a01782bbb8c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693293"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>대량으로 Microsoft 팀 사용자 설정 편집

관리자는 Microsoft 팀 관리 센터에서 팀 사용자 설정을 관리할 수 있습니다. **사용자** 페이지에서 계정 및 라이선스 세부 정보, 정책 및 기타 설정 편집 등의 정보를 볼 수 있습니다. 사용자에 대 한 설정을 개별적으로 또는 여러 사용자가 동시에 편집할 수 있습니다.

## <a name="edit-user-settings-in-bulk"></a>대량으로 사용자 설정 편집

Microsoft 팀 관리 센터를 사용 하 여 한 번에 여러 사용자의 설정을 편집할 수 있습니다. 한 번에 20 명의 사용자에 대 한 설정을 편집 하는 것이 좋습니다. 많은 수의 사용자에 대 한 설정을 편집 하려면 PowerShell을 사용 합니다. 자세한 내용은 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **사용자**를 선택 합니다.
2. 편집 하려는 사용자를 검색 하거나 보기를 필터링 하 여 편집할 사용자를 표시 합니다.
3. **&#x2713;** (확인 표시) 열에서 다음 중 하나를 수행 하 여 사용자를 선택 합니다.
    - 한 번에 하나씩 사용자를 선택 합니다. 선택한 각 사용자 옆에 **&#x2713;** 표시 됩니다. 20 명 이상의 사용자를 선택 하는 경우에는 차단 되지 않지만 선택 하는 사용자가 많을 수록 작업을 완료 하는 데 시간이 오래 걸릴 수 있다는 점에 유의 하세요.

        ![사용자 선택을 표시 하는 사용자 페이지 스크린샷](media/bulk-edit-user-settings-select-users.png)

    - 테이블 맨 위에 있는 &#x2713; (확인 표시)을 클릭 하 여 모든 사용자 (최대 20 명의 사용자)를 선택한 다음, **선택 제한** 대화 상자에서 **계속 해 서 모두 선택을** 클릭 하 여 선택 영역을 완성 합니다.

        ![선택 한계를 보여 주는 사용자 페이지 스크린샷](media/bulk-edit-user-settings-select-all-limit.png) <br> 선택한 사용자 옆에 **&#x2713;** 표시 됩니다.

        ![20 명의 사용자가 선택 되었음을 보여 주는 사용자 페이지 스크린샷](media/bulk-edit-user-settings-select-all.png)
4. **설정 편집**을 클릭 하 고 원하는 대로 변경한 다음 **저장**을 클릭 합니다.

    ![설정 편집 창 스크린샷](media/bulk-edit-user-settings-edit-settings.png)
