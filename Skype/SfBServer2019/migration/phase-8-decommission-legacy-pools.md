---
title: 8단계 레거시 풀 해제
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: 다음 항목에서는 DNS 항목 업데이트, 콘텐츠 관리 서버 이동, 풀 해제, 레거시 배포에서 서버 및 풀 비활성화 및 제거에 대한 지침을 제공합니다. 이 섹션에 나열된 모든 절차가 필수는 아닙니다. 사용할 해제 절차를 확인하려면 설명서를 확인하십시오.
ms.openlocfilehash: b1080c68e3b4075ce92aaef497854855135dc47d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113244"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="cbd81-105">8단계: 레거시 풀 해제</span><span class="sxs-lookup"><span data-stu-id="cbd81-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="cbd81-106">다음 항목에서는 DNS 항목 업데이트, 콘텐츠 관리 서버 이동, 풀 해제, 레거시 배포에서 서버 및 풀 비활성화 및 제거에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbd81-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="cbd81-107">이 섹션에 나열된 모든 절차가 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cbd81-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="cbd81-108">사용할 해제 절차를 확인하려면 설명서를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="cbd81-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="cbd81-109">서버 및 서버 역할 제거에 대한 날짜가 있지만 전체 문서와 배포를 해제하기 위한 단계별 가이드는 [Microsoft Lync Server](https://go.microsoft.com/fwlink/p/?linkId=246227)제거 및 서버 역할 제거를 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="cbd81-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="cbd81-110">레거시 환경을 해제하기 전에 Microsoft UCMA(Unified Communications Managed API) 응용 프로그램을 마이그레이션 및 업그레이드하는 데 대한 자세한 내용은 [UCMA 응용 프로그램:](/previous-versions/office/jj728782(v=office.15))동시 사용, 마이그레이션 및 업그레이드 시나리오를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbd81-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](/previous-versions/office/jj728782(v=office.15)).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="cbd81-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="cbd81-111">In this section</span></span>

> [<span data-ttu-id="cbd81-112">DNS SRV 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="cbd81-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="cbd81-113">레거시 설치 중앙 관리 서버를 비즈니스용 Skype 서버 2019로 이동</span><span class="sxs-lookup"><span data-stu-id="cbd81-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="cbd81-114">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="cbd81-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="cbd81-115">보관 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="cbd81-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="cbd81-116">모니터링 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="cbd81-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="cbd81-117">Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="cbd81-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="cbd81-118">백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="cbd81-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
