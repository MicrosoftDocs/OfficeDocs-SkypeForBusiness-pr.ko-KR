---
title: 클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 문서에는 Teams 및 비즈니스용 Skype에 대한 클라우드 통합의 일부로 하이브리드를 사용 안 하게 하는 자세한 단계가 포함되어 있습니다.
ms.openlocfilehash: 18bda898563e10dbf964ba149f27202372fbcceb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656704"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a>하이브리드 구성을 사용하지 않도록 설정하여 클라우드로의 마이그레이션 완료

이 문서에서는 비즈니스용 Skype 환경을 해제하기 전에 하이브리드 구성을 사용하지 않도록 설정하는 방법을 설명합니다. 이 단계는 다음 단계 중 2단계로, 프레미스 환경을 해제합니다.

- 1단계. 필요한 모든 사용자를 프레미스에서 [온라인으로 이동](decommission-move-on-prem-users.md)

- **2단계. 하이브리드 구성을 사용하지 않도록 설정** (이 문서)

- 3단계. [하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)프레미스에서 온라인으로 이동

- 4단계. [비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)


## <a name="overview"></a>개요

비즈니스용 Skype의 모든 사용자를 Microsoft 365의 Teams 전용으로 업그레이드한 후 비즈니스용 Skype 배포를 해제할 수 있습니다. 비즈니스용 Skype 배포를 해제하고 하드웨어를 제거하기 전에 하이브리드를 해제하여 Microsoft 365에서 논리적으로 배포를 분리해야 합니다. 하이브리드를 비동기화하는 단계는 다음 세 단계로 구성됩니다.

1. Microsoft 365를 가리키도록 DNS 레코드를 업데이트합니다.

2. Microsoft 365 조직에서 공유 sip 주소 공간("분할 도메인"이라고도 알려지기)을 사용하지 않도록 설정합니다.

3. Microsoft 365와 통신하는 기능을 사내에서 사용하지 않도록 설정

이러한 단계는 비즈니스용 Skype 서버의 사내 배포를 Microsoft 365와 논리적으로 분리하며 단위로 함께 수행해야 합니다. 이 문서에서는 각 단계에 대한 세부 정보를 제공합니다. 완료되면 아래 참조된 두 가지 방법 중 하나를 사용하여 비즈니스용 Skype 배포를 해제할 수 있습니다.

> [!Important] 
> 이 논리적 분리가 완료되면, 사내 Active Directory의 msRTCSIP 특성은 여전히 값을 가지며 Azure AD Connect를 통해 Azure AD로 계속 동기화됩니다. 사내 환경을 해제하는 방법은 이러한 특성을 그대로 두는지 아니면 먼저 해당 특성을 On-프레미스 Active Directory에서 지우는지 여부에 따라 결정됩니다. 사내에서 마이그레이션한 후 사내 msRTCSIP 특성을 지우면 사용자에 대한 서비스가 손실될 수 있습니다. 두 가지 해제 방법의 세부 정보 및 장단점에 대한 설명은 나중에 설명되어 있습니다.

## <a name="detailed-steps"></a>세부 단계

