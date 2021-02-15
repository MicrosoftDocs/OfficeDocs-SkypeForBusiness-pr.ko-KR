---
title: 비즈니스용 Skype 서버 암호화
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 비즈니스용 Skype 서버는 TLS 및 MTLS를 사용하여 인스턴트 메시지를 암호화합니다. 모든 서버 간 트래픽에는 트래픽이 내부 네트워크로 제한되거나 내부 네트워크 경계를 넘어가든 관계없이 MTLS가 필요합니다. 비즈니스용 Skype 서버를 제3자 IPPBX 시스템 또는 SIP 트렁크 TLS에 연결하는 것은 선택 사항이지만 중재 서버와 미디어 게이트웨이 간에는 권장됩니다. 이 링크에 TLS가 구성된 경우 MTLS가 필요합니다. 따라서 게이트웨이는 중재 서버에서 신뢰하는 CA의 인증서로 구성해야 합니다.
ms.openlocfilehash: 48af03d7f6aed5b744ad4e0c460622194a87d96e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832208"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="df153-107">비즈니스용 Skype 서버 암호화</span><span class="sxs-lookup"><span data-stu-id="df153-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="df153-108">비즈니스용 Skype 서버는 TLS 및 MTLS를 사용하여 인스턴트 메시지를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="df153-109">모든 서버 간 트래픽에는 트래픽이 내부 네트워크로 제한되거나 내부 네트워크 경계를 넘어가든 관계없이 MTLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="df153-110">비즈니스용 Skype 서버를 타사 IPPBX 시스템 또는 SIP 트렁크 TLS에 연결하는 것은 선택 사항이지만 중재 서버와 미디어 게이트웨이 간에는 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="df153-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="df153-111">이 링크에 TLS가 구성된 경우 MTLS가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="df153-112">따라서 게이트웨이는 중재 서버에서 신뢰하는 CA의 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df153-113">SSL 3.0에 대한 보안 권고는 2014년에 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="df153-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="df153-114">비즈니스용 Skype 서버 2015에서 SSL 3.0을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df153-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="df153-115">보안 권고에 대한 자세한 내용은 [Lync Server 2013 및 비즈니스용 Skype 서버 2015에서 SSL 3.0을](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df153-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span><br/>
<span data-ttu-id="df153-116">**보안 참고 사항:** 가장 강력한 암호화 프로토콜이 사용되도록 하기 위해 비즈니스용 Skype 서버 2015는 **클라이언트에 TLS 1.2, TLS 1.1, TLS 1.0** 순서로 TLS 암호화 프로토콜을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="df153-117">TLS는 비즈니스용 Skype 서버 2015의 중요한 측면으로, 지원되는 환경을 유지 관리하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="df153-118">**보안 참고 사항:** 가장 강력한 암호화 프로토콜이 사용되도록 하기 위해 비즈니스용 Skype 서버 2019는 **클라이언트에 TLS 1.3, TLS 1.2와** 같은 순서로 TLS 암호화 프로토콜을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="df153-119">TLS는 비즈니스용 Skype 서버 2019의 중요한 측면으로, 지원되는 환경을 유지 관리하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="df153-120">다음 표에는 각 트래픽 유형에 대한 프로토콜 요구 사항이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df153-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="df153-121">**트래픽 보호**</span><span class="sxs-lookup"><span data-stu-id="df153-121">**Traffic Protection**</span></span>

|<span data-ttu-id="df153-122">**트래픽 유형**</span><span class="sxs-lookup"><span data-stu-id="df153-122">**Traffic type**</span></span>|<span data-ttu-id="df153-123">**보호 수단**</span><span class="sxs-lookup"><span data-stu-id="df153-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df153-124">서버 대 서버</span><span class="sxs-lookup"><span data-stu-id="df153-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="df153-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="df153-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="df153-126">클라이언트-서버</span><span class="sxs-lookup"><span data-stu-id="df153-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="df153-127">TLS</span><span class="sxs-lookup"><span data-stu-id="df153-127">TLS</span></span>  <br/> |
|<span data-ttu-id="df153-128">인스턴트 메시징 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="df153-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="df153-129">TLS</span><span class="sxs-lookup"><span data-stu-id="df153-129">TLS</span></span>  <br/> |
|<span data-ttu-id="df153-130">미디어의 오디오/비디오 및 데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="df153-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="df153-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="df153-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="df153-132">데스크톱 공유(신호)</span><span class="sxs-lookup"><span data-stu-id="df153-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="df153-133">TLS</span><span class="sxs-lookup"><span data-stu-id="df153-133">TLS</span></span>  <br/> |
|<span data-ttu-id="df153-134">웹 회의</span><span class="sxs-lookup"><span data-stu-id="df153-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="df153-135">TLS</span><span class="sxs-lookup"><span data-stu-id="df153-135">TLS</span></span>  <br/> |
|<span data-ttu-id="df153-136">모임 콘텐츠 다운로드, 주소록 다운로드, 메일 그룹 확장</span><span class="sxs-lookup"><span data-stu-id="df153-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="df153-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="df153-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="df153-138">미디어 암호화</span><span class="sxs-lookup"><span data-stu-id="df153-138">Media Encryption</span></span>

<span data-ttu-id="df153-139">미디어 트래픽은 RTP 트래픽에 대한 기밀성, 인증 및 재생 공격 보호를 제공하는 Real-Time 전송 프로토콜(RTP)의 프로필인 SRTP(Secure RTP)를 사용하여 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="df153-139">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="df153-140">또한 중재 서버와 내부 다음 홉 사이에 양방향으로 흐르는 미디어도 SRTP를 사용하여 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="df153-140">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="df153-141">중재 서버와 미디어 게이트웨이 간에 양방향으로 흐르는 미디어는 선택적으로 암호화되며 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="df153-141">Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended.</span></span> <span data-ttu-id="df153-142">중재 서버는 미디어 게이트웨이에 대한 암호화를 지원할 수 있지만 게이트웨이는 MTLS 및 인증서 저장소를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-142">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="df153-143">하이브리드 설정에 대한 자세한 내용은 하이브리드 연결 [계획을 참조하세요.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)</span><span class="sxs-lookup"><span data-stu-id="df153-143">For more information about setting up hybrid, see [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).</span></span>
  
## <a name="fips"></a><span data-ttu-id="df153-144">FIPS</span><span class="sxs-lookup"><span data-stu-id="df153-144">FIPS</span></span>

<span data-ttu-id="df153-145">비즈니스용 Skype 서버 및 Microsoft Exchange Server 2016은 Windows Server 운영 체제가 시스템 암호화에 FIPS 140-2 알고리즘을 사용하도록 구성된 경우 FIPS(Federal Information Processing Standard) 140-2 알고리즘을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="df153-146">FIPS 지원을 구현하려면 이를 지원하도록 비즈니스용 Skype 서버를 실행하는 각 서버를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df153-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
  

