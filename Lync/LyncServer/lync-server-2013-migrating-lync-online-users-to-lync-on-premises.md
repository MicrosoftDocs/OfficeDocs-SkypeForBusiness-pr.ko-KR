---
title: 'Lync Server 2013: lync Online 사용자를 Lync 온-프레미스로 마이그레이션'
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
ms.openlocfilehash: e76f8c0c40e13d0d9c6b19dee118e1513390d7e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Lync Server 2013에서 lync Online 사용자를 lync 온-프레미스로 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> 이 단계는 lync 온-프레미스를 배포 하기 전에 lync Online에서 원래 Lync를 사용 하도록 설정 된 사용자 계정을 마이그레이션하는 경우에만 필요 합니다. 온-프레미스에서 원래 Lync를 사용 하도록 설정 된 사용자를 이동 하 고 나중에 Lync Online으로 이동 하려면 <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">하이브리드 Lync Server 2013 배포에서 사용자 관리</A>를 참조 하세요.<BR>또한 이동 하려는 모든 사용자는 온-프레미스 Active Directory에 계정이 있어야 합니다.



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>원래 Lync Online에서 설정 된 사용자 계정을 Lync 온-프레미스로 마이그레이션

1.  먼저 조직이 하이브리드 용으로 구성 되어 있는지 확인 합니다.
    
      - Azure Active Directory 동기화 도구를 설치 합니다. 자세한 내용은을 참조 <http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>하세요.
    
      - 사용자가 Lync Online에 single sign-on을 사용할 수 있도록 하려면 Active Directory Federation Services <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>를 설치 합니다.
    
      - 온-프레미스 배포의 Lync Server 관리 셸에서 다음 cmdlet을 입력 하 여 Lync Online 용 호스팅 공급자를 만듭니다.
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  온-프레미스에 지 서버에 다음 표에 표시 된 대로 Lync Online에 연결할 수 있는 인증서 체인이 있는지 확인 합니다. 이 체인은 다음 위치에서 다운로드할 수 있습니다.https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>인증</th>
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
    <td><p>MSIT 기계 Auth CA2 (새 발급 CA2)</p></td>
    <td><p>중개 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  온-프레미스 Active Directory에서 Lync 온-프레미스에 영향을 받는 사용자 계정을 사용 하도록 설정 합니다. 다음 cmdlet을 입력 하 여 개별 사용자에 대해이 작업을 수행할 수 있습니다.
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    또는 파일에서 사용자 이름을 읽고이를 CsUser cmdlet에 대 한 입력으로 제공 하는 스크립트를 만들 수 있습니다.
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  DirSync를 실행 하 여 Lync Online 사용자를 업데이트 된 Lync 온-프레미스 사용자와 동기화 합니다.

5.  모든 SIP 트래픽을 Lync 온-프레미스로 보내도록 일부 DNS 레코드를 업데이트 합니다.
    
      - 온-프레미스 역방향 프록시 서버의 FQDN을 가리키도록 **Lyncdiscover.contoso.com** A 레코드를 업데이트 합니다.
    
      - ***\_Sip *를 업데이트 합니다\_ . **Lync 온-프레미스의 액세스 Edge 서비스에 대 한 공용 IP 또는 VIP 주소로 확인 하려면 Tls.contoso.com SRV 레코드를 선택 합니다.
    
      - ***\_Sipfederationtls *를 업데이트 합니다\_ . **Lync 온-프레미스의 액세스 Edge 서비스에 대 한 공용 IP 또는 VIP 주소로 확인 하려면 Tcp.contoso.com SRV 레코드를 선택 합니다.
    
      - 조직에서 분할 DNS ("분할-두뇌 DNS" 라고도 함)를 사용 하는 경우 내부 DNS 영역을 통해 이름을 확인 하는 사용자가 프런트 엔드 풀로 지정 되어 있는지 확인 합니다.