1. *Microsoft 365를 지점으로 DNS를 업데이트합니다.* 비즈니스용 Skype 레코드가 Microsoft 365를 프레미스 배포가 아닌 Microsoft 365를 지점으로 하게 하기 위해 조직에 대한 조직의 외부 DNS를 업데이트해야 합니다. 특히 다음 사항에 유의합니다.

    |레코드 유형|이름|TTL|값|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|

    또한 meet 또는 dialin(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다. 마지막으로 내부 네트워크에서 비즈니스용 Skype에 대한 DNS 레코드를 제거해야 합니다.

    > [!Note] 
    > 드문 경우지만 DNS를 조직의 Microsoft 365로 설정하는 경우 다른 조직에서 페더링 구성을 업데이트할 때까지 일부 다른 조직과의 페더링이 중지될 수 있습니다.
    >
    > - 이전 Direct Federation 모델(허용 파트너 서버라고도 지칭)을 사용하는 페더러된 조직은 조직에 대해 허용되는 도메인 항목을 업데이트하여 프록시 FQDN을 제거해야 합니다. 이 레거시 페더전 모델은 DNS SRV 레코드를 기반으로 하지 않습니다. 따라서 조직이 클라우드로 이동하면 이러한 구성이 최신이 됩니다.
    > 
    > - sipfed.online.lync에 대해 호스팅 공급자를 사용하도록 설정하지 않은 페더링된 조직입니다. <span> com은 구성을 업데이트하여 사용하도록 설정해야 합니다. 이 상황은 페더러드 조직이 전적으로 사내에 있으며 하이브리드 또는 온라인 테넌트와 페더러이트한 적이 없는 경우만 가능합니다. 이 경우 호스팅 공급자를 사용하도록 설정해야 이러한 조직과의 페더링이 작동하지 않습니다.
    >
    > 페더더러 파트너 중 한 자가 직접 페더ation을 사용 중일 수 있는 것으로 의심되거나 온라인 또는 하이브리드 조직과 페더러이트되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 통신을 해당 파트너에게 보내는 것이 좋은 제안입니다.


2.  *Microsoft 365 조직에서 공유 sip 주소 공간을 사용하지 않도록 설정* 아래 명령은 비즈니스용 Skype Online PowerShell 창에서 완료해야 합니다.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *Microsoft 365와 통신하는 기능을 사내에서 사용하지 않도록 설정* 아래 명령은 다음을 수행해야 합니다.

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>사용자를 사내에서 클라우드로 이동한 후 특성 관리

기본적으로 이전에 비즈니스용 Skype 서버를 사용하도록 설정되어 클라우드로 이동한 모든 사용자는 여전히 msRTCSIP 특성이 사내 Active Directory에 구성되어 있습니다. 이러한 특성, 특히 sip 주소(msRTCSIP-PrimaryUserAddress) 및 잠재적으로 전화 번호(msRTCSIP-Line)는 Azure AD에 계속 동기화합니다. msRTCSIP 특성 중 어느 것이든 변경해야 하는 경우 이러한 변경 내용은 On-premises Active Directory에서 적용한 다음 Azure AD와 동기화해야 합니다. 그러나 비즈니스용 Skype 서버 배포가 제거되면 비즈니스용 Skype 서버 도구를 사용하여 이러한 특성을 관리할 수 없습니다.

이 상황을 처리하는 두 가지 옵션을 사용할 수 있습니다.

1. 비즈니스용 Skype 서버 계정에 대해 사용하도록 설정된 사용자를 그대로 사용하고 Active Directory 도구를 사용하여 msRTCSIP 특성을 관리합니다. 이렇게 하면 마이그레이션된 사용자의 서비스가 손실되지 않고, 전체 해제 없이 서버를 제거(예: 지우기)하여 비즈니스용 Skype 서버 배포를 쉽게 제거할 수 있습니다. 그러나 새로 라이선스가 부여된 사용자는 이러한 특성을 On-premises Active Directory에 채우지 못하며 온라인에서 관리해야 합니다.

2.  모든 msRTCSIP 특성을 모든 msRTCSIP 특성의 선택을 취소하고 온라인 도구를 사용하여 이러한 특성을 관리합니다. 이 방법을 사용하면 기존 사용자와 새 사용자에 대해 일관된 관리 방식을 사용할 수 있습니다. 그러나 잠재적으로는 사내 해제 프로세스 중에 서비스가 일시적으로 손실될 수 있습니다.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>방법 1 - Active Directory에서 사용자의 sip 주소 및 전화 번호 관리

관리자는 이전의 비즈니스용 Skype 서버에서 클라우드로 이동된 사용자를 관리할 수 있습니다. 이 사용자는 사내 배포가 해제된 후에도 관리할 수 있습니다. 사용자의 sip 주소 또는 사용자의 전화 번호(및 sip 주소 또는 전화 번호에 이미 On-premises Active Directory에 값이 있는 경우)를 변경하려는 경우, 이 작업을 On-premises Active Directory에서 이 작업을 하고 값이 Azure AD로 흐르게 해야 합니다. 이 서버에는 비즈니스용 Skype 서버가 필요하지 않습니다. 대신, Active Directory 사용자 및 컴퓨터 MMC 스냅인(아래 그림과 같이)을 사용하거나 PowerShell을 사용하여 이러한 특성을 On-premises Active Directory에서 직접 수정할 수 있습니다. MMC 스냅인을 사용하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭한 후 수정할 적절한 특성을 찾아야 합니다.

- 사용자의 sip 주소를 수정하려면 를 `msRTCSIP-PrimaryUserAddress` 수정합니다. 특성에 sip 주소가 포함되어 있는 경우 해당 값을 모범 사례로 `ProxyAddresses` 업데이트합니다. 의 sip 주소가 채워진 경우 O365에서 무시해도 다른 사내 구성 요소에서 사용할 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 수 있습니다.

- 사용자의 전화 번호를 수정하려면 값이 이미 있는 경우 `msRTCSIP-Line` *수정합니다.*

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
-  사용자가 이동하기 전에 원래의 값이 아닌 경우 비즈니스용 Skype Online PowerShell 모듈의 `msRTCSIP-Line` `onpremLineUri` [Set-CsUser cmdlet에서](/powershell/module/skype/set-csuser?view=skype-ps) - 매개 변수를 사용하여 전화 번호를 수정할 수 있습니다.

하이브리드를 사용하지 않도록 설정한 후 새로 만든 사용자는 이러한 단계를 수행하지 않고 클라우드에서 직접 관리할 수 있습니다. 이러한 방법과 msRTCSIP 특성을 모두 사용하는 것뿐만 아니라 이러한 방법을 사용하는 것이 편한 경우, 단순히 비즈니스용 Skype 서버를 다시 이미지로 만들면 됩니다. 그러나 모든 msRTCSIP 특성을 지우고 비즈니스용 Skype 서버의 기존 제거를 원하는 경우 방법 2를 사용합니다.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>방법 2 - Active Directory의 모든 사내 사용자에 대한 비즈니스용 Skype 특성 지우기

이 옵션을 사용하려면 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 다시 프로비전해야 했기 때문에 추가 작업 및 적절한 계획이 필요합니다. 이러한 사용자는 전화 시스템이 없는 사용자와 전화 시스템이 있는 사용자 등 두 가지 범주로 분류될 수 있습니다. 전화 시스템을 사용할 경우 전화 번호를 클라우드로 전환할 때 전화 번호가 일시적으로 손실됩니다. **대량 사용자 작업을 시작하기 전에 적은 수의 사용자가 전화 시스템을 포함하는 파일럿을 수행하는 것이 좋습니다.** 대규모 배포의 경우 사용자는 서로 다른 시간 창의 소규모 그룹에서 처리될 수 있습니다. 

> [!NOTE] 
> 이 프로세스는 일치하는 sip 주소와 UserPrincipalName이 있는 사용자에게 가장 간단합니다. 이러한 두 특성에서 일치하지 않는 값이 있는 사용자가 있는 조직의 경우 원활한 전환을 위해 아래에서 설명한에 따라 특히 주의해야 합니다.

> [!NOTE]
> 자동 전화 걸기 또는 통화 큐에 대해 사내 하이브리드 응용 프로그램 끝점을 구성한 경우 비즈니스용 Skype 서버를 해제하기 전에 이러한 끝점을 Microsoft 365로 이동해야 합니다.


1. 다음의 비즈니스용 Skype PowerShell cmdlet이 빈 결과를 반환하는지 확인 결과가 비어 있는 것은 사용자가 사내에 있거나 Microsoft 365로 이동되거나 비활성화된 사용자가 없음을 의미합니다.

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 다음의 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 사용자 데이터를 내보내어 사용자의 현재 전화 번호(LineUri), UserPrincipalName 및 관련 정보를 기록합니다.

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > 파일 열기 SfbUserSettings.csv 모든 사용자 데이터를 성공적으로 내보낼 수 있도록 합니다. 이 파일의 복사본을 보관하는 것이 좋습니다.  다음 단계에서는 사용자를 처리하기 위해 이 파일을 사용하지 않습니다. 

3. 다음 단계에서 사용할 사용자 그룹이 있는 파일을 만드십시오. 첫 번째 사용자 그룹이 성공적으로 완료되면 다음 사용자 그룹으로 진행합니다. 아래 예제에서는 사용자 그룹이 사전순으로 선택되지만 사용자를 처리하고자 하는 방식과 일치하는 기준에 따라 사용자를 필터링할 수 있습니다.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > 파일 열기 SfbUsers.csv 사용자 데이터가 성공적으로 내보혔는지 확인하기 전에 이후 단계에서 이 파일의 LineUri(전화 번호), UserPrincipalName, SamAccountName 및 SipAddress가 필요합니다.

4. 업데이트할 준비가 된 사용자 집합에 대해 Active Directory에서 비즈니스용 Skype 서버와 관련된 특성 정보를 삭제합니다.  아래와 같이 이 프로세스에는 2단계가 있습니다.

   > [!Important] 
   > 이 단계를 실행한 후 다음 AAD 동기화 주기가 완료되면 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 전화 시스템을 사용 중인 사용자는 8단계가 성공적으로 완료되고 9단계에서 확인될 때까지 전화를 걸고 받을 수 없습니다. 또한 해당 단계에 해당 정보가 필요하기 때문에 2단계에 따라 사용자의 전화 번호 및 관련 정보를 저장해야 합니다.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   다음으로, 동일한 사용자 집합에 대해, 다음을 사용하여 msRTCSIP-DeploymentLocator의 값을 지우고, 다음을 구현합니다.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. 다음의 비즈니스용 Skype PowerShell cmdlet을 실행하여 sip 주소 값을 다시 On-premises Active Directory proxyAddresses에 추가합니다. 이렇게 하면 이 특성을 사용 하는 상호 연산 문제가 방지 됩니다. 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. Azure AD 동기화 실행

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. 사용자 프로비전이 완료될 때까지 기다렸다가 다음 비즈니스용 Skype Online PowerShell 명령을 실행하여 사용자 프로비전 진행 상황을 모니터링할 수 있습니다. 다음 비즈니스용 Skype Online PowerShell 명령은 프로세스가 완료된 즉시 빈 결과를 반환합니다.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 다음 비즈니스용 Skype Online PowerShell 명령을 실행하여 전화 번호를 할당하고 사용자가 전화 시스템을 사용할 수 있도록 합니다.
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  여전히 비즈니스용 Skype 끝점(Skype 클라이언트 또는 제3자 전화)이 있는 경우 -HostedVoiceMail을 $true. 조직에서 음성 사용 가능 사용자에 대해 Teams 끝점만 사용하는 경우 이 설정은 사용자에게 적용되지 않습니다. 

9. 전화 시스템 기능이 있는 사용자가 올바르게 프로비전되어 있는지 확인합니다. 다음 비즈니스용 Skype Online PowerShell 명령은 프로세스가 완료된 즉시 빈 결과를 반환합니다.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. 모든 사용자가 처리될 때까지 3-9단계를 반복합니다.

11. 다음 두 PowerShell 명령을 실행하여 모든 사용자가 성공적으로 처리된지 확인

    On-premises Skype for Business Server on-premises PowerShell command:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    비즈니스용 Skype Online PowerShell 명령:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. 방법 2의 모든 단계를 완료한 [](decommission-move-on-prem-endpoints.md) 후 하이브리드 응용 프로그램 끝점 이동을 온라인으로 이동 및 비즈니스용 Skype 서버의 온라인으로 이동 및 비즈니스용 [Skype](decommission-remove-on-prem.md) 서버 제거에서 비즈니스용 Skype 서버 배포를 제거하기 위한 추가 단계를 참조하세요.


## <a name="see-also"></a>참고 항목

- [Teams 및 비즈니스용 Skype를 위한 클라우드 통합](cloud-consolidation.md)

- [온-프레미스 비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

