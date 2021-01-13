---
title: 비즈니스용 Skype 서버에서 전화 회의 참가 및 나가기 공지 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '요약: 비즈니스용 Skype 서버에서 회의 참가 및 나가기 공지 사항을 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828108"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="89c6e-103">비즈니스용 Skype 서버에서 전화 회의 참가 및 나가기 공지 관리</span><span class="sxs-lookup"><span data-stu-id="89c6e-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="89c6e-104">**요약:** 비즈니스용 Skype 서버에서 전화 회의 참가 및 나가기 공지 사항을 관리하는 방법에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="89c6e-105">전화 접속 사용자가 전화 회의에 참가하거나 회의에서 나간 경우 회의 공지 응용 프로그램은 톤을 재생하거나 이름을 말하여 입장 또는 퇴장에 대해 공지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="89c6e-106">다음 매개 변수와 함께 비즈니스용 Skype 서버 관리 셸 및 **Set-CsDialinConferencing** cmdlet을 사용하여 공지 사항의 작동 방법을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="89c6e-107">EnableNameRecording - 회의에 입장하기 전에 익명 참가자에게 이름을 기록하도록 요구할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="89c6e-108">기본값은 "$true"입니다. 즉, 회의에 참가할 때 익명 참가자에게 이름을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="89c6e-109">인증된 참가자는 표시 이름이 대신 사용되지 때문에 이름을 기록하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="89c6e-110">EntryExitAnnouncementsEnabledByDefault - 기본적으로 공지 사항을 켜거나 끄는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="89c6e-111">기본값은 "$false"입니다. 즉, 참가자가 회의에 참가하거나 회의에서 나간 경우 기본적으로 공지가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="89c6e-112">모임 이끌이는 모임을 계획할 때 이 설정을 오버라이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="89c6e-113">EntryExitAnnouncementsType - 참가자가 발표가 사용하도록 설정된 회의에 참가하거나 회의에서 나설 때마다 수행되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="89c6e-114">기본값은 "UseNames"입니다. 즉, 공지가 켜져 있는 경우 "Ken Myer가 회의에 참가했습니다."라는 공지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="89c6e-p105">이러한 설정은 전역 범위나 사이트 범위에서 구성할 수 있습니다. 사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="89c6e-117">회의 입장 및 퇴장 알림 동작을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="89c6e-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="89c6e-118">RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="89c6e-119">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="89c6e-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="89c6e-120">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="89c6e-121">이 cmdlet은 참가자가 전화 회의에 참가할 때 이름을 기록해야 하는지 여부 및 참가자가 전화 접속 회의에 참가하거나 퇴장할 때 비즈니스용 Skype 서버가 응답하는 방식에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="89c6e-122">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="89c6e-123">다음 예제에서는 Redmond의 사이트 범위에서 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="89c6e-124">알림이 설정되었지만 참가자가 회의에 참가할 때 이름을 얘기하라는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="89c6e-125">참가자가 회의에 입장 또는 퇴장할 때 신호음이 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="89c6e-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="89c6e-126">구문과 전체 매개 변수 목록을 비롯한 자세한 내용은 [Set-CsDialInConferencingConfiguration을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="89c6e-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

