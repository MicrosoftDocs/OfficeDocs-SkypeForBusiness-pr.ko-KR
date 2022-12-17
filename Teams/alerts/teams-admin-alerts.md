---
title: Microsoft Teams 모니터링 및 경고
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리 센터에서 사용할 수 있는 Teams 경고 및 알림 기능에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 18279954a9bd71932422bd60519977288ae30ca6
ms.sourcegitcommit: b710fc61558a0e031d4e3e4000f234c495e2c4c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2022
ms.locfileid: "69438256"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Microsoft Teams 모니터링 및 경고

Microsoft Teams에 대한 새로운 모니터링 및 경고 기능은 Teams 관리 센터에서 사용할 수 있습니다. Teams 관리 센터의 **알림 & 경고** 섹션에서 사용할 수 있는 다양한 규칙 집합을 사용하여 Teams 기능을 모니터링하고 경고를 받습니다. 예를 들어 예기치 않게 오프라인 상태가 되면 IP 휴대폰, Android의 Teams 룸 등의 Teams 디바이스의 상태를 적극적으로 모니터링할 수 있습니다.  

조직에서는 Teams 모니터링 및 경고를 사용하여 다음 항목을 수행할 수 있습니다.

- Teams 기능 자동 관리
- 예기치 않은 항목이 표시되면 경고를 표시합니다.
- 정정 작업을 수행하여 작업을 다시 궤도에 올 수 있습니다.

> [!NOTE]
> Teams 관리 센터 내의 경고 기능은 GCC/GCC-High 환경에서 사용할 수 없습니다.

## <a name="how-to-manage-monitoring-and-alerting"></a>모니터링 및 경고를 관리하는 방법

 경고 규칙을 구성하려면 Microsoft 365의 전역 관리자 또는 Teams 서비스 관리자여야 합니다. [Teams 관리자 역할 및 각 관리자 역할이](../using-admin-roles.md) 액세스할 수 있는 보고서에 대한 자세한 내용은 Teams 관리자 역할을 사용하여 Teams 관리를 참조하세요.

1. Teams 관리 센터에 로그인합니다.
2. 왼쪽 탐색 영역에서 **알림 & 경고를** 선택합니다.
3. 규칙에서 구성하려는 **규칙을** 선택합니다.

## <a name="teams-monitoring-rules-reference"></a>Teams 모니터링 규칙 참조

다양한 모니터링 기능 및 구성 기능을 추가하여 Teams 모니터링 환경을 계속 추가하고 개선합니다. 다음은 Teams 관리 센터에서 현재 사용할 수 있는 Teams 모니터링 규칙 목록입니다.


|규칙  |모니터링 기능|모니터링되는 항목 |
|---------|---------|---------|
|앱 제출  |Teams 앱 | 승인을 위해 제출된 Teams 앱을 적극적으로 모니터링합니다.|
|[디바이스 상태 규칙](device-health-status.md)  |Teams 디바이스 | Teams 디바이스가 오프라인으로 전환되면 적극적으로 모니터링합니다.|
