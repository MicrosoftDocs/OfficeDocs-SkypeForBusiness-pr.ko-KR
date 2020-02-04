---
title: 'Lync Server 2013: 모바일 클라이언트 배포 프로세스'
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
ms.openlocfilehash: e6beaeac91dae0ff5fbf755c4ccb33cae288df75
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="61e7f-102">Lync Server 2013의 모바일 클라이언트 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="61e7f-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61e7f-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="61e7f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="61e7f-104">Microsoft Lync Server 2013의 배포가 완료 된 후 사용자는 모바일 마켓플레이스에서 특정 장치에 사용 하는 데 익숙한 Lync 2013 앱을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="61e7f-105">Lync 모바일 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="61e7f-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61e7f-106">단계의</span><span class="sxs-lookup"><span data-stu-id="61e7f-106">Phase</span></span></th>
<th><span data-ttu-id="61e7f-107">방법은</span><span class="sxs-lookup"><span data-stu-id="61e7f-107">Steps</span></span></th>
<th><span data-ttu-id="61e7f-108">필요한</span><span class="sxs-lookup"><span data-stu-id="61e7f-108">Permissions</span></span></th>
<th><span data-ttu-id="61e7f-109">설명서</span><span class="sxs-lookup"><span data-stu-id="61e7f-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61e7f-110">설정 전 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="61e7f-111">Lync Server 2013 배포를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="61e7f-112">인증서 요구 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="61e7f-113">관리자</span><span class="sxs-lookup"><span data-stu-id="61e7f-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="61e7f-114">서버 계획 설명서의 <a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013에서 이동성을 계획</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="61e7f-115">서버 배포 설명서의 <a href="lync-server-2013-deploying-mobility.md">Lync Server 2013에서 이동성을 배포</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="61e7f-116">서버 계획 설명서의 <a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013에 대 한 인증서 인프라 요구 사항</a></span><span class="sxs-lookup"><span data-stu-id="61e7f-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e7f-117">Lync 응용 프로그램을 테스트 장치에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="61e7f-118">필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="61e7f-119">모바일 장치와 관련 된 마켓플레이스에서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="61e7f-120">관리자</span><span class="sxs-lookup"><span data-stu-id="61e7f-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="61e7f-121"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우 모바일 장치에 대 한 설치 지침</span><span class="sxs-lookup"><span data-stu-id="61e7f-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e7f-122">클라이언트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="61e7f-123">로그인 설정 및 서버 정보를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="61e7f-124">관리자</span><span class="sxs-lookup"><span data-stu-id="61e7f-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="61e7f-125"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트 배포</a></span><span class="sxs-lookup"><span data-stu-id="61e7f-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61e7f-126">모바일 시나리오를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="61e7f-127">인스턴트 메시지 (IM) 및 현재 상태를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="61e7f-128">전화 걸기 회의를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="61e7f-129">회사 디렉터리에서 연락처를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="61e7f-130">푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="61e7f-131">관리자</span><span class="sxs-lookup"><span data-stu-id="61e7f-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="61e7f-132"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우 모바일 장치에 대 한 확인 지침</span><span class="sxs-lookup"><span data-stu-id="61e7f-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61e7f-133">휴대 전화에 Lync 응용 프로그램을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="61e7f-134">필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="61e7f-135">모바일 장치와 관련 된 마켓플레이스에서 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="61e7f-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="61e7f-136">사용자</span><span class="sxs-lookup"><span data-stu-id="61e7f-136">User</span></span></p></td>
<td><p><span data-ttu-id="61e7f-137"><a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013에서 모바일 클라이언트를 배포</a>하는 경우 모바일 장치에 대 한 설치 지침</span><span class="sxs-lookup"><span data-stu-id="61e7f-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

