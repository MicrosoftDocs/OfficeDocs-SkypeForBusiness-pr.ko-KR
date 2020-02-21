---
title: 'Lync Server 2013: 전화 접속에 대 한 회의 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33f84ec3cb900b4283f30d67e318ab10d3625326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="2f33e-102">Lync Server 2013에서 전화 접속에 대 한 회의 정책 구성</span><span class="sxs-lookup"><span data-stu-id="2f33e-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f33e-103">_**마지막으로 수정 된 항목:** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="2f33e-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="2f33e-p101">회의 정책은 참가자의 회의 환경을 지정하는 사용자 계정 설정이며, 사이트 범위나 사용자 범위에서 만들 수 있습니다. 회의 정책 설정에는 회의 예약 및 참가와 관련된 여러 측면이 포함됩니다. 여러 회의 정책 설정에서는 참가자를 위한 전화 접속 회의가 지원됩니다. 전화 접속 회의를 구성할 경우 이 필드가 조직에 적절하게 설정되어 있는지 확인하고 필요한 경우 필드를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="2f33e-109">회의 정책에서 다음 필드를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="2f33e-110">**참가자가 익명 사용자**   를 초대할 수 있도록 허용이 설정을 사용 하면 모임 이끌이가 익명의 인증 되지 않은 참가자를 모임에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="2f33e-111">이 설정은 전화 접속 회의에 대해 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="2f33e-112">이 설정은 기본 전역 회의 정책에서 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="2f33e-113">**Pstn 전화 접속 회의**   사용 사용자가 pstn에서 전화 접속을 통해 회의의 오디오 부분에 참가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="2f33e-114">이 설정은 전화 접속 회의에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="2f33e-115">이 설정은 기본 전역 회의 정책에서 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="2f33e-116">**익명 참가자가 전화를 걸 수 있도록 허용**   이 설정을 사용 하면 모임에 이미 가입한 익명 사용자가 전화를 걸어 회의의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="2f33e-117">이 설정은 전화 접속 회의에 대해 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="2f33e-118">이 설정은 기본 전역 회의 정책에서 기본적으로 선택 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="2f33e-119">**Enterprise voice에 대해 사용 하도록 설정 되지 않은 참가자가 전화를 걸 수 있도록 허용**   이 설정을 사용 하면 enterprise Voice를 사용 하도록 설정 되지 않은 모임 참가자 및 이끌이는 전화를 걸어 회의의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="2f33e-120">전화 걸기 통화는 이끌이의 할당 된 음성 정책에 따라 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="2f33e-121">이 설정은 기본 전역 회의 정책에서 기본적으로 선택 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="2f33e-122">설정 기본값은 사용 안 함입니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f33e-123">이 기능을 사용 하려면 Enterprise Voice를 사용 하도록 설정 되지 않은 모임 이끌이가 해당 사용자가 구성한 회의에서 전화를 걸 수 있는 권한을 부여 하기 위해 적절 한 음성 정책을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="2f33e-124">Lync Server 관리 셸에서 Enterprise Voice를 사용 하도록 설정 하지 않은 사용자에 게 음성 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="2f33e-125">사용자에 게 자신에 게 명시적으로 할당 된 음성 정책이 없는 경우 사이트 음성 정책이 전화 걸기 요청에 권한을 부여 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="2f33e-126">사이트 음성 정책이 없으면 전역 음성 정책이 사용 됩니다.&nbsp;</span><span class="sxs-lookup"><span data-stu-id="2f33e-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="2f33e-127">이 섹션의 절차에서는 회의 정책을 수정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="2f33e-128">기본 회의 정책에서 참가자 환경을 정의 하는 모든 설정을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 모임 구성 설정 모음 만들기 또는 수정을](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f33e-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="2f33e-129">특정 사용자 또는 사용자 그룹에 대 한 회의 정책을 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f33e-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="2f33e-130">사용 가능한 모든 회의 정책 설정 목록은 [Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f33e-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="2f33e-131">전화 접속 회의 정책을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="2f33e-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="2f33e-132">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="2f33e-133">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2f33e-134">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f33e-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2f33e-135">왼쪽 탐색 모음에서 **회의**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="2f33e-136">**회의 정책** 탭에서 회의 정책 이름을 두 번 클릭하여 **회의 정책 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="2f33e-137">전화 접속 회의 필드가 조직에 적절하게 설정되어 있는지 확인하고 필요한 경우 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="2f33e-138">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2f33e-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

