---
title: 모범 사례 분석기를 사용 하 여 배포를 검사 하 여 잠재적인 문제 해결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="5b28a-102">모범 사례 분석기를 사용 하 여 Lync Server 2013 배포를 검사 하 여 잠재적인 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5b28a-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b28a-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5b28a-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5b28a-104">모범 사례 분석기 검사를 실행 하려면 다음을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="5b28a-105">**자격 증명**   검사를 실행 하려면 로컬 관리자 그룹의 구성원 인 계정을 사용 하 여 모범 사례 분석기가 설치 된 컴퓨터에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="5b28a-106">또한 적절 한 검사를 실행 하는 데 필요한 사용자 권한 및 사용 권한이 있는 사용자 계정을 사용 하 여 로그온 해야 하며 모범 사례 분석기를 실행할 때 적절 한 사용자 권한 및 사용 권한을 가진 자격 증명을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="5b28a-107">자세한 내용은 [Lync Server 2013의 모범 사례 분석기에 대 한 그룹 멤버 자격 및 사용자 권한 요구 사항을](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b28a-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="5b28a-108">**스캔 범위 검사**   범위를 지정 하려면 스캔 하려는 범주와 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="5b28a-109">Lync Server 환경의 특정 범주 내에 있는 모든 범주, 하나 이상의 범주 또는 하나 이상의 서버를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="5b28a-110">**검사 유형 현재**   상태 검사 검사는 사용 가능한 유일한 스캔 유형으로, 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="5b28a-111">상태 검사 검사는 범위에 지정 된 모든 서버에 대 한 오류, 경고 및 기타 정보를 포함 하는 보고서를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="5b28a-112">**네트워크 속도**   네트워크 속도 옵션에는 고속 LAN (100 mbps 이상), LAN (10mbps), 초고속 wan (1.5 mbps) 또는 wan (64 kbps)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="5b28a-113">검사를 완료 하는 데 예상 되는 시간은이 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="5b28a-114">이 설정은 시간 초과 기간을 설정 하는 데도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="5b28a-115">검색 하는 동안 모범 사례 분석기는 지정 된 시간 동안 서버 로부터 응답을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="5b28a-116">지정 된 시간 초과 기간 내에 응답을 받지 못하는 경우에는 검사의 다음 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="5b28a-117">느린 네트워크에서는 네트워크 대기 시간이 길어질 때이 지정 된 시간 초과 기간이 더 길어집니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="5b28a-118">이 매개 변수에 대 한 토폴로지에서 가장 느린 링크를 선택 하 여 도구가 시간을 너무 빨리 초과 하지 않도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="5b28a-119">Lync Server 2013 배포를 검사 하려면</span><span class="sxs-lookup"><span data-stu-id="5b28a-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="5b28a-120">로컬 관리자 그룹의 구성원 인 계정을 사용 하 여 모범 사례 분석기가 설치 된 컴퓨터에 로그온 하 고 다른 필수 사용자 권한이 있는 경우 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="5b28a-121">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync Server 2013**을 차례로 가리킨 다음 모범 **사례 분석기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="5b28a-122">**시작** 화면에서 **새 스캔에 대 한 옵션 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="5b28a-123">**Active directory에 연결** 페이지에서 **active directory 서버**에 지정 된 이름을 확인 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5b28a-124">컴퓨터에 로그온 하는 데 사용한 자격 증명을 사용 하 여 검사를 실행 하려면 **Active Directory 서버에 연결**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="5b28a-125">Active Directory 도메인 서비스, Edge Server 또는 Exchange Server에 사용할 다른 자격 증명을 지정 하려면 **고급 로그온 옵션 표시**를 클릭 하 고 별도의 자격 증명이 필요한 각 확인란을 선택 하 고 선택한 각 확인란에 대 한 자격 증명을 지정한 다음 **Active Directory 서버에 연결**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5b28a-126">검색을 시작 하기 전에 모범 사례 분석기는 지정 된 계정 자격 증명이 유효 하며 모범 사례 분석기에서 Active Directory 도메인 서비스에 연결할 수 있는지 확인 하는 네트워크 및 사용 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-126">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services.</span></span> <span data-ttu-id="5b28a-127">도구를 작업 그룹 서버에서 실행 하는 경우 도구는 주변 네트워크의 Edge 서버 (즉, 스캔에 포함 된 경우)에 연결할 수 있는지도 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-127">If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="5b28a-128">새 모범 **사례 스캔 시작** 페이지에서 스캔에 포함할 옵션을 선택 하 고 네트워크 속도를 지정한 다음 **스캔 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="5b28a-129">**검색 완료** 페이지에서 모범 **사례 검사 보고서 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="5b28a-130">**모범 사례 보고서 보기** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5b28a-131">서버 구성 요소로 구성 된 목록에서 보고서를 보려면 **목록 보고서**를 클릭 한 다음 **모든 문제점** 탭 또는 **정보 항목** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="5b28a-132">결과 종류별로 구성 된 계층적 목록으로 보고서를 보려면 **트리 보고서**를 클릭 한 다음 **자세히 보기** 탭 또는 **요약 보기** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="5b28a-133">다른 보고서를 보려면 **기타 보고서**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b28a-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5b28a-134">모범 사례 분석기 보고서 및 이들이 식별 하는 문제점에 대 한 자세한 내용은 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013에서 모범 사례 분석기를 사용 하 여 만든 보고서 보기 및 작업</A> 및 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync server 2013의 모범 사례 분석기에서 식별 된 문제 분석 및 해결</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b28a-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

