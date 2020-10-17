---
title: 'Lync Server 2013: 통화 관리 기능 관리'
description: 'Lync Server 2013: 통화 관리 기능 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call management features
ms:assetid: c1261140-7a17-4bb2-9823-aa2cf307067c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721872(v=OCS.15)
ms:contentKeyID: 49733805
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c51aa3174ee42047e6b6fe25a834ec832ebc889
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569174"
---
# <a name="managing-call-management-features-in-lync-server-2013"></a><span data-ttu-id="f2b6c-103">Lync Server 2013의 통화 관리 기능 관리</span><span class="sxs-lookup"><span data-stu-id="f2b6c-103">Managing call management features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2b6c-104">_**마지막으로 수정 된 항목:** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="f2b6c-104">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="f2b6c-105">Enterprise Voice 통화 관리 기능은 수신 전화를 라우팅하고 받는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b6c-105">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="f2b6c-106">Lync Server 2013에서는 다음과 같은 통화 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b6c-106">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="f2b6c-107">**통화 대기:** 음성 사용자가 통화를 일시적으로 대기 했다가 같은 전화나 다른 전화기에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b6c-107">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="f2b6c-108">**그룹 픽업:** 사용자가 통화 픽업 그룹 번호를 사용 하 여 다른 사용자에 게 신호음 울림 통화를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b6c-108">**Group Pickup:** Enables users to pick up calls that are ringing for other users by dialing a call pickup group number.</span></span>

  - <span data-ttu-id="f2b6c-109">**응답 그룹:** 헌트 그룹 또는 IVR (대화형 음성 응답) 질문과 대답을 사용 하 여 수신 전화를 에이전트 그룹으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b6c-109">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="f2b6c-110">**공지 사항:** 지정 되지 않은 번호에 대 한 통화에 대해 메시지를 재생 하거나, 통화를 다른 곳으로 라우트 하거나 두 가지를 모두 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b6c-110">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="f2b6c-111">이 섹션에서는 엔터프라이즈 음성 배포에서 이러한 통화 관리 기능을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b6c-111">This section describes how to manage these call management features in your Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f2b6c-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f2b6c-112">In This Section</span></span>

  - [<span data-ttu-id="f2b6c-113">Lync Server 2013의 통화 대기 관리</span><span class="sxs-lookup"><span data-stu-id="f2b6c-113">Managing Call Park in Lync Server 2013</span></span>](lync-server-2013-managing-call-park.md)

  - [<span data-ttu-id="f2b6c-114">Lync Server 2013에서 그룹 통화 픽업 관리</span><span class="sxs-lookup"><span data-stu-id="f2b6c-114">Managing Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-managing-group-call-pickup.md)

  - [<span data-ttu-id="f2b6c-115">Lync Server 2013에서 응답 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="f2b6c-115">Managing response groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-groups.md)

  - [<span data-ttu-id="f2b6c-116">Lync Server 2013에서 할당 되지 않은 번호에 대 한 통화 관리</span><span class="sxs-lookup"><span data-stu-id="f2b6c-116">Managing calls to unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-managing-calls-to-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

