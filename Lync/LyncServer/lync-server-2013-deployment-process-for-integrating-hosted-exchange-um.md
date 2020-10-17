---
title: 'Lync Server 2013: 호스팅된 Exchange UM 통합을 위한 배포 프로세스'
description: 'Lync Server 2013: 호스팅된 Exchange UM 통합을 위한 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542614"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="a4b5b-103">호스팅된 Exchange UM과 Lync Server 2013의 통합을 위한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="a4b5b-103">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4b5b-104">_**마지막으로 수정 된 항목:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="a4b5b-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="a4b5b-105">Lync Server 2013을 호스팅된 Exchange UM (통합 메시징)과 통합 하기 위한 효과적인 계획을 사용 하려면 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-105">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="a4b5b-106">Lync Server 2013과 호스팅된 Exchange UM의 통합을 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a4b5b-106">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="a4b5b-107">통합 프로세스 중 필요한 단계</span><span class="sxs-lookup"><span data-stu-id="a4b5b-107">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="a4b5b-108">호스팅된 Exchange UM과의 통합을 위한 배포 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a4b5b-108">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="a4b5b-109">통합 프로세스를 시작 하려면 먼저 Lync Server 2013 (최소, 프런트 엔드 풀 또는 Standard Edition 서버),에 지 서버 및 Lync 2013 또는 Lync 2010 클라이언트를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-109">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="a4b5b-110">통합 프로세스</span><span class="sxs-lookup"><span data-stu-id="a4b5b-110">Integration Process</span></span>

<span data-ttu-id="a4b5b-111">다음 표에서는 호스팅된 Exchange UM 통합 프로세스에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-111">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="a4b5b-112">배포 단계에 대 한 자세한 내용은 배포 설명서의 [호스팅된 EXCHANGE UM에서 Lync Server 2013 users 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-112">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4b5b-113">단계</span><span class="sxs-lookup"><span data-stu-id="a4b5b-113">Phase</span></span></th>
<th><span data-ttu-id="a4b5b-114">단계</span><span class="sxs-lookup"><span data-stu-id="a4b5b-114">Steps</span></span></th>
<th><span data-ttu-id="a4b5b-115">권한 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a4b5b-115">Rights and permissions</span></span></th>
<th><span data-ttu-id="a4b5b-116">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="a4b5b-116">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4b5b-117">에 지 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-117">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a4b5b-118">페더레이션을 위해에 지 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-118">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="a4b5b-119">에 지 서버에 데이터를 수동으로 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-119">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="a4b5b-120">에 지 서버에서 호스팅 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-120">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a4b5b-121">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a4b5b-121">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a4b5b-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">호스팅된 Exchange UM과의 통합을 위해에 지 서버 구성</a></span><span class="sxs-lookup"><span data-stu-id="a4b5b-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b5b-123">호스팅된 음성 메일 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-123">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a4b5b-124">글로벌 호스트 된 음성 메일 정책을 수정 하거나 사이트 또는 Per-User 범위를 사용 하 여 호스팅된 새 음성 메일 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-124">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="a4b5b-125">Per-User 범위가 있는 정책에 대해 사용자 또는 그룹에 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-125">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a4b5b-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a4b5b-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a4b5b-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</a></span><span class="sxs-lookup"><span data-stu-id="a4b5b-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4b5b-128">사용자가 호스팅된 음성 메일을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-128">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a4b5b-129">사서함이 호스팅된 Exchange 서비스에 있는 사용자에 대 한 사용자 계정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-129">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a4b5b-130">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a4b5b-130">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a4b5b-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013에서 호스팅된 음성 메일에 대해 사용자를 사용 하도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="a4b5b-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4b5b-132">호스팅된 대화 상대 개체를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-132">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a4b5b-133">호스팅된 Exchange UM에 대 한 자동 전화 교환 대화 상대 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-133">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="a4b5b-134">호스팅된 Exchange UM에 대 한 구독자 액세스 대화 상대 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-134">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a4b5b-135">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a4b5b-135">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a4b5b-136">연락처 Remove-CsExUmContact Set-CsExUmContact 개체를 만들거나, 수정 하거나, 제거 하려면 새 연락처 개체가 저장 된 Active Directory 조직 구성 단위에 대 한 올바른 사용 권한을 갖고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-136">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="a4b5b-137">이 사용 권한은 Grant-CsOUPermission cmdlet을 실행 하 여 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-137">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="a4b5b-138">자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4b5b-138">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="a4b5b-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013에서 호스팅된 Exchange UM에 대 한 대화 상대 개체 만들기</a></span><span class="sxs-lookup"><span data-stu-id="a4b5b-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

