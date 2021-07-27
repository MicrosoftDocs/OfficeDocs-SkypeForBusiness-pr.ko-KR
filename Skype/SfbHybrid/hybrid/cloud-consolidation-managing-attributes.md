---
title: 제거 후 특성을 관리하는 방법 결정
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
description: 이 문서에서는 프레미스 환경을 해제한 후 특성을 관리하는 방법에 대해 설명하고 있습니다.
ms.openlocfilehash: d8c61e1a5a76206cadd8ab4ae3ed51de77badc74
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510649"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>제거 후 특성을 관리하는 방법 결정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


기본적으로 이전에 비즈니스용 Skype 서버 사용하도록 설정되어 클라우드로 이동한 모든 사용자는 여전히 msRTCSIP 특성을 사내 Active Directory에 구성합니다. 

이러한 특성, 특히 sip 주소(msRTCSIP-PrimaryUserAddress) 및 잠재적으로 전화 번호(msRTCSIP-Line)는 Azure AD에 계속 동기화합니다. msRTCSIP 특성 중 어느 것이든 변경해야 하는 경우 이러한 변경 내용은 On-premises Active Directory에서 적용한 다음 Azure AD와 동기화해야 합니다. 그러나 비즈니스용 Skype 서버 배포가 제거되면 비즈니스용 Skype 서버 도구를 사용하여 이러한 특성을 관리할 수 없습니다.

이 상황을 처리하는 두 가지 옵션을 사용할 수 있습니다.

1. 서버 계정에 대해 사용하도록 설정된 비즈니스용 Skype 그대로 두고 Active Directory 도구를 사용하여 msRTCSIP 특성을 관리합니다. 이렇게 하면 마이그레이션된 사용자의 서비스가 손실되지 않고, 전체 해제 없이 서버를 제거하여 비즈니스용 Skype 서버 배포를 쉽게 제거할 수 있습니다. 그러나 새로 라이선스가 부여된 사용자는 이러한 특성을 On-premises Active Directory에 채우지 못하며 온라인에서 관리해야 합니다.

2.  모든 msRTCSIP 특성을 모든 msRTCSIP 특성의 선택을 취소하고 온라인 도구를 사용하여 이러한 특성을 관리합니다. 이 방법을 사용하면 기존 사용자와 새 사용자에 대해 일관된 관리 방식을 사용할 수 있습니다. 그러나 잠재적으로는 사내 해제 프로세스 중에 서비스가 일시적으로 손실될 수 있습니다.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>방법 1 - Active Directory에서 사용자의 sip 주소 및 전화 번호 관리

관리자는 사내 배포가 해제된 후에도 이전에 비즈니스용 Skype 서버 이동된 사용자를 관리할 수 있습니다. 

사용자의 sip 주소 또는 사용자의 전화 번호(및 sip 주소 또는 전화 번호에 이미 On-premises Active Directory에 값이 있는 경우)를 변경하려는 경우, 이 작업을 On-premises Active Directory에서 이 작업을 하고 값이 Azure AD로 흐르게 해야 합니다. 이 경우 프레미스 액세스가 필요하지 비즈니스용 Skype 서버. 대신, Active Directory 사용자 및 컴퓨터 MMC 스냅인(아래 그림과 같이)을 사용하거나 PowerShell을 사용하여 이러한 특성을 On-premises Active Directory에서 직접 수정할 수 있습니다. MMC 스냅인을 사용하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭한 후 수정할 적절한 특성을 찾아야 합니다.

- 사용자의 sip 주소를 수정하려면 를 `msRTCSIP-PrimaryUserAddress` 수정합니다.

    > [!NOTE]
    > 특성에 sip 주소가 포함되어 있는 경우 해당 값을 모범 사례로 `ProxyAddresses` 업데이트합니다. 의 sip 주소가 채워진 경우 O365에서 무시해도 다른 사내 구성 요소에서 사용할 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 수 있습니다.

- 사용자의 전화 번호를 수정하려면 값이 이미 있는 경우 `msRTCSIP-Line` *수정합니다.*

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
-  사용자가 이동하기 전에 원래의 On-premises 값이 없는 경우 비즈니스용 Skype Online PowerShell 모듈의 `msRTCSIP-Line` `onpremLineUri` [Set-CsUser cmdlet에서](/powershell/module/skype/set-csuser?view=skype-ps) - 매개 변수를 사용하여 전화 번호를 수정할 수 있습니다.

하이브리드를 사용하지 않도록 설정한 후 새로 만든 사용자는 이러한 단계를 수행하지 않고 클라우드에서 직접 관리할 수 있습니다. 이러한 방법과 msRTCSIP 특성을 모두 사용하는 것뿐만 아니라 이러한 방법을 사용하는 것이 편한 경우, 단순히 해당 서버에 대한 이미지를 다시 비즈니스용 Skype 있습니다. 그러나 모든 msRTCSIP 특성을 지우고 기존 비즈니스용 Skype 서버 방법 2를 사용합니다.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>방법 2 - Active Directory의 비즈니스용 Skype 사용자에 대한 속성 지우기

