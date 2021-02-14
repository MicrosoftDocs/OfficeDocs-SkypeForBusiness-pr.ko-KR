---
title: 비즈니스용 Skype 서버에서 2단계 인증 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: '요약: 비즈니스용 Skype 서버에서 2단계 인증을 관리합니다.'
ms.openlocfilehash: 415eb23779450bc09cdaa25ea2e60b6cf3526e40
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806546"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="4d350-103">비즈니스용 Skype 서버에서 2단계 인증 관리</span><span class="sxs-lookup"><span data-stu-id="4d350-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="4d350-104">**요약:** 비즈니스용 Skype 서버에서 2단계 인증을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="4d350-105">2단계 인증을 사용하면 사용자가 두 가지 형태의 인증 또는 ID, 즉 사용자 이름/암호 조합과 토큰 또는 인증서를 제공하도록 요구하여 보안을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="4d350-106">이를 "있는 것, 알고 있는 것"이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="4d350-107">인증서를 사용하는 2단계 인증의 일반적인 예는 스마트 카드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="4d350-108">스마트 카드에는 사용자 계정과 연결된 인증서가 포함되어 있으며 서버에 저장된 사용자 및 인증서 정보에 대해 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="4d350-109">서버는 사용자 정보(사용자 이름 및 암호)를 제공된 인증서와 비교하여 자격 증명의 유효성을 검사하고 사용자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="4d350-110">2단계 인증을 지원하도록 비즈니스용 Skype 서버 환경을 구성할 때 다음 주제를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="4d350-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="4d350-111">클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="4d350-111">Client Support</span></span>

<span data-ttu-id="4d350-112">Lync Server 2013용 누적 업데이트: 2013년 7월 데스크톱 클라이언트 및 비즈니스용 Skype 클라이언트는 현재 2단계 인증을 지원하는 유일한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="4d350-113">토폴로지 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d350-113">Topology Requirements</span></span>

<span data-ttu-id="4d350-114">고객은 에지, Director 및 사용자 풀이 있는 전용 비즈니스용 Skype 서버를 사용하여 2단계 인증을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="4d350-115">사용자에 대해 수동 인증을 사용하도록 설정하려면 다음을 비롯한 다른 역할 및 서비스에 대해 다른 인증 방법을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="4d350-116">**구성 유형**</span><span class="sxs-lookup"><span data-stu-id="4d350-116">**Configuration Type**</span></span>|<span data-ttu-id="4d350-117">**서비스 종류**</span><span class="sxs-lookup"><span data-stu-id="4d350-117">**Service Type**</span></span>|<span data-ttu-id="4d350-118">**서버 역할**</span><span class="sxs-lookup"><span data-stu-id="4d350-118">**Server Role**</span></span>|<span data-ttu-id="4d350-119">**사용하지 않도록 설정할 인증 유형**</span><span class="sxs-lookup"><span data-stu-id="4d350-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d350-120">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="4d350-120">Web Service</span></span>  <br/> |<span data-ttu-id="4d350-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="4d350-121">WebServer</span></span>  <br/> |<span data-ttu-id="4d350-122">이사</span><span class="sxs-lookup"><span data-stu-id="4d350-122">Director</span></span>  <br/> |<span data-ttu-id="4d350-123">Kerberos, NTLM 및 인증서</span><span class="sxs-lookup"><span data-stu-id="4d350-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="4d350-124">웹 서비스</span><span class="sxs-lookup"><span data-stu-id="4d350-124">Web Service</span></span>  <br/> |<span data-ttu-id="4d350-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="4d350-125">WebServer</span></span>  <br/> |<span data-ttu-id="4d350-126">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="4d350-126">Front End</span></span>  <br/> |<span data-ttu-id="4d350-127">Kerberos, NTLM 및 인증서</span><span class="sxs-lookup"><span data-stu-id="4d350-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="4d350-128">프록시</span><span class="sxs-lookup"><span data-stu-id="4d350-128">Proxy</span></span>  <br/> |<span data-ttu-id="4d350-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="4d350-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="4d350-130">Edge</span><span class="sxs-lookup"><span data-stu-id="4d350-130">Edge</span></span>  <br/> |<span data-ttu-id="4d350-131">Kerberos 및 NTLM</span><span class="sxs-lookup"><span data-stu-id="4d350-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="4d350-132">프록시</span><span class="sxs-lookup"><span data-stu-id="4d350-132">Proxy</span></span>  <br/> |<span data-ttu-id="4d350-133">등록자</span><span class="sxs-lookup"><span data-stu-id="4d350-133">Registrar</span></span>  <br/> |<span data-ttu-id="4d350-134">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="4d350-134">Front End</span></span>  <br/> |<span data-ttu-id="4d350-135">Kerberos 및 NTLM</span><span class="sxs-lookup"><span data-stu-id="4d350-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="4d350-136">서비스 수준에서 이러한 인증 유형을 사용하지 않도록 설정하지 않으면 배포 내에서 2단계 인증을 사용하도록 설정하면 다른 모든 버전의 클라이언트가 성공적으로 로그인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="4d350-137">비즈니스용 Skype 서비스 검색</span><span class="sxs-lookup"><span data-stu-id="4d350-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="4d350-138">내부 및/또는 외부 클라이언트가 비즈니스용 Skype 서비스를 검색하는 데 사용하는 DNS 레코드는 2단계 인증을 사용할 수 없는 비즈니스용 Skype 서버로 확인하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="4d350-139">이 구성에서는 2단계 인증을 사용하도록 설정되지 않은 비즈니스용 Skype 풀의 사용자가 인증을 위해 PIN을 입력할 필요는 없는 반면, 2단계 인증을 사용하도록 설정된 비즈니스용 Skype 풀의 사용자는 인증을 위해 PIN을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="4d350-140">Exchange 인증</span><span class="sxs-lookup"><span data-stu-id="4d350-140">Exchange Authentication</span></span>

