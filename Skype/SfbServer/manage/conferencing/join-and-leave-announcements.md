---
title: 비즈니스용 Skype 서버에서 컨퍼런스 참가 및 공지 사항 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '요약: 비즈니스용 Skype 서버에서 컨퍼런스 참가 및 알림을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 3d9a14e36dfe6b8df51e5ee91dd329ce34452cda
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189663"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="58096-103">비즈니스용 Skype 서버에서 컨퍼런스 참가 및 공지 사항 관리</span><span class="sxs-lookup"><span data-stu-id="58096-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="58096-104">**요약:** 비즈니스용 Skype 서버에서 컨퍼런스 참가를 관리 하 고 알림을 남기기 위한 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="58096-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="58096-105">전화 접속 사용자가 회의에 참가 하거나 나갈 때, 회의 알림 응용 프로그램은 소리를 재생 하거나 자신의 이름을 말하기 때문에 해당 입구 또는 종료를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58096-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="58096-106">비즈니스용 Skype Server Management Shell 및 다음 매개 변수를 사용 하 여 **CsDialinConferencing** cmdlet을 사용 하 여 알림이 작동 하는 방식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58096-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="58096-107">EnableNameRecording-회의를 시작 하기 전에 익명 참가자가 자신의 이름을 기록 하도록 요청 했는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="58096-108">기본값은 "$true" 이며,이는 익명 참가자가 회의에 참가할 때 이름을 명시 하 라는 메시지를 표시 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="58096-109">(인증 된 참가자는 해당 사용자의 표시 이름이 대신 사용 되므로 이름을 기록 하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="58096-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="58096-110">EntryExitAnnouncementsEnabledByDefault-알림을 기본적으로 설정 또는 해제 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58096-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="58096-111">기본값은 "$false" 이며,이는 기본적으로 참가자가 회의에 참가 하거나 나갈 때 공지 사항이 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="58096-112">모임 이끌이는 모임을 예약할 때이 설정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58096-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="58096-113">EntryExitAnnouncementsType-참가자가 알림을 사용할 수 있도록 전화 회의에 참가 하거나 떠날 때마다 수행 되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58096-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="58096-114">기본값은 "UseNames" 이며, 공지 사항이 설정 된 경우 ": 진구 Myer 님이 회의에 참가 했습니다" 라는 알림을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="58096-115">전역 범위 또는 사이트 범위에서 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58096-115">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="58096-116">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-116">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="58096-117">회의 참가를 수정 하 고 알림 동작을 종료 하려면</span><span class="sxs-lookup"><span data-stu-id="58096-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="58096-118">RTCUniversalServerAdmins 그룹의 구성원 또는 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="58096-119">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="58096-120">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-120">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="58096-121">이 cmdlet은 참가자가 전화 접속 회의에 참가 하거나 나갈 때 비즈니스용 Skype 서버가 응답 하는 방법 및 회의 참가 시 사용자의 이름을 기록 하는 데 필요한 지 여부에 대 한 정보를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="58096-122">명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-122">Run the following at the command prompt:</span></span>
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="58096-123">다음 예제에서는 사이트 범위에서 Redmond에 대 한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58096-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="58096-124">알림은 설정 되어 있지만 참가자가 회의에 참가할 때 이름을 말할 것인지 묻는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58096-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="58096-125">참가자가 회의를 시작 하거나 종료할 때 신호음이 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58096-125">A tone is played when participants enter or leave a conference:</span></span>
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="58096-126">구문 및 전체 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58096-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

