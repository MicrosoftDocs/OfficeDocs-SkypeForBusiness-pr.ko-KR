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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="b853e-103">직접 라우팅에 대한 링백 봇 설정</span><span class="sxs-lookup"><span data-stu-id="b853e-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="b853e-104">이 문서에서는 호출을 설정하는 데 시간이 오래 걸리면 발생할 수 있는 예기치 않은 침묵을 방지하는 데 사용할 수 있는 Ringback 봇을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="b853e-105">링백 봇은 비미디어 우회 모드에서 직접 라우팅에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="b853e-106">공용 PSTN(공용 전화 네트워크)에서 Teams 클라이언트로의 인바운드 호출이 설정되는 데 예상보다 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="b853e-107">이는 다양한 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-107">This can occur for various reasons.</span></span> <span data-ttu-id="b853e-108">이 경우 호출자가 아무 소리도 들리지 않을 수 있으며 Teams 클라이언트가 울리지 않습니다. 일부 통신 공급자는 호출을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="b853e-109">링백 봇은 이 시나리오에서 발생할 수 있는 예기치 않은 침묵을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="b853e-110">PSTN에서 Teams 클라이언트로의 인바운드 호출의 경우 Ringback 봇은 호출자에 대한 독특한 오디오 신호를 재생하여 Teams가 호출을 설정하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="b853e-111">Ringback 봇은 Teams 백end에서 초기 미디어를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="b853e-112">일부 국가 및 지역에서는 미디어가 흐르기 시작할 때 호출에 대한 요금이 청구될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="b853e-113">링백 봇 구성</span><span class="sxs-lookup"><span data-stu-id="b853e-113">Configure the Ringback bot</span></span>

<span data-ttu-id="b853e-114">[Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet을 사용하여 이전에 정의된 SBC(세션 테두리 컨트롤러) 구성 또는 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 **CreateRingingWhileLocatingUser** 매개 변수와 함께 새 SBC 구성을 만들어 링백 봇을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-114">Use the [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="b853e-115">링백 봇을 켜기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 를 **$True.**</span><span class="sxs-lookup"><span data-stu-id="b853e-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="b853e-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b853e-116">This is the default value.</span></span> 

- <span data-ttu-id="b853e-117">링백 봇을 해제하기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 를 으로 **$False.**</span><span class="sxs-lookup"><span data-stu-id="b853e-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b853e-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b853e-118">Related topics</span></span>

- [<span data-ttu-id="b853e-119">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="b853e-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)