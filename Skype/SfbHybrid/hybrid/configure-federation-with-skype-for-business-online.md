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
description: '요약: 프레미스 배포와 프레미스 배포 간의 상호 Teams.'
ms.openlocfilehash: a0e33c781e307785456698b20738dec2db02b8b4
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510559"
---
# <a name="configure-skype-for-business-hybrid"></a>비즈니스용 Skype 하이브리드 구성하기

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

비즈니스용 Skype 하이브리드를 구성하기 위해서는 다음 작업을 수행해야 합니다.

- [을(를) 페더에](#configure-your-on-premises-edge-service-to-federate-with-teams)연결하도록 프레미스 에지 서비스를 Teams.
- 공유 SIP 주소 공간을 사용하도록 Teams [구성합니다.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)
- [조직에서 공유 SIP 주소 공간을 Teams.](#enable-shared-sip-address-space-in-your-organization)

Exchange 있는 경우 Exchange 및 온라인 환경 간에 OAuth를 비즈니스용 Skype 수 있습니다. 자세한 내용은 [Manage server-to-server authentication in 비즈니스용 Skype 서버](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and Plan to integrate 비즈니스용 Skype and [Exchange.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>프레미스 에지 서비스에서 사용자와 페더러가 연결하도록 Teams

페더ation을 사용하면 조직 내 온라인 사용자 및 Teams 비즈니스용 Skype 사용자와 통신할 수 있습니다. 페더ation을 구성하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행합니다.
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

'-EnablePartnerDiscovery' 값이 $True 비즈니스용 Skype 서버 DNS 레코드를 사용하여 AllowedDomains 목록에 나열되지 않은 파트너 도메인을 검색합니다. 이 값을 0으로 $False 비즈니스용 Skype 서버 허용Domains 목록에 있는 도메인과만 페더화합니다. 이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다.

> [!NOTE]
> 프레미스 비즈니스용 Skype 배포의 사용자와 Microsoft 365 조직의 사용자 간에 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 Microsoft 365 고객에 대한 페더링 지원 구성을 [비즈니스용 Skype 서버.](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>프레미스 환경에서 공유 SIP 주소 공간을 사용하도록 Teams

또한 공유 SIP 주소 공간을 사용하도록 Teams 환경을 구성해야 합니다. 이 구성은 Teams 환경과 동일한 SIP 도메인 집합에 대한 사용자 계정을 잠재적으로 호스트할 수 있으며, 메시지를 프레미스 및 온라인에서 호스팅되는 사용자 간에 라우팅할 수 있습니다. 아래 설명된 바와 같이 ProxyFqdn=sipfed.online.lync.com을 사용하여 호스팅 공급자를 구성합니다.

먼저 ProxyFqdn=sipfed.online.lync.com을 사용하는 호스팅 공급자가 이미 있는지 확인하십시오. 하나만 있는 경우 관리 셸의 다음 명령을 사용하여 비즈니스용 Skype 서버 제거합니다.

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

그런 다음 다음과 같이 New-CsHostingProvider cmdlet을 사용하여 새 호스팅 공급자를 만들 수 있습니다. 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>조직에서 공유 SIP 주소 공간 사용
  
사내 배포에서 변경한 변경 외에도 Teams 조직에서 해당 변경을 통해 공유 SIP 주소 공간을 사용하도록 설정해야 합니다.  

조직에서 공유 SIP 주소 공간을 사용하도록 설정하려면 조직에서 원격 PowerShell 세션을 Teams 다음 cmdlet을 실행합니다.
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 특성은 온라인으로의 이동이 최종적으로 진행될 때까지 "True"로 유지해야 합니다. 
  
Teams(또는 비즈니스용 Skype Online)를 사용하여 원격 PowerShell 세션을 설정하려면 먼저 [PowerShell](/microsoftteams/teams-powershell-install)모듈 을 Teams 합니다. 이 Teams PowerShell 모듈은 사용 중지된 Busines Online 커넥터 모듈의 Skype 모듈을 대체합니다.
  
모듈을 설치한 후 다음 cmdlet을 사용하여 원격 세션을 설정할 수 있습니다.
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Teams 사용하여 원격 PowerShell 세션을 설정하는 방법 및 Teams PowerShell 모듈을 사용하는 방법에 대한 자세한 내용은 [Set up your computer for Windows PowerShell.](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  


## <a name="see-also"></a>참고 항목

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
