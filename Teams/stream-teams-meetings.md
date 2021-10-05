---
title: 모임 Teams 스트리밍
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 모임에 대한 스트리밍을 설정하고 관리하는 Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127552"
---
# <a name="stream-teams-meetings"></a>모임 Teams 스트리밍

이 문서에서는 모임에 대한 스트리밍을 Teams 도움이 될 것입니다.

## <a name="what-is-streaming-and-how-does-it-work"></a>스트리밍이란 무엇일까요?

스트리밍을 사용하면 조직에서 도달 범위를 확장하고 모임 참석자들에게 더 많은 모임 옵션을 제공합니다. 스트리밍을 사용하도록 설정하면 이끌이는 RTMP(메시징 프로토콜) URL 및 기본 제공 사용자 지정 스트리밍 앱에 Real-Time 메시지를 제공하여 외부 엔드포인트로 모임 및 웨비나를 스트리밍할 수 Teams.

> [!NOTE]
> 라이브 이벤트를 스트리밍할 수 없습니다.

## <a name="set-up-streaming-with-powershell"></a>PowerShell을 통해 스트리밍 설정

PowerShell을 사용하여 스트리밍을 위해 조직을 설정할 수 있습니다. 현재 이 정책은 관리 센터에서 사용할 Teams 없습니다. 사용자당 정책은 라이브 스트리밍을 사용하도록 설정할 **수** 있는 사용자를 지정하는 데 사용됩니다. 이는 기본적으로 해제되어 있습니다.

**Set-CsTeamsMeetingPolicy** cmdlet에서 다음 특성을 Windows PowerShell 스트리밍을 설정할 수 있습니다. cmdlet에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy 를 참조하세요.](/powershell/module/skype/set-csteamsmeetingpolicy)

- LiveStreamingMode

**LiveStreamingMode를** **사용하도록 설정하여** 하나 이상의 사용자에 대한 스트리밍 기능을 설정합니다.

> [!IMPORTANT]
> 이끌이가 웨비나를 스트리밍하기 전에 모임 등록을 켜야 합니다. 자세한 내용은 웨비나 [설정 을 참조하세요.](set-up-webinars.md)

### <a name="assign-the-policy"></a>정책 할당

PowerShell을 통해 정책을 할당하는 방법에 대한 자세한 내용은 에서 정책 [할당을 Teams.](policy-assignment-overview.md)

## <a name="related-topics"></a>관련 항목

- [정책 할당 Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [빠른 시작 - 모임, 웨비나 및 라이브 이벤트](quick-start-meetings-live-events.md)