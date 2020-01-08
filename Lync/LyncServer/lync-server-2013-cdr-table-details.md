---
title: 'Lync Server 2013: CDR 테이블 세부 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87e681cc25f9ed64509ff3bdb31abc5fd77101d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="dc152-102">Lync Server 2013의 CDR 테이블 세부 정보</span><span class="sxs-lookup"><span data-stu-id="dc152-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc152-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="dc152-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="dc152-104">다음 항목에서는 각 CDR (호출 정보 레코드) 데이터베이스 스키마 테이블의 열에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc152-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc152-105">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="dc152-105">In This Section</span></span>

  - [<span data-ttu-id="dc152-106">Lync Server 2013의 Application 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="dc152-107">Lync Server 2013의 CallPriorities 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="dc152-108">Lync Server 2013의 CallType 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="dc152-109">Lync Server 2013의 ClientVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="dc152-110">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="dc152-111">Lync Server 2013의 ConferenceMessageCount 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="dc152-112">Lync Server 2013의 Conferences 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="dc152-113">Lync Server 2013의 ConferenceSessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="dc152-114">Lync Server 2013의 ConferenceUris 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="dc152-115">Lync Server 2013의 ContentTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="dc152-116">Lync Server 2013의 DeRegisterType 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="dc152-117">Lync Server 2013의 Devices 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="dc152-118">Lync Server 2013의 Dialogs 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="dc152-119">Lync Server 2013의 EdgeServers 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="dc152-120">Lync Server 2013의 ErrorCategory 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="dc152-121">Lync Server 2013의 ErrorDef 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="dc152-122">Lync Server 2013의 ErrorReport 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="dc152-123">Lync Server 2013의 FileTransfers 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="dc152-124">Lync Server 2013의 FocusJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="dc152-125">Lync Server 2013의 프런트 엔드 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="dc152-126">Lync Server 2013의 Gateways 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="dc152-127">Lync Server 2013의 HardwareVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="dc152-128">Lync Server 2013의 IMReportSummary 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="dc152-129">Lync Server 2013의 Locations 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="dc152-130">Lync Server 2013의 Manufacturers 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="dc152-131">Lync Server 2013의 McuJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="dc152-132">Lync Server 2013의 Mcus 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="dc152-133">Lync Server 2013의 Media 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="dc152-134">Lync Server 2013의 MediaList 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="dc152-135">Lync Server 2013의 MediationServers 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="dc152-136">Lync Server 2013의 MSMQProcessing 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="dc152-137">Lync Server 2013의 Phones 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="dc152-138">Lync Server 2013의 Pools 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="dc152-139">Lync Server 2013의 ProgressReport 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="dc152-140">Lync Server 2013의 PurgeSettings 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="dc152-141">Lync Server 2013의 Registration 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="dc152-142">Lync Server 2013의 Roles 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="dc152-143">Lync Server 2013의 Servers 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="dc152-144">Lync Server 2013의 SessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="dc152-145">Lync Server 2013의 SIPResponseMetaData 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="dc152-146">Lync Server 2013의 Syndicators 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="dc152-147">Lync Server 2013의 SyndicatorsTenantMap 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="dc152-148">Lync Server 2013의 작업 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="dc152-149">Lync Server 2013의 Tenants 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="dc152-150">Lync Server 2013의 UriTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="dc152-151">Lync Server 2013의 Users 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="dc152-152">Lync Server 2013의 UserAgentDef 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="dc152-153">Lync Server 2013의 UserStatistics 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="dc152-154">Lync Server 2013의 VoipDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="dc152-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

