---
title: 비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항
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
description: 요약:이 항목을 읽으면 비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 39204b675feff78fef56ee02e1c7e381eb36f65f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213234"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="be2ce-103">비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be2ce-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="be2ce-104">**요약:** 비즈니스용 Skype 서버 2015의 영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="be2ce-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="be2ce-105">영구 채팅 서버는 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition과 함께 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="be2ce-106">요구 사항은 설치한 비즈니스용 Skype 서버 2015 및 비즈니스의 성능 요구 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="be2ce-107">Enterprise Edition은 최대 8만 명의 동시 사용자를 지원할 수 있습니다. Standard Edition은 최대 2만 명의 동시 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="be2ce-108">영구 채팅은 프런트 엔드 구성 요소와 백 엔드 SQL 데이터베이스 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="be2ce-109">영구 채팅 서버를 배포 하기 전에 다음 하드웨어 및 소프트웨어 요구 사항이 충족 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="be2ce-110">비즈니스용 Skype 서버 2015, 영구 채팅 서버, 데이터베이스 서버 및 파일 서버를 지원 하기 위한 최소 요구 사항을 충족 하는 하드웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="be2ce-111">자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be2ce-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="be2ce-112">지원 되는 운영 체제 및 데이터베이스 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="be2ce-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="be2ce-113">지원 되는 운영 체제 및 데이터베이스 소프트웨어 및 Windows 업데이트 요구 사항에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be2ce-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="be2ce-114">비즈니스용 Skype 서버 2015 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="be2ce-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="be2ce-115">프런트 엔드 서버는 SIP (Session 착수 프로토콜) 라우팅의 기반 이며 영구 채팅 서버를 실행 하는 컴퓨터와 가능한 영구 채팅 기능을 사용 하 여 통신을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="be2ce-116">메시지 큐 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="be2ce-116">Message Queuing software.</span></span> <span data-ttu-id="be2ce-117">영구 채팅 서버 및 영구 채팅 준수 서비스 (배포 된 경우)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="be2ce-118">다음 섹션에서는 영구 채팅 서버 및 영구 채팅 데이터를 저장 하는 데이터베이스에 대 한 특정 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="be2ce-119">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="be2ce-120">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="be2ce-121">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be2ce-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="be2ce-122">영구 채팅을 사용 해야 하는 경우에는이 기능을 필요로 하는 사용자를 팀으로 마이그레이션하거나 비즈니스용 Skype 서버 2015을 계속 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="be2ce-123">프런트 엔드 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be2ce-123">Front End Server requirements</span></span>

<span data-ttu-id="be2ce-124">프런트 엔드 서버 요구 사항은 비즈니스용 Skype 서버 2015 Enterprise Edition 또는 Standard Edition에 영구 채팅 서버를 배포 하는 지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="be2ce-125">비즈니스용 Skype 서버 2015 Enterprise Edition과 영구 채팅 서버를 배포 하는 경우 Enterprise Edition 풀에 있는 하나 이상의 독립 실행형 컴퓨터에 영구 채팅 서버 프런트 엔드 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="be2ce-126">비즈니스용 Skype 서버 2015 프런트 엔드 서버에서는 영구 채팅 프런트 엔드 서버를 함께 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="be2ce-127">단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="be2ce-128">최대 4 개의 활성 프런트 엔드와 함께 영구 채팅 서버 풀을 사용 하 여 총 8만 동시 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="be2ce-129">비즈니스용 Skype 서버 2015 Standard Edition과 함께 영구 채팅 서버를 배포 하는 경우에는 프런트 엔드 서버와 영구 채팅을 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="be2ce-130">이 단일 서버 배포에서는 최대 2만 명의 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="be2ce-131">영구 채팅 서버 데이터베이스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be2ce-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="be2ce-132">영구 채팅 서버를 사용 하려면 대화방 기록과 콘텐츠, 구성 데이터, 사용자 프로 비전 데이터 및 기타 관련 메타 데이터를 저장 하는 SQL Server 데이터베이스 소프트웨어가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="be2ce-133">필요한 경우 영구 채팅 준수 데이터베이스를 사용 하 여 준수 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="be2ce-134">영구 채팅 데이터베이스는 동일한 SQL Server 또는 백 엔드 데이터베이스와 동일한 SQL 인스턴스에 배치 된 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="be2ce-135">최적의 성능을 보장 하기 위해 비즈니스용 Skype 서버 2015 Enterprise Edition과 함께 영구 채팅 서버를 설치 하는 경우에는 영구 채팅 파일 저장소를 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="be2ce-136">비즈니스용 Skype 서버 2015 Standard edition과 함께 영구 채팅 서버를 설치 하는 경우 로컬 SQL Server Express 인스턴스에 영구 채팅 저장소 백 엔드 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="be2ce-137">영구 채팅 데이터베이스 (mgc) 및 준수 데이터베이스 (mgccomp)는 동일한 SQL Server 인스턴스나 다른 SQL 서버에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="be2ce-138">데이터베이스 서버 플랫폼을 준비 하려면 각 컴퓨터가 하드웨어 요구 사항을 충족 하는지 확인 한 다음 필수 구성 요소 소프트웨어를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="be2ce-139">영구 채팅 데이터베이스 서버에 대 한 서버 플랫폼은 비즈니스용 Skype 서버 2015 백 엔드 데이터베이스 서버와 동일한 하드웨어를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="be2ce-140">자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be2ce-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="be2ce-141">데이터베이스 서버에서 다음 소프트웨어 응용 프로그램 중 하나가 설치 되어 있는지 확인해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="be2ce-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="be2ce-142">최신 서비스 팩을 포함 하는 Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="be2ce-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="be2ce-143">Microsoft SQL Server 2016 서비스 팩 1을 사용 하며, 비즈니스용 Skype 서버 누적 업데이트 7 이상 버전을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="be2ce-144">최신 서비스 팩이 적용 된 SQL Server 2016를 실행 하는 것이 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="be2ce-145">Microsoft SQL Server 2016을 설치 하는 방법에 대 한 자세한 내용은 [INSTALL SQL server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be2ce-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="be2ce-146">Microsoft SQL Server 2014 및 비즈니스용 Skype 서버 누적 업데이트 6 이상 버전에서 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="be2ce-147">최신 서비스 팩이 적용 된 SQL Server 2014를 실행 하는 것이 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="be2ce-148">Microsoft SQL Server 2014을 설치 하는 방법에 대 한 자세한 내용은 [INSTALL SQL server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be2ce-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](https://docs.microsoft.com/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="be2ce-149">Microsoft SQL Server 2012 (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="be2ce-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="be2ce-150">Microsoft SQL Server 2012을 설치 하는 방법에 대 한 자세한 내용은 [INSTALL SQL server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be2ce-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=248559).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="be2ce-151">영구 채팅 서버 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be2ce-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="be2ce-152">인증서 획득, SQL Server 데이터베이스 만들기 및 파일 저장소 만들기에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015](../../deploy/deploy.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="be2ce-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="be2ce-153">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="be2ce-153">For more information</span></span>

<span data-ttu-id="be2ce-154">하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be2ce-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="be2ce-155">비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be2ce-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="be2ce-156">비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항</span><span class="sxs-lookup"><span data-stu-id="be2ce-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
    

