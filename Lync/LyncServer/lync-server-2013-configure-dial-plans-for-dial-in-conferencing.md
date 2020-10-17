---
title: 'Lync Server 2013: 전화 접속 회의에 대 한 다이얼 플랜을 구성 합니다.'
description: 'Lync Server 2013: 전화 접속 회의에 대 한 다이얼 플랜을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28123f905288ce35b6f470168962a3d8e6faa22b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567584"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="5ec79-103">Lync Server 2013에서 전화 접속 회의에 대 한 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="5ec79-103">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ec79-104">_**마지막으로 수정 된 항목:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="5ec79-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="5ec79-p101">전화 접속 회의를 배포할 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 이상의 다이얼 플랜을 만들거나 수정해야 합니다. 각 다이얼 플랜의 하나 이상의 정규화 규칙이 전화 내선 번호를 E.164 형식의 완전한 전화 번호로 변환하는지 확인합니다. 전화 접속 회의의 사용자는 PIN(개인 식별 번호) 및 전화 번호를 입력하여 인증된 엔터프라이즈 사용자로 전화 회의에 참가합니다. 사용자들이 전화 내선 번호를 입력할 때 사용자를 인증할 수 있도록 내선 번호를 완전한 전화 번호로 변환하는 정규화 규칙이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec79-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="5ec79-109">전화 접속 회의에 대해 다이얼 플랜을 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec79-109">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="5ec79-110">Enterprise Voice를 배포 하는지 여부에 관계 없이 전화 접속 회의 지역을 추가 하 고 정규화 규칙을 통해 전화 접속 액세스 번호를 정확 하 게 변환 하도록 전역 다이얼 플랜을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec79-110">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="5ec79-111">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ec79-111">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="5ec79-112">Enterprise Voice를 배포 하지 않은 경우 전화 접속 회의 액세스 번호에 대 한 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ec79-112">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="5ec79-113">이 경우 전화 접속 회의 지역을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec79-113">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="5ec79-114">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ec79-114">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="5ec79-115">Enterprise Voice를 배포한 경우 국가를 포함 하 고 전화 접속 액세스 번호에 대해 적절 한 정규화 규칙을 사용 하려면 Enterprise Voice 다이얼 요금제를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec79-115">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="5ec79-116">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ec79-116">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="5ec79-117">전화 접속 액세스 번호에만 사용되는 전용 다이얼 플랜을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec79-117">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="5ec79-118">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ec79-118">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="5ec79-119">영역 계획에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 전화 접속 회의 요구 사항](lync-server-2013-dial-in-conferencing-requirements.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ec79-119">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5ec79-120">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5ec79-120">In This Section</span></span>

  - [<span data-ttu-id="5ec79-121">Lync Server 2013에서 다이얼 플랜 정보 보기</span><span class="sxs-lookup"><span data-stu-id="5ec79-121">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="5ec79-122">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="5ec79-122">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="5ec79-123">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="5ec79-123">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="5ec79-124">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="5ec79-124">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

