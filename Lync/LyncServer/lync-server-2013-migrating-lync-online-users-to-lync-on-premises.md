---
title: 'Lync Server 2013: Lync Online 사용자를 Lync 온-프레미스로 마이그레이션'
description: 'Lync Server 2013: lync Online 사용자를 Lync 온-프레미스로 마이그레이션'
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
ms.openlocfilehash: 620bc07def8e3c1f6b761c6398b452b4dbcd3b04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561004"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Lync Server 2013에서 lync Online 사용자를 lync 온-프레미스로 마이그레이션

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> 이러한 단계는 lync 온-프레미스를 배포 하기 전에 lync Online에서 원래 Lync를 사용 하도록 설정 된 사용자 계정을 마이그레이션하는 경우에만 필요 합니다. 원래 Lync 온-프레미스를 사용 하도록 설정 된 사용자를 이동 하 고 나중에 Lync Online으로 이동 하 <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">는 경우 하이브리드 Lync Server 2013 배포에서 사용자 관리</A>를 참조 하세요.<BR>또한 이동 중인 모든 사용자에 게 온-프레미스 Active Directory에 계정이 있어야 합니다.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>처음에 Lync Online에서 사용 하도록 설정 된 사용자 계정을 Lync 온-프레미스로 마이그레이션

1.  먼저 조직이 하이브리드 용으로 구성 되어 있는지 확인 합니다.
    
      - Azure Active Directory 동기화 도구를 설치 합니다. 자세한 내용은 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>을 참조하세요.
    
      - 사용자가 Lync Online에 single sign-on을 사용 하도록 설정 하려면 Active Directory Federation Services를 설치 <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> 합니다.
    
      - 온-프레미스 배포의 Lync Server 관리 셸에서 다음 cmdlet을 입력 하 여 Lync Online에 대 한 호스팅 공급자를 만듭니다.
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  온-프레미스에 지 서버에 다음 표에 나와 있는 것 처럼 Lync Online에 대 한 연결을 설정할 수 있는 인증서 체인이 있는지 확인 합니다. 여기에서이 체인을 다운로드할 수 있습니다. https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>인증서</th>
    <th>인증서 저장소</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>신뢰할 수 있는 루트 CA</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft 인터넷 기관 (새 CA 인증서)</p></td>
    <td><p>중개 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (새 발급 CA2)</p></td>
    <td><p>중개 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  온-프레미스 Active Directory에서 Lync 온-프레미스에 대해 영향을 받는 사용자 계정을 사용 하도록 설정 합니다. 개별 사용자에 대해 다음 cmdlet을 입력 하 여이 작업을 수행할 수 있습니다.
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    또는 파일에서 사용자 이름을 읽고이를 Enable-CsUser cmdlet에 대 한 입력으로 제공 하는 스크립트를 만들 수 있습니다.
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  DirSync를 실행 하 여 Lync Online 사용자를 업데이트 된 Lync 온-프레미스 사용자와 동기화 합니다.

5.  모든 SIP 트래픽을 Lync 온-프레미스로 보내도록 일부 DNS 레코드를 업데이트 합니다.
    
      - 온-프레미스 역방향 프록시 서버의 FQDN을 가리키도록 **Lyncdiscover.contoso.com** A 레코드를 업데이트 합니다.
    
      - * Sip *를 업데이트 합니다** \_ . \_ tls.contoso.com** SRV 레코드를 사용 하 여 Lync 온-프레미스의 액세스에 지 서비스에 대 한 공용 IP 또는 VIP 주소를 확인할 수 있습니다.
    
      - * Sipfederationtls *를 업데이트 합니다** \_ . \_ tcp.contoso.com** SRV 레코드를 사용 하 여 Lync 온-프레미스의 액세스에 지 서비스에 대 한 공용 IP 또는 VIP 주소를 확인할 수 있습니다.
    
      - 조직에서 분할 DNS를 사용 하는 경우 (예를 들어, "분할 하는 DNS" 라고도 함) 내부 DNS 영역을 통해 이름을 확인 하는 사용자가 프런트 엔드 풀로 이동 했는지 확인 합니다.

