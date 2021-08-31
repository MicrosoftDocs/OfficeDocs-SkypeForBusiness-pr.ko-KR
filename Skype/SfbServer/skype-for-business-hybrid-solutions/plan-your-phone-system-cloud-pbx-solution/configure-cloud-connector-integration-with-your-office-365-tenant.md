---
title: 조직 또는 조직과 클라우드 커넥터 Microsoft 365 Office 365 구성
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 조직 또는 조직과 클라우드 커넥터 통합을 Microsoft 365 Office 365 방법을 학습합니다.
ms.openlocfilehash: b3b8b13669a2e52ed5146e1bd0ca179a5542e43d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733377"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>조직 또는 조직과 클라우드 커넥터 Microsoft 365 Office 365 구성

> [!Important] 
> Cloud Connector Edition은 온라인과 함께 2021년 7월 31일 비즈니스용 Skype 있습니다. 조직에서 사용자 Teams 직접 라우팅을 사용하여 Teams 방법을 [확인합니다.](/MicrosoftTeams/direct-routing-landing-page)

조직 또는 조직과 클라우드 커넥터 통합을 Microsoft 365 Office 365 방법을 학습합니다.
  
비즈니스용 Skype 클라우드 커넥터 버전 설치가 완료되면 이 섹션의 단계를 수행하여 배포를 구성하고 조직 또는 조직에 Microsoft 365 Office 365 합니다.
  
## <a name="configure-firewall-settings"></a>방화벽 설정 구성

경계 네트워크에 대한 내부 및 외부 방화벽 설정에 대한 방화벽 설정을 구성하여 [](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) Plan [for 비즈니스용 Skype 클라우드 커넥터 버전.](plan-skype-for-business-cloud-connector-edition.md)
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>PSTN(Public Switched Telephone Network) 게이트웨이 설정

모든 어플라이언스에 대한 중재 서버를 다시 설정하기 위해 각 PSTN 게이트웨이에서 트렁크를 설정합니다. 풀 FQDN은 풀의 모든 서버에 대해 동일하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 지점해야 합니다. 트렁크는 동일한 우선 순위로 설정해야 합니다.
  
중재 서버와 게이트웨이 간에 TLS를 사용하는 경우 다음과 같이 MTLS를 지원하도록 게이트웨이 및 중재 서버를 구성해야 합니다.
  
1. 클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보낼 수 있습니다.
    
2. 루트 CA를 가져오는 데 대한 PSTN 게이트웨이 공급업체의 지침을 따릅니다.
    
