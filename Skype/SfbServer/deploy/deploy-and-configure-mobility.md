---
title: 비즈니스용 Skype 서버에 대 한 모바일 기능 배포 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 모바일 기능을 활용할 수 있도록 하는 기존 비즈니스용 Skype 서버 설치를 구성 하는 단계를 안내 합니다.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029069"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 모바일 기능 배포 및 구성  
 
이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 모바일 기능을 활용할 수 있도록 하는 기존 비즈니스용 Skype 서버 설치를 구성 하는 단계를 안내 합니다.
  
비즈니스용 [Skype 서버](../plan-your-deployment/mobility.md) 에 대 한 모바일 기능 계획을 검토 한 후에는 아래 단계를 계속 진행 하 여 비즈니스용 skype 서버 환경에 모바일 기능을 배포할 수 있습니다. 단계는 다음과 같습니다 (이 표에 사용 권한 목록에 포함).
  
|**작업 단계**|**사용 권한**|
|:-----|:-----|
|[DNS 레코드 만들기](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[인증서 수정](deploy-and-configure-mobility.md#ModCerts) <br/> |로컬 관리자  <br/> |
|[역방향 프록시 구성](deploy-and-configure-mobility.md#ConfigRP) <br/> |로컬 관리자  <br/> |
|[하이브리드 배포를 사용 하 여 모바일 기능에 대 한 자동 검색 구성](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[모바일 기능 배포 테스트](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[푸시 알림 구성](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[모바일 정책 구성](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
다음의 모든 섹션에는 계획 항목을 읽은 것으로 가정 하는 단계가 포함 되어 있습니다. 혼란 스러운 경우에는 해당 정보를 자유롭게 확인해 보십시오.

> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.
  
## <a name="create-dns-records"></a>DNS 레코드 만들기
<a name="CreateDNSRec"> </a>

이러한 사용자는 비즈니스용 Skype 서버 환경에 포함 될 수 있지만 자동 검색을 사용 하려면 다음 레코드를 만들어야 합니다.
  
- 조직의 네트워크 내에서 연결 하는 모바일 사용자를 지원 하기 위한 내부 DNS 레코드입니다.
    
- 조직의 네트워크 외부에서 연결 하는 모바일 사용자를 지원 하기 위한 외부 (또는 공용) DNS 레코드
    
이러한 레코드는 (호스트) 이름 또는 CNAME 레코드 (둘 다 수행할 필요는 없음) 일 수 있으며 여기에는 모든 항목에 대 한 단계를 포함 하는 것이 좋습니다.
  
### <a name="create-an-internal-dns-cname-record"></a>내부 DNS CNAME 레코드 만들기

1. **Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹 인 네트워크의 DNS 서버에 로그인 합니다.
    
2. **시작**을 클릭 하 고 **관리 도구** (시작 메뉴에서 옵션을 선택 하지 않은 경우에는 **검색** 을 수행 해야 할 수도 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.
    
3. 콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버에 대 한 홈 도메인으로 이동 하 고 여기에서 **정방향 조회 영역** 을 확장 해야 합니다.
    
4. 다음 중 어느 것이 있는지 잠시 확인해 보십시오.
    
   - 프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
5. 이에 대 한 설명이 나타나면 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 별칭 (CNAME)** 을 선택 합니다.
    
6. **별칭 이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal을 호스트 이름으로 입력 합니다.
    
7. **대상 호스트의 FQDN (정규화 된 도메인 이름**)에서 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버, 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 FQDN을 입력 하거나 탐색 해야 합니다. 이를 입력 하면 확인을 클릭 합니다.
    
8. 비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대해 정방향 조회 영역에 새 자동 검색 CNAME 레코드를 만들어야 합니다.
    
### <a name="create-an-external-dns-cname-record"></a>외부 DNS CNAME 레코드 만들기

1. 이러한 단계는 사용 중인 공용 DNS 공급자를 알 수 없지만, 계속 해 서 도움이 됩니다. 새 DNS 레코드를 만들 수 있는 계정을 사용 하 여 공용 DNS 공급자에 로그인 하세요.
    
2. 이 시점에서는 비즈니스용 Skype 서버에 대 한 SIP 도메인이 이미 존재 해야 합니다. 이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나, 그렇지 않은 경우에는이를 엽니다.
    
3. 다음 중 어느 것이 있는지 잠시 확인해 보십시오.
    
   - 프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
4. 이러한 정보를 확인 한 후에는 **새 별칭 (CNAME)** 을 만드는 옵션을 선택할 수 있어야 합니다.
    
5. 이제 **별칭 이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대해 lyncdiscover를 입력 해야 합니다.
    
6. 다음에는 **대상 호스트에 대해 fqdn**에 입력할 영역이 있어야 하며 위의 3 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버, 디렉터 풀 또는 디렉터)에 대 한 fqdn 이어야 합니다.
    
7. 여기에 저장 해야 하거나, 비즈니스용 Skype 서버 환경에서 각 SIP 도메인의 정방향 조회 영역에 추가 CNAME 레코드를 만들어야 하는 경우에는 해당 작업을 수행 해야 하지만 준비가 완료 되 면 작업이 저장 됩니다.
    
### <a name="create-an-internal-dns-a-record"></a>내부 DNS A 레코드 만들기

1. **Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹 인 네트워크의 DNS 서버에 로그인 합니다.
    
2. **시작**을 클릭 하 고 **관리 도구** (시작 메뉴에서 옵션을 선택 하지 않은 경우에는 **검색** 을 수행 해야 할 수도 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.
    
3. 콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버에 대 한 홈 도메인으로 이동 하 고 여기에서 **정방향 조회 영역** 을 확장 해야 합니다.
    
4. 다음 중 어느 것이 있는지 잠시 확인해 보십시오.
    
   - 프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
5. 이에 대 한 설명이 나타나면 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 호스트 (A 또는 AAAA)** 를 선택 합니다.
    
6. **이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal을 호스트 이름으로 입력 합니다.
    
7. **IP 주소** 텍스트 상자에 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버, 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 IP 주소를 입력 합니다.
    
8. 이 작업이 완료 되 면 **호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.
    
9. 비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대해 정방향 조회 영역에 새 자동 검색 A 또는 AAAA 레코드를 만들어야 합니다. 이 작업을 수행 하려면 6-8 단계를 필요한 만큼 반복 합니다.
    
10. 작업을 마치면 **완료**를 클릭 합니다.
    
### <a name="create-an-external-dns-a-record"></a>외부 DNS A 레코드 만들기

1. 이러한 단계는 사용 중인 공용 DNS 공급자를 알 수 없지만, 계속 해 서 도움이 됩니다. 새 DNS 레코드를 만들 수 있는 계정을 사용 하 여 공용 DNS 공급자에 로그인 하세요.
    
2. 이 시점에서는 비즈니스용 Skype 서버에 대 한 SIP 도메인이 이미 존재 해야 합니다. 이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나, 그렇지 않은 경우에는이를 엽니다.
    
3. 다음 중 어느 것이 있는지 잠시 확인해 보십시오.
    
   - 프런트 엔드 서버에 대 한 호스트 A 또는 AAAA 레코드 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 (s)
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
4. 이러한 정보를 확인 한 후에는 **새 호스트 a 또는 AAAA**를 만드는 옵션을 선택할 수 있어야 합니다.
    
5. 이제 **이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대해 lyncdiscover를 입력 해야 합니다.
    
6. 다음에는 **IP Addresss**에 입력할 영역을 입력 해야 하며 위의 3 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 감독)의 IP 여야 합니다.
    
7. 여기에 저장 해야 하거나, 비즈니스용 Skype 서버 환경에 대 한 각 SIP 도메인의 정방향 조회 영역에서 추가 A 또는 AAAA 레코드를 만들어야 하는 경우에는 해당 작업을 수행 해야 하지만 준비가 완료 되 면 작업이 저장 됩니다.
    
## <a name="modify-certificates"></a>인증서 수정
<a name="ModCerts"> </a>

인증서를 계획 하는 방법에 대 한 질문이 있는 경우 [비즈니스용 Skype 서버](../plan-your-deployment/mobility.md) 에 대 한 모바일 기능 계획 문서에 설명 되어 있습니다. 검토 한 후에는 다음을 안내해 드리겠습니다.
  
- 새 인증서가 필요 합니까?
    
- CA (인증 기관)에서 새 인증서 요청
    
- PowerShell을 사용 하 여 대체 항목을 사용 하 여 원본 위치 인증서 업데이트
    
- MMC (Microsoft Management Console)에서 인증서 스냅인을 사용 하 여 인증서를 확인 합니다.
    
### <a name="do-i-need-new-certificates"></a>새 인증서가 필요 합니까?

1. 먼저 현재 위치에 있는 인증서와 필요한 항목이 있는지 여부를 확인 해야 합니다. 이렇게 하려면 로컬 관리자 인 계정을 사용 하 여 비즈니스용 Skype 서버에 로그인 해야 합니다. 이 계정에는 이러한 단계 중 일부에 대해 발급 하는 CA (인증 기관)에 대 한 권한도 필요할 수도 있습니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 엽니다 (검색을 사용 하 여 시작 메뉴나 작업 표시줄에 고정 되지 않은 경우).
    
3. 업데이트 된 인증서를 추가 하기 전에 어떤 인증서가 할당 되었는지 반드시 확인 해야 합니다. 명령에서 다음을 입력 합니다.
    
   ```powershell
   Get-CsCertificate
   ```

4. 3 단계의 정보는 고유 합니다. 여러 항목에 할당 된 단일 인증서가 있는지 또는이를 필요로 하는 다른 구성 요소에 대해 다른 인증서를 할당 했는지 확인 하기 위해이 방법을 찾아야 합니다. **Use** 매개 변수를 사용 하 여 인증서를 사용 하는 방법을 결정 하 고, **지문** 매개 변수는 모두 동일한 인증서 또는 여러 인증을 갖는 경우를 알려줍니다.
    
5. 이 계획 섹션에서 SAN 항목을 권장 하는 경우에는 좋은 방법입니다. 그렇지 않으면 인증 기관에서 새 인증서 또는 구성에 따라 여러 인증서를 요청 해야 합니다.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>CA (인증 기관)에서 새 인증서 또는 인증서를 요청 합니다.

1. 보유 하 고 있는 SAN 항목을 확인 한 후에는 **단일 인증서** (위 단계를 통해 확인 한 후)가 있고 필요한 항목이 모두 없는 것을 알게 되었습니다. 새 인증서 요청을 CA에 적용 해야 합니다. 비즈니스용 Skype 서버 PowerShell을 엽니다.
    
   - 자동 검색 서비스 SAN의 경우 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기)
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. 또한 DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다. 예를 들면 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기).
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 또한 어떤 SAN 항목이 있는지 확인 한 후에는 필요한 항목을 모두 포함 하지 않은 **인증서가 여러** 개 있다는 것을 알 수 있습니다. 새 인증서 요청을 CA에 적용 해야 합니다. 비즈니스용 Skype 서버 PowerShell을 엽니다.
    
   - 자동 검색 서비스 SAN의 경우 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기)
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. 또한 DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다. 예를 들면 (-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기).
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA에서 새 인증서를 생성 한 후에는 할당 해야 합니다.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용 하 여 인증서 할당

- 위의 새 인증 필요 섹션에 나와 있는 항목에 따라 다음 중 **하나** 를 실행 해야 합니다.
    
  - 모든 항목에 대 한 인증서가 하나인 경우 (지문이 동일)이 작업을 실행 해야 합니다.
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 다른 항목에 대 한 여러 인증서가 있는 경우 (지문을 모두 다른 경우) 대신 다음을 실행 합니다.
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>MMC (Microsoft Management Console)에서 인증서 보기

1. MMC의 인증서 스냅인을 사용 하 여 인증서를 확인할 수 있는 옵션이 있습니다. 검색에 MMC를 입력 하 고 응용 프로그램 옵션으로 팝업 하면 됩니다.
    
2. 인증서 스냅인을 추가 하려면 **파일**을 클릭 한 다음 **스냅인 추가/제거 ...** (또는 바로 가기 **키 Ctrl + M** 도 작동) 합니다. **인증서** 는 왼쪽 창에서 옵션이 되며, 해당 옵션을 선택한 다음 팝업 창에서 **컴퓨터 계정을** 선택 하 고 다음 **을 클릭 합니다.**
    
3. 여전히 팝업 창에서 확인 해야 하는 인증서에 대 한 홈 인 컴퓨터에서이 작업을 수행할 수 있으므로이 경우 **로컬 컴퓨터** 에서 선택 항목을 그대로 유지 합니다. 원격 컴퓨터에서 작업 하는 경우 라디오 단추를 **다른 컴퓨터로** 변경한 다음 해당 컴퓨터의 FQDN을 입력 하거나, **찾아보기** 단추를 사용 하 여 AD를 통해 해당 컴퓨터를 검색 합니다. 컴퓨터를 선택한 후 준비가 되 면 **마침을** 클릭 하 고 **확인** 을 누른 다음 MMC에 스냅인을 추가 합니다.
    
4. MMC의 왼쪽 창에서 **인증서** 섹션을 확장 합니다. **개인** 폴더도 확장 한 다음 **인증서**를 선택 합니다. 이를 통해이 저장소의 인증서를 볼 수 있습니다.
    
5. 보려는 인증서를 찾아서 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.
    
    > [!NOTE]
    > 인증서가 무엇 인지 어떻게 알 수 있나요? 여기에는 팜의 모든 항목에 할당 된 단일 인증서가 있거나, 기본, 내부 웹 서비스 등의 다른 항목에 대 한 인증서가 여러 개 있을 수 있으며,이 경우에는 여러 인증서를 확인 해야 할 수 있습니다. 여러 인증서에는 동일한 지문이 포함 됩니다. 
  
6. **인증서** 보기를 확인 한 후 **자세히**를 선택 합니다. 이렇게 하면 **주체**를 선택 하면 인증서 주체 이름이 표시 되 고 지정 된 주체 이름 및 관련 속성이 표시 됩니다.
    
7. 또한 **주체 대체 이름** 항목을 확인 해야 합니다. 다음 중 하나 이상의 항목을 찾을 수 있습니다.
    
   - 이 풀의 풀 이름 또는 단일 서버 이름 (풀이 아닌 경우)
    
   - 인증서가 할당 된 서버 이름입니다.
    
   - 단순 URL 레코드 (일반적으로 모임 및 전화 접속)
    
   - 웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의를 사용한 웹 서비스 선택에 대 한 선택 사항에 따라 달라 집니다.
    
   - 이미 지정 된 경우 lyncdiscover입니다. \<microsoft.rtc.management.xds.sipdomain object\> 및 lyncdiscoverinternal \<microsoft.rtc.management.xds.sipdomain object\> 레코드
    
     할당 된 인증서가 두 개 이상인 경우에는 여러 보증서를 확인 해야 합니다 (위의 참고 사항 확인).
    
8. 따라서 lyncdiscover가 발견 되 면이 방법을 사용할 수 있습니다. \<microsoft.rtc.management.xds.sipdomain object\> 및 lyncdiscoverinternal \<microsoft.rtc.management.xds.sipdomain object\> 레코드가 이미 구성 되어 있습니다. MMC를 닫을 수 있습니다.
    
9. 할당 되지 않은 경우에는 위에서 설명한 새 인증서 요청을 만들거나 요청 후에 설치 해야 합니다 (위의 PowerShell을 먼저 수행 하는 것이 좋습니다).
    
## <a name="configure-the-reverse-proxy"></a>역방향 프록시 구성
<a name="ConfigRP"> </a>

아래 단계는 정확히 따라야 하는 것은 아닙니다. 이전 버전의 제품에서 TMG (위협 관리 게이트웨이) 구성,이를 사용 하지 않은 경우에는 사용자가 해당 버전에서 직접 작업을 수행 해야 하기 때문입니다.
  
TMG가 Microsoft에서 제품으로 더 이상 제공 되지 않으며 여전히 구성 해야 하는 경우 [Lync Server 2013 단계](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)를 확인할 수 있습니다. 그러나 다음 정보는 모든 역방향 프록시에 대 한 특정 연습 단계를 제공할 수 있는 방법이 없더라도 더 일반적으로 도움이 됩니다.
  
다음과 같은 두 가지 주요 사항을 고려해 야 합니다.
  
- HTTPS를 통한 초기 자동 검색 요청을 수행할 것인가 (권장)?
    
  - 웹 게시 규칙이 있는 경우 수정 해야 합니다.
    
  - 아직 웹 게시 규칙이 없는 경우에는 만들어야 합니다.
    
- HTTP를 통한 초기 자동 검색 요청을 수행 하는 경우 해당 규칙도 만들거나 수정 해야 합니다.
    
> [!NOTE]
> **중요** 프록시 제한 시간 값은 배포에 따라 달라 지는 숫자입니다. 배포를 모니터링 하 고 클라이언트의 모범 환경에 맞게 값을 수정 해야 합니다. 200 보다 낮은 값으로 설정할 수 있습니다. 사용자 환경에서 Lync 모바일 클라이언트를 지 원하는 경우 시간 제한 값이 900 인 Office 365에서 푸시 알림 시간 제한을 허용 하려면이 값을 960로 설정 해야 합니다. 값이 너무 낮을 때 클라이언트 연결이 끊어지지 않도록 하려면 시간 제한 값을 늘려야 하며, 그렇지 않으면 프록시를 통한 연결이 끊어지지 않으면 숫자를 줄이고 클라이언트 연결이 끊어진 후에는 장시간 해제 해야 합니다. 이 값에 대 한 적절 한 설정을 결정 하는 유일한 방법은 사용자 환경에서 일반적으로 수행 하는 작업의 모니터링 및 기준 설정입니다.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>외부 자동 검색 SAN 및 URL에 대 한 기존 웹 게시 규칙 수정

1. 역방향 프록시 인터페이스를 엽니다.
    
2. 웹 게시 규칙을 찾고, 역방향 프록시 구성에 따라 메뉴 또는 탭에 있는 편집 옵션을 선택 해야 합니다.
    
3. 이 웹 게시 규칙이 적용 되는 대상을 나타내는 영역이 있어야 합니다. 수신 사이트 또는 사이트 요청에 대해이 규칙을 수정 해야 합니다. 새 항목을 **추가** 합니다.
    
4. 자동 검색 사이트의 이름 (사용 하는 예제는 lyncdiscover.contoso.com)을 입력 하 고 역방향 프록시 형식에 따라 **확인** 또는 **저장**을 클릭 합니다.
    
5. 자동 검색 SAN 항목을 포함 하는 새 인증서가 있을 수 있습니다. 설치 해야 하 고 역방향 프록시 설정에 따라 사용 하도록 구성 해야 합니다. 구성이 완료 되 면 모든 사항을 저장 해야 합니다.
    
6. 역방향 프록시에 **테스트** 기능이 있는 경우 해당 기능을 사용 하 여 모든 기능이 제대로 작동 하는지 확인 하세요.
    
7. 이제 환경에 디렉터 또는 디렉터 풀이 있는 경우 이러한 단계를 반복 해야 할 수도 있습니다 (이는 두 번째 규칙이 있는 경우).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>외부 자동 검색 URL에 대 한 웹 게시 규칙 만들기

1. 역방향 프록시 인터페이스를 엽니다.
    
2. 인터페이스에서 웹 게시 규칙을 만드는 위치를 찾고, **새** 또는 **만들기** 옵션 (역방향 프록시 구성에 따라 메뉴나 탭에 있을 수 있음)을 선택 해야 합니다. 새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.
    
3. 일반적으로는 다음 정보를 입력 해야 합니다.
    
   - **이름**: 규칙의 이름입니다.
    
   - **규칙 동작**:이 경우에는 사용자가 역방향 프록시를 통과 하는 것이 **허용** 규칙입니다.
    
   - 선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.
    
   - 외부 액세스용으로 **SSL** 을 사용 해야 하는 경우 해당 옵션을 선택 합니다.
    
   - **내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치 (또는 디렉터 풀의 부하 분산 장치에 있는 경우 fqdn)에 외부 웹 서비스의 fqdn을 입력 해야 하는 경우에는 예를 sfb_pool01 합니다.
    
   - 게시할 경로에 ** / ***를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.
    
   - **공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 제공 됩니다. 이 위치는 다음을 입력할 수 있습니다.
    
   - **요청을 수락**하지만이 이름은 도메인 이름 이어야 합니다.
    
   - **이름**에는 **lyncdiscover** 를 입력 해야 합니다. <sipdomain>(이것은 외부 자동 검색 서비스 URL)입니다. 이제 프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대 한 FQDN (예: lyncwebextpool01.contoso.com)을 입력 해야 합니다.
    
   - 여기에는 **경로** 옵션이 있으며 * 여기에 입력 ** / **해야 합니다.
    
   - 최신 공용 인증서를 사용 하 여 **SSL 수신기** 를 선택 해야 합니다.
    
   - **인증 위임은** **위임 안 함**으로 설정 해야 하지만 직접 클라이언트 인증을 허용 **해야** 합니다.
    
   - **모든 사용자**에 대해 규칙을 설정 해야 합니다.
    
   - 이 규칙을 만드는 데 필요한 모든 정보를 확인 하 고 계속 진행할 수 있습니다.
    
4. **원래 호스트 헤더가** 전달 되었는지 확인 해야 합니다.
    
5. **웹 서버** 포트도 함께 설정 해야 하는 경우 다음 작업을 수행 해야 합니다.
    
   - **요청을 HTTP 포트로 리디렉션하고** 포트 번호는 **8080**이어야 합니다.
    
   - **요청을 SSL 포트로 리디렉션하고** 포트 번호는 **4443**이어야 합니다.
    
6. 모든 것이 구성 되어 있으면 이러한 항목을 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>포트 80에 대 한 웹 게시 규칙 만들기 (선택 사항)

1. 역방향 프록시 인터페이스를 엽니다.
    
2. 인터페이스에서 웹 게시 규칙을 만드는 위치를 찾고, **새** 또는 **만들기** 옵션 (역방향 프록시 구성에 따라 메뉴나 탭에 있을 수 있음)을 선택 해야 합니다. 새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.
    
3. 일반적으로는 다음 정보를 입력 해야 합니다.
    
   - **이름**: 규칙의 이름입니다.
    
   - **규칙 동작**:이 경우에는 사용자가 역방향 프록시를 통과 하는 것이 **허용** 규칙입니다.
    
   - 선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.
    
   - 이 연결을 통해 **게시 된 웹 서버 또는 팜에 연결 하려면 보안 되지 않은 연결이**필요 합니다.
    
   - **내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치 **VIP 주소** 에 대 한 FQDN을 입력 해야 하는 경우에는 예제 sfb_pool01 합니다.
    
   - 게시할 경로에 ** / ***를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.
    
   - **공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 제공 됩니다. 이 위치는 다음을 입력할 수 있습니다.
    
   - **요청을 수락**하지만이 이름은 도메인 이름 이어야 합니다.
    
   - **이름**에는 **lyncdiscover** 를 입력 해야 합니다. <sipdomain>(이것은 외부 자동 검색 서비스 URL)입니다.
    
   - 여기에는 **경로** 옵션이 있으며 * 여기에 입력 ** / **해야 합니다.
    
   - 웹 수신기를 선택 하거나 역방향 프록시가 직접 만들도록 허용 해야 합니다.
    
   - **인증 위임은** **위임 안 함**으로 설정 해야 하지만 직접 클라이언트 인증은 허용 **하지 않아야** 합니다.
    
   - **모든 사용자**에 대해 규칙을 설정 해야 합니다.
    
   - 이 규칙을 만드는 데 필요한 모든 정보를 확인 하 고 계속 진행할 수 있습니다.
    
4. **웹 서버** 포트를 설정 해야 하는 경우에는 다음을 수행 해야 합니다.
    
   - **요청을 HTTP 포트로 리디렉션하고** 포트 번호는 **8080**이어야 합니다.
    
   - **요청을 SSL 포트로 리디렉션하고** 포트 번호는 **4443**이어야 합니다.
    
5. 모든 것이 구성 되어 있으면 이러한 항목을 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>하이브리드 배포를 사용 하 여 모바일 기능에 대 한 자동 검색 구성
<a name="ConfigAutoD"> </a>

비즈니스용 Skype 서버의 하이브리드 환경은 온-프레미스 및 O365 환경을 결합 하는 환경입니다. 비즈니스용 Skype 서버가 하이브리드 환경에서 작동 하는 경우 자동 검색 서비스가 이러한 환경 중 하나에서 사용자를 찾을 수 있어야 합니다.
  
모바일 클라이언트가 사용자가 위치한 위치를 검색 하도록 하려면 자동 검색 서비스를 새로운 URL (uniform resource locator)을 사용 하 여 구성 해야 합니다. 그 단계는 다음과 같습니다.
  
1. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 다음을 실행 하 여 비즈니스용 Skype 서버 환경에 대 한 **Proxyfqdn** 특성 값을 가져옵니다.
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 그리고 나 서 셸 창에서 다음을 실행 합니다.
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    여기서 [identity]는 공유 SIP 주소 공간의 도메인 이름으로 대체됩니다.
    
## <a name="test-your-mobility-deployment"></a>모바일 기능 배포 테스트
<a name="TestMobility"> </a>

비즈니스용 Skype 서버 모바일 서비스 및 비즈니스용 Skype 서버 자동 검색 서비스를 배포한 후에는 테스트 트랜잭션을 실행 하 여 배포의 작업 권한을 확인할 수 있습니다. **Test-csucwaconference** 를 실행 하 여 두 사용자가 회의에서 생성, 참가 및 통신 하는 기능을 테스트할 수 있습니다. 이 테스트를 수행 하려면 두 명의 사용자 (실제 또는 테스트)와 전체 자격 증명이 필요 합니다. 이 명령은 Lync Server 2013 클라이언트 뿐만 아니라 비즈니스용 Skype 클라이언트에 대해서도 작동 합니다.
  
Lync Server 2010 클라이언트 (비즈니스용 Skype 서버 2015)의 경우 테스트 하려면 **test-csmcxp2pim** 를 실행 해야 합니다. Lync Server 2010 사용자는 여전히 실제 사용자 이거나 미리 정의 된 테스트 사용자 여야 하며, 암호 자격 증명이 필요 합니다.

> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>비즈니스용 Skype 및 Lync 2013 모바일 클라이언트에 대 한 테스트 회의

1. **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 설치 된 모든 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을** 시작 합니다 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동한 후 선택할 수 있음).
    
3. 명령줄에 다음을 입력 합니다.
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   또한 스크립트에 자격 증명을 설정 하 고이를 테스트 cmdlet에 전달할 수 있습니다. 이에 대 한 예는 다음과 같습니다.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Lync 2010 모바일 클라이언트에 대 한 테스트 회의

> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.

1. **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 설치 된 모든 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을** 시작 합니다 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동한 후 선택할 수 있음).
    
3. 명령줄에 다음을 입력 합니다.
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   또한 스크립트에 자격 증명을 설정 하 고이를 테스트 cmdlet에 전달할 수 있습니다. 이에 대 한 예는 다음과 같습니다.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

명령 절차를 자세히 검토 하려면 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 및 [test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)를 참조 하십시오.
  
## <a name="configure-for-push-notifications"></a>푸시 알림 구성
<a name="ConfigPush"> </a>

배지, 아이콘 또는 경고 형태의 푸시 알림은 Skype 또는 Lync 앱이 비활성 상태인 경우에도 모바일 장치로 전송 될 수 있습니다. 하지만 푸시 알림은 무엇입니까? 이러한 알림은 신규 또는 누락 된 IM 초대 또는 받은 음성 메일과 같은 이벤트 알림입니다. 비즈니스용 Skype 서버 모바일 서비스에서는 이러한 알림을 클라우드 기반 비즈니스용 Skype 서버 푸시 알림 서비스로 보내 Windows Phone 사용자를 위해 MSNS (Microsoft 푸시 알림 서비스)로 알림을 보냅니다.
  
이 기능은 Lync Server 2013에서 변경 되지 않았지만, 비즈니스용 Skype 서버가 있는 경우 다음을 수행 하는 것이 좋습니다.
  
- 비즈니스용 Skype 서버에 지 서버에 대해 새 호스팅 공급자, Microsoft 비즈니스용 Skype Online을 추가 하 고 조직과 비즈니스용 Skype Online 간에 호스팅 공급자 페더레이션을 설정 합니다.
    
- **Get-cspushnotificationconfiguration** cmdlet을 실행 하 여 푸시 알림을 사용 하도록 설정 합니다. 기본적으로 푸시 알림은 해제됩니다.
    
- 페더레이션 구성 및 푸시 알림을 테스트 합니다.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>푸시 알림을 위해 비즈니스용 Skype에 지 서버 구성

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 비즈니스용 Skype 서버 온라인 호스팅 공급자를 추가 합니다.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   예를 들면 다음과 같습니다.
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 단일 호스팅 공급자와 페더레이션 관계를 둘 이상 사용할 수 없습니다. 따라서 sipfed.online.lync.com와 페더레이션 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 id가 SkypeOnline 이외의 다른 호스팅 공급자를 추가 하는 것이 좋습니다. 
  
4. 비즈니스용 Skype Online에서 조직과 푸시 알림 서비스 간의 호스팅 공급자 페더레이션을 설정 합니다. 명령줄에 다음을 입력 해야 합니다.
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>푸시 알림 사용

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 푸시 알림 사용:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 페더레이션을 사용 합니다.
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>테스트 페더레이션 및 푸시 알림

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 페더레이션 구성을 테스트 합니다.
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 푸시 알림을 테스트 합니다.
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>모바일 정책 구성
<a name="ConfigMob"> </a>

비즈니스용 Skype 서버에서 모바일 서비스를 사용할 수 있는 사람, 직장에서의 통화, VoIP (voice over IP) 또는 비디오를 확인 하 고 VoIP 또는 비디오에 대해 WiFi가 필요한 지 여부를 결정 하는 기능이 있습니다. 회사 번호로 전화를 걸어 통화를 걸고 받을 때 모바일 사용자가 자신의 회사 전화 번호 대신 사무실 전화번호를 사용할 수 있습니다. 줄의 다른 쪽 끝에 있는 사람은 휴대폰 번호가 모바일 사용자의 휴대폰 번호를 볼 수 없으며,이를 통해 해당 사용자가 발신 전화 요금을 방지할 있습니다. VoIP 및 비디오가 설정 되 면 사용자는 VoIP 통화 및 비디오를 만들고 사용할 수 있습니다. WiFi 사용에 대 한 설정에 따라 사용자의 모바일 장치에서 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용 해야 하는지 여부가 결정 됩니다.
  
이동성, 회사 전화 통화 및 VoIP 및 비디오 기능은 모두 기본적으로 사용 하도록 설정 됩니다. VoIP 및 비디오용으로 WiFi를 요구 하는 설정을 사용 하지 않도록 설정 합니다. 관리자는 전역, 사이트 또는 사용자별로이를 변경할 수 있습니다.
  
모바일 기능을 사용 하 고 작업을 통해 전화를 걸려면 사용자는 다음을 수행 해야 합니다.
  
- 비즈니스용 Skype 서버 사용
    
- Enterprise Voice를 사용 하도록 설정 합니다.
    
- **EnableMobility** 옵션이 **True**로 설정 된 이동성 정책이 할당 되었습니다.
    
사용자가 회사 번호로 전화를 걸 수 있으려면 다음 작업도 수행 해야 합니다.
  
- **동시 전화 신호 울림 사용** 옵션이 선택 된 음성 정책이 할당 됩니다.
    
- **EnableOutsideVoice** 이 **True**로 설정 된 이동성 정책이 할당 되었습니다.
    
> [!NOTE]
> Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 모바일 장치를 사용 하 여 skype VoIP 통화를 수행 하거나, 연결 된 음성 정책에 대 한 적절 한 옵션이 설정 된 경우 모바일 장치에서 클릭 하 여 링크를 참가 시켜 회의에 참가할 수 있습니다. 으. 계획 항목에서는 더 자세하게 설명 합니다. 
  
### <a name="modify-global-mobility-policy"></a>전역 이동성 정책 수정

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 다음을 입력 하 여 모바일 기능에 대 한 액세스를 해제 하 고 전체 직장에 전화
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 모바일 기능에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 해제할 수 있습니다. 그러나 작업을 통해 통화를 끄지 않고 모바일 기능을 끌 수는 없습니다. 
  
    자세한 내용은 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)를 참조 하세요.
    
### <a name="modify-mobility-policy-by-site"></a>사이트별 모바일 정책 수정

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 사이트 수준 정책을 만들고, VoIP 및 비디오를 끄고, IP 오디오에 대해 WiFi 필요를 사용 하도록 설정 하 고, 사이트 별로 IP 비디오용 WiFi를 요구 합니다. 형식일
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    자세한 내용은 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)을 참고 하세요.
    
### <a name="modify-mobility-policy-by-user"></a>사용자별 모바일 정책 수정

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype 서버 관리 셸** 및 **ocscore** 를 설치한 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 사용자 수준 이동성 정책을 만들고 사용자 별 작업을 통해 이동성 및 통화를 해제 합니다. 형식일
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    예제 데이터가 포함 된 추가 예는 다음과 같습니다.
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 모바일 기능에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 해제할 수 있습니다. 그러나 작업을 통해 통화를 끄지 않고 모바일 기능을 끌 수는 없습니다. 
  

