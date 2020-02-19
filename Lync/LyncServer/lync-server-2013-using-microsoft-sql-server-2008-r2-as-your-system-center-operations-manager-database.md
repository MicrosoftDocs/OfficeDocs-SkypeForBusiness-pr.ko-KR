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
ms.openlocfilehash: 800da512c3cc9690c368c9d397774df0dea2d0e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database-for-lync-server-2013"></a><span data-ttu-id="f2cce-102">Lync Server 2013에 Microsoft SQL Server 2008 R2를 System Center Operations Manager 데이터베이스로 사용</span><span class="sxs-lookup"><span data-stu-id="f2cce-102">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2cce-103">_**마지막으로 수정 된 항목:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="f2cce-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="f2cce-104">SQL Server 2008 R2를 백 엔드 데이터베이스로 사용 하려면이 항목에서 설명 하는 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-104">To use SQL Server 2008 R2 as your back-end database, complete the steps detailed in this topic.</span></span>

<div>

## <a name="configuring-sql-server-2008-r2-and-sql-server-reporting-services"></a><span data-ttu-id="f2cce-105">SQL Server 2008 R2 및 SQL Server Reporting Services 구성</span><span class="sxs-lookup"><span data-stu-id="f2cce-105">Configuring SQL Server 2008 R2 and SQL Server Reporting Services</span></span>

<span data-ttu-id="f2cce-106">System Center Operations Manager 설치를 시작 하기 전에 SQL Server 2008 R2 및 SQL Server Reporting Services 구성에 대 한 두 가지 변경 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-106">Before you begin installing System Center Operations Manager you must make two changes to your SQL Server 2008 R2 and your SQL Server Reporting Services configuration.</span></span> <span data-ttu-id="f2cce-107">이러한 변경 내용은 SQL Server 2008 R2를 Operations Manager 데이터베이스로 사용 하는 경우에만 필요 합니다. 먼저 Operations Manager 데이터베이스를 호스트 하는 컴퓨터에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-107">(These changes are required only if you are using SQL Server 2008 R2 as your Operations Manager database.) First, do the following on the computer that will host your Operations Manager database:</span></span>

1.  <span data-ttu-id="f2cce-108">**시작**을 클릭하고 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-108">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="f2cce-109">**실행** 대화 상자에 **C\\: Program Files\\Microsoft SQL Server\\ atl-sc-001\_은\\Reporting Services\\ReportServer** 를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-109">In the **Run** dialog box, type **C:\\Program Files\\Microsoft SQL Server\\ MSRS10\_50.ARCHINST\\Reporting Services\\ReportServer** and then press ENTER.</span></span>

3.  <span data-ttu-id="f2cce-110">**ReportServer** 폴더에서 **Rsreportserver.config** 파일을 메모장 이나 다른 텍스트 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-110">In the **ReportServer** folder, open the file **rsreportserver.config** in Notepad or any other text editor.</span></span>

4.  <span data-ttu-id="f2cce-111">파일의 시작 부분에 일련의 "Add Key (키)" 노드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-111">Near the beginning of the file you will see a series of "Add Key" nodes.</span></span> <span data-ttu-id="f2cce-112">**Add Key = "secureconnectionlevel"을 입력 하 고 값을 0으로 설정 합니다. \<** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f2cce-112">Find the entry that begins **\<Add Key="SecureConnectionLevel"** and set the value to **0**:</span></span>
    
        <Add Key="SecureConnectionLevel" Value="0"/>

5.  <span data-ttu-id="f2cce-113">**Rsreportserver.config** 파일을 저장 하 고 텍스트 편집기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-113">Save the file **rsreportserver.config** and then close your text editor.</span></span>

<span data-ttu-id="f2cce-114">보고서 서버 구성 파일을 업데이트 한 후에는 SQL Server Reporting Services에 올바른 인증서를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-114">After updating the Report Server configuration file you must then assign the correct certificate to SQL Server Reporting Services.</span></span> <span data-ttu-id="f2cce-115">이렇게 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-115">To do that:</span></span>

