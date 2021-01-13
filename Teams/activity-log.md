---
title: Microsoft Teams 관리 센터의 활동 로그에서 정책 할당 보기
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams 관리 센터의 활동 로그에서 정책 할당 활동을 보는 방법을 배워야 합니다.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821318"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a>활동 로그에서 정책 할당 보기

Microsoft Teams 관리 센터에서 사용자에게 정책을 할당하면 활동 로그에서 해당 정책 할당의 상태를 볼 수 있습니다. 활동 로그는 지난 30일 동안 Microsoft Teams 관리 센터를 통해 20명 이상의 사용자 배치에 대한 정책 할당을 보여줍니다. 활동 로그는 Microsoft Teams 관리 센터를 통해 20명 미만의 사용자 배치에 대한 정책 패키지 할당, 정책 할당 또는 PowerShell을 통한 정책 할당을 표시하지 않습니다.

![활동 로그 페이지의 스크린샷](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>활동 로그에서 정책 할당 활동 보기

활동 로그에서 정책 할당을 확인하려면:

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 대시보드로 이동한 다음 **활동** 로그 아래에서 **세부** 정보 **보기를 선택합니다.**
2. 모든 정책 할당을 보거나 상태를 필터링하여 시작되지 않은 **할당,** 진행 중 또는 완료된 할당만 표시될 **수 있습니다.** 각 할당에 대한 다음 정보가 표시됩니다.
    - **이름:** 정책 할당의 이름입니다. 자세한 내용을 보려면 링크를 클릭합니다. 여기에는 정책이 할당된 사용자 수와 완료된 할당 수, 진행 중, 시작되지 않은 할당 수가 포함됩니다. 또한 일괄 처리의 사용자 목록과 각 사용자에 대한 상태 및 결과가 표시됩니다. 예제는 다음과 같습니다.

        ![다음의 스크린샷](media/activity-log-policy-assignment-detail.png)

    - **제출:** 정책 할당이 제출된 날짜 및 시간입니다.
    - **완료 시간:** 정책 할당이 완료된 날짜 및 시간입니다.
    - **영향:** 일괄 처리의 사용자 수입니다.
    - **전체 상태:** 정책 할당의 상태입니다.

> [!NOTE]
> 사용자 페이지에서 활동 로그를 얻을 **수도** 있습니다. 적용을  클릭하여 대량 정책 할당을 제출하면 페이지 맨 위에 배너가 표시됩니다. **배너에서 활동 로그** 링크를 클릭합니다.

## <a name="related-topics"></a>관련 항목

- [사용자에게 정책 할당](assign-policies.md)
