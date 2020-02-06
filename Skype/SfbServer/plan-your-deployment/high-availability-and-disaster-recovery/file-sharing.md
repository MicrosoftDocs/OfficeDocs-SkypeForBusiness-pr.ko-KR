---
title: 비즈니스용 Skype 서버에서 파일 공유 고가용성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
description: 비즈니스용 Skype 서버에서 DFS를 사용 하 여 파일 공유의 가용성을 확보 하는 방법에 대해 알아보세요.
ms.openlocfilehash: c04c3acd009dd59a3894a62d08395db19c6d2368
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815936"
---
# <a name="file-sharing-high-availability-in-skype-for-business-server"></a><span data-ttu-id="620f9-103">비즈니스용 Skype 서버에서 파일 공유 고가용성</span><span class="sxs-lookup"><span data-stu-id="620f9-103">File sharing high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="620f9-104">비즈니스용 Skype 서버에서 DFS를 사용 하 여 파일 공유의 가용성을 확보 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="620f9-104">Learn about ensuring high availability of your file shares in Skype for Business Server, using DFS.</span></span>
  
<span data-ttu-id="620f9-105">비즈니스용 Skype 서버 배포에서 파일 공유를 위한 고가용성을 보장 하기 위해 DFS (분산 파일 시스템)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-105">To ensure high availability for file sharing in your Skype for Business Server deployment, you can use the Distributed File System (DFS).</span></span> <span data-ttu-id="620f9-106">DFS는 같은 데이터 센터 내에서 한 파일 서버에서 다른 파일로 장애 조치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-106">DFS supports failover from one file server to another within the same data center.</span></span> <span data-ttu-id="620f9-107">대규모 배포의 경우 DFS를 사용 하는 전용 파일 서버를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-107">For a large scale deployment, we recommend that you use dedicated file servers that are paired using DFS.</span></span> <span data-ttu-id="620f9-108">Windows Server 2012의 DFS에 대 한 자세한 내용은을 [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="620f9-108">For more information on DFS in Windows Server 2012, see [https://go.microsoft.com/fwlink/?LinkId=524384](https://go.microsoft.com/fwlink/?LinkId=524384).</span></span> <span data-ttu-id="620f9-109">Windows Server 2008의 DFS에 대 한 자세한 내용은 [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="620f9-109">For information on DFS on Windows Server 2008, see [https://go.microsoft.com/fwlink/p/?LinkId=524385](https://go.microsoft.com/fwlink/p/?LinkId=524385).</span></span>
  
<span data-ttu-id="620f9-110">네트워크 크기와 원하는 복원 력 크기에 따라 한 쌍의 서버를 사용 하 여 사이트의 모든 파일 공유를 호스팅하거나 프런트 엔드 당 하나의 쌍을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-110">Depending on your network's size, and the amount of resiliency you want, you can use one pair of servers to host all file shares in a site, or use one pair per Front End pool.</span></span>
  
<span data-ttu-id="620f9-111">DFS는 게시 된 RTO (복구 시간 목표) 또는 RPO (복구 시점 목표) 약정 없이 최상의 파일 복제 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-111">DFS is a best effort file replication mechanism, with no published recovery time objective (RTO) or recovery point objective (RPO) commitment.</span></span> <span data-ttu-id="620f9-112">DFS 서버 간의 장애 조치를 빠르게 완료 해야 하지만 데이터 복제 지연으로 인해 장애 조치가 발생할 때 사용자가 진행 중인 작업을 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-112">A failover between DFS servers should be completed quickly, but data replication delay may prevent users from being able to continue work in progress when the failover happens.</span></span>
  
<span data-ttu-id="620f9-113">DFS를 사용 하는 경우 파일 공유에 있는 데이터 저장소가 중요 한 경우 4 시간에 한 번, 예를 들어 사용자를 자주 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-113">If you use DFS and the data store on the fileshare is critical, you should back up the file shares frequently, such as every 4 to 8 hours.</span></span> <span data-ttu-id="620f9-114">한 파일 공유가 다운 되 고 복제가 최신 상태가 아닌 경우 백업을 사용 하 여 실패 한 서버의 콘텐츠를 현재 사용할 수 없는 서버와 쌍을 이루는 다른 서버로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="620f9-114">When one file share goes down and replication is not up to date, you can use the backup to restore the content on the failed server to the other server that is paired with the server that is now unavailable.</span></span>
  

