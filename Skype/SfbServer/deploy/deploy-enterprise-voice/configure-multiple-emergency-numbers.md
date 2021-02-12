---
title: 비즈니스용 Skype에서 여러 긴급 번호 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: 이 항목을 읽고 비즈니스용 Skype 서버에서 여러 긴급 번호를 구성하는 방법을 배워야 합니다.
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804108"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="7b7b8-103">비즈니스용 Skype에서 여러 긴급 번호 구성</span><span class="sxs-lookup"><span data-stu-id="7b7b8-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="7b7b8-104">이 항목을 읽고 비즈니스용 Skype 서버에서 여러 긴급 번호를 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="7b7b8-105">비즈니스용 Skype 서버는 이제 클라이언트에 대해 여러 긴급 번호를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="7b7b8-106">여러 긴급 번호는 2016년 6월 누적 업데이트에 도입된 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="7b7b8-107">여러 긴급 번호를 지원하도록 환경을 구성하기 전에 비즈니스용 Skype 서버에서 여러 긴급 번호에 대한 [계획을 읽어야 합니다.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="7b7b8-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7b7b8-108">아직 2016년 11월 누적 업데이트로 업그레이드하지 않은 경우 비즈니스용 [Skype 서버 2015에](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)대한 업데이트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="7b7b8-109">2016년 11월 누적 업데이트를 통해 지원 긴급 번호 수는 5에서 100으로 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="7b7b8-110">여러 긴급 번호 구성</span><span class="sxs-lookup"><span data-stu-id="7b7b8-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="7b7b8-111">여러 긴급 번호를 구성하기 위해 New-CsEmergencyNumber cmdlet을 사용하여 [New-CsLocationPolicy 및 Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용하여 EmergencyNumbers 매개 변수를 지정합니다. [](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7b7b8-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="7b7b8-112">필요한 PSTN 사용 및 위치와 같은 모든 위치 정책 매개 변수에 대한 자세한 내용은 [Set-CsLocationPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7b7b8-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="7b7b8-113">다음 명령은 이 cmdlet을 사용하여 전화 문자열 911이 있는 새 긴급 New-CsEmergency 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="7b7b8-114">다음 명령은 이 cmdlet에서 EmergencyNumbers 매개 변수를 지정하여 지정된 위치 정책에 Set-CsLocationPolicy 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="7b7b8-115">다음 예에서는 단일 다이얼 마스크 112를 사용하여 긴급 번호를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="7b7b8-116">다음 명령은 여러 다이얼 마스크가 있는 긴급 번호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="7b7b8-117">다음 예에서는 여러 다이얼 마스크가 있는 긴급 번호를 여러 개 추가한 다음 긴급 번호를 지정된 위치 정책에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7b7b8-118">다음 예에서는 911과 450을 모두 사용하는 의료 서비스 공급자에 대해 여러 긴급 번호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7b7b8-119">다음 예에서는 런던 시에 대해 여러 긴급 번호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7b7b8-120">다음 예에서는 인도에 대해 여러 긴급 번호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="7b7b8-121">다음 예에서는 Dial 문자열 911 및 Dial 마스크 112 및 999가 있는 기존 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7b7b8-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
