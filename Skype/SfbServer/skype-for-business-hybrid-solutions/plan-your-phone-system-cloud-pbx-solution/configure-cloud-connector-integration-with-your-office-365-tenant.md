---
title: Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합 구성
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합을 구성하는 방법을 자세히 알아보습니다.
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359074"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합 구성

> [!Important] 
> Cloud Connector Edition은 2021년 7월 31일 비즈니스용 Skype Online과 함께 사용 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Microsoft 365 또는 Office 365 조직과 클라우드 커넥터 통합을 구성하는 방법을 자세히 알아보습니다.
  
비즈니스용 Skype 클라우드 커넥터 버전 설치가 완료되면 이 섹션의 단계를 수행하여 배포를 구성하고 Microsoft 365 또는 Office 365 조직에 연결합니다.
  
## <a name="configure-firewall-settings"></a>방화벽 설정 구성

경계 네트워크의 내부 및 외부 방화벽 설정에 대한 방화벽 설정을 구성하여 비즈니스용 Skype 클라우드 커넥터 버전 계획의 포트 및 프로토콜에 설명된 바와 같이 필요한 포트를 [열도록 합니다.](plan-skype-for-business-cloud-connector-edition.md) [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>PSTN(Public Switched Telephone Network) 게이트웨이 설정

모든 어플라이언스에 대한 중재 서버를 다시 지점으로 하여 각 PSTN 게이트웨이에 트렁크를 설치합니다. 풀 FQDN은 풀의 모든 서버에 대해 동일하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 중재 서버 FQDN 또는 IP 주소를 하나씩 설정해야 합니다. 트렁크는 동일한 우선 순위로 설정해야 합니다.
  
중재 서버와 게이트웨이 간에 TLS를 사용하는 경우 다음과 같이 MTLS를 지원하도록 게이트웨이 및 중재 서버를 구성해야 합니다.
  
1. 클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보낼 수 있습니다.
    
2. 루트 CA를 가져오기 위해 PSTN 게이트웨이 공급업체의 지침을 따릅니다.
    
3. 발급된 인증서에 대한 루트 CA 인증서를 중재 서버의 게이트웨이로 가져올 수 있습니다. 게이트웨이에 대한 SSL 인증서를 얻어야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행되는 인증 기관 서비스를 사용하여 이 작업을 수행하면 됩니다.
    
   - 기존 웹 서버 서식 파일을 수정하여 인증된 사용자가 등록할 수 있도록 설정하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성하고 인증된 사용자가 등록할 수 있도록 합니다. 자세한 내용은 인증서 [템플릿을 참조하십시오.](https://technet.microsoft.com/library/cc730705.aspx)
    
   - 사용하도록 설정한 웹 서버 템플릿을 선택하는 인증서 스냅인을 사용하여 인증서를 요청합니다. 게이트웨이의 FQDN을 사용하여 대체 이름의 주체 및 DNS 이름에 일반 이름을 추가하고 키 옵션에서 개인 키를 내보낼 수 있도록 설정하는 개인 키를 선택해야 합니다. 
    
4. 개인 키로 SSL 인증서를 내보내고 PSTN 게이트웨이 공급업체의 지침을 따라 인증서를 가져올 수 있습니다.
    
## <a name="update-the-domain-for-your-tenant"></a>테넌트의 도메인 업데이트

Microsoft 365 또는 Office 365에서 도메인을 업데이트하는 단계를 완료하고 DNS 레코드를 추가할 수 있는지 확인 합니다. Microsoft 365 또는 Office 365에서 도메인을 설정하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)도메인 추가를 참조하세요.
  
## <a name="add-dns-records-for-your-edge"></a>Edge에 대한 DNS 레코드 추가

Microsoft 365 또는 Office 365 조직에 다음 DNS 레코드를 추가합니다. DNS 레코드를 추가하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에서](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)사용자 지정 DNS 레코드 추가 또는 편집을 참조하세요.
  
1. 액세스 에지용 DNS A 레코드를 추가합니다.
    
