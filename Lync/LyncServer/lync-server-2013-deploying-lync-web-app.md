---
title: 'Lync Server 2013: Lync Web App 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c355be1c1709cede9c032d59790d6beefb337ff6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40976654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="2f8f2-102">Lync Server 2013에서 Lync Web App 배포</span><span class="sxs-lookup"><span data-stu-id="2f8f2-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f8f2-103">_**마지막으로 수정한 주제:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="2f8f2-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="2f8f2-104">Lync Web App은 Lync Server 2013와 함께 설치 되며 기본적으로 사용 하도록 설정 되는 IIS (인터넷 정보 서비스) 웹 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="2f8f2-105">서버에서 Lync Web App을 사용 하도록 설정 하거나 웹 클라이언트를 사용자에 게 배포 하는 데 추가 단계가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="2f8f2-106">사용자가 모임 URL을 클릭할 때 Lync 2013 클라이언트가 설치 되어 있지 않은 경우에는 사용자에 게 최신 버전의 Lync Web App을 사용 하 여 모임에 참가할 수 있는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="2f8f2-107">Lync Web App의 음성, 비디오 및 공유 기능을 위해서는 Microsoft ActiveX 컨트롤이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="2f8f2-108">ActiveX 컨트롤을 미리 설치 하거나 사용자가 Lync Web App을 처음 사용할 때 또는 ActiveX 컨트롤이 필요한 기능에 처음으로 액세스할 때 발생 하는 메시지가 나타날 때 설치 하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="2f8f2-109">Lync Server 2013 Edge 서버 배포에서 Lync Web App 클라이언트 액세스에 경계 네트워크의 HTTPS 리버스 프록시가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="2f8f2-110">간단한 Url도 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-110">You must also publish simple URLs.</span></span> <span data-ttu-id="2f8f2-111">자세한 내용은 lync <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">server 2013에 대 한 리버스 프록시 서버 설정</A> 및 <A href="lync-server-2013-planning-for-simple-urls.md">lync server 2013에서 간단한 url에 대 한 계획</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="2f8f2-112">Lync Web App에 대해 다단계 인증을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="2f8f2-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="2f8f2-113">Lync Server 2013 버전의 Lync Web App에서 다단계 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="2f8f2-114">사용자 이름 및 암호 외에도 스마트 카드나 Pin 등의 추가 인증 방법을 요구 하 여 Lync 모임에 로그인 할 때 외부 네트워크에서 참가 하는 사용자를 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="2f8f2-115">Lync Server 2013에서 AD FS (Active Directory Federation Service) 페더레이션 서버를 배포 하 고 수동 인증을 사용 하도록 설정 하 여 multi-factor authentication을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="2f8f2-116">AD FS가 구성 된 후 Lync 모임에 참가 하려고 하는 외부 사용자는 사용자 이름 및 암호 챌린지를 포함 하는 AD FS 다단계 인증 웹 페이지와 함께 구성 된 추가 인증 방법과 함께 제공 됩니다. .</span><span class="sxs-lookup"><span data-stu-id="2f8f2-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="2f8f2-117">다단계 인증을 위해 ADFS를 구성 하려는 경우 다음과 같은 중요 한 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2f8f2-118">다단계 ADFS 인증은 모임 참가자와 이끌이만 둘 다 같은 조직에 있거나 AD FS 페더레이션된 조직에 있는 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-118">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="2f8f2-119">Lync server 웹 인프라가 현재 지원 하지 않기 때문에, Lync 페더레이션 사용자에 게는 multi-factor ADFS 인증이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-119">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="2f8f2-120">하드웨어 부하 분산 장치를 사용 하는 경우에는 Lync Web App 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리 되도록 부하 분산 장치에서 쿠키를 지 속성 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="2f8f2-121">Lync Server와 AD FS 서버 간에 신뢰 당사자 신뢰를 설정 하는 경우 Lync 모임의 최대 길이를 수용할 수 있는 긴 토큰 수명을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="2f8f2-122">일반적으로 240 분의 토큰 수명은 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="2f8f2-123">이 구성은 Lync 모바일 클라이언트에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="2f8f2-124">**다단계 인증을 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="2f8f2-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="2f8f2-125">AD FS 페더레이션 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="2f8f2-126">자세한 내용은 다음의 Active Directory Federation Services 2.0 배포 가이드를 참조 하세요.<http://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="2f8f2-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="2f8f2-127">Adfs에 대 한 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-127">Create certificates for AD FS.</span></span> <span data-ttu-id="2f8f2-128">자세한 내용은의 single sign-on 항목을 사용 하 여 AD FS 계획 및 배포의 "페더레이션 서버 인증서" 섹션을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span><span class="sxs-lookup"><span data-stu-id="2f8f2-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="2f8f2-129">Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="2f8f2-130">다음 명령을 실행 하 여 파트너 관계를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-130">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="2f8f2-131">다음 신뢰 당사자 규칙을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-131">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="2f8f2-132">BranchCache 구성</span><span class="sxs-lookup"><span data-stu-id="2f8f2-132">BranchCache Configuration</span></span>

