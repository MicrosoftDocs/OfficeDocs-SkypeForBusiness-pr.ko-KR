---
title: 'Lync Server 2013: 그룹 통화 픽업 번호 범위 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47639ea1e158ce5cb4e6463b1fb953fc50412c79
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="e84fe-102">Lync Server 2013에서 그룹 통화 픽업 번호 범위 구성</span><span class="sxs-lookup"><span data-stu-id="e84fe-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e84fe-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e84fe-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e84fe-104">그룹 통화 픽업는 통화 대기 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e84fe-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="e84fe-105">그룹 통화 픽업를 배포할 때는 통화 픽업 그룹 번호로 지정 된 전화 번호 범위를 사용 하 여 통화 대기 궤도 테이블을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e84fe-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="e84fe-106">이러한 그룹 번호는 사용자가 다른 사용자에 게 신호음을 울리는 통화를 선택 하기 위해 전화를 거는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e84fe-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="e84fe-107">통화 대기 궤도 번호와 마찬가지로 call pickup 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e84fe-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="e84fe-108">그룹 통화 픽업를 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e84fe-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="e84fe-109">그룹 번호 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e84fe-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e84fe-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e84fe-110">In This Section</span></span>

  - [<span data-ttu-id="e84fe-111">Lync Server 2013에서 그룹 통화 픽업 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e84fe-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="e84fe-112">Lync Server 2013에서 그룹 통화 픽업 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="e84fe-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

