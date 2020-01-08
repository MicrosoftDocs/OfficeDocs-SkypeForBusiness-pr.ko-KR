---
title: 레거시 풀로 파일럿 풀 동시 사용 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67b113a4619d90345df9858f348d663383066d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="5f46a-102">레거시 풀로 파일럿 풀 동시 사용 확인</span><span class="sxs-lookup"><span data-stu-id="5f46a-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f46a-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5f46a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a><span data-ttu-id="5f46a-104">Office Communications Server 2007 R2 관리 도구에서 풀 확인</span><span class="sxs-lookup"><span data-stu-id="5f46a-104">Verify the Pool in Office Communications Server 2007 R2 Administrative Tool</span></span>

1.  <span data-ttu-id="5f46a-105">Office Communications Server 2007 R2 관리 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-105">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="5f46a-106">**포리스트** 노드를 확장 하 고 **스탠더드 버전 서버** 또는 **엔터프라이즈 풀** 노드를 확장 한 다음 풀 또는 서버 이름을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-106">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="5f46a-107">Office Communications Server 2007 R2 서비스가 풀에서 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-107">Ensure that the Office Communications Server 2007 R2 services are running on the pool.</span></span>
    
    <span data-ttu-id="5f46a-108">![Office Communications server 2007 R2 관리 콘솔](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "office Communications Server 2007 R2 관리 콘솔")</span><span class="sxs-lookup"><span data-stu-id="5f46a-108">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a><span data-ttu-id="5f46a-109">Lync Server 2013 제어판에서 시험 운용 풀 확인</span><span class="sxs-lookup"><span data-stu-id="5f46a-109">Verify the Pilot Pool in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="5f46a-110">CsAdministrator 역할의 구성원 인 사용자 계정에서 Lync Server 2013 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-110">From a user account that is a member of the CsAdministrator role, log on to the Lync Server 2013 Front End server.</span></span>

2.  <span data-ttu-id="5f46a-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5f46a-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f46a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5f46a-113">**토폴로지**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-113">Click **Topology**.</span></span>

4.  <span data-ttu-id="5f46a-114">배포 된 서버가 파일럿 풀에 존재 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-114">Verify that the servers you deployed are present in your pilot pool.</span></span>
    
    <span data-ttu-id="5f46a-115">![Lync Server 제어판 토폴로지 페이지](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync server 제어판 토폴로지 페이지")</span><span class="sxs-lookup"><span data-stu-id="5f46a-115">![Lync Server Control Panel Topology page](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server Control Panel Topology page")</span></span>  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a><span data-ttu-id="5f46a-116">Lync Server 2013 서비스가 시작 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="5f46a-116">Verify Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="5f46a-117">Lync Server 2013 프런트 엔드 서버에서 **관리 도구** 그룹에 있는 **서비스** 애플릿을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-117">On the Lync Server 2013 Front End Server, open the **Services** applet from the **Administrative Tools** group.</span></span>

2.  <span data-ttu-id="5f46a-118">나열 된 서비스가 다음 그림의 목록과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f46a-118">Verify that the services listed match the list in the following figure.</span></span>
    
    <span data-ttu-id="5f46a-119">Lync services가 시작 된 lync services 시작(images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "서비스 페이지가") ![표시 된 서비스 페이지]</span><span class="sxs-lookup"><span data-stu-id="5f46a-119">![Services page showing Lync services started](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Services page showing Lync services started")</span></span>  

</div>

</div>

<span> </span>

</div>

</div>

</div>

