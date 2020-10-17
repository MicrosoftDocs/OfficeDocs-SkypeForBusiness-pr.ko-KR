---
title: 그룹 통화 픽업 구성 선행 조건 및 사용자 권한
description: 그룹 통화 픽업 구성 선행 조건 및 사용자 권한
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554454"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="f82ea-103">Lync Server 2013의 통화 픽업 구성 선행 조건 및 사용자 권한 그룹화</span><span class="sxs-lookup"><span data-stu-id="f82ea-103">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f82ea-104">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f82ea-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f82ea-105">그룹 통화 Pickup는 Enterprise Voice를 배포할 때 기본적으로 설치 되는 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-105">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f82ea-106">이 항목에서는 구성 작업을 수행 하는 데 필요한 그룹 통화 픽업 및 사용자 권한을 구성 하기 전에 필요한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-106">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="f82ea-107">이 섹션에서는 그룹 통화 픽업 관련 계획 설명서 ( [Lync Server 2013의 그룹 통화 픽업 계획](lync-server-2013-planning-for-group-call-pickup.md)참조)를 확인 한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-107">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="f82ea-108">그룹 통화 픽업 구성 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f82ea-108">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="f82ea-109">그룹 통화 픽업에는 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-109">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="f82ea-110">응용 프로그램 서비스</span><span class="sxs-lookup"><span data-stu-id="f82ea-110">Application service</span></span>

  - <span data-ttu-id="f82ea-111">통화 대기 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f82ea-111">Call Park application</span></span>

<span data-ttu-id="f82ea-112">이러한 구성 요소는 Enterprise Voice를 배포할 때 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-112">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="f82ea-113">그룹 통화 픽업 구성 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="f82ea-113">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="f82ea-114">다음 관리 도구를 사용 하 여 그룹 통화 픽업를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-114">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="f82ea-115">Communications Server 관리 셸</span><span class="sxs-lookup"><span data-stu-id="f82ea-115">Lync Server Management Shell</span></span>

  - <span data-ttu-id="f82ea-116">SEFAUtil resource kit 도구</span><span class="sxs-lookup"><span data-stu-id="f82ea-116">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="f82ea-117">Lync Server 관리 셸을 사용 하 여 통화 대기 번호 표에 통화 픽업 그룹을 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-117">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="f82ea-118">SEFAUtil 리소스 키트 도구를 사용 하 여 통화 픽업 그룹을 할당 하 고 사용자를 위해 그룹 통화 픽업 기능을 사용 하도록 설정 하거나 사용자를 위해 그룹 통화 픽업를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="f82ea-118">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="f82ea-119">그룹 통화 픽업 구성에는 작업에 따라 다음과 같은 관리 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-119">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="f82ea-120">**CsVoiceAdministrator:** 이 관리자 역할은 모든 음성 관련 설정 및 정책을 만들고 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-120">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="f82ea-121">**Csuseradministrator:** 이 관리자 역할은 사용자에 대 한 그룹 통화 픽업을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-121">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="f82ea-122">또한이 관리자 역할은 모든 음성 구성에 대 한 읽기 전용 보기 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-122">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="f82ea-123">**Csserveradministrator:** 이 관리자 역할은 서버 및 서비스를 관리, 모니터링 및 문제 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-123">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="f82ea-124">**Csadministrator:** 이 관리자 역할은 CsVoiceAdministrator, CsServerAdministrator 및 Csserveradministrator의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f82ea-124">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="f82ea-125">관리 권한에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어에 대 한 계획</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f82ea-125">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f82ea-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f82ea-126">See Also</span></span>


[<span data-ttu-id="f82ea-127">Lync Server 2013에서 Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="f82ea-127">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="f82ea-128">Lync Server 2013의 통화 관리 기능 계획</span><span class="sxs-lookup"><span data-stu-id="f82ea-128">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

