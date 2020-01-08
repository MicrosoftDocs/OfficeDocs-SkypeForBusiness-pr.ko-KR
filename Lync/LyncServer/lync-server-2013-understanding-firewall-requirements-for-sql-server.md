---
title: 'Lync Server 2013: SQL Server에 대한 방화벽 요구 사항 이해'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="e5fab-102">Lync Server 2013의 SQL Server에 대한 방화벽 요구 사항 이해</span><span class="sxs-lookup"><span data-stu-id="e5fab-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5fab-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e5fab-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e5fab-104">스탠더드 버전 배포의 경우 방화벽 예외는 Lync Server 2013 설치 중에 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="e5fab-105">그러나 Enterprise Edition 배포의 경우 SQL Server 백 엔드 서버에서 방화벽 예외를 수동으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="e5fab-106">TCP/IP 프로토콜을 사용 하면 지정 된 IP 주소에 대해 주어진 포트를 한 번만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="e5fab-107">즉, SQL Server 기반 서버에서는 기본 TCP 포트 1433에 기본 데이터베이스 인스턴스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="e5fab-108">다른 경우에는 SQL Server 구성 관리자를 사용 하 여 고유 하 고 사용 하지 않는 포트를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="e5fab-109">이 항목에서는 다음에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-109">This topic covers:</span></span>

  - <span data-ttu-id="e5fab-110">기본 인스턴스를 사용 하는 경우 방화벽 예외에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fab-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="e5fab-111">SQL Server Browser 서비스의 방화벽 예외에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fab-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="e5fab-112">명명 된 인스턴스를 사용 하는 경우 정적 수신 대기 포트에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fab-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="e5fab-113">기본 인스턴스를 사용 하는 경우 방화벽 예외에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fab-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="e5fab-114">Lync Server 2013을 배포할 때 데이터베이스에 대해 SQL Server 기본 인스턴스를 사용 하는 경우 다음 방화벽 규칙 요구 사항을 사용 하 여 프런트 엔드 풀에서 SQL Server 기본 인스턴스로 통신 하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5fab-115">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="e5fab-115">Protocol</span></span></th>
<th><span data-ttu-id="e5fab-116">포트</span><span class="sxs-lookup"><span data-stu-id="e5fab-116">Port</span></span></th>
<th><span data-ttu-id="e5fab-117">지침</span><span class="sxs-lookup"><span data-stu-id="e5fab-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5fab-118">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="e5fab-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="e5fab-119">1433</span><span class="sxs-lookup"><span data-stu-id="e5fab-119">1433</span></span></p></td>
<td><p><span data-ttu-id="e5fab-120">SQL Server로의 인바운드</span><span class="sxs-lookup"><span data-stu-id="e5fab-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="e5fab-121">SQL Server Browser 서비스의 방화벽 예외에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fab-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="e5fab-122">SQL Server Browser 서비스는 데이터베이스 인스턴스를 찾고 인스턴스 (명명 된 또는 기본값)가 사용 하도록 구성 된 포트를 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5fab-123">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="e5fab-123">Protocol</span></span></th>
<th><span data-ttu-id="e5fab-124">포트</span><span class="sxs-lookup"><span data-stu-id="e5fab-124">Port</span></span></th>
<th><span data-ttu-id="e5fab-125">지침</span><span class="sxs-lookup"><span data-stu-id="e5fab-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5fab-126">UDP</span><span class="sxs-lookup"><span data-stu-id="e5fab-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="e5fab-127">1434</span><span class="sxs-lookup"><span data-stu-id="e5fab-127">1434</span></span></p></td>
<td><p><span data-ttu-id="e5fab-128">Ipsec</span><span class="sxs-lookup"><span data-stu-id="e5fab-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="e5fab-129">명명 된 인스턴스를 사용 하는 경우 정적 수신 대기 포트에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5fab-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="e5fab-130">Lync Server 2013을 지 원하는 데이터베이스용 SQL Server 구성에서 명명 된 인스턴스를 사용 하는 경우 SQL Server 구성 관리자를 사용 하 여 정적 포트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="e5fab-131">명명 된 각 인스턴스에 정적 포트를 할당 한 후에는 방화벽의 각 정적 포트에 대 한 예외를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5fab-132">프로토콜별</span><span class="sxs-lookup"><span data-stu-id="e5fab-132">Protocol</span></span></th>
<th><span data-ttu-id="e5fab-133">포트</span><span class="sxs-lookup"><span data-stu-id="e5fab-133">Port</span></span></th>
<th><span data-ttu-id="e5fab-134">지침</span><span class="sxs-lookup"><span data-stu-id="e5fab-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5fab-135">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="e5fab-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="e5fab-136">정적으로 정의 됨</span><span class="sxs-lookup"><span data-stu-id="e5fab-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="e5fab-137">Ipsec</span><span class="sxs-lookup"><span data-stu-id="e5fab-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="e5fab-138">SQL Server 설명서</span><span class="sxs-lookup"><span data-stu-id="e5fab-138">SQL Server Documentation</span></span>

<span data-ttu-id="e5fab-139">Microsoft SQL Server 2012 문서에서는 데이터베이스에 대 한 방화벽 액세스를 구성 하는 방법에 대 한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fab-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="e5fab-140">Microsoft SQL Server 2012에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)"SQL Server 액세스를 허용 하도록 Windows 방화벽 구성"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5fab-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

