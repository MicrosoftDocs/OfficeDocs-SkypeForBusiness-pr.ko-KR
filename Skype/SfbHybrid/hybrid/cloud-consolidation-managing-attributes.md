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
ms.localizationpriority: medium
description: 이 문서에서는 온-프레미스 환경을 서비스 해제한 후 특성을 관리하는 방법을 설명합니다.
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249020"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>제거 후 특성을 관리하는 방법 결정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


기본적으로 비즈니스용 Skype 서버 사용하도록 설정한 다음 클라우드로 이동한 모든 사용자는 여전히 온-프레미스 Active Directory msRTCSIP 특성을 구성합니다. 

이러한 특성, 특히 sip 주소(msRTCSIP-PrimaryUserAddress) 및 전화 번호(msRTCSIP-Line)는 계속해서 Azure AD 동기화됩니다. msRTCSIP 특성을 변경해야 하는 경우 온-프레미스 Active Directory 이러한 변경 내용을 수행한 다음 동기화하여 Azure AD. 그러나 비즈니스용 Skype 서버 배포가 제거되면 비즈니스용 Skype 서버 도구를 사용하여 이러한 특성을 관리할 수 없습니다.

이 상황을 처리하는 데 사용할 수 있는 두 가지 옵션이 있습니다.

1. 비즈니스용 Skype 서버 계정에 대해 사용하도록 설정된 사용자를 있는 그대로 두고 Active Directory 도구를 사용하여 msRTCSIP 특성을 관리합니다. 이 메서드는 마이그레이션된 사용자에 대한 서비스 손실을 방지하고 전체 서비스 해제 없이 서버를 제거(예: 초기화)하여 비즈니스용 Skype 서버 배포를 제거할 수 있도록 합니다. 그러나 새로 라이선스가 부여된 사용자에게는 이러한 특성이 온-프레미스 Active Directory 채워지지 않으므로 온라인으로 관리해야 합니다.

2.  온-프레미스 Active Directory 마이그레이션된 사용자의 모든 msRTCSIP 특성을 지우고 온라인 도구를 사용하여 이러한 특성을 관리합니다. 이 방법을 사용하면 기존 사용자와 새 사용자에 대해 일관된 관리 접근 방식을 사용할 수 있습니다. 그러나 온-프레미스 서비스 해제 프로세스 중에 일시적으로 서비스가 손실될 수 있습니다.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>방법 1 - Active Directory에서 사용자의 sip 주소 및 전화 번호 관리

관리자는 온-프레미스 배포가 서비스 해제된 후에도 온-프레미스 비즈니스용 Skype 서버 클라우드로 이동한 사용자를 관리할 수 있습니다. 

사용자의 sip 주소 또는 사용자의 전화 번호를 변경하려는 경우(sip 주소 또는 전화 번호에 이미 온-프레미스 Active Directory 값이 있음) 온-프레미스 Active Directory 변경하고 값이 Azure AD 흐를 수 있도록 해야 합니다. 이 메서드는 온-프레미스 비즈니스용 Skype 서버 필요하지 않습니다. 대신 아래와 같이 Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용하거나 PowerShell을 사용하여 온-프레미스 Active Directory 직접 이러한 특성을 수정할 수 있습니다. MMC 스냅인을 사용하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭하고 수정할 적절한 특성을 찾습니다.

- 사용자의 sip 주소를 `msRTCSIP-PrimaryUserAddress`수정하려면 .

    > [!NOTE]
    > 특성에 `ProxyAddresses` sip 주소가 포함된 경우 해당 값을 모범 사례로 업데이트합니다. 채워진 경우 `msRTCSIP-PrimaryUserAddress` O365에서 `ProxyAddresses` sip 주소를 무시하지만 다른 온-프레미스 구성 요소에서 사용할 수 있습니다.

