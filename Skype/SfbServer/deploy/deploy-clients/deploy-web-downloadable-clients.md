---
title: 비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '요약: 비즈니스용 skype에 비즈니스용 skype Web App 및 Skype 모임 앱을 배포 합니다.'
ms.openlocfilehash: eb939ddf394ff62b9173939622a8ef3f20faaca9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003528"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="49bdb-103">비즈니스용 Skype 서버에서 웹 다운로드 가능 클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="49bdb-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="49bdb-104">**요약:** 비즈니스용 skype 서버와 함께 사용 되는 비즈니스용 Skype 2015 웹 앱 및 Skype 모임 앱을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="49bdb-105">비즈니스용 skype Web App은 비즈니스용 skype Server를 실행 하는 서버에 설치 되어 있으며 기본적으로 비즈니스용 Skype 클라이언트가 없는 사용자에 게 모임 요청에 따라 배포 되는 IIS (인터넷 정보 서비스) 웹 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="49bdb-106">이러한 모임 사용자는 네트워크 외부에서 연결 하지 않는 것이 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="49bdb-107">사용자가 모임 URL을 클릭할 수 있지만 비즈니스용 Skype 클라이언트가 설치 되어 있지 않은 경우에는 최신 버전의 비즈니스용 Skype Web App, Skype 모임 앱 또는 Mac 용 비즈니스용 Skype를 사용 하 여 모임에 참가할 수 있는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="49bdb-108">비즈니스용 Skype Web App의 음성, 비디오 및 공유 기능을 사용 하려면 사용자 브라우저에서 플러그인으로 사용할 수 있는 Microsoft ActiveX 컨트롤이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="49bdb-109">ActiveX 컨트롤을 미리 설치 하거나 사용자가 비즈니스용 Skype Web App을 처음 사용 하거나 ActiveX 컨트롤이 필요한 기능에 처음으로 액세스할 때 발생 하는 메시지가 나타날 때 설치 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="49bdb-110">비즈니스용 Skype Server Edge 서버 배포에서는 비즈니스용 Skype Web App 클라이언트 액세스에 경계 네트워크의 HTTPS 리버스 프록시가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="49bdb-111">간단한 Url도 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-111">You must also publish simple URLs.</span></span> <span data-ttu-id="49bdb-112">자세한 내용은 [비즈니스용 Skype 서버에서 간단한 url에 대 한](../../plan-your-deployment/network-requirements/simple-urls.md) [리버스 프록시 서버](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) 및 DNS 요구 사항 설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bdb-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="49bdb-113">비즈니스용 Skype Web App에 대해 다단계 인증을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="49bdb-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="49bdb-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="49bdb-114"></span></span>

