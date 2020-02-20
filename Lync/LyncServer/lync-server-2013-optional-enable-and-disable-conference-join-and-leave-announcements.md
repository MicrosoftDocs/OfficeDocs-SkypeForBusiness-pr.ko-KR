---
title: 반드시 전화 회의 참가 및 나가기 알림 사용 및 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67939f67e90e6c0cc044ea871560647cae9e4021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="6d747-102">반드시 Lync Server 2013에서 전화 회의 참가 및 탈퇴 알림 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6d747-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d747-103">_**마지막으로 수정 된 항목:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6d747-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6d747-104">전화 접속 사용자가 회의에 참가 하거나 전화를 걸 때 회의 알림 응용 프로그램은 발신음을 재생 하거나 사용자의 이름을 말하기로 해당 입구 또는 출구를 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="6d747-105">cmdlet를 실행하여 알림 작동 방식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="6d747-106">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="6d747-107">회의 입장 및 퇴장 알림 동작을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="6d747-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="6d747-108">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="6d747-109">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6d747-110">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="6d747-111">이 cmdlet은 참가자가 회의에 참가할 때 사용자의 이름을 기록 해야 하는지 여부와 참가자가 전화 접속 회의에 참가 하거나 나갈 때 Lync Server에서 응답 하는 방식을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="6d747-112">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="6d747-113">**EnableNameRecording**   은 회의에 들어가기 전에 익명 참가자에 게 자신의 이름을 기록할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="6d747-114">기본값은 "$true" 이며,이 값은 익명 참가자가 회의에 참가할 때 자신의 이름을 명시 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="6d747-115">(인증 된 참가자의 경우 대신 표시 이름이 사용 되므로 이름을 기록 하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="6d747-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="6d747-116">**EntryExitAnnouncementsEnabledByDefault**   는 알림을 기본적으로 설정/해제 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="6d747-117">기본값은 "$false" 이며,이 값은 기본적으로 참가자가 회의에 참가 하거나 나갈 때 알림이 제공 되지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="6d747-118">모임 이끌이가 모임을 예약할 때이 설정을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="6d747-119">**EntryExitAnnouncementsType**   는 알림을 사용 하도록 설정 된 참가자가 회의에 참가 하거나 나갈 때마다 수행 되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="6d747-120">기본값은 "UseNames" 이며 공지 사항이 설정 된 경우 "Ken Myer에서 전화 회의에 참가 했습니다."와 같은 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="6d747-p105">이러한 설정은 전역 범위나 사이트 범위에서 구성할 수 있습니다. 사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="6d747-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="6d747-p106">이 예에서는 레드몬드에 대해 사이트 범위에서 설정이 구성되었습니다. 알림이 설정되었지만 참가자가 회의에 참가할 때 이름을 얘기하라는 메시지가 표시되지 않습니다. 참가자가 회의에 참가하거나 회의에서 나갈 때 신호음이 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d747-p106">In this example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

