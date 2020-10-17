---
title: Lync Server 2013에서 SQL Server 비표준 포트 및 별칭 배포
description: Lync Server 2013에 SQL Server 비표준 포트 및 별칭 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da76db2b946a47e13fe3549d7184b0b12894a83a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551234"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="0b0de-103">Lync Server 2013에서 SQL Server 비표준 포트 및 별칭 배포</span><span class="sxs-lookup"><span data-stu-id="0b0de-103">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b0de-104">_**마지막으로 수정 된 항목:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="0b0de-104">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="0b0de-105">Microsoft Lync Server 2013에서는 SQL Server에서 비표준 포트 및 별칭을 사용할 지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-105">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="0b0de-106">SQL Server 비표준 포트 및 별칭을 사용 하면 보안이 향상 되 고 Lync 배포를 위한 보다 유연한 환경이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-106">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="0b0de-107">이 단계는 Lync Server 2013 환경을 올바르게 보호 하는 단일 단계에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-107">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="0b0de-108">Lync Server 2013 구현의 공격 영역을 줄이기 위해 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-108">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="0b0de-109">다음 문서에서는 Lync Server 2013에서 SQL Server 비표준 포트 및 별칭을 설정 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-109">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="0b0de-110">Lync Server 2013에 SQL Server 비표준 포트 및 별칭 배포</span><span class="sxs-lookup"><span data-stu-id="0b0de-110">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="0b0de-111">Lync Server 2013 토폴로지 작성기는 Lync Server 2013을 구성할 때 실제 SQL Server FQDN 대신 FQDN (정규화 된 도메인 이름)으로 SQL Server 별칭을 사용 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-111">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="0b0de-112">이렇게 하면 악성 공격자 로부터 실제 SQL Server FQDN을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-112">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="0b0de-113">또한 비표준 포트를 사용 하는 경우의 실제 포트는 다음 그림과 같이 표준 포트 1433에서 데이터베이스 공격을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-113">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="0b0de-114">![해커는 공격할 포트 번호를 알지 못합니다.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "해커는 공격할 포트 번호를 알지 못합니다.")</span><span class="sxs-lookup"><span data-stu-id="0b0de-114">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="0b0de-115">Lync Server 2013가 SQL Server와 통신 하는 데 사용 하는 포트를 확인 하려면 공격자가 포트 정보를 가져오기 위해 모든 포트를 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-115">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="0b0de-116">공격자가 포트를 검색 하면 보안에서 명령을 검색 하 고 중지할 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-116">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="0b0de-117">비표준 포트를 사용 하 여 보안을 강화 하는 것 외에도 SQL Server 별칭을 사용 하 여 배포의 유연성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-117">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="0b0de-118">이는 SQL Server 이름을 변경 해야 하는 상황에서 구성 변경을 줄이기 위해 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-118">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b0de-119">SQL Server에서는 두 가지 내결함성 방법 (장애 조치 (Failover) 클러스터링 및 미러링)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-119">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="0b0de-120">두 SQL Server 내결함성 방법은 Lync Server 2013을 사용 하는 SQL Server 비표준 포트 및 별칭을 사용 하 여 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-120">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="0b0de-121">풀에서 사용 하는 SQL Server 백엔드가 미러링된 구성에 있는 경우 데이터베이스를 미러된 SQL Server로 장애 조치 (failover) 할 때 프런트 엔드 서버에서 sql Server 백 엔드 서버에 대해이 서비스를 실행 하 여 미러된 데이터베이스에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-121">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="0b0de-122">토폴로지 작성기 내에서 SQL Server 데이터베이스 연결을 구성 하거나 Install-CsDatabase cmdlet을 사용 하는 경우 SQL Server 비표준 포트 번호를 명시적으로 정의 하 여 SQL 인스턴스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-122">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="0b0de-123">비표준 포트를 설정 하려면 SQL Server 및 Windows Server 유틸리티를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-123">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="0b0de-124">Lync Server 2013에서 사용할 SQL Server 비표준 포트 및 별칭을 설정 하려면 세 가지 기본 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-124">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="0b0de-125">이러한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-125">These steps are:</span></span>

  - <span data-ttu-id="0b0de-126">Lync Server 2013에 최신 업데이트가 적용 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-126">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="0b0de-127">SQL Server 비표준 포트 및 별칭을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-127">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="0b0de-128">토폴로지 작성기를 사용 하 여 SQL Server 별칭으로 Lync Server 2013을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-128">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="0b0de-129">토폴로지를 게시 하 고 데이터베이스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-129">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="0b0de-130">Lync Server 2013에 최신 업데이트가 적용 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-130">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="0b0de-131">Lync Server 2013를 최신 상태로 유지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-131">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="0b0de-132">최신 업데이트를 확인 하 고 적용 하는 방법에 대 한 정보를 보려면 [업데이트에서 Lync Server 2013](https://support.microsoft.com/kb/2809243)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b0de-132">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="0b0de-133">SQL Server 비표준 포트 및 별칭 설정</span><span class="sxs-lookup"><span data-stu-id="0b0de-133">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="0b0de-134">Lync Server 2013 토폴로지 작성기에서 참조 하려면 먼저 SQL Server 비표준 포트 및 별칭을 데이터베이스 인스턴스에 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-134">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="0b0de-135">SQL Server 비표준 포트 및 별칭을 설정 하려면 세 가지 기본 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-135">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="0b0de-136">해당 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-136">These steps are as follows:</span></span>

  - <span data-ttu-id="0b0de-137">기본 TCP/IP 프로토콜 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-137">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="0b0de-138">SQL Server 별칭을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-138">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="0b0de-139">DNS (Domain Name System) 정식 이름 (CNAME) 리소스 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-139">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="0b0de-140">**기본 TCP/IP 프로토콜 값 수정**</span><span class="sxs-lookup"><span data-stu-id="0b0de-140">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="0b0de-141">**시작**을 선택 하 고 다음 그림과 같이 **SQL Server 구성 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-141">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-142">![SQL Server Management Studio 아이콘](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 아이콘")</span><span class="sxs-lookup"><span data-stu-id="0b0de-142">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="0b0de-143">탐색 창에서 **Sql server 인스턴스**를 확장 하도록 선택 하 고, **Sql server 네트워크 구성을**확장 하 고, 다음 \*\*에 대 한 \<instance name\> 프로토콜 \*\*을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-143">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-144">![TCP/IP 속성으로 이동](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "TCP/IP 속성으로 이동")</span><span class="sxs-lookup"><span data-stu-id="0b0de-144">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="0b0de-145">오른쪽 창에서 **tcp/ip**를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-145">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="0b0de-146">TCP/IP 속성 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-146">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="0b0de-147">**IP 주소** 탭을 선택 합니다. IP 주소 탭에는 서버의 모든 활성 IP 주소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-147">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="0b0de-148">다음 그림에 표시 된 것 처럼, IP1, IP2, IPAll 형식으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-148">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-149">![TCP/IP 속성을 엽니다.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "TCP/IP 속성을 엽니다.")</span><span class="sxs-lookup"><span data-stu-id="0b0de-149">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="0b0de-150">모든 IP 주소에 대해 **TCP 동적 포트** 필드를 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-150">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="0b0de-151">필드에 문자가 있으면 SQL Server에서 동적 포트를 수신 하 고 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-151">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="0b0de-152">이러한 필드는 지워지고 0이 포함 되어 있지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-152">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="0b0de-153">Lync Server에서 데이터베이스에 연결 하는 데 사용할 IP 주소에 대해 다음 그림과 같이 **Enabled** 가 **Yes**로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-153">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-154">![올바른 IP에 대해 Yes로 설정 사용](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "올바른 IP에 대해 Yes로 설정 사용")</span><span class="sxs-lookup"><span data-stu-id="0b0de-154">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="0b0de-155">대화 상자의 아래쪽에 있는 **Ipall** 섹션에서 다음 그림과 같이 **TCP 포트** 필드에 원하는 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-155">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="0b0de-156">이 예에서는 포트 50062를 사용 하지만 49152과 65535 사이에 아무 포트나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-156">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="0b0de-157">동적 및 개인 사용에 할당 된 포트 이며,이를 통해 Lync Server 2013 배포에서 사용 되는 다른 포트와 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-157">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="0b0de-158">![IPAll 섹션의 포트를 설정 합니다.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "IPAll 섹션의 포트를 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="0b0de-158">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="0b0de-159">**확인** 을 선택 하 여 tcp/ip 속성 대화 상자를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-159">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="0b0de-160">Sql server 구성 관리자의 왼쪽 창에서 **Sql Server 서비스** 를 선택 하 여 sql server 인스턴스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-160">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="0b0de-161">그런 다음 오른쪽 창에서 **SQL \<instance name\> Server** 를 마우스 오른쪽 단추로 클릭 하 고 다음 그림과 같이 **다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-161">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-162">![인스턴스에 대 한 SQL Server 서비스를 다시 설정 합니다.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "인스턴스에 대 한 SQL Server 서비스를 다시 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="0b0de-162">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0b0de-163">새 SQL Server 포트가 적용 되도록 방화벽 설정을 업데이트 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-163">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="0b0de-164">**SQL Server 별칭 만들기 및 구성**</span><span class="sxs-lookup"><span data-stu-id="0b0de-164">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="0b0de-165">**시작**을 선택 하 고 다음 그림과 같이 **SQL Server 구성 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-165">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-166">![SQL Server Management Studio 아이콘](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 아이콘")</span><span class="sxs-lookup"><span data-stu-id="0b0de-166">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="0b0de-167">왼쪽 창에서 **Sql Server 인스턴스**를 확장 하도록 선택 하 고, **sql Native Client \<version\> 구성을**확장 한 후에 다음 그림과 같이 **별칭**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-167">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-168">![SQL Server 구성 관리자의 별칭입니다.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 구성 관리자의 별칭입니다.")</span><span class="sxs-lookup"><span data-stu-id="0b0de-168">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="0b0de-169">**별칭**을 마우스 오른쪽 단추로 클릭 하 고 **새 별칭 ...** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-169">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="0b0de-170">다음 그림에 나와 있는 것 처럼 **별칭 이름**, **포트 번호**, **프로토콜**및 **서버**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-170">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-171">![새 별칭 만들기](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "새 별칭 만들기")</span><span class="sxs-lookup"><span data-stu-id="0b0de-171">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="0b0de-172">이전 단계에서 사용 했던 것과 동일한 비표준 포트 (즉, SQL Server가 수신 대기 하는 포트)를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-172">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="0b0de-173">구성 된 별칭이 잘못 된 SQL Server FQDN 또는 인스턴스에 연결 되는 경우 연결 된 네트워크 프로토콜을 사용 하지 않도록 설정한 다음 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-173">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="0b0de-174">이렇게 하면 캐시 된 연결 정보가 지워지고 클라이언트가 올바르게 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-174">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="0b0de-175">**DNS CNAME 리소스 레코드 만들기**</span><span class="sxs-lookup"><span data-stu-id="0b0de-175">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="0b0de-176">DNS를 관리 하는 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-176">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="0b0de-177">**시작**을 선택 하 고 다음 그림과 같이 **서버 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-177">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-178">![서버 관리자 열기](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "서버 관리자 열기")</span><span class="sxs-lookup"><span data-stu-id="0b0de-178">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="0b0de-179">**도구** 드롭다운을 선택 하 고 다음 그림과 같이 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-179">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-180">![서버 관리자에서 DNS를 엽니다.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "서버 관리자에서 DNS를 엽니다.")</span><span class="sxs-lookup"><span data-stu-id="0b0de-180">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="0b0de-181">왼쪽 창에서 서버 이름 노드, 정방향 조회 영역 노드를 차례로 확장 하 고 관련 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-181">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="0b0de-182">도메인을 마우스 오른쪽 단추로 클릭 하 고 다음 그림과 같이 **새 별칭 (CNAME) ...** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-182">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-183">![새 별칭 CNAME을 만들려면 옵션 선택](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "새 별칭 CNAME을 만들려면 옵션 선택")</span><span class="sxs-lookup"><span data-stu-id="0b0de-183">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="0b0de-184">다음 그림과 같이 **별칭 이름과** **SQL Server의 FQDN**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-184">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-185">![새 별칭 CNAME 대화 상자에 입력 합니다.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "새 별칭 CNAME 대화 상자에 입력 합니다.")</span><span class="sxs-lookup"><span data-stu-id="0b0de-185">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="0b0de-186">**확인** 을 선택 하 여 CNAME을 저장 하 고 DNS 관리자에서 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-186">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="0b0de-187">데이터베이스 연결 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0b0de-187">Validate Database Connectivity</span></span>

<span data-ttu-id="0b0de-188">다양 한 방법으로 작동 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-188">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="0b0de-189">SQL Server 데이터베이스가 별칭을 사용 하 여 지정 된 포트에서 수신 대기 하 고 있는지 확인 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="0b0de-189">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="0b0de-190">**Netstat** 및 **telnet** 명령을 사용 하 여 빠른 검사를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-190">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b0de-191">텔넷 클라이언트는 Windows Server와 함께 제공 되지만 반드시 설치 해야 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-191">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="0b0de-192">서버 관리자를 열고 관리 메뉴에서 역할 및 기능 추가를 선택 하 여 Windows Server 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-192">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="0b0de-193">**Netstat 및 텔넷을 사용 하 여 데이터베이스 연결 확인**</span><span class="sxs-lookup"><span data-stu-id="0b0de-193">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="0b0de-194">**시작**을 선택 하 고 **cmd** 를 입력 하 여 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-194">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="0b0de-195">다음 그림에 표시 된 대로 **netstat-a-f**를 입력 하 고 SQL Server가 올바른 포트로 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-195">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0b0de-196">![Netstat를 사용 하 여 포트 확인](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Netstat를 사용 하 여 포트 확인")</span><span class="sxs-lookup"><span data-stu-id="0b0de-196">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="0b0de-197">\*\* \<alias name\> Telnet \<port \#\> \*\* 을 입력 하 여 SQL Server 인스턴스에 대 한 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-197">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="0b0de-198">연결에 성공 하면 telnet이 연결 되 고 오류가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-198">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="0b0de-199">이는 SQL Server 인스턴스가 올바른 별칭을 사용 하 여 올바른 포트에서 수신 대기 하 고 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-199">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="0b0de-200">SQL Server 데이터베이스에 연결 하는 데 문제가 있는 경우 텔넷은 연결을 설정할 수 없다는 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-200">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="0b0de-201">데이터베이스 서버에서 데이터베이스 연결을 확인 했으므로 네트워크를 통해 Lync Server에서 같은 작업을 수행 하 고 방화벽에서 액세스를 차단 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-201">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="0b0de-202">결론</span><span class="sxs-lookup"><span data-stu-id="0b0de-202">Conclusion</span></span>

<span data-ttu-id="0b0de-203">SQL Server 별칭이 구성 된 후에는 토폴로지 작성기 도구에서이를 사용 하 여 Lync Server 2013 토폴로지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b0de-203">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="0b0de-204">토폴로지에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b0de-204">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b0de-205">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b0de-205">See Also</span></span>


<span data-ttu-id="0b0de-206">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  
 [Lync Server 2013의 보안 계획](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="0b0de-206">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="0b0de-207">Lync Server 2013에서 토폴로지 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="0b0de-207">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="0b0de-208">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="0b0de-208">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

