---
title: 비즈니스용 Skype 하이브리드 구성하기
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 사내 배포와 비즈니스용 Skype Online 간의 상호 연동성을 구성하는 방법을 설명합니다.'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569220"
---
# <a name="configure-skype-for-business-hybrid"></a>비즈니스용 Skype 하이브리드 구성하기

비즈니스용 Skype 하이브리드를 구성하기 위해서는 다음 작업을 수행해야 합니다.

- [Microsoft 365 또는 Office 365와 페더에 연결하도록](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)프레미스 에지 서비스를 구성합니다.
- [Microsoft 365 또는 Office 365를](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)신뢰하고 공유 SIP 주소 공간을 사용하도록 사내 환경을 구성합니다.
- [Microsoft 365 또는 Office 365](#enable-shared-sip-address-space-in-your-organization)조직에서 공유 SIP 주소 공간을 사용하도록 설정

Exchange온-프레미스가 있는 경우 Exchange온-프레미스와 비즈니스용 Skype Online 환경 간에 OAuth를 구성할 수 있습니다. 자세한 내용은 [비즈니스용 Skype](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) 서버에서 서버 대 서버 인증 관리 및 비즈니스용 Skype 및 Exchange 통합 계획을 [참조하세요.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365와 페더에 연결하도록 프레미스 에지 서비스 구성

페더ation을 사용하면 조직의 Microsoft 365 또는 Office 365 사용자와의 통신을 프레미스 배포의 사용자가 사용할 수 있습니다. 페더전을 구성하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행합니다.
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

'-EnablePartnerDiscovery' 값을 $True 경우 비즈니스용 Skype 서버는 DNS 레코드를 사용하여 AllowedDomains 목록에 나열되지 않은 파트너 도메인을 검색합니다. 이 값을 $False 경우 비즈니스용 Skype 서버는 AllowedDomains 목록에 있는 도메인과만 페더러입니다. 이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다.

> [!NOTE]
> 비즈니스용 Skype 배포 사용자와 비즈니스용 Skype Online 조직의 사용자 간에 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 [비즈니스용 Skype](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)서버에서 비즈니스용 Skype Online 고객에 대한 페더링 지원 구성을 참조하세요.


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365와의 공유 SIP 주소 공간을 사용하도록 사내 환경 구성

또한 Microsoft 365 또는 Office 365를 신뢰하고 공유 SIP 주소 공간을 사용하도록 사내 환경을 구성해야 합니다. 즉, Microsoft 365 또는 Office 365는 잠재적으로 사용자 계정을 사내 환경과 동일한 SIP 도메인 집합에 호스트할 수 있으며, 메시지는 프레미스에서 호스트된 사용자와 온라인 사용자 간에 라우팅될 수 있습니다.  아래 설명된 바와 같이 ProxyFqdn=sipfed.online.lync.com을 사용하여 호스팅 공급자를 구성하면 됩니다.

먼저 ProxyFqdn=sipfed.online.lync.com을 사용하는 호스팅 공급자가 이미 있는지 확인하십시오. 이 명령이 있는 경우 다음 명령을 사용하여 제거합니다.

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

그런 다음 새 호스팅 공급자를 만들고 다음과 New-CsHostingProvider cmdlet을 사용합니다. 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>조직에서 공유 SIP 주소 공간 사용
  
Microsoft 365 또는 Office 365 조직에서 변경한 변경 외에도, Microsoft 365 또는 Office 365 조직에서 해당 변경을 통해 공유 SIP 주소 공간을 사내 배포와 함께 사용하도록 설정해야 합니다.  

조직에서 공유 SIP 주소 공간을 사용하도록 설정하려면 비즈니스용 Skype Online을 사용하여 원격 PowerShell 세션을 설정한 후 다음 cmdlet을 실행합니다.
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 특성은 온라인으로의 이동이 최종적으로 진행될 때까지 "True"로 유지해야 합니다. 
  
Teams 또는 비즈니스용 Skype Online과 원격 PowerShell 세션을 설정하려면 먼저 [Teams PowerShell 모듈을 설치해야 합니다.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
  
모듈을 설치한 후 다음 cmdlet을 사용하여 원격 세션을 설정할 수 있습니다.
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

비즈니스용 Skype Online을 사용하여 원격 PowerShell 세션을 설정하는 방법 및 비즈니스용 Skype Online 커넥터 모듈을 사용하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  


## <a name="see-also"></a>기타 참고 항목

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
