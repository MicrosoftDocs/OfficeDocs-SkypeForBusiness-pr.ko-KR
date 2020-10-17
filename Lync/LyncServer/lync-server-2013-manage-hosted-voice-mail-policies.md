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
ms.openlocfilehash: 315bd908b8369a107c4c9ddedcf5ce9911fc48f0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534505"
---
# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="189a7-102">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</span><span class="sxs-lookup"><span data-stu-id="189a7-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="189a7-103">_**마지막으로 수정 된 항목:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="189a7-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="189a7-104">*호스팅된 음성 메일 정책은* Lync Server 2013 Exum 라우팅 응용 프로그램에 사서함이 호스팅된 Exchange 서비스에 있는 사용자에 대해 통화를 라우팅할 위치에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="189a7-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="189a7-p101">일반적으로는 호스팅된 음성 메일 정책만 있으면 됩니다. 대부분의 경우 모든 요구를 충족하기 위해 글로벌 정책을 수정할 수 있습니다. 사이트 범위를 사용하여 정책을 만드는 경우 지정된 사이트에 속한 모든 사용자에 대해 자동으로 해당 정책이 지정됩니다. 사용자별 범위를 사용하여 정책을 만드는 경우에는 해당 정책을 사용자, 그룹 및 대화 상대 개체에 대해 명시적으로 지정해야 합니다. 호스팅된 음성 메일 정책을 여러 개 배포할 수는 있지만, 이렇게 하는 경우에는 사용자별로 정책을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="189a7-p101">Typically, only one hosted voice mail policy is required. In many cases, you can modify the global policy to meet all your needs. If you create a policy with site scope, it is assigned automatically to all users homed at the specified site. If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects. It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="189a7-110">호스팅된 음성 메일 정책을 계획 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [hosted voice mail 정책도 Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="189a7-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="189a7-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="189a7-111">In This Section</span></span>

  - [<span data-ttu-id="189a7-112">Lync Server 2013에서 호스팅된 글로벌 음성 메일 정책 수정</span><span class="sxs-lookup"><span data-stu-id="189a7-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="189a7-113">Lync Server 2013에서 사이트 수준 호스팅된 음성 메일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="189a7-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="189a7-114">Lync Server 2013에서 사용자별 호스팅 음성 메일 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="189a7-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="189a7-115">Lync Server 2013에서 사용자별 호스팅 음성 메일 정책 할당</span><span class="sxs-lookup"><span data-stu-id="189a7-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

