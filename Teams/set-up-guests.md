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
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Office 365 관리자로서 Microsoft Teams에서 게스트 액세스 기능을 설정하거나 해제하는 방법을 알아보세요.
ms.openlocfilehash: c82172eb4d0c9fe50832d45ce2146c89d7e6d7d8
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884522"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="ddde5-103">Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="ddde5-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="ddde5-104">**2021년 2월까지** 게스트 액세스는 기본적으로 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="ddde5-105">Teams에 대한 게스트 액세스를 켜야만 관리자 또는 팀 소유자가 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="ddde5-106">게스트 액세스를 설정한 후 변경 내용이 적용될 수 있는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="ddde5-107">사용자가 게스트를  팀에 추가하려고 할 때 관리자에게 문의하는 메시지가 표시될 경우 게스트 액세스가 설정되지 않았거나 설정이 아직 유효하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> <span data-ttu-id="ddde5-108">**2021년 2월** 이후에는 이 설정을 구성하지 않은 기존 & 신규 고객에 대해 기본적으로 Microsoft Teams의 게스트 액세스가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="ddde5-109">이 변경이 구현되면 Microsoft Teams에서 게스트 액세스 기능을 아직 구성하지 않은 경우 해당 기능이 테넌트에서 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="ddde5-110">게스트 액세스가 조직에 대해 비활성화된 상태로 유지하려면 게스트 액세스 설정이 서비스  기본값 대신 Off로 설정되어 있는지 **확인해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddde5-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddde5-111">게스트 액세스를 설정하는 것은 Azure Active Directory, Microsoft 365, SharePoint 및 Teams의 설정에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="ddde5-112">자세한 내용은 [팀에서 게스트와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddde5-112">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="ddde5-113">Teams 관리 센터에서 게스트 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="ddde5-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="ddde5-114">[Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="ddde5-115">**조직 전체 설정** > **게스트 액세스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="ddde5-116">**Microsoft Teams에서 게스트 액세스 허용** 을 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="ddde5-117">게스트 액세스 허용 스위치를 켜기로 설정하기</span><span class="sxs-lookup"><span data-stu-id="ddde5-117">Allow guest access switch set to On</span></span> ](media/guest-access-setting.png)

4. <span data-ttu-id="ddde5-118">**통화**, **모임**, **메시징** 에서 게스트 사용자에게 허용할 항목에 따라 각 기능에 대한 **켬** 또는 **끔** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="ddde5-119">**개인 전화 걸기** – 게스트가 피어 투 피어 전화를 걸 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="ddde5-120">**IP 비디오 허용** - 게스트가 통화 및 모임에서 비디오를 사용하도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="ddde5-121">**화면 공유 모드** – 이 설정은 게스트 사용자에 대한 화면 공유 가용성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="ddde5-122">게스트가 Teams에서 화면을 공유할 수 있는 기능을 제거하려면 이 설정을 **사용 안 함** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="ddde5-123">개별 응용 프로그램을 공유하도록 허용하려면 이 설정을 **단일 응용 프로그램** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="ddde5-124">전체 화면 공유를 허용하려면 이 설정을 **전체 화면** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="ddde5-125">**모임 시작 허용** – 게스트가 Microsoft Teams에서 모임 시작 기능을 사용하도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="ddde5-126">**보낸 메시지 편집** - 게스트가 이전에 보낸 메시지를 편집할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="ddde5-127">**게스트가 보낸 메시지를 삭제할 수 있음** – 게스트가 이전에 보낸 메시지를 삭제할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="ddde5-128">**채팅** – 게스트가 Teams에서 채팅을 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="ddde5-129">**대화에서 Giphys 사용** - 게스트가 대화에서 Giphys를 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="ddde5-130">Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="ddde5-131">각 Giphy에는 콘텐츠 등급이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="ddde5-132">**Giphy 콘텐츠 등급** – 드롭다운 목록에서 등급을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="ddde5-133">**모든 콘텐츠 허용** - 게스트는 콘텐츠 등급과 상관없이 모든 Giphy를 채팅에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="ddde5-134">**보통** - 게스트는 채팅에 Giphy를 삽입할 수 있지만 성인용 콘텐츠는 보통으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="ddde5-135">**엄격** – 게스트는 채팅에 Giphys를 삽입할 수 있지만 성인 콘텐츠 삽입은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="ddde5-136">**대화에서 밈 사용** - 게스트가 대화에서 밈을 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="ddde5-137">**대화에서 스티커 사용** – 게스트가 대화에서 스티커를 사용할 수 있도록 허용하려면 이를 **켬** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddde5-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Teams의 게스트 사용 권한 설정](media/manage-guest-access-image1.png)

5. <span data-ttu-id="ddde5-139">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddde5-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="ddde5-140">외부 액세스(페더레이션) 대 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="ddde5-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="ddde5-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ddde5-141">See also</span></span>

[<span data-ttu-id="ddde5-142">Microsoft 365를 사용하여 안전한 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="ddde5-142">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="ddde5-143">특정 팀에서 게스트 사용자 차단</span><span class="sxs-lookup"><span data-stu-id="ddde5-143">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="ddde5-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="ddde5-144">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
