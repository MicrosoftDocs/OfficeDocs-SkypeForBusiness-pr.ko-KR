---
title: 특정 사용자에 대한 무료 전화 Teams 사용 안 하도록 지정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 주최자가 오디오 회의 브리지 모임에 무료 번호를 사용할 수 있는 방법을 제어하는 방법에 대해 알아보습니다.
ms.openlocfilehash: f9ab09396778b221ad7f5c016dbf7db76fcba030
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096348"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="dd590-103">특정 사용자에 대한 무료 전화 Teams 사용 안 하도록 지정</span><span class="sxs-lookup"><span data-stu-id="dd590-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="dd590-104">조직에서 Microsoft Audio Conferencing Bridge에 무료 번호가 있는 경우 특정 이끌이의 모임에서 해당 번호를 허용하거나 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="dd590-105">기본적으로 조직의 모든 사용자는 무료 번호를 사용할 수 있습니다. 즉, 해당 숫자를 사용할 수 있는 경우 참가자가 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="dd590-106">조직의 일부 사용자에게 원하는 동작이 아닌 경우 무료 번호 사용 제어를 통해 특정 사용자가 모임에서 해당 번호를 사용하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="dd590-107">주어진 이끌이에 대해 무료 번호가 비활성화된 경우:</span><span class="sxs-lookup"><span data-stu-id="dd590-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="dd590-108">무료 전화 번호는 더 이상 모임 초대에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="dd590-109">무료 전화 번호는 모임 초대에 참조되는 "로컬 번호 찾기" 페이지에 더 이상 나열되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="dd590-110">참가자는 조직의 무료 전화 번호로 전화를 걸면 해당 이끌이의 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="dd590-111">이끌이의 모든 모임이 자동으로 다시 조정되고 무료 전화 번호가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="dd590-112">이렇게 하면 이끌이의 모든 전자 메일 초대가 해당 모임의 모든 참가자에게 다시 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="dd590-113">참가자는 전화 번호를 사용하여 이끌이의 모임에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="dd590-114">특정 사용자의 무료 전화 번호 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="dd590-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="dd590-115">관리 **Microsoft Teams 센터에서**:</span><span class="sxs-lookup"><span data-stu-id="dd590-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="dd590-116">왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd590-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="dd590-117">오디오 **회의** 옆에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd590-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="dd590-118">이 사용자의 모임 요청에 무료 전화 번호 포함 을 **Off로** **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd590-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="dd590-119">저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dd590-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="dd590-120">**PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="dd590-120">**Using PowerShell**</span></span>  

<span data-ttu-id="dd590-121">자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd590-121">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>