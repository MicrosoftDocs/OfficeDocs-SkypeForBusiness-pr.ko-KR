---
title: 비즈니스용 Skype Online에서 오디오 회의에 대한 자동 전화 연결 언어 설정
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
description: 비즈니스용 Skype Online의 오디오 회의 번호에 대한 오디오 회의 자동 전화 회의 언어를 선택하는 방법을 참조하세요.
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163909"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="bf3a1-103">비즈니스용 Skype Online에서 오디오 회의에 대한 자동 전화 연결 언어 설정</span><span class="sxs-lookup"><span data-stu-id="bf3a1-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="bf3a1-104">Microsoft Teams에서 자동 참석 언어 설정에 대한 자세한 내용은 Microsoft Teams에서 오디오 회의에 대한 자동 참석 언어 [설정을 참조하세요.](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)</span><span class="sxs-lookup"><span data-stu-id="bf3a1-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="bf3a1-105">비즈니스용 Skype의 오디오 회의 자동 전화 번호는 모임에 참가할 때 다양한 언어로 오디오 발신자들에게 인사말을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="bf3a1-106">하나의 기본 언어와 최대 4개의 보조 언어를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="bf3a1-107">설정한 기본 언어는 먼저 사용하며, 보조 언어는 선택한 순서대로 자동 attendant에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="bf3a1-108">전용 범주에 속하는 오디오 회의 번호의 언어만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="bf3a1-109">공유 오디오 회의 번호의 언어는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="bf3a1-110">회의 자동 참석 언어 설정</span><span class="sxs-lookup"><span data-stu-id="bf3a1-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="bf3a1-111">이 단계를 [수행하려면](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 전역 관리자 또는 [비즈니스용 Skype](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-111">You must be a [global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="bf3a1-112">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 레거시 **포털로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="bf3a1-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="bf3a1-113">레거시 포털에서 오디오 회의를 선택한 다음 Microsoft **브리지를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf3a1-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="bf3a1-114">목록에서 오디오 회의 전화 번호를 선택하고 작업 창에서 언어 **설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bf3a1-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="bf3a1-115">전용 오디오 회의 번호의 언어만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="bf3a1-116">언어 **설정 페이지에서** 기본 언어  목록을 클릭하여 사용 가능한 언어의 전체 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="bf3a1-117">필요한 경우 각 보조 언어  목록을 클릭하여 보조 언어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bf3a1-118">지원되는 기본 및 보조 언어가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="bf3a1-119">목록에서 선택한 순서는 발신자에 제시된 언어의 순서가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="bf3a1-120">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="bf3a1-121">알아야 할 다른 것이 있나요?</span><span class="sxs-lookup"><span data-stu-id="bf3a1-121">Want else should I know?</span></span>

- <span data-ttu-id="bf3a1-122">오디오 회의에 지원되는 언어 목록을 보시고 오디오 회의 지원 언어를 [참조하세요.](/MicrosoftTeams/audio-conferencing-supported-languages)</span><span class="sxs-lookup"><span data-stu-id="bf3a1-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="bf3a1-123">언어는 전용으로 설정할 수 있지만 공유 전화 번호에는 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="bf3a1-124">공급자로 Microsoft를 사용하여 Microsoft 365 또는 Office 365에서 오디오 회의를 사용할 수 있는 국가/지역 [](phone-numbers-for-audio-conferencing.md)목록을 표시하는 경우 오디오 회의 전화 번호를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-124">To see a list of countries/regions in which Audio Conferencing in Microsoft 365 or Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="bf3a1-125">이 기능을 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bf3a1-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="bf3a1-126">이 단계를 자동화하기 위해 [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) 및 [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf3a1-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) and [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="bf3a1-127">자세한 내용은 비즈니스용 Skype Online Windows PowerShell 작업을 수행하는 방법을 [참조하세요.](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="bf3a1-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bf3a1-128">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bf3a1-128">Related topics</span></span>

[<span data-ttu-id="bf3a1-129">Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="bf3a1-129">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
