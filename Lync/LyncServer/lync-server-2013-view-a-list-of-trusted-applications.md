---
title: 'Lync Server 2013: 신뢰할 수 있는 응용 프로그램 목록 보기'
description: 'Lync Server 2013: 신뢰할 수 있는 응용 프로그램 목록을 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d45c682550640c3fc7284e0b60ca6844896b5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574794"
---
# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="2c6fd-103">Lync Server 2013에서 신뢰할 수 있는 응용 프로그램 목록 보기</span><span class="sxs-lookup"><span data-stu-id="2c6fd-103">View a list of trusted applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c6fd-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2c6fd-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2c6fd-105">Lync Server 2013 제어판을 사용 하 여 Lync Server 2013 환경에 배포한 신뢰할 수 있는 응용 프로그램의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-105">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="2c6fd-106">신뢰할 수 있는 응용 프로그램은 Lync Server 2013에서 신뢰할 수 있는 Microsoft 통합 커뮤니케이션 관리 API (c) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-106">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="2c6fd-107">이 트러스트 관계는 다음 목록에 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-107">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="2c6fd-108">신뢰할 수 있는 응용 프로그램은 Lync Server의 인증에 대해 챌린지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-108">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="2c6fd-109">신뢰할 수 있는 응용 프로그램은 SIP 트랜잭션, 연결 또는 나가는 VoIP (Voice over Internet Protocol) 통화에 대해 Lync Server에 의해 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-109">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="2c6fd-110">신뢰할 수 있는 응용 프로그램은 사용자를 가장 하 여 명단에 표시 하지 않고도 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-110">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="2c6fd-111">신뢰할 수 있는 응용 프로그램은 가용성이 높아야 하며 탄력적으로 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-111">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="2c6fd-112">Lync Server 제어판에서는 응용 프로그램의 이름, 실행 하는 풀 및 사용 하는 포트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-112">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="2c6fd-113">신뢰할 수 있는 응용 프로그램 목록을 보려면</span><span class="sxs-lookup"><span data-stu-id="2c6fd-113">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="2c6fd-114">CsServerAdministrator, CsAdministrator, CsHelpDesk 또는 Csserveradministrator 관리자 역할에 할당 된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-114">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="2c6fd-115">Lync Server 2013에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 [Lync server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-115">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="2c6fd-116">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2c6fd-117">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2c6fd-118">왼쪽 탐색 모음에서 **토폴로지** 를 클릭 하 고 **신뢰할 수 있는 응용 프로그램**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-118">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="2c6fd-119">필요한 경우 **신뢰할 수 있는 응용 프로그램** 페이지에서 열 머리글을 클릭 하 여 응용 프로그램을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c6fd-119">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2c6fd-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c6fd-120">See Also</span></span>


[<span data-ttu-id="2c6fd-121">Lync Server 2013 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="2c6fd-121">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

