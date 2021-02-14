---
title: 직접 라우팅에 대한 벨소리 봇 설정
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: 직접 라우팅에 대한 벨소리 봇을 사용하여 호출이 설정될 때 발생할 수 있는 예기치 않은 묵음을 방지하는 방법을 배워야 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827518"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>직접 라우팅에 대한 벨소리 봇 설정

이 문서에서는 호출을 설정하는 데 시간이 더 오래 걸리는 경우 발생할 수 있는 예기치 않은 묵음을 방지하는 데 사용할 수 있는 벨소리 봇에 대해 설명하고 있습니다. 벨소리백 봇은 미디어 우회 모드가 아닌 직접 라우팅에 사용할 수 있습니다.

경우에 따라 PSTN(공용 전화망)에서 Teams 클라이언트로의 인바운드 통화를 설정하는 데 예상보다 오래 걸릴 수 있습니다. 이는 다양한 이유로 발생할 수 있습니다. 이 경우 발신자가 아무 소리도 들리지 않을 수 있으며 Teams 클라이언트는 벨이 울리지 않습니다. 일부 통신 공급자는 통화를 취소할 수 있습니다.

벨소리 봇은 이 시나리오에서 발생할 수 있는 예기치 않은 묵음을 방지하는 데 도움이 됩니다. PSTN에서 Teams 클라이언트로의 인바운드 호출의 경우 벨소리 봇은 발신자에 대한 독특한 오디오 신호를 재생하여 Teams가 통화를 설정하는 중입니다.

> [!NOTE]
> 벨소리백 봇은 Teams 백end에서 초기 미디어를 생성합니다. 일부 국가 및 지역에서는 미디어가 흐르기 시작할 때 통화 요금이 부과될 수 있습니다.

## <a name="configure-the-ringback-bot"></a>벨소리 봇 구성

[Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet을 사용하여 이전에 정의된 SBC(세션 테두리 컨트롤러) 구성을 수정하거나 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 **GenerateRingingWhileLocatingUser** 매개 변수와 함께 새 SBC 구성을 만들어 벨소리 봇을 구성합니다.

- Ringback 봇을 켜기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 **$True.** 기본값입니다. 

- Ringback 봇을 끄기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 **$False.** 

## <a name="related-topics"></a>관련 항목

- [Teams PowerShell 개요](teams-powershell-overview.md)
