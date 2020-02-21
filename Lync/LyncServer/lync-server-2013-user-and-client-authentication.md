---
title: 'Lync Server 2013: 사용자 및 클라이언트 인증'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbddb0dab36a8ad805691196a00a3dc8bf6f9d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="c2222-102">Lync Server 2013에 대 한 사용자 및 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="c2222-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2222-103">_**마지막으로 수정 된 항목:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="c2222-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="c2222-104">신뢰할 수 있는 사용자는 Microsoft Lync Server 2013의 신뢰할 수 있는 서버에서 자격 증명을 인증 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="c2222-105">이 서버는 일반적으로 Standard Edition 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="c2222-106">Lync Server 2013에서는 Active Directory 도메인 서비스를 사용자 자격 증명의 신뢰할 수 있는 단일 백 엔드 리포지토리로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="c2222-107">인증은 트러스트된 서버에 대한 사용자 자격 증명을 제공하는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="c2222-108">Lync Server 2013에서는 사용자의 상태와 위치에 따라 다음과 같은 인증 프로토콜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="c2222-p103">Active Directory 자격 증명이 있는 내부 사용자를 위한 **MIT Kerberos 버전 5 보안 프로토콜**. Kerberos를 사용하려면 클라이언트가 Active Directory 도메인 서비스에 연결해야 하므로, 회사 방화벽 외부의 클라이언트를 인증하는 데는 Kerberos를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="c2222-p104">회사 방화벽 외부의 끝점에서 연결하며 Active Directory 자격 증명이 있는 사용자를 위한 **NTLM 프로토콜**. 액세스 에지 서비스는 인증을 위해 로그온 요청을 디렉터(있는 경우) 또는 프런트 엔드 서버로 전달합니다. 액세스 에지 서비스 자체는 인증을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c2222-114">NTLM 프로토콜은 Kerberos보다 공격 보호 수준이 낮으므로 일부 조직에서는 NTLM 사용을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="c2222-115">따라서 Lync Server 2013에 대 한 액세스는 VPN 또는 DirectAccess 연결을 통해 연결 된 내부 또는 클라이언트로 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="c2222-p106">익명 사용자를 위한 **다이제스트 프로토콜**. 익명 사용자는 인식할 수 있는 Active Directory 자격 증명을 가지고 있지는 않지만 온-프레미스 전화 회의에 초대를 받았으며 유효한 전화 회의 키를 소유한 외부 사용자입니다. 다른 클라이언트 상호 작용에는 다이제스트 인증이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="c2222-119">Lync Server 2013 인증은 다음의 두 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="c2222-120">클라이언트와 서버 사이에 보안 연결이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="c2222-p107">클라이언트 및 서버가 기존 보안 연결을 사용하여 보내는 메시지에 서명하고 받는 메시지를 확인합니다. 서버에서 인증이 활성화된 경우 클라이언트에서 보낸 인증되지 않은 메시지는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="c2222-p108">사용자 트러스트는 사용자 ID가 아니라 사용자가 생성한 각 메시지에 첨부됩니다. 서버에서는 각 메시지에 올바른 사용자 자격 증명이 있는지 확인합니다. 사용자 자격 증명이 유효하면 메시지를 받는 첫 번째 서버뿐만 아니라 트러스트된 서버 집단의 다른 모든 서버에서도 메시지가 바로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="c2222-126">페더레이션 파트너에서 발급한 유효한 자격 증명이 있는 사용자는 트러스트되지만, 필요한 경우에는 추가적인 제한이 적용되므로 내부 사용자에게 제공되는 전체 권한을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="c2222-127">ICE 및 TURN 프로토콜 역시 IETF TURN RFC에 설명되어 있는 것처럼 다이제스트 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="c2222-128">클라이언트 인증서를 통해 Lync Server 2013에서 사용자를 다른 방식으로 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="c2222-129">사용자 이름 및 암호를 제공하는 대신 사용자가 암호화 시도를 확인하는 데 필요한 인증서 및 해당 인증서에 따른 개인 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="c2222-130">(이 인증서에는 사용자를 식별 하 고, Lync Server 2013을 실행 하는 서버에서 신뢰 하는 루트 CA에서 발급 해야 하며, 인증서의 유효 기간 내에 있어야 하며, 해지 되지 않은 경우에는 주체 이름 또는 주체 대체 이름이 있어야 합니다.) 사용자가 인증을 받기 위해서는 PIN (개인 식별 번호)만 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="c2222-131">인증서는 사용자 이름 및 암호를 입력 하기 어려운 Microsoft Lync 2013 Phone Edition을 실행 하는 전화 및 기타 장치에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2222-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

