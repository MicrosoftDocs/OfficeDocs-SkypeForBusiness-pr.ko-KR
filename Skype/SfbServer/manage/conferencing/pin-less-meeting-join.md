---
title: 비즈니스용 Skype 서버에서 PIN이 지원되지 않은 모임 참가 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: '요약: 비즈니스용 Skype 서버에서 PIN이 지원되지 않은 모임 참가 옵션을 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119397"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="21702-103">비즈니스용 Skype 서버에서 PIN이 지원되지 않은 모임 참가 구성</span><span class="sxs-lookup"><span data-stu-id="21702-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="21702-104">**요약:** 비즈니스용 Skype 서버에서 PIN이 지원되지 않은 모임 참가 옵션을 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21702-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="21702-105">전화 접속 발신자는 모임 참가를 시도할 때 CAA(Conference 자동 전화 교환) 서비스는 발표자에 통화가 아직 연결되지 않은 경우&#x2014; 발신자에 리더 PIN을 입력하지 않은 경우 대기실과 다른 보류 펜에 발신자 번호를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="21702-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="21702-106">PIN 없는 모임 참가 옵션을 사용하면 전화 접속 발신자는 통화의 첫 번째 사용자인 경우에도 리더 PIN을 입력하지 않고도 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="21702-107">이 기능을 구성할 때 다음에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="21702-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="21702-108">비공개 모임에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21702-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="21702-109">PSTN 발신자는 인증된 사용자의 존재 없이 비공개 모임에 계속 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="21702-110">설정이 변경된 후 기존의 모든 비공개 모임과 새 비공개 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21702-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="21702-111">이끌이의 사이트 또는 전역 수준에서 사용하도록 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="21702-112">대기실을 무시할 수 있는 사용자에 대한 옵션은 다음 중 하나에 대해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="21702-113">**발신자에 대한 조직의 모든 사람이 직접 연결됩니다.**</span><span class="sxs-lookup"><span data-stu-id="21702-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="21702-114">**발신자에** 대한 모든 사용자(제한 없음)가 직접 연결됩니다(기본 설정입니다.)</span><span class="sxs-lookup"><span data-stu-id="21702-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="21702-115">PIN이 연결되지 않은 조인을 사용하도록 구성된 경우 CAA 서비스는 여전히 리더 PIN을 묻는 메시지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21702-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="21702-116">사용자는 PIN 입력 여부에 따라 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="21702-117">그러나 리더 PIN을 입력할 수 있는 기능을 유지하면 전화 접속 발신자에서 리더로 인증하고 필요한 경우 모임을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="21702-118">PIN이 적은 모임 참가 구성</span><span class="sxs-lookup"><span data-stu-id="21702-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="21702-119">사용자에 대해 PIN이 아닌 모임 참가를 사용하도록 설정하려면 다음과 같이 AllowAnonymousPstnActivation 매개 변수와 [함께 Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21702-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="21702-120">예를 들어 다음 명령은 Redmond 사이트에 대해 PIN이 적은 모임 참가를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="21702-121">보안을 위해 PIN이 설정되지된 모임 참가가 설정되어 있는 경우 ConferencingPolicy가 다음과 같이 설정되어 있는지를 보장하여 익명 사용자가 전화를 걸지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21702-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="21702-122">자세한 내용은 [Set-CsConferencingPolicy를 참조하세요.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="21702-122">For more information, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