1.  <span data-ttu-id="f2cce-116">**시작**, **모든 프로그램**, **Microsoft SQL Server 2008 R2**, **구성 도구**를 차례로 클릭 한 후 **Reporting Services 구성 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-116">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="f2cce-117">**Reporting Services 구성 연결** 대화 상자에서 서버 이름이 **서버 이름** 상자에 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-117">In the **Reporting Services Configuration Connection** dialog box, make sure that the name of your server appears in the **Server Name** box.</span></span> <span data-ttu-id="f2cce-118">**보고서 서버 인스턴스** 드롭다운 목록에서 Operations Manager 데이터베이스 (예: **은**)를 호스팅할 SQL Server 인스턴스를 선택 하 고 **연결**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-118">Select the SQL Server instance that will host your Operations Manager database (for example, **ARCHINST**) from the **Report Server Instance** drop-down list and then click **Connect**.</span></span>

3.  <span data-ttu-id="f2cce-119">Reporting Services 구성 관리자에서 **웹 서비스 URL**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-119">In Reporting Services Configuration Manager, click **Web Service URL**.</span></span>

4.  <span data-ttu-id="f2cce-120">**웹 서비스 URL** 페이지의 **SSL 인증서** 드롭다운 목록에서 Reporting Services에 사용할 인증서를 선택 하 고 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-120">On the **Web Service URL** page, select the certificate to be used for your Reporting Services from the **SSL Certificate** dropdown list and then click **Apply**.</span></span> <span data-ttu-id="f2cce-121">몇 초 후에는 **보고서 서버 웹 서비스 url**아래에 나열 된 한 쌍의 url이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-121">After a few seconds, you will see a pair of URLs listed under **Report Server Web Service URLs**.</span></span>

5.  <span data-ttu-id="f2cce-122">두 Url을 모두 클릭 하 여 SQL Server Reporting Services에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-122">Click both of the URLs to verify that you can access SQL Server Reporting Services.</span></span>

6.  <span data-ttu-id="f2cce-123">Reporting Services 구성 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-123">Close Reporting Services Configuration Manager.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-database-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="f2cce-124">SQL Server 2008 r 2에 사용할 System Center Operations Manager 데이터베이스 만들기</span><span class="sxs-lookup"><span data-stu-id="f2cce-124">Creating a System Center Operations Manager database for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="f2cce-125">System Center Operations Manager에서 SQL Server 2008 R2 데이터베이스를 사용 하도록 구성 하려면 SQL Server 2008 R2를 실행 하는 컴퓨터에 Operations Manager 데이터베이스를 "수동" 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-125">If you want to configure System Center Operations Manager to use a SQL Server 2008 R2 database, you will need to "manually" create the Operations Manager database on the computer running SQL Server 2008 R2.</span></span> <span data-ttu-id="f2cce-126">다시 말하지만, SQL Server 2005 또는 SQL Server 2008을 백 엔드 데이터베이스로 사용 하는 경우에는 이러한 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-126">(Again, these steps are not required if you are using SQL Server 2005 or SQL Server 2008 as your back-end database.)</span></span>

<span data-ttu-id="f2cce-127">Operations Manager 데이터베이스를 수동으로 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-127">To manually create an Operations Manager database do the following:</span></span>

1.  <span data-ttu-id="f2cce-128">System Center Operations Manager 2007 R2 설치 미디어의 SupportTools\\AMD64 폴더에서 **dbcreatewizard .exe**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-128">On the System Center Operations Manager 2007 R2 setup media, in the SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="f2cce-129">데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-129">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="f2cce-130">**데이터베이스 정보** 페이지에서 모든 설정을 그대로 유지 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-130">On the **Database Information** page leave all the settings as-is and then click **Next**</span></span>

4.  <span data-ttu-id="f2cce-131">관리 그룹 **구성** 페이지의 관리 **그룹 이름** 상자에 관리 그룹의 이름 (예: **Lync Server Monitoring**)을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-131">On the **Management Group Configuration** page type a name for your Management Group (for example, **Lync Server Monitoring**) in the **Management Group name** box and then click **Next**.</span></span>

5.  <span data-ttu-id="f2cce-132">**Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-132">On the **Operations Manager Error Reports** page click **Next**.</span></span>

