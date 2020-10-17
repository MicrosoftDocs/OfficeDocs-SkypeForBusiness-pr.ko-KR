---
title: Lync Server 2013 인증서 인프라 요구 사항
description: Lync Server 2013 인증서 인프라 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c7e69f272c29f0ba9386f403db326b4d39bbff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544294"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="37a7d-103">Lync Server 2013의 인증서 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37a7d-103">Certificate infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a7d-104">_**마지막으로 수정 된 항목:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="37a7d-104">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="37a7d-105">Lync Server 2013에서는 TLS 및 상호 TLS (MTLS) 연결을 지원 하기 위해 PKI (공개 키 인프라)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-105">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="37a7d-106">Lync Server에서는 다음 용도로 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-106">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="37a7d-107">클라이언트와 서버 간의 TLS 연결</span><span class="sxs-lookup"><span data-stu-id="37a7d-107">TLS connections between client and server</span></span>

  - <span data-ttu-id="37a7d-108">서버 간의 MTLS 연결</span><span class="sxs-lookup"><span data-stu-id="37a7d-108">MTLS connections between servers</span></span>

  - <span data-ttu-id="37a7d-109">파트너의 자동 DNS 검색을 사용한 페더레이션</span><span class="sxs-lookup"><span data-stu-id="37a7d-109">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="37a7d-110">IM(인스턴트 메시징)에 대한 원격 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="37a7d-110">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="37a7d-111">A/V(오디오/비디오) 세션, 응용 프로그램 공유 및 웹 회의에 대한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="37a7d-111">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="37a7d-112">웹 서비스 자동 검색을 사용하는 모바일 요청</span><span class="sxs-lookup"><span data-stu-id="37a7d-112">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="37a7d-113">Lync Server의 경우 다음과 같은 일반적인 요구 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-113">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="37a7d-114">모든 서버 인증서는 서버 권한 부여(서버 EKU)를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-114">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="37a7d-115">모든 서버 인증서에는 CDP(CRL 배포 지점)가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-115">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="37a7d-116">모든 인증서는 운영 체제에서 지 원하는 서명 알고리즘을 사용 하 여 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-116">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="37a7d-117">Lync Server 2013는 다이제스트 크기의 sha-1 및 SHA-2 제품군 (224, 256, 384 및 512 비트)을 지원 하며 운영 체제 요구 사항을 충족 하거나 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-117">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="37a7d-118">운영 체제 지원에 대해서는를 참조 하세요 [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) .</span><span class="sxs-lookup"><span data-stu-id="37a7d-118">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37a7d-119">RSASSA 서명 알고리즘을 사용 하는 것은 지원 되지 않으며 다른 문제 중에서 로그인 및 착신 전환 문제에 대 한 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-119">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="37a7d-120">Lync Server를 실행 하는 내부 서버에 대해 자동 등록이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-120">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="37a7d-121">Lync Server에 지 서버에 대해서는 자동 등록이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-121">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="37a7d-122">Windows Server 2003 CA로 웹 기반 인증서 요청을 전송할 때는 Windows Server 2003 SP2 또는 Windows XP를 실행하는 컴퓨터에서 요청을 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-122">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="37a7d-123">KB 922706에서는 Windows Server 2003 인증서 서비스 웹 등록에 대해 웹 인증서를 등록할 때 발생하는 문제를 해결하기 위한 지원 정보가 제공되지만, Windows Server 2008, Windows Vista 또는 Windows 7을 사용하여 Windows Server 2003 CA에서 인증서를 요청할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-123">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="37a7d-124">1024, 2048 및 4096의 암호화 키 길이는 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-124">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="37a7d-125">키 길이가 2048 이상인 경우 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-125">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="37a7d-126">기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-126">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="37a7d-127">ECDH \_ P256, ecdh \_ P384 및 ecdh \_ P521 알고리즘도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37a7d-127">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="37a7d-128">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="37a7d-128">In This Section</span></span>

  - [<span data-ttu-id="37a7d-129">Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37a7d-129">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="37a7d-130">Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37a7d-130">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="37a7d-131">Lync Server 2013의 영구 채팅 서버에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37a7d-131">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="37a7d-132">Lync Server 2013의 모바일 기능에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37a7d-132">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

