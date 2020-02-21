---
title: 'Lync Server 2013: 통화 관리 기능 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying call management features
ms:assetid: 1667cfe4-76fa-4e10-91bb-b3efbedbf759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204706(v=OCS.15)
ms:contentKeyID: 48183504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c5f2664275b4c6c0e3c93810a7a9521f155f21f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="22681-102">Lync Server 2013의 통화 관리 기능 배포</span><span class="sxs-lookup"><span data-stu-id="22681-102">Deploying call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22681-103">_**마지막으로 수정 된 항목:** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="22681-103">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="22681-104">Enterprise Voice 통화 관리 기능은 수신 전화를 라우팅하고 받는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="22681-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="22681-105">Lync Server 2013에서는 다음과 같은 통화 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22681-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="22681-106">**통화 대기:** 음성 사용자가 통화를 일시적으로 대기 했다가 같은 전화나 다른 전화기에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22681-106">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="22681-107">**그룹 픽업:** 사용자가 통화 픽업 그룹 번호에 전화를 걸어 pickup 그룹에 할당 된 다른 사용자에 게 보낸 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22681-107">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="22681-108">**응답 그룹:** 헌트 그룹 또는 IVR (대화형 음성 응답) 질문과 대답을 사용 하 여 수신 전화를 에이전트 그룹으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="22681-108">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="22681-109">**공지 사항:** 지정 되지 않은 번호에 대 한 통화에 대해 메시지를 재생 하거나, 통화를 다른 곳으로 라우트 하거나 두 가지를 모두 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22681-109">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="22681-110">이 섹션에서는 Enterprise Voice 배포 중에 이러한 통화 관리 기능을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22681-110">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="22681-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="22681-111">In This Section</span></span>

  - [<span data-ttu-id="22681-112">Lync Server 2013에서 통화 대기 구성</span><span class="sxs-lookup"><span data-stu-id="22681-112">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="22681-113">Lync Server 2013에서 그룹 통화 픽업 구성</span><span class="sxs-lookup"><span data-stu-id="22681-113">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="22681-114">Lync Server 2013에서 응답 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="22681-114">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="22681-115">Lync Server 2013에서 할당 되지 않은 번호에 대 한 알림 구성</span><span class="sxs-lookup"><span data-stu-id="22681-115">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