6.  <span data-ttu-id="f2cce-133">**요약** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-133">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="creating-a-system-center-operations-manager-data-warehouse-for-use-with-sql-server-2008-r2"></a><span data-ttu-id="f2cce-134">SQL Server 2008 r 2에 사용할 System Center Operations Manager 데이터 웨어하우스 만들기</span><span class="sxs-lookup"><span data-stu-id="f2cce-134">Creating a System Center Operations Manager data warehouse for use with SQL Server 2008 R2</span></span>

<span data-ttu-id="f2cce-135">Microsoft Lync Server 2013은 다음과 같은 세 가지 새로운 System Center Operations Manager 보고서와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-135">Microsoft Lync Server 2013 ships with three new System Center Operations Manager reports:</span></span>

  - <span data-ttu-id="f2cce-136">**End to end Scenario availability report**   이 보고서는 등록 또는 현재 상태의 주요 Lync Server 서비스에 대 한 가용성/가동 시간을 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-136">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="f2cce-137">**용량 보고서**   이 보고서에서는 성능 카운터 정보를 사용 하 여 메모리 가용성 및 프로세서 사용량과 같은 시스템 구성 요소의 추세를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-137">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="f2cce-138">**구성 요소 보고서**   이 보고서에는 Lync Server 구성 요소별 그룹화 된 최상위 알림 생성기가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-138">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="f2cce-139">이러한 새 보고서를 사용 하려면 System Center Operations Manager 데이터 웨어하우스를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-139">In order to use these new reports you must install a System Center Operations Manager data warehouse.</span></span> <span data-ttu-id="f2cce-140">(데이터 웨어하우스는 장기 작업 데이터 저장소를 제공 합니다.) SQL Server 2008 R2에서 데이터 웨어하우스를 사용 하려면 SQL Server 데이터베이스를 호스팅하는 컴퓨터에서 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-140">(A data warehouse provides for long-term storage of operations data.) To use a data warehouse with SQL Server 2008 R2 you must carry out the following steps on the computer that hosts your SQL Server database:</span></span>

1.  <span data-ttu-id="f2cce-141">System Center Operations Manager 설치 미디어의 설치\\지원 도구\\AMD64 폴더에서 **dbcreatewizard .exe**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-141">On the System Center Operations Manager setup media, in the Setup\\SupportTools\\AMD64 folder, double-click **DBCreateWizard.exe**.</span></span>

2.  <span data-ttu-id="f2cce-142">데이터베이스 구성 마법사의 **데이터베이스 구성 마법사 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-142">In the Database Configuration Wizard, on the **Welcome to the Database Configuration Wizard** page, click **Next**.</span></span>

3.  <span data-ttu-id="f2cce-143">**데이터베이스 정보** 페이지의 **데이터베이스 유형** 드롭다운 목록에서 **Operations Manager 데이터 웨어하우스 데이터베이스** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-143">On the **Database Information** page, select **Operations Manager Data Warehouse Database** from the **Database Type** dropdown list and then click **Next**.</span></span>

4.  <span data-ttu-id="f2cce-144">**요약** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-144">On the **Summary** page click **Finish**.</span></span>

</div>

<div>

## <a name="installing-the-system-center-operations-manager-console"></a><span data-ttu-id="f2cce-145">System Center Operations Manager 콘솔 설치</span><span class="sxs-lookup"><span data-stu-id="f2cce-145">Installing the System Center Operations Manager console</span></span>

<span data-ttu-id="f2cce-146">Operations Manager 콘솔은 System Center Operations Manager를 관리 하는 데 사용 되는 기본 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-146">The Operations Manager console is the primary tool used to manage System Center Operations Manager.</span></span> <span data-ttu-id="f2cce-147">Operations Manager 콘솔을 설치 하기 전에 sql Server Reporting Service와 함께 지원 되는 버전의 SQL Server를 설치 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-147">Before you install the Operations Manager console, make sure that you have installed a supported version of SQL Server along with the SQL Server Reporting Service.</span></span> <span data-ttu-id="f2cce-148">또한 SQL Server의 Reporting Services 구성 관리자를 실행 하 여 Reporting Service가 올바르게 설치 및 구성 되었는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-148">It is also recommended that you run SQL Server's Reporting Services Configuration Manager to verify that the Reporting Service has been correctly installed and configured.</span></span>

<span data-ttu-id="f2cce-149">System Center Operations Manager 콘솔을 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="f2cce-149">To install the System Center Operations Manager console:</span></span>

