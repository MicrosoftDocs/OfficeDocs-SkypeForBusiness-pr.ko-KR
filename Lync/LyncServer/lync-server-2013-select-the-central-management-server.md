---
title: 'Lync Server 2013: 중앙 관리 서버 선택'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa99142b1e0814335ea1ca1de8ecf5452029943
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="5531f-102">Lync Server 2013에서 중앙 관리 서버 선택</span><span class="sxs-lookup"><span data-stu-id="5531f-102">Select the Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5531f-103">_**마지막으로 수정한 주제:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="5531f-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="5531f-104">토폴로지를 정의 하 고 구성할 수 있으려면 먼저 중앙 관리 서버를 설치할 위치를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5531f-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5531f-105">토폴로지 작성기에서 토폴로지를 게시 해야이 문제가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5531f-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="5531f-106">토폴로지가 만들어지고 게시 되기 전에 중앙 관리 서버를 설정 하려면 <STRONG>set-CSConfigurationStoreLocation</STRONG>를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5531f-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="5531f-107">중앙 관리 서버를 선택 하려면</span><span class="sxs-lookup"><span data-stu-id="5531f-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="5531f-108">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5531f-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="5531f-109">Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5531f-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5531f-110">중앙 관리 서버 창에서 중앙 관리 서버를 설치할 프런트 엔드 서버를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5531f-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

