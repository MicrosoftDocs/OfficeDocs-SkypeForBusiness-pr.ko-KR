---
title: 모범 사례 분석기를 사용 하 여 배포에서 잠재적인 문제 검색
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f620712404fffe8e46f8f2a6f066c6ffa7b77d74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="24f95-102">모범 사례 분석기를 사용 하 여 Lync Server 2013 배포에서 잠재적인 문제를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24f95-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="24f95-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="24f95-104">모범 사례 분석기 검색을 실행하려면 다음을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="24f95-105">**자격 증명**   검사를 실행 하려면 로컬 Administrators 그룹의 구성원 인 계정을 사용 하 여 모범 사례 분석기가 설치 된 컴퓨터에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="24f95-106">또한 적절한 검색을 실행하는 데 필요한 사용자 권한 및 사용 권한이 있는 사용자 계정을 사용하여 로그온하거나, 모범 사례 분석기를 실행할 때 적절한 사용자 권한 및 사용 권한이 있는 자격 증명을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="24f95-107">자세한 내용은 [Lync Server 2013의 모범 사례 분석기에 대 한 그룹 구성원 자격 및 사용자 권한 요구 사항](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f95-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="24f95-108">**검사 범위 검사**   범위를 지정 하려면 검색할 범주 및 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="24f95-109">Lync Server 환경의 특정 범주에서 모든 범주, 하나 이상의 범주 또는 하나 이상의 서버를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="24f95-110">**검사 유형 현재**   상태 검사 검사는 사용 가능한 유일한 검사 유형으로, 기본적으로 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="24f95-111">상태 검사 검색에서는 범위에 지정된 모든 서버에 대한 오류, 경고 및 기타 정보를 포함하는 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="24f95-112">**네트워크 속도**   네트워크 속도 옵션에는 Fast LAN (100 mbps 이상), LAN (10mbps), 초고속 wan (1.5 Mbps) 또는 WAN (64 kbps)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="24f95-113">검색 완료 예상 시간은 이 설정을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="24f95-114">이 설정은 제한 시간을 설정할 때도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="24f95-115">검색 중에 모범 사례 분석기는 지정된 시간 동안 서버의 응답을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="24f95-116">지정된 제한 시간 내에 응답을 받지 못하면 모범 사례 분석기는 검색의 다음 서버로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="24f95-117">저속 네트워크에서는 네트워크 대기 시간이 더 길기 때문에 이를 반영하여 이 지정된 제한 시간이 더 깁니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="24f95-118">도구에서 너무 빨리 시간이 초과되지 않도록 이 매개 변수에 대해 토폴로지에서 속도가 가장 느린 링크를 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="24f95-119">Lync Server 2013 배포를 검색하려면</span><span class="sxs-lookup"><span data-stu-id="24f95-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="24f95-120">로컬 Administrators 그룹 구성원이며 기타 필요한 사용자 권한 및 사용 권한이 있는 계정을 사용하여 모범 사례 분석기가 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="24f95-121">**시작**을 클릭 하 고 **모든 프로그램**을 가리킨 다음 **Microsoft Lync Server 2013**, **모범 사례 분석기**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="24f95-122">**시작** 화면에서 **새 검색에 대한 옵션 선택**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="24f95-123">**Active Directory에 연결** 페이지에서 **Active Directory 서버**에 지정된 이름을 확인하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="24f95-124">컴퓨터에 로그온하는 데 사용한 자격 증명을 사용하여 검색을 실행하려면 **Active Directory 서버에 연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="24f95-125">Active Directory 도메인 서비스, 에지 서버 또는 Exchange 서버에 대해 사용할 각각 다른 자격 증명을 지정하려면 **고급 로그온 옵션 표시**를 클릭하고 별도의 자격 증명이 필요한 각 확인란을 선택한 다음, 선택한 각 확인란에 대해 자격 증명을 지정하고 **Active Directory 서버에 연결**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="24f95-p105">검색을 시작하기 전에 모범 사례 분석기는 네트워크 및 사용 권한 검사를 수행하여 지정된 계정 자격 증명이 유효하며 모범 사례 분석기가 Active Directory 도메인 서비스에 연결할 수 있는지를 확인합니다. 작업 그룹 서버에서 실행하는 경우 이 도구는 경계 네트워크의 에지 서버에 연결할 수 있는지(에지 서버가 검색에 포함되는지)도 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="24f95-128">**새 Best Practices 검색 시작** 페이지에서 검색에 포함할 옵션을 선택하고 네트워크 속도를 지정한 후에 **검색 시작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="24f95-129">**검색 완료** 페이지에서 **이 Best Practices 검색 보고서 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="24f95-130">**Best Practices 보고서 보기** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="24f95-131">서버 구성 요소로 구성된 목록에서 보고서를 보려면 **목록 보고서**를 클릭한 후 **모든 문제** 탭 또는 **정보 항목** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="24f95-132">결과 유형별로 구성된 계층적 목록으로 보고서를 보려면 **트리 보고서**를 클릭한 후 **자세히 보기** 탭 또는 **요약 보기** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="24f95-133">다른 보고서를 보려면 **기타 보고서**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="24f95-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="24f95-134">모범 사례 분석기 보고서 및 이들이 식별 하는 문제에 대 한 자세한 내용은 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013에서 모범 사례 분석기에서 만든 보고서를 보고 작업</A> 을 수행 하 고 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync Server 2013에서 모범 사례 분석기로 식별 된 문제를 분석 하 고 해결</A>합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="24f95-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

