---
title: 비즈니스용 Skype 서버에서 모니터링 보고서와 미러 데이터베이스 연결
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: '요약: 모니터링 보고서를 비즈니스용 Skype 서버에서 사용하는 미러 데이터베이스와 연결하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802168"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="7a391-103">비즈니스용 Skype 서버에서 모니터링 보고서와 미러 데이터베이스 연결</span><span class="sxs-lookup"><span data-stu-id="7a391-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="7a391-104">**요약:** 모니터링 보고서를 비즈니스용 Skype 서버에서 사용하는 미러 데이터베이스와 연결하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="7a391-105">미러 데이터베이스를 통해 보고서 모니터링</span><span class="sxs-lookup"><span data-stu-id="7a391-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="7a391-106">모니터링 데이터베이스에 대해 미러를 구성하는 경우 장애 조치(failover)가 발생하는 경우 해당 미러 데이터베이스가 기본 데이터베이스로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="7a391-107">그러나 비즈니스용 Skype 서버 모니터링 보고서를 사용하는 경우 장애 조치(failover)가 발생하면 모니터링 보고서가 미러 데이터베이스에 연결되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="7a391-108">이는 모니터링 보고서를 설치할 때 기본 데이터베이스의 위치만 지정하기 때문에 미러 데이터베이스의 위치를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="7a391-109">모니터링 보고서가 미러 데이터베이스에 대해 자동으로 장애 조치(failover)를 수행하려면 모니터링 보고서에서 사용되는 두 데이터베이스(통화 정보 기록 데이터용 데이터베이스 하나와 QoE(QoE)에 대한 다른 데이터베이스)에 미러 데이터베이스를 "장애 조치(failover) 파트너"로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="7a391-110">이 단계는 모니터링 보고서를 설치한 후에 수행해야 합니다. 이러한 두 데이터베이스에서 사용하는 연결 문자열 값을 수동으로 편집하여 장애 조치 파트너 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="7a391-111">이렇게 하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="7a391-112">이 Internet Explorer **Reporting Services** SQL Server 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="7a391-113">Reporting Services 홈 페이지 URL에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="7a391-114">**http:** prefix.</span><span class="sxs-lookup"><span data-stu-id="7a391-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="7a391-115">Reporting Services가 설치된 컴퓨터의 FQDN(FQDN)(예: **atl-sql-001.litwareinc.com).**</span><span class="sxs-lookup"><span data-stu-id="7a391-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="7a391-116">문자열 **/Reports_.**</span><span class="sxs-lookup"><span data-stu-id="7a391-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="7a391-117">모니터링 보고서가 설치된 데이터베이스 인스턴스의 이름입니다(예: **보관).**</span><span class="sxs-lookup"><span data-stu-id="7a391-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="7a391-118">예를 들어 SQL Server Reporting Services가 컴퓨터에 설치되어 있으며 모니터링 보고서에서 atl-sql-001.litwareinc.com 인스턴스 보관을 사용하는 경우 홈 페이지 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="7a391-119">Reporting Services 홈 페이지에 액세스한 후 **ServerReports를** 클릭한 다음 이 **Reports_Content.**</span><span class="sxs-lookup"><span data-stu-id="7a391-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="7a391-120">비즈니스용 Skype 서버 **모니터링** 보고서에 Reports_Content 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="7a391-121">이 **Reports_Content** **CDRDB** 데이터 원본을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="7a391-122">**CDRDB** 페이지의 **속성** 탭에서 연결 문자열 레이블이 붙은 텍스트 **상자를 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="7a391-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="7a391-123">현재 연결 문자열은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="7a391-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="7a391-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="7a391-125">미러 데이터베이스의 서버 이름 및 데이터베이스 인스턴스를 포함하려면 연결 문자열을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="7a391-126">예를 들어 서버 이름이 atl-mirror-001인 경우 미러 데이터베이스가 보관 인스턴스에 있는 경우 다음 구문을 사용하여 미러 데이터베이스를 지정하기 위해 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="7a391-127">장애 조치 파트너=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="7a391-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="7a391-128">편집한 연결 문자열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="7a391-129">Data source=(local)\archinst; 장애 조치 파트너=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="7a391-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="7a391-130">연결 문자열을 업데이트한 후 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7a391-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="7a391-131">**CDRDB 페이지에서** Reports_Content **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7a391-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="7a391-132">**QMSDB 데이터** 원본을 클릭한 다음 QoE 데이터베이스에 대한 연결 문자열을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="7a391-133">예제:</span><span class="sxs-lookup"><span data-stu-id="7a391-133">For example:</span></span>
    
    <span data-ttu-id="7a391-134">Data source=(local)\archinst; 장애 조치 파트너=atl-mirror-001\archinst;초기 카탈로그=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="7a391-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="7a391-135">**적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7a391-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7a391-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a391-136">See also</span></span>

[<span data-ttu-id="7a391-137">비즈니스용 Skype 서버에 모니터링 보고서 설치</span><span class="sxs-lookup"><span data-stu-id="7a391-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="7a391-138">비즈니스용 Skype 서버에서 모니터링 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="7a391-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
