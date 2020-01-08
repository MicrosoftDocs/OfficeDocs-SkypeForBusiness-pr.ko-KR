---
title: 음성 정책, PSTN 사용 레코드 및 음성 경로 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice policies, PSTN usage records, and voice routes
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398272(v=OCS.15)
ms:contentKeyID: 48183573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbd0e6645fbc831f10b9573fe2ba9bb4400d73ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-pstn-usage-records-and-voice-routes-in-lync-server-2013"></a><span data-ttu-id="2ba95-102">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="2ba95-102">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ba95-103">_**마지막으로 수정한 주제:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="2ba95-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="2ba95-104">음성 정책, PSTN 사용 레코드 및 음성 경로는 동맹 관계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba95-104">Voice policies, PSTN usage records, and voice routes are integrally related.</span></span> <span data-ttu-id="2ba95-105">통화 기능 집합을 선택한 다음 정책을 할당 하 여 음성 정책을 할당 받은 사용자 또는 그룹에 대해 권한이 부여 된 권한을 지정 하는 PSTN 사용 레코드 집합을 설정 하 여 음성 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba95-105">You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy.</span></span> <span data-ttu-id="2ba95-106">또한 음성 경로에는 사용 하도록 승인 된 사용자와 경로를 일치 시키는 PSTN 사용 레코드도 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ba95-106">Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them.</span></span> <span data-ttu-id="2ba95-107">즉, 사용자는 일치 하는 PSTN 사용 레코드가 있는 경로를 사용 하는 호출만 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba95-107">That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>

<span data-ttu-id="2ba95-108">새 엔터프라이즈 음성 배포의 권장 워크플로는 적절 한 PSTN 사용 레코드가 포함 된 음성 정책을 구성한 다음, 각 PSTN 사용 레코드에 적절 한 경로를 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ba95-108">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2ba95-109"><EM>사용자</EM> 범위를 사용 하 여 음성 정책을 만들어 개별 사용자 또는 그룹에 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ba95-109">You can also create voice policies with <EM>user</EM> scope and assign them to individual users or groups.</span></span>



</div>

<span data-ttu-id="2ba95-110">각 작업을 수행 하는 자세한 단계는이 섹션의 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ba95-110">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2ba95-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="2ba95-111">In This Section</span></span>

  - [<span data-ttu-id="2ba95-112">Lync Server 2013에서 통화 기능 및 권한을 부여하도록 음성 정책 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="2ba95-112">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [<span data-ttu-id="2ba95-113">Lync Server 2013에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="2ba95-113">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)

  - [<span data-ttu-id="2ba95-114">Lync Server 2013에서 아웃바운드 통화에 대한 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="2ba95-114">Configuring voice routes for outbound calls in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [<span data-ttu-id="2ba95-115">Lync Server 2013에서 음성 라우팅 구성 내보내기 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="2ba95-115">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [<span data-ttu-id="2ba95-116">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="2ba95-116">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [<span data-ttu-id="2ba95-117">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="2ba95-117">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

