---
title: 'Lync Server 2013: 일반적인 회의 개념'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3117f07a3ffffe6b3c081b64a4ad4ba8ee6aee8a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a><span data-ttu-id="ebac4-102">Lync Server 2013의 일반적인 회의 개념</span><span class="sxs-lookup"><span data-stu-id="ebac4-102">Common conferencing concepts in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebac4-103">_**마지막으로 수정 된 항목:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="ebac4-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="ebac4-p101">모든 유형의 회의에는 몇 가지 공통적인 개념이 있습니다. 다음 섹션에서는 이러한 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-p101">Several concepts are common to all types of conferencing. These are described in the following sections.</span></span>

<div>

## <a name="policies-and-bandwidth-management"></a><span data-ttu-id="ebac4-106">정책 및 대역폭 관리</span><span class="sxs-lookup"><span data-stu-id="ebac4-106">Policies and Bandwidth Management</span></span>

<span data-ttu-id="ebac4-107">Lync Server 2013에서는 관리자가 사용자가 구성할 수 있는 모임 유형에 대 한 정책을 설정 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-107">Lync Server 2013 enables administrators to set policies for the types of meetings that users can organize.</span></span> <span data-ttu-id="ebac4-108">이렇게 하면 조직 정책을 적용하고 대역폭 사용을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-108">This helps you enforce your organization’s policies and control bandwidth usage.</span></span> <span data-ttu-id="ebac4-109">다양한 모임 정책을정의하여 개별 사용자 및 사용자 그룹에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-109">You can define a wide variety of meeting policies, and assign them to individual users and groups of users.</span></span> <span data-ttu-id="ebac4-110">또한 피어 투 피어 대화를 제어하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-110">You can also set policies that govern peer-to-peer conversations.</span></span> <span data-ttu-id="ebac4-111">회의 정책 설정에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 회의 정책](lync-server-2013-conferencing-policies.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebac4-111">For details about setting conferencing policies, see [Conferencing policies in Lync Server 2013](lync-server-2013-conferencing-policies.md) in the Operations documentation.</span></span> <span data-ttu-id="ebac4-112">대역폭 관리에 대 한 자세한 내용은 [Lync server 2013의 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md) 및 [lync server 2013의 비디오 대역폭 구성을](lync-server-2013-configuring-video-bandwidth.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebac4-112">For details about bandwidth management, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) and [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

</div>

<div>

## <a name="archiving-and-compliance-features"></a><span data-ttu-id="ebac4-113">보관 및 준수 기능</span><span class="sxs-lookup"><span data-stu-id="ebac4-113">Archiving and Compliance Features</span></span>

<span data-ttu-id="ebac4-114">Lync Server 2013에서는 조직이 규정 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-114">Lync Server 2013 provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="ebac4-115">보관 기능을 사용 하 여 모임에 제공 되는 콘텐츠 및 IM (인스턴트 메시징) 대화 및 IM 회의의 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-115">You can use the archiving abilities to archive content presented in meetings, and also the content of instant messaging (IM) conversations and IM conferences.</span></span> <span data-ttu-id="ebac4-116">자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebac4-116">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="ebac4-117">영구 채팅 서버의 규정 준수 기능을 사용 하 여 시간에 따라 지속 되는 단체 및 토픽 기반 대화를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-117">You can use compliance features of Persistent Chat Server to archive multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ebac4-118">자세한 내용은 계획 설명서에서 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebac4-118">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="monitoring-feature"></a><span data-ttu-id="ebac4-119">모니터링 기능</span><span class="sxs-lookup"><span data-stu-id="ebac4-119">Monitoring Feature</span></span>

<span data-ttu-id="ebac4-120">모니터링 서버 기능은 Lync Server 2013을 사용 하는 사용자를 추적 하는 데 사용할 수 있는 CDRs (통화 정보 기록)를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-120">The Monitoring Server feature can capture call detail records (CDRs), which you can use to track which users talk to which other users using Lync Server 2013.</span></span> <span data-ttu-id="ebac4-121">모니터링 배포 및 구성에 대 한 자세한 내용은 [Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ebac4-121">For details about deploying and configuring monitoring, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a><span data-ttu-id="ebac4-122">외부 사용자의 전화 회의 참가 설정</span><span class="sxs-lookup"><span data-stu-id="ebac4-122">Enabling External Participation in Conferences</span></span>

<span data-ttu-id="ebac4-123">외부 사용자가 초대 된 경우에도 회의에 참가할 수 있도록 하 여 Lync Server 2013 회의에 대 한 투자의 이점을 크게 높일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-123">You can greatly increase the benefits of your investment in Lync Server 2013 conferencing by enabling external users to also participate in conferences when invited.</span></span> <span data-ttu-id="ebac4-124">외부 사용자에는 다음이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-124">External users can include:</span></span>

  - <span data-ttu-id="ebac4-125">**원격 사용자**   방화벽 외부에서 랩톱 또는 기타 Lync Server 2013 장치를 사용 하는 조직의 사용자</span><span class="sxs-lookup"><span data-stu-id="ebac4-125">**Remote Users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server 2013 devices.</span></span>

  - <span data-ttu-id="ebac4-126">\*\*\*\*   사용자가 Lync Server 2013을 실행 하는 회사의 페더레이션 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-126">**Federated Users**   Users from companies you work with who also run Lync Server 2013.</span></span> <span data-ttu-id="ebac4-127">조직의 사용자가 이러한 사용자에게 쉽게 연결할 수 있도록 하려면 이러한 회사와 페더레이션 관계를 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-127">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="ebac4-128">**익명 사용자**   특정 회의에 참가 하기 위해 사용자가 특별히 초대한 기타 모든 외부 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-128">**Anonymous Users**   Any other external users who are invited specifically by your users to join specific conferences.</span></span> <span data-ttu-id="ebac4-129">회사의 모임 이끌이는 외부 사용자에게 전화 회의 초대 전자 메일을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-129">A meeting organizer in your company can send an email invitation for a conference to an external user.</span></span> <span data-ttu-id="ebac4-130">이 전자 메일에는 외부 사용자가 클릭하여 전화 회의에 참가할 수 있는 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-130">The email includes a link that the outside user can click to join the conference.</span></span>

<span data-ttu-id="ebac4-131">이러한 시나리오를 일부 또는 모두 사용 하도록 설정 하려면 Lync Server 2013 배포 및 외부 사용자 간의 보안 통신을 사용 하도록 설정 하는 데 도움이 되는에 지 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-131">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server 2013 deployment and external users.</span></span> <span data-ttu-id="ebac4-132">에 지 서버를 사용 하는 Lync Server 2013 솔루션은 VPN (가상 사설망)과 같은 다른 솔루션 보다 더 높은 수준의 미디어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-132">The Lync Server 2013 solution using Edge Servers provides higher quality media than other solutions such as a virtual private network (VPN).</span></span> <span data-ttu-id="ebac4-133">자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebac4-133">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<span data-ttu-id="ebac4-134">또한 에지 서버 배포 여부에 관계없이 사용자(조직 내부 또는 외부)가 표준 PSTN 전화에서 전화 접속을 통해 온-프레미스 오디오 회의에 참가하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-134">Additionally, whether or not you deploy Edge Servers, you can enable users (that is, either inside or outside your organization) to dial in from standard PSTN phones to join on-premises audio conferences.</span></span> <span data-ttu-id="ebac4-135">Lync Server 2013 전화 접속 회의를 배포 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-135">This is accomplished by deploying Lync Server 2013 dial-in conferencing.</span></span>

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a><span data-ttu-id="ebac4-136">모임 유형 및 클라이언트 버전 간의 호환성</span><span class="sxs-lookup"><span data-stu-id="ebac4-136">Compatibility Among Meeting Types and Client Versions</span></span>

<span data-ttu-id="ebac4-137">Lync Server 2013이 이전 버전의 Office Communications Server 및 해당 클라이언트와 상호 작용 하 게 하려면 다음 문제를 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-137">If you are going to have Lync Server 2013 interoperate with previous versions of Office Communications Server and its clients, you must be aware of the following issues:</span></span>

  - <span data-ttu-id="ebac4-138">Lync Server 2013을 사용 하는 사용자는 Live Meeting 회의를 예약 하거나이 유형의 마이그레이션된 모임을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-138">Users using Lync Server 2013 cannot schedule Live Meeting conferences, or modify any migrated meetings of this type.</span></span>

  - <span data-ttu-id="ebac4-139">Office Communications Server 2007 r 2를 실행 하는 서버에 호스트 되는 Live Meeting 회의에 참가 해야 하는 Lync Server 2013을 사용 하는 사용자는 이러한 회의에 참가 하기 위해 컴퓨터에 Live Meeting 클라이언트 (Lync Server 2013 추가)를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-139">Users using Lync Server 2013 who need to attend Live Meeting conferences hosted on servers running Office Communications Server 2007 R2 must have the Live Meeting client installed on their computer (in addition to Lync Server 2013) to attend these meetings.</span></span>

  - <span data-ttu-id="ebac4-140">Live Meeting 회의가 Lync Server 2013로 마이그레이션될 때 모임 콘텐츠는 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-140">When Live Meeting conferences are migrated to Lync Server 2013, meeting content does not migrate.</span></span> <span data-ttu-id="ebac4-141">이 콘텐츠가 필요한 경우 다시 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebac4-141">If this content is needed, it must be uploaded again.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

