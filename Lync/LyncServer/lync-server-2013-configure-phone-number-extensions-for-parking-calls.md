---
title: 'Lync Server 2013: 파킹 통화에 대 한 전화 번호 내선을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8871454ed95b955558c441d567f68dd0974bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520435"
---
# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="23797-102">Lync Server 2013에서 파킹 통화에 대 한 전화 번호 확장명 구성</span><span class="sxs-lookup"><span data-stu-id="23797-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23797-103">_**마지막으로 수정 된 항목:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="23797-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="23797-104">통화 대기 응용 프로그램은 통화 대기 번호 테이블의 내선 번호로 통화 대기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23797-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="23797-105">조직에서 대기 통화를 위해 예약한 내선 번호의 범위를 사용 하 여 통화 대기 궤도 테이블을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23797-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="23797-106">이 내선 번호는 가상 내선 번호여야 합니다(즉 이 번호에 할당된 사용자나 전화가 없어야 함).</span><span class="sxs-lookup"><span data-stu-id="23797-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="23797-107">통화 대기 응용 프로그램을 배포 하 고 구성 하는 각 Lync Server 풀에는 하나 이상의 궤도 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23797-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="23797-108">궤도 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23797-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="23797-109">통화 대기를 사용 하려면 먼저 음성 정책에서 <STRONG>통화 대기 사용</STRONG> 확인란을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23797-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="23797-110">기본적으로 이 옵션은 선택되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23797-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="23797-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="23797-111">In This Section</span></span>

  - [<span data-ttu-id="23797-112">Lync Server 2013에서 통화 대기 번호 범위 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="23797-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="23797-113">Lync Server 2013에서 통화 대기 번호 범위 삭제</span><span class="sxs-lookup"><span data-stu-id="23797-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

