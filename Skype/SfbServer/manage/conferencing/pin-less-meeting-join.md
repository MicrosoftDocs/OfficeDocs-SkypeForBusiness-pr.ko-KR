---
title: 비즈니스용 Skype 서버에서 핀 덜 모임 참가 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '요약: 비즈니스용 Skype 서버에서 핀 없는 모임 참가 옵션을 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a52738f2ca679838ab7687cde2c017e3364542a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818489"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="234f1-103">비즈니스용 Skype 서버에서 핀 덜 모임 참가 구성</span><span class="sxs-lookup"><span data-stu-id="234f1-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="234f1-104">**요약:** 비즈니스용 Skype 서버에서 핀 없는 모임 참가 옵션을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="234f1-105">전화 접속 발신자가 모임에 참가 하려고 시도 하는 경우, 컨퍼런스 자동 전화 교환 (CAA) 서비스는 해당 발신자가 아직 통화 중이 아니고 전화 접속 발신자가 지시선 핀을 입력 하지 않은 경우에는 대기실와는 다른 대기 &#x2014;을 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="234f1-106">고정 없는 모임 참가 옵션을 사용 하면 전화 접속 발신자가 통화 중에 첫 번째 사용자 인 경우에도 지시선 PIN을 입력 하지 않고도 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="234f1-107">이 기능을 구성할 때 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="234f1-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="234f1-108">비공개 모임에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="234f1-109">PSTN 호출자가 인증 된 사용자 없이 비공개 모임에 유지할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="234f1-110">설정이 변경 되 면 기존 및 새 비공개 모임 모두에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="234f1-111">이끌이 사이트 또는 전역 수준에서 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="234f1-112">대기실를 우회할 수 있는 사용자에 대 한 옵션은 다음 중 하나에 대해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="234f1-113">**호출자가 있는 조직의 모든 사용자에 게 직접 액세스**</span><span class="sxs-lookup"><span data-stu-id="234f1-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="234f1-114">**모든 사람이 (제한 없음) 호출자를 직접 가져옵니다** (이는 기본 설정).</span><span class="sxs-lookup"><span data-stu-id="234f1-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="234f1-115">핀이 없는 참가를 사용 하도록 구성 된 경우 CAA 서비스는 여전히 리더 PIN을 묻는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="234f1-116">사용자는 PIN이 입력 되었는지 여부에 상관 없이 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="234f1-117">그러나, 지시선 PIN을 입력 하는 기능을 통해 전화 접속 발신자가 리더를 인증 하 고 필요한 경우 모임을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="234f1-118">핀 더 적은 모임 참가 구성</span><span class="sxs-lookup"><span data-stu-id="234f1-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="234f1-119">사용자에 대 한 핀 없는 모임 참가를 사용 하도록 설정 하려면 다음과 같이 AllowAnonymousPstnActivation 매개 변수와 함께 [CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="234f1-120">예를 들어 다음 명령을 사용 하 여 사이트 Redmond에 대 한 핀 덜 모임 참가를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="234f1-121">고정이 아닌 모임 참가 연결이 설정 되어 있는 경우, ConferencingPolicy가 다음과 같이 설정 되도록 하 여 익명 사용자가 전화 걸기를 할 수 없도록 제한 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="234f1-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="234f1-122">자세한 내용은 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="234f1-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

