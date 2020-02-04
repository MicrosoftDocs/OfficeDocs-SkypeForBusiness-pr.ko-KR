---
title: 'Lync Server 2013: 시스템 사용 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System usage reports
ms:assetid: 187d316d-2456-417e-b636-05527a18ef06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558618(v=OCS.15)
ms:contentKeyID: 48183529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a349a9816f11b73d942598f0141df497fb0294c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="93816-102">Lync Server 2013의 시스템 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93816-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="93816-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="93816-104">시스템 사용 보고서는 Lync Server에서 수집한 CDR (통화 정보 기록) 데이터를 기반으로 시스템 사용 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93816-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="93816-105">In This Section</span></span>

  - [<span data-ttu-id="93816-106">Lync Server 2013의 사용자 등록 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="93816-107">사용자 로그온 등의 등록 이벤트를 기준으로 Lync Server 2013 배포에 대 한 사용자 연결 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="93816-108">이 보고서는 내부 및 외부 로그온을 모두 볼 수 있는 방법을 제공 하 고, Lync Server 2013에 로그온 한 사용자 수와 함께 서비스를 실제로 사용한 사용자 수를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="93816-109">Lync Server 2013의 피어 투 피어 작업 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="93816-110">피어 투 피어 인스턴트 메시지 (IM), 오디오, 비디오, 파일 전송 및 응용 프로그램 공유 세션에 대 한 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-110">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions.</span></span> <span data-ttu-id="93816-111">피어 투 피어 세션은 두 명의 사용자만 참여 하는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="93816-111">Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="93816-112">Lync Server 2013의 컨퍼런스 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="93816-113">모든 회의 활동에 대 한 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="93816-114">회의는 3 명 이상의 사람들과 관련 된 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="93816-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="93816-115">Lync Server 2013의 PSTN 회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="93816-116">모든 PSTN 컨퍼런스 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-116">Provides a summary of all PSTN conferences.</span></span> <span data-ttu-id="93816-117">이는 한 명 이상의 사용자가 *전화 접속 회의*라고도 하는 PSTN (공개 교환 전화 네트워크)을 사용 하 여 전화를 거는 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="93816-117">These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="93816-118">Lync Server 2013의 응답 그룹 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="93816-119">응답 그룹 사용에 대 한 요약 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="93816-120">응답 그룹 응용 프로그램은 전화 통화를 헬프 데스크 또는 고객 지원 줄과 같은 엔터티로 자동으로 라우팅하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="93816-121">Lync Server 2013의 IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="93816-122">조직에서 현재 사용 중인 IP 전화에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="93816-123">이 보고서는 전화 등록 및 로그온에 기반을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93816-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="93816-124">전체 인벤터리로 간주 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93816-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="93816-125">예를 들어, 보고서에 여전히 나열 된 전화를 한 번 이상 로그온 하 여 제거 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93816-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="93816-126">마찬가지로, 사용자가 새로운 전화기를 사용 하 여 Lync Server에 로그인 하지 않았기 때문에 보고서에 새 전화가 표시 되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93816-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="93816-127">Lync Server 2013의 통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="93816-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="93816-128">통화 허용 제어를 사용 하는 피어 투 피어 및 회의 활동 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93816-128">Provides a list of peer-to-peer and conference activities that use call admission control.</span></span> <span data-ttu-id="93816-129">CAC (통화 허용 제어)는 음성 또는 영상 통화와 같은 실시간 통신 세션을 대역폭 제약 조건에 따라 허용 해야 하는지 여부를 결정 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="93816-129">Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

