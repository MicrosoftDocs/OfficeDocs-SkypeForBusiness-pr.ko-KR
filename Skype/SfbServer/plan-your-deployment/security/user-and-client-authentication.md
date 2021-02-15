---
title: 비즈니스용 Skype 서버에 대한 사용자 및 클라이언트 인증
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
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 신뢰할 수 있는 사용자는 비즈니스용 Skype 서버에서 신뢰할 수 있는 서버에서 자격 증명을 인증한 사용자입니다. 이 서버는 일반적으로 Standard Edition 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다. 비즈니스용 Skype 서버는 Active Directory 도메인 서비스를 사용자 자격 증명의 신뢰할 수 있는 단일 백 엔드 리포지토리로 이용합니다.
ms.openlocfilehash: bf0bde8478cd6c4e2eb068ffade7fba7fac14d56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832008"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="37e99-105">비즈니스용 Skype 서버에 대한 사용자 및 클라이언트 인증</span><span class="sxs-lookup"><span data-stu-id="37e99-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="37e99-106">신뢰할 수 있는 사용자는 비즈니스용 Skype 서버에서 신뢰할 수 있는 서버에서 자격 증명을 인증한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="37e99-107">이 서버는 일반적으로 Standard Edition 서버, Enterprise Edition 프런트 엔드 서버 또는 디렉터입니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="37e99-108">비즈니스용 Skype 서버는 Active Directory 도메인 서비스를 사용자 자격 증명의 신뢰할 수 있는 단일 백 엔드 리포지토리로 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="37e99-109">인증은 트러스트된 서버에 대한 사용자 자격 증명을 제공하는 과정입니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="37e99-110">비즈니스용 Skype 서버는 사용자의 상태 및 위치에 따라 다음 인증 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="37e99-p104">Active Directory 자격 증명이 있는 내부 사용자를 위한 **MIT Kerberos 버전 5 보안 프로토콜**. Kerberos를 사용하려면 클라이언트가 Active Directory 도메인 서비스에 연결해야 하므로, 회사 방화벽 외부의 클라이언트를 인증하는 데는 Kerberos를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-p104">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="37e99-p105">회사 방화벽 외부의 끝점에서 연결하며 Active Directory 자격 증명이 있는 사용자를 위한 **NTLM 프로토콜**. 액세스 에지 서비스는 인증을 위해 로그온 요청을 디렉터(있는 경우) 또는 프런트 엔드 서버로 전달합니다. 액세스 에지 서비스 자체는 인증을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-p105">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="37e99-116">NTLM 프로토콜은 Kerberos보다 공격 보호 수준이 낮으므로 일부 조직에서는 NTLM 사용을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="37e99-117">따라서 비즈니스용 Skype 서버에 대한 액세스는 VPN 또는 DirectAccess 연결을 통해 연결된 내부 또는 클라이언트로 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="37e99-p107">익명 사용자를 위한 **다이제스트 프로토콜**. 익명 사용자는 인식할 수 있는 Active Directory 자격 증명을 가지고 있지는 않지만 온-프레미스 전화 회의에 초대를 받았으며 유효한 전화 회의 키를 소유한 외부 사용자입니다. 다른 클라이언트 상호 작용에는 다이제스트 인증이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="37e99-121">비즈니스용 Skype 서버 인증은 다음 두 단계로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="37e99-122">클라이언트와 서버 사이에 보안 연결이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="37e99-p108">클라이언트 및 서버가 기존 보안 연결을 사용하여 보내는 메시지에 서명하고 받는 메시지를 확인합니다. 서버에서 인증이 활성화된 경우 클라이언트에서 보낸 인증되지 않은 메시지는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="37e99-p109">사용자 트러스트는 사용자 ID가 아니라 사용자가 생성한 각 메시지에 첨부됩니다. 서버에서는 각 메시지에 올바른 사용자 자격 증명이 있는지 확인합니다. 사용자 자격 증명이 유효하면 메시지를 받는 첫 번째 서버뿐만 아니라 트러스트된 서버 집단의 다른 모든 서버에서도 메시지가 바로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="37e99-128">페더레이션 파트너에서 발급한 유효한 자격 증명이 있는 사용자는 트러스트되지만, 필요한 경우에는 추가적인 제한이 적용되므로 내부 사용자에게 제공되는 전체 권한을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="37e99-129">ICE 및 TURN 프로토콜 역시 IETF TURN RFC에 설명되어 있는 것처럼 다이제스트 방식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="37e99-130">클라이언트 인증서는 사용자를 비즈니스용 Skype 서버에서 인증할 수 있는 대체 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="37e99-131">사용자 이름 및 암호를 제공하는 대신 사용자가 암호화 시도를 확인하는 데 필요한 인증서 및 해당 인증서에 따른 개인 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="37e99-132">(이 인증서에는 사용자를 식별하는 주체 이름 또는 주체 대체 이름이 있어야 합니다. 비즈니스용 Skype 서버를 실행하는 서버에서 신뢰하는 루트 CA에서 발급해야 하며 인증서의 유효 기간 내에 있으며 해지되지 않은 것입니다.) 인증을 위해 사용자는 PIN(개인 식별 번호)만 입력하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="37e99-133">인증서는 전화, 휴대폰 및 사용자 이름과 암호를 입력하기 어려운 기타 장치에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="37e99-134">ASP .NET 4.5로 인한 암호화 요구 사항</span><span class="sxs-lookup"><span data-stu-id="37e99-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="37e99-135">비즈니스용 Skype 서버 2015 CU5부터는 ASP.NET 4.6에 대해 AES가 지원되지 않습니다. 이로 인해 Skype 모임 앱이 시작되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="37e99-136">클라이언트가 AES를 컴퓨터 키 유효성 검사 값으로 사용하는 경우 IIS의 Skype 모임 앱 사이트 수준에서 컴퓨터 키 값을 SHA-1 또는 다른 지원 알고리즘으로 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="37e99-137">필요한 경우 [IIS 8.0](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) ASP.NET 구성 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37e99-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="37e99-138">지원되는 다른 값은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-138">Other supported values are:</span></span>
  
- <span data-ttu-id="37e99-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="37e99-139">HMACSHA256</span></span>
    
- <span data-ttu-id="37e99-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="37e99-140">HMACSHA384</span></span>
    
- <span data-ttu-id="37e99-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="37e99-141">HMACSHA512</span></span>
    
  <span data-ttu-id="37e99-142">AES, 3DES 및 MD5 값은 한 번은 4번에 ASP.NET 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="37e99-143">[ASP.NET 4.5, pt. 2의](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) 암호화 개선 사항은 더 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37e99-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
  
