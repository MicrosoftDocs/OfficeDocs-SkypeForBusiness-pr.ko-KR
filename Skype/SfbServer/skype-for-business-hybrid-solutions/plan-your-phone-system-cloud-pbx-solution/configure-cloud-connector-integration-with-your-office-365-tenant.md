---
title: Microsoft 365 또는 Office 365 조직과의 클라우드 커넥터 통합 구성
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
description: Office 365 조직과의 클라우드 커넥터 통합을 구성 하는 방법을 알아봅니다.
ms.openlocfilehash: 1fecf017f614fc8bdf0f38b5f51c29e4b2774357
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780647"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Microsoft 365 또는 Office 365 조직과의 클라우드 커넥터 통합 구성
 
Office 365 조직과의 클라우드 커넥터 통합을 구성 하는 방법을 알아봅니다.
  
비즈니스용 Skype 클라우드 커넥터 Edition 설치가 완료 되 면이 섹션의 단계를 수행 하 여 배포를 구성 하 고 Office 365 조직에 연결 합니다.
  
## <a name="configure-firewall-settings"></a>방화벽 설정 구성

주변 네트워크에 대 한 내부 및 외부 방화벽 설정에 대 한 방화벽 설정을 구성 하 여 [비즈니스용 Skype 클라우드 커넥터 에디션 계획](plan-skype-for-business-cloud-connector-edition.md)의 [포트 및 프로토콜](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) 에 설명 된 대로 필요한 포트를 엽니다.
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>공중 전화망 (PSTN) 게이트웨이 설정

모든 기기에 대 한 중재 서버를 가리키도록 각 PSTN 게이트웨이에서 트렁크을 설정 합니다. 풀 FQDN은 풀에 있는 모든 서버에서 동일 하므로 각 트렁크는 중재 서버 풀 FQDN 대신 하나의 중재 서버 FQDN 또는 IP 주소를 가리켜야 합니다. 트렁크는 동일한 우선 순위로 설정 해야 합니다.
  
중재 서버와 게이트웨이 간에 TLS를 사용 하는 경우 다음과 같이 MTLS를 지원 하도록 게이트웨이 및 중재 서버를 구성 해야 합니다.
  
1. 클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보냅니다.
    
2. PSTN 게이트웨이 공급 업체 지침에 따라 루트 CA를 가져옵니다.
    
3. 중재 서버에서 게이트웨이로 발급 된 인증서에 대 한 루트 CA 인증서를 가져옵니다. 게이트웨이에 대 한 SSL 인증서를 취득 해야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행 되는 인증 기관 서비스를 사용 하 여이 작업을 수행할 수 있습니다.
    
   - 기존 웹 서버 서식 파일을 수정 하 여 인증 된 사용자가 등록 하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성 하 고 인증 된 사용자가 등록할 수 있도록 설정 합니다. 자세한 내용은 [인증서 템플릿을](https://technet.microsoft.com/library/cc730705.aspx)참조 하십시오.
    
   - 사용 하도록 설정한 웹 서버 서식 파일을 선택 하 여 인증서 스냅인을 사용 하 여 인증서를 요청 합니다. 주체 및 DNS 이름의 일반 이름을 게이트웨이 FQDN과 함께 대체 이름으로 추가 하 고, 키 옵션에서 내보낼 수 있는 개인 키를 선택 하는 개인 키를 확인 합니다. 
    
4. 개인 키를 사용 하 여 SSL 인증서를 내보내고 PSTN 게이트웨이 공급 업체의 지침에 따라 인증서를 가져옵니다.
    
## <a name="update-the-domain-for-your-tenant"></a>테 넌 트에 대 한 도메인 업데이트

Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다. Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [Add a domain To office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)을 참조 하십시오.
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>에 지에 대 한 Office 365의 DNS 레코드 추가

Office 365 조직에 다음 DNS 레코드를 추가 합니다. Office 365 조직에 DNS 레코드를 추가 하는 방법에 대 한 자세한 내용은 [office 365에서 사용자 지정 dns 레코드 추가 또는 편집](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)을 참조 하십시오.
  
1. 액세스에 지에 대 한 DNS A 레코드를 추가 합니다.
    
2. SRV 레코드는 Office 365 및 배포 스크립트에 의해 자동으로 만들어집니다. Edge: _sip 및 _sipfederationtls에서 다음 두 SIP 서비스를 조회할 수 있는지 확인 합니다.
    
     ![SRV 레코드 확인](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>클라우드 커넥터 버전 및 Office 365 간 하이브리드 연결 설정

비즈니스용 Skype 클라우드 커넥터 에디션 배포와 Office 365 조 직 간에 하이브리드 연결을 구성 하려면 원격 PowerShell 세션에서 다음 cmdlet을 실행 합니다. 원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell에 대 한 컴퓨터 설정](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)를 참조 하십시오.
  
Cmdlet은 액세스에 지 외부 FQDN을 설정 합니다. 첫 번째 명령에서 외부 액세스에 지 \<FQDN\> 은 SIP 액세스에 지 역할에 대해 하나 여야 합니다. 기본적으로이 이름은 ap. 도메인 이름\<\>이어야 합니다.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 피어 대상에 사용 되는 외부 액세스에 지 FQDN은 사용자가 PSTN 사이트에 할당 되지 않은 경우에만 폴백으로 사용 되는 PSTN 사이트로 설정 해야 합니다. 자세한 내용은 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md) 및 [클라우드 커넥터에 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md)를 참조 하세요. 
  
