---
title: 'Lync Server 2013: 전화 접속 회의에 대한 다이얼 플랜 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11424148db609fa8225b6c98d1de52fa360eb044
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="c7b8c-102">Lync Server 2013에서 전화 접속 회의에 대한 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="c7b8c-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7b8c-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="c7b8c-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="c7b8c-104">전화 접속 회의를 배포 하는 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 또는 그 이상의 다이얼 플랜을 만들거나 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="c7b8c-105">각 다이얼 플랜에서 하나 이상의 정규화 규칙에서 휴대폰 내선 번호를 E 164 형식의 완전 한 전화 번호로 변환 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="c7b8c-106">전화 접속 회의 사용자는 개인 id 번호 (PIN)와 전화 번호를 입력 하 여 인증 된 엔터프라이즈 사용자로 회의에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="c7b8c-107">내선 번호를 완전 한 전화 번호로 변환 하 여 사용자가 전화 내선 번호만 입력 하는 경우 인증 받을 수 있는 정규화 규칙이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="c7b8c-108">전화 접속 회의에 대 한 다이얼 플랜을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="c7b8c-109">엔터프라이즈 음성을 배포할지 여부에 관계 없이 전화 접속 회의 영역을 추가 하도록 전역 다이얼 플랜을 수정 하 고 정규화 규칙이 전화 접속 액세스 번호를 정확 하 게 변환 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="c7b8c-110">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="c7b8c-111">엔터프라이즈 음성을 배포 하지 않은 경우 전화 접속 회의 액세스 번호에 대 한 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="c7b8c-112">전화 접속 회의 지역을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="c7b8c-113">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="c7b8c-114">엔터프라이즈 음성을 배포한 경우 전화 접속 액세스 번호에 대 한 영역을 포함 하 고 적절 한 정규화 규칙을 사용 하도록 필요한 경우 Enterprise Voice dial 계획을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="c7b8c-115">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="c7b8c-116">전화 접속 액세스 번호에만 사용 되는 전용 다이얼 플랜을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="c7b8c-117">자세한 지침은 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="c7b8c-118">계획 영역에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 전화 접속 회의 요구 사항을](lync-server-2013-dial-in-conferencing-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7b8c-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c7b8c-119">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="c7b8c-119">In This Section</span></span>

  - [<span data-ttu-id="c7b8c-120">Lync Server 2013에서 다이얼 플랜 정보 보기</span><span class="sxs-lookup"><span data-stu-id="c7b8c-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="c7b8c-121">Lync Server 2013에서 다이얼 플랜 만들기</span><span class="sxs-lookup"><span data-stu-id="c7b8c-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="c7b8c-122">Lync Server 2013에서 다이얼 플랜 수정</span><span class="sxs-lookup"><span data-stu-id="c7b8c-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="c7b8c-123">Lync Server 2013에서 정규화 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="c7b8c-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

