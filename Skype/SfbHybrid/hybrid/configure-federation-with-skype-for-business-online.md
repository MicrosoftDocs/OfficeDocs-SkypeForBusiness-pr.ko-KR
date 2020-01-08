---
title: 비즈니스용 Skype 하이브리드 구성하기
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: '요약: 온-프레미스 배포와 비즈니스용 Skype Online 간의 상호 운용성을 구성 하는 방법을 알아봅니다.'
ms.openlocfilehash: c451224e7f421b4505560533b2880a14cc04e1a9
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963037"
---
# <a name="configure-skype-for-business-hybrid"></a>비즈니스용 Skype 하이브리드 구성하기

비즈니스용 Skype 하이브리드를 구성하기 위해서는 다음 작업을 수행해야 합니다.

- [Office 365와 페더레이션 할 온-프레미스 환경 서비스를 구성](#configure-your-on-premises-edge-service-to-federate-with-office-365)합니다.
- [Office 365을 신뢰 하도록 온-프레미스 환경을 구성 하 고 office 365와 공유 SIP 주소 공간을 사용 하도록 설정](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365)합니다.
- [Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정](#enable-shared-sip-address-space-in-your-office-365-tenant)합니다.

Exchange 온-프레미스를 사용 하는 경우 Exchange 온-프레미스 및 비즈니스용 Skype 온라인 환경 간에 OAuth를 구성할 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버에서 서버 간 인증 관리](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) 및 [비즈니스용 skype 및 Exchange 통합 계획](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)을 참조 하세요. 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Office 365와 페더레이션 할 온-프레미스에 지 서비스 구성

페더레이션을 사용 하면 온-프레미스 배포의 사용자가 조직의 Office 365 사용자와 통신할 수 있습니다. 페더레이션을 구성 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 cmdlet을 실행 합니다.
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

'-EnablePartnerDiscovery ' 값이 1로 설정 된 경우 비즈니스용 Skype 서버는 DNS 레코드를 사용 하 여 AllowedDomains 목록에 나열 되지 않은 파트너 도메인을 검색 합니다. 값이 0으로 설정 되 면 비즈니스용 Skype 서버가 AllowedDomains 목록에 있는 도메인과만 페더레이션 합니다. 이 매개 변수는 DNS 서비스 라우팅을 사용하는 경우에 필요합니다.



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Office 365에서 공유 SIP 주소 공간을 사용 하도록 온-프레미스 환경을 구성 합니다.

또한 Office 365를 신뢰하고 Office 365와 공유 SIP 주소 공간을 사용하도록 온-프레미스 환경을 구성해야 합니다. 즉, Office 365은 온-프레미스 환경과 동일한 SIP 도메인 집합에 대해 사용자 계정을 잠재적으로 호스트할 수 있으며, 메시지를 온-프레미스와 온라인으로 호스트 되는 사용자 간에 라우팅할 수 있습니다.  아래 설명 된 대로 ProxyFqdn = sipfed.online.lync.com>을 사용 하 여 호스팅 공급자를 구성 하 여이 작업을 수행 합니다.

먼저 ProxyFqdn = sipfed.online.lync.com>을 사용 하는 호스팅 공급자가 이미 있는지 확인 합니다. 하나가 있으면 다음 명령을 사용 하 여 제거 합니다.

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

그런 다음 새 호스팅 공급자를 만들려면 다음과 같이 새-CsHostingProvider cmdlet을 사용 합니다. 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정
  
온-프레미스 배포에서 수행한 변경 사항 외에도 Office 365 테 넌 트에서 해당 변경 사항을 사용 하 여 온-프레미스 배포와 공유 SIP 주소 공간을 설정 해야 합니다.  

Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정 하려면 비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정한 후 다음 cmdlet을 실행 합니다.
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 특성은 온라인으로 전환할 때까지 "True"로 유지 되어야 하며, 사용자는 온-프레미스에 남아 있지 않습니다. 
  
팀 또는 비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정 하려면 먼저 비즈니스용 Skype Online 커넥터 모듈 for Windows PowerShell을 설치 해야 [합니다.](https://go.microsoft.com/fwlink/p/?LinkId=391911)
  
모듈을 설치한 후에는 다음 cmdlet을 사용 하 여 원격 세션을 설정할 수 있습니다.
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

비즈니스용 Skype Online에서 원격 PowerShell 세션을 설정 하는 방법과 비즈니스용 Skype Online 커넥터 모듈을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell에 대 한 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.
  


## <a name="see-also"></a>참고 항목

[새-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