1.  <span data-ttu-id="f2cce-150">System Center Operations Manager 설치 미디어에서 **setupom.exe**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-150">On the System Center Operations Manager setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="f2cce-151">System Center Operations Manager 2007 R2 설치에서 **필수 구성 요소 확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-151">In System Center Operations Manager 2007 R2 Setup, click **Check Prerequisites**.</span></span>

3.  <span data-ttu-id="f2cce-152">System Center Operations Manager 필수 구성 요소 보기에서 설치할 System Center components (**서버**;)를 선택 합니다. **콘솔**; 및 **PowerShell**)을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-152">In the System Center Operations Manager Prerequisite Viewer, select the System Center components to be installed: (**Server**; **Console**; and **PowerShell**) and then click **Check**.</span></span> <span data-ttu-id="f2cce-153">차단 문제가 보고 되지 않았는지 확인 하 고 **닫기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-153">Verify that no blocking issues have been reported and then click **Close**.</span></span> <span data-ttu-id="f2cce-154">차단 문제가 보고 된 경우 문제를 해결 한 다음 **확인** 을 클릭 하 여 필수 구성 요소 테스트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-154">If a blocking issue has been reported, correct the problem and then click **Check** to re-run the prerequisite testing.</span></span>

4.  <span data-ttu-id="f2cce-155">System Center Operations Manager 설치에서 **Operations Manager 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-155">In System Center Operations Manager Setup, click **Install Operations Manager**.</span></span>

5.  <span data-ttu-id="f2cce-156">System Center Operations Manager 설치 마법사의 **System Center Operations Manager 설치 마법사 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-156">In the System Center Operations Manager Setup wizard, on the **Welcome to the System Center Operations Manager Setup Wizard** page, click **Next**.</span></span>

6.  <span data-ttu-id="f2cce-157">**최종 사용자 사용권 계약** 페이지에서 **동의 함을** 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-157">On the **End-User License Agreement** page, select **I accept the terms in the license agreement** and then click **Next**.</span></span>

7.  <span data-ttu-id="f2cce-158">**제품 등록** 페이지의 **사용자 이름** 상자에 이름을 입력 하 고 **조직 상자의 이름**</span><span class="sxs-lookup"><span data-stu-id="f2cce-158">On the **Product Registration** page, type your name in the **User Name** box and name of your organization in the **Organization** box.</span></span> <span data-ttu-id="f2cce-159">**25 자리 CD 키 입력** 상자에 System Center Operations Manager 제품 키를 입력 하 고 **Next (다음**)를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-159">Type your System Center Operations Manager product key in the **Enter your 25 digit CD Key** box and then click **Next**.</span></span>

8.  <span data-ttu-id="f2cce-160">**사용자 지정 설치** 페이지에서 설치할 시스템 센터 옵션을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-160">On the **Custom Setup** page select the System Center options to be installed and then click **Next**.</span></span> <span data-ttu-id="f2cce-161">설치할 **관리 서버**, **사용자 인터페이스**및 **웹 콘솔** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-161">You should select **Management Server**, **User Interfaces**, and **Web Console** to be installed.</span></span> <span data-ttu-id="f2cce-162">**데이터베이스** 를 선택 하 여 설치 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-162">**Database** should not be selected and should not be installed.</span></span>

9.  <span data-ttu-id="f2cce-163">**SC 데이터베이스 서버 인스턴스** 페이지에서 Operations Manager 데이터베이스가 설치 된 컴퓨터의 이름이 **System Center 데이터베이스 서버** 상자에 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-163">On the **SC Database Server Instance** page, verify that the name of the computer where the Operations Manager databases are installed appears in the **System Center Database Server** box.</span></span> <span data-ttu-id="f2cce-164">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-164">Click **Next**.</span></span>

10. <span data-ttu-id="f2cce-165">**관리 서버 작업 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택 하 고 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-165">On the **Management Server Action Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="f2cce-166">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-166">Click **Next**.</span></span>

11. <span data-ttu-id="f2cce-167">**SDK 및 Config Service 계정** 페이지에서 **도메인 또는 로컬 컴퓨터 계정을** 선택 하 고 **사용자 계정**, **암호**및 **도메인 또는 로컬 컴퓨터** 상자에 적절 한 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-167">On the **SDK and Config Service Account** page, select **Domain or Local Computer Account** and then enter the appropriate values in the **User Account**, **Password**, and **Domain or local computer** boxes.</span></span> <span data-ttu-id="f2cce-168">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-168">Click **Next**.</span></span>

