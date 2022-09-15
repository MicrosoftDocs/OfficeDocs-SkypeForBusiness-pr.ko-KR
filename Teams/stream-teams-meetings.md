---
title: Stream Teams 모임
author: MicrosoftHeidi
ms.author: heidip
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
description: Teams 모임에 대한 스트리밍을 설정하고 관리하는 방법을 알아봅니다.
ms.openlocfilehash: b8394abfe66ecde6813e383e0473bcdca2a0ad9f
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67707005"
---
# <a name="stream-teams-meetings"></a>Stream Teams 모임

이 문서는 Teams 모임에 대한 스트리밍을 설정하는 데 도움이 됩니다.

## <a name="what-is-streaming-and-how-does-it-work"></a>스트리밍이란 무엇이며 어떻게 작동하나요?

스트리밍을 사용하면 조직에서 도달 범위를 확장하고 모임 참석자에게 더 많은 모임 옵션을 제공할 수 있습니다. 스트리밍을 사용하도록 설정하면 이끌이는 Teams의 기본 제공 사용자 지정 스트리밍 앱에 rtMP(Real-Time Messaging Protocol) URL 및 키를 제공하여 모임 및 웨비나를 외부 엔드포인트로 스트리밍할 수 있습니다.

> [!NOTE]
> 라이브 이벤트를 스트리밍할 수 없습니다.

## <a name="set-up-streaming-with-powershell"></a>PowerShell을 사용하여 스트리밍 설정

PowerShell을 사용하여 스트리밍하도록 조직을 설정할 수 있습니다. 현재 이 정책은 Teams 관리 센터에서 사용할 수 없습니다. 사용자별 정책은 라이브 스트리밍을 사용하도록 설정할 수 **있는 사용자를** 지정하는 데 사용됩니다. 이는 기본적으로 해제되어 있습니다.

**Windows PowerShell Set-CsTeamsMeetingPolicy** cmdlet 내에서 다음 특성을 사용하여 스트리밍을 설정할 수 있습니다. cmdlet에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy를 참조하세요](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

**LiveStreamingMode를** **사용** 으로 설정하여 하나 이상의 사용자에 대한 스트리밍 기능을 켭니다.

> [!IMPORTANT]
> 이끌이가 웹 세미나를 스트리밍하려면 모임 등록을 설정해야 합니다. 자세한 내용은 [웨비나 설정을 참조하세요](set-up-webinars.md).

### <a name="assign-the-policy"></a>정책 할당

PowerShell을 사용하여 정책을 할당하는 방법에 대한 자세한 내용은 [Teams에서 정책 할당을 참조하세요](policy-assignment-overview.md).

## <a name="related-topics"></a>관련 주제

- [Teams에서 정책 할당](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [빠른 시작 - 모임, 웨비나 및 라이브 이벤트](quick-start-meetings-live-events.md)