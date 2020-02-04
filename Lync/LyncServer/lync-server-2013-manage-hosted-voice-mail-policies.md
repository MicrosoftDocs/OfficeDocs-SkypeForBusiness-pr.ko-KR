---
title: 'Lync Server 2013: 호스팅된 음성 메일 정책 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434cc1eb721635f4a56be33f48802da3bc6db0e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="fd371-102">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</span><span class="sxs-lookup"><span data-stu-id="fd371-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd371-103">_**마지막으로 수정한 주제:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="fd371-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="fd371-104">*호스팅된 음성 메일 정책은* Lync Server 2013 Exum Routing application에 대 한 정보를 제공 하는데,이는 해당 사서함이 호스팅된 Exchange 서비스에 있는 사용자에 대 한 통화를 라우팅할 위치에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd371-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd371-105">일반적으로 호스팅된 음성 메일 정책은 하나만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd371-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="fd371-106">대부분의 경우 모든 요구에 맞게 전역 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd371-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="fd371-107">사이트 범위를 사용 하 여 정책을 만들면 지정 된 사이트에 속한 모든 사용자에 게 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd371-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="fd371-108">사용자별 범위를 사용 하 여 정책을 만드는 경우 사용자, 그룹 및 연락처 개체에 명시적으로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd371-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="fd371-109">여러 호스팅 음성 메일 정책을 배포할 수 있지만,이 경우 사용자 기준으로 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd371-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="fd371-110">호스팅된 음성 메일 정책 계획에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 음성 메일 정책을](lync-server-2013-hosted-voice-mail-policies.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd371-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd371-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fd371-111">In This Section</span></span>

  - [<span data-ttu-id="fd371-112">Lync Server 2013의 글로벌 호스팅 음성 메일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="fd371-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="fd371-113">Lync Server 2013에서 사이트 수준의 호스팅 음성 메일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fd371-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="fd371-114">Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="fd371-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="fd371-115">Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="fd371-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

