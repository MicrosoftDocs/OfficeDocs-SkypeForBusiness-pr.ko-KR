---
title: 'Lync Server 2013: TLS 및 MTLS'
description: 'Lync Server 2013: TLS 및 MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ccee47e635435dd5f0d5eae03711c0cd5e517b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541794"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="03362-103">Lync Server 2013 용 TLS 및 MTLS</span><span class="sxs-lookup"><span data-stu-id="03362-103">TLS and MTLS for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03362-104">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="03362-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="03362-105">TLS (전송 계층 보안) 및 MTLS (상호 전송 계층 보안) 프로토콜은 인터넷에서 암호화 된 통신 및 끝점 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-105">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="03362-106">Microsoft Lync Server 2013에서는 이러한 두 가지 프로토콜을 사용 하 여 신뢰할 수 있는 서버의 네트워크를 만들고 해당 네트워크를 통한 모든 통신을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-106">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="03362-107">서버 간의 모든 SIP 통신은 MTLS를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03362-107">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="03362-108">클라이언트에서 서버로의 SIP 통신은 TLS를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03362-108">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="03362-109">TLS는 클라이언트 소프트웨어를 통해 사용자가 연결 되는 Lync Server 2013 서버를 인증할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-109">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="03362-110">TLS 연결에서는 클라이언트가 서버의 유효한 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-110">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="03362-111">유효한 인증서란 클라이언트에서도 트러스트된 CA가 발급했으며 DNS 이름이 서버의 DNS 이름과 일치하는 인증서를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-111">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="03362-112">인증서가 유효한 경우 클라이언트가 인증서의 공개 키를 사용하여 통신에 사용할 대칭 암호화 키를 암호화하여 인증서의 원래 소유자만 해당 개인 키를 사용하여 통신 내용을 해독할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-112">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="03362-113">이 연결은 트러스트되며 해당 지점부터는 트러스트된 다른 서버나 클라이언트에서 트러스트 여부를 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03362-113">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="03362-114">이 컨텍스트 내에서 웹 서비스와 함께 사용되는 SSL(Secure Sockets Layer)을 TLS 기반으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03362-114">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="03362-115">서버 간 연결은 상호 인증을 위해 MTLS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-115">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="03362-116">MTLS 연결에서 메시지를 보낸 서버와이 서버가 상호 트러스트 된 CA 로부터 인증서를 받는 서버를 교환 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-116">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="03362-117">인증서는 각 서버의 id를 다른 서버에 증명 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-117">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="03362-118">Lync Server 2013 배포에서 Active Directory 도메인의 모든 구성원이 해당 도메인의 엔터프라이즈 CA를 신뢰 하기 때문에, 발급 하는 CA가 해지 하지 않는 엔터프라이즈 CA에서 발급 한 인증서는 모든 내부 클라이언트 및 서버에서 자동으로 유효한 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03362-118">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="03362-119">페더레이션 시나리오에서는 두 페더레이션 파트너가 발급 CA를 신뢰 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-119">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="03362-120">원하는 경우 각 파트너가 다른 CA를 사용할 수 있는 경우 해당 CA도 다른 파트너가이를 신뢰 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03362-120">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="03362-121">이 트러스트는 트러스트 된 루트 ca에 파트너의 루트 CA 인증서가 있거나 두 사용자가 신뢰 하는 타사 CA를 사용 하는에 지 서버가 가장 쉽게 수행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-121">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="03362-122">TLS 및 MTLS를 사용 하는 경우 도청 및 중간자 공격을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03362-122">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="03362-123">중간자가 공격을 받은 경우 공격자는 두 사용자에 게 정보 없이 공격자의 컴퓨터를 통해 네트워크 엔터티 간의 통신을 다시 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-123">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="03362-124">TLS 및 Lync Server 2013 신뢰할 수 있는 서버 (토폴로지 작성기에 지정 된 것만 해당)를 지정 하면 두 끝점 간에 공개 키 암호화를 사용 하 여 종단 간 암호화를 사용 하 여 응용 프로그램 계층에서 부분적으로 공격이 중단 될 위험을 완화 합니다. 그리고 공격자는 해당 개인 키와 신뢰할 수 있는 인증서가 있어야 하며 통신을 해독 하기 위해 클라이언트에서 통신 하는 서비스의 이름으로 발급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-124">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="03362-125">그러나 궁극적으로는 네트워킹 인프라 (이 경우 회사 DNS)에서 최상의 보안 방법을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-125">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="03362-126">Lync Server 2013에서는 DNS 서버가 도메인 컨트롤러와 글로벌 카탈로그를 신뢰할 수 있는 것과 동일한 방식으로 신뢰 되는 것으로 가정 하지만 DNS는 공격자의 서버가 스푸핑된 이름에 대 한 요청에 성공적으로 응답 하지 못하도록 방지 하 여 DNS 가로채기 공격에 대 한 보호 수준을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="03362-126">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="03362-127">다음 그림에서는 Lync Server 2013에서 MTLS를 사용 하 여 신뢰할 수 있는 서버 네트워크를 만드는 방법을 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03362-127">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="03362-128">**Lync Server 네트워크의 트러스트된 연결**</span><span class="sxs-lookup"><span data-stu-id="03362-128">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="03362-129">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="03362-129">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

