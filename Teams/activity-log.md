---
title: 관리 센터의 활동 로그에서 정책 Microsoft Teams 보기
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 관리 센터의 활동 로그에서 정책 할당 활동을 보는 Microsoft Teams 대해 자세히 알아보습니다.
ms.localizationpriority: medium
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58df214ec15153abcee4275f42c6ae6208b5d4b1
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731247"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>활동 로그에서 정책 할당 보기

관리 센터의 사용자에게 정책을 Microsoft Teams 경우 활동 로그에서 해당 정책 할당의 상태를 볼 수 있습니다. 활동 로그는 지난 30일 동안 관리 센터를 통해 20명 Microsoft Teams 일괄 처리에 대한 정책 할당을 보여줍니다. 활동 로그는 PowerShell을 통해 정책 패키지 할당, 20명 미만의 사용자 일괄 처리에 대한 정책 할당을 Microsoft Teams 없습니다.

![활동 로그 페이지의 스크린샷입니다.](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>활동 로그에서 정책 할당 활동 보기

활동 로그에서 정책 할당을 확인하려면 다음을 수행합니다.

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 대시보드로 이동한 다음 활동 로그에서 **세부** **정보 보기를 선택합니다.**
2. 모든 정책 할당을 보거나 상태를 통해 목록을 필터링하여 시작되지 않은  **과제,** 진행 중 또는 완료된 과제만 **표시할 수 있습니다.** 각 과제에 대한 다음 정보가 표시됩니다.
    - **이름**: 정책 할당의 이름입니다. 링크를 클릭하여 자세한 내용을 볼 수 있습니다. 여기에는 정책이 할당된 사용자 수와 완료된 과제 수가 포함되고 진행 중입니다. 또한 일괄 처리의 사용자 목록과 각 사용자의 상태 및 결과가 표시됩니다. 다음은 예제입니다.

        ![스크린샷입니다.](media/activity-log-policy-assignment-detail.png)

    - **제출**: 정책 할당이 제출된 날짜 및 시간입니다.
    - **완료 시간**: 정책 할당이 완료된 날짜 및 시간입니다.
    - **영향**: 일괄 처리의 사용자 수입니다.
    - **전체 상태**: 정책 할당의 상태입니다.

> [!NOTE]
> 사용자 페이지에서 활동 로그에 **얻을** 수도 있습니다. 적용을  클릭하여 대량 정책 할당을 제출하면 페이지 맨 위에 배너가 표시됩니다. **배너에서 활동 로그** 링크를 클릭합니다.

## <a name="related-topics"></a>관련 항목

- [사용자에게 정책 할당](assign-policies.md)
