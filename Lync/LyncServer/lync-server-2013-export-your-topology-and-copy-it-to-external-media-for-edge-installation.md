---
title: 토폴로지 내보내기 및 에지 설치용 외부 미디어에 토폴로지 복사
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdd947287ec5b7fef90d27df6df2dd256481000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="ca2cf-102">Lync Server 2013 토폴로지 내보내기 및 에지 설치용 외부 미디어에 토폴로지 복사</span><span class="sxs-lookup"><span data-stu-id="ca2cf-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca2cf-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ca2cf-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ca2cf-104">토폴로지를 게시 한 후에는 Lync Server 배포 마법사에서 중앙 관리 저장소 데이터에 액세스 하 여 서버에서 배포 프로세스를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="ca2cf-105">내부 네트워크에서는 서버에서 직접 데이터를 사용할 수 있지만, 내부 도메인에 있지 않은 Edge 서버는 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="ca2cf-106">Edge 서버 배포에 대 한 토폴로지 구성 데이터를 사용 하려면 파일에 토폴로지 데이터를 내보낸 다음 외부 미디어 (예: Edge 서버에서 사용할 수 있는 USB 드라이브 또는 네트워크 공유)에 복사 하 여 Lync Server Dep를 실행 해야 합니다. Edge 서버의 loyment 마법사.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="ca2cf-107">배포 중인 Edge 서버에서 토폴로지 구성 데이터를 사용 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ca2cf-108">Edge 서버에 Lync Server 2013을 설치한 후에는 배포의 모든 Edge 서버로 구성을 자동으로 복제 하는 내부 네트워크의 관리 도구를 사용 하 여 Edge 서버를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="ca2cf-109">유일한 예외는 인증서를 할당 및 설치 하 고 서비스를 중지 하 고 시작 하는 것입니다 (둘 다 Edge 서버에서 수행 되어야 함).</span><span class="sxs-lookup"><span data-stu-id="ca2cf-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="ca2cf-110">Lync Server Management Shell을 사용 하 여 Edge 서버에서 토폴로지 데이터를 사용할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ca2cf-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="ca2cf-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ca2cf-112">Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="ca2cf-113">내보낸 파일을 외부 미디어 (예: 배포 중에 Edge 서버에서 사용 가능한 USB 드라이브 또는 네트워크 공유)에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca2cf-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

