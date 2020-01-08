---
title: 'Lync Server 2013: 통화 관리 기능 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call management features
ms:assetid: 5f557345-5a04-45d6-b274-c02dbfe41b33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398421(v=OCS.15)
ms:contentKeyID: 48184298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c799051615a75801640c63ade6fe6d23b8a62dda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-management-features-in-lync-server-2013"></a><span data-ttu-id="6b104-102">Lync Server 2013의 통화 관리 기능 계획</span><span class="sxs-lookup"><span data-stu-id="6b104-102">Planning for call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b104-103">_**마지막으로 수정한 주제:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="6b104-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="6b104-104">기업 음성 통화 관리 기능은 수신 전화를 라우팅하거나 응답 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="6b104-105">Lync Server 2013는 다음과 같은 통화 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="6b104-106">**통화**대기: 음성 사용자가 전화를 일시적으로 충전 한 다음 같은 전화 또는 다른 전화기에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-106">**Call Park**:   Enables voice users to temporarily park a call and then pick it up from the same or another phone.</span></span>

  - <span data-ttu-id="6b104-107">**그룹 픽업**: 음성 사용자가 통화 픽업 그룹에 할당 된 다른 음성 사용자에 게 연결 되는 통화를 선택할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-107">**Group Pickup**:   Enables voice users to pick up calls that are ringing for other voice users who are assigned to call pickup groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6b104-108">그룹 Pickup는 Lync Server에 대 한 누적 업데이트 (2013 2 월 2013)와 관련 된 새로운 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-108">Group Pickup is new with Cumulative Updates for Lync Server 2013: February 2013.</span></span>

    
    </div>

  - <span data-ttu-id="6b104-109">**응답 그룹**: 헌트 그룹 또는 IVR (대화형 음성 응답) 질문 및 답변을 사용 하 여 수신 전화를 에이전트 그룹으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-109">**Response Group**:   Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="6b104-110">**공지 사항:**    지정 하지 않은 번호에 대 한 통화에 대 한 메시지를 재생 하거나 통화를 다른 곳으로 또는 둘 다로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-110">**Announcement:**    Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="6b104-111">엔터프라이즈 음성을 배포 하려는 경우 이러한 통화 관리 기능 중 일부 또는 모두를 구현 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b104-111">If you plan to deploy Enterprise Voice, you can choose to implement any or all of these call management features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6b104-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6b104-112">In This Section</span></span>

  - [<span data-ttu-id="6b104-113">Lync Server 2013의 통화 대기 계획</span><span class="sxs-lookup"><span data-stu-id="6b104-113">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)

  - [<span data-ttu-id="6b104-114">Lync Server 2013의 그룹 통화 픽업 계획</span><span class="sxs-lookup"><span data-stu-id="6b104-114">Planning for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-planning-for-group-call-pickup.md)

  - [<span data-ttu-id="6b104-115">Lync Server 2013의 응답 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="6b104-115">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)

  - [<span data-ttu-id="6b104-116">Lync Server 2013의 알림 계획</span><span class="sxs-lookup"><span data-stu-id="6b104-116">Planning for announcements in Lync Server 2013</span></span>](lync-server-2013-planning-for-announcements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