<span data-ttu-id="4d350-141">Microsoft Exchange에 대해 2단계 인증을 배포한 고객은 클라이언트의 특정 기능을 사용할 수 없음을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="4d350-142">이는 현재 비즈니스용 Skype 클라이언트가 Exchange 통합에 종속된 기능에 대해 2단계 인증을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="4d350-143">연락처</span><span class="sxs-lookup"><span data-stu-id="4d350-143">Contacts</span></span>

<span data-ttu-id="4d350-144">통합 연락처 저장소 기능을 활용하도록 구성된 비즈니스용 Skype 사용자는 2단계 인증을 사용하여 로그인한 후 해당 연락처를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="4d350-145">**Invoke-CsUcsRollback** cmdlet을 사용하여 2단계 인증을 사용하도록 설정하기 전에 통합 연락처 저장소에서 기존 사용자 연락처를 제거하고 비즈니스용 Skype 서버에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="4d350-146">기술 검색</span><span class="sxs-lookup"><span data-stu-id="4d350-146">Skill Search</span></span>

<span data-ttu-id="4d350-147">비즈니스용 Skype 환경에서 기술 검색 기능을 구성한 고객은 비즈니스용 Skype가 2단계 인증을 사용하도록 설정되어 있는 경우 이 기능이 작동하지 않는다는 것을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="4d350-148">이는 Microsoft SharePoint가 현재 2단계 인증을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="4d350-149">자격 증명</span><span class="sxs-lookup"><span data-stu-id="4d350-149">Credentials</span></span>

<span data-ttu-id="4d350-150">저장된 비즈니스용 Skype 자격 증명과 관련된 배포 고려 사항은 2단계 인증을 사용하도록 구성된 사용자에게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="4d350-151">저장된 자격 증명 삭제</span><span class="sxs-lookup"><span data-stu-id="4d350-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="4d350-152">사용자는 2단계 인증을 사용하여 처음으로 로그인하기 전에 비즈니스용 Skype 클라이언트에서 내 로그인 정보 삭제 옵션을 사용하고 %localappdata%\Microsoft\Office\15.0\비즈니스용 Skype에서 SIP 프로필 폴더를 삭제해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="4d350-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="4d350-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="4d350-153">DisableNTCredentials</span></span>

<span data-ttu-id="4d350-154">Kerberos 또는 NTLM 인증 방법을 사용하는 경우 사용자의 Windows 자격 증명이 인증에 자동으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="4d350-155">Kerberos 및/또는 NTLM이 인증을 사용하도록 설정된 일반적인 비즈니스용 Skype 서버 배포에서는 사용자가 로그인할 때마다 자격 증명을 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="4d350-156">사용자에게 PIN을 입력하라는 메시지가 표시되기 전에 사용자에게 자격 증명을 입력하라는 메시지가 표시되면 **DisableNTCredentials** 레지스트리 키가 클라이언트 컴퓨터에서 그룹 정책을 통해 의도하지 않은 것으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="4d350-157">자격 증명에 대한 추가 메시지가 표시되지 않도록 설정하기 위해 로컬 작업소에서 다음 레지스트리 항목을 만들거나 비즈니스용 Skype 관리 템플릿을 사용하여 그룹 정책을 사용하여 특정 풀의 모든 사용자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="4d350-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="4d350-158">SavePassword</span></span>

<span data-ttu-id="4d350-159">사용자가 처음으로 비즈니스용 Skype에 로그인하면 암호를 저장하라는 메시지가 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="4d350-160">이 옵션을 선택하면 사용자의 클라이언트 인증서를 개인 인증서 저장소에 저장하고 사용자의 Windows 자격 증명을 로컬 컴퓨터의 자격 증명 관리자에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="4d350-161">비즈니스용 Skype가 2단계 인증을 지원하도록 구성된 경우 **SavePassword** 레지스트리 설정을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="4d350-162">사용자가 암호를 저장하지 못하게 설정하기 위해 로컬 작업소에서 다음 레지스트리 항목을 변경하거나 비즈니스용 Skype 관리 템플릿을 사용하여 그룹 정책을 사용하여 특정 풀의 모든 사용자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="4d350-163">AD FS 2.0 토큰 재생</span><span class="sxs-lookup"><span data-stu-id="4d350-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="4d350-164">AD FS 2.0은 토큰 재생 검색이라고 하는 기능을 제공합니다. 이 기능을 통해 동일한 토큰을 사용하는 여러 토큰 요청을 검색한 다음 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="4d350-165">이 기능을 사용하는 경우 토큰 재생 검색은 동일한 토큰이 두 번 이상 사용되지 않는지 확인하여 WS-Federation 수동 프로필과 SAML WebSSO 프로필 둘 다에서 인증 요청의 무결성을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="4d350-166">키오스크를 사용하는 경우와 같이 보안이 매우 중요한 상황에서 이 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="4d350-167">토큰 재생 검색에 대한 자세한 내용은 [AD FS 2.0의](https://go.microsoft.com/fwlink/p/?LinkId=309215)보안 계획 및 배포 모범 사례를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d350-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="4d350-168">외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="4d350-168">External User Access</span></span>

<span data-ttu-id="4d350-169">외부 네트워크에서 비즈니스용 Skype 2단계 인증을 지원하도록 ADFS 프록시 또는 역방향 프록시를 구성하는 방법은 이 항목에서 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d350-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d350-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d350-170">See also</span></span>

[<span data-ttu-id="4d350-171">비즈니스용 Skype 서버에서 2단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="4d350-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
