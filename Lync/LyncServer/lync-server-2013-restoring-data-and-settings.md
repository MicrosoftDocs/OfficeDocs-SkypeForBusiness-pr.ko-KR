---
title: 'Lync Server 2013: 데이터 및 설정 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d34d62aa5a27a3f59bae0893c4004ca25c2cb039
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="5f9fe-102">Lync Server 2013에서 데이터 및 설정 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f9fe-103">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="5f9fe-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="5f9fe-104">페어링 된 풀을 사용 하 여 재해 복구 토폴로지를 구현 했으며 이러한 프런트 엔드 풀 중 하나가 다운 되어 사용자에 게 서비스를 빠르게 복원 해야 하는 경우 [Lync Server 2013에서 풀 장애 조치 (failover](lync-server-2013-failing-over-a-pool.md))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f9fe-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="5f9fe-105">그렇지 않은 경우에는 오류 또는 중단 후에 lync Server [2013의 백업 및 복원 워크시트](lync-server-2013-backup-and-restoration-worksheets.md)에 있는 워크시트와 함께 다음 항목의 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9fe-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f9fe-106">가동 중지 시간 및 잠재적인 데이터 손실을 줄이기 위해 문제 해결 절차가 효과적이 지 않은 경우에만이 문서에서 설명 하는 복원 절차를 수행 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f9fe-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="5f9fe-107">문제를 해결 하는 동안 다른 서버 및 구성 요소에 대 한 영향을 최소화 하 여 서버를 종료 하 고 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f9fe-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f9fe-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5f9fe-108">In This Section</span></span>

  - [<span data-ttu-id="5f9fe-109">Lync Server 2013 복원 준비</span><span class="sxs-lookup"><span data-stu-id="5f9fe-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="5f9fe-110">Lync Server 2013에서 Standard Edition server 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="5f9fe-111">Lync Server 2013에서 중앙 관리 저장소를 호스트 하는 서버 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="5f9fe-112">Lync Server 2013에서 Enterprise Edition 백 엔드 서버 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="5f9fe-113">Lync Server 2013에서 Enterprise Edition 구성원 서버 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="5f9fe-114">Lync Server 2013에서 Lync Server 풀 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="5f9fe-115">Lync Server 2013에서 ABC 프런트 엔드 풀 장애 조치 (failover) 수행</span><span class="sxs-lookup"><span data-stu-id="5f9fe-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="5f9fe-116">Lync Server 2013에서 파일 저장소 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="5f9fe-117">Lync Server 2013에서 모니터링 또는 보관 데이터 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="5f9fe-118">Lync Server 2013에서 영구 채팅 데이터 복원</span><span class="sxs-lookup"><span data-stu-id="5f9fe-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

