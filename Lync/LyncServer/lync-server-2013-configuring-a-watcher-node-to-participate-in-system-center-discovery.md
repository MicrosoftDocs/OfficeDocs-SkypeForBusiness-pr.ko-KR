---
title: 시스템 센터 검색에 참여 하도록 감시자 노드 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="d788c-102">Lync Server 2013에서 시스템 센터 검색에 참가 하도록 감시자 노드 구성</span><span class="sxs-lookup"><span data-stu-id="d788c-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d788c-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d788c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d788c-104">감시자 노드가 System Center Operations Manager의 검색 프로세스에 참여 하 고 있는지 확인 하려면 System Center Operations Manager 콘솔이 설치 된 컴퓨터에서 다음 절차를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d788c-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="d788c-105">**관리** 탭에서 **에이전트 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d788c-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="d788c-106">감시자 노드 컴퓨터의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d788c-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="d788c-107">**속성** 대화 상자의 **보안** 탭에서 **이 에이전트가 프록시로 작동할 수 있도록 허용을 선택 하 고 다른 컴퓨터에서 관리 되는 개체를 검색**한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d788c-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="d788c-108">감시자 노드를 프록시 역할을 구성한 후에는 감시자 노드 컴퓨터를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="d788c-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="d788c-109">컴퓨터를 다시 부팅 한 후 해당 컴퓨터의 Operations Manager 이벤트 로그에 오류 이벤트가 기록 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d788c-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="d788c-110">컴퓨터가 15 분 동안 실행 된 후에는 Operations Manager 콘솔을 사용 하 여 lync Server 컴퓨터가 **lync** 범주 아래에 나열 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d788c-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

