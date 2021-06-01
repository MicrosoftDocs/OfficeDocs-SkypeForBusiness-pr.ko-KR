---
title: 특정 온라인 사용자에 대한 무료 전화 비즈니스용 Skype 사용 안 하세요.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: 관리자는 이끌이가 모임에 무료 번호를 사용할 수 있는 방법을 제어할 수 있습니다.
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238513"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a><span data-ttu-id="4ad88-103">특정 온라인 사용자에 대한 무료 전화 비즈니스용 Skype 사용 안 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ad88-103">Disabling toll-free numbers for specific Skype for Business Online users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> <span data-ttu-id="4ad88-104">사용자에 대한 도구 사용 안 하도록 Teams 대한 자세한 내용은 특정 사용자에 대한 무료 Teams [참조하세요.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)</span><span class="sxs-lookup"><span data-stu-id="4ad88-104">For information about disabling tool-free numbers for Teams users, see  [Disabling toll-free numbers for specific Teams users](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).</span></span>

<span data-ttu-id="4ad88-105">조직에서 Microsoft Audio Conferencing Bridge에 무료 번호가 있는 경우 특정 이끌이의 모임에서 해당 번호를 허용하거나 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-105">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="4ad88-106">기본적으로 조직의 모든 사용자는 무료 번호를 사용할 수 있습니다. 즉, 해당 숫자를 사용할 수 있는 경우 참가자가 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-106">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="4ad88-107">조직의 일부 사용자에게 원하는 동작이 아닌 경우 무료 번호 사용 제어를 통해 특정 사용자가 모임에서 해당 번호를 사용하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-107">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="4ad88-108">주어진 이끌이에 대해 무료 번호가 비활성화된 경우:</span><span class="sxs-lookup"><span data-stu-id="4ad88-108">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="4ad88-109">무료 전화 번호는 더 이상 모임 초대에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-109">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4ad88-110">무료 전화 번호는 모임 초대에 참조되는 "로컬 번호 찾기" 페이지에 더 이상 나열되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-110">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="4ad88-111">참가자는 조직의 무료 전화 번호로 전화를 걸면 해당 이끌이의 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-111">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="4ad88-112">이끌이의 모든 모임이 자동으로 다시 조정되고 무료 전화 번호가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-112">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="4ad88-113">이렇게 하면 이끌이의 모든 전자 메일 초대가 해당 모임의 모든 참가자에게 다시 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-113">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="4ad88-114">참가자는 전화 번호를 사용하여 이끌이의 모임에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-114">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="4ad88-115">특정 사용자의 무료 전화 번호 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="4ad88-115">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="4ad88-116">관리 **Microsoft Teams 센터에서**:</span><span class="sxs-lookup"><span data-stu-id="4ad88-116">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="4ad88-117">왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-117">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="4ad88-118">오디오 **회의** 옆에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ad88-118">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="4ad88-119">이 사용자의 모임 요청에 무료 전화 번호 포함 을 **Off로** **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ad88-119">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="4ad88-120">저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ad88-120">Click **Save.**</span></span> 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="4ad88-121">**PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="4ad88-121">**Using PowerShell**</span></span>  

<span data-ttu-id="4ad88-122">이 컨트롤을 사용하도록 설정하거나 사용하지 않도록 설정하려면 Set-CsOnlineDialInConferencingUser cmdlet의 AllowTollFreeDialIn 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-122">You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control.</span></span> <span data-ttu-id="4ad88-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad88-123">For example:</span></span> 

- <span data-ttu-id="4ad88-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span><span class="sxs-lookup"><span data-stu-id="4ad88-124">Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false</span></span>
