---
title: 'Lync Server 2013: call pickup 그룹 번호 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ddcd5ac7ac060a7ff1a295265f400ba3f95f0f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="7689a-102">Lync Server 2013에서 통화 픽업 그룹 번호 구성</span><span class="sxs-lookup"><span data-stu-id="7689a-102">Configure call pickup group numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7689a-103">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="7689a-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="7689a-104">그룹 통화 픽업는 통화 대기 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7689a-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="7689a-105">그룹 통화 픽업를 배포할 때는 통화 픽업 그룹 번호로 지정 된 전화 번호 범위를 사용 하 여 통화 대기 궤도 테이블을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7689a-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="7689a-106">이러한 그룹 번호는 사용자가 다른 사용자에 게 신호음을 울리는 통화를 선택 하기 위해 전화를 거는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7689a-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="7689a-107">통화 대기 궤도 번호와 마찬가지로 call pickup 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7689a-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="7689a-108">그룹 통화 픽업를 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7689a-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="7689a-109">그룹 번호 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7689a-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7689a-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7689a-110">In This Section</span></span>

[<span data-ttu-id="7689a-111">Lync Server 2013에서 그룹 통화 픽업 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="7689a-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

