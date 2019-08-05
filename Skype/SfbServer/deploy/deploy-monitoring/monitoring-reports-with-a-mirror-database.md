---
title: 비즈니스용 Skype 서버에서 모니터링 보고서와 미러 데이터베이스 연결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '요약: 비즈니스용 Skype 서버에서 사용 하는 미러 데이터베이스와 모니터링 보고서를 연결 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 0727a278b87edd0b3666b04d169dcd3460c8215c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186594"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="da197-103">비즈니스용 Skype 서버에서 모니터링 보고서와 미러 데이터베이스 연결</span><span class="sxs-lookup"><span data-stu-id="da197-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="da197-104">**요약:** 비즈니스용 Skype 서버에서 사용 하는 미러 데이터베이스와 모니터링 보고서를 연결 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="da197-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="da197-105">미러 데이터베이스로 보고서 모니터링</span><span class="sxs-lookup"><span data-stu-id="da197-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="da197-106">모니터링 데이터베이스에 대 한 미러를 구성 하는 경우 장애 조치 (failover)가 발생할 경우 미러 데이터베이스가 기본 데이터베이스로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="da197-107">그러나 비즈니스용 Skype 서버 모니터링 보고서를 사용 하는 경우 장애 조치가 발생 하는 경우 모니터링 보고서가 미러 데이터베이스에 연결 되지 않는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da197-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="da197-108">모니터링 보고서를 설치 하는 경우 기본 데이터베이스의 위치만 지정 하기 때문입니다. 미러 데이터베이스의 위치를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da197-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="da197-109">모니터링 보고서에서 미러 데이터베이스로 자동으로 장애 조치 (failover)를 받으려면 모니터링 보고서에 사용 되는 두 데이터베이스 (통화 정보 레코드 데이터에 대 한 데이터베이스 및 다른 품질의 경우)에 따라 미러 데이터베이스를 "장애 조치 (failover) 파트너"로 추가 해야 합니다. 체감 품질 (환경) 데이터).</span><span class="sxs-lookup"><span data-stu-id="da197-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="da197-110">모니터링 보고서를 설치한 후에는이 단계를 수행 해야 합니다. 이러한 두 데이터베이스에서 사용 하는 연결 문자열 값을 수동으로 편집 하 여 장애 조치 파트너 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da197-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="da197-111">이렇게 하려면 다음 절차를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="da197-112">Internet Explorer를 사용 하 여 **SQL Server Reporting Services** 홈 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="da197-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="da197-113">Reporting Services 홈 페이지 URL에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da197-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="da197-114">**Http:** prefix.</span><span class="sxs-lookup"><span data-stu-id="da197-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="da197-115">Reporting Services가 설치 된 컴퓨터의 FQDN (정규화 된 도메인 이름) (예: **atl-sql-001.litwareinc.com**)</span><span class="sxs-lookup"><span data-stu-id="da197-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="da197-116">문자열 **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="da197-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="da197-117">모니터링 보고서가 설치 된 데이터베이스 인스턴스의 이름입니다 (예: **archinst**).</span><span class="sxs-lookup"><span data-stu-id="da197-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="da197-118">예를 들어, SQL Server Reporting Services가 컴퓨터 atl-sql-001.litwareinc.com에 설치 되어 있고 모니터링 보고서가 데이터베이스 인스턴스 archinst를 사용 하는 경우 홈페이지 URL은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da197-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="da197-119">Reporting Services 홈 페이지에 액세스 한 후에는 **Serverreports**를 클릭 한 다음 **Reports_Content**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="da197-120">그러면 비즈니스용 Skype 서버 모니터링 보고서의 **Reports_Content** 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="da197-121">**Reports_Content** 페이지에서 **cdrdb** 데이터 원본을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="da197-122">**Cdrdb** 페이지의 **속성** 탭에서 **연결 문자열**이라는 레이블이 붙은 텍스트 상자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="da197-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="da197-123">현재 연결 문자열은 다음과 유사 하 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da197-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="da197-124">데이터 원본 = (로컬) \archinst, 초기 카탈로그 = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="da197-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="da197-125">연결 문자열을 편집 하 여 미러 데이터베이스의 서버 이름과 데이터베이스 인스턴스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="da197-126">예를 들어, 서버의 이름이 atl-001이 고 미러 데이터베이스가 archinst 인스턴스에 있으면이 구문을 사용 하 여 미러 데이터베이스를 지정 하기 위해 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="da197-127">장애 조치 파트너 = atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="da197-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="da197-128">편집한 연결 문자열은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da197-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="da197-129">데이터 원본 = (로컬) \archinst 장애 조치 (Failover) 파트너 = atl-mirror-001\archinst; 초기 카탈로그 = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="da197-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="da197-130">연결 문자열을 업데이트 한 후 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="da197-131">**Cdrdb** 페이지에서 **Reports_Content** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="da197-132">**Qmsdb** 데이터 원본을 클릭 한 다음 체감 품질 데이터베이스에 대 한 연결 문자열을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="da197-133">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da197-133">For example:</span></span>
    
    <span data-ttu-id="da197-134">데이터 원본 = (로컬) \archinst 장애 조치 (Failover) 파트너 = atl-mirror-001\archinst; 초기 카탈로그 = QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="da197-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="da197-135">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da197-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="da197-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da197-136">See also</span></span>

[<span data-ttu-id="da197-137">비즈니스용 Skype 서버에서 모니터링 보고서 설치</span><span class="sxs-lookup"><span data-stu-id="da197-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="da197-138">비즈니스용 Skype 서버에서 모니터링 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="da197-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
