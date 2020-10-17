---
title: 소개
description: 살펴보았습니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb847c499bde077ccaf2aa050de801ceeedcc6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565284"
---
# <a name="introduction"></a><span data-ttu-id="f9c21-103">소개</span><span class="sxs-lookup"><span data-stu-id="f9c21-103">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9c21-104">_**마지막으로 수정 된 항목:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f9c21-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="f9c21-105">Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool이 라고도 함)는 다음 유형의 사용자 부하를 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-105">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9c21-106">IM(인스턴트 메시징) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="f9c21-106">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="f9c21-107">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="f9c21-107">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c21-108">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="f9c21-108">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f9c21-109">PSTN (공중 전화망) 시뮬레이션을 포함 한 VoIP (Voice over IP) 시뮬레이션이</span><span class="sxs-lookup"><span data-stu-id="f9c21-109">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c21-110">웹 액세스 클라이언트 회의</span><span class="sxs-lookup"><span data-stu-id="f9c21-110">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="f9c21-111">Microsoft Lync 2013 Attendant</span><span class="sxs-lookup"><span data-stu-id="f9c21-111">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c21-112">응답 그룹</span><span class="sxs-lookup"><span data-stu-id="f9c21-112">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="f9c21-113">메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="f9c21-113">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c21-114">주소록 다운로드 및 주소록 쿼리</span><span class="sxs-lookup"><span data-stu-id="f9c21-114">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="f9c21-115">향상 된 9-1-1 (E9-1-1) 통화 및 위치 프로필 (다이얼 플랜)</span><span class="sxs-lookup"><span data-stu-id="f9c21-115">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c21-116">멀티뷰</span><span class="sxs-lookup"><span data-stu-id="f9c21-116">MultiView</span></span></p></td>
<td><p><span data-ttu-id="f9c21-117">회의에서 여러 스트림 보기</span><span class="sxs-lookup"><span data-stu-id="f9c21-117">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f9c21-118">Lync Server 2013 스트레스 및 성능 도구는 고급 구성에서 풀 간 부하 생성 및 페더레이션을 지 원하는 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-118">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="f9c21-119">또한이 도구는 다음 클라이언트에 대 한 사용자 부하를 시뮬레이션 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-119">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="f9c21-120">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="f9c21-120">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="f9c21-121">Lync 2013 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="f9c21-121">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="f9c21-122">따라서 Lync Server 2013 스트레스 및 성능 도구는 다음과 같은 구성 요소의 테스트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-122">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="f9c21-123">Lync 2013 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="f9c21-123">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="f9c21-124">Exchange 통합 시나리오</span><span class="sxs-lookup"><span data-stu-id="f9c21-124">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="f9c21-125">Lync Server 2013 스트레스 및 성능 도구에 포함 된 응용 프로그램 및 파일</span><span class="sxs-lookup"><span data-stu-id="f9c21-125">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="f9c21-126">Lync Server 2013 스트레스 및 성능 도구에는 다음과 같은 응용 프로그램이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-126">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9c21-127">도구</span><span class="sxs-lookup"><span data-stu-id="f9c21-127">Tool</span></span></th>
<th><span data-ttu-id="f9c21-128">설명</span><span class="sxs-lookup"><span data-stu-id="f9c21-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9c21-129">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="f9c21-129">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="f9c21-130">Lync Server 2013 사용자 프로비저닝 도구</span><span class="sxs-lookup"><span data-stu-id="f9c21-130">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="f9c21-131">이 도구는 사용자 및 연락처를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-131">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c21-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="f9c21-132">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="f9c21-133">Lync Server 2013에서는 구성 도구를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-133">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="f9c21-134">이 도구는 시뮬레이션할 사용자 부하의 특성을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-134">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c21-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="f9c21-135">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="f9c21-136">Lync Server 2013 스트레스 및 성능 도구</span><span class="sxs-lookup"><span data-stu-id="f9c21-136">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="f9c21-137">LyncPerfTool은 사용자 부하를 시뮬레이션 하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-137">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c21-138">기본. tmx</span><span class="sxs-lookup"><span data-stu-id="f9c21-138">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="f9c21-139">Lync Server 2013 Logging 도구를 사용 하려면 Default .ttmx가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-139">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c21-140">예제 프로 비전 스크립트</span><span class="sxs-lookup"><span data-stu-id="f9c21-140">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="f9c21-141">이러한 예제는 특정 시나리오를 기반으로 부하 테스트 실행을 위한 토폴로지를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9c21-141">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

