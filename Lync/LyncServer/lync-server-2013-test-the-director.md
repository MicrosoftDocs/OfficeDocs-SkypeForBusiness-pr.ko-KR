---
title: 'Lync Server 2013: 디렉터 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8fbb19ac08886c7603d3b1d60ae3946f7bde32
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="bed85-102">Lync Server 2013에서 디렉터 테스트</span><span class="sxs-lookup"><span data-stu-id="bed85-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed85-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="bed85-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="bed85-104">이 단계에서는 디렉터나 디렉터 풀이 구성되어 있지만 DNS(Domain Name System) SRV 항목에서 여전히 클라이언트에게 풀이나 Standard Edition Server를 사용하여 로그온하라고 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="bed85-105">Lync 2013 클라이언트에서 디렉터를 사용 하 여 자동으로 로그온 하도록 DNS 레코드를 변경 하기 전에 디렉터를 수동으로 가리켜 클라이언트를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="bed85-106">배포를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="bed85-106">To test the deployment</span></span>

1.  <span data-ttu-id="bed85-107">**Csadministrator** 그룹에 속하는 도메인 계정을 사용 하 여 Lync Server 제어판이 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="bed85-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bed85-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bed85-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bed85-110">탐색 창에서 **토폴로지**를 클릭 하 고 **상태** 열에서 디렉터 또는 디렉터 풀에 대 한 화살표 ( ![녹색 화살표가 있는 서버 아이콘](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "녹색 화살표가 있는 서버 아이콘"))가 있는 녹색 서버가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="bed85-111">Lync Server 2013 클라이언트를 설치한 두 대의 클라이언트 컴퓨터를 연결 하 고 각 컴퓨터에 Lync Server 2013에 대해 사용 하도록 설정 된 다른 사용자 계정을 사용 하 여 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="bed85-112">클라이언트 컴퓨터 중 한 대에서 **옵션** 메뉴를 클릭하고 **개인** 설정 그룹을 선택한 다음 **고급**, **수동 구성**을 차례로 클릭하고 **내부 서버 이름 또는 IP 주소**를 새 디렉터나 디렉터 풀의 FQDN(정규화된 도메인 이름)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="bed85-113">두 클라이언트에 모두 로그온하고 디렉터를 사용한 클라이언트 로그온이 제대로 로그온되는지를 확인하고 다른 사용자의 현재 상태를 확인한 다음 두 사용자가 인스턴트 메시지를 교환할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bed85-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

