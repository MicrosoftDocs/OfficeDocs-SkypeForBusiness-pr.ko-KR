---
title: 'Lync Server 2013: Lync Windows 스토어 앱 배포'
description: 'Lync Server 2013: Lync Windows 스토어 앱을 배포 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9260d656079fb694a14aadf5049ca36241830c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571714"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="7a964-103">Lync Server 2013에서 Lync Windows 스토어 앱 배포</span><span class="sxs-lookup"><span data-stu-id="7a964-103">Deploying Lync Windows Store app in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a964-104">_**마지막으로 수정 된 항목:** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="7a964-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="7a964-105">사용자가 Lync Windows 스토어 앱을 사용할 수 있도록 하려면 배포가 [Lync Server 2013의 Lync Windows 스토어 앱 요구 사항을](lync-server-2013-lync-windows-store-app-requirements.md)충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-105">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="7a964-106">Lync Server 2013을 지원 하기 위해 다음 홉 블로그 문서를 구성 하는 방법에 대 한 자세한 내용은의 "Lync Server 자동 검색 및 Lync Windows 스토어 앱"을 참조 하십시오 [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) .</span><span class="sxs-lookup"><span data-stu-id="7a964-106">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="7a964-107">서버 환경을 올바르게 구성한 후에는 "Lync"를 검색 하 여 사용자가 Windows 스토어에서 Lync 앱을 다운로드 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-107">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="7a964-108">Lync Windows 스토어 앱에 대해 다단계 인증을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="7a964-108">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="7a964-109">Lync Server 2013 용 누적 업데이트: 6 월 2013은 Lync Windows 스토어 앱 클라이언트에 대 한 다단계 인증 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-109">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="7a964-110">사용자 이름 및 암호 외에도 추가 인증 방법 (예: 스마트 카드나 Pin)을 사용 하 여 Lync 모임에 로그인 할 때 외부 사용자를 인증 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-110">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="7a964-111">다단계 인증을 사용 하도록 설정 하려면 Lync Server 2013에서 AD FS (Active Directory Federation Service) 페더레이션 서버를 배포 하 고 수동 인증을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-111">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="7a964-112">AD FS가 구성 되 면 Lync 모임을 연결 하려고 시도 하는 외부 사용자에 게 구성한 추가 인증 방법과 함께 사용자 이름 및 암호 챌린지를 포함 하는 AD FS 다단계 인증 웹 페이지가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-112">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="7a964-113">Lync Windows 스토어 앱에 대 한 다단계 인증을 사용 하도록 AD FS를 구성 하려는 경우에는 다음과 같은 중요 한 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-113">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="7a964-114">Lync server 2013에 대 한 누적 업데이트는 최소 2013 6 월 2013 일 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-114">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="7a964-115">Lync 2013 데스크톱 클라이언트는 lync Server 2013 2013에 대 한 누적 업데이트가 필요 하지 않으므로 Lync 2013 클라이언트가 인증을 수행할 수 있기 때문에 수동 인증이 작동 하는 것 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-115">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="7a964-116">그러나 Lync Windows 스토어 앱 클라이언트에 대 한 인증 프로세스가 완료 되지 않으며 알림 또는 오류 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-116">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="7a964-117">수동 인증이 제공 되는 유일한 인증 유형이 되도록 서버를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-117">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="7a964-118">하드웨어 부하 분산 장치를 사용 하는 경우에는 Lync Windows 스토어 앱 클라이언트의 모든 요청이 동일한 프런트 엔드 서버에서 처리 되도록 부하 분산 장치에서 쿠키 지 속성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-118">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="7a964-119">Lync Server와 AD FS 서버 간에 신뢰 당사자 트러스트를 설정 하는 경우 Lync 모임의 최대 길이를 확장 하는 데 충분 한 길이의 토큰 수명을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-119">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="7a964-120">일반적으로 240 분의 토큰 수명은 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-120">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="7a964-121">**다단계 인증을 구성 하려면**</span><span class="sxs-lookup"><span data-stu-id="7a964-121">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="7a964-122">AD FS 페더레이션 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-122">Install an AD FS federation server role.</span></span> <span data-ttu-id="7a964-123">자세한 내용은에서 Active Directory Federation Services 2.0 배포 가이드를 참조 하세요 <https://go.microsoft.com/fwlink/p/?linkid=267511> .</span><span class="sxs-lookup"><span data-stu-id="7a964-123">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <https://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="7a964-124">AD FS에 대 한 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-124">Create certificates for AD FS.</span></span> <span data-ttu-id="7a964-125">자세한 내용은의 ' 페더레이션 서버 인증서 ' 섹션에서 single sign-on 사용에 대 한 use AD FS를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) .</span><span class="sxs-lookup"><span data-stu-id="7a964-125">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="7a964-126">Windows PowerShell 명령줄 인터페이스에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-126">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="7a964-127">다음 명령을 실행 하 여 파트너 관계를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-127">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="7a964-128">다음과 같은 신뢰 당사자 규칙을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-128">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="7a964-129">로그인을 방해할 수 있는 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="7a964-129">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="7a964-130">Lync Windows 스토어 앱을 실행 하는 장치에 시간 및 날짜가 정확히 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="7a964-130">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="7a964-131">장치의 시간 설정은 서버의 시간 설정과 동기화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-131">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="7a964-132">이는 Microsoft Surface와 같은 장치 및 도메인에 가입 되지 않은 Windows RT를 실행 하는 기타 장치에 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-132">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="7a964-133">시간 서버에서 이러한 장치에 대 한 시간을 자동으로 설정 하려면 장치의 관리자 권한 명령 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-133">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="7a964-134">Lync Windows 스토어 앱이 Lync server 또는 서비스에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="7a964-134">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="7a964-135">Lync Windows 스토어 앱은 Windows 8을 실제 장치로 등록 하지 않은 네트워크 어댑터 (예: 4G LTE USB 모뎀)를 통해 Lync server 또는 서비스에 액세스 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-135">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="7a964-136">데스크톱 앱과 브라우저에서 다른 서버 및 웹 사이트에 액세스할 수 있는 경우에도 Lync Windows 스토어 앱이이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-136">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="7a964-137">Lync Windows 스토어 앱은 Lync Server 2010 및 Office Communications Server 2007 R2에 지 서버를 사용 하 여 로그인 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="7a964-137">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="7a964-138">토폴로지가 Office Communications Server 2007 R2에 지 서버를 사용 하 여 Lync Server 2010로 구성 된 경우 Lync Server 용 누적 업데이트 2010:7 월 2013에 제공 되는 업데이트 된 버전의 토폴로지 작성기를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-138">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="7a964-139">이전 버전의 토폴로지 작성기에서는 Office Communications Server 2007에 지 서버에 필요한 매핑을 만들지 않으므로 Lync Windows 스토어 앱 클라이언트에서 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-139">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="7a964-140">다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-140">The following steps are required:</span></span>

