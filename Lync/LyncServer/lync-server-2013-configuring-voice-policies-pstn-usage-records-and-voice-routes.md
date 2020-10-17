---
title: 음성 정책, PSTN 사용 레코드 및 음성 경로 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e749419cf84303cfef9d4718488a4483adecb97
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537005"
---
# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="d8435-102">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="d8435-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8435-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="d8435-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="d8435-p101">음성 정책, PSTN 사용 레코드 및 음성 경로는 완전하게 관련되어 있습니다. 음성 정책을 구성하려면 전화 걸기 기능 집합을 선택한 다음, PSTN 사용 현황 레코드 집합을 정책에 할당합니다. 그러면 음성 정책이 할당되는 사용자 또는 그룹에 대해 부여되는 권한을 지정합니다. 또한 음성 경로에도 PSTN 사용 레코드가 할당됩니다. 이 레코드는 경로 사용 권한이 부여된 사용자와 경로를 일치시키는 데 사용됩니다. 즉, 사용자는 일치하는 PSTN 사용 레코드를 가진 경로를 사용하는 전화만 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8435-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="d8435-108">새 Enterprise Voice 배포에 권장되는 워크플로는, 먼저 해당하는 PSTN 사용 레코드를 포함하는 음성 정책을 구성한 다음 각 PSTN 사용 레코드에 적절한 경로를 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8435-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d8435-109"><EM>사용자</EM> 범위를 사용하여 음성 정책을 만든 다음 개별 사용자 또는 그룹에 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8435-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="d8435-110">이러한 각 작업을 수행하는 자세한 단계는 이 섹션의 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8435-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d8435-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d8435-111">In This Section</span></span>

  - [<span data-ttu-id="d8435-112">Lync Server 2013에서 호출 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="d8435-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="d8435-113">Lync Server 2013에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="d8435-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="d8435-114">Lync Server 2013에서 아웃 바운드 통화에 대 한 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="d8435-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="d8435-115">Lync Server 2013에서 음성 라우팅 구성 내보내기 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="d8435-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="d8435-116">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="d8435-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="d8435-117">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="d8435-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

