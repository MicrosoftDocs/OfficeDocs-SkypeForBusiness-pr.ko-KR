---
title: 외부 사용자에 대한 페더레이션 및 원격 액세스 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ad994eb7769dff067195520c2c6fde955910f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="1749d-102">외부 사용자에 대한 페더레이션 및 원격 액세스 확인</span><span class="sxs-lookup"><span data-stu-id="1749d-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1749d-103">_**마지막으로 수정한 주제:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="1749d-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="1749d-104">페더레이션 경로를 Lync Server 2013 Edge 서버로 전환 하 고 나면 일부 기능적 테스트를 수행 하 여 페더레이션이 예상 대로 수행 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="1749d-105">외부 사용자 액세스에 대 한 테스트에는 조직에서 지 원하는 각 외부 사용자 유형 (다음의 일부 또는 모두 포함)이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="1749d-106">외부 사용자 및 외부 액세스 연결 테스트</span><span class="sxs-lookup"><span data-stu-id="1749d-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="1749d-107">하나 이상의 페더레이션 도메인, Lync Server 2013의 내부 사용자, Lync Server 2010의 사용자 등의 사용자</span><span class="sxs-lookup"><span data-stu-id="1749d-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="1749d-108">인스턴트 메시지 (IM), 현재 상태, 오디오/비디오 (A/V) 및 데스크톱 공유를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="1749d-109">조직에서 지원 하 고 프로 비전이 완료 된 각 공용 IM 서비스 공급자의 사용자는 Lync Server 2013 및 Lync Server 2010의 사용자와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="1749d-110">익명 사용자가 회의에 참가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="1749d-111">Lync server 2010에서 원격 사용자 액세스를 사용 하 여 (VPN을 제외한 인트라넷 외부에서 Lync Server 2010에 로그인 하는 경우 2013) 사용자 및 lync server 2010의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="1749d-112">IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="1749d-113">Lync server 2013에서 원격 사용자 액세스를 사용 하 여 (VPN을 제외한 인트라넷 외부에서 Lync Server 2013에 로그인 하는 경우 2013) 사용자 및 lync server 2010의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="1749d-114">IM, 현재 상태, A/V, 데스크톱 공유를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1749d-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