1.  <span data-ttu-id="7a964-141">Lync server 2010에 대 한 누적 업데이트를 설치 합니다 2010 2010 2013. |</span><span class="sxs-lookup"><span data-stu-id="7a964-141">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="7a964-142">다음을 수행 하 여 Lync 자동 검색 구성을 업데이트 하 여 외부 SIP 진입점이에 지 서버 주소 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-142">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="7a964-143">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-143">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="7a964-144">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-144">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="7a964-145">인증서 이름 유효성 검사 오류로 인해 Lync Windows 스토어 앱에서 로그인 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="7a964-145">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="7a964-146">Microsoft 365 또는 Office 365 사용자가 최신 버전의 Lync Windows 스토어 앱을 실행 하지 않는 경우 로그인 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-146">A sign-in issue can occur for Microsoft 365 or Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="7a964-147">이 문제는 일반적으로 여러 도메인을 사용 하는 경우 발생 합니다 (예: SIP URI가 **userA@domainZ.com** 이지만에 지 서버는 **sip.domainX.com**).</span><span class="sxs-lookup"><span data-stu-id="7a964-147">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="7a964-148">이 문제를 해결 하기 위해 사용자는 Windows 8.1이 필요한 최신 버전의 Lync Windows 스토어 앱을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-148">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="7a964-149">Lync Windows 스토어 앱 로그를 사용 하 여 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7a964-149">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="7a964-150">장치에서 생성 된 로그를 사용 하 여 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-150">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="7a964-151">로그는 다음 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-151">The logs are stored in the following folder:</span></span>

<span data-ttu-id="7a964-152">% LocalAppData% \\ 패키지 \\ Microsoft. LyncMX \_ 8wekyb3d8bbwe \\ localstate \\ Tracing</span><span class="sxs-lookup"><span data-stu-id="7a964-152">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="7a964-153">사용자 로부터 로그를 가져오기 전에 로깅이 설정 되어 있는지 확인 하 고, 메모리에 저장 된 모든 정보가 하드 드라이브의 파일에도 저장 되도록 로그를 저장 하도록 사용자에 게 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-153">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="7a964-154">**로깅을 설정 하려면**</span><span class="sxs-lookup"><span data-stu-id="7a964-154">**To turn on logging**</span></span>

1.  <span data-ttu-id="7a964-155">장치에서 Lync Windows 스토어 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-155">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="7a964-156">화면 오른쪽에서 살짝 밀기</span><span class="sxs-lookup"><span data-stu-id="7a964-156">Swipe from the right side of the screen.</span></span> <span data-ttu-id="7a964-157">마우스를 사용 하는 경우 화면의 오른쪽 위 모서리를 가리킨 다음 마우스 포인터를 화면 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-157">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="7a964-158">**설정을**선택 하 고 **옵션**을 선택한 다음 **진단 로그** 를 **On**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-158">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="7a964-159">이전에 **진단 로그가** 해제 된 경우 Lync를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-159">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="7a964-160">Lync를 다시 시작 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-160">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="7a964-161">장치를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-161">Restart the device.</span></span>
    
      - <span data-ttu-id="7a964-162">Lync 작업을 종료 하 고 앱을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-162">End the Lync task and launch the app again.</span></span> <span data-ttu-id="7a964-163">작업을 종료 하려면 Windows 작업 관리자를 열고 **Lync**를 선택한 다음 **작업 끝내기**를 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-163">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="7a964-164">Lync가 나열 되지 않으면 **세부 정보** 를 탭 하 고 **백그라운드 프로세스**에서 Lync를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-164">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="7a964-165">**로그를 저장 하려면**</span><span class="sxs-lookup"><span data-stu-id="7a964-165">**To save the logs**</span></span>

1.  <span data-ttu-id="7a964-166">장치에서 Lync Windows 스토어 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-166">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="7a964-167">로그인을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-167">Try signing in.</span></span>

3.  <span data-ttu-id="7a964-168">화면 오른쪽에서 살짝 밀기</span><span class="sxs-lookup"><span data-stu-id="7a964-168">Swipe from the right side of the screen.</span></span> <span data-ttu-id="7a964-169">마우스를 사용 하는 경우 화면의 오른쪽 위 모서리를 가리킨 다음 마우스 포인터를 화면 아래로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-169">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="7a964-170">**설정을**선택 하 고 **정보**를 선택한 다음 **로그 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a964-170">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

