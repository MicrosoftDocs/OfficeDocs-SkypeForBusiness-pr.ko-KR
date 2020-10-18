---
title: Lync Server 2013 기술 다이어그램
description: Lync Server 2013 기술 다이어그램
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical diagrams
ms:assetid: 7b6da49b-ac72-4ab0-8957-166e330b38fa
ms:mtpsurl: https://technet.microsoft.com/library/Dn594589(v=OCS.15)
ms:contentKeyID: 61180439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4dee8dab089de924317d6979e6d085072b0beab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577204"
---
# <a name="technical-diagrams-for-lync-server-2013"></a><span data-ttu-id="46427-103">Lync Server 2013에 대 한 기술 다이어그램</span><span class="sxs-lookup"><span data-stu-id="46427-103">Technical diagrams for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46427-104">_**마지막으로 수정 된 항목:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="46427-104">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="46427-105">**요약:**   이러한 다이어그램은 Lync 2013에 대 한 권장 솔루션을 시각적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46427-105">**Summary:** These diagrams provide visual representations of recommended solutions for Lync 2013.</span></span>

<span data-ttu-id="46427-106">이러한 리소스는 Visio (.vsd) 형식 (Visio 2010 또는 Visio 2013) 및 PDF 형식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-106">These resources are available in Visio (.vsd) format (Visio 2010 or Visio 2013) and PDF format.</span></span> <span data-ttu-id="46427-107">문서를 인쇄 하는 방법에 대 한 자세한 내용은 포스터 인쇄용 팁을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="46427-107">For information about how to print documents, see Tips for printing posters.</span></span>

<span data-ttu-id="46427-p102">이러한 파일을 보는 데 추가 소프트웨어가 필요할 수도 있습니다. 자세한 내용은 다음 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46427-p102">You might need additional software to view these files. See the following table for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46427-110">파일 형식</span><span class="sxs-lookup"><span data-stu-id="46427-110">File type</span></span></th>
<th><span data-ttu-id="46427-111">소프트웨어</span><span class="sxs-lookup"><span data-stu-id="46427-111">Software</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46427-112">.vsd</span><span class="sxs-lookup"><span data-stu-id="46427-112">.vsd</span></span></p></td>
<td><p><span data-ttu-id="46427-113">Visio 2010, Visio 2013 또는 <a href="https://go.microsoft.com/fwlink/?linkid=393676">무료 Visio viewer</a></span><span class="sxs-lookup"><span data-stu-id="46427-113">Visio 2010, Visio 2013, or the <a href="https://go.microsoft.com/fwlink/?linkid=393676">free Visio viewer</a></span></span></p>
<p><span data-ttu-id="46427-114">Visio Viewer를 사용하는 경우 VSD 링크를 마우스 오른쪽 단추로 클릭하고 <strong>다른 이름으로 대상 저장</strong>을 클릭하여 컴퓨터에 파일을 저장한 다음 컴퓨터에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46427-114">If you use the Visio viewer, right-click the VSD link, click <strong>Save Target As</strong>, save the file to your computer, and then open the file from your computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46427-115">.pdf</span><span class="sxs-lookup"><span data-stu-id="46427-115">.pdf</span></span></p></td>
<td><p><span data-ttu-id="46427-116"><a href="https://go.microsoft.com/fwlink/?linkid=393675">Adobe Reader</a> 등의 PDF 뷰어</span><span class="sxs-lookup"><span data-stu-id="46427-116">Any PDF viewer, such as <a href="https://go.microsoft.com/fwlink/?linkid=393675">Adobe Reader</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46427-117">.zip</span><span class="sxs-lookup"><span data-stu-id="46427-117">.zip</span></span></p></td>
<td><p><span data-ttu-id="46427-118">모든 파일 압축 유틸리티</span><span class="sxs-lookup"><span data-stu-id="46427-118">Any file compression utility.</span></span> <span data-ttu-id="46427-119">Windows 7과 8에서는 이러한 파일을 기본적으로 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46427-119">Windows 7 and 8 open these files natively.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="posters"></a><span data-ttu-id="46427-120">포스터</span><span class="sxs-lookup"><span data-stu-id="46427-120">Posters</span></span>

