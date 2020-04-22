---
title: 'Lync Server 2013: Lync Online 사용자를 Lync 온-프레미스로 마이그레이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e87b977dd70227d134e5feae8df2ea089e216df3
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="99aea-102">Lync Server 2013에서 lync Online 사용자를 lync 온-프레미스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="99aea-102">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99aea-103">_**마지막으로 수정 된 항목:** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="99aea-103">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="99aea-104">이러한 단계는 lync 온-프레미스를 배포 하기 전에 lync Online에서 원래 Lync를 사용 하도록 설정 된 사용자 계정을 마이그레이션하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-104">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="99aea-105">원래 Lync 온-프레미스를 사용 하도록 설정 된 사용자를 이동 하 고 나중에 Lync Online으로 이동 하 <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">는 경우 하이브리드 Lync Server 2013 배포에서 사용자 관리</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99aea-105">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="99aea-106">또한 이동 중인 모든 사용자에 게 온-프레미스 Active Directory에 계정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-106">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="99aea-107">처음에 Lync Online에서 사용 하도록 설정 된 사용자 계정을 Lync 온-프레미스로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="99aea-107">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="99aea-108">먼저 조직이 하이브리드 용으로 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-108">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="99aea-109">Azure Active Directory 동기화 도구를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-109">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="99aea-110">자세한 내용은 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99aea-110">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="99aea-111">사용자가 Lync Online에 single sign-on을 사용 하도록 설정 하려면 Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-111">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="99aea-112">온-프레미스 배포의 Lync Server 관리 셸에서 다음 cmdlet을 입력 하 여 Lync Online에 대 한 호스팅 공급자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-112">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="99aea-113">온-프레미스에 지 서버에 다음 표에 나와 있는 것 처럼 Lync Online에 대 한 연결을 설정할 수 있는 인증서 체인이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-113">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="99aea-114">여기에서이 체인을 다운로드할 수 있습니다.https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="99aea-114">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="99aea-115">인증서</span><span class="sxs-lookup"><span data-stu-id="99aea-115">Certificate</span></span></th>
    <th><span data-ttu-id="99aea-116">인증서 저장소</span><span class="sxs-lookup"><span data-stu-id="99aea-116">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="99aea-117">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="99aea-117">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="99aea-118">신뢰할 수 있는 루트 CA</span><span class="sxs-lookup"><span data-stu-id="99aea-118">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="99aea-119">Microsoft 인터넷 기관 (새 CA 인증서)</span><span class="sxs-lookup"><span data-stu-id="99aea-119">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="99aea-120">중개 CA</span><span class="sxs-lookup"><span data-stu-id="99aea-120">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="99aea-121">MSIT Machine Auth CA2 (새 발급 CA2)</span><span class="sxs-lookup"><span data-stu-id="99aea-121">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="99aea-122">중개 CA</span><span class="sxs-lookup"><span data-stu-id="99aea-122">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="99aea-123">온-프레미스 Active Directory에서 Lync 온-프레미스에 대해 영향을 받는 사용자 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-123">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="99aea-124">개별 사용자에 대해 다음 cmdlet을 입력 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-124">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="99aea-125">또는 파일에서 사용자 이름을 읽고이를 CsUser cmdlet에 대 한 입력으로 제공 하는 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-125">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="99aea-126">DirSync를 실행 하 여 Lync Online 사용자를 업데이트 된 Lync 온-프레미스 사용자와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-126">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="99aea-127">모든 SIP 트래픽을 Lync 온-프레미스로 보내도록 일부 DNS 레코드를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-127">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="99aea-128">온-프레미스 역방향 프록시 서버의 FQDN을 가리키도록 **Lyncdiscover.contoso.com** A 레코드를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-128">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="99aea-129">\* Sip *를 업데이트 합니다\*\*\_.\_ tls.contoso.com*\* SRV 레코드를 사용 하 여 Lync 온-프레미스의 액세스에 지 서비스에 대 한 공용 IP 또는 VIP 주소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-129">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="99aea-130">\* Sipfederationtls *를 업데이트 합니다\*\*\_.\_ tcp.contoso.com*\* SRV 레코드를 사용 하 여 Lync 온-프레미스의 액세스에 지 서비스에 대 한 공용 IP 또는 VIP 주소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-130">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="99aea-131">조직에서 분할 DNS를 사용 하는 경우 (예를 들어, "분할 하는 DNS" 라고도 함) 내부 DNS 영역을 통해 이름을 확인 하는 사용자가 프런트 엔드 풀로 이동 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-131">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="99aea-132">`Get-CsUser` Cmdlet을 입력 하 여 이동할 사용자에 대 한 일부 속성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-132">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="99aea-133">HostingProviderProxyFQDN가로 `"sipfed.online.lync.com"` 설정 되어 있고 SIP 주소가 올바르게 설정 되어 있는지 확인 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="99aea-133">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="99aea-134">Lync Online 사용자를 Lync 온-프레미스로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-134">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="99aea-135">단일 사용자를 이동 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-135">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="99aea-136">- **CsUSer** cmdlet을 – Filter 매개 변수를 사용 하 여 여러 사용자를 이동 하 고 특정 속성을 가진 사용자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-136">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="99aea-137">예를 들어 {호스팅 공급자 – eq "sipfed.online.lync.om"}에 대해 필터링을 통해 모든 Lync Online 사용자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-137">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="99aea-138">그런 다음 아래에 표시 된 것 처럼, 다음에 나오는 것 처럼, 사용자는 다음에 나오는 것 처럼 **이동** 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-138">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="99aea-139">**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 Url 형식은 호스트 되는 마이그레이션 서비스가 실행 되는 풀의 url 이어야 하며, *Https://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc*형식으로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-139">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="99aea-140">Office 365 조직 계정에 대 한 Lync Online 제어판의 URL을 확인 하 여 호스팅된 마이그레이션 서비스에 대 한 URL을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-140">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-organization"></a><span data-ttu-id="99aea-141">Office 365 조 직에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="99aea-141">To determine the Hosted Migration Service URL for your Office 365 organization</span></span>
    
    1.  <span data-ttu-id="99aea-142">관리자로 Office 365 조직에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-142">Login to your Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="99aea-143">**Lync 관리 센터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-143">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="99aea-144">**Lync 관리 센터** 를 표시 하 고 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-144">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="99aea-145">URL의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-145">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="99aea-146">URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-146">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="99aea-147">URL에 다음 문자열을 추가 합니다: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="99aea-147">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="99aea-148">**HostedMigrationOverrideUrl**값을 나타내는 결과 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-148">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="99aea-149">Rtcxds 데이터베이스에 대 한 트랜잭션 로그 파일의 기본 최대 크기는 16gb입니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-149">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="99aea-150">많은 수의 사용자를 한 번에 이동 하는 경우, 특히 미러링을 사용 하도록 설정한 경우에는이 값이 충분히 크지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-150">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="99aea-151">이 문제를 해결 하려면 파일 크기를 늘리거나 로그 파일을 정기적으로 백업 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-151">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="99aea-152">자세한 내용은를 참조 <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>하세요.</span><span class="sxs-lookup"><span data-stu-id="99aea-152">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="99aea-153">이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-153">This is an optional step.</span></span> <span data-ttu-id="99aea-154">Exchange 2013 Online과 통합 해야 하는 경우에는 추가 호스팅 공급자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-154">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="99aea-155">자세한 내용은 [Exchange Online과 온-프레미스 Lync Server 2013 통합 구성을](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="99aea-155">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="99aea-156">이제 사용자가 이동 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-156">The users are now moved.</span></span> <span data-ttu-id="99aea-157">사용자에 게 다음 표에 표시 된 특성 값이 올바른지 확인 하려면 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-157">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="99aea-158">Active Directory 특성</span><span class="sxs-lookup"><span data-stu-id="99aea-158">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="99aea-159">특성 이름</span><span class="sxs-lookup"><span data-stu-id="99aea-159">Attribute name</span></span></th>
    <th><span data-ttu-id="99aea-160">Lync Online 사용자에 대 한 올바른 값</span><span class="sxs-lookup"><span data-stu-id="99aea-160">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="99aea-161">Lync 온-프레미스 사용자에 대 한 올바른 값</span><span class="sxs-lookup"><span data-stu-id="99aea-161">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="99aea-162">Msrtcsip-gateways-DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="99aea-162">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="99aea-163">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="99aea-163">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="99aea-164">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="99aea-164">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="99aea-165">SRV</span><span class="sxs-lookup"><span data-stu-id="99aea-165">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="99aea-166">Msrtcsip-gateways-Msrtcsip-primaryuseraddress</span><span class="sxs-lookup"><span data-stu-id="99aea-166">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="99aea-167">Nm-server-w15-short</span><span class="sxs-lookup"><span data-stu-id="99aea-167">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="99aea-168">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="99aea-168">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="99aea-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="99aea-169">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="99aea-170">Msrtcsip-gateways-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="99aea-170">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="99aea-171">사용</span><span class="sxs-lookup"><span data-stu-id="99aea-171">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="99aea-172">참</span><span class="sxs-lookup"><span data-stu-id="99aea-172">True</span></span></p></td>
    <td><p><span data-ttu-id="99aea-173">참</span><span class="sxs-lookup"><span data-stu-id="99aea-173">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="99aea-174">이동 된 각 사용자는 Lync에서 로그 아웃 한 다음 다시 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-174">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="99aea-175">로그인 할 때 연락처 목록을 확인 하 고 필요한 경우 연락처를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-175">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="99aea-176">예약 된 모임은 Lync Online에서 Lync 온-프레미스로 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-176">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="99aea-177">사용자는 이러한 모임을 이동한 후에 다시 예약 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-177">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="99aea-178">DNS 레코드가 업데이트 되 고 모든 사용자가 온-프레미스로 연결 되 면 HostingProvider 특성은 Lync 사용자에 게 SRV 레코드를 사용 하거나 온라인 공급자 "sipfed.online.lync.com"로 보내는 것으로 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="99aea-178">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

