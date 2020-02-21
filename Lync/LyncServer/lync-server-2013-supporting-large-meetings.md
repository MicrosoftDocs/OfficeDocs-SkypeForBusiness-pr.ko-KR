---
title: 'Lync Server 2013: 대규모 모임 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 949e5fb209722d8a0d8476d017bba1b7144561a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="3a778-102">Lync Server 2013를 사용 하 여 대규모 모임 지원</span><span class="sxs-lookup"><span data-stu-id="3a778-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a778-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3a778-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3a778-104">대규모 모임은 다음과 같은 특성을 갖기 때문에 이전 섹션에서 설명한 테스트 모델을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="3a778-105">모임 형식이 일대다 프레젠테이션입니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="3a778-106">한 명 또는 소수의 사용자가 발표자이고 그외 모든 사람은 참석자로만 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="3a778-107">PowerPoint 프레젠테이션 공유가 기본 데이터 공동 작업 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="3a778-108">오디오가 필요하고 비디오를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="3a778-109">모임 이끌이 또는 이끌이의 보조 등 전담 사용자가 미리 모임을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="3a778-110">전담 직원(발표자가 아님)이 온라인 모임에 연결하고, 오디오, 비디오 및 슬라이드 공유가 작동하는지 확인하고, 대기실 및 사용자 역할을 관리하고, 참가자를 음소거하거나 음소거를 해제하고, 질문을 받고, 기록을 관리하는 등 모임을 적절하게 운영합니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="3a778-111">최대 1000명의 사용자를 포함하는 대규모 모임을 지원하기 위해서는 공유 하드웨어 모델 및 비예약 모델 모두와 관련된 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="3a778-112">최대 1000 명의 모임에 대 한 충분 한 CPU 및 메모리 리소스를 확보 하려면 호스팅 프런트 엔드 서버에서 다른 IM (인스턴트 메시징) 및 현재 상태 또는 Enterprise Voice 작업을 호스트 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="3a778-113">또한 다른 모임의 크기에 관계없이 다른 모임을 호스팅해서도 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="3a778-114">즉, 최대 1000 명의 사용자에 게 모임을 호스트 하려면 최대 1000 명의 사용자에 대 한 대규모 회의 호스팅 전용의 별도 Lync Server 풀을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="3a778-115">대규모 모임 호스팅 전용 Lync Server 풀은 최대 1000 명의 모임 회의를 동시에 호스트 해야 하므로, 프런트 엔드 Serv에서 전용 지원을 위해 대역 외 예약 프로세스를 통해 모임 시간을 미리 예약 해야 합니다. 사람이.</span><span class="sxs-lookup"><span data-stu-id="3a778-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="3a778-116">동시에 두 개 이상의 대규모 모임을 지원 하려면 여러 전용 대규모 모임 풀을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="3a778-p103">대규모 모임의 온라인 부분은 전담 사용자가 실행하고 모니터링하는 것이 좋습니다. 이 사용자는 조직의 상황에 따라 이끌이거나 이끌이 또는 발표자의 대리인 또는 전담 대규모 모임 지원 팀의 구성원일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="3a778-119">다음 섹션에서는 Lync Server 2013을 사용 하 여 대규모 모임 시나리오를 지원 하기 위한 모범 사례를 포함 하 여 대규모 모임에 대 한 전용 풀을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a778-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3a778-120">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3a778-120">In This Section</span></span>

  - [<span data-ttu-id="3a778-121">Lync Server 2013에서 대규모 모임에 대 한 지원 설정</span><span class="sxs-lookup"><span data-stu-id="3a778-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="3a778-122">Lync Server 2013에서 대규모 모임 관리</span><span class="sxs-lookup"><span data-stu-id="3a778-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

