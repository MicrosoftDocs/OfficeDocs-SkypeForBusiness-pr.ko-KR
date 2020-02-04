---
title: 'Lync Server 2013: System Center Operations Manager 데이터베이스로 Microsoft SQL Server 2008 R2 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database
ms:assetid: 0efe76da-8854-499e-bdc7-3623244a8e85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687969(v=OCS.15)
ms:contentKeyID: 49733555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27516e7ca6c3fb70a01b7c1d245054d515ae351b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="e8c7e-102">Lync Server 2013의 System Center Operations Manager 데이터베이스로 Microsoft SQL Server 2008 R2를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="e8c7e-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8c7e-103">_**마지막으로 수정한 주제:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="e8c7e-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="e8c7e-104">백 엔드 데이터베이스로 SQL Server 2008 R2를 사용 하려면이 항목에서 설명 하는 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="e8c7e-105">SQL Server 2008 R2 및 SQL Server Reporting Services 구성</span><span class="sxs-lookup"><span data-stu-id="e8c7e-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="e8c7e-106">System Center Operations Manager 설치를 시작 하기 전에 SQL Server 2008 R2 및 SQL Server Reporting Services 구성에 대 한 두 가지 변경 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="e8c7e-107">이러한 변경 사항은 SQL Server 2008 R2를 Operations Manager 데이터베이스로 사용 하는 경우에만 필요 합니다. 먼저 Operations Manager 데이터베이스를 호스트 하는 컴퓨터에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="e8c7e-108">**시작** 을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="e8c7e-109">**실행** 대화 상자에 **C\\: Program Files\\Microsoft SQL Server\\ MSRS10\_50ARCHINST\\Reporting Services\\ReportServer** 를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="e8c7e-110">**ReportServer** 폴더에서 메모장 또는 다른 텍스트 편집기에서 **rsreportserver** 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="e8c7e-111">파일의 시작 부분 근처에 일련의 "키 추가" 노드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="e8c7e-112">키 추가를 시작 \*\*\*\* \*\* \<하는 항목을 찾아 "secureconnectionlevel"\*\* 을 입력 하 고 값을 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="e8c7e-113">**Rsreportserver** 파일을 저장 한 다음 텍스트 편집기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="e8c7e-114">보고서 서버 구성 파일을 업데이트 한 후에는 SQL Server Reporting Services에 올바른 인증서를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="e8c7e-115">실행할 작업</span><span class="sxs-lookup"><span data-stu-id="e8c7e-115">To do that:</span></span>

