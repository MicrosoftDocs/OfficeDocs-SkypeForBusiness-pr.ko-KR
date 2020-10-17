---
title: 레거시 풀로 파일럿 풀 동시 사용 확인
description: 파일럿 풀 공존 성을 레거시 풀과 동일 하 게 확인 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b910939b59fdaed6df32ae504eb2719435a0161e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555554"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="a13cd-103">레거시 풀로 파일럿 풀 동시 사용 확인</span><span class="sxs-lookup"><span data-stu-id="a13cd-103">Verify pilot pool coexistence with legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a13cd-104">_**마지막으로 수정 된 항목:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="a13cd-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="a13cd-105">파일럿 풀을 배포한 후 관리 도구를 사용하여 풀 정보를 살펴보면서 두 풀이 모두 존재하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-105">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="a13cd-106">Lync Server 2013 풀 및 레거시 풀의 경우 Lync Server 2013 제어판 및 토폴로지 작성기 도구를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-106">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="a13cd-107">Lync Server 2013 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="a13cd-107">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="a13cd-108">Lync Server 2013 프런트 엔드 서버에서 관리 도구 \\ 서비스 애플릿으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-108">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="a13cd-109">프런트 엔드 서버에서 다음 서비스가 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-109">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="a13cd-110">**Lync Server 2013 서비스**</span><span class="sxs-lookup"><span data-stu-id="a13cd-110">**Lync Server 2013 services**</span></span>

<span data-ttu-id="a13cd-111">![시작 된 Lync Server 서비스 목록](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "시작 된 Lync Server 서비스 목록")</span><span class="sxs-lookup"><span data-stu-id="a13cd-111">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="a13cd-112">Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-112">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="a13cd-113">Lync server 2013 배포의 프런트 엔드 서버에서 Lync Server 2013 제어판을 열고 Lync Server 2010 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-113">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="a13cd-114">이 절차를 반복 하 여 Lync Server 2013 풀을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-114">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="a13cd-115">**Open Lync Server 2013 제어판**</span><span class="sxs-lookup"><span data-stu-id="a13cd-115">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="a13cd-116">![URL 선택 대화 상자](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "URL 선택 대화 상자")</span><span class="sxs-lookup"><span data-stu-id="a13cd-116">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a13cd-117">Lync Server 2013에서는 Lync Server 제어판을 사용 하기 전에 Silverlight를 Silverlight 버전 5로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-117">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="a13cd-118">이 토폴로지에는 이제 Lync Server 2010 및 Lync Server 2013 서버 역할이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-118">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="a13cd-119">**Lync Server 2013 제어판 토폴로지 페이지**</span><span class="sxs-lookup"><span data-stu-id="a13cd-119">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="a13cd-120">![Lync Server 제어판-토폴로지 페이지](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server 제어판-토폴로지 페이지")</span><span class="sxs-lookup"><span data-stu-id="a13cd-120">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="a13cd-121">Lync Server 2010 토폴로지 작성기에서 토폴로지 열기 시도 안 함</span><span class="sxs-lookup"><span data-stu-id="a13cd-121">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="a13cd-122">Lync Server 2010 토폴로지 작성기를 사용 하 여 토폴로지를 열려고 하면 아래 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-122">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="a13cd-123">토폴로지는 Lync Server 2013 토폴로지 작성기를 사용해 서만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-123">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="a13cd-124">Lync server 2013 및 Lync Server 2010에 대 한 풀을 만들려면 Lync Server 2013 Topology Builder를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a13cd-124">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="a13cd-125">**Lync Server 2010 토폴로지 작성기 오류 메시지**</span><span class="sxs-lookup"><span data-stu-id="a13cd-125">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="a13cd-126">![Lync Server 토폴로지 작성기 MMC Snap 오류](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server 토폴로지 작성기 MMC Snap 오류")</span><span class="sxs-lookup"><span data-stu-id="a13cd-126">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