2. SRV 레코드는 Microsoft 365 또는 Office 365 및 배포 스크립트에 의해 자동으로 만들어집니다. 에지에서 sip 및 \_ sipfederationtls의 두 SIP 서비스를 확인할 \_ 수 있습니다.
    
     ![SRV 레코드 확인](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Cloud Connector Edition과 Microsoft 365 또는 Office 365 간에 하이브리드 연결 설정

비즈니스용 Skype 클라우드 커넥터 버전 배포와 Microsoft 365 또는 Office 365 조직 간에 하이브리드 연결을 구성하기 위해 원격 PowerShell 세션에서 다음 cmdlet을 실행합니다. 원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 다음을 참조하여 다음을 [Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
이 cmdlet은 액세스 에지 외부 FQDN을 설정합니다. 첫 번째 명령에서는 SIP 액세스 에지 역할에 \<External Access Edge FQDN\> 대한 명령이 1개입니다. 기본적으로 이 구성은 \<Domain Name\> ap입니다.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 피어 대상에 사용되는 외부 액세스 에지 FQDN은 사용자가 PSTN 사이트에 할당되지 않은 경우만 폴백으로 사용되는 PSTN 사이트로 설정해야 합니다. 자세한 내용은 [클라우드](deploy-a-single-site-in-cloud-connector.md) 커넥터에서 단일 사이트 배포 및 클라우드 커넥터에서 여러 사이트 [배포를 참조하세요.](deploy-multiple-sites-in-cloud-connector.md) 
  
## <a name="set-up-pstn-gateways"></a>PSTN 게이트웨이 설정

모든 어플라이언스에 대한 중재 서버를 다시 지점으로 하여 각 PSTN 게이트웨이에 트렁크를 설치합니다. 풀 FQDN은 풀의 모든 서버에 대해 동일하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 설정해야 합니다. 트렁크는 동일한 우선 순위로 설정해야 합니다.
  
중재 서버와 게이트웨이 간에 TLS를 사용하는 경우 다음과 같이 MTLS를 지원하도록 게이트웨이 및 중재 서버를 구성해야 합니다.
  
1. 클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보낼 수 있습니다.
    
2. 루트 CA를 가져오기 위해 PSTN 게이트웨이 공급업체의 지침을 따릅니다.
    
3. 발급된 인증서에 대한 루트 CA 인증서를 중재 서버의 게이트웨이로 가져올 수 있습니다. 게이트웨이에 대한 SSL 인증서를 얻어야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행되는 인증 기관 서비스를 사용하여 이 작업을 수행하면 됩니다.
    
   - 기존 웹 서버 서식 파일을 수정하여 인증된 사용자가 등록할 수 있도록 설정하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성하고 인증된 사용자가 등록할 수 있도록 합니다. 자세한 내용은 인증서 [템플릿을 참조하십시오.](https://technet.microsoft.com/library/cc730705.aspx)
    
   - 사용하도록 설정한 웹 서버 템플릿을 선택하는 인증서 스냅인을 사용하여 인증서를 요청합니다. 게이트웨이의 FQDN을 사용하여 대체 이름의 주체 및 DNS 이름에 일반 이름을 추가하고 키 옵션에서 개인 키를 내보낼 수 있도록 설정하는 개인 키를 선택해야 합니다. 
    
4. 개인 키로 SSL 인증서를 내보내고 PSTN 게이트웨이 공급업체의 지침을 따라 인증서를 가져올 수 있습니다.
    
5. 한 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결해야 합니다.
    
## <a name="set-up-your-users"></a>사용자 설정

Microsoft 365 관리 센터에 로그인하고, 온라인 음성 서비스를 사용할 수 있는 사용자를 추가하고, E5 라이선스 또는 전화 시스템 추가 기능을 이러한 사용자에게 E3 라이선스에 할당합니다. 사용자를 추가하는 데 대한 자세한 내용은 [비즈니스용 Microsoft 365에 사용자 추가를 참조하세요.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>사용자가 전화 시스템 음성 및 음성메일 서비스를 사용할 수 있도록 설정
 
Microsoft 365 또는 Office 365에 사용자를 추가한 후 음성메일을 포함하여 전화 시스템 음성 서비스에 대한 계정을 사용하도록 설정하십시오. 이러한 기능을 사용하려면 전역 관리자 역할인 계정으로 Microsoft 365 또는 Office 365 조직에 로그인하고 원격 PowerShell을 실행할 수 있어야 합니다. 원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 다음을 참조하여 다음을 [Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- 사용자에게 정책을 할당하고 Identity 매개 변수의 값으로 지정하는 사용자의 비즈니스 음성 전화 번호를 **구성합니다.**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 사용자 ID는 사용자의 SIP 주소, UPN(사용자 계정 이름) 또는 사용자의 Active Directory 표시 이름(예: "Bob Kelly")을 사용하여 지정할 수 있습니다. 표시 이름에 사용자 ID로 추가() 문자를 \* 사용할 수도 있습니다. 예를 들어 ID "Smith"는 표시 이름이 문자열 값 "Smith"로 끝나는 모든 사용자를 \* 반환합니다.
  
그런 다음 다음 스크립트를 사용하여 사용자가 추가 및 사용하도록 설정되어 있는지 확인할 수 있습니다.
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

사용자가 국제 전화를 걸 수 있는지 여부를 결정해야 합니다. 기본적으로 국제 통화는 사용하도록 설정되어 있습니다. 사용자가 온라인 비즈니스용 Skype 관리 센터를 사용하여 국제 전화 걸기를 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.
  
사용자 기준 국제 통화를 사용하지 않도록 설정하기 위해 비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행합니다.
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

사용하지 않도록 설정한 후 사용자 기준으로 국제 통화를 다시 사용하도록 설정하려면 동일한 cmdlet을 실행하지만 **PolicyName의** 값을 *InternationalCallsAllowed로*  변경합니다.
  
## <a name="assign-users-to-pstn-sites"></a>PSTN 사이트에 사용자 할당

단일 사이트만 배포한 경우에도 테넌트 원격 PowerShell을 사용하여 사용자에게 사이트를 할당합니다. 원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 다음을 참조하여 다음을 [Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> 사용자에게 PSTN 사이트가 할당되지 않은 경우 비즈니스용 Skype 클라우드 커넥터 버전 배포와 Microsoft 365 또는 Office 365 조직 간의 하이브리드 연결은 테넌트 수준 기본 1(피어 대상)을 사용하여 통화를 완료할 수 있도록 변경됩니다. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>온라인 하이브리드 중재 서버 설정 구성
<a name="BKMK_ConfigureMediationServer"> </a>

P2P 통화가 PSTN 회의로 에스컬레이터될 때 비즈니스용 Skype Online 회의 서버는 클라우드 커넥터 중재 서버로 초대를 전송합니다. Microsoft 365 또는 Office 365에서 이 초대를 성공적으로 라우팅할 수 있도록하려면 다음과 같이 각 클라우드 커넥터 중재 서버에 대한 온라인 테넌트의 설정을 구성해야 합니다. 
  
1. Microsoft 365 관리 센터에서 사용자를 생성합니다. 원하는 사용자 이름(예: "MediationServer1")을 사용
    
    클라우드 커넥터의 기본 SIP 도메인(.ini 파일의 첫 번째 SIP 도메인)을 사용자 도메인으로 사용 합니다.
    
    라이선스 할당은 사용자가 비즈니스용 Skype 온라인 디렉터리로 전파하는 데만 필요합니다. 만든 계정에 Microsoft 365 또는 Office 365 라이선스(예: E5)를 할당하고 변경 내용이 전파될 수 있도록 최대 1시간을 허용하고, 다음 cmdlet을 실행하여 사용자 계정이 비즈니스용 Skype 온라인 디렉터리에 올바르게 프로비전된 후 이 계정에서 라이선스를 제거합니다.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. 전역 또는 사용자 관리자 자격 증명을 사용하여 테넌트 Azure AD 원격 PowerShell 세션을 시작한 다음 다음 cmdlet을 실행하여 1단계에서 구성된 Azure AD 사용자 계정에 대한 부서를 "HybridMediationServer"로 설정합니다.

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. 비즈니스용 Skype 테넌트 관리자 자격 증명을 사용하여 테넌트 비즈니스용 Skype 원격 PowerShell 세션을 시작한 다음 다음 cmdlet을 실행하여 중재 서버 및 에지 서버 FQDN을 해당 사용자 계정으로 설정하고, 1단계에서 만든 계정의 사용자 표시 이름으로 대체합니다. \<DisplayName\>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    ID의 경우 이 중재 서버에 대해 만든 사용자 계정의 표시 이름을 사용하세요.
    
    *MediationServerFQDN의* 경우 중재 서버에 대해 정의된 내부 FQDN을 사용 합니다.
    
    *EdgeServerExternalFQDN의* 경우 에지 서버 액세스 프록시에 대해 정의된 외부 FQDN을 사용 합니다. 클라우드 커넥터 PSTN 사이트가 여러 개인 경우 중재 서버가 있는 사이트에 할당된 에지 서버 액세스 프록시 FQDN을 선택하십시오.
    
4. 여러 클라우드 커넥터 중재 서버(다중 사이트, HA)가 있는 경우 각각에 대해 이전 단계를 반복하세요.
    
