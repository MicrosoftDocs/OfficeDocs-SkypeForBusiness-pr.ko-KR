---
title: Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Microsoft 팀에서 게스트 액세스 기능을 켜거나 끕니다.
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 186c83b82c396a21fe0098a561bcd4db13370140
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571576"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="0fc8b-103">Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="0fc8b-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="0fc8b-104">Office 365 관리자는 사용자 또는 조직의 사용자 (특히 팀 소유자)가 게스트를 추가할 수 있으려면 먼저 게스트 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="0fc8b-105">게스트 설정은 Azure Active Directory에서 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="0fc8b-106">변경 내용이 Office 365 조직에서 유효 하 게 유지 되려면 2 시간에서 24 시간 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="0fc8b-107">사용자가 팀에 게스트를 추가 하려고 할 때 "관리자에 게 문의" 라는 메시지가 표시 되 면 게스트 기능을 사용 하도록 설정 하지 않았거나 설정이 아직 유효 하지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fc8b-108">게스트 액세스 기능을 완벽 하 게 사용할 수 있도록 설정 하려면 Microsoft 팀, Azure Active Directory 및 Office 365 간의 핵심 인증 종속성을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="0fc8b-109">자세한 내용은 [Microsoft 팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="0fc8b-110">게스트 액세스와 외부 액세스 (페더레이션) 비교</span><span class="sxs-lookup"><span data-stu-id="0fc8b-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="0fc8b-111">Microsoft 팀 관리 센터에서 게스트 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="0fc8b-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="0fc8b-112">Microsoft 팀 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="0fc8b-113">**조직 전체 설정** > **게스트 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="0fc8b-114">**Microsoft 팀에서 게스트 액세스 허용** 전환 스위치를 켜기로 설정 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="0fc8b-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="0fc8b-115">게스트 액세스 스위치를 On으로 설정 허용</span><span class="sxs-lookup"><span data-stu-id="0fc8b-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="0fc8b-116">게스트 사용자에 게 허용할 기능에 따라 **통화**, **모임**, **메시지** **를 설정 하거나** **해제**합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="0fc8b-117">**개인 전화 걸기** – 게스트가 피어 투 피어 통화를 할 수 있도록 **이 설정을 켭니다** .</span><span class="sxs-lookup"><span data-stu-id="0fc8b-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="0fc8b-118">**IP 비디오 허용** -게스트에서 통화 및 모임에 비디오를 사용할 수 **있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="0fc8b-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="0fc8b-119">**화면 공유 모드** –이 설정은 게스트 사용자를 위한 화면 공유의 가용성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="0fc8b-120">이 설정을 **사용 안 함으로** 설정 하 여 게스트가 팀에서 화면을 공유할 수 있는 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="0fc8b-121">개별 응용 프로그램을 공유할 수 있도록이 설정을 **단일 응용 프로그램** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="0fc8b-122">이 설정을 **전체 화면** 으로 전환 하 여 전체 화면 공유를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="0fc8b-123">**모임 시작 허용** -게스트가 Microsoft 팀의 모임 시작 **기능을 사용할 수 있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="0fc8b-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="0fc8b-124">**보낸 메시지 편집** -게스트가 이전에 보낸 메시지를 편집할 수 **있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="0fc8b-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="0fc8b-125">**게스트는 전송 된 메시지를 삭제할 수 있습니다** – **이 설정을 사용 하 여 게스트가** 이전에 보낸 메시지를 삭제 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="0fc8b-126">**채팅** -이 설정을 사용 하 여 게스트가 팀에서 **채팅을 사용할** 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="0fc8b-127">**대화에서 Giphy 사용** -게스트가 대화에 **giphy을 사용할** 수 있도록이 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="0fc8b-128">Giphy는 사용자가 애니메이션 GIF 파일을 검색 하 고 공유 하는 데 사용할 수 있는 온라인 데이터베이스 및 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="0fc8b-129">각 Giphy에는 콘텐츠 등급이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="0fc8b-130">**Giphy 콘텐츠 등급** – 드롭다운 목록에서 평점을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="0fc8b-131">**모든 콘텐츠 허용** -게스트는 콘텐츠 등급에 관계 없이 모든 giphy을 채팅에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="0fc8b-132">**보통** -게스트는 채팅에 giphy를 삽입할 수 있지만, 성인 콘텐츠는 중간에 국한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="0fc8b-133">**Strict** – 게스트는 채팅에 giphy를 삽입할 수 있지만 성인용 메일을 삽입 하는 것이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="0fc8b-134">**대화에서 밈 사용** -게스트가 **대화를 사용할** 수 있도록이 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="0fc8b-135">**대화에서 스티커 사용** – 대화에서 게스트가 **스티커를 사용할 수 있도록 설정 합니다** .</span><span class="sxs-lookup"><span data-stu-id="0fc8b-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="0fc8b-136">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="0fc8b-137">PowerShell을 사용 하 여 게스트 액세스 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="0fc8b-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="0fc8b-138">에서 비즈니스용 Skype Online PowerShell 모듈 다운로드https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="0fc8b-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="0fc8b-139">비즈니스용 Skype Online 끝점에 PowerShell 세션을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="0fc8b-140">구성을 확인 하 고, `AllowGuestUser` 설정 `$False`된 경우 [CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet을 사용 하 여 설정 `$True`합니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="0fc8b-141">이제 조직의 팀에서 게스트 사용자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="0fc8b-142">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0fc8b-142">More information</span></span>

<span data-ttu-id="0fc8b-143">게스트 액세스에 대 한 자세한 내용은 다음 비디오를 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fc8b-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="0fc8b-144">Microsoft 팀에서 게스트 추가</span><span class="sxs-lookup"><span data-stu-id="0fc8b-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
