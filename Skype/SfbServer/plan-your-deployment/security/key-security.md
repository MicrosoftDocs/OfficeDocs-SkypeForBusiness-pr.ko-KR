---
title: 비즈니스용 Skype 서버의 주요 보안 기능
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
description: 비즈니스용 Skype 서버에는 서버 대 서버 인증, 역할 기반 액세스 제어 및 구성 데이터의 중앙 집중식 저장소를 비롯한 여러 보안 기능이 포함되어 있습니다.
ms.openlocfilehash: 1cf1e5f2866a3d03d77604afc83061b420658468
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104224"
---
# <a name="key-security-features-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 주요 보안 기능
 
비즈니스용 Skype 서버에는 서버 대 서버 인증, 역할 기반 액세스 제어 및 구성 데이터의 중앙 집중식 저장소를 비롯한 여러 보안 기능이 포함되어 있습니다. 
  
이 문서에서는 비즈니스용 Skype 서버 보안에 대한 간략한 개요를 제공합니다. 
  
## <a name="key-security-features-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 주요 보안 기능

보안은 매우 광범위한 항목입니다. 보안은 비즈니스용 Skype 서버 에코시스템을 구성하는 데이터베이스, 서비스 및 하드웨어뿐만 아니라 비즈니스용 Skype 서버의 모든 기능에 걸쳐 도달합니다. 이 문서에서는 특히 보안을 위해 설계된 비즈니스용 Skype 서버의 일부 기능에 대해 간략하게 설명합니다.
  
### <a name="planning-and-design-tools"></a>계획 및 디자인 도구

비즈니스용 Skype 서버는 계획 및 디자인을 용이하게 하여 비즈니스용 Skype 서버 구성 요소를 잘못 구성할 가능성이 낮아지기 위한 두 가지 도구를 제공합니다. 
  
- **토폴로지 계획 도구는** 많은 토폴로지 디자인 프로세스를 자동화합니다. 비즈니스용 Skype 서버를 실행하는 각 서버를 설치하는 데 필요한 도구인 계획 도구에서 토폴로지 작성기로 결과를 내보낼 수 있습니다.
    
- **토폴로지 작성기에서는** 모든 구성 정보를 중앙 관리 저장소에 저장합니다.
    
이러한 도구에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 도구 를 참조하세요.](../../management-tools/management-tools.md)
  
### <a name="central-management-store"></a>중앙 관리 저장소

비즈니스용 Skype 서버에서 서버 및 서비스에 대한 구성 데이터는 중앙 관리 저장소의 일부입니다. 중앙 관리 저장소는 비즈니스용 Skype 서버 배포를 정의, 설정, 유지 관리, 관리, 설명 및 운영하는 데 필요한 데이터의 강력하고 구조화된 저장소를 제공합니다. 또한 데이터의 유효성을 검사하여 구성 일관성을 보장합니다. 이 구성 데이터에 대한 모든 변경 내용은 중앙 관리 저장소에서 발생하여 "동기화되지 않습니다." 문제를 제거합니다. 
  
데이터의 읽기 전용 복사본이 Edge 서버를 포함한 토폴로지의 모든 서버로 복제됩니다. 복제는 기본적으로 네트워크 서비스의 컨텍스트에서 실행되는 서비스에서 관리하여 컴퓨터의 단순 사용자에 대한 권한 및 사용 권한을 줄입니다. 
  
### <a name="server-to-server-authentication"></a>서버 대 서버 인증

비즈니스용 Skype 서버에서는 OAuth(Open Authorization) 프로토콜을 사용하여 서버 간에 인증을 구성할 수 있습니다. 예를 들어 2016년 8월에 실행되는 서버에 인증하도록 비즈니스용 Skype 서버를 Microsoft Exchange Server 있습니다. OAuth 프로토콜을 사용하여 비즈니스용 Skype 서버와 Microsoft Exchange Server 서로 신뢰할 수 있습니다. 이렇게 하면 제품을 원활하게 통합할 수 있습니다. 자세한 내용은 [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md)를 참조하세요.
  
### <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell 관리 및 웹 기반 관리 인터페이스

비즈니스용 Skype 서버는 명령줄 인터페이스를 사용하여 구축된 강력한 Windows PowerShell 인터페이스를 제공합니다. 여기에는 보안을 관리하기 위한 cmdlet이 포함되어 있으며, Windows PowerShell 보안 기능은 기본적으로 사용하도록 설정되어 있으므로 사용자가 스크립트를 쉽게 또는 무의식적으로 실행할 수 없습니다. 즉, 소프트웨어 기본값이 자동으로 보안을 최대화하고 공격의 위험을 줄일 수 있도록 설정되어 있습니다. 비즈니스용 Skype Windows PowerShell 지원에 대한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸을 참조하세요.](../../manage/management-shell.md) 
  
### <a name="role-based-access-control-rbac"></a>RBAC(역할 기반 액세스 제어)

