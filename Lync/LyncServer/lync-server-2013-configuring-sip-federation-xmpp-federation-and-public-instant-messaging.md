---
title: SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성
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
ms.openlocfilehash: 8d97966d0a5062b133e9802f97ff77934ba29300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="c679c-102">Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="c679c-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c679c-103">_**마지막으로 수정 된 항목:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c679c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c679c-104">페더레이션, 공용 인스턴트 메시징 연결 및 XMPP(Extensible Messaging and Presence Protocol)는 페더레이션 사용자라는 새로운 클래스의 사용자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="c679c-105">페더레이션 Lync Server 배포 또는 XMPP 배포의 사용자는 제한 된 서비스 집합에 액세스 하 고 외부 배포에서 인증을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="c679c-106">원격 사용자는 Lync Server 배포의 구성원이 며 배포에서 제공 하는 모든 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c679c-107">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="c679c-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c679c-108">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-108">has been announced.</span></span> <span data-ttu-id="c679c-109">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c679c-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="c679c-110">공용 인스턴트 메시징 연결은 lync Server 클라이언트가 Lync 2013를 사용 하 여 구성 된 공용 인스턴트 메시징 파트너에 액세스할 수 있도록 하는 특별 한 유형의 페더레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="c679c-111">현재 공용 인스턴트 메시징 연결 파트너는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="c679c-112">America Online</span><span class="sxs-lookup"><span data-stu-id="c679c-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="c679c-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="c679c-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="c679c-114">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c679c-114">Yahoo\!</span></span>

<span data-ttu-id="c679c-115">공용 인스턴트 메시징 연결 구성을 사용하면 Lync 사용자가 다음을 통해 공용 인스턴트 메시징 연결 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="c679c-116">IM 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="c679c-116">IM and Presence</span></span>

  - <span data-ttu-id="c679c-117">Lync 클라이언트에 공용 인스턴트 메시징 연결 대화 상대 표시</span><span class="sxs-lookup"><span data-stu-id="c679c-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="c679c-118">대화 상대와 개인간 IM 대화</span><span class="sxs-lookup"><span data-stu-id="c679c-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="c679c-119">Windows Live 사용자와 오디오 및 비디오 통화</span><span class="sxs-lookup"><span data-stu-id="c679c-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="c679c-p104">Lync Server 페더레이션은 조직의 Lync Server 배포와 다른 Office Communications Server 2007 R2 또는 Lync Server 배포 간의 규약을 정의합니다. 페더레이션 구성을 사용하면 Lync 사용자가 다음을 통해 페더레이션 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="c679c-122">IM 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="c679c-122">IM and Presence</span></span>

  - <span data-ttu-id="c679c-123">Lync 클라이언트에 페더레이션 대화 상대 만들기</span><span class="sxs-lookup"><span data-stu-id="c679c-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="c679c-p105">XMPP 페더레이션은 XMPP(eXtensible Messaging and Presence Protocol)을 기반으로 외부 배포를 정의합니다. XMPP 구성을 사용하면 Lync 사용자가 다음을 통해 허용된 XMPP 도메인 사용자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="c679c-126">IM 및 현재 상태 – 개인간에만 가능</span><span class="sxs-lookup"><span data-stu-id="c679c-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="c679c-127">Lync 클라이언트에서 XMPP 페더레이션 연락처 만들기</span><span class="sxs-lookup"><span data-stu-id="c679c-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c679c-128">Lync Server 2013의 XMPP 기능은 Google 대화를 사용한 인스턴트 메시징 페더레이션을 위해 Microsoft에서 테스트 하 고 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="c679c-129">다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션과 모든 배포 또는 문제 해결 권장 사항을 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="c679c-130">에지 서버 외부 페더레이션, 공용 인스턴트 메시징 연결 및 XMPP 사용자 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="c679c-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c679c-131">단계</span><span class="sxs-lookup"><span data-stu-id="c679c-131">Phase</span></span></th>