<span data-ttu-id="2f8f2-133">Windows 7 및 Windows Server 2008 R2의 BranchCache 기능은 Lync Web App 웹 구성 요소를 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="2f8f2-134">Lync Web App 사용자에 대 한 문제를 방지 하려면 BranchCache를 사용 하도록 설정 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="2f8f2-135">BranchCache를 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 Windows Server 2008 R2 기술 라이브러리의 Microsoft 다운로드 센터 [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) 에서 Word 형식으로 제공 되는 BranchCache 배포 가이드를 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span><span class="sxs-lookup"><span data-stu-id="2f8f2-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="2f8f2-136">Lync Web App 배포 확인</span><span class="sxs-lookup"><span data-stu-id="2f8f2-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="2f8f2-137">CsUcwaConference cmdlet을 사용 하 여 테스트 사용자 쌍이 통합 커뮤니케이션 웹 API를 사용 하 여 회의에 참가할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="2f8f2-138">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="2f8f2-139">Windows Server 2008 R2에서 플러그 인 설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2f8f2-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="2f8f2-140">Windows Server 2008 R2를 실행 하는 컴퓨터에서 플러그 인 설치가 실패 하는 경우 Internet Explorer 보안 설정 또는 DisableMSI 레지스트리 키 설정을 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="2f8f2-141">**Internet Explorer에서 보안 설정을 수정 하려면**</span><span class="sxs-lookup"><span data-stu-id="2f8f2-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="2f8f2-142">Internet Explorer를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="2f8f2-143">**도구**를 클릭 하 고 **인터넷 옵션**을 클릭 한 다음 **고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="2f8f2-144">아래로 스크롤하여 **보안** 섹션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="2f8f2-145">**암호화 된 페이지를 디스크에 저장 안 함**을 선택 취소 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="2f8f2-146">이 설정을 선택 하는 경우 Lync Web App에서 첨부 파일을 다운로드 하려고 할 때 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="2f8f2-147">모임에 다시 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-147">Rejoin the meeting.</span></span> <span data-ttu-id="2f8f2-148">플러그 인을 오류 없이 다운로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="2f8f2-149">**DisableMSI 레지스트리 설정을 수정 하려면**</span><span class="sxs-lookup"><span data-stu-id="2f8f2-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="2f8f2-150">**시작**을 클릭 한 다음 **실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="2f8f2-151">레지스트리 편집기에 액세스 하려면 **regedit**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="2f8f2-152">HKEY\_LOCAL\_MACHINE\\소프트웨어\\정책\\으로 이동 합니다\\Microsoft\\Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="2f8f2-153">REG\_DWORD 형식의 DisableMSI 레지스트리 키를 편집 하거나 추가 하 고 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="2f8f2-154">모임에 다시 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8f2-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f8f2-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f8f2-155">See Also</span></span>


[<span data-ttu-id="2f8f2-156">Lync Server 2013에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="2f8f2-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="2f8f2-157">Lync Server 2013 용으로 지원 되는 lync Web App 플랫폼</span><span class="sxs-lookup"><span data-stu-id="2f8f2-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