1.  <span data-ttu-id="e8c7e-116">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft SQL Server 2008 R2**, **구성 도구**를 차례로 클릭 한 다음 **Reporting Services 구성 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="e8c7e-117">**Reporting Services 구성 연결** 대화 상자의 **서버** 이름 상자에 서버 이름이 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="e8c7e-118">**보고서 서버 인스턴스** 드롭다운 목록에서 Operations Manager 데이터베이스 (예: **ARCHINST**)을 호스팅할 SQL Server 인스턴스를 선택한 다음 **연결**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="e8c7e-119">Reporting Services 구성 관리자에서 **웹 서비스 URL**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="e8c7e-120">**웹 서비스 URL** 페이지의 **SSL 인증서** 드롭다운 목록에서 보고 서비스에 사용할 인증서를 선택 하 고 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="e8c7e-121">몇 초 후에는 **보고서 서버 웹 서비스 url**아래에 나열 된 하나의 url이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="e8c7e-122">두 Url을 모두 클릭 하 여 SQL Server Reporting Services에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="e8c7e-123">Reporting Services 구성 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="e8c7e-124">SQL Server 2008 R2와 함께 사용할 System Center Operations Manager 데이터베이스 만들기</span><span class="sxs-lookup"><span data-stu-id="e8c7e-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="e8c7e-125">SQL Server 2008 R2 데이터베이스를 사용 하도록 System Center Operations Manager를 구성 하려면 SQL Server 2008 R2를 실행 하는 컴퓨터에서 Operations Manager 데이터베이스를 "수동으로 만들어야 합니다."가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="e8c7e-126">(이 단계는 SQL Server 2005 또는 SQL Server 2008를 백 엔드 데이터베이스로 사용 하는 경우에는 필요 하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="e8c7e-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="e8c7e-127">Operations Manager 데이터베이스를 수동으로 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="e8c7e-128">System Center Operations Manager 2007 R2 설치 미디어의 SupportTools\\AMD64 폴더에서 **dbcreatewizard. exe**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="e8c7e-129">데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="e8c7e-130">**데이터베이스 정보** 페이지에서 모든 설정을 그대로 두고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="e8c7e-131">관리 그룹 **구성** 페이지의 관리 그룹 **이름** 상자에 관리 그룹의 이름 (예: **Lync Server 모니터링**)을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="e8c7e-132">**Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="e8c7e-133">**요약** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="e8c7e-134">SQL Server 2008 R2와 함께 사용할 System Center Operations Manager 데이터 웨어하우스 만들기</span><span class="sxs-lookup"><span data-stu-id="e8c7e-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="e8c7e-135">Microsoft Lync Server 2013에는 다음과 같은 세 가지 새로운 System Center Operations Manager 보고서가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="e8c7e-136">**End to end 시나리오 가용성 보고서**   이 보고서에는 등록 또는 현재 상태와 같은 주요 Lync Server 서비스의 가용성/가동 시간이 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="e8c7e-137">**용량 보고서**   성능 카운터 정보를 사용 하 여이 보고서에는 메모리 가용성 및 프로세서 사용량 같은 시스템 구성 요소에 대 한 추세가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="e8c7e-138">**구성 요소 보고서**   이 보고서에는 Lync Server 구성 요소로 그룹화 된 최상위 알림 생성기가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="e8c7e-139">이러한 새 보고서를 사용 하기 위해서는 System Center Operations Manager 데이터 웨어하우스를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="e8c7e-140">(데이터 웨어하우스는 작업 데이터의 장기 저장소를 제공 합니다.) SQL Server 2008 R2에서 데이터 웨어하우스를 사용 하려면 SQL Server 데이터베이스를 호스트 하는 컴퓨터에서 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="e8c7e-141">System Center Operations Manager 설치 미디어의 설정\\supporttools\\AMD64 폴더에서 **dbcreatewizard. exe**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="e8c7e-142">데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="e8c7e-143">**데이터베이스 정보** 페이지의 **데이터베이스 유형** 드롭다운 목록에서 **Operations Manager 데이터 웨어하우스 데이터베이스** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="e8c7e-144">**요약** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="e8c7e-145">System Center Operations Manager 콘솔 설치</span><span class="sxs-lookup"><span data-stu-id="e8c7e-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="e8c7e-146">Operations Manager 콘솔은 System Center Operations Manager를 관리 하는 데 사용 되는 기본 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="e8c7e-147">Operations Manager 콘솔을 설치 하기 전에 SQL Server Reporting Services와 함께 지원 되는 버전의 SQL Server가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="e8c7e-148">또한 SQL Server의 Reporting Services 구성 관리자를 실행 하 여 보고 서비스가 올바르게 설치 및 구성 되었는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="e8c7e-149">System Center Operations Manager 콘솔을 설치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="e8c7e-150">System Center Operations Manager 설치 미디어에서 **SetupOM**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="e8c7e-151">System Center Operations Manager 2007 R2 설정에서 **필수 구성 요소 확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="e8c7e-152">System Center Operations Manager 필수 구성 요소 뷰어에서 설치할 System Center 구성 요소 (**서버**;)를 선택 합니다. **콘솔**; 및 **PowerShell**)을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="e8c7e-153">차단 문제가 보고 되지 않았는지 확인 한 다음 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="e8c7e-154">차단 문제가 보고 된 경우 문제를 해결 한 다음 **확인** 을 클릭 하 여 필수 구성 요소 테스트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="e8c7e-155">System Center Operations Manager 설치에서 **Operations Manager 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="e8c7e-156">System Center Operations Manager 설치 마법사의 **System Center Operations Manager 설치 마법사 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="e8c7e-157">**최종 사용자 사용권 계약** 페이지에서 **사용권 계약에 동의 함을** 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="e8c7e-158">**제품 등록** 페이지의 **사용자 이름** 상자에 이름을 입력 하 고 **조직** 상자에 조직의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="e8c7e-159">**25 자리 CD 키 입력** 상자에 System Center Operations Manager 제품 키를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="e8c7e-160">**사용자 지정 설정** 페이지에서 설치할 시스템 센터 옵션을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="e8c7e-161">설치할 **관리 서버**, **사용자 인터페이스**, **웹 콘솔** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="e8c7e-162">**데이터베이스** 를 선택 하 여 설치 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="e8c7e-163">**SC 데이터베이스 서버 인스턴스** 페이지에서 Operations Manager 데이터베이스가 설치 되어 있는 컴퓨터의 이름이 **System Center 데이터베이스 서버** 상자에 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="e8c7e-164">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-164">Click **Next**.</span></span>

