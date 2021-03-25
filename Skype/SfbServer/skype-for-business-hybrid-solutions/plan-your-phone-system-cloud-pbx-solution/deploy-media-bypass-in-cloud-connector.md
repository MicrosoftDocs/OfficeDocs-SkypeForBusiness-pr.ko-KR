---
title: 클라우드 커넥터 버전에서 미디어 우회 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 이 항목을 통해 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 배포하는 단계에 대해 자세히 알아보십시오.
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119367"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>클라우드 커넥터 버전에서 미디어 우회 배포
 
> [!Important]
> Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)

이 항목을 통해 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 배포하는 단계에 대해 자세히 알아보십시오. 
  
미디어 우회를 통해 클라이언트는 PSTN(Public Switched Telephone Network) 다음 홉(게이트웨이 또는 SBC(Session Border Controller))으로 직접 미디어를 보내고 미디어 경로에서 Cloud Connector Edition 구성 요소를 제거할 수 있습니다. Cloud [Connector Edition의 미디어 우회 계획을 참조합니다.](plan-for-media-bypass-in-cloud-connector-edition.md)
  
## <a name="enable-media-bypass"></a>미디어 바이패스 사용

미디어 우회를 사용하도록 설정하려면 미디어 우회 웹 서비스의 DNS 이름을 구성하고 테넌트 구성에서 미디어 우회를 설정해야 합니다. 미디어 우회 웹 서비스는 모든 중재 서버에 자동으로 배포됩니다. 테넌트 관리자는 하이브리드 음성 서비스(사이트)의 이름을 선택해야 합니다. 이 이름은 하이브리드 음성에 등록된 SIP 도메인에서 제공되어야 합니다. 서비스 이름은 클라이언트 위치에 관계없이 모든 클라우드 커넥터 어플라이언스 및 모든 PSTN 사이트에서 동일해야 합니다. 웹 서비스는 네트워크에서 내부적으로만 사용할 수 있습니다.
  
