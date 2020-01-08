---
title: 'Lync Server 2013: 사용자 및 클라이언트 인증'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="a6d3a-102">Lync Server 2013에 대 한 사용자 및 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="a6d3a-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6d3a-103">_**마지막으로 수정한 주제:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="a6d3a-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="a6d3a-104">신뢰할 수 있는 사용자는 Microsoft Lync Server 2013의 신뢰할 수 있는 서버에서 자격 증명을 인증 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="a6d3a-105">이 서버는 일반적으로 스탠더드 버전 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="a6d3a-106">Lync Server 2013는 Active Directory 도메인 서비스를 사용자 자격 증명의 신뢰할 수 있는 단일 백 엔드 리포지토리로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="a6d3a-107">인증은 신뢰할 수 있는 서버에 대 한 사용자 자격 증명을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="a6d3a-108">Lync Server 2013는 사용자의 상태 및 위치에 따라 다음 인증 프로토콜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="a6d3a-109">Active Directory 자격 증명을 사용 하는 내부 사용자 용 **MIT Kerberos 버전 5 보안 프로토콜** 입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="a6d3a-110">Kerberos에는 Active Directory 도메인 서비스에 대 한 클라이언트 연결이 필요 하며,이 때문에 회사 방화벽 외부에서 클라이언트를 인증 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="a6d3a-111">회사 방화벽 외부의 끝점에서 연결 하는 Active Directory 자격 증명이 있는 사용자에 대 한 **NTLM 프로토콜** 입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="a6d3a-112">액세스에 지 서비스가 로그인 요청을 디렉터 (있는 경우) 또는 프런트 엔드 서버 (인증)에 게 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="a6d3a-113">액세스에 지 서비스 자체는 인증을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6d3a-114">NTLM 프로토콜은 Kerberos 보다 약한 공격 보호 기능을 제공 하므로 일부 조직에서는 NTLM의 사용을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="a6d3a-115">결과적으로 Lync Server 2013에 대 한 액세스는 VPN 또는 DirectAccess 연결을 통해 연결 된 내부 또는 클라이언트로 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="a6d3a-116">익명 사용자 라고 불리는 **다이제스트 프로토콜** 입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-116">**Digest protocol** for so-called anonymous users.</span></span> <span data-ttu-id="a6d3a-117">익명 사용자는 Active Directory 자격 증명을 인식할 수 없지만 온-프레미스 회의에 초대 하 고 유효한 컨퍼런스 키를 소유 하는 사용자 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-117">Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key.</span></span> <span data-ttu-id="a6d3a-118">다이제스트 인증은 다른 클라이언트 조작에는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-118">Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="a6d3a-119">Lync Server 2013 인증은 다음 두 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="a6d3a-120">클라이언트와 서버 간에 보안 연결이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="a6d3a-121">클라이언트와 서버는 기존 보안 연결을 사용 하 여 보내는 메시지에 서명 하 고 자신이 받은 메시지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-121">The client and server use the existing security association to sign messages that they send and to verify the messages they receive.</span></span> <span data-ttu-id="a6d3a-122">서버에서 인증을 사용 하도록 설정 되어 있는 경우에는 클라이언트의 인증 되지 않은 메시지가 수락 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-122">Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="a6d3a-123">사용자 신뢰는 사용자 id 자체가 아니라 사용자 로부터 들어오는 각 메시지에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-123">User trust is attached to each message that originates from a user, not to the user identity itself.</span></span> <span data-ttu-id="a6d3a-124">서버가 각 메시지에 유효한 사용자 자격 증명을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-124">The server checks each message for valid user credentials.</span></span> <span data-ttu-id="a6d3a-125">사용자 자격 증명이 유효 하 게 표시 되는 경우에는 해당 메시지가 첫 번째 서버 에서만 수신 되 고 신뢰 된 서버 클라우드의 다른 모든 서버에서 unchallenged 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-125">If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="a6d3a-126">페더레이션 파트너가 발급 하는 유효한 자격 증명을 사용 하는 사용자는 신뢰할 수 있지만 필요에 따라 추가 제약 조건에서 내부 사용자에 게 적용 되는 모든 범위의 권한을 제공 하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="a6d3a-127">또한 얼음 및 선반 가공 프로토콜은 IETF RFC에서 설명한 대로 다이제스트 챌린지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="a6d3a-128">클라이언트 인증서는 Lync Server 2013에서 사용자를 인증 하는 대체 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="a6d3a-129">사용자 이름 및 암호를 제공 하는 대신, 사용자는 인증서와 암호화 챌린지를 해결 하는 데 필요한 인증서에 해당 하는 개인 키를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="a6d3a-130">(이 인증서는 사용자를 식별 하는 주체 이름 또는 주체 대체 이름을 가져야 하며, Lync Server 2013를 실행 하는 서버에서 신뢰 하는 루트 CA가 발급 해야 하며, 인증서 유효 기간 내에 있고, 해지 되지 않은 것입니다.) 인증을 받기 위해 사용자는 PIN (개인 식별 번호)을 입력 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="a6d3a-131">인증서는 사용자 이름 및 암호를 입력 하는 것이 어렵기 때문에 Microsoft Lync 2013 전화 버전을 실행 하는 전화 및 기타 장치에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d3a-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

