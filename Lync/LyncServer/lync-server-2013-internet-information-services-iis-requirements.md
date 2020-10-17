---
title: 'Lync Server 2013: IIS (인터넷 정보 서비스) 요구 사항'
description: 'Lync Server 2013: IIS (인터넷 정보 서비스) 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543994"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="942c9-103">Lync Server 2013의 IIS (인터넷 정보 서비스) 요구 사항</span><span class="sxs-lookup"><span data-stu-id="942c9-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="942c9-104">_**마지막으로 수정 된 항목:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="942c9-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="942c9-105">여러 Lync Server 2013 구성 요소에는 IIS (인터넷 정보 서비스)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="942c9-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="942c9-106">이 항목에서는 Lync Server를 지 원하는 데 필요한 특정 IIS 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="942c9-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="942c9-107">이 섹션의 항목에서는 IIS의 특정 구성 요소에 대한 요구 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="942c9-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="942c9-p102">Windows Server 2008에서 웹 서버(IIS) 역할이 사용하도록 설정되어 있으면 다양한 역할 서비스가 기본적으로 설치됩니다. 다음 표에서는 Windows Server 2008에서 웹 서버(IIS) 역할이 사용하도록 설정되어 있을 때 설치해야 하는 추가 역할 서비스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="942c9-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="942c9-110">역할 서비스</span><span class="sxs-lookup"><span data-stu-id="942c9-110">Role service</span></span></th>
<th><span data-ttu-id="942c9-111">기능</span><span class="sxs-lookup"><span data-stu-id="942c9-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="942c9-112">일반 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="942c9-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="942c9-113">HTTP 리디렉션</span><span class="sxs-lookup"><span data-stu-id="942c9-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942c9-114">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="942c9-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="942c9-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="942c9-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942c9-116">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="942c9-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="942c9-117">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="942c9-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942c9-118">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="942c9-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="942c9-119">ISAPI 확장</span><span class="sxs-lookup"><span data-stu-id="942c9-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942c9-120">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="942c9-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="942c9-121">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="942c9-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942c9-122">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="942c9-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="942c9-123">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="942c9-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942c9-124">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="942c9-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="942c9-125">추적은</span><span class="sxs-lookup"><span data-stu-id="942c9-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942c9-126">보안</span><span class="sxs-lookup"><span data-stu-id="942c9-126">Security</span></span></p></td>
<td><p><span data-ttu-id="942c9-127">기본 인증</span><span class="sxs-lookup"><span data-stu-id="942c9-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942c9-128">보안</span><span class="sxs-lookup"><span data-stu-id="942c9-128">Security</span></span></p></td>
<td><p><span data-ttu-id="942c9-129">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="942c9-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="942c9-130">관리 도구</span><span class="sxs-lookup"><span data-stu-id="942c9-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="942c9-131">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="942c9-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="942c9-132">관리 도구</span><span class="sxs-lookup"><span data-stu-id="942c9-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="942c9-133">IIS 6 관리 호환성</span><span class="sxs-lookup"><span data-stu-id="942c9-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" /><span data-ttu-id="942c9-135">보안 메모:</span><span class="sxs-lookup"><span data-stu-id="942c9-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="942c9-136">Windows Server 2008 운영 체제에서 IIS 7.0을 사용 하는 경우 Lync Server 설치 프로그램에서 커널 모드 인증을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="942c9-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="942c9-137">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="942c9-137">In This Section</span></span>

  - [<span data-ttu-id="942c9-138">Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대 한 IIS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="942c9-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

