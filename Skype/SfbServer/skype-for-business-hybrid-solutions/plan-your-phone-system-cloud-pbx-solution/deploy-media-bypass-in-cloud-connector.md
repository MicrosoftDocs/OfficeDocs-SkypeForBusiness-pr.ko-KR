---
title: 클라우드 커넥터 에디션에 미디어 우회 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 이 항목에서는 클라우드 커넥터 버전 2.0 이상에서 미디어 바이패스를 배포 하는 단계에 대해 자세히 알아봅니다.
ms.openlocfilehash: 6f3ad140d25d5f1d03196e576ac57dc56e905d44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190851"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>클라우드 커넥터 에디션에 미디어 우회 배포
 
이 항목에서는 클라우드 커넥터 버전 2.0 이상에서 미디어 바이패스를 배포 하는 단계에 대해 자세히 알아봅니다. 
  
미디어 바이패스는 클라이언트가 PSTN (공용 전환 전화 네트워크) 다음 홉 인 게이트웨이 또는 세션 경계 컨트롤러 (SBC)로 직접 미디어를 보낼 수 있도록 하 고 미디어 경로에서 클라우드 커넥터 에디션 구성 요소를 제거 합니다. [클라우드 커넥터 에디션의 미디어 바이패스 계획](plan-for-media-bypass-in-cloud-connector-edition.md)을 참조 하세요.
  
## <a name="enable-media-bypass"></a>미디어 바이패스 사용

미디어 바이패스를 사용 하도록 설정 하려면 미디어 우회 웹 서비스의 DNS 이름을 구성 하 고 테 넌 트 구성에서 미디어 바이패스를 켜야 합니다. 미디어 우회 웹 서비스는 모든 중재 서버에 자동으로 배포 됩니다. 테 넌 트 관리자는 하이브리드 음성 서비스 (사이트)의 이름을 선택 해야 하며,이 이름은 하이브리드 음성에 대해 등록 된 SIP 도메인에서 가져와야 합니다. 서비스 이름은 클라이언트 위치에 관계 없이 모든 클라우드 커넥터 기기와 모든 PSTN 사이트에서 동일 해야 합니다. 웹 서비스는 네트워크 내부 에서만 사용할 수 있어야 합니다.
  
테 넌 트 관리자는 내부 프로덕션 Active Directory에서 DNS A 레코드를 구성 해야 합니다. 복잡 한 다중 사이트 환경이 있는 경우 예제 [: 복잡 한 다중 사이트 환경에서 미디어 우회 웹 사이트 DNS 레코드](deploy-media-bypass-in-cloud-connector.md#Example)를 참조 하세요. DNS 레코드는 내부 네트워크 클라이언트에 대해서만 확인 해야 합니다. 외부 네트워크 클라이언트에 대해 확인 하지 않아야 합니다.
  
DNS를 구성한 후 비즈니스용 skype 관리자 자격 증명을 사용 하 여 원격 PowerShell을 비즈니스용 Skype Online에 연결 합니다. 자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) 참조 하세요.
  
PowerShell 세션에서 다음 명령을 입력 하 여 미디어 바이패스를 사용 하도록 설정 합니다.
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

