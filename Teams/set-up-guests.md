---
title: Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft 팀에서 게스트 액세스 기능을 켜거나 끕니다.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bcdbc3251820bdcee860323ad993efc8d6673c0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835648"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="bcf99-103">Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="bcf99-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="bcf99-104">기본적으로 게스트 액세스가 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-104">By default, guest access is turned off.</span></span> <span data-ttu-id="bcf99-105">Office 365 관리자는 관리자 또는 팀 소유자가 게스트를 추가할 수 있으려면 먼저 팀에 대 한 게스트 액세스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-105">As the Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="bcf99-106">게스트 액세스를 설정 하려면 [게스트 액세스 검사 목록을](guest-access-checklist.md)사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="bcf99-107">게스트 액세스를 설정한 후 변경 내용이 적용 되려면 2-24 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-107">After you turn on guest access, it takes 2-24 hours for the changes to take effect.</span></span> <span data-ttu-id="bcf99-108">사용자가 팀에 게스트를 추가 하려고 할 때 "관리자에 게 문의" 라는 메시지가 표시 되 면 게스트 액세스가 설정 되지 않았거나 설정이 아직 유효 하지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bcf99-109">게스트 액세스는 Azure Active Directory, Office 365, SharePoint Online, 팀의 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-109">Turning on guest access depends on settings in Azure Active Directory, Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="bcf99-110">자세한 내용은 [팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcf99-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="bcf99-111">팀 관리 센터에서 게스트 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="bcf99-111">Configure guest access in the Teams admin center</span></span>

1.  <span data-ttu-id="bcf99-112">Microsoft 팀 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="bcf99-113">**조직 전체 설정** > **게스트 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="bcf99-114">**Microsoft 팀에서 게스트 액세스 허용** 을 **On**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="bcf99-115">게스트 액세스 스위치를 On으로 설정 허용</span><span class="sxs-lookup"><span data-stu-id="bcf99-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="bcf99-116">**호출**, **모임**, **메시지**에서 게스트 사용자에 게 허용할 사항에 따라 각 접근 권한 값에 대해 **설정** 또는 **해제** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

    - <span data-ttu-id="bcf99-117">**개인 전화 걸기** – 게스트가 피어 투 피어 통화를 할 수 있도록 **이 설정을 켭니다** .</span><span class="sxs-lookup"><span data-stu-id="bcf99-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="bcf99-118">**IP 비디오 허용** -게스트에서 통화 및 모임에 비디오를 사용할 수 **있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="bcf99-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="bcf99-119">**화면 공유 모드** –이 설정은 게스트 사용자를 위한 화면 공유의 가용성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="bcf99-120">이 설정을 **사용 안 함으로** 설정 하 여 게스트가 팀에서 화면을 공유할 수 있는 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="bcf99-121">개별 응용 프로그램을 공유할 수 있도록이 설정을 **단일 응용 프로그램** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="bcf99-122">이 설정을 **전체 화면** 으로 전환 하 여 전체 화면 공유를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="bcf99-123">**모임 시작 허용** -게스트가 Microsoft 팀의 모임 시작 **기능을 사용할 수 있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="bcf99-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="bcf99-124">**보낸 메시지 편집** -게스트가 이전에 보낸 메시지를 편집할 수 **있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="bcf99-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="bcf99-125">**게스트는 전송 된 메시지를 삭제할 수 있습니다** – **이 설정을 사용 하 여 게스트가** 이전에 보낸 메시지를 삭제 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="bcf99-126">**채팅** -이 설정을 사용 하 여 게스트가 팀에서 **채팅을 사용할** 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="bcf99-127">**대화에서 Giphy 사용** -게스트가 대화에 **giphy을 사용할** 수 있도록이 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="bcf99-128">Giphy는 사용자가 애니메이션 GIF 파일을 검색 하 고 공유 하는 데 사용할 수 있는 온라인 데이터베이스 및 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="bcf99-129">각 Giphy에는 콘텐츠 등급이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="bcf99-130">**Giphy 콘텐츠 등급** – 드롭다운 목록에서 평점을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="bcf99-131">**모든 콘텐츠 허용** -게스트는 콘텐츠 등급에 관계 없이 모든 giphy을 채팅에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="bcf99-132">**보통** -게스트는 채팅에 giphy를 삽입할 수 있지만, 성인 콘텐츠는 중간에 국한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="bcf99-133">**Strict** – 게스트는 채팅에 giphy를 삽입할 수 있지만 성인용 메일을 삽입 하는 것이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="bcf99-134">**대화에서 밈 사용** -게스트가 **대화를 사용할** 수 있도록이 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="bcf99-135">**대화에서 스티커 사용** – 대화에서 게스트가 **스티커를 사용할 수 있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="bcf99-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="bcf99-136">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcf99-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="bcf99-137">PowerShell을 사용 하 여 게스트 액세스 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="bcf99-137">Use PowerShell to turn guest access on or off</span></span>
<span data-ttu-id="bcf99-138">[PowerShell을 참조 하 여 게스트 액세스 설정 또는 해제](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="bcf99-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="bcf99-139">비디오: 팀에서 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="bcf99-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="bcf99-140">Microsoft 팀에서 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="bcf99-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="bcf99-141">외부 액세스 (페더레이션) 및 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="bcf99-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]