3. 중재 서버의 게이트웨이로 발급된 인증서에 대한 루트 CA 인증서를 가져올 수 있습니다. 게이트웨이에 대한 SSL 인증서를 얻어야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행되는 인증 기관 서비스를 사용하여 이 작업을 수행하면 됩니다.
    
   - 기존 웹 서버 서식 파일을 수정하여 인증된 사용자가 등록하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성하고 인증된 사용자가 등록할 수 있도록 합니다. 자세한 지침은 인증서 템플릿 [을 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - 사용하도록 설정한 웹 서버 템플릿을 선택하는 인증서 스냅인을 사용하여 인증서를 요청합니다. 게이트웨이의 FQDN을 사용하여 대체 이름의 주체 및 DNS 이름에 일반 이름을 추가하고 키 옵션에서 개인 키를 내보낼 수 있도록 설정이 선택되어 있는지 개인 키에 대해 확인을 선택합니다. 
    
4. 개인 키로 SSL 인증서를 내보내고 인증서를 가져오기 위해 PSTN 게이트웨이 공급업체의 지침을 따릅니다.
    
## <a name="update-the-domain-for-your-tenant"></a>테넌트의 도메인 업데이트

도메인을 업데이트하는 단계를 완료해야 Microsoft 365 Office 365 DNS 레코드를 추가할 수 있습니다. Microsoft 365 또는 Office 365 도메인을 설정하는 방법에 대한 자세한 내용은 [Add a domain to Microsoft 365 or Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
  
## <a name="add-dns-records-for-your-edge"></a>Edge에 대한 DNS 레코드 추가

조직 또는 조직에 다음 DNS Microsoft 365 Office 365 추가합니다. DNS 레코드를 추가하는 방법에 대한 자세한 내용은 [Add or edit custom DNS records in Microsoft 365 or Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
  
1. 액세스 에지용 DNS A 레코드를 추가합니다.
    
2. SRV 레코드는 배포 Microsoft 365 Office 365 자동으로 만들어집니다. 에지에서 sip 및 \_ sipfederationtls의 두 SIP 서비스를 확인할 \_ 수 있습니다.
    
     ![SRV 레코드 확인입니다.](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>클라우드 커넥터 버전과 클라우드 커넥터 버전 또는 Microsoft 365 Office 365

비즈니스용 Skype 클라우드 커넥터 버전 배포와 Microsoft 365 또는 Office 365 간에 하이브리드 연결을 구성하기 위해 원격 PowerShell 세션에서 다음 cmdlet을 실행합니다. 원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
이 cmdlet은 액세스 에지 외부 FQDN을 설정합니다. 첫 번째 명령에서는 SIP 액세스 에지 역할에 \<External Access Edge FQDN\> 대한 명령이 에지 역할을 해야 합니다. 기본적으로 이 구성은 ap \<Domain Name\> 입니다.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 피어 대상에 사용되는 외부 액세스 에지 FQDN은 사용자가 PSTN 사이트에 할당되지 않은 경우만 폴백으로 사용되는 PSTN 사이트로 설정해야 합니다. 자세한 내용은 [클라우드](deploy-a-single-site-in-cloud-connector.md) 커넥터에서 단일 사이트 배포 및 클라우드 커넥터에서 여러 [사이트 배포를 참조하세요.](deploy-multiple-sites-in-cloud-connector.md) 
  
## <a name="set-up-pstn-gateways"></a>PSTN 게이트웨이 설정

모든 어플라이언스에 대한 중재 서버를 다시 설정하기 위해 각 PSTN 게이트웨이에서 트렁크를 설정합니다. 풀 FQDN은 풀의 모든 서버에 대해 동일하기 때문에 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 지점해야 합니다. 트렁크는 동일한 우선 순위로 설정해야 합니다.
  
중재 서버와 게이트웨이 간에 TLS를 사용하는 경우 다음과 같이 MTLS를 지원하도록 게이트웨이 및 중재 서버를 구성해야 합니다.
  
1. 클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보낼 수 있습니다.
    
2. 루트 CA를 가져오는 데 대한 PSTN 게이트웨이 공급업체의 지침을 따릅니다.
    
3. 중재 서버의 게이트웨이로 발급된 인증서에 대한 루트 CA 인증서를 가져올 수 있습니다. 게이트웨이에 대한 SSL 인증서를 얻어야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행되는 인증 기관 서비스를 사용하여 이 작업을 수행하면 됩니다.
    
   - 기존 웹 서버 서식 파일을 수정하여 인증된 사용자가 등록할 수 있도록 설정하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성하고 인증된 사용자가 등록할 수 있도록 합니다. 자세한 지침은 인증서 템플릿 [을 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))
    
   - 사용하도록 설정한 웹 서버 템플릿을 선택하는 인증서 스냅인을 사용하여 인증서를 요청합니다. 게이트웨이의 FQDN을 사용하여 대체 이름의 주체 및 DNS 이름에 일반 이름을 추가하고 키 옵션에서 개인 키를 내보낼 수 있도록 설정이 선택되어 있는지 개인 키에 대해 확인을 선택합니다. 
    
4. 개인 키로 SSL 인증서를 내보내고 인증서를 가져오기 위해 PSTN 게이트웨이 공급업체의 지침을 따릅니다.
    
5. 한 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결해야 합니다.
    
## <a name="set-up-your-users"></a>사용자 설정

Microsoft 365 관리 센터 로그인하고 온라인 음성 서비스를 사용할 수 있는 사용자를 추가하고, E5 라이선스 또는 전화 시스템 추가 기능을 이러한 사용자에게 할당합니다. 사용자 추가에 대한 자세한 내용은 비즈니스용 앱에 Microsoft 365 [추가를 참조하세요.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>사용자가 음성 및 전화 시스템 서비스를 사용할 수 있도록 설정
 
사용자를 음성 Microsoft 365 Office 365 추가한 후 음성 전화 시스템 포함하여 음성 서비스에 대한 계정을 사용하도록 설정하십시오. 이러한 기능을 사용하려면 전역 관리자 역할인 계정을 사용하여 Microsoft 365 또는 Office 365 조직에 로그인하고 원격 PowerShell을 실행할 수 있어야 합니다. 원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- 사용자에게 정책을 할당하고 Identity 매개 변수의 값으로 지정하는 사용자의 비즈니스 음성 전화 번호를 **구성합니다.**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 사용자 ID는 사용자의 SIP 주소, UPN(사용자 계정 이름) 또는 사용자의 Active Directory 표시 이름(예: "Bob Kelly")을 사용하여 지정할 수 있습니다. 또한 표시 이름에 사용자 ID로 \* 추가() 문자를 사용할 수도 있습니다. 예를 들어 ID "Smith"는 표시 이름이 문자열 값 "Smith"로 끝나는 모든 사용자를 \* 반환합니다.
  
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

사용자가 국제 전화를 걸 수 있는지 여부를 결정해야 합니다. 기본적으로 국제 통화는 사용하도록 설정되어 있습니다. 온라인 전화 걸기 관리 센터를 사용하여 사용자를 국제 전화 걸기를 사용하지 않도록 설정하거나 비즈니스용 Skype 있습니다.
  
사용자 기준으로 국제 통화를 사용하지 않도록 설정하기 위해 온라인 PowerShell에서 비즈니스용 Skype 실행합니다.
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

사용하지 않도록 설정한 후 사용자 기준 국제 통화를 다시 사용하도록 설정하려면 동일한 cmdlet을 실행하 고 **PolicyName의** 값을 *InternationalCallsAllowed로*  변경합니다.
  
## <a name="assign-users-to-pstn-sites"></a>PSTN 사이트에 사용자 할당

단일 사이트만 배포한 경우에도 테넌트 원격 PowerShell을 사용하여 사용자에게 사이트를 할당합니다. 원격 PowerShell 세션을 설정하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
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
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>온라인 하이브리드 중재 서버 설정
<a name="BKMK_ConfigureMediationServer"> </a>

P2P 통화가 PSTN 회의로 에스컬레이터될 때 비즈니스용 Skype 온라인 회의 서버는 클라우드 커넥터 중재 서버로 초대를 전송합니다. 이 Microsoft 365 Office 365 라우팅할 수 있도록 각 클라우드 커넥터 중재 서버에 대해 온라인 테넌트의 설정을 다음과 같이 구성해야 합니다. 
  
1. 사용자 계정에서 사용자를 Microsoft 365 관리 센터. 원하는 사용자 이름(예: "MediationServer1")을 사용
    
    클라우드 커넥터의 기본 SIP 도메인(.ini 파일의 첫 번째 SIP 도메인)을 사용자 도메인으로 사용 합니다.
    
    라이선스 할당은 사용자가 온라인 디렉터리에 비즈니스용 Skype 필요합니다. 만든 계정에 Microsoft 365 또는 Office 365 라이선스(예: E5)를 할당하고 변경 내용이 전파될 수 있도록 최대 1시간을 허용하고, 다음 cmdlet을 실행하여 사용자 계정이 비즈니스용 Skype online 디렉터리에 올바르게 프로비전되어 있는지 확인한 다음 이 계정에서 라이선스를 제거합니다.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. 전역 또는 사용자 관리자 자격 증명을 사용하여 테넌트 Azure AD 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행하여 1단계에서 구성된 Azure AD 사용자 계정의 부서를 "HybridMediationServer"로 설정합니다.

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. 비즈니스용 Skype 테넌트 관리자 자격 증명을 사용하여 테넌트 비즈니스용 Skype PowerShell 세션을 시작한 후 다음 cmdlet을 실행하여 중재 서버 및 에지 서버 FQDN을 해당 사용자 계정으로 설정하고, 1단계에서 만든 계정에 대한 사용자의 표시 이름으로 대체합니다. \<DisplayName\>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    ID의 경우 이 중재 서버에 대해 만든 사용자 계정의 표시 이름을 사용하세요.
    
    *MediationServerFQDN의* 경우 중재 서버에 대해 정의된 내부 FQDN을 사용 합니다.
    
    *EdgeServerExternalFQDN의* 경우 에지 서버 액세스 프록시에 정의된 외부 FQDN을 사용 합니다. 클라우드 커넥터 PSTN 사이트가 여러 개 있는 경우 중재 서버가 있는 사이트에 할당된 에지 서버 액세스 프록시 FQDN을 선택하십시오.
    
4. 여러 클라우드 커넥터 중재 서버(다중 사이트, HA)가 있는 경우 각 서버에 대해 이전 단계를 반복하세요.
