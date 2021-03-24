---
title: 직접 라우팅에 대한 링백 봇 설정
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 직접 라우팅에 대한 Ringback 봇을 사용하여 호출이 설정될 때 발생할 수 있는 예기치 않은 침묵을 방지하는 방법에 대해 자세히 알아보습니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098424"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>직접 라우팅에 대한 링백 봇 설정

이 문서에서는 호출을 설정하는 데 시간이 오래 걸리면 발생할 수 있는 예기치 않은 침묵을 방지하는 데 사용할 수 있는 Ringback 봇을 설명합니다. 링백 봇은 비미디어 우회 모드에서 직접 라우팅에 사용할 수 있습니다.

공용 PSTN(공용 전화 네트워크)에서 Teams 클라이언트로의 인바운드 호출이 설정되는 데 예상보다 오래 걸릴 수 있습니다. 이는 다양한 이유로 발생할 수 있습니다. 이 경우 호출자가 아무 소리도 들리지 않을 수 있으며 Teams 클라이언트가 울리지 않습니다. 일부 통신 공급자는 호출을 취소할 수 있습니다.

링백 봇은 이 시나리오에서 발생할 수 있는 예기치 않은 침묵을 방지하는 데 도움이 됩니다. PSTN에서 Teams 클라이언트로의 인바운드 호출의 경우 Ringback 봇은 호출자에 대한 독특한 오디오 신호를 재생하여 Teams가 호출을 설정하는 중입니다.

> [!NOTE]
> Ringback 봇은 Teams 백end에서 초기 미디어를 생성합니다. 일부 국가 및 지역에서는 미디어가 흐르기 시작할 때 호출에 대한 요금이 청구될 수 있습니다.

## <a name="configure-the-ringback-bot"></a>링백 봇 구성

[Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet을 사용하여 이전에 정의된 SBC(세션 테두리 컨트롤러) 구성 또는 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 **CreateRingingWhileLocatingUser** 매개 변수와 함께 새 SBC 구성을 만들어 링백 봇을 구성합니다.

- 링백 봇을 켜기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 를 **$True.** 기본값입니다. 

- 링백 봇을 해제하기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 를 으로 **$False.** 

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)