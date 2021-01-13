---
title: 비즈니스용 Skype 서버 모바일 배포 및 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 이동성 기능을 활용할 수 있도록 기존 비즈니스용 Skype 서버 설치를 모바일 서비스를 사용하도록 구성하는 단계를 단계에 대해 다단계를 수행합니다.
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820898"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>비즈니스용 Skype 서버 모바일 배포 및 구성  
 
이 문서에서는 모바일 장치에서 비즈니스용 Skype 서버 이동성 기능을 활용할 수 있도록 기존 비즈니스용 Skype 서버 설치를 모바일 서비스를 사용하도록 구성하는 단계를 단계에 대해 다단계를 수행합니다.
  
비즈니스용 [Skype](../plan-your-deployment/mobility.md) 서버의 모바일 계획 문서를 검토한 경우 아래 단계를 진행하여 비즈니스용 Skype 서버 환경에 Mobility을 배포할 수 있습니다. 단계는 다음과 같습니다(이 표에 사용 권한 목록 포함).
  
|**작업 단계**|**사용 권한**|
|:-----|:-----|
|[DNS 레코드 만들기](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[인증서 수정](deploy-and-configure-mobility.md#ModCerts) <br/> |로컬 관리자  <br/> |
|[역방향 프록시 구성](deploy-and-configure-mobility.md#ConfigRP) <br/> |로컬 관리자  <br/> |
|[하이브리드 배포를 통해 모바일에 대한 자동Iscover 구성](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[모바일 배포 테스트](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[푸시 알림 구성](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[모바일 정책 구성](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
다음 모든 섹션에는 계획 항목을 읽었다고 가정하는 단계가 포함되어 있습니다. 혼란스러울 경우 정보를 자유롭게 확인할 수 있습니다.

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
## <a name="create-dns-records"></a>DNS 레코드 만들기
<a name="CreateDNSRec"> </a>

이러한 레코드가 비즈니스용 Skype 서버 환경의 일부로 이미 있을 수 있지만 자동 검색이 작동하려면 다음 레코드를 만들어야 합니다.
  
- 조직 네트워크 내에서 연결하는 모바일 사용자를 지원하는 내부 DNS 레코드입니다.
    
- 조직의 네트워크 외부에서 연결하는 모바일 사용자를 지원하기 위한 외부(또는 공용) DNS 레코드입니다.
    
이러한 레코드는 A(호스트) 이름 또는 CNAME 레코드일 수 있습니다(둘 다 만들지 않은 경우 여기에 있는 모든 단계만 포함).
  
### <a name="create-an-internal-dns-cname-record"></a>내부 DNS CNAME 레코드 만들기

1. **Domain Admins** 그룹 또는 **DnsAdmins** 그룹의 구성원인 네트워크의 DNS 서버에 로그인합니다.
    
2. 시작, 관리  도구 선택(시작  메뉴의 옵션이 아닌 경우 검색해야 할 수 있습니다)을 클릭한 다음 **DNS를** 클릭하여 DNS 관리 스냅인을 열 수 있습니다. 
    
3. 콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버가 있는 도메인으로 이동하여 정방 검색 영역도 확장해야 **합니다.**
    
4. 다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.
    
   - 프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드
    
   - Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)
    
5. 이를 확인한 후 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 메뉴에서 **새 별칭(CNAME)을** 선택합니다.
    
6. 별칭 **이름** 텍스트 상자에 내부 자동 검색 서비스 URL에 호스트 이름의 lyncdiscoverinternal을 입력합니다.
    
7. 대상 호스트의 **FQDN(FQDN)에서** 위 4단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)에 대한 내부 웹 서비스 FQDN을 입력하거나 찾아야 합니다. 입력할 때 확인을 클릭합니다.
    
8. 비즈니스용 Skype 서버 환경에서 지원되는 각 SIP 도메인에 대한 정방 검색 영역의 새 자동 검색 CNAME 레코드를 만들어야 합니다.
    
### <a name="create-an-external-dns-cname-record"></a>외부 DNS CNAME 레코드 만들기

1. 이러한 단계는 일반적입니다. 사용 중일 수 있는 공용 DNS 공급자를 알 수 없지만 여전히 도움이 될 것입니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인하세요.
    
2. 이때 비즈니스용 Skype 서버에 대한 SIP 도메인이 이미 존재해야 합니다. 이 SIP **도메인에** 대한 정방 검색 영역 확장 또는 열립니다.
    
3. 다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.
    
   - 프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드
    
   - Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)
    
4. 해당 정보가 있는 경우 새 별칭(CNAME)을 만들기 위한 옵션을 선택할 수 **있습니다.**
    
5. 이제 별칭 이름을 입력할 수 있습니다. 외부 자동iscover 서비스 URL에 대해 여기에 lyncdiscover를 입력해야 합니다. 
    
6. 다음으로 대상 호스트의 FQDN에 입력할 영역이 있습니다. 이 영역은 위의 3단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)의 **FQDN이** 되거나,
    
7. 여기서 저장해야 할 수도 있습니다. 또는 비즈니스용 Skype 서버 환경의 각 SIP 도메인의 정방 검색 영역으로 추가 CNAME 레코드를 만들어야 하는 경우 이렇게 해야 하지만 준비가 된 후 작업을 저장합니다.
    
### <a name="create-an-internal-dns-a-record"></a>내부 DNS A 레코드 만들기

1. **Domain Admins** 그룹 또는 **DnsAdmins** 그룹의 구성원인 네트워크의 DNS 서버에 로그인합니다.
    
2. 시작, 관리  도구 선택(시작  메뉴의 옵션이 아닌 경우 검색해야 할 수 있습니다)을 클릭한 다음 **DNS를** 클릭하여 DNS 관리 스냅인을 열 수 있습니다. 
    
3. 콘솔 창의 왼쪽 창에서 비즈니스용 Skype 서버의 프런트 엔드 서버가 있는 도메인으로 이동하여 정방 검색 영역도 확장해야 **합니다.**
    
4. 다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.
    
   - 프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드
    
   - Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)
    
5. 이를 적어 두면 SIP 도메인 이름을 마우스 오른쪽 단추로 클릭한 다음 메뉴에서 새 **호스트(A 또는 AAAA)를** 선택합니다.
    
6. 이름 **텍스트** 상자에 내부 자동 검색 서비스 URL에 호스트 이름의 lyncdiscoverinternal을 입력합니다.
    
7. IP **주소 텍스트** 상자에 위의 4단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)의 내부 웹 서비스 IP 주소를 입력합니다.
    
8. 이 완료되면 호스트 추가를 클릭한 다음 확인을 **클릭합니다.**
    
9. 비즈니스용 Skype 서버 환경에서 지원되는 각 SIP 도메인에 대한 정방 검색 영역의 새 자동 검색 A 또는 AAAA 레코드를 만들어야 합니다. 이 작업을 수행하려면 필요에 따라 6-8단계를 반복합니다.
    
10. 완료되면 완료를 **클릭합니다.**
    
### <a name="create-an-external-dns-a-record"></a>외부 DNS A 레코드 만들기

1. 이러한 단계는 일반적입니다. 사용 중일 수 있는 공용 DNS 공급자를 알 수 없지만 여전히 도움이 될 것입니다. 새 DNS 레코드를 만들 수 있는 계정으로 공용 DNS 공급자에 로그인하세요.
    
2. 이때 비즈니스용 Skype 서버에 대한 SIP 도메인이 이미 존재해야 합니다. 이 SIP **도메인에** 대한 정방 검색 영역 확장 또는 열립니다.
    
3. 다음 중 어떤 것이 필요한지 잠시 시간을 내어 봐야 합니다.
    
   - 프런트 엔드 서버(Standard 또는 Enterprise) 또는 프런트 엔드 풀에 대한 호스트 A 또는 AAAA 레코드
    
   - Director 또는 Director 풀에 대한 모든 호스트 A 또는 AAAA 레코드(배포에 사용할 수 있는 선택적 구성)
    
4. 해당 정보가 있는 경우 새 호스트 A 또는 **AAAA를** 만들기 위한 옵션을 선택할 수 있습니다.
    
5. 이제 이름을 입력할 수 있습니다. 외부 자동iscover 서비스 URL에 대해 여기에 lyncdiscover를 입력해야 합니다.
    
6. 다음으로 IP 주소에 입력할 영역이 있습니다. 이 영역은 위의 3단계에서 식별된 프런트 엔드 풀(또는 단일 프런트 엔드 서버 또는 Director 풀 또는 Director)의 **IP가** 되거나,
    
7. 여기서 저장해야 할 수도 있습니다. 또는 비즈니스용 Skype 서버 환경에 대한 각 SIP 도메인의 정방 지원 영역으로 추가 A 또는 AAAA 레코드를 만들어야 하는 경우 이 작업을 해야 하지만 준비가 된 후 작업을 저장합니다.
    
## <a name="modify-certificates"></a>인증서 수정
<a name="ModCerts"> </a>

인증서 계획에 대한 질문이 있는 경우 비즈니스용 Skype 서버의 모바일 계획 문서에 [설명되어](../plan-your-deployment/mobility.md) 있습니다. 검토한 후 다음을 진행합니다.
  
- 새 인증서가 필요한가요?
    
- CA(인증 기관)에서 새 인증서 요청
    
- PowerShell을 사용하여 대체 인증서로 인치 인증서를 업데이트합니다.
    
- MMC(Microsoft Management Console)에서 인증서 스냅인을 사용하여 인증서 확인
    
### <a name="do-i-need-new-certificates"></a>새 인증서가 필요한가요?

1. 먼저 현재 있는 인증서와 해당 인증서에 필요한 항목이 있는지 여부를 확인하고 확인해야 할 수 있습니다. 이를 위해 로컬 관리자 계정으로 비즈니스용 Skype 서버에 로그인해야 합니다. 이 계정은 또한 이러한 단계 중 일부에 대해 발급 CA(인증 기관)에 대한 권한이 필요할 수도 있습니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 열고(시작 메뉴 또는 작업 표시줄에 고정되지 않은 경우 검색을 사용하여 찾을 수 있습니다).
    
3. 업데이트된 인증서를 추가하기 전에 할당된 인증서를 반드시 알아야 합니다. 따라서 명령에 다음을 입력합니다.
    
   ```powershell
   Get-CsCertificate
   ```

4. 3단계의 정보는 고유합니다. 여러 가지에 대해 할당된 단일 인증서가 있는지 또는 인증서가 필요한 다른 구성 요소에 대해 다른 인증서가 할당되어 있는지 여부를 확인하려면 이를 살펴보아야 합니다. Use  매개 변수는 인증서의 사용 방법을 알려 **주며, Thumbprint** 매개 변수는 인증서가 모두 동일한 인증서인지 또는 여러 인증서인지를 알 수 있습니다.
    
5. 계획 섹션에서 권장되는 SAN 항목이 있는 경우 좋습니다. 그렇지 않은 경우 인증 기관에서 새 인증서 또는 구성에 따라 여러 인증서를 요청해야 합니다.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>CA(인증 기관)에서 새 인증서 또는 인증서 요청

1. 어떤 SAN 항목이 필요한지 확인한 후 위의 단계를 통해  확인한 후 단일 인증서가 있으며 필요한 항목이 모두 없는 것을 알 수 있습니다. CA에 새 인증서 요청을 만들어야 합니다. 비즈니스용 Skype 서버 PowerShell을 여는 경우:
    
   - 누락된 자동iscover 서비스 SAN의 경우(-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 이제 SIP 도메인이 여러 개 있는 경우 위의 예와 같은 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용해야 합니다. DomainName 매개 변수를 사용할 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대한 FQDN을 정의해야 합니다. 예를 들면 다음과 같습니다(-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기).
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. 또는 어떤 SAN 항목이 있는지 확인한 후 필요한 모든  항목이 없는 인증서가 여러 개 있는 것을 발견했습니다. CA에 새 인증서 요청을 만들어야 합니다. 비즈니스용 Skype 서버 PowerShell을 여는 경우:
    
   - 누락된 자동iscover 서비스 SAN의 경우(-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 이제 SIP 도메인이 여러 개 있는 경우 위의 예와 같은 AllSipDomain 매개 변수를 사용할 수 없습니다. 대신 DomainName 매개 변수를 사용해야 합니다. DomainName 매개 변수를 사용할 경우 lyncdiscoverinternal 및 lyncdiscover 레코드에 대한 FQDN을 정의해야 합니다. 예를 들면 다음과 같습니다(-Ca 매개 변수를 자체 인증 기관 경로로 바꾸기).
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA에서 새 인증서를 생성한 후 할당해야 합니다.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 인증서 할당

- 위의 Do I need new certifications(Do I need new  certifications) 섹션에서 찾은 바와 같이 다음 중 하나를 실행해야 합니다.
    
  - 모든(지문이 동일)에 대해 단일 인증서가 있는 경우 다음을 실행해야 합니다.
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 다른 인증서가 있는 경우(지문이 모두 다를 경우) 대신 이 인증서를 실행합니다.
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>MMC(Microsoft Management Console)에서 인증서 보기

1. MMC에 대한 인증서 스냅인을 사용하여 인증서를 볼 수 있습니다. MMC를 검색에 입력하기만 하면 응용 프로그램 옵션으로 팝업됩니다.
    
2. 인증서 스냅인을 추가하려면 파일을 클릭한 다음 스냅인 **추가/제거...를** 클릭해야 합니다(또는 바로 가기 **키 Ctrl+M도** 작동). **왼쪽 창에서** 인증서를 선택하고 팝업 창에서 컴퓨터 계정을  선택한 다음 다음으로 인증서를 선택할 수 **있습니다.**
    
3. 여전히 팝업 창에서 보아야 하는 인증서가 있는 컴퓨터에서 이 작업을 수행하고 있으므로 로컬 컴퓨터에서 선택을 그대로 두십시오.  원격 컴퓨터에서 작업하는 경우 라디오 단추를 다른  컴퓨터로 변경한 다음 해당 컴퓨터의 FQDN을 입력하거나 찾아보기 단추를 사용하여 AD를 통해 해당 컴퓨터를 검색합니다.  컴퓨터를 선택한 후 준비되면 **마친** 다음 MMC에  스냅인을 추가하려면 확인을 클릭해야 합니다.
    
4. MMC의 왼쪽 창에서 인증서 섹션을 확장합니다.  개인 **폴더도** 확장한 다음 **인증서를 선택합니다.** 이렇게 하면 이 저장소에서 인증서를 볼 수 있습니다.
    
5. 보하려는 인증서를 찾아 마우스 오른쪽 단추로 클릭한 다음 열기 를 **선택해야 합니다.**
    
    > [!NOTE]
    > 인증서를 어떻게 알 수 있나요? 팜의 모든 인증서에 할당된 단일 인증서 또는 기본, 내부 웹 서비스 등 여러 가지에 대해 여러 인증서가 있을 수 있습니다. 이 경우 여러 인증서를 찾아야 할 수 있습니다. 여러 인증서의 지문이 동일합니다. 
  
6. 인증서 보기를 확인한  후 세부 **정보를 선택하십시오.** 이렇게 하면 주체 선택 시 인증서 주체 이름을 볼 수 있으며 **할당된** 주체 이름 및 관련 속성이 표시됩니다.
    
7. 주체 대체 이름 **항목도 확인해야** 합니다. 다음 중 하나 이상을 찾을 수 있습니다.
    
   - 이 풀의 풀 이름 또는 풀이 아닌 경우 단일 서버 이름입니다.
    
   - 인증서가 할당된 서버 이름입니다.
    
   - 단순 URL 레코드(일반적으로 meet 및 dialin)
    
   - 토폴로지 작성기 및 과다하게 라이선딩된 웹 서비스 선택에 따라 웹 서비스 내부 및 웹 서비스 외부 이름(예: webpool01.contoso.net, webpool01.contoso.com)입니다.
    
   - 이미 할당된 경우 lyncdiscover입니다.\<sipdomain\> 및 lyncdiscoverinternal.\<sipdomain\> 레코드를 기록합니다.
    
     할당된 인증서가 두 개 이상 있는 경우 여러 인증서를 확인해야 합니다(위의 참고 사항 확인).
    
8. 따라서 lyncdiscover를 찾으면\<sipdomain\> 및 lyncdiscoverinternal.\<sipdomain\> 레코드를 이미 구성했습니다. MMC를 닫을 수 있습니다.
    
9. 할당되지 않은 경우 새 인증서 요청을 만들거나(위에 설명된) 요청 후 설치해야 합니다(위의 PowerShell에 대해 다음을 권장).
    
## <a name="configure-the-reverse-proxy"></a>역방향 프록시 구성
<a name="ConfigRP"> </a>

아래 단계는 정확히 따르지 않습니다. 이전 버전의 제품에서는 TMG(Threat Management Gateway) 구성과 같은 작업을 진행해 보며, TMG를 사용하지 않는 경우 해당 버전부터 직접 작업해야 합니다.
  
Microsoft는 더 이상 제품으로 TMG를 제공하지 않습니다. TMG를 구성해야 하는 경우 [Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)단계를 볼 수 있습니다. 그러나 다음 정보는 모든 역방향 프록시에 대해 특정 안내 단계를 제공할 수 없는 경우에도 일반적으로 유용하게 사용할 수 있습니다.
  
다음과 같은 두 가지 주요 고려 사항들을 고려해야 합니다.
  
- HTTPS를 통해 초기 자동iscover 요청을 수행하고 있습니까(권장)
    
  - 웹 게시 규칙이 있는 경우 해당 규칙을 수정해야 합니다.
    
  - 아직 웹 게시 규칙이 없는 경우 만들어야 합니다.
    
- HTTP를 통해 초기 자동Iscover 요청을 수행하고 있는 경우 해당 규칙을 만들거나 수정해야 합니다.
    
> [!NOTE]
> **중요** 프록시 시간 아웃 값은 배포마다 다른 숫자입니다. 배포를 모니터링하고 클라이언트에 가장 적합한 환경을 위해 값을 수정해야 합니다. 값을 200으로 낮게 설정할 수 있습니다. 환경에서 Lync 모바일 클라이언트를 지원하는 경우 시간 한계 값이 900인 Office 365의 푸시 알림 시간 아웃을 허용하도록 값을 960으로 설정해야 합니다. 값이 너무 낮을 때 클라이언트 연결이 끊어지지 않도록 시간 종료 값을 늘려야 합니다. 프록시를 통한 연결이 끊어지지는 않지만 클라이언트 연결이 끊어진 후 오래 지워지지 않을 경우 이 수를 낮출 수 있습니다. 환경에 일반적인 기준을 모니터링하고 기준을 세우는 것만이 이 값에 적합한 설정을 결정하는 유일한 방법입니다.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>외부 자동 검색 SAN 및 URL에 대한 기존 웹 게시 규칙 수정

1. 역방향 프록시 인터페이스를 열 수 있습니다.
    
2. 웹 게시 규칙을 찾아 편집 옵션을 선택해야 합니다(역방향 프록시 구성에 따라 메뉴 또는 탭에 있을 수 있습니다).
    
3. 이 웹 게시 규칙이 적용되는 영역을 사용할 수 있습니다. 들어오는 사이트 또는 사이트에 대한 요청에 대해 이 규칙을 수정해야 합니다. 새 항목을 **추가합니다.**
    
4. 자동 검색 사이트의 이름(예: lyncdiscover.contoso.com)을 입력하고 역방향 프록시의  형식에 따라 확인 또는 저장을 클릭합니다. 
    
5. 자동iscover SAN 항목이 있는 새 인증서가 있을 수 있습니다. 역방향 프록시의 설정에 따라 사용하도록 설치 및 구성해야 합니다. 구성이 완료되면 모든 것을 저장해야 합니다.
    
6. 역방향 프록시에  테스트 기능이 있는 경우 이를 사용하여 모든 기능이 제대로 작동하도록 하십시오.
    
7. 이제 환경에 Director 또는 Director 풀이 있는 경우 이러한 단계를 반복해야 할 수 있습니다(두 번째 규칙이 있는 경우).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>외부 자동 검색 URL에 대한 웹 게시 규칙 만들기

1. 역방향 프록시 인터페이스를 열 수 있습니다.
    
2. 인터페이스에서 웹 게시 규칙을 만들고 새로 만들기 또는 만들기 옵션을  선택해야  합니다(역방향 프록시 구성에 따라 메뉴 또는 탭에 있을 수 있습니다). 새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.
    
3. 일반적으로 다음 정보를 입력해야 합니다.
    
   - **이름**: 규칙의 이름
    
   - **규칙 동작:** 이 경우 허용  규칙인 경우 역방향 프록시를 통과하도록 허용합니다.
    
   - 선택한 **게시** 규칙 또는 옵션은 단일 웹 사이트 또는 부하 부하 조정 **서비스입니다.**
    
   - 외부 액세스에 **대해 SSL이** 필요한 경우 해당 옵션을 선택합니다.
    
   - 내부 게시에 대한 경로를 게시하고 프런트 엔드 풀의 부하 균형 조정에 외부 웹 서비스에 대한 FQDN을 입력해야 합니다(또는 이 경우 Director 풀의 부하 균형 조정 서비스의 FQDN). 예를 들어 sfb_pool01.contoso.local을 예로 들 수 있습니다.
    
   - _를 게시할 경로로 입력해야 하지만 원래 호스트 **/\\** 헤더를 _*전달해야 합니다.**.
    
   - 공개 또는 외부 이름 세부 정보 또는 정보에 **대한** 옵션이 제공됩니다. 입력할 수 있는 위치입니다.
    
   - **요청을 수락하지만** 도메인 이름에 대한 것이 좋습니다.
    
   - 이름의 경우 **lyncdiscover를 입력해야 합니다.** <sipdomain> 이 URL은 외부 자동iscover 서비스 URL입니다. 이제 프런트 엔드 풀에서 외부 웹 서비스 URL에 대한 규칙을 만드는 경우 프런트 엔드 풀의 외부 웹 서비스에 대한 FQDN을 입력해야 합니다(예: lyncwebextpool01.contoso.com).
    
   - 경로 옵션이  있으며 여기에 **/\\** _를 입력해야 합니다.
    
   - 최신 공용 인증서를 사용 하 여 _ *SSL 수신기**를 선택 해야 합니다.
    
   - **인증 위임은** **위임 안 되지만** 직접 클라이언트 인증은 **허용해야** 합니다.
    
   - 규칙을 모든 사용자로 **설정해야 합니다.**
    
   - 이 규칙은 이 규칙을 만들고 계속 진행하는 데 필요한 모든 정보입니다.
    
4. 원래 호스트 헤더가 전달되도록 **해야** 합니다.
    
5. 웹 **서버** 포트도 설정해야 합니다.
    
   - **HTTP 포트로** 요청을 리디렉션하고 포트 번호는 **8080이 되어야 합니다.**
    
   - **SSL** 포트로 요청을 리디렉션하고 포트 번호는 **4443입니다.**
    
6. 모든 구성이 구성된 경우 이러한 규칙을 저장하거나 적용한 다음 규칙을 테스트해야 합니다.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>포트 80에 대한 웹 게시 규칙 만들기(선택 사항)

1. 역방향 프록시 인터페이스를 열 수 있습니다.
    
2. 인터페이스에서 웹 게시 규칙을 만들고 새로 만들기 또는 만들기 옵션을  선택해야  합니다(역방향 프록시 구성에 따라 메뉴 또는 탭에 있을 수 있습니다). 새 웹 게시 규칙을 만드는 옵션을 찾고 있습니다.
    
3. 일반적으로 다음 정보를 입력해야 합니다.
    
   - **이름**: 규칙의 이름
    
   - **규칙 동작:** 이 경우 허용  규칙인 경우 역방향 프록시를 통과하도록 허용합니다.
    
   - 선택한 **게시** 규칙 또는 옵션은 단일 웹 사이트 또는 부하 부하 조정 **서비스입니다.**
    
   - 게시된 웹 서버 또는 팜에 연결하기 위해 보안되지 않은 **연결일 수 있습니다.**
    
   - **내부** 게시에 대한 경로를 게시하고 프런트 엔드 풀의 부하 균형 조정의 **VIP** 주소에 대한 FQDN을 입력해야 합니다. 예를 들어 sfb_pool01.contoso.local을 예로 들 수 있습니다.
    
   - _를 게시할 경로로 입력해야 하지만 원래 호스트 **/\\** 헤더를 _*전달해야 합니다.**.
    
   - 공개 또는 외부 이름 세부 정보 또는 정보에 **대한** 옵션이 제공됩니다. 입력할 수 있는 위치입니다.
    
   - **요청을 수락하지만** 도메인 이름에 대한 것이 좋습니다.
    
   - 이름의 경우 **lyncdiscover를 입력해야 합니다.** <sipdomain> 이 URL은 외부 자동iscover 서비스 URL입니다.
    
   - 경로 옵션이  있으며 여기에 **/\\** _를 입력해야 합니다.
    
   - 웹 수신기 또는 역방향 프록시에서 만들 수 있도록 허용해야 합니다.
    
   - _ *인증 위임**을 **위임 없음으로** 설정해야 하지만 직접 클라이언트 인증은 **허용되지** 않습니다.
    
   - 규칙을 모든 사용자로 **설정해야 합니다.**
    
   - 이 규칙은 이 규칙을 만들고 계속 진행하는 데 필요한 모든 정보입니다.
    
4. 웹 **서버** 포트를 설정해야 합니다. 다음을 실행해야 합니다.
    
   - **HTTP 포트로** 요청을 리디렉션하고 포트 번호는 **8080이 되어야 합니다.**
    
   - **SSL** 포트로 요청을 리디렉션하고 포트 번호는 **4443입니다.**
    
5. 모든 구성이 구성된 경우 이러한 규칙을 저장하거나 적용한 다음 규칙을 테스트해야 합니다.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>하이브리드 배포를 통해 모바일에 대한 자동Iscover 구성
<a name="ConfigAutoD"> </a>

비즈니스용 Skype 서버의 하이브리드 환경은 온라인과 O365 환경을 결합하는 환경입니다. 하이브리드 환경에서 작업하는 비즈니스용 Skype 서버가 있는 경우 자동 검색 서비스는 이러한 환경 중 하나에서 사용자를 찾을 수 있도록 설정해야 합니다.
  
모바일 클라이언트에서 사용자의 위치를 검색할 수 있도록 자동 검색 서비스를 새 URL(Uniform Resource Locator)으로 구성해야 합니다. 그 단계는 다음과 같습니다.
  
1. 비즈니스용 Skype 서버 관리 셸을 여는 경우
    
2. 다음을 실행하여 비즈니스용 Skype 서버 환경의 **ProxyFQDN** 특성 값을 얻습니다.
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 그런 다음 셸 창에서 다음을 실행합니다.
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    여기서 [identity]는 공유 SIP 주소 공간의 도메인 이름으로 대체됩니다.
    
## <a name="test-your-mobility-deployment"></a>모바일 배포 테스트
<a name="TestMobility"> </a>

비즈니스용 Skype 서버 Mobility Service 및 비즈니스용 Skype 서버 자동 검색 서비스를 배포한 후 테스트 트랜잭션을 실행하여 배포가 올바른지 확인하면 됩니다. **Test-CsUcwaConference를** 실행하여 두 사용자가 회의를 만들고 참가하고 통신할 수 있는 기능을 테스트할 수 있습니다. 이 테스트를 수행하려면 두 사용자(실제 또는 테스트)와 전체 자격 증명이 필요합니다. 이 명령은 비즈니스용 Skype 클라이언트와 Lync Server 2013 클라이언트 모두에 대해 작동됩니다.
  
비즈니스용 Skype 서버 2015의 Lync Server 2010 클라이언트의 경우 **Test-CsMcxP2PIM을** 실행하여 테스트해야 합니다. Lync Server 2010 사용자는 여전히 실제 사용자 또는 미리 정의한 테스트 사용자일 수 있으며 암호 자격 증명이 필요합니다.

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>비즈니스용 Skype 및 Lync 2013 모바일 클라이언트에 대한 회의 테스트

1. 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에서 **CsAdministrator** 역할의 구성원으로 로그온합니다.
    
2. 비즈니스용 **Skype 서버** 관리 셸을 시작합니다(검색에  이름을 입력하거나 모든 프로그램으로 이동하여 선택할 수 있습니다).
    
3. 명령줄에 다음을 입력합니다.
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   스크립트에서 자격 증명을 설정하고 테스트 cmdlet에 전달할 수도 있습니다. 아래 예가 있습니다.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Lync 2010 모바일 클라이언트에 대한 테스트 회의

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.

1. 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 모든 컴퓨터에서 **CsAdministrator** 역할의 구성원으로 로그온합니다.
    
2. 비즈니스용 **Skype 서버** 관리 셸을 시작합니다(검색에  이름을 입력하거나 모든 프로그램으로 이동하여 선택할 수 있습니다).
    
3. 명령줄에 다음을 입력합니다.
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   스크립트에서 자격 증명을 설정하고 테스트 cmdlet에 전달할 수도 있습니다. 아래 예가 있습니다.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

명령 절차를 더 검토하기 위해 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 및 [Test-CsMcxP2PIM을](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)체크 아웃하면 됩니다.
  
## <a name="configure-for-push-notifications"></a>푸시 알림 구성
<a name="ConfigPush"> </a>

배지, 아이콘 또는 경고 형식의 푸시 알림은 Skype 또는 Lync 앱이 비활성인 경우에도 모바일 장치로 전송될 수 있습니다. 그러나 푸시 알림이란? 새 IM 초대나 부재 중 IM 초대와 같은 이벤트 경고 또는 수신된 음성 메일에 대한 알림입니다. 비즈니스용 Skype 서버 모바일 서비스는 이러한 알림을 클라우드 기반 비즈니스용 Skype 서버 푸시 알림 서비스로 전송한 다음 Windows Phone 사용자를 위해 MSNS(Microsoft 푸시 알림 서비스)에 알림을 전송합니다.
  
이 기능은 Lync Server 2013에서 변경되지 않지만 비즈니스용 Skype 서버가 있는 경우 다음을 실행해야 합니다.
  
- 비즈니스용 Skype 서버 에지 서버의 경우 새 호스팅 공급자인 Microsoft 비즈니스용 Skype Online을 추가한 다음 조직과 비즈니스용 Skype Online 간에 호스팅 공급자 페더링을 설정합니다.
    
- **Set-CsPushNotificationConfiguration** cmdlet을 실행하여 푸시 알림을 사용하도록 설정합니다. 기본적으로 푸시 알림은 해제됩니다.
    
- 페더전 구성 및 푸시 알림을 테스트합니다.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>푸시 알림에 대한 비즈니스용 Skype 에지 서버 구성

1. **CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 관리 셸을 시작합니다.**
    
3. 비즈니스용 Skype 서버 온라인 호스팅 공급자를 추가합니다.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   예를 들면 다음과 같습니다.
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 단일 호스팅 공급자와의 페더링 관계는 두 개 이상일 수 없습니다. 따라서 sipfed.online.lync.com 페더링 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 ID가 SkypeOnline이 아니어도 다른 호스팅 공급자를 추가하지 않습니다. 
  
4. 조직과 비즈니스용 Skype Online의 푸시 알림 서비스 간에 호스팅 공급자 페더링을 설정합니다. 명령줄에 다음을 입력해야 합니다.
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>푸시 알림 사용

1. **CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 관리 셸을 시작합니다.**
    
3. 푸시 알림을 사용하도록 설정:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. 페더ation을 사용하도록 설정:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>페더ation 및 푸시 알림 테스트

1. **CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 관리 셸을 시작합니다.**
    
3. 페더전 구성을 테스트합니다.
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. 푸시 알림을 테스트합니다.
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>모바일 정책 구성
<a name="ConfigMob"> </a>

비즈니스용 Skype 서버와 함께 모바일 서비스, 직장 전화, VoIP(Voice over IP) 또는 비디오를 사용할 수 있는 사용자와 VoIP 또는 비디오에 WiFi가 필요한지 여부를 결정할 수 있습니다. 모바일 사용자는 업무번호로 전화 기능을 사용하여 전화를 걸고 받을 때 휴대폰 번호 대신 직장 전화 번호를 사용할 수 있습니다. 회선의 다른 끝에 있는 사용자는 모바일 사용자의 휴대폰 번호를 볼 수 없습니다. 이를 통해 모바일 사용자는 발신 전화 요금을 피할 수 있습니다. VoIP 및 비디오가 설정되어 있는 경우 사용자는 VoIP 통화 및 비디오를 받아서 만들 수 있습니다. WiFi 사용 설정에 따라 사용자의 모바일 장치가 셀룰러 데이터 네트워크를 통해 WiFi 네트워크를 사용하는 데 필요한지 여부가 결정됩니다.
  
모바일 기능, 직장 전화 및 VoIP 및 비디오 기능은 모두 기본적으로 사용하도록 설정됩니다. VoIP 및 비디오에 WiFi를 요구하는 설정은 사용할 수 없습니다. 관리자는 전역, 사이트 또는 사용자에 따라 이를 변경할 수 있습니다.
  
모바일 기능 및 직장을 통한 통화 기능을 사용하려면 사용자는 다음을 해야 합니다.
  
- 비즈니스용 Skype 서버에 사용
    
- 기본 설정에 Enterprise Voice.
    
- **EnableMobility** 옵션이 True로 설정된 모바일 **정책이 할당됩니다.**
    
사용자가 직장에서 전화 기능을 사용할 수 있도록 하려면 다음 작업도 필요합니다.
  
- 전화 동시 전화 울림 사용 옵션이 선택된 음성 **정책이** 할당되었습니다.
    
- **EnableOutsideVoice가 True로** 설정된 모바일 **정책이 할당됩니다.**
    
> [!NOTE]
> Enterprise Voice 사용할 수 없는 사용자는 모바일 장치를 사용하여 Skype에서 Skype VoIP로 전화를 걸거나, 연결된 음성 정책에 대해 적절한 옵션이 설정된 경우 모바일 장치에서 클릭하여 참가 링크를 사용하여 전화 회의에 참가할 수 있습니다. 계획 항목에는 자세한 설명이 있습니다. 
  
### <a name="modify-global-mobility-policy"></a>전역 모바일 정책 수정

1. **CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 관리 셸을 시작합니다.**
    
3. 다음을 입력하여 Mobility and Call via Work에 대한 액세스를 전역적으로 해제합니다.
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Mobility에 대한 액세스를 해제하지 않고도 업무를 통한 통화를 해제할 수 있습니다. 그러나 업무를 통한 통화도 끄지 않고는 모바일 기능을 해제할 수 있습니다. 
  
    자세한 내용은 [Set-CsMobilityPolicy를 확인하세요.](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)
    
### <a name="modify-mobility-policy-by-site"></a>사이트당 모바일 정책 수정

1. **CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 관리 셸을 시작합니다.**
    
3. 사이트 수준 정책을 만들고, VoIP 및 비디오를 끄고, IP 오디오에 WiFi를 사용하도록 설정하고, IP 비디오에 WiFi를 사이트로 요구할 수 있습니다. 유형:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    자세한 내용은 [New-CsMobilityPolicy를 통해 자세히 알아보아야 합니다.](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)
    
### <a name="modify-mobility-policy-by-user"></a>사용자에 따라 모바일 정책 수정

1. **CsAdministrator** 역할의 구성원인 계정으로 비즈니스용 **Skype** 서버 관리 셸 및 **Ocscore가** 설치된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 관리 셸을 시작합니다.**
    
3. 사용자 수준 이동성 정책을 만들고 사용자에 의해 모바일 및 직장을 통한 통화를 해제합니다. 유형:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    예제 데이터가 있는 추가 예제:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Mobility에 대한 액세스를 해제하지 않고도 업무를 통한 통화를 해제할 수 있습니다. 그러나 업무를 통한 통화도 끄지 않고는 모바일 기능을 해제할 수 있습니다. 
  

