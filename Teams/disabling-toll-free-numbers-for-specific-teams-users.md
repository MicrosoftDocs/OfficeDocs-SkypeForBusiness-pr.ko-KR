---
title: 특정 팀 사용자를 위해 무료 번호를 사용 하지 않도록 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 관리자는 이끌이가 무료 전화 번호를 모임에 사용 하는 방법을 제어할 수 있습니다.
ms.openlocfilehash: 423aab1c942850c94385f4df15a07d3218dbe2da
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182345"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a><span data-ttu-id="6319d-103">특정 팀 사용자를 위해 무료 번호를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6319d-103">Disabling toll-free numbers for specific Teams users</span></span>

<span data-ttu-id="6319d-104">조직의 Microsoft 오디오 회의 브리지에 무료 번호가 있는 경우 특정 이끌이의 모임에서 사용을 허용 하거나 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-104">If your organization has toll-free numbers in its Microsoft Audio Conferencing Bridge, you can allow or prevent their usage in the meetings of specific organizers.</span></span>  

<span data-ttu-id="6319d-105">기본적으로 조직의 모든 사용자는 무료 번호를 사용할 수 있으며, 해당 번호 (사용 가능한 경우)를 참가자가 모임에 참가 하는 데 사용 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-105">By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings.</span></span> <span data-ttu-id="6319d-106">조직의 일부 사용자가이 동작을 원하지 않는 경우에는 무료 번호 사용 제어를 통해 특정 사용자가 모임에서 해당 번호를 사용 하지 못하도록 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-106">If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control.</span></span> 

<span data-ttu-id="6319d-107">특정 이끌이의 무료 전화 번호를 사용 하지 않는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-107">When toll-free numbers are disabled for a given organizer:</span></span> 
 - <span data-ttu-id="6319d-108">무료 번호는 귀하의 모임 초대에 더 이상 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-108">A toll-free number will no longer be included in his or her meeting invites.</span></span> 
 - <span data-ttu-id="6319d-109">무료 번호는 귀하의 모임 초대에서 참조 되는 "지역 번호 찾기" 페이지에 더 이상 나열 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-109">Toll-free numbers will no longer be listed on the "Find a local number" page that is referenced in his or her meeting invites.</span></span> 
 - <span data-ttu-id="6319d-110">무료 조직의 번호로 전화를 걸어야 하는 경우 참가자가 지정 된 이끌이의 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-110">Participants won't be able to join the meeting of the given organizer if they dial any toll-free number of the organization.</span></span> 
 - <span data-ttu-id="6319d-111">이끌이의 모든 모임이 자동으로 재조정 되 고 무료 번호가 해당 번호에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-111">All meetings of the organizer will be automatically rescheduled, and the toll-free number will be removed from them.</span></span>  

    > [!IMPORTANT]
    > <span data-ttu-id="6319d-112">이렇게 하면 해당 모임의 모든 참가자에 게 이끌이의 전자 메일 초대가 모두 다시 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-112">This will resend all of the email invites of the organizer to all the participants of those meetings.</span></span> 

 - <span data-ttu-id="6319d-113">참가자는 유료 전화 번호를 사용 하 여 이끌이 모임에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-113">Participants can continue joining meetings of the organizer using toll numbers.</span></span> 

## <a name="disabling-toll-free-numbers-for-specific-users"></a><span data-ttu-id="6319d-114">특정 사용자에 대해 무료 번호 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6319d-114">Disabling toll-free numbers for specific users</span></span> 

<span data-ttu-id="6319d-115">**Microsoft 팀 관리 센터**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-115">From the **Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="6319d-116">왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-116">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="6319d-117">**오디오 회의**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-117">Next to **Audio Conferencing**, click **Edit**.</span></span>

3. <span data-ttu-id="6319d-118">**이 사용자의 모임 요청에 무료 전화 번호 포함** 을 **Off**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6319d-118">Set **Include toll-free numbers in meeting requests from this user** to **Off**.</span></span> 

4. <span data-ttu-id="6319d-119">**저장을 클릭 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6319d-119">Click **Save.**</span></span> 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
<span data-ttu-id="6319d-120">**PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="6319d-120">**Using PowerShell**</span></span>  

<span data-ttu-id="6319d-121">자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6319d-121">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
