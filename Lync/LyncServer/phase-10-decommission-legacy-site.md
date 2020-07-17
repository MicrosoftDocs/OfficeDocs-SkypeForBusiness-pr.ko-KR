---
title: '단계 10: 레거시 사이트 해제'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d40c988822a27a34f148e4e1e7893a077965fcd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="ee870-102">단계 10: 레거시 사이트 해제</span><span class="sxs-lookup"><span data-stu-id="ee870-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee870-103">_**마지막으로 수정 된 항목:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="ee870-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="ee870-104">다음 항목에서는 Office Communications Server 2007 R2의 레거시 배포에서 서버 및 풀을 비활성화 하 고 제거 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee870-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="ee870-105">이 섹션에 나열된 모든 절차가 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ee870-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="ee870-106">사용할 해제 절차를 확인하려면 이러한 각 항목의 정보를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="ee870-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ee870-107">전화 접속 회의에 대 한 회의 디렉터리를 Lync Server 2013로 가져온 경우에는 풀 해제를 시작 하기 전에 전화 회의 디렉터리 소유권을 Lync Server 2013로 전환 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee870-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="ee870-108">먼저 회의 디렉터리 소유권을 전환하지 않고 풀을 해제할 경우 모든 마이그레이션된 모임에 대한 전화 접속 기능이 더 이상 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee870-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="ee870-109">레거시 풀에 있는 각 회의 디렉터리에 대해 소유권을 한 번 전환하는 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee870-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee870-110">레거시 환경을 제거 하기 전에 Microsoft 통합 커뮤니케이션 관리 API (c) 응용 프로그램을 마이그레이션 및 업그레이드 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="ee870-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee870-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ee870-111">In This Section</span></span>

  - [<span data-ttu-id="ee870-112">전화 회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="ee870-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="ee870-113">DNS SRV 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="ee870-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="ee870-114">서버 및 풀 해제</span><span class="sxs-lookup"><span data-stu-id="ee870-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="ee870-115">BackCompatSite 제거</span><span class="sxs-lookup"><span data-stu-id="ee870-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