비즈니스용 Skype 서버는 높은 보안 표준을 유지하면서 관리 작업을 위임할 수 있도록 RBAC(역할 기반 액세스 제어)를 제공합니다. RBAC를 사용하여 "최소 권한"의 원칙을 따를 수 있습니다. 이 원칙에 따라 사용자에게는 해당 작업에서 필요한 관리 권한만 부여됩니다. 비즈니스용 Skype 서버는 새 역할을 만드는 기능을 제공하며 기존 역할을 수정하는 기능을 제공합니다. 
  
## <a name="network-address-translation-nat"></a>NAT(Network Address Translation)

비즈니스용 Skype 서버는 에지 서버의 내부 인터페이스에서 NAT(네트워크 주소 변환)를 사용할 수 없지만, 단일 및 확장 통합 에지 서버 토폴로지 둘 다에 대해 NAT(Network Address Translation)를 수행하는 라우터 또는 방화벽 뒤에 액세스 에지 서비스, 웹 회의 에지 서비스 및 A/V 에지 서비스의 외부 인터페이스 배치를 지원합니다. 하드웨어 부하 균형 조정기 뒤에 있는 여러 에지 서버는 NAT를 사용할 수 없습니다. 여러 에지 서버가 외부 인터페이스에서 NAT를 사용하는 경우 DNS(Domain Name System) 부하 분산이 필요합니다. 따라서 DNS 부하 분산을 사용하면 에지 서버 풀의 에지 서버당 공용 IP 주소 수를 줄일 수 있습니다. 자세한 내용은 비즈니스용 [Skype 서버의 에지 서버 시나리오를 참조하세요.](../../plan-your-deployment/edge-server-deployments/scenarios.md)
  
> [!NOTE]
> Microsoft Office Communications Server 2007 배포가 있는 엔터프라이즈와 페더러티드 엔터프라이즈 간에 오디오/비디오를 사용하려면 배포된 이전 버전의 에지 서버에 대한 포트 요구 사항이 포트 요구 사항입니다. 예를 들어 페더러티 파트너가 에지 서버를 비즈니스용 Skype 서버로 업그레이드할 때까지 이러한 이전 버전에 필요한 포트 범위를 두 엔터프라이즈에 대해 열 수 있어야 합니다. 이때 새 구성에 따라 포트 요구 사항을 검토하고 줄일 수 있습니다. 
  
## <a name="simplified-certificates-for-edge-servers"></a>에지 서버에 대한 간소화된 인증서

배포 마법사는 주체 이름(SNS) 및 SA(주체 대체 이름)를 자동으로 채울 수 있으며 불필요하고 보안되지 않은 항목을 포함하지 않아도 됩니다.
  
## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>신뢰할 수 있는 컴퓨팅 SDL(보안 개발 수명 주기)

비즈니스용 Skype 서버는 [Microsoft Trustworthy Computing](/previous-versions/ms995349(v=msdn.10)) SDL(보안 개발 수명 주기)을 준수하여 설계 및 개발됩니다.
  
- **디자인에 의해 신뢰할 수 있습니다.** 보다 안전한 통합 통신 시스템을 만드는 첫 번째 단계는 위협 모델을 디자인하고 설계한 각 기능을 테스트하는 것입니다. 또한 Microsoft는 예기치 않은 제품 동작으로 인한 보안 취약성을 찾기 위해 디자인된 동작 외부에서 테스트를 수행합니다. 코딩 프로세스 및 사례에는 여러 보안 관련 개선이 기본 제공되어 있습니다. 빌드 타임 도구는 코드가 최종 제품에 체크 인되기 전에 버퍼 오버런 및 기타 잠재적인 보안 위협을 감지합니다. 물론 알 수 없는 모든 보안 위협에 대해 디자인할 수 없습니다. 어떤 시스템도 완전한 보안을 보장할 수 없습니다. 그러나 제품 개발은 시작부터 안전한 디자인 원칙을 수용하기 때문에 비즈니스용 Skype 서버는 업계 표준 보안 기술을 아키텍처의 기본 부분으로 통합합니다.
    
- **기본적으로 신뢰할 수 있습니다.** 기본적으로 비즈니스용 Skype 서버의 네트워크 통신은 암호화됩니다. 모든 서버에서 인증서 및 Kerberos 인증, TLS, SRTP(Secure Real-Time Transport Protocol) 및 128비트 AES(Advanced Encryption Standard) 암호화를 비롯한 기타 업계 표준 암호화 기술을 사용하며, 거의 모든 비즈니스용 Skype 서버 데이터는 네트워크에서 보호됩니다. 또한 역할 기반 액세스 제어를 사용하면 각 서버 역할이 서비스만 실행되고 해당 서비스와 관련된 사용 권한만 서버 역할에 적합한 사용 권한만 하도록 비즈니스용 Skype 서버를 실행 중인 서버를 배포할 수 있습니다.
    
- **배포에 의해 신뢰할 수 있습니다.** 모든 비즈니스용 Skype 서버 설명서에는 배포에 대한 최적의 보안 수준을 결정 및 구성하고 기본이 아닌 옵션을 활성화할 때의 보안 위험을 평가하는 데 도움이 되는 모범 사례 및 권장 사항이 포함되어 있습니다.
