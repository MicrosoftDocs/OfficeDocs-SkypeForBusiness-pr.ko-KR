---
title: 'Lync Server 2013: 암호화'
description: 'Lync Server 2013: 암호화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab2c46af16cfdbb9a01631777e65219acb2ceb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575654"
---
# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="fe3fb-103">Lync Server 2013에 대 한 암호화</span><span class="sxs-lookup"><span data-stu-id="fe3fb-103">Encryption for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe3fb-104">_**마지막으로 수정 된 항목:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="fe3fb-104">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="fe3fb-105">Microsoft Lync Server 2013에서는 TLS 및 MTLS를 사용 하 여 인스턴트 메시지를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-105">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="fe3fb-106">모든 서버 간 트래픽은 트래픽이 내부 네트워크에 한정 되는지 아니면 내부 네트워크 경계를 교차 하는지에 관계 없이 MTLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-106">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="fe3fb-107">TLS는 선택적 이지만 중재 서버와 미디어 게이트웨이 간에는 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-107">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="fe3fb-108">이 링크에 TLS가 구성 된 경우 MTLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-108">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="fe3fb-109">따라서 중재 서버에서 신뢰 하는 CA에서 발급 한 인증서를 사용 하 여 게이트웨이를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-109">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe3fb-110">SSL 3.0에 대 한 보안 권고는 2014에 게시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-110">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="fe3fb-111">Lync Server 2013에서 SSL 3.0을 사용 하지 않도록 설정 하는 것은 지원 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-111">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="fe3fb-112">보안 권고에 대 한 자세한 내용은를 참조 하세요 <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="fe3fb-112">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" /><span data-ttu-id="fe3fb-114">보안 메모:</span><span class="sxs-lookup"><span data-stu-id="fe3fb-114">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="fe3fb-115">가장 강력한 암호화 프로토콜을 사용 하기 위해 Lync Server 2013에서는 tls <strong>1.2</strong> , <strong>tls 1.1</strong>, <strong>TLS 1.0</strong>와 같은 순서로 tls 암호화 프로토콜을 클라이언트에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-115">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="fe3fb-116">TLS는 Lync Server 2013의 중요 한 측면이 며, 지원 되는 환경을 유지 관리 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-116">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="fe3fb-p104">클라이언트 간 트래픽의 요구 사항은 트래픽이 내부 회사 방화벽을 통과하는지 여부에 따라 달라집니다. 내부 전용 트래픽은 TLS(인스턴트 메시지가 암호화됨) 또는 TCP(인스턴트 메시지가 암호화되지 않음)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="fe3fb-119">다음 표에는 각 트래픽 유형에 대한 프로토콜 요구 사항이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-119">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="fe3fb-120">트래픽 보호</span><span class="sxs-lookup"><span data-stu-id="fe3fb-120">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe3fb-121">트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="fe3fb-121">Traffic type</span></span></th>
<th><span data-ttu-id="fe3fb-122">보호 수단</span><span class="sxs-lookup"><span data-stu-id="fe3fb-122">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe3fb-123">서버 간</span><span class="sxs-lookup"><span data-stu-id="fe3fb-123">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="fe3fb-124">MTLS</span><span class="sxs-lookup"><span data-stu-id="fe3fb-124">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3fb-125">클라이언트-서버</span><span class="sxs-lookup"><span data-stu-id="fe3fb-125">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="fe3fb-126">TLS</span><span class="sxs-lookup"><span data-stu-id="fe3fb-126">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3fb-127">인스턴트 메시징 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="fe3fb-127">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="fe3fb-128">TLS(TLS에 대해 구성된 경우)</span><span class="sxs-lookup"><span data-stu-id="fe3fb-128">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3fb-129">미디어의 오디오/비디오 및 데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="fe3fb-129">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="fe3fb-130">SRTP</span><span class="sxs-lookup"><span data-stu-id="fe3fb-130">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3fb-131">데스크톱 공유(신호)</span><span class="sxs-lookup"><span data-stu-id="fe3fb-131">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="fe3fb-132">TLS</span><span class="sxs-lookup"><span data-stu-id="fe3fb-132">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe3fb-133">웹 회의</span><span class="sxs-lookup"><span data-stu-id="fe3fb-133">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="fe3fb-134">TLS</span><span class="sxs-lookup"><span data-stu-id="fe3fb-134">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe3fb-135">모임 콘텐츠 다운로드, 주소록 다운로드, 메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="fe3fb-135">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="fe3fb-136">H</span><span class="sxs-lookup"><span data-stu-id="fe3fb-136">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="fe3fb-137">미디어 암호화</span><span class="sxs-lookup"><span data-stu-id="fe3fb-137">Media Encryption</span></span>

<span data-ttu-id="fe3fb-138">미디어 트래픽은 SRTP (보안 RTP)를 사용 하 여 암호화 되며, RTP (Real-Time Transport Protocol)의 프로필에 대 한 기밀, 인증, replay 공격 방지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-138">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="fe3fb-139">또한 중재 서버와 내부 다음 홉 사이에 양방향으로 흐르는 미디어도 SRTP를 사용하여 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-139">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="fe3fb-140">중재 서버와 미디어 게이트웨이 사이에 양방향으로 진행 되는 미디어 흐름은 기본적으로 암호화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-140">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="fe3fb-141">중재 서버는 미디어 게이트웨이에 대 한 암호화를 지원할 수 있지만, 게이트웨이는 MTLS 및 인증서의 저장소를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-141">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe3fb-142">A/V (오디오/비디오)는 Windows Live Messenger의 새 버전에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-142">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="fe3fb-143">Windows Live Messenger와의 A/V 페더레이션을 구현하는 경우에는 Lync Server 암호화 수준도 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-143">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="fe3fb-144">기본적으로 암호화 수준은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="fe3fb-145">Lync Server 관리 셸을 사용 하 여이 설정을 지원으로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-145">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="fe3fb-146">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013의 외부 사용자 액세스 배포</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-146">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="fe3fb-147">Microsoft Lync 2013 및 Windows Live 클라이언트 간에 오디오 및 비디오 미디어 트래픽이 암호화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-147">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="fe3fb-148">서명에</span><span class="sxs-lookup"><span data-stu-id="fe3fb-148">FIPS</span></span>

<span data-ttu-id="fe3fb-149">Windows Server 운영 체제가 시스템 암호화에 FIPS 140-2 알고리즘을 사용 하도록 구성 되어 있는 경우 Lync Server 2013 및 Microsoft Exchange Server 2013는 FIPS (정보 처리 표준) 140-2 알고리즘을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-149">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="fe3fb-150">FIPS 지원을 구현 하려면 Lync Server 2013를 실행 하는 각 서버가 지원 되도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-150">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="fe3fb-151">FIPS 규격 알고리즘 사용에 대 한 자세한 내용과 FIPS 지원을 구현 하는 방법에 대 한 자세한 811833 내용은 Windows XP 및 이후 버전의 Windows에서 "시스템 암호화: 암호화, 해시 및 서명에 FIPS 호환 알고리즘 사용" 보안 설정을 사용 하는 경우의 결과를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) .</span><span class="sxs-lookup"><span data-stu-id="fe3fb-151">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="fe3fb-152">Exchange 2010의 FIPS 140-2 지원 및 제한 사항에 대 한 자세한 내용은 Exchange 2010 SP1 및에서 FIPS 호환 알고리즘 지원를 참조 [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe3fb-152">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