<span data-ttu-id="49bdb-115">비즈니스용 skype Web App, Skype 모임 앱, Mac 용 비즈니스용 Skype for multi-factor authentication이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="49bdb-116">사용자 이름 및 암호 외에도 스마트 카드나 Pin 등의 추가 인증 방법을 요구 하 여 비즈니스용 Skype 모임에 로그인 할 때 외부 네트워크에서 참가 하는 사용자를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="49bdb-117">비즈니스용 Skype 서버에서 AD FS (Active Directory Federation Service) 페더레이션 서버를 배포 하 고 수동 인증을 사용 하도록 설정 하 여 multi-factor authentication을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="49bdb-118">ADFS가 구성 된 후 비즈니스용 Skype 모임에 참가 하려고 하는 외부 사용자는 사용자 이름 및 암호 챌린지를 포함 하는 AD FS 다단계 인증 웹 페이지를 통해 제공 되며, 여기에 나와 있는 추가 인증 방법을 사용할 수 있습니다. 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49bdb-119">다단계 인증을 위해 ADFS를 구성 하려는 경우 다음과 같은 중요 한 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="49bdb-120">다단계 ADFS 인증은 모임 참가자와 이끌이만 둘 다 같은 조직에 있거나 AD FS 페더레이션된 조직에 있는 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="49bdb-121">Lync server 웹 인프라가 현재 지원 하지 않기 때문에, Lync 페더레이션 사용자에 게는 multi-factor ADFS 인증이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="49bdb-122">하드웨어 부하 분산 장치를 사용 하는 경우 비즈니스용 Skype Web App 또는 모임 앱 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리 되도록 부하 분산 장치에서 쿠키 유지 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="49bdb-123">비즈니스용 Skype 서버와 AD FS 서버 간에 신뢰 당사자 신뢰를 설정 하는 경우 비즈니스용 Skype 모임의 최대 길이를 수용할 수 있는 긴 토큰 수명을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="49bdb-124">일반적으로 240 분의 토큰 수명은 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="49bdb-125">이 구성은 Lync 모바일 클라이언트에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="49bdb-126">다단계 인증 구성</span><span class="sxs-lookup"><span data-stu-id="49bdb-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="49bdb-127">AD FS 페더레이션 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="49bdb-128">자세한 내용은 [Active Directory Federation Services 2.0 배포 가이드](https://go.microsoft.com/fwlink/p/?linkid=267511) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bdb-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="49bdb-129">Adfs에 대 한 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-129">Create certificates for AD FS.</span></span> <span data-ttu-id="49bdb-130">자세한 내용은 single sign-on 항목을 사용 하 여 AD FS 계획 및 배포의 ["페더레이션 서버 인증서"](https://go.microsoft.com/fwlink/p/?LinkId=285376) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bdb-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="49bdb-131">Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="49bdb-132">다음 명령을 실행 하 여 파트너 관계를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="49bdb-133">다음 신뢰 당사자 규칙을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="49bdb-134">BranchCache 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="49bdb-134">Disable BranchCache</span></span>
<span data-ttu-id="49bdb-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="49bdb-135"></span></span>

<span data-ttu-id="49bdb-136">Windows 7 및 Windows Server 2008 R2의 BranchCache 기능은 비즈니스용 Skype Web App 웹 구성 요소를 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="49bdb-137">비즈니스용 Skype Web App 사용자에 대 한 문제를 방지 하려면 BranchCache를 사용 하도록 설정 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="49bdb-138">BranchCache를 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [Branchcache 배포 가이드](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bdb-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="49bdb-139">비즈니스용 Skype Web App 배포 확인</span><span class="sxs-lookup"><span data-stu-id="49bdb-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="49bdb-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="49bdb-140"></span></span>

<span data-ttu-id="49bdb-141">CsUcwaConference cmdlet을 사용 하 여 테스트 사용자 쌍이 통합 커뮤니케이션 웹 API를 사용 하 여 회의에 참가할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="49bdb-142">이 cmdlet에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서의 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bdb-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="49bdb-143">Windows Server 2008 R2에서 플러그 인 설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="49bdb-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="49bdb-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="49bdb-144"></span></span>

<span data-ttu-id="49bdb-145">Windows Server 2008 R2를 실행 하는 컴퓨터에서 플러그 인 설치가 실패 하는 경우 Internet Explorer 보안 설정 또는 DisableMSI 레지스트리 키 설정을 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="49bdb-146">Internet Explorer의 보안 설정 수정</span><span class="sxs-lookup"><span data-stu-id="49bdb-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="49bdb-147">Internet Explorer를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="49bdb-148">**도구**를 클릭 하 고 **인터넷 옵션**을 클릭 한 다음 **고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="49bdb-149">아래로 스크롤하여 **보안** 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="49bdb-150">**암호화 된 페이지를 디스크에 저장 안 함**을 선택 취소 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="49bdb-151">이 설정을 선택 하는 경우 비즈니스용 Skype Web App에서 첨부 파일을 다운로드 하려고 할 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="49bdb-152">모임에 다시 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-152">Rejoin the meeting.</span></span> <span data-ttu-id="49bdb-153">플러그 인을 오류 없이 다운로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="49bdb-154">DisableMSI 레지스트리 설정 수정</span><span class="sxs-lookup"><span data-stu-id="49bdb-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="49bdb-155">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="49bdb-156">레지스트리 편집기에 액세스 하려면 **regedit**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="49bdb-157">HKEY_LOCAL_MACHINE \Software\Policies\Microsoft\Windows\Installer. 이동</span><span class="sxs-lookup"><span data-stu-id="49bdb-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="49bdb-158">REG_DWORD 형식의 DisableMSI 레지스트리 키를 편집 하거나 추가 하 고이를 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="49bdb-159">모임에 다시 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="49bdb-160">Skype 모임 앱을 사용 하 여 비즈니스용 Skype Web App 바꾸기 (선택 사항, 비즈니스용 Skype Server 2015에만 해당)</span><span class="sxs-lookup"><span data-stu-id="49bdb-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="49bdb-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="49bdb-161"></span></span>

<span data-ttu-id="49bdb-162">이 절차는 선택 사항이 며 비즈니스용 Skype 서버 2015 CU5 이상에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="49bdb-163">이 기능을 사용 하지 않으면 외부 사용자가 비즈니스용 Skype Web App을 사용 하 여 모임에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="49bdb-164">간단한 모임 참가 및 Skype 모임 앱 사용</span><span class="sxs-lookup"><span data-stu-id="49bdb-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="49bdb-165">CDN (콘텐츠 배달 네트워크)에 대 한 액세스를 사용 하도록 설정 하면 사용자가 CDN online에 연결 하 여 비즈니스용 skype 모임 앱 (Windows)과 mac 용 비즈니스용 Skype (Mac)를 사용할 수 있으며, 간단한 모임 참가 환경을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="49bdb-166">모임 참가 웹 페이지나 Skype 모임 앱에서 클라이언트 쪽 로깅 원격 분석을 Microsoft 서버로 보낼 수 있도록 허용 합니다 (기본값은 false입니다).</span><span class="sxs-lookup"><span data-stu-id="49bdb-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="49bdb-167">Microsoft로 전송 되는 정보는 [비즈니스용 Skype 데이터 수집 방법을](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)엄격히 준수 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="49bdb-168">CDN을 사용할 수 없는 경우 로컬에서 호스팅되는 비즈니스용 Skype Web App 환경으로 전환 하기 전에 제한 시간을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="49bdb-169">기본값은 6 초입니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-169">The default value is 6 seconds.</span></span> <span data-ttu-id="49bdb-170">이 값을 0으로 설정 하면 시간이 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="49bdb-171">비즈니스용 Skype Server 2015 누적 업데이트 5에서 MeetingUxUseCdn를 사용 하는 경우 기본값은 False로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="49bdb-172">이는 비즈니스용 skype 관리자가 MeetingUxUseCdn를 True로 설정한 경우에도 for Mac 클라이언트가 페더레이션 되지 않은 모임에 게스트로 참가할 수 없는 문제를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="49bdb-173">이 작업을 수행 하려면 비즈니스용 Skype 서버 2015에 누적 업데이트 7, 6.0.9319.534 또는 이후 버전을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bdb-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="49bdb-174">비즈니스용 skype [Server 2015에서 Skype 모임 앱이 비즈니스용 Skype Web app을 교체할 수 있도록 허용을](https://support.microsoft.com/kb/4132312)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bdb-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="49bdb-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49bdb-175">See also</span></span>
<span data-ttu-id="49bdb-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="49bdb-176"></span></span>

[<span data-ttu-id="49bdb-177">모임 클라이언트 계획 (웹 앱 및 모임 앱)</span><span class="sxs-lookup"><span data-stu-id="49bdb-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="49bdb-178">비즈니스용 Skype 서버에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="49bdb-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="49bdb-179">Microsoft Online Services 개인 정보 취급 방침</span><span class="sxs-lookup"><span data-stu-id="49bdb-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="49bdb-180">라이선스 약관 및 설명서</span><span class="sxs-lookup"><span data-stu-id="49bdb-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
