---
title: 직접 라우팅에 대 한 Ringback 봇 설정
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Ringback 봇을 사용 하 여 통화를 설정할 때 발생할 수 있는 예기치 않은 silences 방지 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9ee3f227faa736d7fdda3ebedc755c8ac5049d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834998"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>직접 라우팅에 대 한 Ringback 봇 설정

이 문서에서는 통화를 설정 하는 데 시간이 오래 걸릴 때 발생할 수 있는 예기치 않은 silences을 방지 하는 데 사용할 수 있는 Ringback bot에 대해 설명 합니다. Ringback 봇은 비 미디어 우회 모드의 직접 라우팅에 사용할 수 있습니다.

때로는 PSTN (공개 통신 네트워크)에서 팀 클라이언트로 들어오는 인바운드 호출이 예상 보다 오래 걸릴 수 있습니다. 이 문제는 다양 한 이유로 발생할 수 있습니다. 이 문제가 발생 하는 경우 발신자는 어떤 작업도 들리지 않으며, 팀 클라이언트가 전화를 걸지 않으며, 통신 공급자가 통화를 취소 했을 수 있습니다.

Ringback bot는이 시나리오에서 발생할 수 있는 예기치 않은 silences을 방지 하는 데 도움이 됩니다. PSTN에서 팀 클라이언트로의 인바운드 호출에 대해 Ringback bot는 호출자에 게 고유한 오디오 신호를 재생 하 여 팀이 통화를 설정 하는 과정에서 진행 중임을 나타냅니다.

> [!NOTE]
> Ringback 봇은 팀 백 엔드 로부터 초기 미디어를 생성 합니다. 일부 국가 및 지역에서는 미디어 흐름이 시작 될 때 통화 요금이 부과 될 수 있습니다.

## <a name="configure-the-ringback-bot"></a>Ringback 봇 구성

[CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) 및 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet을 **GenerateRingingWhileLocatingUser** 매개 변수와 함께 사용 하 여 Ringback bot을 구성 합니다.

Ringback bot를 설정 하려면 **GenerateRingingWhileLocatingUser** 매개 변수를 **$True**으로 설정 합니다. 기본값입니다. 

Ringback bot를 끄려면 **GenerateRingingWhileLocatingUser** 매개 변수를 **$False**으로 설정 합니다. 

## <a name="related-topics"></a>관련 항목

- [팀 PowerShell 개요](teams-powershell-overview.md)