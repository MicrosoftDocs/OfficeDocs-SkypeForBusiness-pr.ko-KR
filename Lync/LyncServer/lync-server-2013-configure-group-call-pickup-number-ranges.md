---
title: 'Lync Server 2013: 그룹 통화 픽업 번호 범위 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbcbf05fbb73e2023b48bdb1f7e74ecdee6a36bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="799d3-102">Lync Server 2013에서 그룹 통화 픽업 번호 범위 구성</span><span class="sxs-lookup"><span data-stu-id="799d3-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="799d3-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="799d3-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="799d3-104">그룹 통화 픽업는 통화 공원 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="799d3-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="799d3-105">그룹 통화 픽업을 배포 하는 경우 통화 픽업 그룹 번호로 지정 된 전화 번호 범위를 사용 하 여 통화 공원 궤도 테이블을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="799d3-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="799d3-106">이러한 그룹 번호는 다른 사용자에 게 연결 되는 통화를 선택 하기 위해 사용자가 전화를 거는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="799d3-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="799d3-107">통화 공원 번호와 같은 통화 픽업 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="799d3-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="799d3-108">그룹 통화 픽업을 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="799d3-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="799d3-109">그룹 번호 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="799d3-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="799d3-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="799d3-110">In This Section</span></span>

  - [<span data-ttu-id="799d3-111">Lync Server 2013에서 그룹 통화 픽업 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="799d3-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="799d3-112">Lync Server 2013에서 그룹 통화 픽업 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="799d3-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

