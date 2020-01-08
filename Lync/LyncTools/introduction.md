---
title: 소개
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="aa569-102">소개</span><span class="sxs-lookup"><span data-stu-id="aa569-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa569-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="aa569-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="aa569-104">Lync Server 2013 스트레스 및 성능 도구 (as/Ccptool이 라고도 함)는 다음 형식의 사용자 로드를 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa569-105">인스턴트 메시지 (IM) 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="aa569-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="aa569-106">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="aa569-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa569-107">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="aa569-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="aa569-108">PSTN (공개 통신 네트워크) 시뮬레이션을 포함 한 VoIP (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="aa569-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa569-109">웹 액세스 클라이언트 회의</span><span class="sxs-lookup"><span data-stu-id="aa569-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="aa569-110">Microsoft Lync 2013 수행자</span><span class="sxs-lookup"><span data-stu-id="aa569-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa569-111">응답 그룹</span><span class="sxs-lookup"><span data-stu-id="aa569-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="aa569-112">메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="aa569-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa569-113">주소록 다운로드 및 주소록 쿼리</span><span class="sxs-lookup"><span data-stu-id="aa569-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="aa569-114">향상 된 9-1-1 (E9-1) 통화 및 위치 프로필 (다이얼 플랜)</span><span class="sxs-lookup"><span data-stu-id="aa569-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa569-115">MultiView</span><span class="sxs-lookup"><span data-stu-id="aa569-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="aa569-116">회의에서 여러 스트림 보기</span><span class="sxs-lookup"><span data-stu-id="aa569-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aa569-117">Lync Server 2013 스트레스 및 성능 도구는 고급 구성을 통해서만 교차 풀 부하 생성 및 페더레이션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="aa569-118">또한이 도구는 다음 클라이언트에 대 한 사용자 로드를 시뮬레이션 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="aa569-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="aa569-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="aa569-120">Lync 2013 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="aa569-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="aa569-121">결과적으로 Lync Server 2013 스트레스 및 성능 도구는 다음 구성 요소 테스트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="aa569-122">Lync 2013 영구 채팅</span><span class="sxs-lookup"><span data-stu-id="aa569-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="aa569-123">Exchange 통합 시나리오</span><span class="sxs-lookup"><span data-stu-id="aa569-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="aa569-124">Lync Server 2013 스트레스 및 성능 도구에 포함 된 응용 프로그램 및 파일</span><span class="sxs-lookup"><span data-stu-id="aa569-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="aa569-125">Lync Server 2013 스트레스 및 성능 도구에는 다음과 같은 응용 프로그램이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa569-126">도구</span><span class="sxs-lookup"><span data-stu-id="aa569-126">Tool</span></span></th>
<th><span data-ttu-id="aa569-127">설명</span><span class="sxs-lookup"><span data-stu-id="aa569-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa569-128">UserProvisioningTool</span><span class="sxs-lookup"><span data-stu-id="aa569-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="aa569-129">Lync Server 2013 사용자 프로비저닝 도구</span><span class="sxs-lookup"><span data-stu-id="aa569-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="aa569-130">이 도구는 사용자 및 연락처를 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa569-131">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="aa569-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="aa569-132">Lync Server 2013 부하 구성 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="aa569-133">이 도구는 시뮬레이션할 사용자 부하의 특성을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa569-134">L<c13> Cperftool .exe</span><span class="sxs-lookup"><span data-stu-id="aa569-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="aa569-135">Lync 서버 2013 스트레스 및 성능 도구.</span><span class="sxs-lookup"><span data-stu-id="aa569-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="aa569-136">L<c13> Cperftool은 사용자 부하를 시뮬레이트하는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa569-137">Default. tmx</span><span class="sxs-lookup"><span data-stu-id="aa569-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="aa569-138">Lync Server 2013 로깅 도구를 사용 하려면 Default .ttmx가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa569-139">예제 프로비저닝 스크립트</span><span class="sxs-lookup"><span data-stu-id="aa569-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="aa569-140">이러한 예제는 특정 시나리오를 기반으로 부하 테스트 실행에 대 한 토폴로지를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa569-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