이 옵션을 사용하려면 이전에 사내에서 클라우드로 이동한 사용자를 다시 프로비전해야 비즈니스용 Skype 서버 추가 작업과 적절한 계획이 필요합니다. 이러한 사용자는 두 가지 범주, 두 가지 범주로 분류될 수 있습니다. 전화 시스템 없는 사용자와 사용자가 전화 시스템. 사용자가 전화 시스템 전화 번호를 클라우드로 관리하는 동안 전화 번호가 일시적으로 손실됩니다. **대량 사용자 작업을 시작하기 전에 소수의 사용자와 관련된 파일럿을 전화 시스템 것이 좋습니다.** 대규모 배포의 경우 사용자는 서로 다른 시간 창의 소규모 그룹에서 처리될 수 있습니다. 

> [!NOTE] 
> 이 프로세스는 일치하는 sip 주소와 UserPrincipalName이 있는 사용자에게 가장 간단합니다. 이러한 두 특성에서 일치하지 않는 값이 있는 사용자가 있는 조직의 경우 원활한 전환을 위해 아래에서 설명한에 따라 특히 주의해야 합니다.

> [!NOTE]
> 자동 전화 걸기 또는 통화 큐에 대해 사내 하이브리드 응용 프로그램 끝점을 구성한 경우 이러한 끝점을 해제하기 전에 Microsoft 365 끝점을 비즈니스용 Skype 서버.


1. PowerShell cmdlet이 빈 비즈니스용 Skype 반환하는 다음의 사내 프레미스를 확인 합니다. 비어 있는 결과는 사용자가 모든 사용자가 사내에 있거나 해당 위치로 이동되거나 Microsoft 365 수 없음을 의미합니다.

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 다음의 PowerShell cmdlet을 실행하여 사용자 데이터를 내보낼 수 있도록 다음 비즈니스용 Skype 서버 실행하여 사용자의 현재 전화 번호(LineUri), UserPrincipalName 및 관련 정보를 기록합니다.

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

4. 업데이트할 준비가 된 비즈니스용 Skype 서버 Active Directory에서 사용자와 관련된 특성 정보를 삭제합니다.  아래와 같이 이 프로세스에는 2단계가 있습니다.

   > [!Important] 
   > 이 단계를 실행한 후 다음 AAD Sync 주기가 전화 시스템 이전에 클라우드로 이동한 비즈니스용 Skype 서버 있는 사용자는 8단계가 성공적으로 완료되고 9단계에서 확인될 때까지 전화를 걸고 받을 수 없습니다. 또한 해당 단계에 해당 정보가 필요하기 때문에 2단계에 따라 사용자의 전화 번호 및 관련 정보를 저장해야 합니다.

 
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

5. cmdlet에 대해 다음의 Windows PowerShell Active Directory 모듈을 실행하여 sip 주소 값을 다시 on-premises Active Directory proxyAddresses에 추가합니다. 이렇게 하면 이 특성을 사용 하는 상호 연산 문제가 방지 됩니다. 

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

6. 실행 Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. 사용자 프로비전이 완료될 때까지 기다렸다가 다음 온라인 PowerShell 명령을 실행하여 사용자 프로비전 비즈니스용 Skype 수 있습니다. 다음 비즈니스용 Skype 온라인 PowerShell 명령은 프로세스가 완료되는 즉시 빈 결과를 반환합니다.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. 다음 온라인 비즈니스용 Skype PowerShell 명령을 실행하여 전화 번호를 할당하고 사용자가 전화 번호를 사용하도록 전화 시스템.
     
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
   >  끝점이 비즈니스용 Skype(Skype 또는 제3자 전화)가 있는 경우 -HostedVoiceMail을 $true. 조직에서 음성 사용이 가능한 Teams 끝점만 사용하는 경우 이 설정은 사용자에게 적용되지 않습니다. 

9. 전화 시스템 기능이 올바르게 프로비전되어 있는지 확인합니다. 다음 비즈니스용 Skype 온라인 PowerShell 명령은 프로세스가 완료되는 즉시 빈 결과를 반환합니다.

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

    On-premises 비즈니스용 Skype 서버 On-premises PowerShell command:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    비즈니스용 Skype 온라인 PowerShell 명령:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. 방법 2의 모든 단계를 완료한 [](decommission-move-on-prem-endpoints.md) 후 하이브리드 응용 프로그램 끝점 이동을 [](decommission-remove-on-prem.md) 온라인으로 이동 및 비즈니스용 Skype 서버 배포를 제거하기 위한 추가 단계를 비즈니스용 Skype 서버 단계를 참조하세요.


## <a name="see-also"></a>참고 항목

- [비즈니스 및 Teams 클라우드 비즈니스용 Skype](cloud-consolidation.md)

- [온-프레미스 비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

