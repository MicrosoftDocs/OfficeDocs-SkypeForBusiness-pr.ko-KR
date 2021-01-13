---
title: 비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '요약: 비즈니스용 Skype와 함께 사용되는 비즈니스용 Skype Web App 및 Skype 모임 앱을 배포합니다.'
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805928"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="51813-103">비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="51813-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="51813-104">**요약:** 비즈니스용 Skype 서버와 함께 사용되는 비즈니스용 Skype 2015 Web App 및 Skype 모임 앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="51813-105">비즈니스용 Skype Web App은 비즈니스용 Skype 서버를 실행하는 서버에 설치되는 IIS(인터넷 정보 서비스) 웹 클라이언트로, 기본적으로 비즈니스용 Skype 클라이언트가 아직 없는 사용자를 충족하기 위해 요청 시 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="51813-106">이러한 모임 사용자는 네트워크 외부에서 연결하지 않는 것보다 더 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="51813-107">사용자가 모임 URL을 클릭하지만 비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 최신 버전의 비즈니스용 Skype Web App, Skype 모임 앱 또는 Mac용 비즈니스용 Skype를 사용하여 모임에 참가할 수 있는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="51813-108">비즈니스용 Skype Web App의 음성, 비디오 및 공유 기능을 사용하려면 ActiveX 브라우저에서 플러그 인으로 사용되는 Microsoft ActiveX 컨트롤이 필요하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="51813-109">ActiveX 컨트롤을 미리 설치하거나 메시지가 표시될 때 설치하도록 허용할 수 있습니다. 이 경우 사용자가 비즈니스용 Skype Web App을 처음 사용할 때 또는 사용자가 ActiveX 컨트롤이 필요한 기능에 처음 액세스할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="51813-110">비즈니스용 Skype 서버 에지 서버 배포에서는 비즈니스용 Skype Web App 클라이언트 액세스에 경계 네트워크의 HTTPS 역방향 프록시가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="51813-111">단순 URL도 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-111">You must also publish simple URLs.</span></span> <span data-ttu-id="51813-112">자세한 내용은 비즈니스용 Skype 서버에서 단순 URL에 대한 역방향 프록시 서버 및 DNS 요구 사항 [설정을 참조하세요.](../../plan-your-deployment/network-requirements/simple-urls.md) [](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)</span><span class="sxs-lookup"><span data-stu-id="51813-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="51813-113">비즈니스용 Skype 웹앱에 다단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="51813-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="51813-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="51813-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="51813-115">비즈니스용 Skype Web App, Skype 모임 앱 및 Mac용 비즈니스용 Skype는 다단계 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="51813-116">사용자 이름 및 암호 외에도 비즈니스용 Skype 모임에 로그인할 때 외부 네트워크에서 참가하는 사용자를 인증하기 위해 스마트 카드 또는 PINS와 같은 추가 인증 방법이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="51813-117">AD FS(Active Directory Federation Service) 페더링 서버를 배포하고 비즈니스용 Skype 서버에서 수동 인증을 사용하도록 설정하여 다단계 인증을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="51813-118">AD FS를 구성한 후 비즈니스용 Skype 모임에 참가하려는 외부 사용자에게는 구성한 추가 인증 방법과 함께 사용자 이름 및 암호 챌린지가 포함된 AD FS 다단계 인증 웹 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51813-119">다단계 인증을 위해 AD FS를 구성할 계획인 경우 중요한 고려 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="51813-120">다단계 ADFS 인증은 모임 참가자와 이끌이가 같은 조직에 둘 다 있는 경우 작동하며 AD FS 페더맹 조직에서 모두 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="51813-121">다단계 ADFS 인증은 Lync 서버 웹 인프라에서 현재 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="51813-122">하드웨어 부하 균형을 사용하는 경우 비즈니스용 Skype Web App 또는 모임 앱 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리될 수 있도록 부하 균형 조정기에서 쿠키 지속을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="51813-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="51813-123">비즈니스용 Skype 서버와 AD FS 서버 간에 신뢰 관계 트러스트가 설정되는 경우 비즈니스용 Skype 모임의 최대 기간에 걸쳐 충분한 토큰 수명을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="51813-124">일반적으로 토큰 수명은 240분으로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="51813-125">이 구성은 Lync 모바일 클라이언트에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="51813-126">다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="51813-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="51813-127">AD FS 페더ation 서버 역할을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="51813-128">자세한 내용은 Active [Directory Federation Services 2.0 배포 가이드를 참조하십시오.](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="51813-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="51813-129">AD FS용 인증서를 만드시다.</span><span class="sxs-lookup"><span data-stu-id="51813-129">Create certificates for AD FS.</span></span> <span data-ttu-id="51813-130">자세한 내용은 Single Sign-On 항목에 사용할 AD FS 배포 및 계획의 "페더전 서버 [인증서"](https://go.microsoft.com/fwlink/p/?LinkId=285376) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51813-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="51813-131">명령줄 Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="51813-132">다음 명령을 실행하여 파트너 관계를 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="51813-133">다음의 레지스터링자 규칙을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="51813-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="51813-134">BranchCache를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="51813-134">Disable BranchCache</span></span>
<span data-ttu-id="51813-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="51813-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="51813-136">Windows 7 및 Windows Server 2008 R2의 BranchCache 기능은 비즈니스용 Skype Web App 웹 구성 요소를 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="51813-137">비즈니스용 Skype Web App 사용자의 문제를 방지할 수 있도록 BranchCache가 사용하도록 설정되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="51813-138">BranchCache를 사용 안 하게 하는 자세한 내용은 [BranchCache 배포 가이드를 참조하십시오.](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="51813-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="51813-139">비즈니스용 Skype Web App 배포 확인</span><span class="sxs-lookup"><span data-stu-id="51813-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="51813-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="51813-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="51813-141">Test-CsUcwaConference cmdlet을 사용하여 한 쌍의 테스트 사용자가 UCWA(Unified Communications Web API)를 사용하여 회의에 참가할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="51813-142">이 cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서에서 [Test-CsUcwaConference를](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="51813-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="51813-143">Windows Server 2008 R2에서 플러그 인 설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="51813-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="51813-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="51813-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="51813-145">Windows Server 2008 R2를 실행하는 컴퓨터에서 플러그 인을 설치하지 못하는 경우 Internet Explorer 보안 설정 또는 DisableMSI 레지스트리 키 설정을 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="51813-146">2016에서 보안 설정을 Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="51813-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="51813-147">Internet Explorer를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="51813-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="51813-148">도구를 **클릭하고** **인터넷 옵션을 클릭한** 다음 **고급을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="51813-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="51813-149">보안 섹션까지 **아래로 스크롤합니다.**</span><span class="sxs-lookup"><span data-stu-id="51813-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="51813-150">암호화된 **페이지를 디스크에 저장하지** 않는 선택을 취소하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="51813-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51813-151">이 설정을 선택하면 비즈니스용 Skype Web App에서 첨부 파일을 다운로드하려고 할 때도 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="51813-152">모임에 다시 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-152">Rejoin the meeting.</span></span> <span data-ttu-id="51813-153">오류 없이 플러그 인을 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="51813-154">DisableMSI 레지스트리 설정 수정</span><span class="sxs-lookup"><span data-stu-id="51813-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="51813-155">**시작** 을 클릭한 다음 **실행** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="51813-156">레지스트리 편집기에 액세스하기 위해 **regedit를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="51813-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="51813-157">사이트로 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span><span class="sxs-lookup"><span data-stu-id="51813-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="51813-158">다음 형식의 DisableMSI 레지스트리 키를 편집하거나 추가하고 REG_DWORD 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="51813-159">모임에 다시 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="51813-160">비즈니스용 Skype 웹앱을 바꾸기 위해 Skype 모임 앱을 사용하도록 설정(선택 사항, 비즈니스용 Skype 서버 2015만 해당)</span><span class="sxs-lookup"><span data-stu-id="51813-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="51813-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="51813-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="51813-162">이 절차는 선택 사항이며 비즈니스용 Skype 서버 2015 CU5 이상에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="51813-163">이 기능을 사용하지 않는 경우 외부 사용자는 비즈니스용 Skype Web App을 사용하여 모임에 계속 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="51813-164">간소화된 모임 참가 및 Skype 모임 앱 사용</span><span class="sxs-lookup"><span data-stu-id="51813-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="51813-165">CDN(콘텐츠 배달 네트워크)에 대한 액세스를 사용하도록 설정하면 사용자는 CDN에 온라인으로 연결하고 Skype 모임 앱(Windows에서) 및 Mac용 비즈니스용 Skype(Mac)를 다운로드할 수 있으며 간소화된 모임 참가 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="51813-166">모임 참가 웹 페이지 또는 Skype 모임 앱의 클라이언트 쪽 로깅 원격 분석이 Microsoft 서버로 전송될 수 있도록 허용합니다(기본적으로 false로 설정).</span><span class="sxs-lookup"><span data-stu-id="51813-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="51813-167">Microsoft로 전송되는 정보는 비즈니스용 Skype 데이터 수집 규정을 [엄격하게 준수합니다.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)</span><span class="sxs-lookup"><span data-stu-id="51813-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="51813-168">CDN을 사용할 수 없는 경우 로컬로 호스팅되는 비즈니스용 Skype Web App 환경으로 돌아가기 전에 시간 제한을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="51813-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="51813-169">기본값은 6초입니다.</span><span class="sxs-lookup"><span data-stu-id="51813-169">The default value is 6 seconds.</span></span> <span data-ttu-id="51813-170">이 값을 0으로 설정하면 시간 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="51813-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="51813-171">비즈니스용 Skype 서버 2015 누적 업데이트 5에서 MeetingUxUseCdn을 사용할 경우 기본값은 False로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="51813-172">이로 인해 비즈니스용 Skype 관리자가 MeetingUxUseCdn을 True로 설정한 경우에도 Mac용 비즈니스용 Skype 클라이언트가 비 페더러이트 파트너의 모임에 게스트로 참가할 수 없는 문제가 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51813-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="51813-173">이렇게 하기 위해 비즈니스용 Skype 서버 2015에는 누적 업데이트 7, 6.0.9319.534 이상이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51813-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="51813-174">비즈니스용 Skype 서버 [2015에서](https://support.microsoft.com/kb/4132312)비즈니스용 Skype Web App을 바꾸기 위해 Skype 모임 앱 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51813-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="51813-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51813-175">See also</span></span>
<span data-ttu-id="51813-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="51813-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="51813-177">모임 클라이언트 계획(Web App 및 모임 앱)</span><span class="sxs-lookup"><span data-stu-id="51813-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="51813-178">비즈니스용 Skype 서버에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="51813-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="51813-179">Microsoft Online Services 개인 정보 취급 방침</span><span class="sxs-lookup"><span data-stu-id="51813-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="51813-180">사용 조건 및 설명서</span><span class="sxs-lookup"><span data-stu-id="51813-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
