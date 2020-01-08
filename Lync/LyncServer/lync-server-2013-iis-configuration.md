---
title: 'Lync Server 2013: IIS 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2205ad049beb05f30dd58795257b62eca68d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="a428b-102">Lync Server 2013의 IIS 구성</span><span class="sxs-lookup"><span data-stu-id="a428b-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a428b-103">_**마지막으로 수정한 주제:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="a428b-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="a428b-104">이 절차를 성공적으로 완료 하려면 로컬 관리자 및 도메인 사용자로 서버에 최소한으로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="a428b-105">Lync Server 2013, Standard Edition 또는 풀의 첫 번째 프런트 엔드 서버에 대 한 프런트 엔드 서버를 구성 하 고 설치 하기 전에 IIS (인터넷 정보 서비스)에 대 한 서버 역할 및 웹 서비스를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="a428b-106">조직에서 시스템 드라이브가 아닌 다른 드라이브의 모든 웹 서비스를 IIS와 찾아야 하는 경우, Lync Server 2013을 처음 설치 하는 경우 설정 대화 상자에서 Lync Server 2013 파일의 설치 위치 경로를 변경할 수 있습니다. 관리 도구.</span><span class="sxs-lookup"><span data-stu-id="a428b-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="a428b-107">IIS를 설치 하기 전에 관리 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="a428b-108">OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우에는 Lync Server 2013 파일의 나머지 부분도이 드라이브에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="a428b-109">Dtails의 경우 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 관리 도구 설치</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a428b-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="a428b-110">IIS를 설치할 때 Windows Server 관리자가 배포한 INETPUB을 재배치 하는 방법에 대 한 <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a428b-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="a428b-111">다음 표에서는 필요한 IIS 7.5 역할 서비스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="a428b-112">IIS 7.5 역할 서비스</span><span class="sxs-lookup"><span data-stu-id="a428b-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a428b-113">역할 제목</span><span class="sxs-lookup"><span data-stu-id="a428b-113">Role Heading</span></span></th>
<th><span data-ttu-id="a428b-114">역할 서비스</span><span class="sxs-lookup"><span data-stu-id="a428b-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a428b-115">일반적인 HTTP 기능 설치 됨</span><span class="sxs-lookup"><span data-stu-id="a428b-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="a428b-116">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="a428b-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-117">일반적인 HTTP 기능 설치 됨</span><span class="sxs-lookup"><span data-stu-id="a428b-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="a428b-118">기본 문서</span><span class="sxs-lookup"><span data-stu-id="a428b-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-119">일반적인 HTTP 기능 설치 됨</span><span class="sxs-lookup"><span data-stu-id="a428b-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="a428b-120">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="a428b-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-121">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="a428b-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a428b-122">ASP.NET</span></span></p>
<p><span data-ttu-id="a428b-123">Windows Server 2012에도 ASP. NET 4.5가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-124">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="a428b-125">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="a428b-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-126">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="a428b-127">ISAPI (인터넷 서버 API) 확장</span><span class="sxs-lookup"><span data-stu-id="a428b-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-128">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="a428b-129">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="a428b-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-130">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="a428b-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a428b-131">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="a428b-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-132">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="a428b-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a428b-133">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-134">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="a428b-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a428b-135">추적할</span><span class="sxs-lookup"><span data-stu-id="a428b-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-136">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-136">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-137">익명 인증 (설치 됨 및 기본적으로 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="a428b-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-138">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-138">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-139">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="a428b-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-140">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-140">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-141">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="a428b-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-142">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-142">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-143">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="a428b-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-144">성능을</span><span class="sxs-lookup"><span data-stu-id="a428b-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="a428b-145">정적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="a428b-145">Static content compression</span></span></p>
<p><span data-ttu-id="a428b-146">동적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="a428b-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-147">관리 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a428b-148">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="a428b-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-149">관리 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a428b-150">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a428b-151">Windows Server 2008 R2 SP1 x64 운영 체제에서 Windows PowerShell 2.0을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="a428b-152">먼저 ServerManager 모듈을 가져온 다음 IIS 7.5 역할 및 역할 서비스를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="a428b-153">익명 인증은 IIS 서버 역할을 사용 하 여 기본적으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="a428b-154">IIS를 설치한 후에 익명 인증을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="a428b-155">자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>"익명 인증 사용 (IIS 7)"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a428b-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="a428b-156">다음 표에서는 Windows Server 2012 및 Windows Server 2012 R2에 대 한 필수 IIS 8.0 및 IIS 8.5 역할 서비스를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="a428b-157">Windows Server 2012 및 Windows Server 2012 R2의 경우 Add-windowsfeature cmdlet이 설치-Add-windowsfeature cmdlet으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="a428b-158">자세한 내용은 <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">설치-add-windowsfeature</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a428b-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="a428b-159">IIS 8.0 및 IIS 8.5 역할 서비스</span><span class="sxs-lookup"><span data-stu-id="a428b-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a428b-160">역할 제목</span><span class="sxs-lookup"><span data-stu-id="a428b-160">Role Heading</span></span></th>
<th><span data-ttu-id="a428b-161">역할 서비스</span><span class="sxs-lookup"><span data-stu-id="a428b-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a428b-162">웹 서버 (IIS)</span><span class="sxs-lookup"><span data-stu-id="a428b-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="a428b-163">웹 서버</span><span class="sxs-lookup"><span data-stu-id="a428b-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-164">일반적인 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-165">기본 문서</span><span class="sxs-lookup"><span data-stu-id="a428b-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-166">일반적인 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-167">디렉터리 검색</span><span class="sxs-lookup"><span data-stu-id="a428b-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-168">일반적인 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-169">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="a428b-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-170">일반적인 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-171">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="a428b-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-172">일반적인 HTTP 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-173">HTTP 리디렉션</span><span class="sxs-lookup"><span data-stu-id="a428b-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-174">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="a428b-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a428b-175">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="a428b-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-176">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="a428b-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a428b-177">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-178">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="a428b-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a428b-179">요청 모니터</span><span class="sxs-lookup"><span data-stu-id="a428b-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-180">상태 및 진단</span><span class="sxs-lookup"><span data-stu-id="a428b-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="a428b-181">추적할</span><span class="sxs-lookup"><span data-stu-id="a428b-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-182">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-182">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-183">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="a428b-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-184">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-184">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-185">기본 인증</span><span class="sxs-lookup"><span data-stu-id="a428b-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-186">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-186">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-187">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="a428b-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-188">보안</span><span class="sxs-lookup"><span data-stu-id="a428b-188">Security</span></span></p></td>
<td><p><span data-ttu-id="a428b-189">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="a428b-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-190">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a428b-191">.Net 확장성 3.5</span><span class="sxs-lookup"><span data-stu-id="a428b-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-192">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a428b-193">.Net 확장성 4.5</span><span class="sxs-lookup"><span data-stu-id="a428b-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-194">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a428b-195">ASP.Net 3.5</span><span class="sxs-lookup"><span data-stu-id="a428b-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-196">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a428b-197">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="a428b-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-198">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a428b-199">ISAPI 확장</span><span class="sxs-lookup"><span data-stu-id="a428b-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-200">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a428b-201">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="a428b-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-202">응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a428b-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="a428b-203">서버 쪽 포함</span><span class="sxs-lookup"><span data-stu-id="a428b-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-204">관리 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a428b-205">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="a428b-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-206">관리 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a428b-207">IIS 6 메타 베이스 호환성</span><span class="sxs-lookup"><span data-stu-id="a428b-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-208">관리 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="a428b-209">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="a428b-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-210">.Net 3.5 프레임 워크 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-211">.Net 3.5 프레임 워크</span><span class="sxs-lookup"><span data-stu-id="a428b-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-212">.Net 4.5 프레임 워크 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-213">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="a428b-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-214">.Net 4.5 프레임 워크 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-215">ASP.Net 4.5</span><span class="sxs-lookup"><span data-stu-id="a428b-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-216">.Net 4.5 프레임 워크 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-217">HTTP 활성화</span><span class="sxs-lookup"><span data-stu-id="a428b-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-218">.Net 4.5 프레임 워크 기능</span><span class="sxs-lookup"><span data-stu-id="a428b-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="a428b-219">TCP 포트 공유</span><span class="sxs-lookup"><span data-stu-id="a428b-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-220">백그라운드 인텔리전트 전송 서비스</span><span class="sxs-lookup"><span data-stu-id="a428b-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="a428b-221">IIS Server Extensions</span><span class="sxs-lookup"><span data-stu-id="a428b-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-222">잉크 및 필기 서비스</span><span class="sxs-lookup"><span data-stu-id="a428b-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="a428b-223">잉크 및 필기 서비스</span><span class="sxs-lookup"><span data-stu-id="a428b-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-224">미디어 파운데이션</span><span class="sxs-lookup"><span data-stu-id="a428b-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="a428b-225">미디어 파운데이션</span><span class="sxs-lookup"><span data-stu-id="a428b-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-226">사용자 인터페이스 및 인프라</span><span class="sxs-lookup"><span data-stu-id="a428b-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="a428b-227">그래픽 관리 도구 및 인프라</span><span class="sxs-lookup"><span data-stu-id="a428b-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-228">사용자 인터페이스 및 인프라</span><span class="sxs-lookup"><span data-stu-id="a428b-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="a428b-229">데스크톱 환경</span><span class="sxs-lookup"><span data-stu-id="a428b-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-230">사용자 인터페이스 및 인프라</span><span class="sxs-lookup"><span data-stu-id="a428b-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="a428b-231">서버 그래픽 셸</span><span class="sxs-lookup"><span data-stu-id="a428b-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-232">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="a428b-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="a428b-233">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="a428b-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a428b-234">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="a428b-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="a428b-235">프로세스 모델</span><span class="sxs-lookup"><span data-stu-id="a428b-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a428b-236">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="a428b-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="a428b-237">구성 Api</span><span class="sxs-lookup"><span data-stu-id="a428b-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a428b-238">Windows Server 2012 및 Windows Server 2012 R2에서 Windows PowerShell 3.0을 사용 하 여 IIS 요구 사항을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="a428b-239">Windows PowerShell 3.0에서 ServerManager 모듈을 사용 하 여 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```
    Import-Module ServerManager
   ```

   ```
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="a428b-240">Windows Server 2012의 새로운 기능은 Windows Server 2012 원본 미디어를 찾을 수 있는 위치를 정의 하는 – Source 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="a428b-241">미디어는 DVD 드라이브 (예: D:\Sources\Sxs) 또는 미디어 파일이 복사 된 네트워크 공유 (예: \\fileserver\windows2012\sources\Sxs)로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a428b-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a428b-242">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a428b-242">See Also</span></span>


[<span data-ttu-id="a428b-243">Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대한 IIS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a428b-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

