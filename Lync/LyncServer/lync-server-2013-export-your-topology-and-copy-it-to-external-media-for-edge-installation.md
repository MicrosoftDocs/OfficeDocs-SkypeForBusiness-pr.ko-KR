---
title: 토폴로지를 내보내고에 지 설치를 위해 외부 미디어에 복사
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 784ed29372b137d5d3f58d749a3660d11cbb55d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="347c7-102">Lync Server 2013 토폴로지를 내보내고에 지 설치를 위해 외부 미디어에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="347c7-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="347c7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="347c7-104">토폴로지를 게시 한 후에는 Lync Server 배포 마법사에서 중앙 관리 저장소 데이터에 액세스 하 여 서버에서 배포 프로세스를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="347c7-105">내부 네트워크에서는 서버에서 데이터를 직접 사용할 수 있지만 내부 도메인에 없는 에지 서버에서는 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="347c7-106">에 지 서버 배포에서 토폴로지 구성 데이터를 사용할 수 있도록 하려면 Lync Server Dep를 실행 하기 전에 토폴로지 데이터를 파일로 내보낸 다음 해당 파일을 외부 미디어 (예:에 지 서버에서 사용할 수 있는 USB 드라이브 또는 네트워크 공유)에 복사 해야 합니다. 에 지 서버에서 loyment 마법사를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="347c7-107">다음 절차를 사용하여 배포 중인 에지 서버에서 토폴로지 구성 데이터를 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="347c7-108">에 지 서버에 Lync Server 2013을 설치한 후에는 내부 네트워크의 관리 도구를 사용 하 여에 지 서버를 관리 하 여 배포의 모든에 지 서버로 구성을 자동으로 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="347c7-109">단, 인증서를 할당 및 설치 하 고 서비스를 중지 및 시작 하는 것은 모두에 지 서버에서 수행 해야 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="347c7-110">Lync Server 관리 셸을 사용하여 토폴로지 데이터를 에지 서버에서 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="347c7-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="347c7-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="347c7-112">Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="347c7-113">내보낸 파일을 외부 미디어(예: 배포하는 동안 에지 서버에서 사용할 수 있는 네트워크 공유나 USB 드라이브)에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="347c7-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

