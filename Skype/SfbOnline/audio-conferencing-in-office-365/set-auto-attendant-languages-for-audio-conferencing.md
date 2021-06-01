---
title: 온라인에서 오디오 회의에 대한 자동 비즈니스용 Skype 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 온라인에서 오디오 회의 번호에 대한 오디오 회의 자동 참석 언어를 선택하는 비즈니스용 Skype 참조하세요.
ms.openlocfilehash: 714312989bc3898fea2ed0d335fed8f5f2eebbb3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237024"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="4771e-103">온라인에서 오디오 회의에 대한 자동 비즈니스용 Skype 설정</span><span class="sxs-lookup"><span data-stu-id="4771e-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="4771e-104">자동 참석 언어 설정에 대한 자세한 내용은 Microsoft Teams 에서 오디오 회의에 대한 자동 참석 언어 [Microsoft Teams.](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)</span><span class="sxs-lookup"><span data-stu-id="4771e-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="4771e-105">오디오 회의 자동 비즈니스용 Skype 모임에 참가할 때 다양한 언어로 오디오 발신자들을 맞이할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="4771e-106">하나의 기본 언어와 최대 4개의 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="4771e-107">설정한 기본 언어는 먼저 사용하며, 보조 언어는 선택한 순서대로 자동 참석자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="4771e-108">전용 범주의 오디오 회의 번호의 언어만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="4771e-109">공유 오디오 회의 번호의 언어를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="4771e-110">회의 자동 참석 언어 설정</span><span class="sxs-lookup"><span data-stu-id="4771e-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="4771e-111">이 단계를 [](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 수행하려면 전역 관리자 또는 비즈니스용 Skype [관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="4771e-112">관리 **비즈니스용 Skype** 왼쪽 탐색에서 레거시 포털 **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="4771e-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="4771e-113">레거시 포털에서 오디오 회의를 선택한 다음 Microsoft **브리지 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4771e-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="4771e-114">목록에서 오디오 회의 전화 번호를 선택하고 작업 창에서 언어 설정 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4771e-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="4771e-115">전용 오디오 회의 번호의 언어를 변경할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="4771e-116">언어 **설정 페이지에서** 기본 언어  목록을 클릭하여 사용 가능한 언어의 전체 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="4771e-117">필요한 경우 각 보조 언어  목록을 클릭하여 보조 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4771e-118">지원되는 기본 언어 및 보조 언어가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="4771e-119">목록에서 선택한 순서는 발신자에 제시된 언어의 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="4771e-120">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="4771e-121">다른 것을 알고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="4771e-121">Want else should I know?</span></span>

- <span data-ttu-id="4771e-122">오디오 회의에 지원되는 언어 목록은 오디오 회의 지원 언어 [를 참조하세요.](/MicrosoftTeams/audio-conferencing-supported-languages)</span><span class="sxs-lookup"><span data-stu-id="4771e-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="4771e-123">언어는 전용으로 설정할 수 있지만 공유 전화 번호는 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="4771e-124">Microsoft를 사용하여 오디오 회의를 사용할 수 있는 Microsoft 365 Office 365 국가/지역 목록을 보시고 오디오 회의의 전화 숫자를 [참조하세요.](phone-numbers-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="4771e-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="4771e-125">Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4771e-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="4771e-126">이 단계를 자동화하기 위해 [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) 및 [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4771e-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) and [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlets.</span></span>
  
<span data-ttu-id="4771e-127">자세한 내용은 온라인 관리 Windows PowerShell 작업을 수행하기 위해 비즈니스용 Skype [참조하세요.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="4771e-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4771e-128">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4771e-128">Related topics</span></span>

[<span data-ttu-id="4771e-129">오디오 회의를 시도하거나 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="4771e-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
