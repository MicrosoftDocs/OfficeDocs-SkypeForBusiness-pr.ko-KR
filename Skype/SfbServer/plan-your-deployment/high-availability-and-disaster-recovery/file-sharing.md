---
title: 비즈니스용 Skype 서버에서 파일 공유 고가용성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: DFS를 사용하여 비즈니스용 Skype 서버에서 파일 공유의 고가용성을 보장하는 방법을 자세히 알아보고
ms.openlocfilehash: 4d443425f453d63694511d13c6d3a84893058daa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802898"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="4ad50-103">비즈니스용 Skype 서버에서 파일 공유 고가용성</span><span class="sxs-lookup"><span data-stu-id="4ad50-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="4ad50-104">DFS를 사용하여 비즈니스용 Skype 서버에서 파일 공유의 고가용성을 보장하는 방법을 자세히 알아보고</span><span class="sxs-lookup"><span data-stu-id="4ad50-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="4ad50-105">비즈니스용 Skype 서버 배포에서 파일 공유에 대한 고가용성을 보장하기 위해 DFS(분산 파일 시스템)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="4ad50-106">DFS는 한 파일 서버에서 동일한 데이터 센터 내에 있는 다른 파일 서버로의 장애 조치(failover)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="4ad50-107">대규모 배포의 경우 DFS를 사용하여 한 쌍으로 구성한 전용 파일 서버를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="4ad50-108">DFS에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384) Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="4ad50-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="4ad50-109">Windows Server 2008의 DFS에 대한 자세한 내용은 [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385) 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ad50-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="4ad50-110">네트워크 규모와 원하는 복원력 수준에 따라 한 쌍의 서버로 사이트의 모든 파일 공유를 호스팅할 수도 있고 프런트 엔드 풀당 한 쌍의 서버를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="4ad50-111">DFS는 공표된 RTO(복구 시간 목표) 또는 RPO(복구 시점 목표)가 없는 "최상의 노력" 파일 복제 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="4ad50-112">DFS 서버 간의 장애 조치(failover)는 빠르게 완료해야 하지만 데이터 복제 지연으로 인해 장애 조치(failover)가 발생할 때 사용자가 계속 진행되는 작업을 진행하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="4ad50-113">DFS를 사용하는 경우 파일 공유의 데이터 저장소가 중요한 경우 4~8시간마다와 같이 파일 공유를 자주 백업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="4ad50-114">한 파일 공유가 다운되고 복제가 최신 상태가 아닌 경우 백업을 사용하여 장애가 발생한 서버의 콘텐츠를 현재 사용할 수 없는 서버와 한 쌍으로 구성된 다른 서버로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad50-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

