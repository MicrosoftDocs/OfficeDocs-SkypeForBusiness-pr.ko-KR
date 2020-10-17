---
title: 'Lync Server 2013: CDR 테이블 세부 정보'
description: 'Lync Server 2013: CDR 테이블 세부 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a3dfd4ffccac2ac4a442eeb9ad9171defb41c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544394"
---
# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="0130f-103">Lync Server 2013의 CDR 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="0130f-103">CDR table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0130f-104">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0130f-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0130f-105">다음 항목에서는 각 CDR(통화 정보 기록) 데이터베이스 스키마 테이블에 있는 열에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0130f-105">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0130f-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0130f-106">In This Section</span></span>

  - [<span data-ttu-id="0130f-107">Lync Server 2013의 응용 프로그램 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-107">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="0130f-108">Lync Server 2013의 CallPriorities 순위 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-108">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="0130f-109">Lync Server 2013의 CallType 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-109">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="0130f-110">Lync Server 2013의 ClientVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-110">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="0130f-111">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-111">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="0130f-112">Lync Server 2013의 ConferenceMessageCount 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-112">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="0130f-113">Lync Server 2013의 회의 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-113">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="0130f-114">Lync Server 2013의 ConferenceSessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-114">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="0130f-115">Lync Server 2013의 ConferenceUris 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-115">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="0130f-116">Lync Server 2013의 ContentTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-116">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="0130f-117">Lync Server 2013의 DeRegisterType 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-117">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="0130f-118">Lync Server 2013의 Devices 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-118">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="0130f-119">Lync Server 2013의 Dialogs 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-119">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="0130f-120">Lync Server 2013의 EdgeServers 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-120">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="0130f-121">Lync Server 2013의 ErrorCategory 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-121">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="0130f-122">Lync Server 2013의 ErrorDef 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-122">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="0130f-123">Lync Server 2013의 ErrorReport 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-123">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="0130f-124">Lync Server 2013의 FileTransfers 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-124">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="0130f-125">Lync Server 2013의 FocusJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-125">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="0130f-126">Lync Server 2013의 프런트 엔드 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-126">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="0130f-127">Lync Server 2013의 게이트웨이 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-127">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="0130f-128">Lync Server 2013의 HardwareVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-128">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="0130f-129">Lync Server 2013의 IMReportSummary 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-129">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="0130f-130">Lync Server 2013의 위치 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-130">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="0130f-131">Lync Server 2013의 제조업체 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-131">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="0130f-132">Lync Server 2013의 McuJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-132">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="0130f-133">Lync Server 2013의 Mcus 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-133">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="0130f-134">Lync Server 2013의 미디어 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-134">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="0130f-135">Lync Server 2013의 MediaList 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-135">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="0130f-136">Lync Server 2013의 MediationServers 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-136">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="0130f-137">Lync Server 2013의 MSMQProcessing 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-137">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="0130f-138">Lync Server 2013의 전화 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-138">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="0130f-139">Lync Server 2013의 풀 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-139">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="0130f-140">Lync Server 2013의 ProgressReport 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-140">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="0130f-141">Lync Server 2013의 PurgeSettings 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-141">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="0130f-142">Lync Server 2013의 정합 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-142">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="0130f-143">Lync Server 2013의 역할 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-143">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="0130f-144">Lync Server 2013의 Servers 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-144">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="0130f-145">Lync Server 2013의 SessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-145">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="0130f-146">Lync Server 2013의 SIPResponseMetaData 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-146">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="0130f-147">Lync Server 2013의 Syndicators 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-147">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="0130f-148">Lync Server 2013의 SyndicatorsTenantMap 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-148">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="0130f-149">Lync Server 2013의 작업 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-149">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="0130f-150">Lync Server 2013의 테 넌 트 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-150">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="0130f-151">Lync Server 2013의 UriTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-151">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="0130f-152">Lync Server 2013의 Users 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-152">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="0130f-153">Lync Server 2013의 UserAgentDef 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-153">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="0130f-154">Lync Server 2013의 UserStatistics 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-154">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="0130f-155">Lync Server 2013의 VoipDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="0130f-155">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

