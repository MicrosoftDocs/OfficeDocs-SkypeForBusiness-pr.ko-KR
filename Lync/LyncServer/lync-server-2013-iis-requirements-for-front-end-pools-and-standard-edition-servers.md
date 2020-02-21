---
title: 프런트 엔드 풀 및 Standard Edition server에 대 한 IIS 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1511ea24acb058f8de7bdbcf7f831e6493b2ffd6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="53f98-102">Lync Server 2013의 프런트 엔드 풀 및 Standard Edition 서버에 대 한 IIS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="53f98-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53f98-103">_**마지막으로 수정 된 항목:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="53f98-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="53f98-104">Standard Edition 서버 및 프런트 엔드 서버 및 디렉터의 경우 Lync Server 2013 installer는 다음과 같은 목적으로 IIS (인터넷 정보 서비스)에서 가상 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="53f98-105">사용자가 주소록 서비스에서 파일을 다운로드할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="53f98-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="53f98-106">클라이언트에서 업데이트를 가져올 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="53f98-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="53f98-107">회의를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="53f98-107">To enable conferencing</span></span>

  - <span data-ttu-id="53f98-108">사용자가 모임 콘텐츠를 다운로드할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="53f98-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="53f98-109">사용자가 메일 그룹을 확장할 수 있도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="53f98-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="53f98-110">전화 회의를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="53f98-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="53f98-111">응답 그룹 기능을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="53f98-111">To enable response group features</span></span>

<span data-ttu-id="53f98-112">또한 Lync Server 2010 용 누적 업데이트: 11 월 2011 설치 관리자는 다음 목적을 위해 IIS에서 가상 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="53f98-113">모바일 장치에서 IM (인스턴트 메시징) 및 현재 상태와 같은 모바일 기능을 지원 하기 위한 프런트 엔드 서버 또는 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="53f98-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="53f98-114">모바일 장치에서 이동성 리소스를 자동으로 검색할 수 있도록 프런트 엔드 서버 또는 Standard Edition 서버 및 디렉터에서</span><span class="sxs-lookup"><span data-stu-id="53f98-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="53f98-115">모바일 기능을 배포 하는 경우에는 IIS 7.5를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="53f98-116">Lync Server Mobility Service installer는 성능을 개선 하기 위해 몇 가지 ASP.NET 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="53f98-117">IIS 7.5는 Windows Server 2008 R2에서 기본적으로 설치되며, Mobility Service 설치 관리자는 ASP.NET 설정을 자동으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="53f98-118">Windows Server 2008에서 IIS 7.0을 사용하는 경우에는 이러한 설정을 수동으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="53f98-119">Lync Server를 사용 하려면 다음 IIS 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="53f98-120">조직에서 IIS 및 모든 웹 서비스를 시스템 드라이브가 아닌 다른 드라이브에 배치 해야 하는 경우 설치 대화 상자에서 Lync Server 파일의 설치 위치 경로를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="53f98-121">OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우 나머지 Lync Server 파일이이 드라이브에도 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="53f98-122">IIS를 설치할 때 Windows Server 관리자가 배포한 INETPUB의 위치를 변경 하는 방법에 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>대 한 자세한 내용은를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="53f98-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="53f98-123">정적 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="53f98-123">Static Content</span></span>

  - <span data-ttu-id="53f98-124">기본 문서</span><span class="sxs-lookup"><span data-stu-id="53f98-124">Default Document</span></span>

  - <span data-ttu-id="53f98-125">HTTP 오류</span><span class="sxs-lookup"><span data-stu-id="53f98-125">HTTP Errors</span></span>

  - <span data-ttu-id="53f98-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="53f98-126">ASP.NET</span></span>

  - <span data-ttu-id="53f98-127">.NET 확장성</span><span class="sxs-lookup"><span data-stu-id="53f98-127">.NET Extensibility</span></span>

  - <span data-ttu-id="53f98-128">ISAPI(인터넷 서버 API) 확장</span><span class="sxs-lookup"><span data-stu-id="53f98-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="53f98-129">ISAPI 필터</span><span class="sxs-lookup"><span data-stu-id="53f98-129">ISAPI Filters</span></span>

  - <span data-ttu-id="53f98-130">HTTP 로깅</span><span class="sxs-lookup"><span data-stu-id="53f98-130">HTTP Logging</span></span>

  - <span data-ttu-id="53f98-131">로깅 도구</span><span class="sxs-lookup"><span data-stu-id="53f98-131">Logging Tools</span></span>

  - <span data-ttu-id="53f98-132">추적은</span><span class="sxs-lookup"><span data-stu-id="53f98-132">Tracing</span></span>

  - <span data-ttu-id="53f98-133">Windows 인증</span><span class="sxs-lookup"><span data-stu-id="53f98-133">Windows Authentication</span></span>

  - <span data-ttu-id="53f98-134">요청 필터링</span><span class="sxs-lookup"><span data-stu-id="53f98-134">Request Filtering</span></span>

  - <span data-ttu-id="53f98-135">정적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="53f98-135">Static Content Compression</span></span>

  - <span data-ttu-id="53f98-136">동적 콘텐츠 압축</span><span class="sxs-lookup"><span data-stu-id="53f98-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="53f98-137">IIS 관리 콘솔</span><span class="sxs-lookup"><span data-stu-id="53f98-137">IIS Management Console</span></span>

  - <span data-ttu-id="53f98-138">IIS 관리 스크립트 및 도구</span><span class="sxs-lookup"><span data-stu-id="53f98-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="53f98-139">익명 인증 (IIS가 설치 될 때 기본적으로 설치 됨)</span><span class="sxs-lookup"><span data-stu-id="53f98-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="53f98-140">클라이언트 인증서 매핑 인증</span><span class="sxs-lookup"><span data-stu-id="53f98-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="53f98-141">다음 표에는 내부 액세스를 위한 가상 디렉터리의 Uri와 해당 사용자가 참조 하는 파일 시스템 리소스가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="53f98-142">내부 액세스용 가상 디렉터리</span><span class="sxs-lookup"><span data-stu-id="53f98-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53f98-143">기능</span><span class="sxs-lookup"><span data-stu-id="53f98-143">Feature</span></span></th>
