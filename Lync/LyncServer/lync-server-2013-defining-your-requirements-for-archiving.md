---
title: 'Lync Server 2013: 보관에 대한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Archiving
ms:assetid: ce0fc0f6-7704-4b80-bf19-a1fa9818fc7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205276(v=OCS.15)
ms:contentKeyID: 48185462
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cee7269620a9525456e40604ae3f1d1c2cf33d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="ab6c2-102">Lync Server 2013에서 보관에 대한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="ab6c2-102">Defining your requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab6c2-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="ab6c2-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="ab6c2-104">조직이 준수 규정을 따라야 하는 경우 보관을 배포 하 여 Lync Server 2013 인스턴트 메시징 (IM) 및 회의 (모임)에 대 한 보관 지원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-104">If your organization must follow compliance regulations, you can deploy Archiving to enable archiving support for Lync Server 2013 instant messaging (IM) and conferencing (meetings).</span></span> <span data-ttu-id="ab6c2-105">보관할 수 있는 콘텐츠 형식에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 개요](lync-server-2013-overview-of-archiving.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-105">For details about the type of content that can be archived, see [Overview of Archiving in Lync Server 2013](lync-server-2013-overview-of-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="ab6c2-106">보관을 구현 하려면 먼저 조직의 보관 요구 사항에 맞는 방법을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-106">To implement Archiving, you need to first decide how to meet your organization’s requirements for Archiving.</span></span> <span data-ttu-id="ab6c2-107">이를 위해서는 다음을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-107">This requires determining the following:</span></span>

  - <span data-ttu-id="ab6c2-108">**보관을 배포 하는 경우**</span><span class="sxs-lookup"><span data-stu-id="ab6c2-108">**When to deploy Archiving**.</span></span> <span data-ttu-id="ab6c2-109">초기 Lync Server 2013 배포의 일부로 보관을 배포 하거나 기존 배포에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-109">You can deploy Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="ab6c2-110">토폴로지 작성기를 사용 하 여 보관을 배포 하 여 토폴로지에 추가한 다음 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-110">You deploy Archiving by using Topology Builder to add it to your topology, and then publishing the topology.</span></span>

  - <span data-ttu-id="ab6c2-111">**내부 또는 외부 통신을 보관할지 여부**.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-111">**Whether to archive internal or external communications**.</span></span> <span data-ttu-id="ab6c2-112">내부 통신 (내부 사용자 간 통신), 외부 통신 (내부 네트워크 외부에 있는 사용자를 하나 이상 포함 하는 통신) 또는 두 가지 모두에 대해 보관을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-112">You can enable archiving for internal communications (communications between internal users), external communications (communications that include at least one user outside your internal network), or both.</span></span> <span data-ttu-id="ab6c2-113">조직 전체에 대해 이러한 옵션을 지정 하거나 특정 사이트 및 풀에 대해 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-113">You can specify these options for your entire organization, or you can specify them for specific sites and pools.</span></span> <span data-ttu-id="ab6c2-114">기본적으로 두 옵션이 모두 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-114">By default, neither option is enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab6c2-115">Microsoft Exchange 통합을 사용 하 여 보관 된 데이터를 저장 하는 경우 Exchange 설정이 Lync 통신을 보관할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-115">If you use Microsoft Exchange integration to store archived data, your Exchange settings control whether Lync communications are archived.</span></span> <span data-ttu-id="ab6c2-116">배포에 여러 포리스트가 포함 된 경우 Lync Server와 Exchange 간에 설정을 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-116">If your deployment includes multiple forests, you must synchronize the settings between Lync Server and Exchange.</span></span> <span data-ttu-id="ab6c2-117">내부 또는 외부 통신을 위한 보관을 제어 하는 것은 Lync 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-117">Controlling archiving for internal or external communications is only available for Lync Policy.</span></span> <span data-ttu-id="ab6c2-118">Exchange 통합 보관의 경우 두 파일 모두 보관 되거나 보관 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-118">For Exchange-integrated archiving, both of them will be archived or not archived.</span></span>

    
    </div>

  - <span data-ttu-id="ab6c2-119">**보관을 사용 하는 이유**</span><span class="sxs-lookup"><span data-stu-id="ab6c2-119">**Why enable Archiving**.</span></span> <span data-ttu-id="ab6c2-120">전역 수준에서 전체 배포에 대 한 보관을 사용 하거나 사용 하지 않도록 설정할 수 있으며, 특정 사이트 및 사용자의 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-120">You can enable and disable Archiving for your entire deployment at a global level, and you can enable and disable Archiving for specific sites and users.</span></span> <span data-ttu-id="ab6c2-121">이러한 각 수준에서 IM 세션 보관 (피어 투 피어), 회의 (모임, 단체 세션) 또는 둘 다를 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-121">At each of these levels, you specify whether to enable archiving of IM sessions (peer-to-peer), conferences (meetings, which are multiparty sessions), or both.</span></span> <span data-ttu-id="ab6c2-122">기본적으로 보관을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-122">By default, Archiving is disabled.</span></span>

  - <span data-ttu-id="ab6c2-123">**조직의 사용자에 게 얼마나 중요 한 보관이 되는지 설명**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-123">**How critical Archiving is to users in your organization**.</span></span> <span data-ttu-id="ab6c2-124">조직에서 업무에 중요 한 보관 인 경우에는 Lync Server 2013을 중요 모드로 실행 하도록 지정할 수 있으며, 보관이 실패 하는 경우 IM 및 회의 세션을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-124">If archiving is mission-critical in your organization, you can specify that Lync Server 2013 run in critical mode, which blocks IM and conferencing sessions if archiving fails.</span></span> <span data-ttu-id="ab6c2-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-125">For example:</span></span>
    
      - <span data-ttu-id="ab6c2-126">보관 서비스가 일시적으로 데이터베이스 큐로 메시지를 보내거나 데이터베이스에 메시지를 삽입할 수 없는 경우에는 보관 지원이 복원 될 때까지 배포에서 IM 및 회의 기능이 모두 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-126">If the Archiving service is temporarily unable to send a message to the database queue or insert a message into the database), both IM and conferencing functionality are blocked in the deployment until archiving support is restored.</span></span>
    
      - <span data-ttu-id="ab6c2-127">회의 사용자가 파일을 업로드 했지만 보관 파일 저장소에 복사할 수 없는 경우에는 문제가 해결 될 때까지 배포에서 회의 기능이 차단 되지만 메신저 기능은 차단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-127">If a conferencing user uploads a file, but the file cannot be copied to the archiving file store, conferencing functionality is blocked in the deployment until the problem is resolved, but IM functionality is not blocked.</span></span>
    
    <span data-ttu-id="ab6c2-128">전역 수준, 사이트 수준 및 풀 수준에서이 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-128">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="ab6c2-129">기본적으로 중요 모드는 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-129">By default, critical mode is not enabled.</span></span>

  - <span data-ttu-id="ab6c2-130">**Microsoft Exchange 통합 사용 여부**</span><span class="sxs-lookup"><span data-stu-id="ab6c2-130">**Whether to use Microsoft Exchange integration**.</span></span> <span data-ttu-id="ab6c2-131">이 옵션은 보관 저장소를 Exchange 2013 저장소와 통합 하 여 Lync Server 보관 데이터 및 Exchange 2013 아카이브된 데이터를 Exchange에 함께 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-131">This option integrates Archiving storage with your Exchange 2013 storage, so that your Lync Server archived data and Exchange 2013 archived data are stored together in Exchange.</span></span> <span data-ttu-id="ab6c2-132">사서함이 원본 위치 유지에 저장 되어 있는 경우 Exchange 2013에 있는 사용자의 보관 데이터 저장소에 Microsoft Exchange 통합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-132">You can use Microsoft Exchange integration for storage of archiving data for users who are homed on Exchange 2013, if their mailboxes have been put on In-Place Hold.</span></span> <span data-ttu-id="ab6c2-133">Exchange 2013 배포를 보유 하 고 있지 않거나이를 통합 하지 않으려는 경우 또는 Exchange 2013에 있지 않은 Lync 사용자가 있는 경우 SQL Server를 사용 하 여 Lync 통신에서 보관 된 데이터를 저장 하 여 별도의 보관 데이터베이스를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-133">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync users who are not homed on Exchange 2013, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="ab6c2-134">전역 수준, 사이트 수준 및 풀 수준에서 Microsoft Exchange 통합 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-134">You can configure the Microsoft Exchange integration option at the global level, site level, and pool level.</span></span> <span data-ttu-id="ab6c2-135">기본적으로 Microsoft Exchange 통합은 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-135">By default, Microsoft Exchange integration is not enabled.</span></span>

  - <span data-ttu-id="ab6c2-136">**보관 된 데이터를 관리 하는 방법**입니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-136">**How archived data is to be managed**.</span></span> <span data-ttu-id="ab6c2-137">보관 데이터베이스는 장기 보존을 위한 것이 아니며 Lync Server 2013에서 보관 된 데이터에 대 한 e-검색 (검색) 솔루션을 제공 하지 않으므로 데이터를 다른 저장소로 옮겨야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-137">The archiving database is not intended for long-term retention and Lync Server 2013 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="ab6c2-138">Lync Server는 보관 된 데이터를 내보내는 데 사용할 수 있는 세션 내보내기 도구를 제공 하 고 보관 된 데이터의 검색 가능한 성적 증명서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-138">Lync Server does provide a session export tool that you can use to export archived data, and which creates searchable transcripts of the archived data.</span></span> <span data-ttu-id="ab6c2-139">전역 정책과 만드는 각 사이트 및 사용자 정책에 대해 데이터 제거를 사용 하도록 설정 하 고 다음 옵션 중 하나를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-139">For the global policy, and for each site and user policy that you create, you can enable data purging and specify one of the following options:</span></span>
    
      - <span data-ttu-id="ab6c2-140">내보낸 보관 데이터를 모두 제거 하 고 특정 일 수 후에 보관 데이터를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-140">Purge both exported archiving data and stored archiving data after a specific number of days.</span></span> <span data-ttu-id="ab6c2-141">지정할 수 있는 최소 날짜 수는 1 일입니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-141">The minimum number of days that you can specify is one day.</span></span> <span data-ttu-id="ab6c2-142">지정할 수 있는 최대 일 수는 2562 일입니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-142">The maximum number of days that you can specify is 2562 days.</span></span>
    
      - <span data-ttu-id="ab6c2-143">내보낸 보관 데이터만 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-143">Purge exported archiving data only.</span></span> <span data-ttu-id="ab6c2-144">이 옵션은 세션 내보내기 도구에서 내보내고 안전한 것으로 표시 된 모든 레코드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-144">This option purges all records that have been exported and marked as safe to delete by the session export tool.</span></span>
    
    <span data-ttu-id="ab6c2-145">전역 수준, 사이트 수준 및 풀 수준에서이 옵션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-145">You can configure this option at the global level, site level, and pool level.</span></span> <span data-ttu-id="ab6c2-146">기본적으로 제거는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-146">By default, purging is not enabled.</span></span>

<span data-ttu-id="ab6c2-147">다음 메서드를 사용 하 여 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-147">You control Archiving by using the following methods:</span></span>

  - <span data-ttu-id="ab6c2-148">**보관 정책**.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-148">**Archiving policies**.</span></span> <span data-ttu-id="ab6c2-149">하나 이상의 보관 정책을 사용 하 여 내부 및 외부 통신의 보관을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-149">You use one or more Archiving policies to enable and disable archiving of internal and external communications.</span></span> <span data-ttu-id="ab6c2-150">기본적으로 보관을 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-150">By default, no archiving is enabled.</span></span> <span data-ttu-id="ab6c2-151">기본 전역 정책을 사용 하 여 배포에서 내부 통신, 외부 통신 또는 둘 다에 대해 보관을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-151">You enable or disable Archiving for internal communications, external communications, or both in your deployment by using the default global policy.</span></span> <span data-ttu-id="ab6c2-152">전역 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-152">You cannot delete the global policy.</span></span> <span data-ttu-id="ab6c2-153">특정 사이트에 대 한 내부 및 외부 통신의 보관을 사용 하거나 사용 하지 않도록 하나 이상의 선택적 사이트 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-153">You can specify one or more optional site policies to enable or disable Archiving for internal and external communications for specific sites.</span></span> <span data-ttu-id="ab6c2-154">또한 특정 사용자 및 사용자 그룹의 보관을 사용 하거나 사용 하지 않도록 설정 하는 사용자 정책을 하나 이상 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-154">You can also specify one or more user policies to enable or disable Archiving for specific users and user groups.</span></span> <span data-ttu-id="ab6c2-155">사용자 수준 정책은 사이트 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-155">User-level policies override site policies.</span></span> <span data-ttu-id="ab6c2-156">사이트 수준 정책은 전역 수준 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-156">Site-level policies override the global-level policies.</span></span> <span data-ttu-id="ab6c2-157">사용자 수준 정책은 정책을 사용 하도록 구성 된 특정 사용자만 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-157">User-level policies are implemented only for the specific users who are configured to use the policy.</span></span> <span data-ttu-id="ab6c2-158">그룹 인스턴트 메시지와 회의는 참가자 중 한 명 이상에 대 한 정책이 보관을 사용 하도록 구성 된 경우에만 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-158">Group instant messages and conferences are archived only if a policy for at least one of the participants is configured to enable archiving.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab6c2-159">Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013 정책은 Exchange 2013 서버에 속한 모든 사용자에 대해 Lync Server 보관 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-159">If you use Microsoft Exchange integration, Exchange 2013 policies override Lync Server Archiving policies for all users homed on the Exchange 2013 servers.</span></span>

    
    </div>

  - <span data-ttu-id="ab6c2-160">**구성을 보관**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-160">**Archiving configurations**.</span></span> <span data-ttu-id="ab6c2-161">앞에서 설명한 대로 보관 정책을 사용 하 여 구성 된 내부 및 외부 통신을 보관 하는 경우를 제외 하 고는 하나 이상의 보관 구성을 사용 하 여이 항목에서 설명 하는 대부분의 보관 옵션을 지정 합니다. 이전 글머리 기호)</span><span class="sxs-lookup"><span data-stu-id="ab6c2-161">You use one or more Archiving configurations to specify most of the Archiving options that are described previously in this topic, except for enabling archiving of internal and external communications (configured using Archiving policies, as described in the previous bullet).</span></span> <span data-ttu-id="ab6c2-162">보관 구성은 기본 전역 구성과 선택적 사이트 및 풀 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-162">Archiving configurations include the default global configuration and optional site and pool configurations.</span></span> <span data-ttu-id="ab6c2-163">전역 구성은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-163">You cannot delete the global configuration.</span></span> <span data-ttu-id="ab6c2-164">풀 수준 구성은 사이트 수준 구성 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-164">Pool-level configurations override site-level configurations.</span></span> <span data-ttu-id="ab6c2-165">사이트 수준 구성은 전역 수준 구성 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-165">Site-level configurations override the global-level configuration.</span></span>

<span data-ttu-id="ab6c2-166">요구 사항 분석의 일부로 전역 보관 구성 및 전역 보관 정책을 구성 하는 방법을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-166">As part of your requirements analysis, you need to determine how to configure the global Archiving configuration and global Archiving policy.</span></span> <span data-ttu-id="ab6c2-167">또한 사이트 수준 보관 구성, 풀 수준 보관 구성, 사이트 수준 보관 정책, 사용자 수준 보관 정책에 대 한 요구 사항을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-167">You also need to determine your requirements for any site-level Archiving configurations, pool-level Archiving configurations, site-level Archiving policies, and user-level Archiving policies.</span></span>

<span data-ttu-id="ab6c2-168">하나 이상의 프런트 엔드 풀 또는 Standard Edition 서버에 대해 보관을 배포 하는 경우 배포의 다른 모든 프런트 엔드 풀 및 Standard Edition 서버에서 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-168">If you deploy Archiving for one Front End pool or Standard Edition server, you should then enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="ab6c2-169">이 작업은 통신을 보관 해야 하는 사용자가 다른 풀에서 호스트 되는 그룹 메신저 대화 또는 모임에 초대 될 수 있기 때문에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-169">You need to do this because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="ab6c2-170">대화 또는 모임이 호스팅되는 풀에서 보관을 사용할 수 없는 경우에는 모든 컨퍼런스 데이터가 보관 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-170">If archiving is not enabled on the pool where the conversation or meeting is hosted, all conference data may not be archived.</span></span> <span data-ttu-id="ab6c2-171">보관은 계속 해 서 사용할 수 있는 사용자 및 모든 메신저 메시지에 적용 되지만, 회의 콘텐츠 및 이벤트는 보관 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-171">Archiving will still work for archiving enabled users and all IM messages, but conferencing content and events may not be archived.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab6c2-172">조직의 보안 표준을 유지 하면서 관리 작업을 위임할 수 있도록 Lync Server 2013&nbsp;는 RBAC (역할 기반 액세스 제어)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-172">To enable delegation of administrative tasks while maintaining your organization's security standards, Lync Server 2013&nbsp;uses role-based access control (RBAC).</span></span> <span data-ttu-id="ab6c2-173">RBAC를 사용 하는 경우 사용자를 미리 정의 된 관리 역할에 할당 하 여 관리 권한을 부여 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-173">With RBAC, administrative privilege is granted by assigning users to predefined administrative roles.</span></span> <span data-ttu-id="ab6c2-174">Lync 보관 정책 및 보관 구성을 구성 하려면 사용자가 CsArchivingAdministrator 역할에 할당 되어야 합니다 (다른 컴퓨터에서 원격으로 저장 되지 않고 보관을 배포 하는 서버에서 직접 구성 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="ab6c2-174">To configure Lync Archiving policies and Archiving configurations, the user must be assigned to the CsArchivingAdministrator role (unless the configuration is done directly on the server where Archiving is deployed, instead of remotely from another computer).</span></span> <span data-ttu-id="ab6c2-175">RBAC에 대 한 자세한 내용은 계획 문서에서 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013의 역할 기반 액세스 제어 계획</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-175">For details about RBAC, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="ab6c2-176">배포 보관에 필요한 사용자 권한, 사용 권한 및 역할 목록은 계획 문서와 배포 설명서 모두에서 제공 되는 <A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013에서 보관에 대 한 배포 검사 목록을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-176">For a list of the user rights, permissions, and roles required for archiving deployment, see <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>, which is available in both the Planning documentation and the Deployment documentation.</span></span><BR><span data-ttu-id="ab6c2-177">Microsoft Exchange 통합을 사용 하는 경우 Exchange 정책 구성에 적절 한 관리자 권한 및 사용 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-177">If you use Microsoft Exchange integration, configuration of Exchange policies requires appropriate administrator rights and permissions.</span></span> <span data-ttu-id="ab6c2-178">자세한 내용은 Exchange 2013 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab6c2-178">For details, see the Exchange 2013 documentation.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

