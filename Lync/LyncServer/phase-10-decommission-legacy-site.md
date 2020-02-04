---
title: '10 단계: 레거시 사이트 서비스 해제'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="f0500-102">10 단계: 레거시 사이트 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="f0500-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0500-103">_**마지막으로 수정한 주제:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f0500-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f0500-104">다음 항목에서는 Office Communications Server 2007 R2의 레거시 배포에서 서버 및 풀을 비활성화 하거나 제거 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0500-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="f0500-105">이 섹션에 나열 된 절차 중 일부는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0500-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="f0500-106">각 항목의 정보를 읽고 사용할 역할 해제 프로시저를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0500-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f0500-107">전화 접속 회의를 위한 회의 디렉터리를 Lync Server 2013으로 가져온 경우, 풀을 서비스 해제 하기 전에 먼저 Lync Server 2013로 전화 회의 디렉터리 소유권을 전환 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0500-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="f0500-108">우선 회의 디렉터리 소유권을 전환 하지 않고 풀을 역할 해제 한 경우 마이그레이션된 모든 모임의 전화 접속 기능이 더 이상 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0500-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="f0500-109">이전 풀의 각 회의 디렉터리에 대해 소유권을 한 번씩 전환 하는 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0500-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f0500-110">레거시 환경을 서비스 해제 하기 전에 Microsoft 통합 커뮤니케이션 관리 API (사용자 MA) 응용 프로그램을 마이그레이션 및 업그레이드 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="f0500-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f0500-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f0500-111">In This Section</span></span>

  - [<span data-ttu-id="f0500-112">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="f0500-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="f0500-113">DNS SRV 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="f0500-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="f0500-114">서버 및 풀 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="f0500-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="f0500-115">BackCompatSite 제거</span><span class="sxs-lookup"><span data-stu-id="f0500-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

