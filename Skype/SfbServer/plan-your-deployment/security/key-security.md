---
title: 비즈니스용 Skype 서버의 주요 보안 기능
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: 비즈니스용 Skype Server에는 서버 간 인증, 역할 기반 액세스 제어 및 구성 데이터의 중앙 집중화를 비롯 한 다양 한 보안 기능이 포함 되어 있습니다.
ms.openlocfilehash: ac1891194d231c4d494ba4014e4abd8bd7f1185b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815656"
---
# <a name="key-security-features-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 주요 보안 기능
 
비즈니스용 Skype Server에는 서버 간 인증, 역할 기반 액세스 제어 및 구성 데이터의 중앙 집중화를 비롯 한 다양 한 보안 기능이 포함 되어 있습니다. 
  
이 문서에서는 비즈니스용 Skype 서버 보안에 대해 간략하게 설명 합니다. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 주요 보안 기능

보안은 매우 광범위 한 주제입니다. 비즈니스용 skype server의 모든 기능, 그리고 비즈니스용 Skype 서버 에코 시스템을 구성 하는 데이터베이스, 서비스 및 하드웨어를 통해 보안이 유지 됩니다. 이 문서에서는 보안을 위해 디자인 된 비즈니스용 Skype Server의 일부 기능에 대해 간략하게 설명 합니다.
  
### <a name="planning-and-design-tools"></a>계획 및 디자인 도구

비즈니스용 skype Server는 비즈니스용 Skype 서버 구성 요소를 잘못 구성 하는 것을 도와주는 두 가지 도구인 계획 및 디자인을 제공 합니다. 
  
- **토폴로지 계획 도구** 는 토폴로지 디자인 프로세스의 대부분을 자동화 합니다. 비즈니스용 Skype Server를 실행 하는 각 서버를 설치 하는 데 필요한 도구인 계획 도구에서 토폴로지 작성기로 결과를 내보낼 수 있습니다.
    
- **토폴로지 작성기** 는 중앙 관리 저장소에 모든 구성 정보를 저장 합니다.
    
이러한 도구에 대 한 자세한 내용은 [비즈니스용 Skype 서버 관리 도구](../../management-tools/management-tools.md)를 참조 하세요.
  
### <a name="central-management-store"></a>중앙 관리 저장소

비즈니스용 Skype 서버에서 서버 및 서비스에 대 한 구성 데이터는 중앙 관리 저장소의 일부입니다. 중앙 관리 저장소는 비즈니스용 Skype 서버 배포를 정의, 설정, 유지 관리, 관리, 설명 및 운영 하는 데 필요한 데이터에 대 한 강력 하 고 schematized 저장소를 제공 합니다. 또한 구성을 일관성 있게 유지 하기 위해 데이터의 유효성을 검사 합니다. 이 구성 데이터에 대 한 모든 변경 사항은 중앙 관리 저장소에서 수행 되며 "동기화 되지 않은" 문제를 제거 합니다. 
  
데이터의 읽기 전용 복사본은 Edge 서버 및 Survivable Branch 기기를 포함 하 여 토폴로지의 모든 서버에 복제 됩니다. 복제는 기본적으로 네트워크 서비스의 컨텍스트에서 실행 되며 컴퓨터에 있는 단순 사용자의 권한 및 사용 권한을 줄이는 서비스에 의해 관리 됩니다. 
  
### <a name="server-to-server-authentication"></a>서버 대 서버 인증

비즈니스용 Skype Server에서는 OAuth (Open Authorization) 프로토콜을 사용 하 여 서버 간에 인증을 구성할 수 있습니다. 예를 들어 Microsoft Exchange Server 2016를 실행 하는 서버에서 인증 하도록 비즈니스용 Skype 서버를 구성할 수 있습니다. OAuth 프로토콜을 사용 하는 경우 비즈니스용 Skype 서버와 Microsoft Exchange Server는 서로를 신뢰할 수 있습니다. 이를 통해 원활한 방식으로 제품을 통합할 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버에서 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리](../../manage/authentication/server-to-server-and-partner-applications.md)를 참조 하세요.
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell 기반 관리 및 웹 기반 관리 인터페이스

비즈니스용 Skype Server는 Windows PowerShell 명령줄 인터페이스를 기반으로 하는 강력한 관리 인터페이스를 제공 합니다. 여기에는 보안을 관리 하는 cmdlet이 포함 되어 있으며 사용자가 스크립트를 쉽게 실행할 수 없도록 Windows PowerShell 보안 기능이 기본적으로 사용 하도록 설정 되어 있습니다. 즉, 소프트웨어 기본값이 자동으로 보안을 최대화 하 고 공격을 줄일 수 있도록 설정 됩니다. 비즈니스용 Skype Server의 Windows PowerShell 관리 지원에 대 한 자세한 내용은 비즈니스용 [Skype Server Management Shell](../../manage/management-shell.md)을 참조 하세요. 
  
### <a name="role-based-access-control-rbac"></a>RBAC (역할 기반 액세스 제어)

