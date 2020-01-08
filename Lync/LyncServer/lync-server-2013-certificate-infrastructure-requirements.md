---
title: Lync Server 2013 인증서 인프라 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="7093a-102">Lync Server 2013에 대한 인증서 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7093a-102">Certificate infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7093a-103">_**마지막으로 수정한 주제:** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="7093a-103">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="7093a-104">Lync Server 2013에는 TLS 및 상호 TLS (MTLS) 연결을 지원 하기 위한 PKI (공개 키 인프라)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-104">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="7093a-105">Lync Server는 다음과 같은 목적으로 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-105">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="7093a-106">클라이언트와 서버 간의 TLS 연결</span><span class="sxs-lookup"><span data-stu-id="7093a-106">TLS connections between client and server</span></span>

  - <span data-ttu-id="7093a-107">서버 간 MTLS 연결</span><span class="sxs-lookup"><span data-stu-id="7093a-107">MTLS connections between servers</span></span>

  - <span data-ttu-id="7093a-108">파트너의 자동 DNS 검색을 사용 하는 페더레이션</span><span class="sxs-lookup"><span data-stu-id="7093a-108">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="7093a-109">IM (인스턴트 메시징)에 대 한 원격 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="7093a-109">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="7093a-110">오디오/비디오 (A/V) 세션, 응용 프로그램 공유, 회의에 대 한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="7093a-110">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="7093a-111">웹 서비스의 자동 검색을 사용 하는 모바일 요청</span><span class="sxs-lookup"><span data-stu-id="7093a-111">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="7093a-112">Lync Server의 경우 다음과 같은 일반적인 요구 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-112">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="7093a-113">모든 서버 인증서는 서버 권한 부여 (서버 EKU)를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-113">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="7093a-114">모든 서버 인증서에는 CDP (CRL 배포 지점이)가 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-114">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="7093a-115">모든 인증서는 운영 체제에서 지원 되는 서명 알고리즘을 사용 하 여 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-115">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="7093a-116">Lync Server 2013는 다이제스트 크기의 SHA-1 및 SHA-2 제품군 (224, 256, 384, 512 비트)을 지원 하 고 운영 체제 요구 사항을 충족 하거나 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-116">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="7093a-117">운영 체제 지원은을 참조 [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)하세요.</span><span class="sxs-lookup"><span data-stu-id="7093a-117">For operating system support, see [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7093a-118">RSASSA 서명 알고리즘을 사용 하는 것은 지원 되지 않으며,이 경우 로그인 및 착신 전환 문제에 대 한 오류가 발생할 수 있습니다 (다른 여러 가지 문제).</span><span class="sxs-lookup"><span data-stu-id="7093a-118">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="7093a-119">Lync Server를 실행 하는 내부 서버에 대해 자동 등록이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-119">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="7093a-120">Lync Server Edge 서버에는 자동 등록이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-120">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="7093a-121">Windows Server 2003 CA에 웹 기반 인증서 요청을 제출 하는 경우 Windows Server 2003 SP2 또는 Windows XP를 실행 하는 컴퓨터에서 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-121">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="7093a-122">KB922706는 Windows Server 2003 인증서 서비스 웹 등록에 대해 웹 인증서 등록 문제를 해결할 수 있도록 지원 하지만, Windows Server 2008, Windows Vista 또는 Windows 7을 사용 하 여 다음을 요청 하는 것은 불가능 합니다. Windows Server 2003 CA의 인증서</span><span class="sxs-lookup"><span data-stu-id="7093a-122">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="7093a-123">1024, 2048, 4096의 암호화 키 길이가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-123">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="7093a-124">2048 이상의 키 길이를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-124">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="7093a-125">기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-125">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="7093a-126">ECDH\_P256, ecdh\_P384, ecdh\_P521 알고리즘도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7093a-126">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="7093a-127">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7093a-127">In This Section</span></span>

  - [<span data-ttu-id="7093a-128">Lync Server 2013의 내부 서버에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7093a-128">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="7093a-129">Lync Server 2013의 외부 사용자 액세스에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7093a-129">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="7093a-130">Lync Server 2013의 영구 채팅 서버에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7093a-130">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="7093a-131">Lync Server 2013의 모바일 기능에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7093a-131">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