12. <span data-ttu-id="f2cce-169">**Operations Manager 오류 보고서** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-169">On the **Operations Manager Error Reports** page click **Next**.</span></span>

13. <span data-ttu-id="f2cce-170">**사용자 환경 개선 프로그램** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-170">On the **Customer Experience Improvement Program** page click **Next**.</span></span>

14. <span data-ttu-id="f2cce-171">**프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-171">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="f2cce-172">**System Center Operations Manager 설치 완료** 페이지에서 **암호화 키 백업** 및 **콘솔 시작 확인란** 선택을 취소 하 고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-172">On the **Completing the System Center Operations Manager Setup** page, clear the **Backup Encryption Key** and **Start the console checkboxes** and then click **Finish**.</span></span>

16. <span data-ttu-id="f2cce-173">System Center Operations Manager 설치에서 **끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-173">In System Center Operations Manager Setup click **Exit**.</span></span>

</div>

<div>

## <a name="installing-system-center-reporting-services"></a><span data-ttu-id="f2cce-174">System Center Reporting Services 설치</span><span class="sxs-lookup"><span data-stu-id="f2cce-174">Installing System Center Reporting Services</span></span>

<span data-ttu-id="f2cce-175">System Center Operations Manager 콘솔을 설치 및 구성한 후 System Center Reporting Services를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-175">After installing and configuring the System Center Operations Manager console you must then install System Center Reporting Services.</span></span> <span data-ttu-id="f2cce-176">SQL Server 2008 R2를 Operations Manager 백 엔드 데이터베이스로 사용 하는 경우에는 먼저 SQL Server Reporting Services와 연결 된 보안 그룹을 임시로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-176">If you are using SQL Server 2008 R2 as your Operations Manager back-end database, that means that you must first make a temporary change to the security group associated with SQL Server Reporting Services.</span></span> <span data-ttu-id="f2cce-177">SQL Server 2008 R2를 사용 하는 경우에는 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-177">If you are using SQL Server 2008 R2, you must do the following:</span></span>

1.  <span data-ttu-id="f2cce-178">**시작**을 클릭하고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-178">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="f2cce-179">서버 관리자에서 **구성**, **로컬 사용자 및 그룹**을 차례로 확장한 다음 **그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-179">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="f2cce-180">다음 그룹을 찾습니다. 여기서 atl-sc-a는 컴퓨터의 이름을 나타내고은는 System Center 데이터베이스에 대 한 SQL Server 인스턴스 **SQLServerReportServerUser $ atl-sc-001 $\_atl-sc-001 50은**를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-180">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the System Center database: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

4.  <span data-ttu-id="f2cce-181">그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-181">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="f2cce-182">그룹 이름에서 \*\* \_50\*\* 을 삭제 하 여 그룹 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-182">Rename the group by deleting **\_50** from the group name.</span></span> <span data-ttu-id="f2cce-183">예: **SQLServerReportServerUser $ atl-sc-001 $ atl-sc-001. 은**</span><span class="sxs-lookup"><span data-stu-id="f2cce-183">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

5.  <span data-ttu-id="f2cce-184">서버 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-184">Close Server Manager.</span></span>

<span data-ttu-id="f2cce-185">이 시점에 System Center Reporting Services를 설치할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-185">At this point you are ready to install System Center Reporting Services.</span></span> <span data-ttu-id="f2cce-186">이렇게 하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-186">To do this:</span></span>

1.  <span data-ttu-id="f2cce-187">System Center Operations Manager 2007 R2 설치 미디어에서 **setupom.exe**를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-187">On the System Center Operations Manager 2007 R2 Setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="f2cce-188">System Center Operations Manager 2007 R2 설치에서 **Operations Manager 보고 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-188">In System Center Operations Manager 2007 R2 Setup, click **Install Operations Manager Reporting**.</span></span>

3.  <span data-ttu-id="f2cce-189">System Center Operations Manager 2007 R2 Reporting 설치 마법사의 **Operations Manager Reporting 설치 시작** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-189">In the System Center Operations Manager 2007 R2 Reporting Setup wizard, on the **Welcome to Operations Manager Reporting Setup** page, click **Next**.</span></span>

