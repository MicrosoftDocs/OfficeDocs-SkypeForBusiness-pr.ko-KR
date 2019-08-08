---
title: 8 단계 레거시 풀 서비스 해제
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: 다음 항목에서는 DNS 항목 업데이트, 콘텐츠 관리 서버 이동, 풀 서비스 해제, 레거시 배포에서 서버 및 풀 비활성화 및 제거에 대 한 지침을 제공 합니다. 이 섹션에 나열 된 절차 중 일부는 필요 하지 않습니다. 설명서를 읽고 사용할 서비스 해제 프로시저를 결정 합니다.
ms.openlocfilehash: 5edad470bcd7bcf0340a311a890f73ef01645138
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237283"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="80b46-105">8 단계: 레거시 풀 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="80b46-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="80b46-106">다음 항목에서는 DNS 항목 업데이트, 콘텐츠 관리 서버 이동, 풀 서비스 해제, 레거시 배포에서 서버 및 풀 비활성화 및 제거에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b46-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="80b46-107">이 섹션에 나열 된 절차 중 일부는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80b46-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="80b46-108">설명서를 읽고 사용할 서비스 해제 프로시저를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80b46-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="80b46-109">서버와 서버 역할 제거에 대 한 자세한 내용 및 배포 서비스 해제에 대 한 단계별 가이드, [Microsoft Lync Server 제거 및 서버 역할 제거](https://go.microsoft.com/fwlink/p/?linkId=246227)에 대해 설명 하는 문서를 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="80b46-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="80b46-110">레거시 환경을 해제 하기 전에 Microsoft 통합 커뮤니케이션 관리 API (사용자 MA) 응용 프로그램을 마이그레이션 및 업그레이드 하는 방법에 대 한 자세한 내용은 (c) [응용 프로그램: 공존, 마이그레이션, 업그레이드 시나리오](https://go.microsoft.com/fwlink/p/?LinkId=269555)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80b46-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="80b46-111">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="80b46-111">In this section</span></span>

> [<span data-ttu-id="80b46-112">DNS SRV 레코드 업데이트</span><span class="sxs-lookup"><span data-stu-id="80b46-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="80b46-113">레거시 설치 중앙 관리 서버를 비즈니스용 Skype 서버 2019로 이동</span><span class="sxs-lookup"><span data-stu-id="80b46-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="80b46-114">회의 디렉터리 이동</span><span class="sxs-lookup"><span data-stu-id="80b46-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="80b46-115">보관 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="80b46-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="80b46-116">모니터링 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="80b46-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="80b46-117">Enterprise Edition 프런트 엔드 서버 또는 Standard Edition 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="80b46-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="80b46-118">백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="80b46-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

