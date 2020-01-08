---
title: 'Lync Server 2013: 지원되는 Active Directory 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="ad671-102">Lync Server 2013에서 지원되는 Active Directory 토폴로지</span><span class="sxs-lookup"><span data-stu-id="ad671-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad671-103">_**마지막으로 수정한 주제:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="ad671-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="ad671-104">Lync Server 2013는 Microsoft Lync Server 2010 및 Microsoft Office Communications Server 2007 R2와 동일한 Active Directory 도메인 서비스 토폴로지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="ad671-105">다음과 같은 토폴로지가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="ad671-106">단일 도메인이 있는 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-106">Single forest with single domain</span></span>

  - <span data-ttu-id="ad671-107">단일 트리 및 여러 도메인이 있는 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="ad671-108">여러 트리 및 분리 네임 스페이스가 있는 단일 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="ad671-109">중앙 포리스트 토폴로지의 여러 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="ad671-110">리소스 포리스트 토폴로지의 여러 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="ad671-111">Exchange Online을 사용 하는 Lync 리소스 포리스트 토폴로지의 여러 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="ad671-112">다음 그림은이 섹션의 일러스트레이션에 사용 된 아이콘을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="ad671-113">**토폴로지 그림의 기호**</span><span class="sxs-lookup"><span data-stu-id="ad671-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="ad671-114">토폴로지 일러스트레이션에 대 한 ![핵심](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "그림 그림")</span><span class="sxs-lookup"><span data-stu-id="ad671-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="ad671-115">단일 포리스트, 단일 도메인</span><span class="sxs-lookup"><span data-stu-id="ad671-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="ad671-116">Lync Server에서 지원 되는 가장 간단한 Active Directory 토폴로지 인 단일 도메인 포리스트는 일반적인 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="ad671-117">다음 그림은 단일 도메인 Active Directory 토폴로지에서 Lync Server 배포를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="ad671-118">**단일 도메인 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="ad671-118">**Single domain topology**</span></span>

