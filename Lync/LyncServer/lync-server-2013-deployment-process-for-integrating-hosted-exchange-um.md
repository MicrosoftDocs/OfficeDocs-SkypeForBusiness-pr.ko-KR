---
title: 'Lync Server 2013: 호스팅된 Exchange UM 통합을 위한 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="8d739-102">호스팅된 Exchange UM과 Lync Server 2013의 통합을 위한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="8d739-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d739-103">_**마지막으로 수정한 주제:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="8d739-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="8d739-104">Lync 서버 2013와 호스팅된 Exchange 통합 메시징 (UM)을 통합 하기 위한 효과적인 계획을 위해서는 다음을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="8d739-105">Lync Server 2013을 호스트 된 Exchange UM과 통합 하기 위한 필수 조건</span><span class="sxs-lookup"><span data-stu-id="8d739-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="8d739-106">통합 프로세스 중 필요한 단계</span><span class="sxs-lookup"><span data-stu-id="8d739-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="8d739-107">호스팅된 Exchange UM과 통합 하기 위한 배포 필수 조건</span><span class="sxs-lookup"><span data-stu-id="8d739-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="8d739-108">통합 프로세스를 시작 하려면 먼저 Lync Server 2013 (최소, 프런트 엔드 풀 또는 Standard Edition 서버), Edge 서버, Lync 2013 또는 Lync 2010 클라이언트를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="8d739-109">통합 프로세스</span><span class="sxs-lookup"><span data-stu-id="8d739-109">Integration Process</span></span>

<span data-ttu-id="8d739-110">다음 표에서는 호스팅된 Exchange UM 통합 프로세스에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="8d739-111">배포 단계에 대 한 자세한 내용은 배포 설명서의 [호스팅된 EXCHANGE UM에서 Lync Server 2013 사용자에 게 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d739-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d739-112">단계의</span><span class="sxs-lookup"><span data-stu-id="8d739-112">Phase</span></span></th>
<th><span data-ttu-id="8d739-113">방법은</span><span class="sxs-lookup"><span data-stu-id="8d739-113">Steps</span></span></th>
<th><span data-ttu-id="8d739-114">권한 및 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8d739-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="8d739-115">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="8d739-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d739-116">Edge 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8d739-117">에지 서버에서 페더레이션을 사용할 수 있도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="8d739-118">Edge 서버에 데이터를 수동으로 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="8d739-119">Edge 서버에서 호스팅 공급자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8d739-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8d739-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8d739-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">호스팅된 Exchange UM과의 통합을 위한 에지 서버 구성</a></span><span class="sxs-lookup"><span data-stu-id="8d739-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d739-122">호스팅된 음성 메일 정책 구성</span><span class="sxs-lookup"><span data-stu-id="8d739-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8d739-123">글로벌 호스팅 음성 메일 정책을 수정 하거나 사이트 또는 사용자별 범위를 사용 하 여 새로 호스팅되는 음성 메일 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="8d739-124">사용자별 범위 정책에 대해 정책을 사용자 또는 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8d739-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8d739-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8d739-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책 관리</a></span><span class="sxs-lookup"><span data-stu-id="8d739-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d739-127">사용자가 호스팅된 음성 메일을 사용할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8d739-128">사서함이 호스팅된 Exchange 서비스에 속한 사용자의 사용자 계정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8d739-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8d739-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8d739-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013에서 사용자가 호스팅된 음성 사서함을 사용할 수 있도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="8d739-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d739-131">호스팅된 연락처 개체를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8d739-132">호스트 된 Exchange UM에 대 한 자동 전화 교환 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="8d739-133">호스트 된 Exchange UM에 대 한 구독자 액세스 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8d739-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8d739-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8d739-135">연락처 개체를 만들거나 수정 하거나 제거 하려면 새 연락처 개체가 저장 된 Active Directory 조직 구성 단위에 대해 Set-CsExUmContact 또는 Remove-CsExUmContact cmdlet을 실행 하는 사용자에 게 올바른 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="8d739-136">이 권한은 부여-CsOUPermission cmdlet을 실행 하 여 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d739-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="8d739-137">자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8d739-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="8d739-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013에서 호스팅된 Exchange UM에 대한 대화 상대 개체 만들기</a></span><span class="sxs-lookup"><span data-stu-id="8d739-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