6.  Cmdlet을 `Get-CsUser` 입력 하 여 이동할 사용자에 대 한 일부 속성을 확인 합니다. HostingProviderProxyFQDN가로 `"sipfed.online.lync.com"` 설정 되어 있고 SIP 주소가 올바르게 설정 되어 있는지 확인 하려고 합니다.

7.  Lync Online 사용자를 Lync 온-프레미스로 이동 합니다.
    
    단일 사용자를 이동 하려면 다음을 입력 합니다.
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    - **CsUSer** cmdlet을 – Filter 매개 변수를 사용 하 여 여러 사용자를 이동 하면 특정 속성이 있는 사용자를 선택할 수 있습니다. 예를 들어 {호스팅 공급자 – eq "sipfed.online.lync.om"}에 대해 필터링 하 여 Lync Online 사용자를 모두 선택할 수 있습니다. 그런 다음 다음과 같이 **이동-CsUSer** cmdlet에 반환 된 사용자를 파이프 할 수 있습니다.
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    **HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 Url 형식은 호스팅된 마이그레이션 서비스가 실행 되는 풀의 url 이어야 하며, *Https://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc*형식으로 되어 있어야 합니다.
    
    Office 365 테 넌 트 계정에 대 한 Lync Online 제어판의 URL을 보고 호스팅된 마이그레이션 서비스의 URL을 확인할 수 있습니다.
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Office 365 테 넌 트에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면
    
    1.  관리자 권한으로 Office 365 테 넌 트에 로그인 합니다.
    
    2.  **Lync 관리 센터**를 엽니다.
    
    3.  **Lync 관리 센터** 를 표시 한 상태에서 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다. URL 예제는 다음과 같습니다.
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.
        
        `https://admin0a.online.lync.com`
    
    5.  URL에 다음 문자열을 추가 합니다. **/HostedMigration/hostedmigrationservice.svc**.
        
        **HostedMigrationOverrideUrl**의 값인 결과 URL은 다음과 같이 표시 됩니다.
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Rtcxds 데이터베이스의 트랜잭션 로그 파일의 기본 최대 크기는 16gb입니다. 특히 미러링 기능을 사용 하는 경우에는 많은 수의 사용자를 한 번에 이동 하는 경우에는이 작업이 충분히 크지 않을 수 있습니다. 이 문제를 해결 하기 위해 파일 크기를 늘리거나 로그 파일을 정기적으로 백업할 수 있습니다. 자세한 내용은을 참조 <A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>하세요.

    
    </div>

8.  이 단계는 선택 사항입니다. Exchange 2013 온라인과 통합 해야 하는 경우에는 추가 호스팅 공급자를 사용 해야 합니다. 자세한 내용은 [Exchange Online과 온-프레미스 Lync Server 2013 통합 구성을](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)참조 하세요.

9.  이제 사용자가 이동 되었습니다. 사용자에 게 다음 표에 표시 된 특성에 대 한 올바른 값이 있는지 확인 하려면 다음 cmdlet을 입력 합니다.
    
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
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>수</p></td>
    <td><p>False</p></td>
    <td><p>False</p></td>
    </tr>
    </tbody>
    </table>


10. 이동한 각 사용자는 Lync에서 로그 아웃 한 다음 다시 로그인 해야 합니다. 로그인 할 때 사용자의 연락처 목록을 확인 하 고 필요한 경우 연락처를 추가 해야 합니다.
    
    예약 된 모임은 Lync Online에서 Lync 온-프레미스로 마이그레이션되지 않음에 유의 하세요. 사용자는 이러한 모임을 이동한 후에 일정을 조정 해야 합니다.
    
    DNS 레코드가 업데이트 되 고 모든 사용자가 구내에 연결 되 면 HostingProvider 특성은 Lync 사용자에 게 SRV 레코드를 사용 하거나 온라인 공급자 "sipfed.online.lync.com"에 게 지시 하도록 지시 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

