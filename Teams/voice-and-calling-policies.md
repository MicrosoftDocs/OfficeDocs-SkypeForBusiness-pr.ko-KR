---
title: Teams에서 음성 및 통화 정책 관리
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Teams 음성 및 통화 정책에 대해 알아봅니다.
audience: admin
ms.localizationpriority: medium
ms.collection:
- M365-voice
ms.openlocfilehash: 5a6676d29a439ed978385d096c6e8b0584049557
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270293"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a>Microsoft Teams에서 음성 및 통화 정책 관리

음성 및 통화 정책은 Microsoft Teams에서 음성 및 통화를 제어하는 데 사용됩니다.

## <a name="emergency-calling-policies"></a>긴급 통화 정책

[긴급 통화 정책을](manage-emergency-calling-policies.md) 사용하여 조직의 사용자가 긴급 전화를 걸 때 발생하는 작업을 구성합니다. 이러한 정책은 Teams 관리 센터에서 또는 Windows PowerShell 사용하여 관리됩니다.

![긴급 통화 정책의 스크린샷.](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a>긴급 통화 라우팅 정책

조직에서 **전화 시스템 직접 라우팅을** 배포한 경우 [긴급 통화 라우팅 정책을 사용하여 긴급 통화](manage-emergency-call-routing-policies.md) 라우팅 위치, 향상된 응급 서비스 사용 여부 및 응급 서비스에 사용되는 번호를 확인할 수 있습니다. 이러한 정책은 PowerShell을 사용하거나 Microsoft Teams 관리 센터에서 관리됩니다.

![긴급 통화 라우팅 정책의 스크린샷.](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a>호출자 ID 정책

[호출자 ID 정책은 호출자 ID](caller-id-policies.md) 를 변경하거나 차단하는 데 사용됩니다.

![호출자 ID 정책의 스크린샷.](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a>음성 라우팅 정책

[음성 라우팅 정책은](manage-voice-routing-policies.md) PSTN(공중 전화망) 사용 레코드에 대한 컨테이너입니다. 조직에서 **전화 시스템 직접 라우팅** 을 배포한 경우 이러한 정책을 사용할 수 있습니다. 음성 라우팅 정책은 PowerShell 또는 Teams 관리 센터에서 관리할 수 있습니다.

![음성 라우팅 정책의 스크린샷.](media/voice-routing-policy.png)

## <a name="calling-policies"></a>통화 정책

[통화 정책은](teams-calling-policy.md) 사용자가 개인 통화를 할 수 있는지, 통화 그룹에 전화를 걸고, 음성 메일로 통화를 라우팅할 수 있는지 여부를 포함하여 사용자가 사용할 수 있는 통화 및 착신 전환 기능을 제어합니다.

![통화 정책의 스크린샷.](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a>통화 대기 및 정책 검색

[통화 대기 및 검색](call-park-and-retrieve.md) 을 통해 사용자는 다른 사용자를 보류하고 동일한 사용자 또는 다른 사용자가 통화를 계속할 수 있습니다.

![통화 대기 및 검색 정책의 스크린샷.](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a>다이얼 플랜 만들기 및 관리

[전화 걸기 플랜](create-and-manage-dial-plans.md) 은 통화 권한 부여 및 라우팅을 위해 전화 걸기 전화 번호를 변환합니다. PowerShell 또는 Microsoft Teams 관리 센터를 통해 다이얼 플랜을 만들고 관리할 수 있습니다.

![다이얼 플랜의 스크린샷.](media/dial-plans.png)

## <a name="related-topics"></a>관련 항목

* [Microsoft Teams에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)
* [긴급 전화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
* [Microsoft Teams에서 발신자 ID 정책 관리](caller-id-policies.md)
* [음성 라우팅 정책 관리](manage-voice-routing-policies.md)
* [Microsoft Teams에서 통화 정책](teams-calling-policy.md)
* [Microsoft Teams에서 통화 대기 및 검색](call-park-and-retrieve.md)
* [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)
* [정책을 준수하여 Teams 관리](manage-teams-with-policies.md)