<th><span data-ttu-id="c679c-132">단계</span><span class="sxs-lookup"><span data-stu-id="c679c-132">Steps</span></span></th>
<th><span data-ttu-id="c679c-133">권한</span><span class="sxs-lookup"><span data-stu-id="c679c-133">Permissions</span></span></th>
<th><span data-ttu-id="c679c-134">설명서</span><span class="sxs-lookup"><span data-stu-id="c679c-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c679c-135">기존 에지 배포에 추가할 옵션 결정</span><span class="sxs-lookup"><span data-stu-id="c679c-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="c679c-136">토폴로지 작성기를 실행 하 여에 지 서버 설정을 편집 하 고 토폴로지를 만들고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="c679c-137">기존에 지 토폴로지가 중앙 관리 저장소에서에 지 서버로 변경 내용을 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="c679c-138">Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹</span><span class="sxs-lookup"><span data-stu-id="c679c-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="c679c-139">로컬 사용자 그룹의 구성원인 계정을 사용하여 토폴로지를 편집할 수 있지만 토폴로지를 게시하려면 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원인 계정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="c679c-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013에서에 지 및 디렉터 토폴로지 구축</a></span><span class="sxs-lookup"><span data-stu-id="c679c-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c679c-141">설치 준비</span><span class="sxs-lookup"><span data-stu-id="c679c-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c679c-142">시스템 필수 구성 요소를 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="c679c-143">공용 인스턴트 메시징 연결, Lync 페더레이션 및 XMPP 페더레이션을 지원하도록 내부/외부 DNS 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="c679c-144">배포하려는 페더레이션 유형을 지원하도록 방화벽의 포트와 프로토콜을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="c679c-p108">공용 인증서를 얻어 설치합니다. 인증서를 얻는 데 소요되는 시간은 인증서를 발급하는 CA(인증 기관)에 따라 다릅니다. 이 시점에서는 이 단계가 배포의 선택 사항이지만 이 시점에 이 단계를 수행하지 않을 경우 에지 서버 구성 중에 수행해야 합니다. 인증서를 얻어야만 에지 서버 서비스를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c679c-150">일반적으로 이러한 역할은 여러 작업 그룹으로 분할되므로 조직의 필요에 따라 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="c679c-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Lync Server 2013에서 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징 계획</a></span><span class="sxs-lookup"><span data-stu-id="c679c-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c679c-152">페더레이션 시나리오를 위한 에지 서버 설정</span><span class="sxs-lookup"><span data-stu-id="c679c-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c679c-153">내보낸 토폴로지 구성 파일을 각 에지 서버로 전송합니다. 즉, 복제가 완료되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="c679c-154">배포 마법사를 다시 실행하여 페더레이션을 위한 지원 구성 요소를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="c679c-155">에지 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="c679c-156">각 에지 서버에 대한 인증서를 요청하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="c679c-157">에지 서버 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c679c-158">Administrators 그룹</span><span class="sxs-lookup"><span data-stu-id="c679c-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c679c-159"><a href="lync-server-2013-setting-up-lync-federation.md">Lync Server 2013에서 Lync 페더레이션 설정</a></span><span class="sxs-lookup"><span data-stu-id="c679c-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c679c-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Lync Server 2013에서 공용 인스턴트 메시징 연결 설정</a></span><span class="sxs-lookup"><span data-stu-id="c679c-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c679c-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Lync Server 2013에서 XMPP 페더레이션 설정</a></span><span class="sxs-lookup"><span data-stu-id="c679c-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c679c-162">외부 사용자 액세스에 대한 지원 구성</span><span class="sxs-lookup"><span data-stu-id="c679c-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="c679c-163">Lync Server 제어판 외부 사용자 액세스 사용</span><span class="sxs-lookup"><span data-stu-id="c679c-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="c679c-164">페더레이션 사용자 또는 공용 사용자와의 통신을 사용할 수 있도록 외부 액세스 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="c679c-165">도메인을 허용하거나 차단하도록 SIP 페더레이션 도메인을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="c679c-166">공용 인스턴트 메시징 연결 공급자에 대해 SIP 페더레이션 공급자를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="c679c-167">XMPP 도메인별로 XMPP 페더레이션 파트너를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="c679c-168">CSAdministrator 역할에 할당된 RTCUniversalServerAdmins 그룹 또는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="c679c-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="c679c-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성</a></span><span class="sxs-lookup"><span data-stu-id="c679c-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c679c-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Lync Server 2013에서 공용 공급자에 대해 미디어 암호화 구성</a></span><span class="sxs-lookup"><span data-stu-id="c679c-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c679c-171">에지 서버 구성 확인</span><span class="sxs-lookup"><span data-stu-id="c679c-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="c679c-172">서버 연결과 내부 서버에서의 구성 데이터 복제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c679c-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="c679c-173">복제 확인을 위해서는 CSAdministrator 역할에 할당된 RTCUniversalServerAdmins 그룹 또는 사용자 계정, 사용자 연결 확인을 위해서는 각 페더레이션 사용자 유형의 사용자</span><span class="sxs-lookup"><span data-stu-id="c679c-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="c679c-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Lync Server 2013에서에 지 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="c679c-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="c679c-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Lync Server 2013의 XMPP 구성 예-Google 대화를 사용한 XMPP 페더레이션</a></span><span class="sxs-lookup"><span data-stu-id="c679c-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

