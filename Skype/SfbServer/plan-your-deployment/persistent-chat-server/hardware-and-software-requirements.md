---
title: 영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: '요약: 비즈니스용 Skype Server 2015에서 영구 채팅 서버의 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: cba3b340710e4c5ed041c085f39f1a4cc209a789
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815756"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="24f02-103">영구 채팅 서버에 대한 하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="24f02-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="24f02-104">**요약:** 이 항목에서는 비즈니스용 Skype Server 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="24f02-105">영구 채팅 서버는 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition과 함께 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="24f02-106">요구 사항은 설치 된 비즈니스용 Skype 서버 2015의 버전과 비즈니스의 성능 요구 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="24f02-107">Enterprise Edition은 최대 8만 동시 사용자를 지원할 수 있습니다. 스탠더드 버전은 최대 2만 동시 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="24f02-108">영구 채팅은 프런트 엔드 구성 요소 및 백 엔드 SQL 데이터베이스 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="24f02-109">영구 채팅 서버를 배포 하기 전에 다음 하드웨어 및 소프트웨어 요구 사항이 충족 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="24f02-110">비즈니스용 Skype 서버 2015, 영구 채팅 서버, 데이터베이스 서버, 파일 서버를 지원 하기 위한 최소 요구 사항을 충족 하는 하드웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="24f02-111">자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="24f02-112">지원 되는 운영 체제 및 데이터베이스 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="24f02-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="24f02-113">지원 되는 운영 체제 및 데이터베이스 소프트웨어 및 Windows 업데이트 요구 사항에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="24f02-114">비즈니스용 Skype 서버 2015 프런트 엔드 서버.</span><span class="sxs-lookup"><span data-stu-id="24f02-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="24f02-115">프런트 엔드 서버는 SIP (세션 초기화 프로토콜) 라우팅의 기반 이므로 영구 채팅 서버를 실행 하는 컴퓨터와 영구 채팅 기능을 통해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="24f02-116">메시지 대기열 소프트웨어.</span><span class="sxs-lookup"><span data-stu-id="24f02-116">Message Queuing software.</span></span> <span data-ttu-id="24f02-117">영구 채팅 서버와 영구 채팅 준수 서비스 (배포 된 경우)에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="24f02-118">다음 섹션에서는 영구 채팅 서버와 영구 채팅 데이터를 저장 하는 데이터베이스에 대 한 특정 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="24f02-119">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="24f02-120">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="24f02-121">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="24f02-122">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="24f02-123">프런트 엔드 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="24f02-123">Front End Server requirements</span></span>

<span data-ttu-id="24f02-124">프런트 엔드 서버 요구 사항은 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition과 영구 채팅 서버를 배포 하 고 있는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="24f02-125">비즈니스용 Skype Server 2015 Enterprise Edition을 사용 하 여 영구 채팅 서버를 배포 하는 경우 엔터프라이즈 버전 풀에 있는 하나 이상의 독립 실행형 컴퓨터에 영구 채팅 서버 프런트 엔드 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="24f02-126">비즈니스용 Skype 서버 2015 프런트 엔드 서버에서 영구 채팅 프런트 엔드 서버를 collocate 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="24f02-127">단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="24f02-128">최대 4 개의 활성 프론트 엔드와 영구 채팅 서버 풀을 사용 하 여 총 8만 동시 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="24f02-129">비즈니스용 Skype Server 2015 Standard Edition과 영구 채팅 서버를 배포 하는 경우 프런트 엔드 서버와 영구 채팅을 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="24f02-130">이 단일 서버 배포는 최대 2만 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="24f02-131">영구 채팅 서버 데이터베이스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="24f02-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="24f02-132">영구 채팅 서버에는 채팅방 기록과 콘텐츠, 구성 데이터, 사용자 프로 비전 데이터 및 기타 관련 메타 데이터를 저장 하는 SQL Server 데이터베이스 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="24f02-133">필요에 따라 지속적인 채팅 준수 데이터베이스를 사용 하 여 규정 준수 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="24f02-134">영구 채팅 데이터베이스는 동일한 SQL Server 또는 백 엔드 데이터베이스와 동일한 SQL 인스턴스에서 collocated 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="24f02-135">비즈니스용 Skype Server 2015 Enterprise Edition과 영구 채팅 서버를 설치 하는 경우 최적의 성능을 유지 하려면 영구 채팅 파일 저장소를 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="24f02-136">비즈니스용 Skype Server 2015 Standard edition과 영구 채팅 서버를 설치 하는 경우 로컬 SQL Server Express 인스턴스에서 영구 채팅 저장소 백 엔드 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="24f02-137">Mgc (지속적인 채팅 데이터베이스) 및 mgccomp (준수 데이터베이스)는 SQL Server의 동일한 인스턴스나 다른 SQL 서버에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="24f02-138">데이터베이스 서버 플랫폼을 준비 하려면 각 컴퓨터가 하드웨어 요구 사항을 충족 하는지 확인 한 다음 필수 구성 요소 소프트웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="24f02-139">영구 채팅 데이터베이스 서버의 서버 플랫폼에는 비즈니스용 Skype 서버 2015 백 엔드 데이터베이스 서버와 동일한 하드웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="24f02-140">자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="24f02-141">데이터베이스 서버에서 다음 소프트웨어 응용 프로그램 중 하나가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="24f02-142">최신 서비스 팩을 사용 하는 Microsoft SQL Server 2017.</span><span class="sxs-lookup"><span data-stu-id="24f02-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="24f02-143">Microsoft SQL Server 2016 (서비스 팩 1)에서는 비즈니스용 Skype Server 누적 업데이트 7 이상 버전으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="24f02-144">최신 서비스 팩을 사용 하 여 SQL Server 2016을 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="24f02-145">Microsoft SQL Server 2016을 설치 하는 방법에 대 한 자세한 내용은 [SQL server 2016 설치](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="24f02-146">Microsoft SQL Server 2014를 사용 하 고 있으며 비즈니스용 Skype Server 누적 업데이트 6 이상 릴리스에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="24f02-147">최신 서비스 팩을 사용 하 여 SQL Server 2014을 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="24f02-148">Microsoft SQL Server 2014을 설치 하는 방법에 대 한 자세한 내용은 [SQL server 2014 설치](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/pt-pt/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="24f02-149">Microsoft SQL Server 2012 (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24f02-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="24f02-150">Microsoft SQL Server 2012을 설치 하는 방법에 대 한 자세한 내용은 [SQL server 2012 설치](https://go.microsoft.com/fwlink/p/?LinkID=248559)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="24f02-151">영구 채팅 서버 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="24f02-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="24f02-152">인증서를 획득 하 고 SQL Server 데이터베이스를 만들고 파일 저장소를 만드는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015](../../deploy/deploy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="24f02-153">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="24f02-153">For more information</span></span>

<span data-ttu-id="24f02-154">하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f02-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="24f02-155">비즈니스용 Skype 서버 2015의 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="24f02-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="24f02-156">비즈니스용 Skype 서버 2015에 대한 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="24f02-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