- 사용자의 전화 번호를 수정하려면 *이미 값이 있는지* 수정 `msRTCSIP-Line` 합니다.

  ![Active Directory 사용자 및 컴퓨터 도구.](../media/disable-hybrid-1.png)


- 사용자가 이동하기 전에 원래 온-프레미스에 대한 `msRTCSIP-Line` 값이 없는 경우 Teams PowerShell 모듈의 [Set-CsPhoneNumberAssignment cmdlet](/powershell/module/teams/set-csphonenumberassignment)에서 매개 변수를 사용하여 `-PhoneNumber` 전화 번호를 수정할 수 있습니다.

하이브리드를 사용하지 않도록 설정한 후에 만든 새 사용자에게는 이러한 단계가 필요하지 않으며 해당 사용자는 클라우드에서 직접 관리할 수 있습니다. 이러한 메서드를 혼합하여 msRTCSIP 특성을 온-프레미스 Active Directory 그대로 두는 것이 편한 경우 온-프레미스 비즈니스용 Skype 서버를 다시 이미지화할 수 있습니다. 그러나 모든 msRTCSIP 특성을 지우고 기존 비즈니스용 Skype 서버 제거하려는 경우 메서드 2를 사용합니다.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>방법 2 - Active Directory의 모든 온-프레미스 사용자에 대한 비즈니스용 Skype 특성 지우기

온-프레미스 비즈니스용 Skype 서버 클라우드로 이동한 사용자를 다시 프로비전해야 하므로 이 옵션을 사용하려면 더 많은 노력과 적절한 계획이 필요합니다. 이러한 사용자는 전화 시스템 없는 사용자와 전화 시스템 있는 사용자라는 두 가지 범주로 분류할 수 있습니다. 전화 시스템 있는 사용자는 전화 번호가 온-프레미스 Active Directory 관리되는 것을 클라우드로 전환하는 과정의 일환으로 일시적으로 전화 서비스가 손실됩니다. **대량 사용자 작업을 시작하기 전에 소수의 사용자가 전화 시스템 파일럿을 수행하는 것이 좋습니다.** 대규모 배포의 경우 사용자는 다른 시간 창의 작은 그룹에서 처리할 수 있습니다. 

> [!NOTE] 
> 이 프로세스는 일치하는 sip 주소와 UserPrincipalName이 있는 사용자에게 가장 간단합니다. 이러한 두 특성에서 일치하지 않는 값을 가진 사용자가 있는 조직의 경우 원활한 전환을 위해 아래와 같이 각별한 주의를 기울여야 합니다.

> [!NOTE]
> 자동 전화 교환 또는 통화 큐에 대한 온-프레미스 하이브리드 애플리케이션 엔드포인트를 구성한 경우 비즈니스용 Skype 서버 서비스 해제하기 전에 이러한 엔드포인트를 Microsoft 365 이동해야 합니다. 자세한 내용은 [온-프레미스 환경을 서비스 해제하기 전에 하이브리드 애플리케이션 엔드포인트 마이그레이션을 참조하세요](decommission-move-on-prem-endpoints.md).  


1. 다음 온-프레미스 비즈니스용 Skype PowerShell cmdlet이 빈 결과를 반환하는지 확인합니다. 빈 결과는 사용자가 온-프레미스에 있고 Microsoft 365 이동되었거나 사용하지 않도록 설정된 사용자가 없음을 의미합니다.

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. 다음 온-프레미스 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 사용자 데이터를 내보내어 사용자의 현재 전화 번호(LineUri), UserPrincipalName 및 관련 정보를 기록합니다.

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > 계속하기 전에 SfbUserSettings.csv 파일을 열고 모든 사용자 데이터가 성공적으로 내보내졌는지 확인합니다. 이 파일의 복사본을 유지하는 것이 좋습니다.  사용자를 처리하기 위해 다음 단계에서 이 파일을 사용하지 마세요. 

