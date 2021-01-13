---
title: 비즈니스용 Skype 서버에서 등록자 구성 설정 관리
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '요약: 비즈니스용 Skype 서버에 대한 등록자 구성 설정을 관리합니다.'
ms.openlocfilehash: 9a56e803470054ab8c2ba3cf9e2c758d4e71e17a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828328"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a5386-103">비즈니스용 Skype 서버에서 등록자 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="a5386-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a5386-104">**요약:** 비즈니스용 Skype 서버에 대한 등록자 구성 설정을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="a5386-105">등록자에서 프록시 서버 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-105">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="a5386-106">지정하는 인증 프로토콜에 따라 풀의 서버가 클라이언트에 대해 어떤 유형의 문제를 챌린지로 챌린지할지 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-106">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="a5386-107">사용 가능한 프로토콜은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-107">The available protocols are:</span></span>
  
- <span data-ttu-id="a5386-108">**Kerberos** 클라이언트에서 사용할 수 있는 가장 강력한 암호 기반 인증 체계이지만 일반적으로는 키 배포 센터(Kerberos 도메인 컨트롤러)에 대한 클라이언트 연결이 필요하기 때문에 엔터프라이즈 클라이언트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="a5386-109">이 설정은 서버에서 엔터프라이즈 클라이언트만 인증하는 경우 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="a5386-110">**NTLM** 암호에 대해 챌린지 응답 해시 체계를 사용하는 클라이언트에서 사용할 수 있는 암호 기반 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="a5386-111">원격 사용자와 같은 키 배포 센터(Kerberos 도메인 컨트롤러)에 연결하지 않고 클라이언트에서 사용할 수 있는 유일한 인증 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="a5386-112">서버에서 원격 사용자만 인증하는 경우 NTLM을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="a5386-113">**인증서 인증** 서버가 Lync Phone Edition 클라이언트, 공통 영역 전화, 비즈니스용 Skype 및 Lync Windows 스토어 앱에서 인증서를 얻어야 하는 경우의 새로운 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="a5386-114">Lync Phone Edition 클라이언트에서 사용자가 로그인하고 PIN(개인 식별 번호)을 제공하여 인증된 후 비즈니스용 Skype 서버는 전화에 SIP URI를 프로비전하고 비즈니스용 Skype 서버 서명 인증서 또는 Joe(예: SN=joe@contoso.com)를 휴대폰에 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="a5386-115">이 인증서는 등록자 및 웹 서비스에 대한 인증에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5386-p105">서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="a5386-120">Lync Windows 스토어 앱 클라이언트를 사용하려면 인증서 인증을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="a5386-121">새 등록자 구성 설정을 만들하려면</span><span class="sxs-lookup"><span data-stu-id="a5386-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="a5386-122">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a5386-123">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a5386-124">왼쪽 탐색 표시줄에서 **보안**, **등록자** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a5386-125">등록자 **페이지에서** 새로 **고치기 클릭**</span><span class="sxs-lookup"><span data-stu-id="a5386-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="a5386-126">서비스 **선택에서** 등록자가 적용될 서비스를 클릭한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a5386-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="a5386-127">새 **등록자 설정에서** 사용자 환경의 지원 및 클라이언트 기능에 따라 다음 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a5386-128">**Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="a5386-129">**NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="a5386-130">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="a5386-131">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="a5386-132">기존 등록자 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="a5386-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="a5386-133">등록자를 사용하여 프록시 서버 인증 프토토콜을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a5386-p106">서버에서 원격 클라이언트 및 엔터프라이즈 클라이언트 둘 다에 대한 인증을 지원할 경우 Kerberos 및 NTLM을 모두 사용하도록 설정하는 것이 좋습니다. 이렇게 하면 원격 클라이언트에는 NTLM 인증만 제공되도록 에지 서버와 내부 서버가 통신합니다. 이 서버에서 Kerberos만 사용하도록 설정한 경우에는 원격 사용자를 인증할 수 없습니다. 서버에 대해 엔터프라이즈 사용자를 인증할 경우에도 Kerberos가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="a5386-138">다음 단계에 따라 기존의 등록자를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="a5386-139">기존 등록자 구성 설정을 수정하려면</span><span class="sxs-lookup"><span data-stu-id="a5386-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="a5386-140">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a5386-141">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a5386-142">왼쪽 탐색 표시줄에서 **보안**, **등록자** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a5386-143">**등록자** 페이지에서 서비스를 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a5386-144">환경의 지원 및 클라이언트 기능에 따라 **등록자 설정 편집** 에서 다음 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a5386-145">**Kerberos 인증 사용** - 이 풀의 서버가 Kerberos 인증을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="a5386-146">**NTLM 인증 사용** - 이 풀의 서버가 NTLM을 사용하여 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="a5386-147">**인증서 인증 사용** - 이 풀의 서버가 클라이언트에 대한 인증서를 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="a5386-148">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="a5386-149">등록자 구성 설정을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="a5386-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="a5386-150">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a5386-151">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a5386-152">왼쪽 탐색 표시줄에서 **보안**, **등록자** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="a5386-153">등록자 **페이지 및** 검색 필드에 삭제할 등록자 이름 전체 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="a5386-154">목록에서 원하는 등록자, 편집을 **클릭한** 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a5386-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="a5386-155">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a5386-156">cmdlet을 사용하여 등록자 구성 Windows PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="a5386-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a5386-157">등록자 구성 설정은 **Remove-CsProxyConfiguration** cmdlet과 Windows PowerShell 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="a5386-158">비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a5386-159">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5386-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a5386-160">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="a5386-161">특정 등록자 보안 설정 집합을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a5386-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="a5386-162">다음 명령은 에지 서버 에지 서버에 적용된 등록자 보안 설정을 atl-edge-011.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="a5386-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="a5386-163">사이트 범위에 적용된 모든 등록자 보안 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a5386-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="a5386-164">다음 명령은 등록자 서비스에 적용된 모든 등록자 보안 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="a5386-165">NTLM 인증을 허용하는 모든 등록자 보안 설정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a5386-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="a5386-166">다음 명령은 클라이언트 인증에 NTLM을 사용할 수 있는 모든 등록자 보안 설정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="a5386-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="a5386-167">자세한 내용은 [Remove-CsProxyConfiguration을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a5386-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

