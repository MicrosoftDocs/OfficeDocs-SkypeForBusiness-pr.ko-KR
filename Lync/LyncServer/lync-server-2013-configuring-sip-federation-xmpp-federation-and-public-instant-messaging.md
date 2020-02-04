---
title: SIP 페더레이션, XMPP 페더레이션 및 공용 메신저 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45abe0b4c32cf236912ad1a0e39f842653817e59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="2e6c7-102">Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 메신저 구성</span><span class="sxs-lookup"><span data-stu-id="2e6c7-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e6c7-103">_**마지막으로 수정한 주제:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="2e6c7-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="2e6c7-104">페더레이션, 공용 인스턴트 메시지 연결 및 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP)은 외부 사용자의 다른 클래스 (페더레이션 사용자)를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="2e6c7-105">페더레이션된 Lync Server 배포 또는 XMPP 배포의 사용자는 제한 된 서비스 집합에 액세스할 수 있으며 외부 배포에서 인증 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="2e6c7-106">원격 사용자는 Lync Server 배포의 구성원이 며 배포 시 제공 되는 모든 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2e6c7-107">AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="2e6c7-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="2e6c7-108">님이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-108">has been announced.</span></span> <span data-ttu-id="2e6c7-109">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2e6c7-110">공용 인스턴트 메시징 연결은 Lync Server 클라이언트가 Lync 2013를 사용 하 여 구성 된 공개 인스턴트 메시징 파트너에 액세스할 수 있도록 하는 특별 한 유형의 페더레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="2e6c7-111">현재 공개 인스턴트 메시징 연결 파트너는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="2e6c7-112">아메리카 온라인</span><span class="sxs-lookup"><span data-stu-id="2e6c7-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="2e6c7-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="2e6c7-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="2e6c7-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="2e6c7-114">Yahoo\!</span></span>

<span data-ttu-id="2e6c7-115">공용 인스턴트 메시징 연결 구성을 통해 Lync 사용자는 다음과 같은 방법으로 공용 인스턴트 메시징 연결 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="2e6c7-116">메신저 대화 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="2e6c7-116">IM and Presence</span></span>

  - <span data-ttu-id="2e6c7-117">Lync 클라이언트의 공개 인스턴트 메시지 연결 연락처 표시</span><span class="sxs-lookup"><span data-stu-id="2e6c7-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="2e6c7-118">대화 상대에 게 연락처와 대화를 주고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="2e6c7-119">Windows Live 사용자와의 음성 및 영상 통화</span><span class="sxs-lookup"><span data-stu-id="2e6c7-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="2e6c7-120">Lync server federation는 Lync Server 배포와 다른 Office Communications Server 2007 R2 또는 Lync Server 배포 간의 계약을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="2e6c7-121">Lync Server 페더레이션된 구성을 사용 하면 Lync 사용자가 다음과 같은 방법으로 페더레이션 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="2e6c7-122">메신저 대화 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="2e6c7-122">IM and Presence</span></span>

  - <span data-ttu-id="2e6c7-123">Lync 클라이언트에 페더레이션 대화 상대 만들기</span><span class="sxs-lookup"><span data-stu-id="2e6c7-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="2e6c7-124">XMPP federation는 확장 가능한 메시징 및 현재 상태 프로토콜을 기반으로 외부 배포를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="2e6c7-125">XMPP 구성을 사용 하면 Lync 사용자는 다음과 같은 방법으로 허용 된 XMPP 도메인 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="2e6c7-126">IM 및 현재 상태 – 사용자에만 해당</span><span class="sxs-lookup"><span data-stu-id="2e6c7-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="2e6c7-127">Lync 클라이언트에서 XMPP 페더레이션 대화 만들기</span><span class="sxs-lookup"><span data-stu-id="2e6c7-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2e6c7-128">Google 대화가 포함 된 인스턴트 메시징 페더레이션에 대해 Microsoft에서 Lync Server 2013의 XMPP 기능을 테스트 하 고 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="2e6c7-129">다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션이 지원 되는지 여부와 배포 또는 문제 해결에 대 한 권장 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="2e6c7-130">Edge 서버 외부 페더레이션, 공개 인스턴트 메시지 연결 및 XMPP 사용자 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="2e6c7-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e6c7-131">단계의</span><span class="sxs-lookup"><span data-stu-id="2e6c7-131">Phase</span></span></th>
