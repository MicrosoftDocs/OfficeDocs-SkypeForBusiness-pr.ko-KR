---
title: 비즈니스용 Skype 서버에 대 한 사용자 및 클라이언트 인증
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
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 신뢰할 수 있는 사용자는 비즈니스용 Skype 서버의 신뢰할 수 있는 서버에서 자격 증명을 인증 한 것입니다. 이 서버는 일반적으로 스탠더드 버전 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다. 비즈니스용 Skype Server는 Active Directory 도메인 서비스를 사용자 자격 증명의 단일 신뢰할 수 있는 백 엔드 리포지토리로 사용 합니다.
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815586"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="eeac2-105">비즈니스용 Skype 서버에 대 한 사용자 및 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="eeac2-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="eeac2-106">신뢰할 수 있는 사용자는 비즈니스용 Skype 서버의 신뢰할 수 있는 서버에서 자격 증명을 인증 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="eeac2-107">이 서버는 일반적으로 스탠더드 버전 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="eeac2-108">비즈니스용 Skype Server는 Active Directory 도메인 서비스를 사용자 자격 증명의 단일 신뢰할 수 있는 백 엔드 리포지토리로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="eeac2-109">인증은 신뢰할 수 있는 서버에 대 한 사용자 자격 증명을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="eeac2-110">비즈니스용 Skype 서버는 사용자의 상태와 위치에 따라 다음 인증 프로토콜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="eeac2-111">Active Directory 자격 증명을 사용 하는 내부 사용자 용 **MIT Kerberos 버전 5 보안 프로토콜** 입니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-111">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="eeac2-112">Kerberos에는 Active Directory 도메인 서비스에 대 한 클라이언트 연결이 필요 하며,이 때문에 회사 방화벽 외부에서 클라이언트를 인증 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-112">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="eeac2-113">회사 방화벽 외부의 끝점에서 연결 하는 Active Directory 자격 증명이 있는 사용자에 대 한 **NTLM 프로토콜** 입니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-113">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="eeac2-114">액세스에 지 서비스가 로그인 요청을 디렉터 (있는 경우) 또는 프런트 엔드 서버 (인증)에 게 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-114">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="eeac2-115">액세스에 지 서비스 자체는 인증을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-115">The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eeac2-116">NTLM 프로토콜은 Kerberos 보다 약한 공격 보호 기능을 제공 하므로 일부 조직에서는 NTLM의 사용을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="eeac2-117">따라서 비즈니스용 Skype 서버에 대 한 액세스가 VPN 또는 DirectAccess 연결을 통해 연결 된 내부 또는 클라이언트로 제한 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="eeac2-118">익명 사용자 라고 불리는 **다이제스트 프로토콜** 입니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-118">**Digest protocol** for so-called anonymous users.</span></span> <span data-ttu-id="eeac2-119">익명 사용자는 Active Directory 자격 증명을 인식할 수 없지만 온-프레미스 회의에 초대 하 고 유효한 컨퍼런스 키를 소유 하는 사용자 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-119">Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key.</span></span> <span data-ttu-id="eeac2-120">다이제스트 인증은 다른 클라이언트 조작에는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-120">Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="eeac2-121">비즈니스용 Skype 서버 인증은 다음 두 단계로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="eeac2-122">클라이언트와 서버 간에 보안 연결이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="eeac2-123">클라이언트와 서버는 기존 보안 연결을 사용 하 여 보내는 메시지에 서명 하 고 자신이 받은 메시지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-123">The client and server use the existing security association to sign messages that they send and to verify the messages they receive.</span></span> <span data-ttu-id="eeac2-124">서버에서 인증을 사용 하도록 설정 되어 있는 경우에는 클라이언트의 인증 되지 않은 메시지가 수락 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-124">Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="eeac2-125">사용자 신뢰는 사용자 id 자체가 아니라 사용자 로부터 들어오는 각 메시지에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-125">User trust is attached to each message that originates from a user, not to the user identity itself.</span></span> <span data-ttu-id="eeac2-126">서버가 각 메시지에 유효한 사용자 자격 증명을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-126">The server checks each message for valid user credentials.</span></span> <span data-ttu-id="eeac2-127">사용자 자격 증명이 유효 하 게 표시 되는 경우에는 해당 메시지가 첫 번째 서버 에서만 수신 되 고 신뢰 된 서버 클라우드의 다른 모든 서버에서 unchallenged 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-127">If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="eeac2-128">페더레이션 파트너가 발급 하는 유효한 자격 증명을 사용 하는 사용자는 신뢰할 수 있지만 필요에 따라 추가 제약 조건에서 내부 사용자에 게 적용 되는 모든 범위의 권한을 제공 하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="eeac2-129">또한 얼음 및 선반 가공 프로토콜은 IETF RFC에서 설명한 대로 다이제스트 챌린지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="eeac2-130">클라이언트 인증서는 비즈니스용 Skype 서버에서 사용자를 인증 하는 대체 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="eeac2-131">사용자 이름 및 암호를 제공 하는 대신, 사용자는 인증서와 암호화 챌린지를 해결 하는 데 필요한 인증서에 해당 하는 개인 키를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="eeac2-132">(이 인증서에는 사용자를 식별 하는 주체 이름 또는 주체 대체 이름이 있어야 하며, 비즈니스용 Skype Server를 실행 하는 서버에서 신뢰 하는 루트 CA가 발급 해야 하며, 인증서의 유효 기간 내에 있어야 하며, 해지 되지 않았습니다.) 인증을 받기 위해 사용자는 PIN (개인 식별 번호)을 입력 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="eeac2-133">인증서는 사용자 이름 및 암호를 입력 하는 것이 어려운 전화, 휴대 전화 및 기타 장치에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="eeac2-134">ASP .NET 4.5으로 인 한 암호화 요구 사항</span><span class="sxs-lookup"><span data-stu-id="eeac2-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="eeac2-135">비즈니스용 Skype Server 2015 CU5의 경우 ASP.NET 4.6에는 AES가 지원 되지 않으며,이로 인해 Skype 모임 앱이 시작 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="eeac2-136">클라이언트가 컴퓨터 키 유효성 검사 값으로 AES를 사용 하는 경우에는 IIS의 Skype Meeting App site level에서 컴퓨터 키 값을 SHA-1 또는 다른 지원 되는 알고리즘으로 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="eeac2-137">필요한 경우 [IIS 8.0 ASP.NET 구성 관리](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) 에 대 한 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eeac2-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="eeac2-138">기타 지원 되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-138">Other supported values are:</span></span>
  
- <span data-ttu-id="eeac2-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="eeac2-139">HMACSHA256</span></span>
    
- <span data-ttu-id="eeac2-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="eeac2-140">HMACSHA384</span></span>
    
- <span data-ttu-id="eeac2-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="eeac2-141">HMACSHA512</span></span>
    
  <span data-ttu-id="eeac2-142">AES, 3DES 및 MD5 값은 ASP.NET 4에 비해 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="eeac2-143">[ASP.NET 4.5, pt. 2의 암호화 개선](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) 사항에 대 한 세부 정보가 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeac2-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
  
