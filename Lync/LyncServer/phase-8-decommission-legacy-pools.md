---
title: '8단계: 레거시 풀 해제'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9c21aa29f2e98aacd3ec68076a21ba2b4d2a76e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="4edf4-102">8단계: 레거시 풀 해제</span><span class="sxs-lookup"><span data-stu-id="4edf4-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4edf4-103">_**마지막으로 수정한 주제:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="4edf4-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="4edf4-104">다음 항목에서는 DNS 항목 업데이트, 콘텐츠 관리 서버 이동, 풀 서비스 해제, Lync Server 2010의 레거시 배포에서 서버 및 풀 비활성화 및 제거에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edf4-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="4edf4-105">이 섹션에 나열 된 절차 중 일부는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4edf4-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="4edf4-106">설명서를 읽고 사용할 서비스 해제 프로시저를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4edf4-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="4edf4-107">Lync Server 2010 서버 및 서버 역할 제거와 Lync Server 2010 배포를 해제 하는 방법에 대 한 단계별 가이드는 "Microsoft Lync Server 2010 제거 및 서버 역할 제거"를 참조 하 여에서 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4edf4-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4edf4-108">레거시 환경을 서비스 해제 하기 전에 Microsoft 통합 커뮤니케이션 관리 API (사용자 MA) 응용 프로그램을 마이그레이션 및 업그레이드 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="4edf4-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4edf4-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="4edf4-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="4edf4-110">DNS SRV 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="4edf4-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="4edf4-111">Lync Server 2010 중앙 관리 서버를 Lync Server 2013로 이동</span><span class="sxs-lookup"><span data-stu-id="4edf4-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="4edf4-112">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="4edf4-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="4edf4-113">보관 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="4edf4-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="4edf4-114">모니터링 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="4edf4-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="4edf4-115">Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="4edf4-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="4edf4-116">백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="4edf4-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

