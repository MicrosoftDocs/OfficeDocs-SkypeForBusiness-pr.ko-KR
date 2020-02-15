---
title: 그룹 통화 픽업 구성 선행 조건 및 사용자 권한
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
ms.openlocfilehash: d1f5387ac7c67e01e3c4473367e1256cf07181a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="c7dcd-102">Lync Server 2013의 통화 픽업 구성 선행 조건 및 사용자 권한 그룹화</span><span class="sxs-lookup"><span data-stu-id="c7dcd-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7dcd-103">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="c7dcd-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="c7dcd-104">그룹 통화 Pickup는 Enterprise Voice를 배포할 때 기본적으로 설치 되는 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c7dcd-105">이 항목에서는 구성 작업을 수행 하는 데 필요한 그룹 통화 픽업 및 사용자 권한을 구성 하기 전에 필요한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="c7dcd-106">이 섹션에서는 그룹 통화 픽업 관련 계획 설명서 ( [Lync Server 2013의 그룹 통화 픽업 계획](lync-server-2013-planning-for-group-call-pickup.md)참조)를 확인 한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="c7dcd-107">그룹 통화 픽업 구성 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="c7dcd-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="c7dcd-108">그룹 통화 픽업에는 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="c7dcd-109">응용 프로그램 서비스</span><span class="sxs-lookup"><span data-stu-id="c7dcd-109">Application service</span></span>

  - <span data-ttu-id="c7dcd-110">통화 대기 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="c7dcd-110">Call Park application</span></span>

<span data-ttu-id="c7dcd-111">이러한 구성 요소는 Enterprise Voice를 배포할 때 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="c7dcd-112">그룹 통화 픽업 구성 사용자 권한</span><span class="sxs-lookup"><span data-stu-id="c7dcd-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="c7dcd-113">다음 관리 도구를 사용 하 여 그룹 통화 픽업를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="c7dcd-114">Communications Server 관리 셸</span><span class="sxs-lookup"><span data-stu-id="c7dcd-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="c7dcd-115">SEFAUtil resource kit 도구</span><span class="sxs-lookup"><span data-stu-id="c7dcd-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="c7dcd-116">Lync Server 관리 셸을 사용 하 여 통화 대기 번호 표에 통화 픽업 그룹을 만들고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="c7dcd-117">SEFAUtil 리소스 키트 도구를 사용 하 여 통화 픽업 그룹을 할당 하 고 사용자를 위해 그룹 통화 픽업 기능을 사용 하도록 설정 하거나 사용자를 위해 그룹 통화 픽업를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="c7dcd-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="c7dcd-118">그룹 통화 픽업 구성에는 작업에 따라 다음과 같은 관리 역할이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="c7dcd-119">**CsVoiceAdministrator:** 이 관리자 역할은 모든 음성 관련 설정 및 정책을 만들고 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="c7dcd-120">**Csuseradministrator:** 이 관리자 역할은 사용자에 대 한 그룹 통화 픽업을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="c7dcd-121">또한이 관리자 역할은 모든 음성 구성에 대 한 읽기 전용 보기 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="c7dcd-122">**Csserveradministrator:** 이 관리자 역할은 서버 및 서비스를 관리, 모니터링 및 문제 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="c7dcd-123">**Csadministrator:** 이 관리자 역할은 CsVoiceAdministrator, CsServerAdministrator 및 Csserveradministrator의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c7dcd-124">관리 권한에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어에 대 한 계획</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7dcd-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7dcd-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7dcd-125">See Also</span></span>


[<span data-ttu-id="c7dcd-126">Lync Server 2013에서 Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="c7dcd-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="c7dcd-127">Lync Server 2013의 통화 관리 기능 계획</span><span class="sxs-lookup"><span data-stu-id="c7dcd-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