비즈니스용 Skype Server는 보안을 위해 높은 표준을 유지 하면서 관리 작업을 위임할 수 있는 RBAC (역할 기반 액세스 제어)를 제공 합니다. RBAC를 사용 하 여 사용자가 작업에 필요한 관리 권한만 부여 받은 "최소 권한"의 원칙을 따를 수 있습니다. 비즈니스용 Skype Server는 새 역할을 만드는 기능과 기존 역할을 수정 하는 기능도 제공 합니다. 
  
## <a name="network-address-translation-nat"></a>NAT (Network Address Translation)

비즈니스용 Skype 서버는 Edge 서버의 내부 인터페이스에서 NAT (network address translation) 사용을 지원 하지 않지만, 단일 및 배율 통합 Edge 서버 토폴로지에 대해 NAT (network address translation)를 수행 하는 라우터 또는 방화벽 뒤에 대 한 액세스 경계 서비스, 웹 회의 Edge 서비스,/V Edge 서비스의 외부 인터페이스를 제공 하는 것을 지원 합니다. 하드웨어 부하 분산 장치 뒤에 있는 여러 Edge 서버는 NAT를 사용할 수 없습니다. 외부 인터페이스에서 여러 Edge 서버가 NAT를 사용 하는 경우 DNS (Domain Name System) 부하 분산이 필요 합니다. 그런 다음 DNS 부하 분산을 사용 하면 Edge 서버 풀의 Edge 서버 당 공용 IP 주소 수를 줄일 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버의 Edge 서버 시나리오](../../plan-your-deployment/edge-server-deployments/scenarios.md)를 참조 하세요.
  
> [!NOTE]
> Microsoft Office Communications Server 2007 배포를 보유 하는 기업과 페더레이션 하 고 enterprise와 페더레이션 엔터프라이즈 사이에 오디오/비디오를 사용 해야 하는 경우 포트 요구 사항은 배포 되는 이전 버전의 Edge 서버에 대 한 것입니다. 예를 들어 이러한 이전 버전에 필요한 포트 범위는 페더레이션 파트너가 Edge 서버를 비즈니스용 Skype Server로 업그레이드할 때까지 두 엔터프라이즈 모두에 대해 열려 있어야 합니다. 이 때 새 구성에 따라 포트 요구 사항을 검토 하 고 축소할 수 있습니다. 
  
## <a name="simplified-certificates-for-edge-servers"></a>Edge 서버용으로 간소화 된 인증서

배포 마법사가 자동으로 주체 이름 (SNs) 및 주체 대체 이름 (San)을 채워 불필요 하 고 잠재적 하 게 보안 되지 않는 항목을 포함할 가능성을 줄일 수 있습니다.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>SDL (신뢰할 수 있는 컴퓨팅 보안 개발 수명 주기)

비즈니스용 Skype 서버는 Microsoft의 신뢰할 수 있는 컴퓨팅 SDL ( [보안 개발 수명 주기](https://go.microsoft.com/fwlink/p/?linkid=68761) )을 준수 하 여 디자인 및 개발 되었습니다.
  
- **신뢰할** 수 있는 디자인 더욱 안전한 통합 커뮤니케이션 시스템을 만드는 첫 번째 단계는 위협 모델을 디자인 하 고 각 기능을 디자인 한 대로 테스트 하는 것입니다. 또한 Microsoft는 예기치 않은 제품 동작으로 인해 발생 하는 보안 취약점을 찾기 위해 디자인 된 동작을 벗어난 테스트를 수행 합니다. 여러 보안 관련 개선 사항이 코딩 프로세스 및 관례에 기본으로 제공 되었습니다. 빌드 시간 도구는 코드가 최종 제품에 체크 인 되기 전에 버퍼 오버런과 기타 잠재적인 보안 위험을 검색 합니다. 물론 알 수 없는 모든 보안 위협 으로부터 디자인 하는 것은 불가능 합니다. 시스템에서 완벽 한 보안을 보장할 수 없습니다. 그러나 제품 개발 embraced 시작부터 안전한 디자인 원칙 때문에 비즈니스용 Skype 서버는 업계 표준 보안 기술을 해당 아키텍처의 기본 부분으로 통합 합니다.
    
- **신뢰할** 수 있는 기본 기본적으로 비즈니스용 Skype 서버의 네트워크 통신이 암호화 됩니다. 모든 서버는 인증서와 Kerberos 인증, TLS, 안전한 SRTP (실시간 전송 프로토콜), 그리고 128 비트 AES (고급 암호화 표준) 암호화를 비롯 한 기타 업계 표준 암호화 기술을 사용 하기 때문에 거의 모든 Skype 비즈니스 서버 데이터는 네트워크에서 보호 됩니다. 또한 역할 기반 액세스 제어를 통해 각 서버 역할이 서비스만 실행 하 고 해당 서비스와 관련 된 사용 권한만 있고 서버 역할에 해당 되는 경우에는 비즈니스용 Skype 서버를 실행 하는 서버를 배포할 수 있습니다.
    
- **배포에** 의 한 신뢰 모든 비즈니스용 Skype 서버 설명서에는 배포에 적합 한 보안 수준을 확인 하 고 구성 하는 데 도움이 되는 모범 사례 및 권장 사항이 포함 되어 있으며, 비기본 옵션을 활성화 하는 경우의 보안 위험을 평가할 수 있습니다.
    