미디어 바이패스 사용은 두 단계로 진행 됩니다. 새로운 CsNetworkMedia cmdlet은 새 구성을 즉시 저장 하지 않습니다. 메모리 에서만 설정을 만들 수 있습니다. 이 cmdlet에서 만든 개체는 변수에 저장 한 다음 네트워크 구성의 Mediabyp이 설정 속성에 할당 해야 합니다. 자세한 내용은 [예제: 복잡 한 다중 사이트 환경에서 미디어 우회 웹 사이트 DNS 레코드](deploy-media-bypass-in-cloud-connector.md#Example)를 참조 하세요.
  
온-프레미스 및 온라인 구성 요소 간의 복제에는 최대 24 시간이 걸릴 수 있으므로 사용자를 사용 하도록 설정 하기 전에 필요한 명령을 실행 하는 것이 좋습니다.
  
## <a name="confirm-media-bypass-settings"></a>미디어 바이패스 설정 확인

다음과 같이 미디어 바이패스 설정을 확인할 수 있습니다. 
  
테 넌 트 풀로 온라인 복제를 확인 하려면 원격 PowerShell에서 다음 명령을 실행 합니다.
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

온-프레미스 복제를 확인 하려면 클라우드 커넥터 중재 서버에 연결 하 고 PowerShell에서 다음 명령을 실행 한 다음 Enabled = True 및 AlwaysBypass = True 인지 확인 합니다.
  
```
Get-CsNetworkConfiguration -LocalStore
```

클라이언트 설정을 확인 하려면 비즈니스용 Skype 클라이언트에서 로그 아웃 하 고 다시 로그인 하 여 클라이언트가 다음과 같이 서비스 URL을 받았는지 확인 합니다.
  
1. %Appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 열기 
    
2. Hybridconfigserviceinternalurl를 검색 하 고 URL이 정의한 것과 일치 하는지 확인 합니다.
    
## <a name="change-media-bypass-parameters"></a>미디어 무시 매개 변수 변경

테 넌 트 관리자는 다음 cmdlet을 실행 하 여 웹 서비스의 DNS 이름을 변경할 수 있습니다.
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> 클라이언트가 로그 아웃 하 고 로그인 해야 새 서비스 이름을 얻고 변경 내용을 인식할 수 있습니다. 
  
## <a name="temporarily-disable-media-bypass"></a>일시적으로 미디어 바이패스 사용 안 함

이 시나리오는 문제를 해결 하거나 유지 관리 하는 데 유용할 수 있습니다. 서비스를 사용 하지 않도록 설정 하려면 다음 cmdlet을 실행 합니다.
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

변경 후에는 변경 내용이 모든 클라우드 커넥터로 복제 되는 데 약간의 시간이 걸릴 수 있습니다. 복제 상태를 확인 하려면 클라우드 커넥터 중재 서버의 PowerShell에서 다음 cmdlet을 실행 합니다. 
  
```
Get- CsNetworkConfiguration -LocalStore
```

변경 내용이 복제 된 후 중재 서버의 웹 서비스는 미디어 바이패스 서비스에 대 한 클라이언트 요청 거부를 시작 합니다.
  
## <a name="disable-media-bypass-permanently"></a>미디어 우회를 영구적으로 사용 하지 않음

미디어 바이패스를 영구적으로 사용 하지 않도록 설정 하려면 테 넌 트 관리자가 다음 명령을 실행 해야 합니다. 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

또한 관리자는 내부 DNS 서버에서 미디어를 우회 하는 웹 주소도 제거 해야 합니다. 변경 후에는 변경 내용이 모든 클라우드 커넥터 기기에 복제 되는 데 약간의 시간이 걸릴 수 있습니다. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>예: 미디어 건너뛰기 복잡 한 다중 사이트 환경에서 웹 사이트 DNS 레코드 사용
<a name="Example"> </a>

클라이언트는 내부 DNS 서버에서 미디어 우회 웹 서비스의 웹 주소를 받습니다. 웹 서비스의 이름은 모든 클라우드 커넥터 기기 및 클라우드 커넥터 PSTN 사이트에서 동일 하 게 유지 됩니다. 복잡 한 다중 사이트 환경에서는 지리적 위치 기반 트래픽 관리에 Windows 2016 DNS 정책을 사용 하는 것이 좋으며, 클라이언트는 네트워크의 로컬인 웹 서비스로 리디렉션할 수 있습니다. 
  
Windows 2016 DNS 정책에 대 한 자세한 내용은 [기본 서버에서 지리적 위치 기반 트래픽 관리에 DNS 정책 사용](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)을 참조 하세요.
  
다음은 지리적 위치 기반 트래픽 관리를 위해 Windows 2016 DNS 정책을 사용 하는 여러 사이트가 있는 회사의 구성 예입니다.
  
우회 서비스의 이름은 ' hybridvoice.adatum.biz '입니다.
  
암스테르담의 사이트에는 다음 중재 서버 IP 주소를 사용 하 여 배포 된 4 개의 클라우드 커넥터 기기가 있습니다.
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
시애틀의 사이트에는 다음과 같은 중재 서버 IP 주소를 사용 하 여 배포 된 세 개의 클라우드 커넥터 기기가 있습니다.
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
지리적 위치 기반 트래픽 관리를 사용 하는 경우 DNS 서버는 다음과 같이 구성 됩니다.
  
1. 암스테르담 및 시애틀 서브넷 모두에 대해 DNS 클라이언트 서브넷을 만듭니다.
    
2. 암스테르담 및 시애틀에 대해 adatum.biz에 대 한 DNS 영역 범위를 만듭니다.
    
3. 각 DNS 영역 범위에서 DNS 레코드를 만듭니다.
    
    암스테르담
    
   - 입력 A;
    
   - Name: adatum.biz DNS 영역에서 hybridvoice
    
   - 대상: 192.168.1.45
    
     추가 중재 서버에 대 한 추가 레코드 만들기
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     시애틀
    
   - 입력 하십시오
    
   - Name: adatum.biz DNS 영역의 hybridvoice
    
   - 대상: 10.10.1.8
    
     추가 중재 서버에 대 한 추가 레코드 만들기
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. 클라이언트 서브넷을 적절 한 영역 범위에 연결 하는 DNS 정책을 만들어 원하는 DNS 해상도를 보장 합니다.
    
이 시점에서 hybridvoice.adatum.biz 용 암스테르담 서브넷에서 DNS 쿼리를 생성 하는 클라이언트가 192.168.1.45, 192.168.1.46, 192.168.1.47 및 192.168.1.48 주소를 반환 하는 반면, 동일한 쿼리 양식 시애틀을 하는 클라이언트는 10.10.1.8를 반환 합니다. 10.10.1.9 및 10.10.1.10.

> [!NOTE]
> CCE 기기가 업데이트 된 설정을 가져오지 않는 것 같으면 기기가 원격 PowerShell을 통해 테 넌 트에 연결할 수 있는지 확인 합니다. 원격 PowerShell을 사용 하 여 CsHybridPSTNAppliance로 기기 상태를 확인 하거나 CCE 호스트의 PowerShell을 사용 하 여 상태를 Get-CcApplianceStatus으로 확인할 수 있습니다.

  
## <a name="see-also"></a>참고 항목
<a name="Example"> </a>

[클라우드 커넥터 에디션의 미디어 바이패스 계획](plan-for-media-bypass-in-cloud-connector-edition.md)