<th><span data-ttu-id="2e6c7-132">방법은</span><span class="sxs-lookup"><span data-stu-id="2e6c7-132">Steps</span></span></th>
<th><span data-ttu-id="2e6c7-133">필요한</span><span class="sxs-lookup"><span data-stu-id="2e6c7-133">Permissions</span></span></th>
<th><span data-ttu-id="2e6c7-134">설명서</span><span class="sxs-lookup"><span data-stu-id="2e6c7-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e6c7-135">기존 Edge 배포에 추가할 옵션 결정</span><span class="sxs-lookup"><span data-stu-id="2e6c7-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-136">토폴로지 작성기를 실행 하 여 Edge 서버 설정을 편집 하 고 토폴로지를 만들고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="2e6c7-137">기존 Edge 토폴로지가 중앙 관리 저장소의 변경 내용을 Edge 서버로 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-138">Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹</span><span class="sxs-lookup"><span data-stu-id="2e6c7-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="2e6c7-139">로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 편집할 수 있지만 토폴로지를 게시 하려면 Domain Admins 그룹의 구성원 인 계정 및 RTCUniversalServerAdmins 그룹이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="2e6c7-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서 에지 및 디렉터 토폴로지 구성</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e6c7-141">설치 준비</span><span class="sxs-lookup"><span data-stu-id="2e6c7-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2e6c7-142">시스템 필수 조건이 충족 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-143">공용 인스턴트 메시징 연결, Lync Federation 및 XMPP 페더레이션을 지원 하도록 내부 및 외부 DNS 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="2e6c7-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-144">배포 하는 페더레이션 유형을 지원 하도록 방화벽에서 포트 및 프로토콜 구성</span><span class="sxs-lookup"><span data-stu-id="2e6c7-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-145">공용 인증서를 구하여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-145">Obtain and install public certificates.</span></span> <span data-ttu-id="2e6c7-146">인증서를 획득 하는 데 필요한 시간은 인증서를 발급 하는 CA (인증 기관)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="2e6c7-147">이 단계는 배포의이 시점에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="2e6c7-148">이 단계를 수행 하지 않는 경우에는 Edge Server 구성 중에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="2e6c7-149">인증서를 가져올 때까지 Edge 서버 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2e6c7-150">이러한 역할은 일반적으로 많은 작업 그룹에서 분리 되므로 조직에 따라</span><span class="sxs-lookup"><span data-stu-id="2e6c7-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">SIP, XMPP 페더레이션 및 Lync Server 2013에서 공개 인스턴트 메시지에 대 한 계획</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e6c7-152">페더레이션 시나리오에 대 한 Edge 서버 설정</span><span class="sxs-lookup"><span data-stu-id="2e6c7-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2e6c7-153">내보낸 토폴로지 구성 파일을 각 Edge 서버로 전송 하거나 복제를 완료 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="2e6c7-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-154">배포 마법사를 다시 실행 하 여 페더레이션에 대 한 지원 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="2e6c7-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-155">Edge 서버 구성</span><span class="sxs-lookup"><span data-stu-id="2e6c7-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-156">각 Edge 서버용 인증서 요청 및 설치</span><span class="sxs-lookup"><span data-stu-id="2e6c7-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-157">Edge 서버 서비스 다시 시작</span><span class="sxs-lookup"><span data-stu-id="2e6c7-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2e6c7-158">관리자 그룹</span><span class="sxs-lookup"><span data-stu-id="2e6c7-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-159"><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013에서 Lync 페더레이션 설정</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2e6c7-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013에서 공용 메신저 연결 설정</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2e6c7-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013에서 XMPP 페더레이션 설정</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e6c7-162">외부 사용자 액세스에 대 한 지원을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2e6c7-163">Lync Server 제어판 외부 사용자 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="2e6c7-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-164">페더레이션 사용자 또는 공용 사용자와의 통신을 가능 하 게 하는 외부 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="2e6c7-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-165">도메인을 허용 하거나 차단 하도록 SIP 페더레이션 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="2e6c7-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-166">공용 인스턴트 메시징 연결 공급자에 대해 SIP 페더레이션 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="2e6c7-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="2e6c7-167">XMPP 도메인 당 XMPP 페더레이션 파트너 구성</span><span class="sxs-lookup"><span data-stu-id="2e6c7-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2e6c7-168">CSAdministrator 역할에 할당 된 RTCUniversalServerAdmins group 또는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="2e6c7-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대한 지원 구성</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2e6c7-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013에서 공용 공급자용 미디어 암호화 구성</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e6c7-171">Edge 서버 구성 확인</span><span class="sxs-lookup"><span data-stu-id="2e6c7-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-172">내부 서버에서 서버 연결 및 구성 데이터 복제 확인</span><span class="sxs-lookup"><span data-stu-id="2e6c7-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-173">사용자 연결 확인을 위해 CSAdministrator 역할에 할당 된 복제, RTCUniversalServerAdmins group 또는 사용자 계정에 대 한 확인을 위해 각 유형의 페더레이션 사용자에 대 한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="2e6c7-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="2e6c7-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서 에지 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="2e6c7-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013의 예제 XMPP 구성 - Google Talk와 XMPP 페더레이션</a></span><span class="sxs-lookup"><span data-stu-id="2e6c7-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

