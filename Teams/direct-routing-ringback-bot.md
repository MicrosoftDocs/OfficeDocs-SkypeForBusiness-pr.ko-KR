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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="acf25-103">직접 라우팅에 대한 벨소리 봇 설정</span><span class="sxs-lookup"><span data-stu-id="acf25-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="acf25-104">이 문서에서는 호출을 설정하는 데 시간이 더 오래 걸리는 경우 발생할 수 있는 예기치 않은 묵음을 방지하는 데 사용할 수 있는 벨소리 봇에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="acf25-105">벨소리백 봇은 미디어 우회 모드가 아닌 직접 라우팅에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="acf25-106">경우에 따라 PSTN(공용 전화망)에서 Teams 클라이언트로의 인바운드 통화를 설정하는 데 예상보다 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="acf25-107">이는 다양한 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-107">This can occur for various reasons.</span></span> <span data-ttu-id="acf25-108">이 경우 발신자가 아무 소리도 들리지 않을 수 있으며 Teams 클라이언트는 벨이 울리지 않습니다. 일부 통신 공급자는 통화를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="acf25-109">벨소리 봇은 이 시나리오에서 발생할 수 있는 예기치 않은 묵음을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="acf25-110">PSTN에서 Teams 클라이언트로의 인바운드 호출의 경우 벨소리 봇은 발신자에 대한 독특한 오디오 신호를 재생하여 Teams가 통화를 설정하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="acf25-111">벨소리백 봇은 Teams 백end에서 초기 미디어를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="acf25-112">일부 국가 및 지역에서는 미디어가 흐르기 시작할 때 통화 요금이 부과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="acf25-113">벨소리 봇 구성</span><span class="sxs-lookup"><span data-stu-id="acf25-113">Configure the Ringback bot</span></span>

<span data-ttu-id="acf25-114">[Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet을 사용하여 이전에 정의된 SBC(세션 테두리 컨트롤러) 구성을 수정하거나 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 **GenerateRingingWhileLocatingUser** 매개 변수와 함께 새 SBC 구성을 만들어 벨소리 봇을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="acf25-115">링백 봇을 켜기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 **$True.**</span><span class="sxs-lookup"><span data-stu-id="acf25-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="acf25-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="acf25-116">This is the default value.</span></span> 

- <span data-ttu-id="acf25-117">Ringback 봇을 끄기 위해 **GenerateRingingWhileLocatingUser** 매개 변수를 **$False.**</span><span class="sxs-lookup"><span data-stu-id="acf25-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="acf25-118">관련 항목</span><span class="sxs-lookup"><span data-stu-id="acf25-118">Related topics</span></span>

- [<span data-ttu-id="acf25-119">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="acf25-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
