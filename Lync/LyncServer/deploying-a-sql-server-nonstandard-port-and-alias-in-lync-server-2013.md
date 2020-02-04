---
title: Lync Server 2013에서 SQL Server 비표준 포트 및 별칭 배포
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
ms.openlocfilehash: fffa3502b04a9d05387cd94e157ed183e1fe32ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="bda7a-102">Lync Server 2013에서 SQL Server 비표준 포트 및 별칭 배포</span><span class="sxs-lookup"><span data-stu-id="bda7a-102">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bda7a-103">_**마지막으로 수정한 주제:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="bda7a-103">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="bda7a-104">Microsoft Lync Server 2013는 SQL Server에서 비표준 포트와 별칭 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-104">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="bda7a-105">SQL Server 비표준 포트와 별칭을 사용 하면 보안이 향상 되 고 Lync 배포에 보다 유연 하 게 환경이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-105">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="bda7a-106">이 단계는 Lync Server 2013 환경을 올바르게 보호 하는 단일 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-106">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="bda7a-107">Lync Server 2013 구현의 공격 허점을 줄이기 위해 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-107">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="bda7a-108">다음 문서는 Lync Server 2013에서 SQL Server 비표준 포트 및 별칭을 설정 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-108">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="bda7a-109">Lync Server 2013에서 SQL Server 비표준 포트 및 별칭 배포</span><span class="sxs-lookup"><span data-stu-id="bda7a-109">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="bda7a-110">Lync Server 2013 토폴로지 작성기는 Lync Server 2013을 구성할 때 실제 SQL Server FQDN 대신 FQDN (정규화 된 도메인 이름)으로 SQL Server 별칭을 사용 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-110">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="bda7a-111">이렇게 하면 악의적인 공격자의 실제 SQL Server FQDN을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-111">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="bda7a-112">또한 비표준 포트를 사용 하는 경우 다음 그림에 표시 된 대로 표준 포트 1433에서 데이터베이스를 공격 하려고 하는 공격자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-112">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="bda7a-113">![해커가 공격할 포트 번호를 알지 못합니다.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "해커가 공격할 포트 번호를 알지 못합니다.")</span><span class="sxs-lookup"><span data-stu-id="bda7a-113">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="bda7a-114">Lync Server 2013에서 SQL Server와 통신 하는 데 사용 하는 포트를 확인 하려면 공격자가 포트 정보를 얻기 위해 모든 포트를 검사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-114">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="bda7a-115">공격자에의 한 포트 검사는 보안이 명령을 감지 하 고 중지할 수 있는 가능성을 증대 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-115">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="bda7a-116">비표준 포트를 사용 하 여 증가 하는 보안을 추가 하는 것 외에도 SQL Server 별칭을 사용 하 여 배포에 유연성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-116">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="bda7a-117">이는 SQL Server 이름 변경이 필요한 상황에서 구성 변경 사항을 줄이기 위해 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-117">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bda7a-118">SQL Server는 두 가지 내결함성 방법 (장애 조치 클러스터링 및 미러링)을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-118">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="bda7a-119">Sql server 내결함성 메서드는 Lync Server 2013에서 SQL Server 비표준 포트와 별칭을 사용 하 여 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-119">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="bda7a-120">풀에서 사용 하는 SQL Server 백 엔드가 미러된 구성에 있는 경우 데이터베이스를 미러된 SQL로 장애 조치 할 때 프런트 엔드 서버에서 미러된 데이터베이스에 연결 하려면 SQL Server 백 엔드 서버의 SQL browser 서비스가 실행 되 고 있어야 합니다. Server.</span><span class="sxs-lookup"><span data-stu-id="bda7a-120">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="bda7a-121">토폴로지 작성기 내에서 SQL Server 데이터베이스 연결을 구성 하거나, 설치-CsDatabase cmdlet을 사용 하는 경우 SQL Server 비표준 포트 번호를 명시적으로 정의 하 고 SQL 인스턴스와 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-121">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="bda7a-122">비표준 포트를 설정 하려면 SQL Server 및 Windows Server 유틸리티를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-122">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="bda7a-123">Lync Server 2013에서 사용할 SQL Server 비표준 포트 및 별칭을 설정 하려면 세 가지 기본 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-123">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="bda7a-124">이러한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-124">These steps are:</span></span>

  - <span data-ttu-id="bda7a-125">Lync Server 2013에 최신 업데이트가 적용 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-125">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="bda7a-126">SQL Server 비표준 포트 및 별칭을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-126">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="bda7a-127">토폴로지 작성기를 사용 하 여 Lync Server 2013을 SQL Server 별칭으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-127">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="bda7a-128">토폴로지를 게시 하 고 데이터베이스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-128">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="bda7a-129">Lync Server 2013에 최신 업데이트가 적용 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="bda7a-129">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="bda7a-130">Lync Server 2013을 최신 상태로 유지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-130">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="bda7a-131">최신 업데이트 및 적용 방법에 대 한 정보를 확인 하려면 [Lync Server 2013 업데이트](http://support.microsoft.com/kb/2809243)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bda7a-131">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](http://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="bda7a-132">SQL Server 비표준 포트 및 별칭 설정</span><span class="sxs-lookup"><span data-stu-id="bda7a-132">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="bda7a-133">SQL Server 비표준 포트 및 별칭을 Lync Server 2013 토폴로지 작성기에서 참조할 수 있으려면 먼저 데이터베이스 인스턴스에서 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-133">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="bda7a-134">SQL Server 비표준 포트와 별칭을 설정 하려면 세 가지 주요 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-134">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="bda7a-135">이러한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-135">These steps are as follows:</span></span>

  - <span data-ttu-id="bda7a-136">기본 TCP/IP 프로토콜 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-136">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="bda7a-137">SQL Server 별칭을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-137">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="bda7a-138">DNS (도메인 이름 시스템) 정식 이름 (CNAME) 리소스 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-138">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="bda7a-139">**기본 TCP/IP 프로토콜 값 수정**</span><span class="sxs-lookup"><span data-stu-id="bda7a-139">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="bda7a-140">**시작**을 선택 하 고 다음 그림과 같이 **SQL Server 구성 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-140">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-141">![SQL Server Management Studio 아이콘](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 아이콘")</span><span class="sxs-lookup"><span data-stu-id="bda7a-141">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="bda7a-142">탐색 창에서 **sql server 인스턴스**확장을 선택 하 고, **sql server 네트워크 구성을**확장 하 고, 다음 그림과 같이 **인스턴스 이름 \<\>에 대 한 프로토콜**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-142">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-143">![TCP/IP 속성으로 이동](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "TCP/IP 속성으로 이동")</span><span class="sxs-lookup"><span data-stu-id="bda7a-143">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="bda7a-144">오른쪽 창에서 **tcp/ip**를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-144">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="bda7a-145">TCP/IP 속성 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-145">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="bda7a-146">**IP 주소** 탭을 선택 합니다. IP 주소 탭에는 서버의 모든 활성 IP 주소가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-146">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="bda7a-147">다음 그림에 표시 된 것과 같이, IP1 형식 (IP2, 최대 IPAll)으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-147">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-148">![TCP/IP 속성을 엽니다.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "TCP/IP 속성을 엽니다.")</span><span class="sxs-lookup"><span data-stu-id="bda7a-148">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="bda7a-149">모든 IP 주소에 대 한 **TCP 동적 포트** 필드를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-149">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="bda7a-150">필드에 0 문자가 포함 되어 있으면 SQL Server에서 동적 포트를 수신 대기 하 고 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-150">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="bda7a-151">이러한 필드는 지워지고 0이 포함 되어 있지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-151">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="bda7a-152">Lync Server에서 데이터베이스에 연결 하는 데 사용할 IP 주소의 경우 다음 그림과 같이 **사용 하도록** 설정 되어 있는지 확인 합니다 \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="bda7a-152">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-153">![올바른 IP에 대해 사용을 예로 설정합니다.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "올바른 IP에 대해 사용을 예로 설정합니다.")</span><span class="sxs-lookup"><span data-stu-id="bda7a-153">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="bda7a-154">대화 상자 아래쪽에 있는 **Ipall** 섹션에 다음 그림과 같이 **TCP 포트** 필드에 원하는 포트를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-154">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="bda7a-155">이 예제에서는 포트 50062를 사용 하지만 49152 및 65535 사이의 모든 포트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-155">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="bda7a-156">이 포트는 동적 및 사설 사용에 할당 되었으며,이는 Lync Server 2013 배포에 사용 되는 다른 포트와 충돌 하지 않도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-156">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="bda7a-157">![IPAll 섹션에서 포트를 설정합니다.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "IPAll 섹션에서 포트를 설정합니다.")</span><span class="sxs-lookup"><span data-stu-id="bda7a-157">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="bda7a-158">**확인** 을 선택 하 여 tcp/ip 속성 대화 상자를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-158">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="bda7a-159">Sql server 구성 관리자의 왼쪽 창에서 sql server **서비스** 를 선택 하 여 sql server 인스턴스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-159">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="bda7a-160">그런 다음 오른쪽 창에서 **SQL \<Server 인스턴스\> 이름을** 마우스 오른쪽 단추로 클릭 하 고 다음 그림과 같이 **다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-160">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-161">![인스턴스에 대한 SQL Server 서비스를 다시 설정합니다.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "인스턴스에 대한 SQL Server 서비스를 다시 설정합니다.")</span><span class="sxs-lookup"><span data-stu-id="bda7a-161">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bda7a-162">새 SQL Server 포트에 맞게 방화벽 설정을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-162">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="bda7a-163">**SQL Server 별칭 만들기 및 구성**</span><span class="sxs-lookup"><span data-stu-id="bda7a-163">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="bda7a-164">**시작**을 선택 하 고 다음 그림과 같이 **SQL Server 구성 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-164">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-165">![SQL Server Management Studio 아이콘](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio 아이콘")</span><span class="sxs-lookup"><span data-stu-id="bda7a-165">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="bda7a-166">왼쪽 창에서 **Sql Server 인스턴스**를 확장 하도록 선택 하 고, \*\* \<sql 네이티브 클라이언트 버전\> 구성을\*\*확장 하도록 선택한 후, 다음 그림과 같이 **별칭**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-166">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-167">![SQL Server 구성 관리자의 별칭](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 구성 관리자의 별칭")</span><span class="sxs-lookup"><span data-stu-id="bda7a-167">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="bda7a-168">**별칭**을 마우스 오른쪽 단추로 클릭 하 고 **새 별칭 ...** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-168">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="bda7a-169">다음 그림과 같이 **별칭 이름**, **포트 번호**, **프로토콜**, **서버**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-169">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-170">![새 별칭 만들기](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "새 별칭 만들기")</span><span class="sxs-lookup"><span data-stu-id="bda7a-170">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="bda7a-171">이전 단계에서 사용 했던 것과 동일한 비표준 포트 (SQL Server가 수신 대기 하는 포트)를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-171">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="bda7a-172">구성 된 별칭이 잘못 된 SQL Server FQDN 또는 인스턴스에 연결 되는 경우 연결 된 네트워크 프로토콜을 사용 하지 않도록 설정한 다음 다시 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-172">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="bda7a-173">이렇게 하면 캐시 된 연결 정보가 지워지고 클라이언트가 제대로 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-173">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="bda7a-174">**DNS CNAME 리소스 레코드 만들기**</span><span class="sxs-lookup"><span data-stu-id="bda7a-174">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="bda7a-175">DNS를 관리 하는 컴퓨터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-175">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="bda7a-176">**시작**을 선택 하 고 다음 그림과 같이 **서버 관리자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-176">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-177">![서버 관리자 열기](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "서버 관리자 열기")</span><span class="sxs-lookup"><span data-stu-id="bda7a-177">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="bda7a-178">다음 그림과 같이 **도구** 드롭다운을 선택 하 고 **DNS**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-178">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-179">![서버 관리자에서 DNS 열기](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "서버 관리자에서 DNS 열기")</span><span class="sxs-lookup"><span data-stu-id="bda7a-179">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="bda7a-180">왼쪽 창에서 서버 이름 노드를 확장 하 고 정방향 조회 영역 노드를 확장 한 다음 관련 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-180">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="bda7a-181">도메인을 마우스 오른쪽 단추로 클릭 하 고 다음 그림과 같이 **새 별칭 (CNAME) ...** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-181">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-182">![옵션을 선택하여 새 별칭 CNAME 만들기](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "옵션을 선택하여 새 별칭 CNAME 만들기")</span><span class="sxs-lookup"><span data-stu-id="bda7a-182">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="bda7a-183">다음 그림과 같이 **별칭 이름과** **SQL Server의 FQDN**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-183">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-184">![새 별칭 CNAME 대화 상자 채우기](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "새 별칭 CNAME 대화 상자 채우기")</span><span class="sxs-lookup"><span data-stu-id="bda7a-184">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="bda7a-185">**확인** 을 선택 하 여 CNAME을 저장 하 고 DNS 관리자에서 봅니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-185">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="bda7a-186">데이터베이스 연결 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="bda7a-186">Validate Database Connectivity</span></span>

