---
title: 웨비나에 대해 Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 모임에 대한 Webinar 정책을 관리하는 Teams 대해 자세히 알아보습니다.
ms.openlocfilehash: aafa7b57eea1228fa5565bb4d5e95304b42751a3
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718049"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a><span data-ttu-id="18717-103">웨비나에 대해 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18717-103">Set up for webinars in Microsoft Teams</span></span>

<span data-ttu-id="18717-104">이 문서에서는 웨비나를 호스트할 조직을 설정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18717-104">This article will help you set up your organization to host webinars.</span></span>

## <a name="what-are-webinars"></a><span data-ttu-id="18717-105">웨비나란?</span><span class="sxs-lookup"><span data-stu-id="18717-105">What are webinars?</span></span>

<span data-ttu-id="18717-106">웨비나는 강사와 참가자가 명확한 역할을 가지는 구조화된 모임으로, 교육 목적 또는 영업 및 마케팅 리드 생성 시나리오에 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18717-106">Webinars are structured meetings where instructors and participants have clear roles, often used for training purposes or sales and marketing lead generation scenarios.</span></span>

<span data-ttu-id="18717-107">조직에서 웨비나를 설정한 후 사용자는 웨비나를 예약하고 참석자에 대한 등록을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18717-107">After setting up webinars in your organization, your users can schedule webinars and open registration to attendees.</span></span> <span data-ttu-id="18717-108">많은 토론과 작업 할당이 포함된 기존 모임과 달리 웨비나는 대화형 프레젠테이션을 위한 것이고 참석자 분석 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-108">Unlike traditional meetings that include many discussions and task assignment, webinars are meant for interactive presentations and provide tools for attendee analysis.</span></span>

## <a name="allow-users-to-schedule-webinars-using-powershell"></a><span data-ttu-id="18717-109">PowerShell을 사용하여 사용자가 웨비나 예약 허용</span><span class="sxs-lookup"><span data-stu-id="18717-109">Allow users to schedule webinars using PowerShell</span></span>

<span data-ttu-id="18717-110">Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet에서 다음 특성을 사용하여 Teams.</span><span class="sxs-lookup"><span data-stu-id="18717-110">You can use the following attributes within the Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet to set up for webinars in Teams.</span></span>

- <span data-ttu-id="18717-111">AllowMeetingRegistration</span><span class="sxs-lookup"><span data-stu-id="18717-111">AllowMeetingRegistration</span></span>
- <span data-ttu-id="18717-112">WhoCanRegister</span><span class="sxs-lookup"><span data-stu-id="18717-112">WhoCanRegister</span></span>
- <span data-ttu-id="18717-113">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="18717-113">AllowPrivateMeetingScheduling</span></span>

<span data-ttu-id="18717-114">cmdlet에 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy를](/powershell/module/skype/set-csteamsmeetingpolicy) 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="18717-114">Read [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) for more information on the cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="18717-115">이러한 cmdlet을 실행하려면 먼저 온라인 PowerShell에 비즈니스용 Skype 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-115">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="18717-116">자세한 내용은 [PowerShell에서](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)비즈니스용 Skype 온라인 Microsoft 365 Office 365 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18717-116">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

### <a name="allow-users-to-schedule-webinars"></a><span data-ttu-id="18717-117">사용자가 웨비나 예약 허용</span><span class="sxs-lookup"><span data-stu-id="18717-117">Allow users to schedule webinars</span></span>

<span data-ttu-id="18717-118">조직의 사용자가 웨비나를 예약할 수 있도록 허용하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-118">To allow users in your organization to schedule webinars, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```
### <a name="configure-who-can-register-for-webinars"></a><span data-ttu-id="18717-119">웨비나에 등록할 수 있는 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="18717-119">Configure who can register for webinars</span></span>

