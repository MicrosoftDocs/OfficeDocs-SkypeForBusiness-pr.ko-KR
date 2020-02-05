---
title: 비즈니스용 Skype에서 여러 응급 번호 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype 서버에서 여러 응급 번호를 구성 하는 방법을 알아보려면이 항목을 참조 하세요.
ms.openlocfilehash: 9805462d8c9498af3e3cf1cb743e2af9e08ec285
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768121"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="bf71d-103">비즈니스용 Skype에서 여러 응급 번호 구성</span><span class="sxs-lookup"><span data-stu-id="bf71d-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="bf71d-104">비즈니스용 Skype 서버에서 여러 응급 번호를 구성 하는 방법을 알아보려면이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf71d-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="bf71d-105">이제 비즈니스용 Skype 서버에서 클라이언트에 대 한 여러 응급 번호를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="bf71d-106">여러 비상 번호는 6 월 2016 누적 업데이트에 도입 된 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="bf71d-107">여러 응급 번호를 지원 하도록 환경을 구성 하기 전에 [비즈니스용 Skype 서버에서 여러 응급 번호 요금제](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="bf71d-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bf71d-108">11 월 2016 누적 업데이트로 아직 업그레이드 하지 않은 경우 비즈니스용 [Skype Server 2015 업데이트](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf71d-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="bf71d-109">11 월 2016 누적 업데이트를 사용 하는 경우 지원 되는 응급 번호 수는 5에서 100로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="bf71d-110">여러 긴급 번호 구성</span><span class="sxs-lookup"><span data-stu-id="bf71d-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="bf71d-111">여러 비상 번호를 구성 하려면 CsEmergencyNumber cmdlet을 사용 하 여 [새-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) 및 [Set cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlet에 EmergencyNumbers 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="bf71d-112">PSTN 사용 및 필수 위치와 같은 모든 위치 정책 매개 변수에 대 한 자세한 설명은 [Set CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf71d-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="bf71d-113">다음 명령은 CsEmergency cmdlet을 사용 하 여 dial 문자열 911를 사용 하 여 새 비상 번호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="bf71d-114">다음 명령은 Set-CsLocationPolicy cmdlet에서 EmergencyNumbers 매개 변수를 지정 하 여 번호를 지정 된 위치 정책에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="bf71d-115">다음 예제에서 비상 번호는 단일 다이얼 마스크로 생성 됩니다. 112:</span><span class="sxs-lookup"><span data-stu-id="bf71d-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="bf71d-116">다음 명령은 여러 다이얼 마스크가 있는 비상 번호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="bf71d-117">다음 예에서는 여러 개의 전화 접속 마스크를 사용 하 여 여러 응급 번호를 추가한 다음 비상 번호를 지정 된 위치 정책에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="bf71d-118">다음 예에서는 911 및 450를 모두 사용 하는 의료 보험 제공자에 대해 여러 비상 번호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="bf71d-119">다음 예에서는 London의 구/군/시에 대해 여러 비상 번호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="bf71d-120">다음 예에서는 인도에 대 한 여러 응급 번호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="bf71d-121">다음 예제에서는 Dial 문자열 911 및 다이얼 마스크 112 및 999이 있는 기존 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf71d-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