<span data-ttu-id="bda7a-187">다양 한 방법으로 작동 하 고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-187">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="bda7a-188">SQL Server 데이터베이스에서 별칭을 사용 하 여 지정 된 포트를 수신 하 고 있는지 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-188">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="bda7a-189">빠른 검사는 **netstat** 및 **telnet** 명령을 사용 하 여 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-189">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bda7a-190">텔넷 클라이언트는 Windows Server와 함께 제공 되지만, 설치 해야 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-190">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="bda7a-191">서버 관리자를 열고 관리 메뉴에서 역할 및 기능 추가를 선택 하 여 Windows Server 기능을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-191">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="bda7a-192">**Netstat 및 telnet을 사용 하 여 데이터베이스 연결 확인**</span><span class="sxs-lookup"><span data-stu-id="bda7a-192">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="bda7a-193">**시작**을 선택 하 고 **cmd** 를 입력 하 여 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-193">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="bda7a-194">다음 그림과 같이 **netstat-a-f**를 입력 하 고 올바른 포트를 사용 하 여 SQL Server가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-194">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="bda7a-195">![netstat을 사용하여 포트 확인](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "netstat을 사용하여 포트 확인")</span><span class="sxs-lookup"><span data-stu-id="bda7a-195">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="bda7a-196">\*\*텔넷 \<\> \<별칭 이름 포트 \# \*\* 를 입력 하 여 SQL Server 인스턴스에 대 한 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-196">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="bda7a-197">연결에 성공 하면 telnet이 연결 되 고 오류가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-197">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="bda7a-198">이는 SQL Server 인스턴스가 올바른 별칭으로 올바른 포트를 수신 대기 하 고 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-198">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="bda7a-199">SQL Server 데이터베이스에 연결 하는 데 문제가 있는 경우 텔넷은 연결을 설정할 수 없다는 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-199">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="bda7a-200">데이터베이스 서버에서 데이터베이스 연결을 선택 했으므로 Lync Server (네트워크를 통해)에서 동일한 작업을 수행 하 고 방화벽에 대 한 액세스를 차단 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-200">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="bda7a-201">결론</span><span class="sxs-lookup"><span data-stu-id="bda7a-201">Conclusion</span></span>

<span data-ttu-id="bda7a-202">SQL Server 별칭을 구성한 후에는 토폴로지 작성기 도구를 사용 하 여 Lync Server 2013 토폴로지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda7a-202">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="bda7a-203">토폴로지에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bda7a-203">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bda7a-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bda7a-204">See Also</span></span>


<span data-ttu-id="bda7a-205">[](microsoft-lync-server-2013.md) 
[Lync server 2013의 보안을 위한](lync-server-2013-planning-for-security.md) Microsoft lync server 2013 계획</span><span class="sxs-lookup"><span data-stu-id="bda7a-205">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="bda7a-206">Lync Server 2013에서 토폴로지 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="bda7a-206">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="bda7a-207">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="bda7a-207">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

