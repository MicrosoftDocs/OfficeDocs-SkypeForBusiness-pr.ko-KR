---
title: 'Lync Server 2013: SQL Server에 대 한 방화벽 요구 사항 이해'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f836c71023defd6c826ab763d36e395a1240d3da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527745"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="4334f-102">Lync Server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해</span><span class="sxs-lookup"><span data-stu-id="4334f-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4334f-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4334f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4334f-104">Standard Edition 배포의 경우 Lync Server 2013 설치 중에 방화벽 예외가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="4334f-105">그러나 Enterprise Edition 배포의 경우 SQL Server 백 엔드 서버에서 방화벽 예외를 수동으로 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="4334f-106">TCP/IP 프로토콜을 사용하는 경우 지정된 IP 주소에 대해 지정된 포트를 한 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="4334f-107">즉, SQL Server 기반 서버의 경우 기본 데이터베이스 인스턴스에 기본 TCP 포트 1433을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="4334f-108">기타 모든 인스턴스의 경우에는 SQL Server 구성 관리자를 사용하여 고유한 미사용 포트를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="4334f-109">이 항목에서는 다음에 대해 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-109">This topic covers:</span></span>

  - <span data-ttu-id="4334f-110">기본 인스턴스를 사용하는 경우의 방화벽 예외 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4334f-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="4334f-111">SQL Server Browser 서비스를 사용하는 경우의 방화벽 예외 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4334f-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="4334f-112">명명된 인스턴스를 사용하는 경우의 정적 수신 대기 포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4334f-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="4334f-113">기본 인스턴스를 사용하는 경우의 방화벽 예외 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4334f-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="4334f-114">Lync Server 2013를 배포할 때 모든 데이터베이스에 대해 SQL Server 기본 인스턴스를 사용 하는 경우에는 다음 방화벽 규칙 요구 사항을 사용 하 여 프런트 엔드 풀에서 SQL Server 기본 인스턴스에 대 한 통신을 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4334f-115">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="4334f-115">Protocol</span></span></th>
<th><span data-ttu-id="4334f-116">포트</span><span class="sxs-lookup"><span data-stu-id="4334f-116">Port</span></span></th>
<th><span data-ttu-id="4334f-117">Direction</span><span class="sxs-lookup"><span data-stu-id="4334f-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4334f-118">TCP</span><span class="sxs-lookup"><span data-stu-id="4334f-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="4334f-119">1433</span><span class="sxs-lookup"><span data-stu-id="4334f-119">1433</span></span></p></td>
<td><p><span data-ttu-id="4334f-120">SQL Server로 인바운드</span><span class="sxs-lookup"><span data-stu-id="4334f-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="4334f-121">SQL Server Browser 서비스를 사용하는 경우의 방화벽 예외 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4334f-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="4334f-122">SQL Server Browser 서비스는 데이터베이스 인스턴스를 찾아 해당 인스턴스(명명된 인스턴스 또는 기본 인스턴스)가 사용하도록 구성된 포트와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4334f-123">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="4334f-123">Protocol</span></span></th>
<th><span data-ttu-id="4334f-124">포트</span><span class="sxs-lookup"><span data-stu-id="4334f-124">Port</span></span></th>
<th><span data-ttu-id="4334f-125">Direction</span><span class="sxs-lookup"><span data-stu-id="4334f-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4334f-126">P</span><span class="sxs-lookup"><span data-stu-id="4334f-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="4334f-127">1434</span><span class="sxs-lookup"><span data-stu-id="4334f-127">1434</span></span></p></td>
<td><p><span data-ttu-id="4334f-128">인바운드</span><span class="sxs-lookup"><span data-stu-id="4334f-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="4334f-129">명명된 인스턴스를 사용하는 경우의 정적 수신 대기 포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4334f-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="4334f-130">Lync Server 2013을 지 원하는 데이터베이스에 대 한 SQL Server 구성에서 명명 된 인스턴스를 사용 하는 경우 SQL Server Configuration Manager를 사용 하 여 정적 포트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="4334f-131">정적 포트를 각 명명된 인스턴스에 할당한 후에는 방화벽의 각 정적 포트에 대한 예외를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4334f-132">Protocol(프로토콜)</span><span class="sxs-lookup"><span data-stu-id="4334f-132">Protocol</span></span></th>
<th><span data-ttu-id="4334f-133">포트</span><span class="sxs-lookup"><span data-stu-id="4334f-133">Port</span></span></th>
<th><span data-ttu-id="4334f-134">Direction</span><span class="sxs-lookup"><span data-stu-id="4334f-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4334f-135">TCP</span><span class="sxs-lookup"><span data-stu-id="4334f-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="4334f-136">정적으로 정의됨</span><span class="sxs-lookup"><span data-stu-id="4334f-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="4334f-137">인바운드</span><span class="sxs-lookup"><span data-stu-id="4334f-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="4334f-138">SQL Server 설명서</span><span class="sxs-lookup"><span data-stu-id="4334f-138">SQL Server Documentation</span></span>

<span data-ttu-id="4334f-139">Microsoft SQL Server 2012 문서에서는 데이터베이스에 대 한 방화벽 액세스를 구성 하는 방법에 대 한 자세한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4334f-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="4334f-140">Microsoft SQL Server 2012에 대 한 자세한 내용은의 "SQL Server 액세스를 허용 하도록 Windows 방화벽 구성"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) .</span><span class="sxs-lookup"><span data-stu-id="4334f-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

