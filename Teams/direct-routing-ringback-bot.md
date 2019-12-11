---
title: 직접 라우팅에 대 한 Ringback 봇 설정
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Ringback 봇을 사용 하 여 통화를 설정할 때 발생할 수 있는 예기치 않은 silences 방지 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fcb69ba1bc612fe940054ec982eb7462c6679be
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962505"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="44289-103">직접 라우팅에 대 한 Ringback 봇 설정</span><span class="sxs-lookup"><span data-stu-id="44289-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="44289-104">이 문서에서는 통화를 설정 하는 데 시간이 오래 걸릴 때 발생할 수 있는 예기치 않은 silences을 방지 하는 데 사용할 수 있는 Ringback bot에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="44289-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="44289-105">Ringback 봇은 비 미디어 우회 모드의 직접 라우팅에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44289-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="44289-106">때로는 PSTN (공개 통신 네트워크)에서 팀 클라이언트로 들어오는 인바운드 호출이 예상 보다 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44289-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="44289-107">이 문제는 다양 한 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44289-107">This can occur for various reasons.</span></span> <span data-ttu-id="44289-108">이 문제가 발생 하는 경우 발신자는 어떤 작업도 들리지 않으며, 팀 클라이언트가 전화를 걸지 않으며, 통신 공급자가 통화를 취소 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44289-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="44289-109">Ringback bot는이 시나리오에서 발생할 수 있는 예기치 않은 silences을 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44289-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="44289-110">PSTN에서 팀 클라이언트로의 인바운드 호출에 대해 Ringback bot는 호출자에 게 고유한 오디오 신호를 재생 하 여 팀이 통화를 설정 하는 과정에서 진행 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="44289-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="44289-111">Ringback 봇은 팀 백 엔드 로부터 초기 미디어를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="44289-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="44289-112">일부 국가 및 지역에서는 미디어 흐름이 시작 될 때 통화 요금이 부과 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44289-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="44289-113">Ringback 봇 구성</span><span class="sxs-lookup"><span data-stu-id="44289-113">Configure the Ringback bot</span></span>

<span data-ttu-id="44289-114">[CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) 및 [CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet을 **GenerateRingingWhileLocatingUser** 매개 변수와 함께 사용 하 여 Ringback bot을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="44289-114">Use the [Set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="44289-115">Ringback bot를 설정 하려면 **GenerateRingingWhileLocatingUser** 매개 변수를 **$True**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44289-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="44289-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="44289-116">This is the default value.</span></span> 

<span data-ttu-id="44289-117">Ringback bot를 끄려면 **GenerateRingingWhileLocatingUser** 매개 변수를 **$False**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44289-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="44289-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="44289-118">Related topics</span></span>

- [<span data-ttu-id="44289-119">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="44289-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)