## <a name="set-up-pstn-gateways"></a>PSTN 게이트웨이 설정

모든 기기에 대 한 중재 서버를 가리키도록 각 PSTN 게이트웨이에서 트렁크을 설정 합니다. 풀 FQDN은 풀에 있는 모든 서버에서 동일 하므로 각 트렁크는 중재 서버 풀 FQDN 대신 중재 서버 FQDN 또는 IP 주소 하나를 가리켜야 합니다. 트렁크는 동일한 우선 순위로 설정 해야 합니다.
  
중재 서버와 게이트웨이 간에 TLS를 사용 하는 경우 다음과 같이 MTLS를 지원 하도록 게이트웨이 및 중재 서버를 구성 해야 합니다.
  
1. 클라우드 커넥터 Active Directory 컴퓨터에서 루트 CA를 내보냅니다.
    
2. PSTN 게이트웨이 공급 업체 지침에 따라 루트 CA를 가져옵니다.
    
3. 중재 서버에서 게이트웨이로 발급 된 인증서에 대 한 루트 CA 인증서를 가져옵니다. 게이트웨이에 대 한 SSL 인증서를 취득 해야 하는 경우 다음과 같이 클라우드 커넥터 Active Directory 컴퓨터에서 실행 되는 인증 기관 서비스를 사용 하 여이 작업을 수행할 수 있습니다.
    
   - 기존 웹 서버 서식 파일을 수정 하 여 인증 된 사용자가 등록 하거나 새 웹 서버 템플릿을 만들어 다른 속성을 구성 하 고 인증 된 사용자가 등록할 수 있도록 설정 합니다. 자세한 내용은 [인증서 템플릿을](https://technet.microsoft.com/library/cc730705.aspx)참조 하십시오.
    
   - 사용 하도록 설정한 웹 서버 서식 파일을 선택 하 여 인증서 스냅인을 사용 하 여 인증서를 요청 합니다. 주체 및 DNS 이름의 일반 이름을 게이트웨이 FQDN과 함께 대체 이름으로 추가 하 고, 키 옵션에서 내보낼 수 있는 개인 키를 선택 하는 개인 키를 확인 합니다. 
    
4. 개인 키를 사용 하 여 SSL 인증서를 내보내고 PSTN 게이트웨이 공급 업체의 지침에 따라 인증서를 가져옵니다.
    
5. PSTN 사이트 하나에 있는 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결 해야 합니다.
    
## <a name="set-up-your-users-in-office-365"></a>Office 365에서 사용자 설정

Microsoft 365 관리 센터에 로그인 하 고, 온라인 음성 서비스에 사용할 사용자를 추가 하 고, 다음 사용자에 게 E3 라이선스에 대 한 e 5 추가 기능 365에서 E5 라이선스 또는 전화 시스템을 할당 합니다. 사용자를 추가 하는 방법에 대 한 자세한 내용은 [비즈니스용 Office 365에 사용자 추가](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)를 참조 하세요.
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Office 365 음성 및 음성 메일 서비스에서 전화 시스템에 대해 사용자를 사용 하도록 설정

Office 365에 사용자를 추가한 후 음성 메일을 포함 하 여 Office 365 음성 서비스에서 전화 시스템용 계정을 사용 하도록 설정 합니다. 이러한 기능을 사용 하도록 설정 하려면 전역 관리자 역할인 계정을 사용 하 여 Office 365 조직에 로그인 하 고 원격 PowerShell을 실행할 수 있어야 합니다. 원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell에 대 한 컴퓨터 설정](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx) 를 참조 하세요.
  
- 사용자에 게 정책을 할당 하 고 **Identity** 매개 변수의 값으로 지정 하는 사용자의 비즈니스 음성 전화 번호를 구성 합니다.
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 사용자의 SIP 주소, UPN (사용자 계정 이름) 또는 사용자의 Active Directory 표시 이름 (예: "Bob 최소라")을 사용 하 여 id를 지정할 수 있습니다. 별표 (\*) 문자는 사용자 Id로 표시 이름과 함께 사용할 수도 있습니다. 예를 들어 Id "\*smith"는 표시 이름이 문자열 값 "Smith"로 끝나는 모든 사용자를 반환 합니다.
  
