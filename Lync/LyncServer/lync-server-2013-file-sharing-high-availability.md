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
ms.openlocfilehash: f67fc8cfffc0b5dbecaf6da212b3a8e5414b18ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a><span data-ttu-id="74040-102">Lync Server 2013에서 파일 공유 고가용성</span><span class="sxs-lookup"><span data-stu-id="74040-102">File sharing high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74040-103">_**마지막으로 수정한 주제:** 2012-03-30_</span><span class="sxs-lookup"><span data-stu-id="74040-103">_**Topic Last Modified:** 2012-03-30_</span></span>

<span data-ttu-id="74040-104">단일 데이터 센터 내에서 Lync Server 파일 공유에 대 한 고가용성을 보장 하기 위해 DFS (분산 파일 시스템)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74040-104">To ensure high availability for Lync Server file sharing within a single data center, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="74040-105">DFS는 같은 데이터 센터 내에서 한 파일 서버에서 다른 파일로 장애 조치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="74040-105">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="74040-106">대규모 배포의 경우 DFS를 사용 하는 전용 파일 서버를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74040-106">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span>

<span data-ttu-id="74040-107">네트워크 크기와 원하는 복원 력 크기에 따라 한 쌍의 서버를 사용 하 여 사이트의 모든 파일 공유를 호스팅하거나 프런트 엔드 당 하나의 쌍을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74040-107">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>

<span data-ttu-id="74040-108">DFS는 게시 된 RTO (복구 시간 목표) 또는 RPO (복구 시점 목표) 약정 없이 최상의 파일 복제 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="74040-108">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="74040-109">DFS 서버 간의 장애 조치를 빠르게 완료 해야 하지만 데이터 복제 지연 때문에 장애 조치 발생 시 사용자가 진행 중인 작업을 계속할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74040-109">The failover between the DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>

<span data-ttu-id="74040-110">공유 하는 DFS와 데이터 저장소를 사용 하는 것이 중요 한 경우에는 4 시간 마다 자주 파일 공유를 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74040-110">If you use DFS and data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="74040-111">한 파일 공유가 다운 되 고 복제가 최신 상태가 아닌 경우 백업을 사용 하 여 실패 한 서버의 콘텐츠를 현재 사용할 수 없는 서버와 쌍을 이루는 다른 서버로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74040-111">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

