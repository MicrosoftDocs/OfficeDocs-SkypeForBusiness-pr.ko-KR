---
title: 'Lync Server 2013: IIS(인터넷 정보 서비스) 요구 사항'
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
ms.openlocfilehash: 3f4b51ac4996e2556ced3ad91e15a6cc58a1623c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="ff9f8-102">Lync Server 2013의 IIS(인터넷 정보 서비스) 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff9f8-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff9f8-103">_**마지막으로 수정한 주제:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ff9f8-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ff9f8-104">여러 Lync Server 2013 구성 요소에는 IIS (인터넷 정보 서비스)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff9f8-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="ff9f8-105">이 항목에서는 Lync Server를 지 원하는 데 필요한 특정 IIS 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff9f8-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="ff9f8-106">이 섹션의 항목에서는 IIS의 특정 구성 요소에 대 한 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff9f8-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="ff9f8-107">Windows Server 2008에서 웹 서버 (IIS) 역할을 사용 하도록 설정 하면 다양 한 역할 서비스가 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff9f8-107">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="ff9f8-108">다음 표에서는 Windows Server 2008에서 웹 서버 (IIS) 역할을 사용할 때 설치 해야 하는 추가 역할 서비스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff9f8-108">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff9f8-109">역할 서비스</span><span class="sxs-lookup"><span data-stu-id="ff9f8-109">Role service</span></span></th>
<th><span data-ttu-id="ff9f8-110">기능</span><span class="sxs-lookup"><span data-stu-id="ff9f8-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff9f8-111">일반적인 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="ff9f8-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-112">HTTP 리디렉션</span><span class="sxs-lookup"><span data-stu-id="ff9f8-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f8-113">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="ff9f8-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ff9f8-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f8-115">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="ff9f8-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-116">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="ff9f8-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f8-117">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="ff9f8-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-118">ISAPI 확장</span><span class="sxs-lookup"><span data-stu-id="ff9f8-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f8-119">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="ff9f8-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-120">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="ff9f8-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f8-121">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="ff9f8-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-122">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="ff9f8-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f8-123">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="ff9f8-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-124">추적할</span><span class="sxs-lookup"><span data-stu-id="ff9f8-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f8-125">보안</span><span class="sxs-lookup"><span data-stu-id="ff9f8-125">Security</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-126">기본 인증</span><span class="sxs-lookup"><span data-stu-id="ff9f8-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f8-127">보안</span><span class="sxs-lookup"><span data-stu-id="ff9f8-127">Security</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-128">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="ff9f8-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9f8-129">관리 도구</span><span class="sxs-lookup"><span data-stu-id="ff9f8-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-130">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="ff9f8-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9f8-131">관리 도구</span><span class="sxs-lookup"><span data-stu-id="ff9f8-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="ff9f8-132">IIS 6 관리 호환성</span><span class="sxs-lookup"><span data-stu-id="ff9f8-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" /><span data-ttu-id="ff9f8-134">보안 참고 사항:</span><span class="sxs-lookup"><span data-stu-id="ff9f8-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ff9f8-135">Windows Server 2008 운영 체제에서 IIS 7.0를 사용 하는 경우 Lync Server 설치 프로그램에서 IIS의 커널 모드 인증을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff9f8-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff9f8-136">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ff9f8-136">In This Section</span></span>

  - [<span data-ttu-id="ff9f8-137">Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대한 IIS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff9f8-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