<span data-ttu-id="ad671-119">![단일 도메인 토폴로지](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "단일 도메인 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="ad671-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="ad671-120">단일 포리스트, 여러 도메인</span><span class="sxs-lookup"><span data-stu-id="ad671-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="ad671-121">Lync Server에서 지원 되는 다른 Active Directory 토폴로지는 루트 도메인과 하나 이상의 자식 도메인으로 구성 된 단일 포리스트입니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="ad671-122">이러한 유형의 Active Directory 토폴로지에서는 사용자가 만드는 도메인이 Lync Server를 배포 하는 도메인과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="ad671-123">그러나 프런트 엔드 풀을 배포 하는 경우에는 풀의 모든 프런트 엔드 서버를 단일 도메인 내에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="ad671-124">Windows 유니버설 관리자 그룹에 대 한 Lync 서버 지원은 도메인 간 관리를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="ad671-125">다음 그림은 여러 도메인이 있는 단일 포리스트에 배포 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="ad671-126">이 그림에서 사용자 아이콘은 사용자 계정이 있는 도메인을 표시 하 고 화살표는 Lync 서버 풀이 있는 도메인을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="ad671-127">사용자 계정에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-127">User accounts include the following:</span></span>

  - <span data-ttu-id="ad671-128">Lync Server 풀과 동일한 도메인 내의 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="ad671-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="ad671-129">Lync Server 풀의 다른 도메인에 있는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="ad671-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="ad671-130">Lync Server 풀을 사용 하 여 도메인의 자식 도메인에 있는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="ad671-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="ad671-131">**도메인이 여러 개인 단일 포리스트**</span><span class="sxs-lookup"><span data-stu-id="ad671-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="ad671-132">여러(images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "도메인이 있는") 단일 포리스트에 ![여러 도메인이 있는 단일 포리스트]</span><span class="sxs-lookup"><span data-stu-id="ad671-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="ad671-133">단일 포리스트, 여러 트리</span><span class="sxs-lookup"><span data-stu-id="ad671-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="ad671-134">다중 트리 포리스트 토폴로지는 독립 트리 구조와 별도의 Active Directory 네임 스페이스를 정의 하는 둘 이상의 도메인으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="ad671-135">다음 그림은 여러 트리가 있는 단일 포리스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="ad671-136">이 그림에서 사용자 아이콘은 사용자 계정이 있는 도메인을 표시 하 고, 실선은 같은 도메인에 있는 Lync 서버 풀을 가리킵니다. 다른 트리에 있는 Lync 서버 풀을 가리키는 파선입니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="ad671-137">사용자 계정에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-137">User accounts include the following:</span></span>

  - <span data-ttu-id="ad671-138">Lync Server 풀과 동일한 도메인 내의 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="ad671-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="ad671-139">다른 도메인에 있는 사용자 계정 (그러나 같은 트리)은 Lync 서버 풀과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="ad671-140">Lync Server 풀의 다른 트리에 있는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="ad671-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="ad671-141">**트리가 여러 개인 단일 포리스트**</span><span class="sxs-lookup"><span data-stu-id="ad671-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="ad671-142">여러 트리로(images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "이루어진 단일") 포리스트 ![여러 트리로 이루어진 단일 포리스트]</span><span class="sxs-lookup"><span data-stu-id="ad671-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="ad671-143">다중 포리스트, 중앙 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="ad671-144">Lync Server는 중앙 포리스트 토폴로지에 구성 된 여러 포리스트를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="ad671-145">중앙 포리스트 토폴로지는 중앙 포리스트의 연락처 개체를 사용 하 여 다른 포리스트의 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="ad671-146">또한 중앙 포리스트는이 포리스트의 모든 사용자에 대 한 사용자 계정을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="ad671-147">MIIS (Microsoft Id 통합 서버), Microsoft Forefront Identity Manager (FIM) 2010 또는 Microsoft Id 수명 주기 관리자 (ILM) 2007 기능 팩 1 (FP1) 등의 디렉터리 동기화 제품에서 사용자 계정의 수명 주기를 관리 합니다. 조직: 포리스트 중 하나에서 새 사용자 계정을 만들거나 사용자 계정이 포리스트에서 삭제 되 면 디렉터리 동기화 제품이 중앙 포리스트의 해당 연락처를 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="ad671-148">중앙 포리스트의 장점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="ad671-149">Lync Server를 실행 하는 서버는 단일 포리스트 내에서 중앙 집중화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="ad671-150">사용자는 모든 포리스트에서 다른 사용자를 검색 하 고 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="ad671-151">사용자는 모든 포리스트에서 다른 사용자의 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="ad671-152">디렉터리 동기화 제품은 사용자 계정이 만들어지거나 제거 될 때 중앙 포리스트에서 연락처 개체의 추가 및 삭제를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="ad671-153">다음 그림은 중앙 포리스트 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="ad671-154">이 그림에는 중앙 포리스트의 Lync Server를 호스트 하는 도메인과 별도 포리스트의 각 사용자 전용 도메인 사이에 양방향 트러스트 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="ad671-155">별도의 사용자 포리스트에 있는 스키마는 확장할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="ad671-156">**중앙 포리스트 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="ad671-156">**Central forest topology**</span></span>

<span data-ttu-id="ad671-157">![중앙 포리스트 토폴로지](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "중앙 포리스트 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="ad671-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="ad671-158">다중 포리스트, 리소스 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="ad671-159">리소스 포리스트 토폴로지에서 하나의 포리스트는 Microsoft Exchange Server 및 Lync Server와 같은 서버 응용 프로그램을 실행 하는 것을 전담 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="ad671-160">리소스 포리스트는 활성 사용자 개체의 서버 응용 프로그램 및 동기화 된 표시를 호스팅하고 있지만 로그온이 지원 되는 사용자 계정은 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="ad671-161">리소스 포리스트는 사용자 개체가 상주 하는 다른 포리스트의 공유 서비스 환경 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="ad671-162">사용자 포리스트에는 리소스 포리스트와 포리스트 수준의 신뢰 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="ad671-163">이 유형의 토폴로지에서 Lync Server를 배포 하는 경우 사용자 포리스트에 있는 모든 사용자 계정에 대해 리소스 포리스트에서 사용 하지 않도록 설정 된 사용자 개체를 하나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="ad671-164">Microsoft Exchange가 이미 리소스 포리스트에 배포 되어 있는 경우 사용 하지 않도록 설정 된 사용자 계정이 이미 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="ad671-165">MIIS, Microsoft Forefront Identity Manager (FIM) 2010 또는 Microsoft Id 수명 주기 관리자 (ILM) 2007 기능 팩 1 (FP1)과 같은 디렉터리 동기화 제품은 사용자 계정의 수명 주기를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="ad671-166">사용자 포리스트 중 하나에서 새 사용자 계정을 만들거나 사용자 계정이 포리스트에서 삭제 되 면 디렉터리 동기화 제품이 리소스 포리스트의 해당 사용자 표현을 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="ad671-167">이 토폴로지를 사용 하 여 여러 포리스트를 관리 하는 조직의 서비스에 대 한 공유 인프라를 제공 하거나 다른 관리에서 Active Directory 개체의 관리를 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="ad671-168">보안상의 이유로 Active Directory 관리를 격리 해야 하는 기업은이 토폴로지를 선택 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="ad671-169">이 토폴로지는 Active Directory 스키마를 단일 포리스트 (즉, 리소스 포리스트)로 확장할 필요가 없도록 제한 하는 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="ad671-170">다음 다이어그램은 리소스 포리스트 토폴로지를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="ad671-171">**리소스 포리스트 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="ad671-171">**Resource forest topology**</span></span>

<span data-ttu-id="ad671-172">![Active Directory 리소스 포리스트 토폴로지](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 리소스 포리스트 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="ad671-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="ad671-173">Exchange Online을 사용 하는 Lync 리소스 포리스트 토폴로지의 여러 포리스트</span><span class="sxs-lookup"><span data-stu-id="ad671-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="ad671-174">이 토폴로지에서는 하나 이상의 포리스트가 온-프레미스에 있으며 Active Directory 사용자 계정 호스팅 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="ad671-175">리소스 포리스트는 오프 라인으로 배치 되며 타사 호스팅 공급자에 의해 유지 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="ad671-176">리소스 포리스트에는 온-프레미스 사용자 계정 포리스트의 사용자 계정에 대 한 동기화 된 복제 및 Lync Server 배포만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="ad671-177">로그온 할 수 있는 사용자 계정이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="ad671-178">Exchange는 Exchange Online (하이브리드)과 함께 통합 된 온-프레미스 사용자 계정 포리스트에서 배포 되거나 온-프레미스 사용자 계정에 대 한 전자 메일 서비스가 Exchange Online에서 독점적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="ad671-179">리소스 포리스트는 사용자 개체가 상주 하는 온-프레미스 Active Directory 포리스트의 공유 서비스 환경 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="ad671-180">사용자 계정 포리스트는 리소스 포리스트와 단방향 포리스트 수준의 트러스트 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="ad671-181">이 유형의 토폴로지에서 Lync Server를 배포 하는 경우 사용자 포리스트에 있는 모든 사용자 계정에 대해 리소스 포리스트에서 사용 하지 않도록 설정 된 사용자 개체를 하나 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="ad671-182">MIIS, Microsoft Forefront Identity Manager (FIM) 2010 또는 Microsoft Id 수명 주기 관리자 (ILM) 2007 기능 팩 1 (FP1)과 같은 디렉터리 동기화 제품은 사용자 계정의 수명 주기를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="ad671-183">사용자 포리스트 중 하나에서 새 사용자 계정을 만들거나 사용자 계정이 포리스트에서 삭제 되 면 디렉터리 동기화 제품이 리소스 포리스트의 해당 사용자 표현을 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad671-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="ad671-184">다중 포리스트 배포를 구성 하는 방법에 대 한 자세한 내용은 [다중 포리스트 아키텍처에서 Lync 배포 (Exchange 하이브리드을 사용 하는 파트너 호스트 Lync)](http://go.microsoft.com/fwlink/p/?linkid=513216)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad671-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

