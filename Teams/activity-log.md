---
title: Microsoft 팀 관리 센터의 활동 로그에서 정책 과제 보기
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft 팀 관리 센터의 활동 로그에서 정책 할당 활동을 보는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a363d934ffd66d04bc3eb778380613e33e460a9
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350082"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>활동 로그에서 정책 과제 보기

Microsoft 팀 관리 센터에서 사용자에 게 정책을 할당 하면 활동 로그에서 해당 정책 할당의 상태를 볼 수 있습니다. 활동 로그에는 지난 30 일간 Microsoft 팀 관리 센터를 통해 20 명 이상의 사용자 일괄 처리에 대 한 정책 할당이 표시 됩니다. 활동 로그에는 정책 패키지 할당이 표시 되지 않으며, Microsoft 팀 관리 센터를 통해 20 명 미만의 사용자의 일괄 처리에 대 한 정책 할당 또는 PowerShell을 통한 정책 할당에는 아무런 변화가 없습니다.

![활동 로그 페이지 스크린샷](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>활동 로그에서 정책 할당 활동 보기

활동 로그에서 정책 할당을 보려면 다음을 수행 합니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **대시보드로**이동한 다음 **활동 로그**에서 **세부 정보 보기**를 선택 합니다.
2. 모든 정책 할당을 확인 하거나 상태별로 목록을 필터링 하 여 시작, **진행**중 또는 완료 **되지**않은 배정만 표시할 수 있습니다. **Completed** 각 과제에 대 한 다음 정보가 표시 됩니다.
    - **Name**: 정책 할당의 이름입니다. 링크를 클릭 하 여 자세한 정보를 확인 합니다. 여기에는 정책에 할당 된 사용자 수와 완료 된 배정 수 (진행 중) 및 시작 되지 않음이 포함 됩니다. 또한 일괄 작업의 사용자 목록과 각 사용자의 상태 및 결과를 볼 수 있습니다. 예를 들면 다음과 같습니다.

        ![의 스크린샷](media/activity-log-policy-assignment-detail.png)

    - **제출**: 정책 할당이 제출 된 날짜 및 시간입니다.
    - **완료 시간**: 정책 할당이 완료 된 날짜 및 시간입니다.
    - **영향**: 일괄 작업의 사용자 수입니다.
    - **전체 상태**: 정책 할당의 상태입니다.

> [!NOTE]
> **사용자** 페이지에서 활동 로그로 이동할 수도 있습니다. **적용** 을 클릭 하 여 대량 정책 할당을 제출 하면 페이지 맨 위에 배너가 표시 됩니다. 배너에서 **활동 로그** 링크를 클릭 합니다.

## <a name="related-topics"></a>관련 항목

- [사용자에 게 정책 할당](assign-policies.md)
