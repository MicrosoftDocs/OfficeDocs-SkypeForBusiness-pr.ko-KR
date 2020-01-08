---
title: 시스템 센터 검색에 참가 하도록 Lync Server 컴퓨터 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b50fad3e0d197259847db9a94bf9e64618d7e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="38a2b-102">시스템 센터 검색에 참가 하도록 Lync Server 2013 컴퓨터 구성</span><span class="sxs-lookup"><span data-stu-id="38a2b-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38a2b-103">_**마지막으로 수정한 주제:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="38a2b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="38a2b-104">새 Lync Server 에이전트가 System Center Operations Manager의 검색 프로세스에 참여 하 고 있는지 확인 하려면 System Center Operations Manager 콘솔이 설치 된 각 컴퓨터에서 다음 절차를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="38a2b-105">**관리** 탭에서 **에이전트 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="38a2b-106">컴퓨터의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="38a2b-107">**속성** 대화 상자의 **보안** 탭에서 **이 에이전트가 프록시로 작동할 수 있도록 허용을 선택 하 고 다른 컴퓨터에서 관리 되는 개체를 검색**한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="38a2b-108">2 단계를 완료 한 후 상태 에이전트 서비스를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="38a2b-109">(서비스를 다시 부팅 하면 새 컴퓨터에 "강제" 검색을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="38a2b-110">서비스를 다시 부팅 하지 않으면 시스템 센터 Operations Manager에서 새 컴퓨터가 검색 되기까지 4 시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="38a2b-111">서비스를 다시 부팅 한 후 해당 컴퓨터의 Operations Manager 이벤트 로그에 오류 이벤트가 기록 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a2b-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

