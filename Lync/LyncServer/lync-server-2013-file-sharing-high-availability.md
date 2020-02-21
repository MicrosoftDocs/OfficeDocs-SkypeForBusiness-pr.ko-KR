---
title: 'Lync Server 2013: 파일 공유 고가용성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40ec1c925ef2889b381c005918efbbb5e67c2f65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="8a334-102">Lync Server 2013의 파일 공유 고가용성</span><span class="sxs-lookup"><span data-stu-id="8a334-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a334-103">_**마지막으로 수정 된 항목:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="8a334-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="8a334-104">단일 데이터 센터 내에서 Lync Server 파일 공유에 대 한 고가용성을 보장 하기 위해 DFS (분산 파일 시스템)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a334-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="8a334-105">DFS는 한 파일 서버에서 동일한 데이터 센터 내에 있는 다른 파일 서버로의 장애 조치(failover)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8a334-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="8a334-106">대규모 배포의 경우 DFS를 사용하여 한 쌍으로 구성한 전용 파일 서버를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a334-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="8a334-107">네트워크 규모와 원하는 복원력 수준에 따라 한 쌍의 서버로 사이트의 모든 파일 공유를 호스팅할 수도 있고 프런트 엔드 풀당 한 쌍의 서버를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a334-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="8a334-p102">DFS는 공표된 RTO(복구 시간 목표) 또는 RPO(복구 시점 목표)가 없는 "최상의 노력" 파일 복제 메커니즘입니다. DFS 서버 간의 장애 조치는 신속하게 완료되겠지만 데이터 복제 지연으로 장애 조치 도중에 사용자가 작업을 계속 진행하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a334-p102">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment. The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="8a334-p103">DFS를 사용하고 있으며 파일 공유 데이터 저장소가 중요한 경우 파일 공유를 자주(예: 4~8시간마다) 백업해야 합니다. 한 파일 공유가 다운되고 복제가 최신 상태가 아닌 경우 백업을 사용하여 장애가 발생한 서버의 콘텐츠를 현재 사용할 수 없는 서버와 한 쌍으로 구성된 다른 서버로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a334-p103">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours. When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

