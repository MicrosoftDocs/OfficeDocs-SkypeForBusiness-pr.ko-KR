---
title: 'Lync Server 2013: Lync 사용 전화를 통해 전화 걸기 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c91980655d6786a092856c454ce4d662fef56e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="98c34-102">Lync 사용 전화 및 Lync Server 2013에서 전화 걸기 사용</span><span class="sxs-lookup"><span data-stu-id="98c34-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c34-103">_**마지막으로 수정 된 항목:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="98c34-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="98c34-104">Lync의 통화 시 기능을 사용 하면 휴대폰, "지역" 또는 PSTN (공중 전화망)에 연결 된 기타 장치를 통해 사용자가 전화 회의의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="98c34-105">Lync를 사용 하 여 모임에 참가 하려고 하면 일반적으로 **모임 오디오 참가** 대화 상자에 다음과 같은 내용이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="98c34-106">![Lync를 사용 하 여 모임 오디오 창 스크린샷 참가](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Lync를 사용 하 여 모임 오디오 창 스크린샷 참가")</span><span class="sxs-lookup"><span data-stu-id="98c34-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="98c34-107">**전화 걸기를**선택한 경우 드롭다운 목록에서 전화 번호를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="98c34-108">Lync Server 2013는 선택한 번호로 전화를 걸고, 해당 전화를 사용 하 여 회의의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="98c34-109">드롭다운 목록은 **Lync – Options** 대화 상자의 전화 탭에서 입력 한 휴대폰 번호 **(휴대폰,** 집 전화 또는 기타 전화)로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="98c34-110">![Lync 전화 설정 옵션 스크린샷](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync 전화 설정 옵션 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="98c34-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="98c34-111">**휴대폰** 탭에서 전화 번호를 입력 하지 않은 경우에는 드롭다운 상자에 사용할 수 있는 숫자가 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="98c34-112">그러나 언제 든 지 **새 번호** 를 클릭 하 고 Lync Server가 원하는 전화 번호로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="98c34-113">![Lync join meeting audio call me 창 스크린샷](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me 창 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="98c34-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="98c34-114">전화 걸기 기능을 사용 하는 경우에는 Lync Server에서 PSTN 전화 번호를 호출 하 여 원하는 방식으로이 작업을 수행 하는 것이 매우 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="98c34-115">그러나 lync Server가 Lync 사용 가능 끝점 (예: 회의실이 나 전화)에서 전화를 걸 것을 요청 하는 경우에는 최적이 아닌 환경으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="98c34-116">다음은이 문제를 해결 하는 두 가지 방법 뿐 아니라 발생할 수 있는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="98c34-117">시작 하려면 전화 번호 기능을 Lync 사용 가능 전화와 함께 제공 하는 경우 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="98c34-118">Ken Myer lync server에서 Lync Server 사용 전화 번호를 사용해 서 1-206-555-1219에 연락 하 여 모임에 참가 하려고 시도 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="98c34-119">Ken은 처음에 모임에 연결 되지만 몇 초 후 Lync에서 메시지 **호출이 완료 되지 않았거나 종료**된 것으로 표시 되 고, Ken이 모임에서 삭제 된 것 처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="98c34-120">![Lync 통화 회의 창의 스크린샷](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Lync 통화 회의 창의 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="98c34-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="98c34-121">그러나 Lync 대화 창에는 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="98c34-122">Ken Myer는 **참가자** 제목 아래에만 표시 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="98c34-123">그러나 창의 제목 표시줄을 살펴보면 회의에 총 4 명의 참가자가 포함 되어 있는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="98c34-124">마찬가지로 다른 모든 회의 참가자의 대화 창을 살펴보면 Ken Myer 아무 위치에 나 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="98c34-125">![Lync 참가자 목록 창 스크린샷](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync 참가자 목록 창 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="98c34-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="98c34-126">또한 Ken Myer는 Lync 사용 전화를 사용 하 여 통화의 오디오 부분에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="98c34-127">전화 걸기 기능에서 실제로 작업을 수행 했지만 사용자 환경이 최적 보다 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="98c34-128">이 문제를 해결 하는 데는 두 가지 이상의 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="98c34-129">이미이 방식으로 회의에 참가 한 경우 (예 Ken Myer) 다른 형식으로 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="98c34-130">예를 들어 인스턴트 메시지를 보내는 경우 대화 창에는 사용자 자신을 포함 하 여 모든 회의 참가자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="98c34-131">![Lync 대화 및 참가자 목록 스크린샷](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync 대화 및 참가자 목록 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="98c34-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="98c34-132">이 시점에서 예상 되는 방식으로 모임에 참가할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="98c34-133">또는 모임에 참가 하는 방식을 변경 하 여이 문제를 완전히 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="98c34-134">Lync Server에서 Lync Server 사용 전화를 호출 해야 하는 경우에는 오디오 연결 없이 모임에 참가 하는 것으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="98c34-135">이렇게 하려면 모임 오디오 참가 대화 상자에 다음이 표시 될 때 오디오 연결 안 함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="98c34-136">![Lync가 모임 오디오 창 스크린샷에 참가 하지 않음](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync가 모임 오디오 창 스크린샷에 참가 하지 않음")</span><span class="sxs-lookup"><span data-stu-id="98c34-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="98c34-137">모임에 성공적으로 연결한 후에는 이제 Lync Server 사용 가능 전화를 모임에 참가 하도록 "초대" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="98c34-138">이렇게 하려면 사용자 아이콘 위에 마우스를 놓고 **추가 사용자 초대**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="98c34-139">![Lync 더 많은 참가자 초대 창 스크린샷](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync 더 많은 참가자 초대 창 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="98c34-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="98c34-140">그러면 **IM 보내기** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="98c34-141">대화 상자 제목 무시 (실제로 인스턴트 메시지를 전송 하지 않음) 및 Lync 사용 전화의 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="98c34-142">![IM 보내기 대화 상자 스크린샷](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "IM 보내기 대화 상자 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="98c34-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="98c34-143">**확인**을 클릭 하면 Lync Server가 대화 상자에 입력 된 번호를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="98c34-144">연결이 설정 되 면 Lync 사용이 가능한 전화를 통해 전체 오디오 기능을 사용할 수 있으며 전체 회의 명단을 확인 하 고 상호 작용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c34-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

