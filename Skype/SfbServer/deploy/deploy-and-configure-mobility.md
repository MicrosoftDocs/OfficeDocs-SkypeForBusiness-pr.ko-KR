---
title: 비즈니스용 Skype 서버에 대 한 이동성 배포 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 이동성 기능을 활용할 수 있도록 하기 위해 기존 비즈니스용 Skype Server 설치를 구성 하는 단계를 안내 합니다.
ms.openlocfilehash: 3e39c354fd77d7ac36e3a4c36ed7e36e1d8ffbbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002868"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 이동성 배포 및 구성  
 
이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 이동성 기능을 활용할 수 있도록 하기 위해 기존 비즈니스용 Skype Server 설치를 구성 하는 단계를 안내 합니다.
  
비즈니스용 [Skype server 문서에 대 한 이동성 계획](../plan-your-deployment/mobility.md) 을 검토 한 후 아래 단계를 진행 하 여 비즈니스용 skype server 환경에 이동성을 배포할 준비가 되어 있어야 합니다. 단계는 다음과 같습니다 (이 표에는 사용 권한 목록에 포함 되어 있습니다).
  
|**단계의**|**필요한**|
|:-----|:-----|
|[DNS 레코드 만들기](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |도메인 관리자  <br/> DNSAdmins  <br/> |
|[인증서 수정](deploy-and-configure-mobility.md#ModCerts) <br/> |로컬 관리자  <br/> |
|[역방향 프록시 구성](deploy-and-configure-mobility.md#ConfigRP) <br/> |로컬 관리자  <br/> |
|[하이브리드 배포를 사용 하 여 이동성에 대 한 자동 검색 구성](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |도메인 관리자  <br/> |
|[모바일 배포 테스트](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[푸시 알림 구성](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[이동성 정책 구성](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
다음 섹션에는 계획 항목을 읽은 것으로 가정 하는 단계가 포함 되어 있습니다. 혼란 스 러 울 경우 해당 위치에서 정보를 자유롭게 확인해 보세요.

> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.
  
## <a name="create-dns-records"></a>DNS 레코드 만들기
<a name="CreateDNSRec"> </a>

이는 비즈니스용 Skype Server 환경의 일부로 이미 포함 되어 있을 수 있지만 자동 검색을 사용 하려면 다음 레코드를 만들어야 합니다.
  
- 조직의 네트워크 내에서 연결 하는 모바일 사용자를 지 원하는 내부 DNS 레코드입니다.
    
- 외부 (또는 공용) DNS 레코드-조직의 네트워크 외부에서 연결 하는 모바일 사용자를 지원 합니다.
    
이러한 레코드는 (호스트) 이름 또는 CNAME 레코드 (여기에 모두 포함 될 필요는 없음) 일 수 있습니다.
  
### <a name="create-an-internal-dns-cname-record"></a>내부 DNS CNAME 레코드 만들기

1. 네트워크에서 **Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹에 속하는 DNS 서버에 로그인 합니다.
    
2. **시작**을 클릭 하 고 **관리 도구** (시작 메뉴를 해제 하는 옵션이 아닌 경우 **검색** 해야 할 수 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.
    
3. 콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버 프런트 엔드 서버에 홈으로 접속 하는 도메인으로 이동 하 고 여기서 **정방향 조회 영역** 을 확장 해야 합니다.
    
4. 다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.
    
   - 프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
5. 이 내용을 적어 둔 후 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 별칭 (CNAME)** 을 선택 합니다.
    
6. **별칭 이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal를 호스트 이름으로 입력 합니다.
    
7. 정규화 된 **도메인 이름 (대상 호스트의 FQDN**)에서 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 싱글 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 FQDN을 입력 하거나 탐색 해야 합니다. 입력 하는 경우 확인을 클릭 합니다.
    
8. 비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대해 정방향 조회 영역에서 새 자동 검색 CNAME 레코드를 만들어야 합니다.
    
### <a name="create-an-external-dns-cname-record"></a>외부 DNS CNAME 레코드 만들기

1. 사용 하 고 있는 공용 DNS 공급자를 알 수 없기 때문에이 단계를 수행 하는 데 도움이 필요 합니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인 하세요.
    
2. 이 시점에서 SIP 도메인은 비즈니스용 Skype 서버용으로 이미 존재 해야 합니다. 이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나 다른 방법으로 엽니다.
    
3. 다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.
    
   - 프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
4. 해당 정보를 찾았으면 **새 별칭 (CNAME)** 을 만들기 위한 옵션을 선택할 수 있습니다.
    
5. 이제 **별칭 이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대 한 lyncdiscover를 입력 해야 합니다.
    
6. 그 다음에는 **대상 호스트의 fqdn**에 입력할 영역이 있으며 위의 3 단계에서 확인 된 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 fqdn 이어야 합니다.
    
7. 여기에 저장 해야 하거나 비즈니스용 Skype 서버 환경에서 각 SIP 도메인의 정방향 조회 영역에 추가 CNAME 레코드를 만들어야 하는 경우에는이 작업을 수행 해야 하지만, 준비가 되 면 업무를 저장 하세요.
    
### <a name="create-an-internal-dns-a-record"></a>내부 DNS A 레코드 만들기

1. 네트워크에서 **Domain Admins** 그룹의 구성원 이거나 **DnsAdmins** 그룹에 속하는 DNS 서버에 로그인 합니다.
    
2. **시작**을 클릭 하 고 **관리 도구** (시작 메뉴를 해제 하는 옵션이 아닌 경우 **검색** 해야 할 수 있음)를 선택한 다음 **dns** 를 클릭 하 여 dns 관리 스냅인을 엽니다.
    
3. 콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버 프런트 엔드 서버에 홈으로 접속 하는 도메인으로 이동 하 고 여기서 **정방향 조회 영역** 을 확장 해야 합니다.
    
4. 다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.
    
   - 프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
5. 이에 대 한 설명이 표시 되 면 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **새 호스트 (A 또는 AAAA)** 를 선택 합니다.
    
6. **이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 대 한 lyncdiscoverinternal를 호스트 이름으로 입력 합니다.
    
7. **IP 주소** 텍스트 상자에 위의 4 단계에서 확인 한 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 내부 웹 서비스 IP 주소를 입력 합니다.
    
8. 이 작업이 완료 되 면 **호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.
    
9. 비즈니스용 Skype 서버 환경에서 지원 되는 각 SIP 도메인에 대 한 새 자동 검색 A 또는 AAAA 레코드를 정방향 조회 영역에서 만들어야 합니다. 이렇게 하려면, 필요한 횟수 만큼 6-8 단계를 반복 합니다.
    
10. 모두 마쳤으면 **완료**를 클릭 합니다.
    
### <a name="create-an-external-dns-a-record"></a>외부 DNS A 레코드 만들기

1. 사용 하 고 있는 공용 DNS 공급자를 알 수 없기 때문에이 단계를 수행 하는 데 도움이 필요 합니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인 하세요.
    
2. 이 시점에서 SIP 도메인은 비즈니스용 Skype 서버용으로 이미 존재 해야 합니다. 이 SIP 도메인에 대 한 **정방향 조회 영역** 을 확장 하거나 다른 방법으로 엽니다.
    
3. 다음 중 어느 것을 사용 하 고 있는지 확인해 주십시오.
    
   - 프런트 엔드 서버 (Standard 또는 Enterprise) 또는 프런트 엔드 풀 () 용 호스트 A 또는 AAAA 레코드
    
   - 디렉터 또는 디렉터 풀에 대 한 모든 호스트 A 또는 AAAA 레코드 (배포에 포함 될 수 있는 선택적 구성)
    
4. 이 정보를 사용 하는 경우 새 호스트를 만드는 옵션을 선택할 수 있습니다 ( **a 또는 AAAA**).
    
5. 이제 **이름을**입력할 수 있으며, 외부 자동 검색 서비스 URL에 대해 여기서 lyncdiscover를 입력 해야 합니다.
    
6. 그 다음에는 **IP Addresss**에 입력할 영역 이어야 하며, 위의 3 단계에서 확인 된 프런트 엔드 풀 (또는 단일 프런트 엔드 서버 또는 디렉터 풀 또는 디렉터)에 대 한 IP가 있어야 합니다.
    
7. 여기에 저장 해야 하거나 비즈니스용 Skype 서버 환경에 대 한 각 SIP 도메인의 정방향 조회 영역에서 추가 A 또는 AAAA 레코드를 만들어야 하는 경우에는이 작업을 수행 해야 하지만, 준비 된 후에는 업무를 저장할 수 있습니다.
    
## <a name="modify-certificates"></a>인증서 수정
<a name="ModCerts"> </a>

인증서를 계획 하는 방법에 대 한 질문이 있는 경우 [비즈니스용 Skype 서버 문서에 대 한 모바일 이동성 계획](../plan-your-deployment/mobility.md) 에서이에 대해 설명 했습니다. 검토가 완료 되 면 다음을 안내 합니다.
  
- 새 인증서가 필요 한가요?
    
- CA (인증 기관)에서 새 인증서 요청
    
- PowerShell을 사용 하 여 현재 위치 인증서를 대체 하 여 업데이트 합니다.
    
- MMC (Microsoft Management Console)에서 인증서 스냅인을 사용 하 여 인증서를 확인 합니다.
    
### <a name="do-i-need-new-certificates"></a>새 인증서가 필요 한가요?

1. 먼저 현재 위치에 있는 인증서와 필요한 항목이 있는지 여부를 확인 해야 할 수 있습니다. 이렇게 하려면 로컬 관리자 계정을 사용 하 여 비즈니스용 Skype 서버에 로그인 해야 합니다. 이 계정에는 이러한 단계 중 일부에 대해 발급 하는 CA (인증 기관)에 대 한 권한도 있어야 할 수도 있습니다.
    
2. 비즈니스용 Skype Server Management Shell을 엽니다 (검색을 사용 하 여 시작 메뉴 또는 작업 표시줄에 고정 되어 있지 않은 경우 찾을 수 있음).
    
3. 업데이트 된 인증서를 추가 하기 전에 어떤 인증서가 할당 되었는지 아는 것이 중요 합니다. 명령에 다음을 입력 합니다.
    
   ```powershell
   Get-CsCertificate
   ```

4. 3 단계의 정보는 사용자에 게 고유 합니다. 여러 작업에 할당 된 단일 인증서가 있는지 또는이를 필요로 하는 다른 구성 요소에 대해 다른 인증서가 할당 되었는지 확인 하려면이를 찾아야 합니다. **Use** 매개 변수는 인증서를 사용 하는 방법을 알려 주는 반면, **지문** 매개 변수는 동일한 인증서 또는 여러 인증서가 있는지 여부를 알려줍니다.
    
5. 계획 섹션에 SAN 항목이 권장 되는 경우에는 좋은 방법입니다. 그렇지 않은 경우 인증 기관에서 새 인증서 또는 구성에 따라 여러 인증서를 요청 해야 합니다.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>CA (인증 기관)에서 새 인증서 또는 인증서 요청

1. 보유 하 고 있는 SAN 항목을 확인 한 후에는 **단일 인증서** (위 단계를 통해 확인 한 후)가 있다는 것을 알고 있으며 필요한 항목이 모두 없는 것을 배웠습니다. CA에 대 한 새로운 인증서 요청이 필요 합니다. 비즈니스용 Skype Server PowerShell을 엽니다.
    
   - 누락 된 자동 검색 서비스 SAN (-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 경우):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다. 예를 들어-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 것이 가능 합니다.
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 또는, 보유 하 고 있는 SAN 항목을 확인 한 후에는 필요한 항목을 모두 갖고 있지 않은 **여러 개의 인증서** 가 있다는 것을 발견 했습니다. CA에 대 한 새로운 인증서 요청이 필요 합니다. 비즈니스용 Skype Server PowerShell을 엽니다.
    
   - 누락 된 자동 검색 서비스 SAN (-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 경우):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 이제 여러 SIP 도메인이 있는 경우 위의 예제와 같이 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용 해야 합니다. DomainName 매개 변수를 사용 하는 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대 한 FQDN을 정의 해야 합니다. 예를 들면 (-Ca 매개 변수를 고유한 인증 기관 경로로 바꾸는 경우):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA에서 새 인증서를 생성 한 후에는 할당 해야 합니다.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 인증서 할당

- 위의 새 인증 필요 사항 섹션에 있는 항목에 따라 다음 중 **하나** 를 실행 해야 합니다.
    
  - 모든 것에 대 한 단일 인증서가 있는 경우 (지문이 동일한 경우) 다음을 실행 해야 합니다.
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 다른 항목에 대 한 인증서가 있다면 (지문이 모두 다름) 대신이를 실행 합니다.
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>MMC (Microsoft Management Console)에서 인증서 보기

1. MMC에 대 한 인증서 스냅인을 사용 하 여 인증서를 확인 하는 옵션이 있습니다. 검색에 MMC를 입력 하면 응용 프로그램 옵션으로 팝업 됩니다.
    
2. 인증서 스냅인을 추가 하려면 **파일**을 클릭 한 다음 **스냅인 추가/제거 ...** (또는 바로 가기 **키 Ctrl + M** 을 사용할 수도 있습니다.) **인증서** 는 왼쪽 창의 옵션이 되며,이 옵션을 선택 하 고 나 서 팝업 창에서 **컴퓨터 계정을** 선택한 다음 **다음**을 클릭 합니다.
    
3. 여전히 팝업 창에 표시 해야 하는 인증서가 있는 컴퓨터에서이 작업을 수행할 수 있으므로, 이렇게 하면 **로컬 컴퓨터** 에서 선택 항목을 유지 합니다. 원격 컴퓨터에서 작업 하는 경우 라디오 단추를 **다른 컴퓨터로** 변경 하 고 해당 컴퓨터의 FQDN을 입력 하거나 **찾아보기** 단추를 사용 하 여 광고를 통해 해당 컴퓨터를 검색 합니다. 컴퓨터를 선택한 후에 준비가 되 면 **마침을** 클릭 하 고 **확인** 으로 MMC에 스냅인을 추가 해야 합니다.
    
4. MMC의 왼쪽 창에서 **인증서** 섹션을 확장 합니다. **개인** 폴더도 확장 하 고 **인증서**를 선택 합니다. 이 저장소의 인증서를 볼 수 있습니다.
    
5. 보려는 인증서를 찾아 마우스 오른쪽 단추로 클릭 한 다음 **열기**를 선택 합니다.
    
    > [!NOTE]
    > 인증서의 종류를 어떻게 알 수 있나요? 이는 팜에 대해 모든 사용자에 게 할당 된 단일 인증서 이거나 기본 웹 서비스 등 다양 한 항목에 대해 여러 인증서가 있을 수 있으며,이 경우 여러 인증서를 확인 해야 합니다. 여러 인증서에는 동일한 지문이 있습니다. 
  
6. **인증서** 보기로 연결한 후에 **세부 정보**를 선택 합니다. 이를 통해 **주체**를 선택 하면 인증서 주체 이름이 표시 되 고 지정 된 제목 이름과 관련 속성이 표시 됩니다.
    
7. 또한 **주체 대체 이름** 항목을 확인 해야 합니다. 다음 중 하나 이상을 찾을 수 있습니다.
    
   - 이 풀의 풀 이름 또는 풀이 아닌 경우 단일 서버 이름입니다.
    
   - 인증서가 할당 된 서버 이름입니다.
    
   - 간단한 URL 레코드 (일반적으로 모임 및 전화 접속)
    
   - 웹 서비스 내부 및 웹 서비스 외부 이름 (예: webpool01.contoso.net, webpool01.contoso.com)-토폴로지 작성기 및 재정의 된 웹 서비스 선택 항목을 기준으로 합니다.
    
   - 이미 할당 된 경우 lyncdiscover. \<sipdomain\> 및 lyncdiscoverinternal. \<레코드\> 를 sipdomain.
    
     둘 이상의 항목을 할당 한 경우 여러 개의 인증서를 확인 해야 합니다 (위의 참고 사항 확인).
    
8. 따라서 lyncdiscover을 찾을 수 있습니다. \<sipdomain\> 및 lyncdiscoverinternal. \<sipdomain\> 레코드가 이미 구성 되어 있습니다. MMC를 닫을 수 있습니다.
    
9. 해당 사용자가 할당 되지 않은 경우에는 새 인증서 요청을 만들어야 합니다 (위 개요). 또는 사후 요청을 설치 해야 합니다 (위의 PowerShell을 다음에 추천).
    
## <a name="configure-the-reverse-proxy"></a>역방향 프록시 구성
<a name="ConfigRP"> </a>

아래 단계는 정확히 팔 로우 할 수 없습니다. 이는 이전 버전의 제품에서 TMG (위협 관리 게이트웨이)를 구성 하는 등의 작업을 수행 하 고, 사용 하지 않은 경우 해당 위치에서 자신만의 버전을 관리 해야 하기 때문입니다.
  
TMG는 Microsoft에서 더 이상 제품으로 제공 되지 않으며 여전히 구성 해야 하는 경우 [Lync Server 2013 단계](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)를 살펴볼 수 있습니다. 그러나 다음 정보는 모든 리버스 프록시에 대해 특정 연습 단계를 제공할 수 없는 경우에도 더 일반적으로 도움이 됩니다.
  
다음과 같은 두 가지 주요 사항을 고려해 야 합니다.
  
- HTTPS를 통해 초기 자동 검색 요청을 진행 하 고 계십니까 (권장)?
    
  - 웹 게시 규칙이 있으면 수정 해야 합니다.
    
  - 웹 게시 규칙이 아직 없는 경우 만들어야 합니다.
    
- HTTP를 통해 초기 자동 검색 요청을 수행 하는 경우에는 해당 규칙도 만들거나 수정 해야 합니다.
    
> [!NOTE]
> **중요** 프록시 시간 초과 값은 배포에 따라 달라 지는 숫자입니다. 배포를 모니터링 하 고 클라이언트에 대 한 최상의 환경을 위해 값을 수정 해야 합니다. 200 보다 낮은 값으로 설정할 수 있습니다. 환경에서 Lync 모바일 클라이언트를 지원 하는 경우에는 시간 제한 값이 900 인 Office 365에서 푸시 알림 시간 제한을 허용 하도록 값을 960로 설정 해야 합니다. 값이 너무 낮을 경우 클라이언트 연결이 끊어지지 않도록 시간 초과 값을 늘려야 하거나, 프록시를 통한 연결이 끊어지면이를 차단 하지만 클라이언트의 연결이 끊긴 후에는 장시간 해제 해야 할 가능성이 높습니다. 환경에 대 한 모니터링 및 기준 지정은 해당 값에 대 한 적절 한 설정을 결정 하는 유일한 올바른 방법입니다.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>외부 자동 검색 SAN 및 URL에 대 한 기존 웹 게시 규칙 수정

1. 역방향 프록시 인터페이스를 엽니다.
    
2. 웹 게시 규칙을 찾고 편집 옵션을 선택 해야 합니다 (리버스 프록시 구성에 따라 메뉴나 탭에 있을 수 있음).
    
3. 이 웹 게시 규칙이 적용 되는 내용을 명시 하는 영역이 있어야 합니다. 수신 사이트 또는 사이트 요청에 대해이 규칙을 수정 해야 합니다. 새 항목을 **추가** 해 보겠습니다.
    
4. 자동 검색 사이트의 이름을 입력 하 고 (사용 하는 예제는 lyncdiscover.contoso.com) 리버스 프록시의 형식에 따라 **확인** 또는 **저장**을 클릭 합니다.
    
5. 자동 검색 하는 SAN 항목이 있는 새 인증서가 있을 수 있습니다. 또한 리버스 프록시의 설정에 따라 함께 설치 하 고 사용 하도록 구성 해야 합니다. 구성이 완료 되 면 모두 저장 해야 합니다.
    
6. 역방향 프록시에 **테스트** 기능이 있는 경우 해당 기능을 사용 하 여 모든 항목이 제대로 작동 하는지 확인 하세요.
    
7. 이제 환경에 디렉터 또는 디렉터 풀이 있는 경우이 단계를 반복 해야 할 수 있습니다 (이는 두 번째 규칙이 있는 것을 의미 함).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>외부 자동 검색 URL에 대 한 웹 게시 규칙 만들기

1. 역방향 프록시 인터페이스를 엽니다.
    
2. 웹 게시 규칙을 만드는 인터페이스에서 위치를 찾고, **새** 또는 **만들기** 옵션을 선택 해야 합니다 (이는 리버스 프록시 구성에 따라 메뉴나 탭에 있을 수 있음). 새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.
    
3. 일반적으로 아래와 같은 정보를 입력 해야 합니다.
    
   - **이름**: 규칙 이름
    
   - **규칙 동작**:이 경우에는 사용자가 리버스 프록시를 통과 **하도록 허용** 하는 규칙입니다.
    
   - 선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.
    
   - 이는 외부 액세스를 위해 **SSL** 이어야 하며 해당 옵션을 선택 합니다.
    
   - **내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치 (또는 사용자가 있는 경우 디렉터 풀의 부하 분산 장치)에 대 한 fqdn을 입력 해야 하는 경우 예제는 sfb_pool01입니다.
    
   - 게시할 경로로 * ** / **를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.
    
   - **공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 나타납니다. 입력할 수 있는 위치는 다음과 같습니다.
    
   - **요청을 수락**하지만 도메인 이름 이어야 합니다.
    
   - **이름**에는 **lyncdiscover** 를 입력 해야 합니다. <sipdomain>(외부 자동 검색 서비스 URL) 이제 프런트 엔드 풀에서 외부 웹 서비스 URL에 대 한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대 한 FQDN을 입력 해야 합니다 (예: lyncwebextpool01.contoso.com).
    
   - **경로** 옵션이 있으므로 * 여기에 *를 입력 ** / **해야 합니다.
    
   - 최신 공용 인증서를 사용 하 여 **SSL 수신기** 를 선택 해야 합니다.
    
   - **인증 위임은** **위임 없음으로**설정 해야 하지만 직접 **클라이언트 인증은 허용 되어야 합니다** .
    
   - **모든 사용자**에 게 규칙을 설정 해야 합니다.
    
   - 이 규칙을 만드는 데 필요한 모든 정보를 사용 하 여 계속 진행할 수 있습니다.
    
4. **원본 호스트 헤더가** 전달 되었는지 확인 해야 합니다.
    
5. **웹 서버** 포트만 설정 해야 하므로 다음을 수행 해야 합니다.
    
   - **요청을 HTTP 포트로 리디렉션** 하 고 포트 번호는 **8080**이어야 합니다.
    
   - **요청을 SSL 포트로 리디렉션** 하 고 포트 번호는 **4443**이어야 합니다.
    
6. 모든 것이 구성 된 경우에는이를 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>포트 80에 대 한 웹 게시 규칙 만들기 (선택 사항)

1. 역방향 프록시 인터페이스를 엽니다.
    
2. 웹 게시 규칙을 만드는 인터페이스에서 위치를 찾고, **새** 또는 **만들기** 옵션을 선택 해야 합니다 (이는 리버스 프록시 구성에 따라 메뉴나 탭에 있을 수 있음). 새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.
    
3. 일반적으로 아래와 같은 정보를 입력 해야 합니다.
    
   - **이름**: 규칙 이름
    
   - **규칙 동작**:이 경우에는 사용자가 리버스 프록시를 통과 **하도록 허용** 하는 규칙입니다.
    
   - 선택 하는 **게시** 규칙이 나 옵션은 **단일 웹 사이트 또는 부하 분산 장치**입니다.
    
   - 이 연결을 통해 **게시 된 웹 서버 또는 팜에 연결 하려면 보안이 되지 않는**것이 필요 합니다.
    
   - **내부 게시용**경로를 게시 하 고 프런트 엔드 풀의 부하 분산 장치의 **VIP 주소** 에 대 한 FQDN을 입력 해야 하는 경우 예제는 sfb_pool01입니다.
    
   - 게시할 경로로 * ** / **를 입력 해야 하지만, **원본 호스트 헤더도 전달**해야 합니다.
    
   - **공용 또는 외부 이름** 세부 정보 또는 정보에 대 한 옵션이 나타납니다. 입력할 수 있는 위치는 다음과 같습니다.
    
   - **요청을 수락**하지만 도메인 이름 이어야 합니다.
    
   - **이름**에는 **lyncdiscover** 를 입력 해야 합니다. <sipdomain>(외부 자동 검색 서비스 URL)
    
   - **경로** 옵션이 있으므로 * 여기에 *를 입력 ** / **해야 합니다.
    
   - 웹 수신기를 선택 하거나 리버스 프록시에서 만들 수 있도록 허용 해야 합니다.
    
   - **인증 위임은** **위임 없음으로**설정 해야 하지만 직접 클라이언트 인증은 허용 **되지 않습니다** .
    
   - **모든 사용자**에 게 규칙을 설정 해야 합니다.
    
   - 이 규칙을 만드는 데 필요한 모든 정보를 사용 하 여 계속 진행할 수 있습니다.
    
4. **웹 서버** 포트를 설정 해야 하는 경우 다음을 수행 해야 합니다.
    
   - **요청을 HTTP 포트로 리디렉션** 하 고 포트 번호는 **8080**이어야 합니다.
    
   - **요청을 SSL 포트로 리디렉션** 하 고 포트 번호는 **4443**이어야 합니다.
    
5. 모든 것이 구성 된 경우에는이를 저장 하거나 적용 한 다음 규칙을 테스트 해야 합니다.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>하이브리드 배포를 사용 하 여 이동성에 대 한 자동 검색 구성
<a name="ConfigAutoD"> </a>

비즈니스용 Skype Server의 하이브리드 환경은 온-프레미스 및 O365 환경을 결합 하는 환경입니다. 하이브리드 환경에서 비즈니스용 Skype 서버를 사용 하는 경우 자동 검색 서비스가 이러한 환경 중 하나에서 사용자를 찾을 수 있어야 합니다.
  
모바일 클라이언트가 사용자가 위치한 위치를 검색할 수 있도록 하려면 새 URL (uniform resource locator)을 사용 하 여 자동 검색 서비스를 구성 해야 합니다. 단계는 다음과 같습니다.
  
1. 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 다음을 실행 하 여 비즈니스용 Skype 서버 환경에 대 한 **Proxyfqdn** 특성 값을 가져옵니다.
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 계속 해 서 셸 창에서 다음을 실행 합니다.
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    여기서 [identity]는 공유 SIP 주소 공간의 도메인 이름으로 대체 됩니다.
    
## <a name="test-your-mobility-deployment"></a>모바일 배포 테스트
<a name="TestMobility"> </a>

비즈니스용 Skype Server Mobility Service 및 비즈니스용 Skype 서버 자동 검색 서비스를 배포한 후에는 테스트 트랜잭션을 실행 하 여 배포의 작동을 확인할 수 있습니다. **테스트-CsUcwaConference** 를 실행 하 여 두 사용자가 회의를 만들고 참가 하 고 통신 하는 기능을 테스트할 수 있습니다. 이 테스트를 수행 하려면 두 명의 사용자 (실제 또는 테스트)와 전체 자격 증명이 필요 합니다. 이 명령은 Lync Server 2013 클라이언트는 물론 비즈니스용 Skype 클라이언트 모두에 대해 작동 합니다.
  
비즈니스용 Skype Server 2015의 Lync Server 2010 클라이언트의 경우 테스트 하려면 **CsMcxP2PIM** 을 실행 해야 합니다. Lync Server 2010 사용자는 여전히 실제 사용자 또는 미리 정의 된 테스트 사용자 여야 하며, 암호 자격 증명이 필요 합니다.

> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>비즈니스용 Skype 및 Lync 2013 모바일 클라이언트에 대 한 회의 테스트

1. **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 되어 있는 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.
    
2. **비즈니스용 Skype Server Management Shell** 을 시작 하세요 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동 하 고 선택할 수 있습니다.)
    
3. 명령줄에 다음을 입력 합니다.
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   스크립트에서 자격 증명을 설정 하 고 테스트 cmdlet에 전달할 수도 있습니다. 이에 대 한 예는 다음과 같습니다.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Lync 2010 모바일 클라이언트에 대 한 회의 테스트

> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.

1. **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 되어 있는 컴퓨터에서 **csadministrator** 역할의 구성원으로 로그온 합니다.
    
2. **비즈니스용 Skype Server Management Shell** 을 시작 하세요 (검색에 이름을 입력 하거나 **모든 프로그램** 으로 이동 하 고 선택할 수 있습니다.)
    
3. 명령줄에 다음을 입력 합니다.
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   스크립트에서 자격 증명을 설정 하 고 테스트 cmdlet에 전달할 수도 있습니다. 이에 대 한 예는 다음과 같습니다.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

명령 절차를 더 자세히 검토 하기 위해 [CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 및 [test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)를 확인할 수 있습니다.
  
## <a name="configure-for-push-notifications"></a>푸시 알림 구성
<a name="ConfigPush"> </a>

배지, 아이콘 또는 알림 형식의 푸시 알림은 Skype 또는 Lync 앱이 비활성화 된 경우에도 모바일 장치로 전송 될 수 있습니다. 그러나 푸시 알림은 무엇입니까? 이러한 알림은 새로운 또는 부재 중 메신저 대화 초대 또는 받은 보이스 메일 등의 이벤트 알림입니다. 비즈니스용 Skype 서버 모바일 서비스는이 알림을 클라우드 기반 비즈니스용 Skype Server 푸시 알림 서비스로 보내 Windows Phone 사용자를 위한 MSNS (Microsoft 푸시 알림 서비스)에 알림을 보냅니다.
  
이 기능은 Lync Server 2013에서 변경 되지 않았지만 비즈니스용 Skype 서버를 사용 하는 경우 다음을 수행 하는 것이 좋습니다.
  
- 비즈니스용 Skype Server Edge 서버의 경우 새 호스팅 공급자, Microsoft 비즈니스용 Skype Online을 추가 하 고 조직과 비즈니스용 Skype Online 간 호스팅 공급자 페더레이션을 설정 합니다.
    
- **Set-CsPushNotificationConfiguration** cmdlet을 실행 하 여 푸시 알림을 사용 하도록 설정 합니다. 기본적으로 푸시 알림은 꺼져 있습니다.
    
- 페더레이션 구성 및 푸시 알림을 테스트 합니다.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>푸시 알림에 대 한 비즈니스용 Skype Edge 서버 구성

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 비즈니스용 Skype 서버 online 호스팅 공급자를 추가 합니다.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   예를 들면 다음과 같습니다.
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 단일 호스팅 공급자에 두 개 이상의 페더레이션 관계를 사용할 수 없습니다. 따라서 sipfed.online.lync.com와 페더레이션 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 id가 SkypeOnline 이외의 다른 호스팅 공급자를 사용 하는 경우에도이를 추가 해야 합니다. 
  
4. 비즈니스용 Skype Online에서 조직과 푸시 알림 서비스 간에 호스팅 공급자 페더레이션을 설정 합니다. 명령줄에 다음을 입력 해야 합니다.
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>푸시 알림 사용

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 푸시 알림 사용:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 페더레이션 사용:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>페더레이션 및 푸시 알림 테스트

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 페더레이션 구성을 테스트 합니다.
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 푸시 알림 테스트:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>이동성 정책 구성
<a name="ConfigMob"> </a>

비즈니스용 Skype 서버에서 모바일 서비스를 사용할 수 있는 사용자, 작업 시간, VoIP (voice over IP) 또는 비디오를 비롯 하 여 VoIP 또는 비디오에 WiFi가 필요한 지 여부를 결정 하는 기능이 있습니다. 회사 전화를 통해 전화를 통해 휴대 전화는 전화를 걸고 받을 때 휴대폰 번호 대신 회사 전화번호를 사용할 수 있습니다. 줄의 다른 쪽 끝에 있는 사용자는 휴대폰 번호를 볼 수 없으며,이로 인해 모바일 사용자가 발신 전화 요금을 방지할 수 있습니다. VoIP와 비디오가 설정 되 면 사용자는 VoIP 통화와 동영상을 할 수 있습니다. WiFi 사용 설정에 따라 사용자의 모바일 장치에서 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용 해야 하는지 여부가 결정 됩니다.
  
이동성, 업무에 대 한 통화, VoIP 및 비디오 기능은 기본적으로 사용 하도록 설정 되어 있습니다. VoIP 및 비디오에 WiFi를 요구 하는 설정을 사용할 수 없습니다. 관리자는 전역, 사이트별 또는 사용자를 기준으로 변경할 수 있습니다.
  
모바일 기능을 사용 하 고 작업을 통해 통화할 수 있으려면 사용자가 다음과 같이 해야 합니다.
  
- 비즈니스용 Skype 서버 사용
    
- 엔터프라이즈 음성에 사용 합니다.
    
- **EnableMobility** 옵션이 **True**로 설정 된 이동성 정책이 할당 되었습니다.
    
사용자가 작업을 통해 통화를 사용할 수 있도록 하려면 다음도 수행 해야 합니다.
  
- **전화의 동시 신호음 사용** 옵션이 선택 된 음성 정책이 할당 되었습니다.
    
- **EnableOutsideVoice** 가 **True**로 설정 된 이동성 정책을 할당 했습니다.
    
> [!NOTE]
> Enterprise Voice를 사용 하도록 설정 하지 않은 사용자는 모바일 장치를 사용 하 여 Skype VoIP 통화를 하거나, 해당 옵션이 연결 된 음성 정책에 대해 설정 된 경우 클릭 하 여 링크를 사용 하 여 회의에 참가할 수 있습니다. 과. 자세한 내용은 계획 항목을 참조 하세요. 
  
### <a name="modify-global-mobility-policy"></a>전역 이동성 정책 수정

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 다음을 입력 하 여 업무에 대 한 액세스를 해제 하 고 회사의 전화를 통해 통화 하세요.
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Mobility에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 끌 수 있습니다. 그러나 작업을 통해 통화를 끄지 않고는 이동성을 해제할 수 없습니다. 
  
    자세한 내용은 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)를 참조 하세요.
    
### <a name="modify-mobility-policy-by-site"></a>사이트별 이동성 정책 수정

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 사이트 수준 정책을 만들고, VoIP 및 비디오를 끄고 IP 오디오에 WiFi 필요를 사용 하도록 설정 하 고, 사이트 별로 IP 비디오에 WiFi를 요구할 수 있습니다. 입력할
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    [새로운 기능](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)에 대해 자세히 CsMobilityPolicy.
    
### <a name="modify-mobility-policy-by-user"></a>사용자별 이동성 정책 수정

1. **Csadministrator** 역할의 구성원 인 계정을 사용 하 여 **비즈니스용 Skype Server Management Shell** 및 **ocscore** 설치 된 컴퓨터에 로그온 합니다.
    
2. **비즈니스용 Skype 서버 관리 셸을**시작 합니다.
    
3. 사용자 수준 이동성 정책을 만들고, 이동성을 사용 하지 않도록 설정 하 고, 사용자의 작업을 통해 전화를 겁니다. 입력할
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    예제 데이터가 있는 추가 예:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Mobility에 대 한 액세스를 해제 하지 않고 작업을 통해 통화를 끌 수 있습니다. 그러나 작업을 통해 통화를 끄지 않고는 이동성을 해제할 수 없습니다. 
  