<th><span data-ttu-id="53f98-144">가상 디렉터리 URI</span><span class="sxs-lookup"><span data-stu-id="53f98-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="53f98-145">참조 대상</span><span class="sxs-lookup"><span data-stu-id="53f98-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53f98-146">주소록 서버</span><span class="sxs-lookup"><span data-stu-id="53f98-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="53f98-147">https://&lt;내부 FQDN&gt;/ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="53f98-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="53f98-148">내부 사용자 용 주소록 서버 다운로드 파일의 위치</span><span class="sxs-lookup"><span data-stu-id="53f98-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f98-149">자동 검색 서비스</span><span class="sxs-lookup"><span data-stu-id="53f98-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="53f98-150">https://&lt;내부 FQDN&gt;/자동 검색</span><span class="sxs-lookup"><span data-stu-id="53f98-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="53f98-151">내부 모바일 장치 사용자에 대 한 모바일 리소스를 찾는 Lync Server 자동 검색 서비스의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f98-152">클라이언트 업데이트</span><span class="sxs-lookup"><span data-stu-id="53f98-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="53f98-153">http://&lt;내부 FQDN&gt;/AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="53f98-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="53f98-154">내부 컴퓨터 기반 클라이언트용 업데이트 파일의 위치</span><span class="sxs-lookup"><span data-stu-id="53f98-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f98-155">회의</span><span class="sxs-lookup"><span data-stu-id="53f98-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="53f98-156">http://&lt;내부 FQDN&gt;/vrvi</span><span class="sxs-lookup"><span data-stu-id="53f98-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="53f98-157">내부 사용자에 대 한 회의 리소스의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f98-158">장치 업데이트</span><span class="sxs-lookup"><span data-stu-id="53f98-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="53f98-159">http://&lt;내부 FQDN&gt;/DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="53f98-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="53f98-160">내부 UC 장치에 대 한 UC (통합 통신) 장치 업데이트 파일의 위치</span><span class="sxs-lookup"><span data-stu-id="53f98-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f98-161">모임</span><span class="sxs-lookup"><span data-stu-id="53f98-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="53f98-162">http://&lt;내부 FQDN&gt;/etc/place/null</span><span class="sxs-lookup"><span data-stu-id="53f98-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="53f98-163">내부 사용자에 대 한 모임 콘텐츠 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f98-164">모바일 서비스</span><span class="sxs-lookup"><span data-stu-id="53f98-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="53f98-165">https://&lt;내부 FQDN&gt;/mcx</span><span class="sxs-lookup"><span data-stu-id="53f98-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="53f98-166">내부 모바일 장치 사용자에 대 한 모바일 서비스 리소스의 위치</span><span class="sxs-lookup"><span data-stu-id="53f98-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f98-167">그룹 확장 및 주소록 웹 쿼리 서비스</span><span class="sxs-lookup"><span data-stu-id="53f98-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="53f98-168">http://&lt;내부 FQDN&gt;/GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="53f98-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="53f98-169">내부 사용자에 대 한 그룹 확장을 사용 하도록 설정 하는 웹 서비스의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="53f98-170">또한 내부 Lync Mobile Microsoft Lync 2010 모바일 클라이언트에 전체 주소 목록 정보를 제공 하는 주소록 웹 쿼리 서비스의 위치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f98-171">전화 회의</span><span class="sxs-lookup"><span data-stu-id="53f98-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="53f98-172">http://&lt;내부 FQDN&gt;/PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="53f98-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="53f98-173">내부 사용자에 대 한 전화 회의 데이터의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53f98-174">장치 업데이트</span><span class="sxs-lookup"><span data-stu-id="53f98-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="53f98-175">http://&lt;내부 FQDN&gt;/RequestHandler</span><span class="sxs-lookup"><span data-stu-id="53f98-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="53f98-176">내부 UC 장치가 로그를 업로드 하 고 업데이트를 확인할 수 있도록 하는 장치 업데이트 웹 서비스 요청 처리기의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53f98-177">응답 그룹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="53f98-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="53f98-178">http://&lt;내부 FQDN&gt;/RgsConfig</span><span class="sxs-lookup"><span data-stu-id="53f98-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="53f98-179">http://&lt;내부 FQDN&gt;/RgsClients</span><span class="sxs-lookup"><span data-stu-id="53f98-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="53f98-180">응답 그룹 구성 도구의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="53f98-181">통합 된 구성의 프런트 엔드 풀에 대해 서버를 풀에 추가 하려면 먼저 IIS를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" /><span data-ttu-id="53f98-183">보안 메모:</span><span class="sxs-lookup"><span data-stu-id="53f98-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="53f98-184">Iis 웹 구성 요소 서버에서 사용 하는 인증서를 할당 하려면 IIS 관리 스냅인을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53f98-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

