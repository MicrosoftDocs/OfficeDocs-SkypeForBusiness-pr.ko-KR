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
ms.openlocfilehash: a1b020217863dd4adf04a8e91041dcae8fa078ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-usage-reports-in-lync-server-2013"></a><span data-ttu-id="50d0f-102">Lync Server 2013의 시스템 사용 현황 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-102">System usage reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50d0f-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="50d0f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="50d0f-104">시스템 사용 현황 보고서는 Lync Server에서 수집한 CDR (통화 정보 기록) 데이터를 기반으로 시스템 사용 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-104">The System Usage Reports provide system usage information based on call detail recording (CDR) data collected by the Lync Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="50d0f-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="50d0f-105">In This Section</span></span>

  - [<span data-ttu-id="50d0f-106">Lync Server 2013의 사용자 등록 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-106">User Registration Report in Lync Server 2013</span></span>](lync-server-2013-user-registration-report.md)
    
    <span data-ttu-id="50d0f-107">사용자 로그온과 같은 등록 이벤트에 따라 Lync Server 2013 배포에 대 한 사용자 연결을 요약해 서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-107">Provides a summary of user connectivity to the Lync Server 2013 deployment based on registration events such as user logons.</span></span> <span data-ttu-id="50d0f-108">이 보고서에서는 내부 및 외부 로그온을 모두 확인 하 고, Lync Server 2013에 로그온 한 사용자 수를 로그온 한 동안 실제로 사용한 사용자 수와 비교할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-108">The report provides a way to view both internal and external logons, and to compare the number of users who logged on to Lync Server 2013 with the number of users who actually used the service while they were logged on.</span></span>

  - [<span data-ttu-id="50d0f-109">Lync Server 2013의 피어 투 피어 활동 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-109">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-summary-report.md)
    
    <span data-ttu-id="50d0f-p102">피어-투-피어 활동 요약 보고서에서는 피어-투-피어 IM(인스턴트 메시징), 오디오, 비디오, 파일, 전송 및 응용 프로그램 공유 세션에 대한 요약을 제공합니다. 피어-투-피어 세션은 두 사용자만 포함된 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-p102">Provides a summary of peer-to-peer instant messaging (IM), audio, video, file transfer, and application sharing sessions. Peer-to-peer sessions are sessions involving just two users.</span></span>

  - [<span data-ttu-id="50d0f-112">Lync Server 2013의 전화 회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-112">Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-conference-summary-report.md)
    
    <span data-ttu-id="50d0f-113">모든 회의 활동에 대한 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-113">Provides a summary of all conference activities.</span></span> <span data-ttu-id="50d0f-114">회의는 세 명 이상의 사용자가 포함된 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-114">Conferences are sessions involving three or more people.</span></span>

  - [<span data-ttu-id="50d0f-115">Lync Server 2013의 PSTN 전화 회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-115">PSTN Conference Summary Report in Lync Server 2013</span></span>](lync-server-2013-pstn-conference-summary-report.md)
    
    <span data-ttu-id="50d0f-p104">모든 PSTN 회의에 대한 요약 정보를 제공합니다. 이러한 회의는 사용자 중 한 명 이상이 공중 전화망(PSTN)을 사용하여 전화 접속하는 회의로, *전화 접속 회의*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-p104">Provides a summary of all PSTN conferences. These are conferences where at least one user dials in using the public switched telephone network (PSTN), which is also referred to as *dial-in conferencing*.</span></span>

  - [<span data-ttu-id="50d0f-118">Lync Server 2013의 응답 그룹 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-118">Response Group Usage Report in Lync Server 2013</span></span>](lync-server-2013-response-group-usage-report.md)
    
    <span data-ttu-id="50d0f-119">응답 그룹 사용에 대 한 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-119">Provides a summary of Response Group usage.</span></span> <span data-ttu-id="50d0f-120">응답 그룹 응용 프로그램을 통해 전화 통화를 자동으로 지원 센터 또는 고객 지원부와 같은 엔터티로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-120">The Response Group application provides a way for you to automatically route phone calls to entities such as a help desk or customer support line.</span></span>

  - [<span data-ttu-id="50d0f-121">Lync Server 2013의 IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-121">IP Phone Inventory Report in Lync Server 2013</span></span>](lync-server-2013-ip-phone-inventory-report.md)
    
    <span data-ttu-id="50d0f-122">조직에서 현재 사용 중인 IP 전화에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-122">Provides information about the IP phones currently in use in the organization.</span></span> <span data-ttu-id="50d0f-123">이 보고서는 전화 등록 및 로그온을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-123">The report is based on phone registrations and logons.</span></span> <span data-ttu-id="50d0f-124">이 보고서를 완전한 인벤토리로 간주해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-124">It should not be considered a complete inventory.</span></span> <span data-ttu-id="50d0f-125">예를 들어 이전에 제거한 전화가 보고서에는 여전히 나열되어 있을 수 있습니다(최소한 한 번 이상 로그온한 경우).</span><span class="sxs-lookup"><span data-stu-id="50d0f-125">For example, you might have removed phones that are still listed in the report because they logged on at least once.</span></span> <span data-ttu-id="50d0f-126">마찬가지로 사용자가 새 전화기를 사용 하 여 Lync Server에 로그온 하지 않았으므로 보고서에 새 전화가 표시 되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-126">Likewise, you might also have new phones that do not show up in the report simply because users have not logged on to Lync Server with their new phones yet.</span></span>

  - [<span data-ttu-id="50d0f-127">Lync Server 2013의 통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="50d0f-127">Call Admission Control Report in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-report.md)
    
    <span data-ttu-id="50d0f-p107">통화 허용 제어를 사용하는 피어-투-피어 및 회의 활동 목록을 제공합니다. CAC(통화 허용 제어)는 음성 또는 비디오 통화와 같은 실시간 통신 세션을 대역폭 제약 조건에 따라 허용할지 여부를 결정하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="50d0f-p107">Provides a list of peer-to-peer and conference activities that use call admission control. Call admission control (CAC) is a way of determining whether you should allow real-time communications sessions, such as voice or video calls, based on bandwidth constraints.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

