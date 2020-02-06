---
title: 비즈니스용 Skype 서버 암호화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 비즈니스용 Skype Server는 TLS 및 MTLS를 사용 하 여 인스턴트 메시지를 암호화 합니다. 모든 서버 간 트래픽에는 트래픽이 내부 네트워크에 한정 되는지 아니면 내부 네트워크 경계를 교차 하는지에 관계 없이 MTLS가 필요 합니다. 비즈니스용 Skype 서버를 타사 IPPBX 시스템에 연결 하는 경우 SIP trunks TLS는 선택 사항 이지만 중재 서버와 미디어 게이트웨이 사이에 강력히 권장 됩니다. 이 링크에 TLS가 구성 되어 있으면 MTLS가 필요 합니다. 따라서 중재 서버에서 신뢰 하는 CA의 인증서를 사용 하 여 게이트웨이를 구성 해야 합니다.
ms.openlocfilehash: 64e7199cf761ad7d7ec18b00e8f3b7f27fed6f04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815666"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="cbc2a-107">비즈니스용 Skype 서버 암호화</span><span class="sxs-lookup"><span data-stu-id="cbc2a-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="cbc2a-108">비즈니스용 Skype Server는 TLS 및 MTLS를 사용 하 여 인스턴트 메시지를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="cbc2a-109">모든 서버 간 트래픽에는 트래픽이 내부 네트워크에 한정 되는지 아니면 내부 네트워크 경계를 교차 하는지에 관계 없이 MTLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="cbc2a-110">비즈니스용 Skype 서버를 타사 IPPBX 시스템에 연결 하거나 SIP trunks TLS는 선택 사항 이지만 중재 서버와 미디어 게이트웨이 사이에 강력히 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="cbc2a-111">이 링크에 TLS가 구성 되어 있으면 MTLS가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="cbc2a-112">따라서 중재 서버에서 신뢰 하는 CA의 인증서를 사용 하 여 게이트웨이를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cbc2a-113">SSL 3.0에 대 한 보안 권고는 2014에 게시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="cbc2a-114">비즈니스용 Skype Server 2015에서 SSL 3.0을 사용 하지 않도록 설정 하는 것은 지원 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="cbc2a-115">보안 권고에 대 한 자세한 내용은 [Lync server 2013 및 비즈니스용 Skype 서버 2015에서 SSL 3.0 사용 안 함을](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span><br/>
<span data-ttu-id="cbc2a-116">**보안 참고 사항:** 가장 강력한 암호화 프로토콜을 사용 하기 위해 비즈니스용 Skype 서버 2015은 tls **1.2, tls 1.1, tls 1.0**에 대 한 tls 암호화 프로토콜을 다음 순서로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="cbc2a-117">TLS는 비즈니스용 Skype 서버 2015에 중요 한 요소 이므로 지원 되는 환경을 유지 관리 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="cbc2a-118">**보안 참고 사항:** 가장 강력한 암호화 프로토콜을 사용 하기 위해, 비즈니스용 Skype 서버 2019는 tls 암호화 프로토콜을 클라이언트에 게 제공 합니다. i s e **1.3, tls 1.2**.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="cbc2a-119">TLS는 비즈니스용 Skype 서버 2019에 중요 한 요소 이므로 지원 되는 환경을 유지 관리 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="cbc2a-120">다음 표에는 각 트래픽 유형에 대 한 프로토콜 요구 사항이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="cbc2a-121">**트래픽 보호**</span><span class="sxs-lookup"><span data-stu-id="cbc2a-121">**Traffic Protection**</span></span>

|<span data-ttu-id="cbc2a-122">**트래픽 유형**</span><span class="sxs-lookup"><span data-stu-id="cbc2a-122">**Traffic type**</span></span>|<span data-ttu-id="cbc2a-123">**보호**</span><span class="sxs-lookup"><span data-stu-id="cbc2a-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cbc2a-124">서버 간</span><span class="sxs-lookup"><span data-stu-id="cbc2a-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="cbc2a-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="cbc2a-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="cbc2a-126">클라이언트에서 서버로</span><span class="sxs-lookup"><span data-stu-id="cbc2a-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="cbc2a-127">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="cbc2a-127">TLS</span></span>  <br/> |
|<span data-ttu-id="cbc2a-128">인스턴트 메시징 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="cbc2a-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="cbc2a-129">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="cbc2a-129">TLS</span></span>  <br/> |
|<span data-ttu-id="cbc2a-130">미디어의 오디오 및 비디오 및 데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="cbc2a-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="cbc2a-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="cbc2a-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="cbc2a-132">데스크톱 공유 (신호)</span><span class="sxs-lookup"><span data-stu-id="cbc2a-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="cbc2a-133">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="cbc2a-133">TLS</span></span>  <br/> |
|<span data-ttu-id="cbc2a-134">웹 회의</span><span class="sxs-lookup"><span data-stu-id="cbc2a-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="cbc2a-135">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="cbc2a-135">TLS</span></span>  <br/> |
|<span data-ttu-id="cbc2a-136">모임 콘텐츠 다운로드, 주소록 다운로드, 메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="cbc2a-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="cbc2a-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="cbc2a-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="cbc2a-138">미디어 암호화</span><span class="sxs-lookup"><span data-stu-id="cbc2a-138">Media Encryption</span></span>

<span data-ttu-id="cbc2a-139">미디어 트래픽은 RTP (실시간 전송 프로토콜)의 프로필 인 보안 RTP (SRTP)를 사용 하 여 기밀성, 인증, 재생 공격 방지를 제공 하는 RTP 트래픽에 대해 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-139">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="cbc2a-140">또한 중재 서버와 해당 내부 다음 홉 간의 양방향 모두에서 미디어를 SRTP를 사용 하 여이를 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-140">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="cbc2a-141">중재 서버와 미디어 게이트웨이 간의 양방향에서 미디어 흐름이 선택적으로 암호화 되 고 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-141">Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended.</span></span> <span data-ttu-id="cbc2a-142">중재 서버는 미디어 게이트웨이에 대 한 암호화를 지원할 수 있지만, 게이트웨이에서는 인증서의 MTLS 및 저장소를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-142">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cbc2a-143">하이브리드을 설정 하는 방법에 대 한 자세한 내용은 [하이브리드 연결 계획](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-143">For more information about setting up hybrid, see [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).</span></span>
  
## <a name="fips"></a><span data-ttu-id="cbc2a-144">서명에</span><span class="sxs-lookup"><span data-stu-id="cbc2a-144">FIPS</span></span>

<span data-ttu-id="cbc2a-145">Windows Server 운영 체제가 시스템 암호화에 FIPS 140-2 알고리즘을 사용 하도록 구성 된 경우 비즈니스용 Skype 서버와 Microsoft Exchange Server 2016는 FIPS (정보 처리 표준) 140-2 알고리즘에 대 한 지원으로 작동 합니다. .</span><span class="sxs-lookup"><span data-stu-id="cbc2a-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="cbc2a-146">FIPS 지원을 구현 하려면 비즈니스용 Skype Server를 실행 하는 각 서버를 지원 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc2a-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
  

