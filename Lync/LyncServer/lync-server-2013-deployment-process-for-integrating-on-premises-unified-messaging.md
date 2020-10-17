---
title: 온-프레미스 통합 메시징 통합을 위한 배포 프로세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53dcbeb362387c31a97ad1e26713b642f82b2390
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529125"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="556b3-102">온-프레미스 통합 메시징과 Lync Server 2013의 통합을 위한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="556b3-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="556b3-103">_**마지막으로 수정 된 항목:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="556b3-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="556b3-104">Exchange UM (통합 메시징)을 Lync Server 2013와 통합 하려면이 항목에서 설명 하는 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="556b3-105">또한 [온-프레미스 통합 메시징과 Lync Server 2013을 통합 하기 위한 지침](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)에 설명 된 모범 사례 계획 및 배포를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="556b3-106">이 항목에서는 lync server 2013을 배치 된 중재 서버와 함께 배포 했으며, 사용자가 Lync Server 2013를 사용할 수 있도록 설정 했으며, 배포 설명서의 [Enterprise voice In Lync server 2013](lync-server-2013-deploying-enterprise-voice.md) 에서 설명 하는 대로 enterprise voice를 사용할 수 있도록 하는 모든 배포 및 구성 단계를 수행 하지 않았다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="556b3-107">통합 메시징 통합 프로세스</span><span class="sxs-lookup"><span data-stu-id="556b3-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="556b3-108">조직의 Exchange 관리자와 함께 원활 하 고 성공적인 통합을 보장 하기 위해 각각의 작업을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="556b3-109">단계</span><span class="sxs-lookup"><span data-stu-id="556b3-109">Phase</span></span></th>
<th><span data-ttu-id="556b3-110">단계</span><span class="sxs-lookup"><span data-stu-id="556b3-110">Steps</span></span></th>
<th><span data-ttu-id="556b3-111">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="556b3-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="556b3-112">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="556b3-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="556b3-113">다음 중 하나를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="556b3-114">Microsoft Exchange Server 2007 SP2 (서비스 팩 1) 또는 최신 서비스 팩</span><span class="sxs-lookup"><span data-stu-id="556b3-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="556b3-115">Microsoft Exchange Server 2010 또는 최신 서비스 팩</span><span class="sxs-lookup"><span data-stu-id="556b3-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="556b3-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="556b3-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="556b3-117">Microsoft Exchange Server 2013을 사용 하는 경우 Lync Server 2013과 동일한 포리스트나 다른 포리스트에 다음 Exchange 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="556b3-118">클라이언트 액세스</span><span class="sxs-lookup"><span data-stu-id="556b3-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="556b3-119">메일함</span><span class="sxs-lookup"><span data-stu-id="556b3-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="556b3-120">Microsoft Exchange Server 2013 및 Exchange UM (통합 메시징)이 서로 다른 포리스트에 설치 된 경우 Lync Server 2013 포리스트를 신뢰 하도록 각 Exchange 포리스트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="556b3-121">Exchange 2010을 사용 하는 경우 Lync Server 2013과 동일한 포리스트나 다른 포리스트에 다음 Exchange 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="556b3-122">통합 메시징</span><span class="sxs-lookup"><span data-stu-id="556b3-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="556b3-123">허브 전송</span><span class="sxs-lookup"><span data-stu-id="556b3-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="556b3-124">클라이언트 액세스</span><span class="sxs-lookup"><span data-stu-id="556b3-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="556b3-125">메일함</span><span class="sxs-lookup"><span data-stu-id="556b3-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="556b3-126">Lync Server 2013 및 Exchange UM (통합 메시징)이 서로 다른 포리스트에 설치 된 경우 Lync Server 2013 포리스트를 신뢰 하도록 각 Exchange 포리스트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="556b3-127">엔터프라이즈 관리자 (조직의 첫 번째 Exchange 서버인 경우)</span><span class="sxs-lookup"><span data-stu-id="556b3-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="556b3-128">-또는-</span><span class="sxs-lookup"><span data-stu-id="556b3-128">-OR-</span></span></p>
<p><span data-ttu-id="556b3-129">Exchange 조직 관리자 (조직의 첫 번째 Exchange 서버가 아닌 경우)</span><span class="sxs-lookup"><span data-stu-id="556b3-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="556b3-130">해당 버전의 Exchange Server에 대 한 해당 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="556b3-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="556b3-131">Exchange Server 2007 배포 설명서를 참조 <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> 하세요.</span><span class="sxs-lookup"><span data-stu-id="556b3-131">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="556b3-132">Exchange Server 2010 또는 최신 서비스 팩 배포 설명서를 참조 <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> 하세요.</span><span class="sxs-lookup"><span data-stu-id="556b3-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="556b3-133">Microsoft Exchange Server 2013 계획 및 <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> 배포 위치</span><span class="sxs-lookup"><span data-stu-id="556b3-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="556b3-134">인증서를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="556b3-135">신뢰할 수 있는 루트 CA (인증 기관)에서 각 Exchange UM 서버에 대 한 인증서를 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="556b3-136">이 인증서는 Exchange UM 및 Lync Server 2013을 실행 하는 서버 간의 MTLS (상호 전송 수준 보안)를 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="556b3-137">관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="556b3-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성</a></span><span class="sxs-lookup"><span data-stu-id="556b3-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="556b3-139">새 Exchange UM SIP 다이얼 플랜을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="556b3-140">Exchange UM 서버에서 조직의 특정 배포 요구 사항에 따라 SIP 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="556b3-141">Exchange 조직 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="556b3-142">Exchange 2007 SP1 또는 최신 서비스 팩의 경우 &quot; 통합 메시징 SIP URI 다이얼 플랜을 만드는 방법을 참조 하세요 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="556b3-143">Exchange 2010 또는 최신 서비스 팩의 경우 &quot; UM 다이얼 플랜 만들기를 참조 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> 하세요.</span><span class="sxs-lookup"><span data-stu-id="556b3-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="556b3-144">Exchange 2013의 경우 통합 메시징 ()을 참조 하세요 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-144">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="556b3-145">Exchange UM SIP 다이얼 플랜에 대 한 보안 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="556b3-146">Enterprise Voice 트래픽을 암호화 하려면 <strong>sip</strong> 보안 또는 <strong>보안</strong>으로 Exchange UM SIP 다이얼 플랜의 보안 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="556b3-147">이는 환경에서 Lync Phone Edition 장치를 배포 했거나 배포할 계획인 경우에 특히 중요 한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="556b3-148">Exchange UM 통합을 사용 하는 환경에서 Lync Phone Edition 장치가 작동 하려면 Lync Server 암호화 설정이 Exchange UM 다이얼 플랜 보안 설정과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="556b3-149">자세한 내용은 배포 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="556b3-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="556b3-150">Exchange 조직 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="556b3-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성</a></span><span class="sxs-lookup"><span data-stu-id="556b3-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="556b3-152">Exchange 2007 SP1 또는 최신 서비스 팩의 경우 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="556b3-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="556b3-153">&quot;에서 통합 메시징 다이얼 플랜에 대 한 보안을 구성 하는 방법을 설명 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="556b3-154">Exchange 2010 또는 최신 서비스 팩의 경우 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="556b3-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="556b3-155">&quot;UM 다이얼 플랜에 대해 VoIP 보안을 구성 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="556b3-156">Exchange 2013의 경우 통합 메시징 ()을 참조 하세요 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-156">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="556b3-157">Exchange UM SIP 다이얼 플랜에 통합 메시징 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="556b3-158">새로 설치한 통합 메시징 서버에서 수신 전화에 응답 하 고이를 처리할 수 있도록 하려면 통합 메시징 서버를 UM 다이얼 플랜에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="556b3-159">이 경우에는 Exchange UM SIP 다이얼 플랜에 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="556b3-160">관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-160">Administrators</span></span></p>
<p><span data-ttu-id="556b3-161">Exchange Server 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="556b3-162">Exchange 2007 SP1 또는 최신 서비스 팩의 경우 다음 &quot; 위치에서 통합 메시징 서버를 다이얼 플랜에 추가 하는 방법을 참조 하세요 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="556b3-163">Exchange 2010 또는 최신 서비스 팩의 경우 &quot; UM 서버의 속성 보기 또는 구성을 참조 하십시오 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="556b3-164">Exchange 2013의 경우 통합 메시징 ()을 참조 하세요 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-164">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="556b3-165">SIP 주소를 사용 하 여 사서함을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="556b3-166">Exchange UM 기능을 사용할 Enterprise Voice 사용자의 사서함에 SIP 주소를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="556b3-167">Lync Server 2013 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="556b3-168">Exchange 받는 사람 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="556b3-169">Exchange 2007 SP1 또는 최신 서비스 팩의 경우 &quot; UM-Enabled 사용자에 대 한 SIP 주소를 추가, 제거 또는 수정 하는 방법에 대 한 자세한 내용은를 참조 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> 하세요.</span><span class="sxs-lookup"><span data-stu-id="556b3-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="556b3-170">Exchange 2010 또는 최신 서비스 팩의 경우 &quot; UM-Enabled 사용자에 대 한 SIP 주소 수정를 &quot; 참조 <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> 하세요.</span><span class="sxs-lookup"><span data-stu-id="556b3-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="556b3-171">Exchange 2013의 경우 통합 메시징 ()을 참조 하세요 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-171">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="556b3-172">exchucutil.ps1 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="556b3-173">Exchange UM 서비스를 실행 하는 서버에서 Exchange 관리 셸을 열고 다음 작업을 수행 하는 exchucutil.ps1 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="556b3-174">Lync Server 2013에 게 이전 작업에서 만든 SIP 다이얼 플랜을 사용 하 여 Exchange UM Active Directory 도메인 서비스 개체를 읽을 수 있는 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="556b3-175">Enterprise Voice를 사용할 수 있는 사용자를 호스트 하는 각 Lync Server 2013 Enterprise Edition 풀 또는 Standard Edition Server에 대해 Active Directory에 통합 메시징 IP 게이트웨이 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="556b3-176">각 게이트웨이에 대해 Exchange UM 헌트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="556b3-177">헌트 그룹 파일럿 식별자는 해당 게이트웨이와 연결 된 다이얼 플랜의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="556b3-178">두 개 이상의 다이얼 플랜이 있으면 1:1 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="556b3-179">Exchange 조직 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="556b3-180">Exchange 받는 사람 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="556b3-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 용 Microsoft Exchange에서 통합 메시징 구성</a></span><span class="sxs-lookup"><span data-stu-id="556b3-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="556b3-182">Lync Server 2013 다이얼 플랜을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="556b3-183">Exchange 2007 SP1 또는 최신 서비스 팩 이나 Exchange 2010와 통합 하는 경우 Exchange UM 다이얼 플랜 정규화 된 도메인 이름 (FQDN)과 일치 하는 이름을 사용 하 여 새 Enterprise Voice 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="556b3-184">각 UM 다이얼 플랜에 대해이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="556b3-185">Exchange 2010 s p 1과 통합 하는 경우 적절 한 글로벌/사이트 수준 또는 풀 수준의 Enterprise Voice 다이얼 플랜이 구성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="556b3-186">Exchange 2010 s p 1과 통합 하는 경우 Lync Server 다이얼 플랜 및 Exchange UM SIP 다이얼 플랜 이름이 일치 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="556b3-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="556b3-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="556b3-188"><a href="lync-server-2013-configuring-dial-plans.md">Lync Server 2013에서 다이얼 플랜 구성</a></span><span class="sxs-lookup"><span data-stu-id="556b3-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="556b3-189">Exchange UM 통합 도구를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="556b3-190">Lync Server 2013에서 다음을 실행 <strong>ocsumutil.exe</strong>합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="556b3-191">구독자 액세스 및 자동 전화 교환 대화 상대 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="556b3-192">Exchange UM 다이얼 플랜 FQDN과 일치 하는 이름의 Enterprise Voice 다이얼 플랜이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="556b3-193">Exchange 2010 SP1 이상을 실행 하는 경우 다이얼 플랜 이름이 일치 하지 않아도 되며,이에 대 한 도구의 경고는 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="556b3-194">이 도구는 Exchange UM 설정에 대 한 Active Directory를 검사 하 고 Lync Server 2013 관리자가 연락처 개체를 보고, 만들고, 편집할 수 있도록 하는 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="556b3-195">RTCUniversalServerAdmins <em>및</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="556b3-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="556b3-196">ocsumutil.exe를 성공적으로 실행 하려면 사용자가이 두 그룹 모두에 속해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="556b3-197">연락처 개체를 만들려면 ocsumutil.exe를 실행 하는 사용자에 게 새 연락처 개체가 저장 되는 Active Directory OU (조직 구성 단위)에 대 한 올바른 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="556b3-198">이 사용 권한은 <STRONG>부여-CsOUPermission</STRONG> cmdlet을 실행 하 여 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="556b3-199">자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="556b3-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="556b3-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Microsoft Exchange Server의 통합 메시징과 함께 작동 하도록 Lync Server 2013 구성</a></span><span class="sxs-lookup"><span data-stu-id="556b3-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="556b3-201">필요한 경우 다른 Enterprise Voice 구성 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="556b3-202">서버 또는 사용자에 대해 Enterprise Voice 설정을 아직 구성 하지 않은 경우 다음 중 하나 이상을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="556b3-203">배포 및 구성</span><span class="sxs-lookup"><span data-stu-id="556b3-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="556b3-204">공중 전화망 (PSTN) 게이트웨이 및 중재 서버</span><span class="sxs-lookup"><span data-stu-id="556b3-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="556b3-205">음성 정책, PSTN 사용 레코드 및 아웃 바운드 통화 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="556b3-206">사용자가 Enterprise Voice를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="556b3-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="556b3-207">필요한 경우 다이얼 플랜을 사용 하 여 특정 사용자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="556b3-208">사용 하도록 설정한 Enterprise Voice 기능에 따라 다른 구성 단계가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="556b3-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="556b3-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="556b3-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="556b3-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="556b3-211">다음 섹션의 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="556b3-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="556b3-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성</a></span><span class="sxs-lookup"><span data-stu-id="556b3-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="556b3-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013에서 Enterprise Voice 배포</a></span><span class="sxs-lookup"><span data-stu-id="556b3-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="556b3-214">Exchange UM에 대해 Enterprise Voice 사용자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="556b3-215">Exchange UM 서버에서 통합 메시징 사서함 정책이 만들어졌고 각 사용자에 게 고유한 내선 번호 할당이 있는지 확인 한 다음 사용자가 통합 메시징을 사용할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="556b3-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="556b3-216">Exchange 받는 사람 관리자</span><span class="sxs-lookup"><span data-stu-id="556b3-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="556b3-217">Exchange 2007 SP1 또는 최신 서비스 팩의 경우 &quot; 사용자가 통합 메시징을 사용 하도록 설정 하는 방법을 참조 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> 하세요.</span><span class="sxs-lookup"><span data-stu-id="556b3-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="556b3-218">Exchange 2010 또는 최신 서비스 팩의 경우 &quot; 사용자가 통합 메시징을 사용 하도록 설정에서를 참조 하세요 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="556b3-219">Exchange 2013의 경우 통합 메시징 ()을 참조 하세요 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="556b3-219">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

