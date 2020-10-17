---
title: 'Lync Server 2013: 모바일 클라이언트 배포 프로세스'
description: 'Lync Server 2013: 모바일 클라이언트 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa4e9e1d272915e06009df5c06480309ce104e0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563484"
---
# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="f029f-103">Lync Server 2013의 모바일 클라이언트 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="f029f-103">Mobile client deployment process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f029f-104">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f029f-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f029f-105">Microsoft Lync Server 2013의 배포를 완료 한 후에는 사용자가 특정 장치에서 사용 하기 위해 익숙한 모바일 마켓플레이스에서 Lync 2013 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-105">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="f029f-106">Lync 모바일 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="f029f-106">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f029f-107">단계</span><span class="sxs-lookup"><span data-stu-id="f029f-107">Phase</span></span></th>
<th><span data-ttu-id="f029f-108">단계</span><span class="sxs-lookup"><span data-stu-id="f029f-108">Steps</span></span></th>
<th><span data-ttu-id="f029f-109">권한</span><span class="sxs-lookup"><span data-stu-id="f029f-109">Permissions</span></span></th>
<th><span data-ttu-id="f029f-110">설명서</span><span class="sxs-lookup"><span data-stu-id="f029f-110">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f029f-111">설치 전 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-111">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f029f-112">Lync Server 2013 배포를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-112">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="f029f-113">인증서 요구 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-113">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f029f-114">관리자</span><span class="sxs-lookup"><span data-stu-id="f029f-114">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f029f-115">서버 계획 설명서의 <a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013에서 모바일 기능을 계획</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-115"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="f029f-116">서버 배포 설명서의 <a href="lync-server-2013-deploying-mobility.md">Lync Server 2013에서 모바일 기능을 배포</a> 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-116"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="f029f-117">서버 계획 설명서의 <a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013에 대 한 인증서 인프라 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="f029f-117"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f029f-118">테스트 장치에 Lync 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-118">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f029f-119">필수 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-119">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="f029f-120">모바일 장치별 마켓플레이스에서 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-120">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f029f-121">관리자</span><span class="sxs-lookup"><span data-stu-id="f029f-121">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f029f-122"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우의 모바일 장치 관련 설치 지침</span><span class="sxs-lookup"><span data-stu-id="f029f-122">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f029f-123">클라이언트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-123">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f029f-124">로그인 설정 및 서버 정보를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-124">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="f029f-125">관리자</span><span class="sxs-lookup"><span data-stu-id="f029f-125">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f029f-126"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트 배포</a></span><span class="sxs-lookup"><span data-stu-id="f029f-126"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f029f-127">모바일 시나리오를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-127">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f029f-128">IM (인스턴트 메시징) 및 현재 상태를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-128">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="f029f-129">전화 접속 회의를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-129">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="f029f-130">회사 디렉터리에서 대화 상대를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-130">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="f029f-131">푸시 알림을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-131">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f029f-132">관리자</span><span class="sxs-lookup"><span data-stu-id="f029f-132">Administrator</span></span></p></td>
<td><p><span data-ttu-id="f029f-133"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우의 모바일 장치 관련 확인 지침</span><span class="sxs-lookup"><span data-stu-id="f029f-133">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f029f-134">휴대폰에 Lync 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-134">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f029f-135">필수 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-135">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="f029f-136">모바일 장치별 마켓플레이스에서 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f029f-136">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="f029f-137">사용자</span><span class="sxs-lookup"><span data-stu-id="f029f-137">User</span></span></p></td>
<td><p><span data-ttu-id="f029f-138"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우의 모바일 장치 관련 설치 지침</span><span class="sxs-lookup"><span data-stu-id="f029f-138">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