3. 다음 단계에서 사용할 사용자 그룹이 있는 파일을 만듭니다. 첫 번째 사용자 그룹이 성공적으로 완료되면 다음 사용자 그룹을 진행합니다. 아래 예제에서는 사용자 그룹이 사전순으로 선택됩니다. 사용자를 처리하려는 방법과 일치하는 조건에 따라 사용자를 필터링할 수 있습니다.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > SfbUsers.csv 파일을 열고 사용자 데이터가 성공적으로 내보내졌는지 확인하기 전에 이후 단계에서 이 파일의 LineUri(전화 번호), UserPrincipalName, SamAccountName 및 SipAddress가 필요합니다.

4. 업데이트할 준비가 된 사용자 집합에 대한 active Directory에서 비즈니스용 Skype 서버 관련된 특성 정보를 삭제합니다.  아래와 같이 이 프로세스에는 두 단계가 있습니다.

   > [!Important] 
   > 이 단계를 실행한 후 다음 AAD Sync 주기 후에 온-프레미스 비즈니스용 Skype 서버 클라우드로 이동한 전화 시스템 있는 사용자는 8단계가 성공적으로 완료되고 9단계에서 확인될 때까지 전화를 걸고 받을 수 있는 기능을 잃게 됩니다. 또한 해당 단계에 해당 정보가 필요하므로 2단계에 따라 사용자의 전화 번호 및 관련 정보를 저장했는지 확인합니다.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   그런 다음, 동일한 사용자 집합에 대해 온-프레미스 Active Directory PowerShell을 사용하여 msRTCSIP-DeploymentLocator의 값을 지웁

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. sip 주소 값을 온-프레미스 Active Directory proxyAddresses에 다시 추가하려면 Windows PowerShell cmdlet에 대해 다음 온-프레미스 Active Directory 모듈을 실행합니다. 이 작업은 이 특성에 의존하는 상호 운용성 문제를 방지합니다. 

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

6. Azure AD Sync 실행

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. 사용자 프로비저닝이 완료되기를 기다립니다. 다음 Teams PowerShell 명령을 실행하여 사용자 프로비전 진행률을 모니터링할 수 있습니다. 다음 Teams PowerShell 명령은 프로세스가 완료되는 즉시 빈 결과를 반환합니다.

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. 전화 번호를 할당하고 사용자가 전화 시스템 사용하도록 설정하려면 다음 Teams PowerShell 명령을 실행합니다.


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  비즈니스용 Skype 엔드포인트(Skype 클라이언트 또는 타사 휴대폰)가 있는 경우에도 -HostedVoiceMail을 $true 설정해야 합니다. 조직에서 음성 지원 사용자에 대해서만 Teams 엔드포인트를 사용하는 경우 이 설정은 사용자에게 적용되지 않습니다. 

9. 전화 시스템 기능이 있는 사용자가 올바르게 프로비전되었는지 확인합니다. 다음 Teams PowerShell 명령은 프로세스가 완료되는 즉시 빈 결과를 반환합니다.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. 모든 사용자가 처리될 때까지 3~9단계를 반복합니다.

11. 다음 두 PowerShell 명령을 실행하여 모든 사용자가 성공적으로 처리되었는지 확인합니다.

    온-프레미스 비즈니스용 Skype 서버 온-프레미스 PowerShell 명령:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell 명령:

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. 방법 2의 모든 단계를 완료한 후에는 [하이브리드 애플리케이션 엔드포인트를 온-프레미스에서 온라인으로 이동](decommission-move-on-prem-endpoints.md) 및 [온-프레미스 비즈니스용 Skype 서버 제거](decommission-remove-on-prem.md)를 참조하여 비즈니스용 Skype 서버 온-프레미스 배포를 제거하는 추가 단계를 참조하세요.


## <a name="see-also"></a>참고 항목

- [Teams 및 비즈니스용 Skype 대한 클라우드 통합](cloud-consolidation.md)

- [온-프레미스 비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