<span data-ttu-id="18717-120">조직의 사용자로만 등록을 제한하거나 테넌트 내부 및 외부의 모든 사용자에게 등록을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18717-120">You can restrict registration to users only in your organization or open it up to everyone both inside and outside your tenant.</span></span> <span data-ttu-id="18717-121">기본적으로 **WhoCanRegister를** 사용하도록 설정하고 모든 으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="18717-121">By default, **WhoCanRegister** is enabled and set to **Everyone**.</span></span> <span data-ttu-id="18717-122">모임 등록을 해제하려는 경우 **AllowMeetingRegistration을 False로** **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="18717-122">If you want to turn off meeting registration, set **AllowMeetingRegistration** to **False**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18717-123">**AllowPrivateMeetingScheduling은** **AllowMeetingRegistration이** 작동하려면 True로 설정해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="18717-123">Keep in mind that **AllowPrivateMeetingScheduling** must be set to **True** for **AllowMeetingRegistration** to work.</span></span> <span data-ttu-id="18717-124">또한 Microsoft Lists는 Microsoft 목록에서 설정해야 SharePoint.</span><span class="sxs-lookup"><span data-stu-id="18717-124">Additionally, Microsoft Lists needs to be set up in SharePoint.</span></span> <span data-ttu-id="18717-125">자세한 내용은 [Microsoft Lists에 대한 제어 설정을 참조하세요.](/sharepoint/control-lists)</span><span class="sxs-lookup"><span data-stu-id="18717-125">To learn more, see [Control settings for Microsoft Lists](/sharepoint/control-lists).</span></span>

<span data-ttu-id="18717-126">**조직의 *사용자만* 웨비나에 등록할 수 있도록 허용하기 위해 다음을 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="18717-126">**To allow *only* users in your organization to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="18717-127">그런 다음, 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-127">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

<span data-ttu-id="18717-128">**익명 사용자를 비롯한 모든 사용자가 웨비나에 등록할 수 있도록 허용하기 위해 다음을 실행합니다.**</span><span class="sxs-lookup"><span data-stu-id="18717-128">**To allow anyone, including anonymous users, to register for webinars, run:**</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

<span data-ttu-id="18717-129">그런 다음, 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-129">Then, run:</span></span>

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!IMPORTANT]
> <span data-ttu-id="18717-130">모임 설정에서 익명 조인이 해제된 경우 익명 사용자는 웨비나에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18717-130">If anonymous join is turned off in meeting settings, anonymous users can't join webinars.</span></span> <span data-ttu-id="18717-131">자세한 내용을 알아보고 이 설정을 사용하도록 설정하려면 에서 모임 [설정을 Teams.](meeting-settings-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="18717-131">To learn more and enable this setting, see [Meeting settings in Teams](meeting-settings-in-teams.md).</span></span>

### <a name="collect-meeting-attendance"></a><span data-ttu-id="18717-132">모임 참석자 수집</span><span class="sxs-lookup"><span data-stu-id="18717-132">Collect meeting attendance</span></span>

<span data-ttu-id="18717-133">주최자가 등록하고 참석한 웨비나를 분석하려면 **AllowEngagementReport** 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-133">If you want organizers to analyze who registered and attended webinars, you'll need to turn on the **AllowEngagementReport** policy.</span></span> <span data-ttu-id="18717-134">이렇게 하여 PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-134">To do this, run the following command in PowerShell.</span></span>

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a><span data-ttu-id="18717-135">웨비나 설정 구성</span><span class="sxs-lookup"><span data-stu-id="18717-135">Configure webinar settings</span></span>

<span data-ttu-id="18717-136">웨비나에 대한 환경을 사용하도록 설정한 후 추가 관리자 관리가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18717-136">After enabling your environment for webinars, no further admin management is required.</span></span> <span data-ttu-id="18717-137">정책은 웨비나 이끌이에 대해 표시하는 옵션을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="18717-137">The policy controls which options show up for webinar organizers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="18717-138">관련 항목</span><span class="sxs-lookup"><span data-stu-id="18717-138">Related topics</span></span>

- [<span data-ttu-id="18717-139">Teams 모임 정책 - 일반</span><span class="sxs-lookup"><span data-stu-id="18717-139">Meeting policies in Teams - General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="18717-140">Set-CsTeamsMeetingPolicy 설명서</span><span class="sxs-lookup"><span data-stu-id="18717-140">Set-CsTeamsMeetingPolicy documentation</span></span>](/powershell/module/skype/set-csteamsmeetingpolicy)