4.  <span data-ttu-id="f2cce-190">**최종 사용자 사용권 계약** 페이지에서 **동의** 함을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-190">On the **End-user License Agreement** page select **I accept the terms of the license agreement** and then click **Next**.</span></span>

5.  <span data-ttu-id="f2cce-191">**제품 등록** 페이지에서 **사용자** 이름과 **조직 상자에 조직의 이름 및 이름이** 표시 되는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-191">On the **Product Registration** page, ensure that your name and the name of your organization appear in the **User Name** and **Organization** boxes and then click **Next**.</span></span>

6.  <span data-ttu-id="f2cce-192">**사용자 지정 설치** 페이지에서 **Reporting Server** 를 클릭 하 고 **이 구성 요소를 선택 하 고 모든 종속 구성 요소를 로컬 디스크 드라이브에 설치**합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-192">On the **Custom Setup** page, click **Reporting Server** and select **This component, and all dependent components, will be installed on local disk drive**.</span></span> <span data-ttu-id="f2cce-193">**데이터 웨어하우스** 를 클릭 하 고 **이 구성 요소를 사용할 수 없는**것을 선택한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-193">Click **Data Warehouse** and select **This component will not be available**, and then click **Next**.</span></span>

7.  <span data-ttu-id="f2cce-194">**루트 관리 서버에 연결** 페이지의 **루트 관리 서버** 상자에 Operations Manager 루트 관리 서버의 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-194">On the **Connect to the Root Management Server** page, type the name of your Operations Manager root management server in the **Root Management Server** box and then click **Next**.</span></span>

8.  <span data-ttu-id="f2cce-195">**Operations Manager 데이터 웨어하우스에 연결** 페이지에서 데이터 웨어하우스가 **sql server 인스턴스** 상자에 있는 sql server 인스턴스를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-195">On the **Connect to the Operations Manager Data Warehouse** page, type the SQL Server instance where your data warehouse is located in the **SQL Server Instance** box.</span></span> <span data-ttu-id="f2cce-196">(데이터 웨어하우스가 기본 인스턴스에 있는 경우에는 서버 이름 (예: atl-sql-dmo)을 입력 하면 됩니다.) 데이터베이스 이름 **OperationsManagerDW** 이 **이름** 상자에 나타나고 해당 포트 **1433** 이 **SQL Server 포트** 상자에 나타나는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-196">(If your data warehouse is located in the Default instance then simply type the server name; for example: atl-sql-001.) Verify that the database name **OperationsManagerDW** appears in the **Name** box, and that port **1433** appears in the **SQL Server port** box.</span></span> <span data-ttu-id="f2cce-197">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-197">Click **Next**.</span></span>

9.  <span data-ttu-id="f2cce-198">**Sql Server 보고 인스턴스** 페이지의 **Sql Server Reporting Services 서버 입력** 드롭다운 목록에서 sql server 보고 서버를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-198">On the **SQL Server Reporting Instance** page, select your SQL Server reporting server from the **Enter the SQL Server Reporting Services Server** dropdown list and then click **Next**.</span></span>

10. <span data-ttu-id="f2cce-199">**데이터 웨어하우스의 계정 쓰기** 페이지에서 **사용자 계정** 및 **암호** 상자에 데이터 웨어하우스에서 처음에 할당 될 사용자의 이름과 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-199">On the **Data Warehouse Write Account** page, enter the name and password of the user to be initially assigned write permissions to the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="f2cce-200">**도메인** 드롭다운 목록에서 사용자의 도메인을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-200">Select the user's domain from the **Domain** dropdown list and then click **Next**.</span></span>

11. <span data-ttu-id="f2cce-201">**데이터 판독기 계정** 페이지에 SQL Reporting Services에서 **사용자 계정** 및 **암호** 상자에 데이터 웨어하우스를 쿼리할 때 사용할 사용자 계정의 이름과 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-201">On the **Data Reader Account** page, enter the name and password of the user account to be used when SQL Reporting Services queries the data warehouse in the **User Account** and **Password** boxes.</span></span> <span data-ttu-id="f2cce-202">**도메인** 드롭다운 목록에서 계정 도메인을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-202">Select the account domain from the **Domain** dropdown list and then click **Next**.</span></span>