10. <span data-ttu-id="e8c7e-165">**관리 서버 작업 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택한 다음 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="e8c7e-166">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-166">Click **Next**.</span></span>

11. <span data-ttu-id="e8c7e-167">**SDK 및 구성 서비스 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택한 다음 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="e8c7e-168">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-168">Click **Next**.</span></span>

12. <span data-ttu-id="e8c7e-169">**Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="e8c7e-170">**사용자 환경 개선 프로그램** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="e8c7e-171">**프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="e8c7e-172">**System Center Operations Manager 설치 완료** 페이지에서 **백업 암호화 키** 를 지우고 **콘솔 확인란을 시작한** 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="e8c7e-173">System Center Operations Manager 설치 **종료**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="e8c7e-174">System Center Reporting Services 설치</span><span class="sxs-lookup"><span data-stu-id="e8c7e-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="e8c7e-175">System Center Operations Manager 콘솔을 설치 하 고 구성한 후 System Center Reporting Services를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="e8c7e-176">SQL Server 2008 R2를 Operations Manager 백 엔드 데이터베이스로 사용 하는 경우 먼저 SQL Server Reporting Services와 연결 된 보안 그룹에 대 한 임시 변경 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="e8c7e-177">SQL Server 2008 R2를 사용 하는 경우 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="e8c7e-178">**시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="e8c7e-179">서버 관리자에서 **구성을**확장 하 고 **로컬 사용자 및 그룹**을 확장 한 다음 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="e8c7e-180">다음 그룹을 찾습니다. 여기서 atl-sc-001은 컴퓨터의 이름을 나타내고 ARCHINST는 System Center 데이터베이스에 대 한 SQL Server 인스턴스를 나타냅니다. **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="e8c7e-181">그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="e8c7e-182">그룹 이름에서 \*\* \_50\*\* 을 삭제 하 여 그룹의 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="e8c7e-183">예: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="e8c7e-184">서버 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-184">Close Server Manager.</span></span>

<span data-ttu-id="e8c7e-185">이 시점에서 System Center Reporting Services를 설치할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="e8c7e-186">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="e8c7e-186">To do this:</span></span>

