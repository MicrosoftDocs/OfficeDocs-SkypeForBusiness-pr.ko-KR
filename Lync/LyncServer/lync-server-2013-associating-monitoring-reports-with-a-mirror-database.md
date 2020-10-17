---
title: 'Lync Server 2013: 모니터링 보고서와 미러 데이터베이스 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655c6ec788b934a533295fee577e72febb7818de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527105"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="19aed-102">Lync Server 2013에서 모니터링 보고서와 미러 데이터베이스 연결</span><span class="sxs-lookup"><span data-stu-id="19aed-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19aed-103">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="19aed-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="19aed-104">모니터링 데이터베이스에 대 한 미러를 구성 하는 경우 장애 조치 (failover)가 발생 하는 경우 미러 데이터베이스가 기본 데이터베이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="19aed-105">그러나 Lync Server 모니터링 보고서를 사용 하는 경우 장애 조치 (failover)가 수행 되는 경우 모니터링 보고서가 미러 데이터베이스에 연결 되어 있지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="19aed-106">모니터링 보고서를 설치할 때 기본 데이터베이스의 위치만 지정 하기 때문입니다. 미러 데이터베이스의 위치를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="19aed-107">모니터링 보고서에서 미러 데이터베이스로 자동으로 장애 조치 (failover)를 수행 하려면 모니터링 보고서에 사용 되는 두 데이터베이스, 즉 통화 정보 레코드 데이터에 대 한 데이터베이스 및 기타 (QoE) 데이터)에 미러 데이터베이스를 "장애 조치 (failover) 파트너"로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="19aed-108">이 단계는 모니터링 보고서를 설치한 후에 수행 해야 합니다. 이러한 두 데이터베이스에서 사용 하는 연결 문자열 값을 수동으로 편집 하 여 장애 조치 (failover) 파트너 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="19aed-109">이렇게 하려면 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="19aed-110">Internet Explorer를 사용 하 여 **SQL Server Reporting Services** 홈 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="19aed-111">Reporting Services 홈 페이지 URL에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="19aed-112">**Http:** 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="19aed-113">Reporting Services가 설치 된 컴퓨터의 FQDN (정규화 된 도메인 이름) (예: **atl-sql-001.litwareinc.com**)입니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="19aed-114">문자열 \*\*/보고서 \_ \*\*</span><span class="sxs-lookup"><span data-stu-id="19aed-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="19aed-115">모니터링 보고서가 설치 되는 데이터베이스 인스턴스의 이름 (예: **은**)입니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="19aed-116">예를 들어 SQL Server Reporting Services가 컴퓨터 atl-sql-001.litwareinc.com에 설치 되어 있고 모니터링 보고서에 데이터베이스 인스턴스은가 사용 되는 경우 홈 페이지 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="19aed-117">Reporting Services 홈 페이지에 액세스 한 후에는 **Lyncserverreports**를 클릭 한 다음 **보고서 \_ 콘텐츠**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="19aed-118">그러면 Lync Server 모니터링 보고서에 대 한 **보고서 \_ 콘텐츠** 페이지로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="19aed-119">**보고서 \_ 콘텐츠** 페이지에서 **cdrdb** 데이터 원본을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="19aed-120">**Cdrdb** 페이지의 **속성** 탭에서 **연결 문자열**이라는 텍스트 상자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="19aed-121">현재 연결 문자열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="19aed-122">**데이터 원본 = (로컬) \\ 은, 초기 카탈로그 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="19aed-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="19aed-123">미러 데이터베이스에 대 한 서버 이름 및 데이터베이스 인스턴스를 포함 하도록 연결 문자열을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="19aed-124">예를 들어 서버 이름이 s s s-a s s-a s s-001이 고 미러 데이터베이스가은 인스턴스에 있는 경우 다음 구문을 사용 하 여 미러 데이터베이스를 지정 하려면 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="19aed-125">**장애 조치 (Failover) 파트너 = a-미러-001 \\ 은**</span><span class="sxs-lookup"><span data-stu-id="19aed-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="19aed-126">편집한 연결 문자열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="19aed-127">**데이터 원본 = (로컬) \\ 은; 장애 조치 (Failover) 파트너 = a-mirror-001 \\ 은; 초기 카탈로그 = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="19aed-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="19aed-128">연결 문자열을 업데이트 한 후 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="19aed-129">**Cdrdb** 페이지에서 \*\* \_ 콘텐츠 보고서\*\* 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="19aed-130">**Qmsdb** 데이터 원본을 클릭 하 고 QoE 데이터베이스에 대 한 연결 문자열을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="19aed-131">예제:</span><span class="sxs-lookup"><span data-stu-id="19aed-131">For example:</span></span>
    
    <span data-ttu-id="19aed-132">**데이터 원본 = (로컬) \\ 은; 장애 조치 (Failover) 파트너 = a-mirror-001 \\ 은; 초기 카탈로그 = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="19aed-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="19aed-133">**적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="19aed-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="19aed-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19aed-134">See Also</span></span>


[<span data-ttu-id="19aed-135">Lync Server 2013 모니터링 보고서 설치</span><span class="sxs-lookup"><span data-stu-id="19aed-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="19aed-136">Lync Server 2013에서 모니터링 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="19aed-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