12. <span data-ttu-id="f2cce-203">**운영 데이터 보고서** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-203">On the **Operational Data Reports** page, click **Next**.</span></span>

13. <span data-ttu-id="f2cce-204">**Microsoft 업데이트** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-204">On the **Microsoft Update** page, click **Next**.</span></span>

14. <span data-ttu-id="f2cce-205">**프로그램 설치 준비 완료** 페이지에서 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-205">On the **Ready to Install the Program** page, click **Install**.</span></span>

15. <span data-ttu-id="f2cce-206">**Operations Manager Reporting Components 설치 마법사 완료** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-206">On the **Completing the Operations Manager Reporting Components Setup Wizard** page, click **Finish**.</span></span>

16. <span data-ttu-id="f2cce-207">System Center Operations Manager 2007 R2 설치에서 **끝내기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-207">In System Center Operations Manager 2007 R2 Setup, click **Exit**.</span></span>

<span data-ttu-id="f2cce-208">System Center 보고가 설치 된 후 다음 절차에 따라 SQL Server 보고와 연결 된 보안 그룹의 이름을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-208">After System Center reporting has been installed you then use the following procedure to reset the name of the security group associated with SQL Server reporting.</span></span> <span data-ttu-id="f2cce-209">이 절차는 SQL Server를 사용 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-209">Again, this procedure is only required if you are using SQL Server:</span></span>

1.  <span data-ttu-id="f2cce-210">**시작**을 클릭하고 **관리 도구**를 가리킨 다음 **서버 관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-210">Click **Start**, point to **Administrative Tools**, and then click **Server Manager**.</span></span>

2.  <span data-ttu-id="f2cce-211">서버 관리자에서 **구성**, **로컬 사용자 및 그룹**을 차례로 확장한 다음 **그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-211">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="f2cce-212">다음 그룹을 찾습니다. 여기서 atl-sc-a는 컴퓨터의 이름을 나타내고은은 보관 및 모니터링 데이터베이스에 대 한 SQL Server 인스턴스 **SQLServerReportServerUser $ atl-sc-001 $ atl-sc-001를 나타냅니다. 은**</span><span class="sxs-lookup"><span data-stu-id="f2cce-212">Locate the following group, where atl-sc-001 represents the name of your computer and ARCHINST represents the SQL Server instance for the archiving and monitoring databases: **SQLServerReportServerUser$atl-sc-001$MSRS10.ARCHINST**.</span></span>

4.  <span data-ttu-id="f2cce-213">그룹을 마우스 오른쪽 단추로 클릭 한 다음 **이름 바꾸기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-213">Right-click the group and then click **Rename**.</span></span> <span data-ttu-id="f2cce-214">그룹 이름 끝에 \*\* \_50\*\* 을 더하여 SQL Server 인스턴스 이름 바로 앞에 추가 하 여 그룹 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-214">Rename the group by adding **\_50** to the end of the group name, right before the SQL Server instance name.</span></span> <span data-ttu-id="f2cce-215">예: **SQLServerReportServerUser $ atl-sc-001 $ atl-sc-001\_50.은**</span><span class="sxs-lookup"><span data-stu-id="f2cce-215">For example: **SQLServerReportServerUser$atl-sc-001$MSRS10\_50.ARCHINST**.</span></span>

5.  <span data-ttu-id="f2cce-216">서버 관리자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-216">Close Server Manager.</span></span>

<span data-ttu-id="f2cce-217">System Center Operations 콘솔이 열려 있는 경우 응용 프로그램을 닫고 다시 시작 해야 합니다. 이 작업을 수행 하지 않으면 작업 콘솔 사용자 인터페이스에 **보고** 탭이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-217">If the System Center Operations Console is open you will need to close the application and then restart it; if you do not do this the **Reporting** tab will not appear in the Operations Console user interface.</span></span> <span data-ttu-id="f2cce-218">운영 콘솔을 처음 다시 시작한 후에는 모든 모니터링 보고서가 **보고** 탭에 표시 될 때까지 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cce-218">Note that, after restarting the Operations Console the first time, it could take several minutes before all the Monitoring Reports appear on the **Reporting** tab.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