테넌트 관리자는 내부 프로덕션 Active Directory에서 DNS A 레코드를 구성해야 합니다. 복잡한 다중 사이트 환경이 있는 경우 예제: 복잡한 다중 사이트 환경의 미디어 우회 웹 [사이트 DNS 레코드를 참조하세요.](deploy-media-bypass-in-cloud-connector.md#Example) DNS 레코드는 내부 네트워크 클라이언트에 한해 확인해야 합니다. 외부 네트워크 클라이언트에 대해 확인하면 안 됩니다.
  
DNS를 구성한 후 비즈니스용 Skype 관리자 자격 증명과 함께 원격 PowerShell을 사용하여 비즈니스용 Skype Online에 연결합니다. 자세한 내용은 [Set up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
PowerShell 세션에서 미디어 우회를 사용하도록 설정하려면 다음 명령을 입력합니다.
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

미디어 우회를 사용하도록 설정하는 과정은 2단계 프로세스입니다. 이 New-CsNetworkMedia 새 구성을 즉시 저장하지는 않습니다. 메모리에 설정만 만듭니다. 이 cmdlet에서 만든 개체는 변수에 저장한 다음 네트워크 구성의 MediaBypassSettings 속성에 할당해야 합니다. 자세한 내용은 예: 복잡한 다중 사이트 환경에서 미디어 우회 웹 사이트 [DNS 레코드를 참조하세요.](deploy-media-bypass-in-cloud-connector.md#Example)
  
프레미스 구성 요소와 온라인 구성 요소 간의 복제에는 최대 24시간이 걸릴 수 있으므로 사용자를 사용하도록 설정하기 전에 필요한 명령을 실행하는 것이 좋습니다.
  
## <a name="confirm-media-bypass-settings"></a>미디어 우회 설정 확인

미디어 우회 설정을 다음과 같이 확인할 수 있습니다. 
  
테넌트 풀에 대한 온라인 복제를 확인하기 위해 원격 PowerShell에서 다음 명령을 실행합니다.
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

클라우드 커넥터 중재 서버에 연결하고 PowerShell에서 다음 명령을 실행하여 Enabled=True 및 AlwaysBypass=True를 확인한 다음, 사내 복제를 확인합니다.
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

클라이언트 설정을 확인하려면 비즈니스용 Skype 클라이언트에서 로그인하고 다시 로그인하고 클라이언트가 다음과 같이 서비스 URL을 수신한지 확인합니다.
  
1. %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog를 열 수 있습니다. 
    
2. hybridconfigserviceinternalurl을 검색하고 URL이 정의한 URL과 일치하는지 확인합니다.
    
## <a name="change-media-bypass-parameters"></a>미디어 우회 매개 변수 변경

테넌트 관리자는 다음 cmdlet을 실행하여 웹 서비스의 DNS 이름을 변경할 수 있습니다.
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> 클라이언트는 새 서비스 이름을 입력하고 변경을 인식하려면 로그인하여 로그인해야 합니다. 
  
## <a name="temporarily-disable-media-bypass"></a>미디어 우회를 일시적으로 사용하지 않도록 설정

이 시나리오는 문제 해결 또는 유지 관리에 유용할 수 있습니다. 서비스를 사용하지 않도록 설정하기 위해 다음 cmdlet을 실행합니다.
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

변경한 후 변경 내용을 모든 클라우드 커넥터에 복제하는 데 다소 시간이 걸릴 수 있습니다. 복제 상태를 확인하기 위해 클라우드 커넥터 중재 서버의 PowerShell에서 다음 cmdlet을 실행합니다. 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

변경 내용이 복제된 후 중재 서버의 웹 서비스가 미디어 우회 서비스에 대한 클라이언트 요청을 거부하기 시작하게 됩니다.
  
## <a name="disable-media-bypass-permanently"></a>미디어 우회를 영구적으로 사용하지 않도록 설정

미디어 우회를 영구적으로 사용하지 않도록 설정하기 위해 테넌트 관리자는 다음 명령을 실행해야 합니다. 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

관리자는 또한 내부 DNS 서버에서 미디어 우회에 대한 웹 주소를 제거해야 합니다. 변경한 후 변경 내용을 모든 클라우드 커넥터 어플라이언스에 복제하는 데 다소 시간이 걸릴 수 있습니다. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>예: 복잡한 다중 사이트 환경에서 미디어 우회 웹 사이트 DNS 레코드
<a name="Example"> </a>

클라이언트는 내부 DNS 서버에서 미디어 우회 웹 서비스의 웹 주소를 받게 됩니다. 웹 서비스의 이름은 모든 클라우드 커넥터 어플라이언스 및 클라우드 커넥터 PSTN 사이트에서 동일합니다. 복잡한 다중 사이트 환경에서는 클라이언트를 네트워크의 로컬 웹 서비스로 리디렉션할 수 있도록 Geo-Location 기반 트래픽 관리에 Windows 2016 DNS 정책을 사용하는 것이 좋습니다. 
  
Windows 2016 DNS 정책에 대한 자세한 내용은 [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers을 참조하십시오.](/windows-server/networking/dns/deploy/primary-geo-location)
  
다음은 Windows 2016 DNS 정책을 사용하여 사이트가 여러 개 있는 회사의 구성 예입니다Geo-Location 기반 트래픽 관리.
  
우회 서비스의 이름은 'hybridvoice.adatum.biz.'입니다.
  
암스테르담 사이트에는 다음 중재 서버 IP 주소와 함께 배포된 4개의 클라우드 커넥터 어플라이언스가 있습니다.
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
시애틀의 사이트에는 다음 중재 서버 IP 주소와 함께 배포된 3개의 클라우드 커넥터 어플라이언스가 있습니다.
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Geo-Location 기반 트래픽 관리를 사용하는 경우 DNS 서버는 다음과 같이 구성됩니다.
  
1. 암스테르담 및 시애틀 서브넷 모두에 대한 DNS 클라이언트 서브넷을 생성합니다.
    
2. 암스테르담 및 시애틀에 adatum.biz DNS 영역 범위를 만들 수 있습니다.
    
3. 각 DNS 영역 범위에서 DNS 레코드를 생성합니다.
    
    암스테르담
    
   - A를 입력합니다.
    
   - 이름 : adatum.biz DNS 영역의 hybridvoice
    
   - 대상: 192.168.1.45
    
     추가 중재 서버에 대한 추가 레코드 만들기
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     시애틀
    
   - A 입력
    
   - 이름 : adatum.biz DNS 영역의 hybridvoice
    
   - 대상: 10.10.1.8
    
     추가 중재 서버에 대한 추가 레코드 만들기
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. 클라이언트 서브넷을 적절한 영역 범위에 연결하는 DNS 정책을 만들어 원하는 DNS 확인을 보장합니다.
    
이때 클라이언트가 암스테르담 서브넷에서 DNS 쿼리를 hybridvoice.adatum.biz 192.168.1.45가 반환됩니다. 192.168.1.46, 192.168.1.47 및 192.168.1.48 주소가 있는 반면 시애틀에서 동일한 쿼리 양식을 만드는 클라이언트는 10.10.1.8, 10.10.1.9 및 10.10.1.10을 반환합니다.

> [!NOTE]
> CCE 어플라이언스가 업데이트된 설정을 받고 있는 것 같지 않은 경우 어플라이언스가 원격 PowerShell을 통해 테넌트에 연락할 수 있는지 확인합니다. 원격 PowerShell을 사용하여 응용 Get-CsHybridPSTNAppliance 상태 확인 또는 CCE 호스트의 PowerShell을 사용하여 Get-CcApplianceStatus의 상태를 확인할 수 있습니다.

  
## <a name="see-also"></a>참고 항목
<a name="Example"> </a>

[클라우드 커넥터 버전에서 미디어 바이패스 계획](plan-for-media-bypass-in-cloud-connector-edition.md)