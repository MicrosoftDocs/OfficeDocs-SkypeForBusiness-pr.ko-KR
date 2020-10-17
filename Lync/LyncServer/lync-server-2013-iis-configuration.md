---
title: 'Lync Server 2013: IIS 구성'
description: 'Lync Server 2013: IIS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554874"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="d8b9f-103">Lync Server 2013의 IIS 구성</span><span class="sxs-lookup"><span data-stu-id="d8b9f-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8b9f-104">_**마지막으로 수정 된 항목:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="d8b9f-104">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="d8b9f-105">이 절차를 성공적으로 완료 하려면 최소한 로컬 관리자 및 도메인 사용자로 서버에 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-105">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="d8b9f-106">Lync Server 2013, Standard Edition 또는 풀의 첫 번째 프런트 엔드 서버에 대 한 프런트 엔드 서버를 구성 하 고 설치 하기 전에 IIS (인터넷 정보 서비스)에 대 한 서버 역할과 웹 서비스를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-106">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="d8b9f-107">조직에서 IIS 및 모든 웹 서비스를 시스템 드라이브 이외의 드라이브에 배치 해야 하는 경우 Lync Server 2013 관리 도구를 처음 설치 하는 경우 설치 대화 상자에서 Lync Server 2013 파일의 설치 위치 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-107">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="d8b9f-108">IIS를 설치 하기 전에 관리 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-108">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="d8b9f-109">OCSCore.msi를 포함 하 여이 경로에 설치 파일을 설치 하면 나머지 Lync Server 2013 파일이이 드라이브에도 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-109">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="d8b9f-110">Dtails의 경우 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 관리 도구 설치</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-110">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="d8b9f-111">IIS를 설치할 때 Windows Server 관리자가 배포한 INETPUB의 위치를 변경 하는 방법에 대 한 자세한 내용은를 참조 하십시오 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="d8b9f-111">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="d8b9f-112">다음 표에는 필요한 IIS 7.5 역할 서비스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-112">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="d8b9f-113">IIS 7.5 역할 서비스</span><span class="sxs-lookup"><span data-stu-id="d8b9f-113">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8b9f-114">역할 제목</span><span class="sxs-lookup"><span data-stu-id="d8b9f-114">Role Heading</span></span></th>
<th><span data-ttu-id="d8b9f-115">역할 서비스</span><span class="sxs-lookup"><span data-stu-id="d8b9f-115">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-116">일반적인 HTTP 기능 설치 됨</span><span class="sxs-lookup"><span data-stu-id="d8b9f-116">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-117">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d8b9f-117">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-118">일반적인 HTTP 기능 설치 됨</span><span class="sxs-lookup"><span data-stu-id="d8b9f-118">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-119">기본 문서</span><span class="sxs-lookup"><span data-stu-id="d8b9f-119">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-120">일반적인 HTTP 기능 설치 됨</span><span class="sxs-lookup"><span data-stu-id="d8b9f-120">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-121">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="d8b9f-121">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-122">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-122">Application development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d8b9f-123">ASP.NET</span></span></p>
<p><span data-ttu-id="d8b9f-124">Windows Server 2012에도 ASP. NET 4.5가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-124">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-125">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-125">Application development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-126">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="d8b9f-126">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-127">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-127">Application development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-128">ISAPI (인터넷 서버 API) 확장</span><span class="sxs-lookup"><span data-stu-id="d8b9f-128">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-129">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-129">Application development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-130">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="d8b9f-130">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-131">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="d8b9f-131">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-132">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="d8b9f-132">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-133">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="d8b9f-133">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-134">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-134">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-135">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="d8b9f-135">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-136">추적은</span><span class="sxs-lookup"><span data-stu-id="d8b9f-136">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-137">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-137">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-138">익명 인증 (기본적으로 설치 및 사용 하도록 설정 됨)</span><span class="sxs-lookup"><span data-stu-id="d8b9f-138">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-139">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-139">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-140">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="d8b9f-140">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-141">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-141">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-142">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="d8b9f-142">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-143">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-143">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-144">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="d8b9f-144">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-145">성능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-145">Performance</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-146">정적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="d8b9f-146">Static content compression</span></span></p>
<p><span data-ttu-id="d8b9f-147">동적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="d8b9f-147">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-148">관리 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-148">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-149">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="d8b9f-149">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-150">관리 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-150">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-151">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-151">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d8b9f-152">Windows Server 2008 R2 SP1 x64 운영 체제에서 Windows PowerShell 2.0를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-152">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="d8b9f-153">먼저 ServerManager 모듈을 가져온 다음 IIS 7.5 역할 및 역할 서비스를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-153">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="d8b9f-154">익명 인증은 기본적으로 IIS 서버 역할과 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-154">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="d8b9f-155">IIS를 설치한 후 익명 인증을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-155">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="d8b9f-156">자세한 내용은에서 "익명 인증 사용 (IIS 7)"을 참조 하십시오 <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="d8b9f-156">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="d8b9f-157">다음 표에는 Windows Server 2012 및 Windows Server 2012 r 2에 대 한 필수 IIS 8.0 및 IIS 8.5 역할 서비스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-157">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="d8b9f-158">Windows Server 2012 및 Windows Server 2012 r 2의 경우 Add-WindowsFeature cmdlet이 Install-WindowsFeature cmdlet으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-158">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="d8b9f-159">자세한 내용은 <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-add-windowsfeature</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-159">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="d8b9f-160">IIS 8.0 및 IIS 8.5 역할 서비스</span><span class="sxs-lookup"><span data-stu-id="d8b9f-160">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8b9f-161">역할 제목</span><span class="sxs-lookup"><span data-stu-id="d8b9f-161">Role Heading</span></span></th>
<th><span data-ttu-id="d8b9f-162">역할 서비스</span><span class="sxs-lookup"><span data-stu-id="d8b9f-162">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-163">웹 서버 (IIS)</span><span class="sxs-lookup"><span data-stu-id="d8b9f-163">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-164">웹 서버</span><span class="sxs-lookup"><span data-stu-id="d8b9f-164">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-165">일반 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-165">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-166">기본 문서</span><span class="sxs-lookup"><span data-stu-id="d8b9f-166">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-167">일반 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-167">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-168">디렉터리 검색</span><span class="sxs-lookup"><span data-stu-id="d8b9f-168">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-169">일반 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-169">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-170">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="d8b9f-170">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-171">일반 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-171">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-172">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="d8b9f-172">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-173">일반 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-173">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-174">HTTP 리디렉션</span><span class="sxs-lookup"><span data-stu-id="d8b9f-174">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-175">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="d8b9f-175">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-176">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="d8b9f-176">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-177">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="d8b9f-177">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-178">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-178">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-179">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="d8b9f-179">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-180">요청 모니터</span><span class="sxs-lookup"><span data-stu-id="d8b9f-180">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-181">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="d8b9f-181">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-182">추적은</span><span class="sxs-lookup"><span data-stu-id="d8b9f-182">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-183">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-183">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-184">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="d8b9f-184">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-185">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-185">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-186">기본 인증</span><span class="sxs-lookup"><span data-stu-id="d8b9f-186">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-187">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-187">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-188">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="d8b9f-188">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-189">보안</span><span class="sxs-lookup"><span data-stu-id="d8b9f-189">Security</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-190">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="d8b9f-190">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-191">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-191">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-192">.Net 확장성 3.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-192">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-193">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-193">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-194">.Net 확장성 4.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-194">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-195">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-195">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-196">ASP.Net 3.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-196">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-197">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-197">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-198">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-198">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-199">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-199">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-200">ISAPI 확장</span><span class="sxs-lookup"><span data-stu-id="d8b9f-200">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-201">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-201">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-202">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="d8b9f-202">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-203">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="d8b9f-203">Application Development</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-204">SSI(Server Side Includes)</span><span class="sxs-lookup"><span data-stu-id="d8b9f-204">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-205">관리 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-205">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-206">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="d8b9f-206">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-207">관리 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-207">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-208">IIS 6 메타 베이스 호환성</span><span class="sxs-lookup"><span data-stu-id="d8b9f-208">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-209">관리 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-209">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-210">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="d8b9f-210">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-211">.Net 3.5 Framework 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-211">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-212">.Net 3.5 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="d8b9f-212">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-213">.Net 4.5 Framework 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-213">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-214">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-214">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-215">.Net 4.5 Framework 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-215">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-216">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-216">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-217">.Net 4.5 Framework 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-217">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-218">HTTP 활성화</span><span class="sxs-lookup"><span data-stu-id="d8b9f-218">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-219">.Net 4.5 Framework 기능</span><span class="sxs-lookup"><span data-stu-id="d8b9f-219">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-220">TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="d8b9f-220">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-221">백그라운드 인텔리전트 전송 서비스</span><span class="sxs-lookup"><span data-stu-id="d8b9f-221">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-222">IIS 서버 확장</span><span class="sxs-lookup"><span data-stu-id="d8b9f-222">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-223">잉크 및 필기 서비스</span><span class="sxs-lookup"><span data-stu-id="d8b9f-223">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-224">잉크 및 필기 서비스</span><span class="sxs-lookup"><span data-stu-id="d8b9f-224">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-225">미디어 파운데이션</span><span class="sxs-lookup"><span data-stu-id="d8b9f-225">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-226">미디어 파운데이션</span><span class="sxs-lookup"><span data-stu-id="d8b9f-226">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-227">사용자 인터페이스 및 인프라</span><span class="sxs-lookup"><span data-stu-id="d8b9f-227">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-228">그래픽 관리 도구 및 인프라</span><span class="sxs-lookup"><span data-stu-id="d8b9f-228">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-229">사용자 인터페이스 및 인프라</span><span class="sxs-lookup"><span data-stu-id="d8b9f-229">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-230">데스크톱 환경</span><span class="sxs-lookup"><span data-stu-id="d8b9f-230">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-231">사용자 인터페이스 및 인프라</span><span class="sxs-lookup"><span data-stu-id="d8b9f-231">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-232">서버 그래픽 셸</span><span class="sxs-lookup"><span data-stu-id="d8b9f-232">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-233">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-234">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="d8b9f-234">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b9f-235">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="d8b9f-235">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-236">프로세스 모델</span><span class="sxs-lookup"><span data-stu-id="d8b9f-236">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b9f-237">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="d8b9f-237">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="d8b9f-238">구성 Api</span><span class="sxs-lookup"><span data-stu-id="d8b9f-238">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d8b9f-239">Windows Server 2012 및 Windows Server 2012 r 2에서는 Windows PowerShell 3.0을 사용 하 여 IIS 요구 사항을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-239">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="d8b9f-240">Windows PowerShell 3.0의 ServerManager 모듈을 사용 하 여 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-240">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="d8b9f-241">Windows Server 2012의 새로운 기능은 Windows Server 2012 원본 미디어를 찾을 수 있는 위치를 정의 하는-Source 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b9f-241">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="d8b9f-242">미디어는 DVD 드라이브 (예: D:\Sources\Sxs) 또는 미디어 파일이 복사 된 네트워크 공유 (예: Fileserver\windows2012\sources\Sxs)로 정의 될 수 있습니다 \\ .</span><span class="sxs-lookup"><span data-stu-id="d8b9f-242">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d8b9f-243">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8b9f-243">See Also</span></span>


[<span data-ttu-id="d8b9f-244">Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대 한 IIS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d8b9f-244">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