1.  <span data-ttu-id="e8c7e-187">System Center Operations Manager 2007 R2 설치 미디어에서 **SetupOM**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="e8c7e-188">System Center Operations Manager 2007 R2 설정에서 **Operations Manager Reporting 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="e8c7e-189">System Center Operations Manager 2007 R2 Reporting 설치 마법사의 **Operations Manager Reporting Setup 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="e8c7e-190">**최종 사용자 사용권 계약** 페이지에서 **사용권 계약 조건에 동의 함을** 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="e8c7e-191">**제품 등록** 페이지에서 **사용자** 이름 및 **조직** 상자에 조직의 이름과 이름이 표시 되는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="e8c7e-192">**사용자 지정 설정** 페이지에서 **보고 서버** 를 클릭 하 고 **이 구성 요소와 모든 종속 구성 요소가 로컬 디스크 드라이브에 설치 됩니다**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="e8c7e-193">**데이터 웨어하우스** 를 클릭 하 고 **이 구성 요소를 사용할 수 없게 됨**을 선택한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="e8c7e-194">**루트 관리 서버에 연결** 페이지의 **루트 관리 서버** 상자에 Operations Manager 루트 관리 서버의 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="e8c7e-195">**Operations Manager 데이터 웨어하우스에 연결** 페이지에서 **sql server 인스턴스** 상자에 데이터 웨어하우스가 있는 sql server 인스턴스를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="e8c7e-196">(데이터 웨어하우스가 기본 인스턴스에 있는 경우 서버 이름을 입력 합니다 (예: atl--001).). **이름** 상자에 데이터베이스 이름 **OperationsManagerDW** 이 표시 되 고 해당 포트 **1433** 이 **SQL Server 포트** 상자에 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="e8c7e-197">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-197">Click **Next**.</span></span>

9.  <span data-ttu-id="e8c7e-198">**Sql Server 보고 인스턴스** 페이지의 **Sql Server reporting Services 서버** 드롭다운 목록에서 sql server reporting server를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="e8c7e-199">**데이터 웨어하우스 쓰기 계정** 페이지에서 **사용자 계정** 및 **암호** 상자에 데이터 웨어하우스에 대 한 쓰기 권한을 처음 할당할 사용자의 이름과 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="e8c7e-200">**도메인** 드롭다운 목록에서 사용자의 도메인을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="e8c7e-201">**데이터 읽기 프로그램 계정** 페이지에서 SQL Reporting Services **가 사용자 계정** 및 **암호** 상자에 데이터 웨어하우스를 쿼리할 때 사용할 사용자 계정의 이름과 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="e8c7e-202">**도메인** 드롭다운 목록에서 계정 도메인을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="e8c7e-203">**작업 데이터 보고서** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="e8c7e-204">**Microsoft 업데이트** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="e8c7e-205">**프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="e8c7e-206">**Operations Manager 보고 구성 요소 설정 마법사 완료** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="e8c7e-207">System Center Operations Manager 2007 R2 설정에서 **끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="e8c7e-208">System Center reporting을 설치한 후에는 다음 절차를 사용 하 여 SQL Server reporting에 연결 된 보안 그룹의 이름을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="e8c7e-209">이 절차는 SQL Server를 사용 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="e8c7e-210">**시작**을 클릭 하 고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="e8c7e-211">서버 관리자에서 **구성을**확장 하 고 **로컬 사용자 및 그룹**을 확장 한 다음 **그룹**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="e8c7e-212">다음 그룹을 찾습니다. 여기서 atl-sc-001은 컴퓨터의 이름을 나타내고 ARCHINST는 보관 및 모니터링 데이터베이스에 대 한 SQL Server 인스턴스를 나타냅니다. **SQLServerReportServerUser $ atl-sc-001 $ MSRS10. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="e8c7e-213">그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="e8c7e-214">그룹 이름 끝에 \*\* \_50\*\* 를 추가 하 여 그룹의 이름을 변경 하 고 SQL Server 인스턴스 이름 바로 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="e8c7e-215">예: **SQLServerReportServerUser $ atl-sc-001 $ MSRS10\_50. ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="e8c7e-216">서버 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-216">Close Server Manager.</span></span>

<span data-ttu-id="e8c7e-217">System Center Operations Console이 열려 있는 경우에는 응용 프로그램을 닫았다가 다시 시작 해야 합니다. 이 작업을 수행 하지 않으면 작업 콘솔 사용자 인터페이스에 **보고** 탭이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="e8c7e-218">처음으로 운영 콘솔을 다시 시작한 후에는 모든 모니터링 보고서가 **보고** 탭에 표시 되기까지 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c7e-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

