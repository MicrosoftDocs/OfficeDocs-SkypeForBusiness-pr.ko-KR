---
title: 'Lync Server 2013: 파킹 통화에 대 한 전화 번호 확장명 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a0fd55b851715fe8aef238797392af6317dff0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="d0289-102">Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성</span><span class="sxs-lookup"><span data-stu-id="d0289-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0289-103">_**마지막으로 수정한 주제:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="d0289-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="d0289-104">통화 공원 응용 프로그램은 통화 공원 표에서 내선 번호를 사용 하 여 통화를 파킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0289-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="d0289-105">조직에서 파킹 통화를 위해 예약한 내선 번호 범위를 사용 하 여 통화 공원 궤도 테이블을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0289-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="d0289-106">이 내선 번호는 가상 내선 번호여야 합니다(즉, 이 번호에 할당된 사용자나 전화가 없어야 함).</span><span class="sxs-lookup"><span data-stu-id="d0289-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="d0289-107">통화 공원 응용 프로그램을 배포 하 고 구성 하는 각 Lync Server 풀에는 하나 이상의 궤도 범위가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0289-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="d0289-108">궤도 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0289-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d0289-109">통화 공원을 사용 하려면 먼저 음성 정책에서 <STRONG>통화 대기 사용</STRONG> 확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0289-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="d0289-110">이 옵션은 기본적으로 선택 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0289-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d0289-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d0289-111">In This Section</span></span>

  - [<span data-ttu-id="d0289-112">Lync Server 2013에서 통화 공원 궤도 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d0289-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="d0289-113">Lync Server 2013에서 통화 공원 궤도 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="d0289-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

