---
title: 'Lync Server 2013: 모바일 클라이언트 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0d0bf17fe4906d49fefd8bd319d25d1268191e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="e495e-102">Lync Server 2013의 모바일 클라이언트 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="e495e-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e495e-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e495e-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e495e-104">Microsoft Lync Server 2013의 배포가 완료 된 후 사용자는 모바일 마켓플레이스에서 특정 장치에 사용 하는 데 익숙한 Lync 2013 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="e495e-105">Lync 모바일 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="e495e-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e495e-106">단계의</span><span class="sxs-lookup"><span data-stu-id="e495e-106">Phase</span></span></th>
<th><span data-ttu-id="e495e-107">방법은</span><span class="sxs-lookup"><span data-stu-id="e495e-107">Steps</span></span></th>
<th><span data-ttu-id="e495e-108">필요한</span><span class="sxs-lookup"><span data-stu-id="e495e-108">Permissions</span></span></th>
<th><span data-ttu-id="e495e-109">설명서</span><span class="sxs-lookup"><span data-stu-id="e495e-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e495e-110">설정 전 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e495e-111">Lync Server 2013 배포를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="e495e-112">인증서 요구 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e495e-113">관리자</span><span class="sxs-lookup"><span data-stu-id="e495e-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e495e-114">서버 계획 설명서의 <a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013에서 이동성을 계획</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="e495e-115">서버 배포 설명서의 <a href="lync-server-2013-deploying-mobility.md">Lync Server 2013에서 이동성을 배포</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="e495e-116">서버 계획 설명서의 <a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013에 대 한 인증서 인프라 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="e495e-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e495e-117">Lync 응용 프로그램을 테스트 장치에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e495e-118">필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e495e-119">모바일 장치와 관련 된 마켓플레이스에서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e495e-120">관리자</span><span class="sxs-lookup"><span data-stu-id="e495e-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e495e-121"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우 모바일 장치에 대 한 설치 지침</span><span class="sxs-lookup"><span data-stu-id="e495e-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e495e-122">클라이언트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="e495e-123">로그인 설정 및 서버 정보를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e495e-124">관리자</span><span class="sxs-lookup"><span data-stu-id="e495e-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e495e-125"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트 배포</a></span><span class="sxs-lookup"><span data-stu-id="e495e-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e495e-126">모바일 시나리오를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e495e-127">인스턴트 메시지 (IM) 및 현재 상태를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="e495e-128">전화 걸기 회의를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="e495e-129">회사 디렉터리에서 연락처를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="e495e-130">푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e495e-131">관리자</span><span class="sxs-lookup"><span data-stu-id="e495e-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="e495e-132"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우 모바일 장치에 대 한 확인 지침</span><span class="sxs-lookup"><span data-stu-id="e495e-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e495e-133">휴대 전화에 Lync 응용 프로그램을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="e495e-134">필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="e495e-135">모바일 장치와 관련 된 마켓플레이스에서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e495e-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e495e-136">사용자</span><span class="sxs-lookup"><span data-stu-id="e495e-136">User</span></span></p></td>
<td><p><span data-ttu-id="e495e-137"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우 모바일 장치에 대 한 설치 지침</span><span class="sxs-lookup"><span data-stu-id="e495e-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

