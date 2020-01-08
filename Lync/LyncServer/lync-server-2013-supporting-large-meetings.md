---
title: 'Lync Server 2013: 대용량 모임 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="97e99-102">Lync Server 2013를 사용 하 여 대용량 모임 지원</span><span class="sxs-lookup"><span data-stu-id="97e99-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97e99-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="97e99-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="97e99-104">대규모 회의는 다음 특성을 가지 므로 이전 섹션에서 설명한 테스트 모델을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="97e99-105">모임 형식은 일대다 프레젠테이션입니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="97e99-106">한 명 또는 소수의 사용자가 발표자이 고 모든 사람이 참석자로 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="97e99-107">PowerPoint 프레젠테이션 공유는 기본 데이터 공동 작업 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="97e99-108">오디오는 필수 이며 비디오만 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="97e99-109">일반적으로 모임 이끌이 또는 이끌이를 위한 보조자 등의 전담 사용자가 모임을 미리 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="97e99-110">전용 스태프 (발표자가 아님)는 온라인 모임 연결, 오디오, 비디오 및 슬라이드 공유 작업 확인, 로비와 사용자 역할, 음소거 및 음소거 해제, 질문 하기, 녹음/녹화 관리 등의 모임을 실행 합니다. 알맞은.</span><span class="sxs-lookup"><span data-stu-id="97e99-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="97e99-111">최대 1000 명의 사용자에 대 한 대규모 모임을 지원 하려면 공유 하드웨어 모델과 비 예약 모델에 관련 된 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="97e99-112">1000 사용자의 모임에 충분 한 CPU 및 메모리 리소스를 확보 하기 위해 호스팅 프런트 엔드 서버는 다른 인스턴트 메시징 (IM) 및 현재 상태 또는 엔터프라이즈 음성 작업 부하를 호스팅하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="97e99-113">또한 다른 모임의 크기에 관계 없이 다른 모임을 호스팅하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="97e99-114">즉, 최대 1000 사용자에 게 모임을 호스팅 하려면 최대 1000 사용자에 대 한 대규모 모임 호스팅 전용 별도의 Lync Server 풀을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="97e99-115">대규모 모임을 호스팅 전용으로 사용할 수 있는 Lync 서버 풀은 동시에 최대 1000 사용자에 대 한 하나의 모임만 호스팅하고 있으므로, 프런트 엔드 Serv의 전용 지원을 위해 모임 시간을 대역 외 예약 프로세스를 통해 미리 예약 해야 합니다. 사람이.</span><span class="sxs-lookup"><span data-stu-id="97e99-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="97e99-116">동시에 여러 개의 대용량 모임을 지원 하려면 하나의 전용 대량 모임 풀을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="97e99-117">전용 사용자는 대규모 모임의 온라인 부분을 실행 하 고 모니터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-117">We recommend that a dedicated person run and monitor the online portion of a large meeting.</span></span> <span data-ttu-id="97e99-118">조직의 기본 설정에 따라이 사람이 이끌이, 이끌이 또는 발표자의 대리인 또는 전용 대규모 모임 지원 팀의 구성원 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-118">This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="97e99-119">다음 섹션에서는 대규모 모임 시나리오를 지원 하기 위해 Lync Server 2013를 사용 하는 모범 사례를 포함 하 여 대규모 모임에 대 한 전용 풀을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e99-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97e99-120">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="97e99-120">In This Section</span></span>

  - [<span data-ttu-id="97e99-121">Lync Server 2013에서 대규모 모임에 대 한 지원 설정</span><span class="sxs-lookup"><span data-stu-id="97e99-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="97e99-122">Lync Server 2013에서 대규모 모임 관리</span><span class="sxs-lookup"><span data-stu-id="97e99-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

