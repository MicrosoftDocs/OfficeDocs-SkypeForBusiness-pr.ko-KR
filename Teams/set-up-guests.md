---
title: Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Office 365 관리자로 Microsoft 팀에서 게스트 액세스 기능을 설정 하거나 해제 하는 방법에 대해 알아봅니다.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43c225cad121d88d14bb6f179f48b452a61d89d7
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333248"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="06361-103">Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="06361-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="06361-104">기본적으로 게스트 액세스 기능은 꺼져있습니다.</span><span class="sxs-lookup"><span data-stu-id="06361-104">By default, guest access is turned off.</span></span> <span data-ttu-id="06361-105">Microsoft 365 또는 Office 365 관리자는 관리자 또는 팀 소유자가 게스트를 추가할 수 있으려면 먼저 팀에 대 한 게스트 액세스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-105">As the Microsoft 365 or Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span>

<span data-ttu-id="06361-106">게스트 액세스를 설정한 후 변경 내용이 적용 되는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06361-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="06361-107">사용자가 팀에 게스트를 추가하려고 할 때 "관리자에게 문의하세요."라는 메시지가 표시되면 게스트 액세스가 켜지지 않았거나 설정이 아직 적용되지 않았을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="06361-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06361-108">게스트 액세스를 설정 하는 것은 Azure Active Directory, Microsoft 365, SharePoint, 팀의 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="06361-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="06361-109">자세한 내용은 [팀에서 게스트 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06361-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="06361-110">Teams 관리 센터에서 게스트 액세스 구성하기</span><span class="sxs-lookup"><span data-stu-id="06361-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="06361-111">Microsoft Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-111">Sign in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="06361-112">**조직 전체 설정** > **게스트 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="06361-113">**Microsoft Teams에서 게스트 액세스 허용**을 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="06361-114">게스트 액세스 허용 스위치를 켜기로 설정하기</span><span class="sxs-lookup"><span data-stu-id="06361-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="06361-115">**통화**, **모임**, **메시징**에서 게스트 사용자에게 허용할 항목에 따라 각 기능에 대한 **켬** 또는 **끔**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="06361-116">**개인 전화 걸기** – 게스트가 피어 투 피어 전화를 걸 수 있도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="06361-117">**IP 비디오 허용** - 게스트가 통화 및 모임에서 비디오를 사용하도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="06361-118">**화면 공유 모드** – 이 설정은 게스트 사용자에 대한 화면 공유 가용성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="06361-119">게스트가 Teams에서 화면을 공유할 수 있는 기능을 제거하려면 이 설정을 **사용 안 함**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="06361-120">개별 응용 프로그램을 공유하도록 허용하려면 이 설정을 **단일 응용 프로그램**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="06361-121">전체 화면 공유를 허용하려면 이 설정을 **전체 화면**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="06361-122">**모임 시작 허용** – 게스트가 Microsoft Teams에서 모임 시작 기능을 사용하도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="06361-123">**보낸 메시지 편집** - 게스트가 이전에 보낸 메시지를 편집할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="06361-124">**게스트가 보낸 메시지를 삭제할 수 있음** – 게스트가 이전에 보낸 메시지를 삭제할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="06361-125">**채팅** – 게스트가 Teams에서 채팅을 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="06361-126">**대화에서 Giphys 사용** - 게스트가 대화에서 Giphys를 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="06361-127">Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="06361-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="06361-128">각 Giphy에는 콘텐츠 등급이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="06361-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="06361-129">**Giphy 콘텐츠 등급** – 드롭다운 목록에서 등급을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="06361-130">**모든 콘텐츠 허용** - 게스트는 콘텐츠 등급과 상관없이 모든 Giphy를 채팅에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06361-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="06361-131">**보통** - 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠는 보통으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="06361-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="06361-132">**엄격** - 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠 삽입은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="06361-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="06361-133">**대화에서 밈 사용** - 게스트가 대화에서 밈을 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="06361-134">**대화에서 스티커 사용** – 게스트가 대화에서 스티커를 사용할 수 있도록 허용하려면 이를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

5. <span data-ttu-id="06361-135">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="06361-135">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="06361-136">외부 액세스 (페더레이션) 및 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="06361-136">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="06361-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06361-137">See also</span></span>

[<span data-ttu-id="06361-138">특정 팀의 게스트 사용자 차단</span><span class="sxs-lookup"><span data-stu-id="06361-138">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="06361-139">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="06361-139">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)