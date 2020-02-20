---
title: 'Lync Server 2013: SQL Server Reporting Services 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3527e3abca5bb9d6fa953db59be902c0ee340721
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="e5db5-102">Lync Server 2013에 SQL Server Reporting Services 설치</span><span class="sxs-lookup"><span data-stu-id="e5db5-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5db5-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e5db5-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e5db5-104">Microsoft Lync Server 2013 모니터링 보고서를 사용 하려는 경우 (자세한 내용은이 설명서의 다음 섹션 참조) 먼저 SQL Server Reporting Services를 설치 해야 합니다. Reporting Services는 Microsoft SQL Server를 설치할 때와 동시에 또는 SQL Server가 설치 된 후에 언제 든 지 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="e5db5-105">SQL Server를 설치 하지 않은 경우이 설명서의 앞부분에 나와 있는 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="e5db5-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="e5db5-106">SQL Server를 설치할 때 기능 선택 페이지에서 Reporting Services를 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="e5db5-107">그러면 SQL Server Reporting Services가 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="e5db5-108">이미 SQL Server를 설치했지만 아직 SQL Server Reporting Services를 설치하지 않은 경우 필요에 따라 SQL Server 2008 R2 또는 SQL Server 2012의 적합한 지침에 따라 해당 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="e5db5-109">Reporting Services가 성공적으로 설치되었는지 확인하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="e5db5-110">Microsoft SQL Server 2008 R2를 실행하는 경우 **시작**, **모든 프로그램**, **Microsoft SQL Server 2008 R2**, **구성 도구**를 차례로 클릭한 후 **Reporting Services 구성 관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="e5db5-111">Microsoft SQL Server 2012를 실행하는 경우 **시작**, **모든 프로그램**, **Microsoft SQL Server 2012**, **구성 도구**를 차례로 클릭한 후 **Reporting Services 구성 관리자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="e5db5-p102">**Reporting Services 구성 연결** 대화 상자의 **서버 이름** 상자에 해당 서버 이름이 표시되었는지 확인하고 모니터링 데이터가 저장되는 SQL Server 인스턴스 이름이 **보고서 서버 인스턴스** 상자에 표시되는지 확인합니다. **연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="e5db5-114">Reporting Service 구성 관리자에서 보고서 서버 상태 창에 SQL Server Reporting Services가 설치 되었고 현재 보고 서비스가 실행 되 고 있는지 확인 하 고, 보고서 서버 상태가 **시작** 됨으로 표시 되 고 **시작** 단추를 사용할 수 없도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="e5db5-115">Reporting Service가 실행 되 고 있지 않으면 **시작** 을 클릭 하 여 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="e5db5-116">보고서 서버 데이터베이스 이름 레이블 옆에 데이터베이스가 나열되어 있지 않으면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="e5db5-117">Reporting Services 구성 관리자에서 **데이터베이스**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="e5db5-118">보고서 서버 데이터베이스 창에서 **데이터베이스 변경**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="e5db5-119">보고서 서버 데이터베이스 연결 마법사의 작업 창에서 **새 보고서 서버 데이터베이스 만들기**를 선택한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="e5db5-p104">보고서 서버 데이터베이스 구성 마법사의 데이터베이스 서버 창에서 **서버 이름**, **인증 유형** 및 **사용자 이름** 상자에 나열된 정보가 올바른지 확인합니다. **연결 테스트**를 클릭하여 데이터베이스 서버에 연결할 수 있는지 확인한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="e5db5-122">보고서 서버 데이터베이스 구성 마법사의 데이터베이스 창에서 **데이터베이스 이름**, **언어** 및 **보고서 서버 모드**의 기본값을 사용하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="e5db5-123">보고서 서버 데이터베이스 구성 마법사의 자격 증명 창에서 **인증 유형** 드롭다운 목록 및 **사용자 이름** 및 **암호** 상자에 올바른 정보가 나열되었는지 확인한 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="e5db5-124">보고서 서버 데이터베이스 구성 마법사의 요약 창에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="e5db5-125">보고서 서버 데이터베이스 구성 마법사의 진행률 및 마침 요약 창에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="e5db5-p105">Reporting Services URL이 구성되었는지 확인하려면 **웹 서비스 URL**을 클릭합니다. **보고서 서버 웹 서비스 URL** 제목 아래에 하나 이상의 URL이 나열되어 있습니다. 이러한 URL을 각각 클릭하여 SQL Server Reporting Services의 로컬 설치에 대한 홈 페이지에 연결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5db5-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