<span data-ttu-id="46427-121">이러한 포스터는 특정 기술 영역을 상세히 설명 하며, TechNet의 해당 문서와 함께 사용 하거나 다운로드 센터에서 사용할 수 있는 콘텐츠를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-121">These posters detail a specific technical area, and are intended to be used with corresponding articles on TechNet or content available on the download center.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46427-122">제목</span><span class="sxs-lookup"><span data-stu-id="46427-122">Title</span></span></th>
<th><span data-ttu-id="46427-123">설명</span><span class="sxs-lookup"><span data-stu-id="46427-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46427-124"><strong>Lync Server 2013 온-프레미스 아키텍처</strong></span><span class="sxs-lookup"><span data-stu-id="46427-124"><strong>Lync Server 2013 On-Premises Architectures</strong></span></span></p>
<img src="images/Dn594589.36530bb8-732f-4be0-9502-082c01df9fba(OCS.15).jpg" title="Lync 아키텍처 포스터 축소판 그림" alt="thumbnail of Lync architectures poster" />
<p><span data-ttu-id="46427-126"><a href="https://go.microsoft.com/fwlink/?linkid=392974">Microsoft에서 Zoom.it를 사용 하 여 포스터 확대 세부 정보</a>(데스크톱 또는 랩탑 컴퓨터에서 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-126"><a href="https://go.microsoft.com/fwlink/?linkid=392974">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="46427-127"><a href="https://go.microsoft.com/fwlink/?linkid=392578">PDF 버전</a> (모바일 장치 또는 태블릿 컴퓨터에서 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-127"><a href="https://go.microsoft.com/fwlink/?linkid=392578">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="46427-128"><a href="https://go.microsoft.com/fwlink/?linkid=392579">Visio 버전</a> (visio 사용자에 게 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-128"><a href="https://go.microsoft.com/fwlink/?linkid=392579">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="46427-129">포스터는 계획 및 배포에 대 한 아키텍처 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-129">Poster provides architectural guidance for planning and deployment.</span></span> <span data-ttu-id="46427-130">포스터에는 Lync Server의 일반 구성 요소, 배포 계획 시 사용 되는 용어, 새 기능, 서버 역할 및 설치 개요에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-130">The poster contains information about common components of Lync Server, terminology used when planning a deployment, new features, server roles, and an installation overview.</span></span> <span data-ttu-id="46427-131">또한 포스터에는 소형, 중형 및 대형 샘플 토폴로지의 고가용성 및 재해 복구를 향상 시키기 위한 예제 아키텍처가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-131">In addition the poster contains example architectures for increasing high availability and disaster recovery as well as small, medium, and large sample topologies.</span></span></p>
<p><span data-ttu-id="46427-132">크기: 34-44 인치</span><span class="sxs-lookup"><span data-stu-id="46427-132">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="46427-133">이 포스터는 Visio 2013를 사용 하 여 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-133">This poster was created using Visio 2013.</span></span> <span data-ttu-id="46427-134">특정 환경에 대 한 수정이 필요 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-134">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46427-135"><strong>Lync 통화 품질 방법론</strong></span><span class="sxs-lookup"><span data-stu-id="46427-135"><strong>Lync Call Quality Methodology</strong></span></span></p>
<img src="images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg" title="CQM 프로세스를 설명 하는 포스터" alt="Poster describing the CQM process" />
<p><span data-ttu-id="46427-137"><a href="https://go.microsoft.com/fwlink/?linkid=392972">Microsoft에서 Zoom.it를 사용 하 여 포스터 확대 세부 정보</a>(데스크톱 또는 랩탑 컴퓨터에서 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-137"><a href="https://go.microsoft.com/fwlink/?linkid=392972">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="46427-138"><a href="https://go.microsoft.com/fwlink/?linkid=391841">.Zip 파일에 Visio 및 PDF 버전 함께</a></span><span class="sxs-lookup"><span data-stu-id="46427-138"><a href="https://go.microsoft.com/fwlink/?linkid=391841">Visio and PDF versions together in a .zip file</a></span></span></p></td>
<td><p><span data-ttu-id="46427-139">Lync 시스템 문제 해결에 대해 설명 하는 포스터, 특히 엔터프라이즈 음성 품질에 영향을 주는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="46427-139">Poster describing Lync system troubleshooting, especially for issues affecting enterprise voice quality.</span></span> <span data-ttu-id="46427-140">사용할 포스터:</span><span class="sxs-lookup"><span data-stu-id="46427-140">Use this poster with:</span></span></p>
<ul>
<li><p><span data-ttu-id="46427-141"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server 네트워킹 가이드</a></span><span class="sxs-lookup"><span data-stu-id="46427-141"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server Networking Guide</a></span></span></p></li>
<li><p><span data-ttu-id="46427-142"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Server 2013의 Lync 통화 품질 방법론</a> (접근성 문서)</span><span class="sxs-lookup"><span data-stu-id="46427-142"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Call Quality Methodology in Lync Server 2013</a> (accessibility article)</span></span></p></li>
<li><p><span data-ttu-id="46427-143"><a href="lync-server-2013-poster-key-health-indicators.md">Lync Server 2013의 주요 상태 지표</a> (접근성 문서)</span><span class="sxs-lookup"><span data-stu-id="46427-143"><a href="lync-server-2013-poster-key-health-indicators.md">Key Health Indicators in Lync Server 2013</a> (accessibility article)</span></span></p></li>
</ul>
<p><span data-ttu-id="46427-144">크기: 34-44 인치</span><span class="sxs-lookup"><span data-stu-id="46427-144">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="46427-145">이 포스터는 Visio 2010를 사용 하 여 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-145">This poster was created using Visio 2010.</span></span> <span data-ttu-id="46427-146">특정 환경에 대 한 수정이 필요 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-146">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46427-147"><strong>주요 상태 표시기</strong></span><span class="sxs-lookup"><span data-stu-id="46427-147"><strong>Key Health Indicators</strong></span></span></p>
<img src="images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg" title="KHI 데이터를 사용한 문제 해결에 대해 설명 하는 포스터" alt="Poster describing troubleshooting using KHI data" />
<p><span data-ttu-id="46427-149"><a href="https://go.microsoft.com/fwlink/?linkid=392971">Microsoft에서 Zoom.it를 사용 하 여 포스터 확대 세부 정보</a>(데스크톱 또는 랩탑 컴퓨터에서 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-149"><a href="https://go.microsoft.com/fwlink/?linkid=392971">Zoom into the poster in full detail with Zoom.it from Microsoft</a>(best on desktop or laptop computers)</span></span></p>
<p><span data-ttu-id="46427-150"><a href="https://go.microsoft.com/fwlink/?linkid=391838">.Zip 파일에 Visio 및 PDF 버전 함께</a></span><span class="sxs-lookup"><span data-stu-id="46427-150"><a href="https://go.microsoft.com/fwlink/?linkid=391838">Visio and PDF versions together in a .zip file</a></span></span></p></td>
<td><p><span data-ttu-id="46427-151">서버 문제 해결 메트릭 및 Lync 구현에서 주어진 서버의 역할에 대 한 기본 서버 상태를 설명 하는 포스터입니다.</span><span class="sxs-lookup"><span data-stu-id="46427-151">Poster describing server troubleshooting metrics both for basic server health and for a given server’s role in the Lync implementation.</span></span> <span data-ttu-id="46427-152">사용할 포스터:</span><span class="sxs-lookup"><span data-stu-id="46427-152">Use this poster with:</span></span></p>
<ul>
<li><p><span data-ttu-id="46427-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server 네트워킹 가이드</a></span><span class="sxs-lookup"><span data-stu-id="46427-153"><a href="https://go.microsoft.com/fwlink/p/?linkid=390677">Lync Server Networking Guide</a></span></span></p></li>
<li><p><span data-ttu-id="46427-154"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Server 2013의 Lync 통화 품질 방법론</a> (접근성 문서)</span><span class="sxs-lookup"><span data-stu-id="46427-154"><a href="lync-server-2013-poster-lync-call-quality-methodology.md">Lync Call Quality Methodology in Lync Server 2013</a> (accessibility article)</span></span></p></li>
<li><p><span data-ttu-id="46427-155"><a href="lync-server-2013-poster-key-health-indicators.md">Lync Server 2013의 주요 상태 지표</a> (접근성 문서)</span><span class="sxs-lookup"><span data-stu-id="46427-155"><a href="lync-server-2013-poster-key-health-indicators.md">Key Health Indicators in Lync Server 2013</a> (accessibility article)</span></span></p></li>
</ul>
<p><span data-ttu-id="46427-156">크기: 17 x 22 인치</span><span class="sxs-lookup"><span data-stu-id="46427-156">Size: 17-by-22 inch</span></span></p>
<p><span data-ttu-id="46427-157">이 포스터는 Visio 2010를 사용 하 여 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-157">This poster was created using Visio 2010.</span></span> <span data-ttu-id="46427-158">특정 환경에 대 한 수정이 필요 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-158">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46427-159"><strong>Lync 2013 플랫폼 옵션</strong></span><span class="sxs-lookup"><span data-stu-id="46427-159"><strong>Lync 2013 Platform Options</strong></span></span></p>
<img src="images/Dn594589.c5b66828-c3cf-4654-bb75-b93f97d085b3(OCS.15).jpg" title="플랫폼 옵션 포스터의 축소판 그림 보기" alt="thumbnail view of platform options poster" />
<p><span data-ttu-id="46427-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=391840">Microsoft에서 Zoom.it로 전체 세부 정보로 포스터 확대</a></span><span class="sxs-lookup"><span data-stu-id="46427-161"><a href="https://go.microsoft.com/fwlink/p/?linkid=391840">Zoom into the poster in full detail with Zoom.it from Microsoft</a></span></span></p>
<p><span data-ttu-id="46427-162"><a href="https://go.microsoft.com/fwlink/p/?linkid=391837">PDF 버전</a> (모바일 장치 또는 태블릿 컴퓨터에서 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-162"><a href="https://go.microsoft.com/fwlink/p/?linkid=391837">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="46427-163"><a href="https://go.microsoft.com/fwlink/p/?linkid=391839">Visio 버전</a> (visio 사용자에 게 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-163"><a href="https://go.microsoft.com/fwlink/p/?linkid=391839">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="46427-164">이 포스터에서는 Lync 2013에 대 한 사용 가능한 플랫폼 옵션에 대해 설명 하 고, BDMs 설계자는 Microsoft 365, Hybrid Lync, Lync Server 온-프레미스 및 호스팅된 Lync를 사용 하 여 Lync Online에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-164">This poster describes the available platform options for Lync 2013 to BDMs and architects  Customers can choose from Lync Online with Microsoft 365, Hybrid Lync, Lync Server on-premises and Hosted Lync.</span></span> <span data-ttu-id="46427-165">이 포스터에는 각 라이선스 요구 사항 및 IT 전문가 업무에 가장 적합한 시나리오를 포함하여 각 아키텍처 옵션에 대한 세부 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-165">The poster includes details of each architectural option, including the most ideal scenarios for each, the license requirements and IT Pro responsibilities.</span></span></p>
<p><span data-ttu-id="46427-166">크기: 34-44 인치</span><span class="sxs-lookup"><span data-stu-id="46427-166">Size: 34-by-44 inch</span></span></p>
<p><span data-ttu-id="46427-167">이 포스터는 Visio 2013를 사용 하 여 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-167">This poster was created using Visio 2013.</span></span> <span data-ttu-id="46427-168">특정 환경에 대 한 수정이 필요 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-168">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46427-169"><strong>Microsoft Lync Server 2013 프로토콜 작업</strong></span><span class="sxs-lookup"><span data-stu-id="46427-169"><strong>Microsoft Lync Server 2013 Protocol Workloads</strong></span></span></p>
<img src="images/Dn594589.e00f8445-4e00-48f6-a3e2-f97334dde719(OCS.15).jpg" title="프로토콜 워크 로드 포스터의 축소판 그림 보기" alt="thumbnail view of protocol Workloads poster" />
<p><span data-ttu-id="46427-171"><a href="https://go.microsoft.com/fwlink/?linkid=392970">Microsoft에서 Zoom.it로 전체 세부 정보로 포스터 확대</a></span><span class="sxs-lookup"><span data-stu-id="46427-171"><a href="https://go.microsoft.com/fwlink/?linkid=392970">Zoom into the poster in full detail with Zoom.it from Microsoft</a></span></span></p>
<p><span data-ttu-id="46427-172"><a href="https://go.microsoft.com/fwlink/?linkid=392512">PDF 버전</a> (모바일 장치 또는 태블릿 컴퓨터에서 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-172"><a href="https://go.microsoft.com/fwlink/?linkid=392512">PDF version</a> (best for mobile devices or tablet computers)</span></span></p>
<p><span data-ttu-id="46427-173"><a href="https://go.microsoft.com/fwlink/?linkid=392513">Visio 버전</a> (visio 사용자에 게 가장 적합)</span><span class="sxs-lookup"><span data-stu-id="46427-173"><a href="https://go.microsoft.com/fwlink/?linkid=392513">Visio version</a> (best for users with Visio)</span></span></p></td>
<td><p><span data-ttu-id="46427-174">이 포스터를 다운로드 하 여 Lync 2013, Lync Phone, Lync Web App, lync for Mac 및 Lync Mobile w의 기능 및 요구 사항을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-174">Download this poster to understand the capabilities and requirements of Lync 2013, Lync Phone, Lync Web App, Lync for Mac, and Lync Mobile w.</span></span> <span data-ttu-id="46427-175">Lync Server 워크 로드를 통해 조직 전체의 통신을 활용 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46427-175">See how Lync Server workloads facilitate communication across an organization.</span></span></p>
<p><span data-ttu-id="46427-176">크기: 24 x 36 인치</span><span class="sxs-lookup"><span data-stu-id="46427-176">Size: 24-by-36 inch</span></span></p>
<p><span data-ttu-id="46427-177">이 포스터는 Visio 2013를 사용 하 여 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="46427-177">This poster was created using Visio 2013.</span></span> <span data-ttu-id="46427-178">특정 환경에 대 한 수정이 필요 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-178">No modification should be needed for a specific environment.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="tips"></span>

<div>

## <a name="tips-for-printing-posters"></a><span data-ttu-id="46427-179">포스터 인쇄 팁</span><span class="sxs-lookup"><span data-stu-id="46427-179">Tips for printing posters</span></span>

<span data-ttu-id="46427-p114">플로터가 있는 경우 이러한 포스터를 최대 크기로 인쇄할 수 있습니다. 플로터가 없으면 다음 단계에 따라 더 작은 용지에 인쇄하십시오.</span><span class="sxs-lookup"><span data-stu-id="46427-p114">If you have a plotter, you can print these posters in their full size. If you don't have plotter, use the following steps to print on smaller paper.</span></span>

<span data-ttu-id="46427-182">**더 작은 용지에 포스터 인쇄**</span><span class="sxs-lookup"><span data-stu-id="46427-182">**Print posters on smaller paper**</span></span>

1.  <span data-ttu-id="46427-183">Visio에서 포스터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="46427-183">Open the poster in Visio.</span></span>

2.  <span data-ttu-id="46427-184">**파일** 메뉴에서 **페이지 설정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-184">On the **File** menu, click **Page Setup**.</span></span>

3.  <span data-ttu-id="46427-185">**인쇄 설정** 탭의 **프린터 용지** 섹션에서 인쇄할 용지 크기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-185">On the **Print Setup** tab, in the **Printer paper** section, select the size of paper you want to print on.</span></span>

4.  <span data-ttu-id="46427-186">**인쇄 설정** 탭의 **확대/축소 인쇄** 섹션에서 **자동 맞춤**을 클릭하고 **1 용지 너비/1 용지 높이**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-186">On the **Print Setup** tab, in the **Print zoom** section, click **Fit to**, and then enter **1 sheet across by 1 sheet down**.</span></span>

5.  <span data-ttu-id="46427-187">**페이지 크기** 탭에서 **드로잉 내용에 맞게 크기 조정**을 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-187">On the **Page Size** tab, click **Size to fit drawing contents**, and then click **OK**.</span></span>

6.  <span data-ttu-id="46427-188">**파일** 메뉴에서 **인쇄**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46427-188">On the **File** menu, click **Print**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