6.  Cmdlet을 입력 `Get-CsUser` 하 여 이동할 사용자에 대 한 일부 속성을 확인 합니다. HostingProviderProxyFQDN가로 설정 되어 `"sipfed.online.lync.com"` 있고 SIP 주소가 올바르게 설정 되어 있는지 확인 하려는 경우

7.  Lync Online 사용자를 Lync 온-프레미스로 이동 합니다.
    
    단일 사용자를 이동 하려면 다음을 입력 합니다.
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    - **CsUSer** cmdlet을 – Filter 매개 변수를 사용 하 여 여러 사용자를 이동 하 고 특정 속성을 가진 사용자를 선택할 수 있습니다. 예를 들어 {호스팅 공급자 – eq "sipfed.online.lync.om"}에 대해 필터링을 통해 모든 Lync Online 사용자를 선택할 수 있습니다. 그런 다음 아래에 표시 된 것 처럼, 다음에 나오는 것 처럼, 사용자는 다음에 나오는 것 처럼 **이동** 합니다.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    **HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 Url 형식은 호스트 되는 마이그레이션 서비스가 실행 되는 풀의 url 이어야 하며,이 형식은 *Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*입니다.
    
    Microsoft 365 또는 Office 365 조직 계정에 대 한 Lync Online 제어판의 URL을 확인 하 여 호스팅된 마이그레이션 서비스에 대 한 URL을 확인할 수 있습니다.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a>Organizaton의 호스팅된 마이그레이션 서비스 URL을 확인 하려면
    
    1.  Microsoft 365 또는 Office 365 조직에 관리자로 로그인 합니다.
    
    2.  **Lync 관리 센터**를 엽니다.
    
    3.  **Lync 관리 센터** 를 표시 하 고 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다. URL의 예는 다음과 같습니다.
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.
        
        `https://admin0a.online.lync.com`
    
    5.  URL에 다음 문자열을 추가 합니다: **/HostedMigration/hostedmigrationservice.svc**.
        
        **HostedMigrationOverrideUrl**값을 나타내는 결과 URL은 다음과 같습니다.
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Rtcxds 데이터베이스에 대 한 트랜잭션 로그 파일의 기본 최대 크기는 16gb입니다. 많은 수의 사용자를 한 번에 이동 하는 경우, 특히 미러링을 사용 하도록 설정한 경우에는이 값이 충분히 크지 않을 수 있습니다. 이 문제를 해결 하려면 파일 크기를 늘리거나 로그 파일을 정기적으로 백업 하면 됩니다. 자세한 내용은를 참조 <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> 하세요.

    
    </div>

8.  이 단계는 선택 사항입니다. Exchange 2013 Online과 통합 해야 하는 경우에는 추가 호스팅 공급자를 사용 해야 합니다. 자세한 내용은 [Exchange Online과 온-프레미스 Lync Server 2013 통합 구성을](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)참조 하십시오.

9.  이제 사용자가 이동 되었습니다. 사용자에 게 다음 표에 표시 된 특성 값이 올바른지 확인 하려면 다음 cmdlet을 입력 합니다.
    
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
    <th>Active Directory 특성</th>
    <th>특성 이름</th>
    <th>Lync Online 사용자에 대 한 올바른 값</th>
    <th>Lync 온-프레미스 사용자에 대 한 올바른 값</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Msrtcsip-gateways-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>Msrtcsip-gateways-Msrtcsip-primaryuseraddress</p></td>
    <td><p>Nm-server-w15-short</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>Msrtcsip-gateways-UserEnabled</p></td>
    <td><p>사용</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 이동 된 각 사용자는 Lync에서 로그 아웃 한 다음 다시 로그인 해야 합니다. 로그인 할 때 연락처 목록을 확인 하 고 필요한 경우 연락처를 추가 해야 합니다.
    
    예약 된 모임은 Lync Online에서 Lync 온-프레미스로 마이그레이션되지 않습니다. 사용자는 이러한 모임을 이동한 후에 다시 예약 해야 합니다.
    
    DNS 레코드가 업데이트 되 고 모든 사용자가 온-프레미스로 연결 되 면 HostingProvider 특성은 Lync 사용자에 게 SRV 레코드를 사용 하거나 온라인 공급자 "sipfed.online.lync.com"로 보내는 것으로 지시 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