그러면 다음 스크립트를 사용 하 여 사용자가 추가 되 고 사용 하도록 설정 되었는지 확인할 수 있습니다.
  
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

사용자가 국제 전화를 걸 수 있도록 할지 여부를 결정 해야 합니다. 기본적으로 국제 통화는 사용 하도록 설정 되어 있습니다. 온라인 비즈니스용 Skype 관리 센터를 사용 하 여 국제 전화 걸기에 대해 사용자를 사용 하지 않도록 설정 하거나 사용 하도록 설정할 수 있습니다.
  
사용자별로 국제 통화를 사용 하지 않도록 설정 하려면 비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행 합니다.
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

사용자 단위를 사용 하지 않도록 설정한 후 국가별 호출을 다시 사용 하도록 설정 하려면 동일한 cmdlet을 실행 하 되 **PolicyName** 의 값을 *InternationalCallsAllowed* 로 변경 합니다.
  
## <a name="assign-users-to-pstn-sites"></a>PSTN 사이트에 사용자 할당

단일 사이트만 배포한 경우에도 테 넌 트 원격 PowerShell을 사용 하 여 사용자에 게 사이트를 할당 합니다. 원격 PowerShell 세션을 설정 하는 방법에 [대 한 자세한 내용은 Windows PowerShell에 대 한 컴퓨터 설정](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)를 참조 하십시오.
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> 사용자에 게 할당 된 PSTN 사이트가 없는 경우 비즈니스용 Skype 클라우드 커넥터 에디션 배포와 Office 365 조직 간의 하이브리드 연결이 다시 시도 하 여 전화를 완료할 수 있도록 테 넌 트 수준 기본 1 (피어 대상)을 사용 하 게 됩니다. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>온라인 하이브리드 중재 서버 설정 구성
<a name="BKMK_ConfigureMediationServer"> </a>

P2P 호출이 PSTN 회의로 에스컬레이션 되 면 비즈니스용 Skype 온라인 회의 서버에서 클라우드 커넥터 중재 서버에 대 한 초대를 보냅니다. Office 365에서이 초대를 라우팅할 수 있도록 하려면 각 클라우드 커넥터 중재 서버에 대해 다음과 같이 온라인 테 넌 트의 설정을 구성 해야 합니다. 
  
1. Microsoft 365 관리 센터에서 사용자를 만듭니다. 원하는 사용자 이름 (예: "MediationServer1")을 사용 합니다.
    
    사용자 도메인으로는 클라우드 커넥터의 기본 SIP 도메인 (.ini 파일의 첫 번째 SIP 도메인)을 사용 합니다.
    
    라이선스 할당은 비즈니스용 Skype online 디렉터리로의 사용자 전파에만 필요 합니다. 만든 계정에 Office 365 라이선스 (예: E5)를 할당 하 고, 변경 내용을 전파할 최대 1 시간을 허용 하 고, 다음 cmdlet을 실행 하 여 사용자 계정이 비즈니스용 Skype 온라인 디렉터리에 올바르게 프로 비전 되었는지 확인 한 후에이 계정에서 라이선스를 제거 합니다.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. 전역 또는 사용자 관리자 자격 증명을 사용 하 여 테 넌 트 Azure AD 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 1 단계에서 구성한 Azure AD 사용자 계정에 대 한 부서를 "HybridMediationServer"로 설정 합니다.

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. 비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 비즈니스용 Skype 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 중재 서버 및에 지 서버 FQDN을 해당 사용자 \<계정\> 으로 설정 하 고 DisplayName을 1 단계에서 만든 계정에 대 한 사용자의 표시 이름으로 바꿉니다.
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Id의 경우이 중재 서버에 대해 만든 사용자 계정의 표시 이름을 사용 합니다.
    
    *Mediationserverfqdn* 에 대해 중재 서버에 대해 정의 된 내부 FQDN을 사용 합니다.
    
    *EdgeServerExternalFQDN* 의 경우에 지 서버 액세스 프록시에 대해 정의 된 외부 FQDN을 사용 합니다. 클라우드 커넥터 PSTN 사이트가 여러 개인 경우 중재 서버가 있는 사이트에 할당 된에 지 서버 액세스 프록시 FQDN을 선택 합니다.
    
4. 여러 클라우드 커넥터 중재 서버 (다중 사이트, HA)가 있는 경우에는 각 작업에 대해 위의 단계를 반복 해 보십시오.
    

