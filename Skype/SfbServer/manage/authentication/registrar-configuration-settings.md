---
title: 비즈니스용 Skype 서버에서 등록자 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '요약: 비즈니스용 Skype 서버에 대 한 등록자 구성 설정을 관리 합니다.'
ms.openlocfilehash: 4ad7815da0744a78cd72208ef390362bff26c2ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191865"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e228d-103">비즈니스용 Skype 서버에서 등록자 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="e228d-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e228d-104">**요약:** 비즈니스용 Skype 서버에 대 한 등록자 구성 설정을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="e228d-105">레지스트라를 사용 하 여 프록시 서버 인증 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-105">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="e228d-106">지정 하는 인증 프로토콜은 풀의 서버가 클라이언트에 발급 하는 챌린지 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-106">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="e228d-107">사용할 수 있는 프로토콜은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-107">The available protocols are:</span></span>
  
- <span data-ttu-id="e228d-108">**커버로스** 이는 클라이언트가 사용할 수 있는 가장 강력한 암호 기반 인증 구성표 이지만 일반적으로 키 배포 센터 (Kerberos 도메인 컨트롤러)에 대 한 클라이언트 연결이 필요 하기 때문에 엔터프라이즈 클라이언트 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="e228d-109">이 설정은 서버에서 엔터프라이즈 클라이언트만 인증 하는 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="e228d-110">**NTLM** 암호에 챌린지 응답 해싱 스키마를 사용 하는 클라이언트가 사용할 수 있는 암호 기반 인증입니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="e228d-111">이것은 원격 사용자와 같은 키 배포 센터 (Kerberos 도메인 컨트롤러)에 연결 되지 않고 클라이언트가 사용할 수 있는 유일한 인증 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="e228d-112">서버에서 원격 사용자만 인증 하는 경우 NTLM을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="e228d-113">**인증서 인증** 이는 서버가 Lync Phone Edition 클라이언트, 공통 지역 전화, 비즈니스용 Skype 및 Lync Windows 스토어 앱에서 인증서를 받아야 하는 경우의 새로운 인증 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="e228d-114">Lync Phone Edition 클라이언트에서 사용자가 로그인 한 후 PIN (개인 식별 번호)을 제공 하 여 성공적으로 인증 되 고 나면 비즈니스용 Skype 서버에서 SIP URI를 프로 비전 하 여 비즈니스용 Skype 서버에 로그인 합니다. 전화에서 Joe (예: SN=joe@contoso.com)를 식별 하는 인증서 또는 사용자 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="e228d-115">이 인증서는 레지스트라 및 웹 서비스를 사용 하 여 인증 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e228d-116">서버에서 원격 및 엔터프라이즈 클라이언트에 대 한 인증을 지 원하는 경우 Kerberos와 NTLM을 모두 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-116">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="e228d-117">Edge 서버와 내부 서버는 원격 클라이언트에만 NTLM 인증만 제공 되도록 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-117">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="e228d-118">이러한 서버에서 Kerberos만 사용 하도록 설정 된 경우에는 원격 사용자를 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-118">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="e228d-119">엔터프라이즈 사용자도 서버에 대해 인증 하는 경우 Kerberos가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-119">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="e228d-120">Lync Windows 스토어 앱 클라이언트를 사용 하는 경우 인증서 인증을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="e228d-121">새 등록자 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e228d-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="e228d-122">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="e228d-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e228d-123">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e228d-124">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="e228d-125">**등록자** 페이지에서 **새로 만들기** 클릭</span><span class="sxs-lookup"><span data-stu-id="e228d-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="e228d-126">**서비스 선택**에서 등록 기관에 적용할 서비스를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="e228d-127">**새 등록자 설정**에서 해당 환경의 클라이언트 및 지원 기능에 따라 다음 중 하나 이상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="e228d-128">Kerberos **인증을 사용** 하 여 풀의 서버에서 kerberos 인증을 사용 하 여 문제를 해결 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="e228d-129">**Ntlm 인증을 사용** 하 여 풀의 서버에서 ntlm을 사용 하는 데 문제가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="e228d-130">**인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="e228d-131">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="e228d-132">기존 등록자 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="e228d-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="e228d-133">레지스트라를 사용 하 여 프록시 서버 인증 프로토콜을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e228d-134">서버에서 원격 및 엔터프라이즈 클라이언트에 대 한 인증을 지 원하는 경우 Kerberos와 NTLM을 모두 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-134">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="e228d-135">Edge 서버와 내부 서버는 원격 클라이언트에만 NTLM 인증만 제공 되도록 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-135">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="e228d-136">이러한 서버에서 Kerberos만 사용 하도록 설정 된 경우에는 원격 사용자를 인증할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-136">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="e228d-137">엔터프라이즈 사용자도 서버에 대해 인증 하는 경우 Kerberos가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-137">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="e228d-138">기존 등록자를 수정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e228d-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="e228d-139">기존 등록자 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="e228d-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="e228d-140">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="e228d-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e228d-141">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e228d-142">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="e228d-143">**등록자** 페이지에서 서비스를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e228d-144">**등록자 편집 설정**에서 해당 환경의 클라이언트 및 지원의 기능에 따라 다음 중 하나 이상을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="e228d-145">Kerberos **인증을 사용** 하 여 풀의 서버에서 kerberos 인증을 사용 하 여 문제를 해결 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="e228d-146">**Ntlm 인증을 사용** 하 여 풀의 서버에서 ntlm을 사용 하는 데 문제가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="e228d-147">**인증서 인증을 사용 하도록 설정** 하 여 풀의 서버가 클라이언트에 인증서를 발급 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="e228d-148">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="e228d-149">등록자 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="e228d-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="e228d-150">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="e228d-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e228d-151">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e228d-152">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="e228d-153">**등록자** 페이지에서 검색 필드에 삭제 하려는 등록자의 이름을 전부 또는 일부 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="e228d-154">목록에서 원하는 등록 기관을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="e228d-155">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e228d-156">Windows PowerShell Cmdlet을 사용 하 여 등록자 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="e228d-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e228d-157">Windows PowerShell 및 **제거-CsProxyConfiguration** cmdlet을 사용 하 여 등록자 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="e228d-158">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e228d-159">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e228d-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e228d-160">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="e228d-161">특정 등록자 보안 설정 집합을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e228d-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="e228d-162">다음 명령은 edge Server atl-edge-011.litwareinc.com에 적용 된 등록자 보안 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="e228d-163">사이트 범위에 적용 된 모든 등록자 보안 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e228d-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="e228d-164">다음 명령을 실행 하면 등록자 서비스에 적용 된 모든 등록자 보안 설정이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="e228d-165">NTLM 인증을 허용 하는 모든 등록자 보안 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e228d-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="e228d-166">다음 명령은 클라이언트 인증에 NTLM을 사용할 수 있는 모든 등록자 보안 설정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e228d-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="e228d-167">자세한 내용은 [-CsProxyConfiguration 제거](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e228d-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

