---
title: 클라우드 커넥터 배포 문제 해결
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Cloud Connector Edition 배포 문제를 해결 합니다.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359334"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>클라우드 커넥터 배포 문제 해결

> [!Important]
> 클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다. 조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.
 
Cloud Connector Edition 배포 문제를 해결 합니다.
  
이 항목에서는 Cloud Connector Edition 배포와 관련 된 일반적인 문제에 대 한 해결 방법을 설명 합니다. 공중 전화망 (PSTN)과의 통화에 문제가 발생 하는 경우이 항목에서 설명 하는 솔루션을 따라 조사할 수 있습니다.
  
클라우드 커넥터는 일부 문제를 자동으로 해결 하기 위한 기본 제공 메커니즘을 제공 합니다. 자동 검색 프로세스는 클라우드 커넥터 기기와 관련 된 잠재적 문제를 찾은 다음, 가능한 경우 관리자의 개입 없이 해당 문제를 해결 하기 위해 정정 작업을 수행 합니다. 검색 프로세스는 다음과 같이 작동 합니다.
  
- **검색 시퀀스:** 클라우드 커넥터 관리 서비스는 기기가 다운 되었는지 여부를 검색 하기 위해 60 초 마다 프로세스를 실행 합니다. 클라우드 커넥터 버전 2.0 이상에서 검색 프로세스는 클라우드 커넥터 컴퓨터에 PowerShell 연결을 설정 하는 데 비즈니스용 Skype Corpnet 스위치를 사용 합니다. 이전 버전 2.0의 경우 검색 프로세스에서 클라우드 커넥터 관리 스위치를 사용 합니다.
    
    > [!NOTE]
    > 자동 복구가 성공 하려면 호스트 네트워크 스위치를 통해 호스트와 가상 컴퓨터 간에 네트워크 연결이 있어야 합니다. 네트워크 연결을 확인 하 여 자동 검색 및 복구가 성공할 수 있는지 확인 합니다. 
  
- **모니터링:** 다음 서비스는 클라우드 커넥터 버전 2.0 이상에서 모니터링 됩니다.
    
  - 가상 컴퓨터가 클라우드 커넥터 회사 또는 인터넷 가상 스위치에 연결 되어 있지 않음
    
  - 가상 컴퓨터가 저장 또는 중지 된 상태입니다.
    
  - 중앙 관리 서버 서비스: 복제본, 마스터
    
  - 중재 서버 서비스: REPLICA, RTCSRV 및 MEDSVC
    
  - 에 지 서버 서비스: 복제본, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - 중재 서버에서 RTCSRV에 지 서버, CS RTCMEDSRV의 CS에 대해 인바운드 방화벽 규칙이 사용 되지 않도록 설정 됨
    
    클라우드 커넥터 버전 1.4.2에서는 다음 서비스만 모니터링 됩니다.
    
  - 중재 서버 서비스: RTCSRV 및 MEDSVC
    
  - 에 지 서버 서비스: RTCSRV
    
- **복구 프로세스:** 모니터링 되는 서비스가 다운 되 면 기기가 다운 된 것으로 표시 되며 모든 문제를 해결할 수 있을 때까지 서비스가 중지 되 고 설명서로 표시 됩니다. 이렇게 하면 호출 오류가 발생할 수 있는 기기로의 호출이 차단 되지 않습니다.
    
    클라우드 커넥터 관리 서비스는 다음과 같이 자동 복구를 다시 시도 합니다.
    
  - 초기 다시 시도 간격은 최대 10 초 간격으로 1 시간입니다.
    
  - 처음 세 가지 복구를 시도 하는 경우 간격 시간은 10 초입니다. 네 번째 다시 시도 부터는 간격 시간이 이전 간격 시간의 2 배가 증가 합니다. 예를 들어, 네 번째 다시 시도는 20 초, 5 번째는 40 초에 발생 합니다. 
    
  - 한 시간 동안 최대 간격 시간에 도달 하면 한 시간 마다 한 번씩 다시 시도 됩니다.
    
  - 복구에 성공 하면 간격 및 다시 시도 횟수가 초기 값으로 설정 됩니다.
    
  - 관리 서비스를 다시 시작 하면 간격 및 다시 시도 횟수가 초기 값으로 다시 설정 됩니다.
    
## <a name="troubleshooting"></a>문제 해결

다음은 일반적으로 발생 하는 문제에 대 한 해결 방법입니다.
  
- **문제: 배포 스크립트를 실행할 때 배포가 실패 하거나 응답을 멈춥니다. 각 VM에 로그온 한 후에는 관리/내부/외부 NIC에 대해 IP 주소가 누락 되거나 잘못 된 것입니다.**
    
    **해결 방법:** 이 문제는 자동으로 해결할 수 없습니다. Nic를 실행 하는 동안 Vm에 추가할 수 없습니다. Hyper-v 관리자에서 이러한 Vm을 종료 하 고 제거한 후 다음 cmdlet을 실행 하십시오.
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **문제: Active Directory 서버 및 포리스트를 설치한 후 CMS 서버 및/또는 중재 서버가 도메인에 올바르게 가입 하지 않았습니다.**
    
    **해결 방법:** 이 문제를 해결 하려면 다음 단계를 수행 합니다.
    
  - Active Directory 서버에 로그온 하 고 도메인이 제대로 만들어졌는지 확인 합니다.
    
  - CMS/중재 서버에 로그온 하 고 corpnet NIC에서 유효한 IP 주소가 할당 되었으며, 유효한 고정 IP 및 DNS가 AD 서버의 IP 주소로 구성 되어 있는지 확인 합니다.
    
  - CMS/중재 서버에 로그온 하 고 명령 프롬프트를 엽니다. Active Directory 서버의 FQDN 및 IP 주소에 대해 ping을 사용할 수 있는지 확인 합니다. 사용할 수 없는 경우 IP 주소 충돌이 있을 수 있습니다. 이에 따라 CMS/중재 서버에서 Active Directory에 대 한 새 IP를 할당 하 고 DNS를 업데이트 해 보세요.
    
- **문제: "Remove-VMSwitch: virtual Ethernet 스위치를 제거 하는 동안 다음 오류 메시지가 표시 됩니다. 가상 스위치 ' 클라우드 커넥터 관리 스위치 '은 (는) 실행 중인 가상 컴퓨터에서 사용 중이거나 자식 풀에 할당 되어 있으므로 삭제할 수 없습니다. "**
    
    **해결 방법:** 배포 후에 "클라우드 커넥터 관리 스위치"가 삭제 되지 않았습니다. 이 오류가 발생 하는 경우 Hyper-v 관리자로 이동 하 여 여전히 여전히 연결 된 가상 컴퓨터가 없는지 확인 하십시오. 아직 연결 된 가상 컴퓨터가 있으면 연결을 끊고 관리 스위치를 삭제 합니다. 여전히 관리 스위치를 삭제할 수 없으면 호스트 서버를 다시 시작 하 고 다시 시도 합니다.
    
- **문제: "서비스 RTCMRAUTH을 시작 하지 못했습니다. 라는 오류 메시지가 표시 됩니다. 서비스가 사용 하지 않도록 설정 되어 있는지 확인 하십시오. "**
    
    > [!NOTE]
    > 이 문제는 1.4.2 이전 클라우드 커넥터 버전에만 적용 됩니다. 
  
    또한이 프런트 엔드 서버가 이전에 장애 조치 (failover over 사용) 되었기 때문일 수 있습니다. 이 경우에는 장애 복구 (컴퓨터 장애 복구)를 호출 하십시오.
    
    **해결 방법:** 이 문제는에 지 서버에서 루트 CA 인증서 또는 중개 CA 인증서를 신뢰 하지 않을 때에 지 서버에서 발생 합니다. 외부 인증서를 가져올 수 있지만 인증서 체인은 손상 된 경우에도 마찬가지입니다. 이 조건에서는 RTCMRAUTH 및/또는 RTCSRV 서비스를 시작할 수 없습니다.
    
    외부 인증서의 루트 CA 인증서 및 모든 중간 CA 인증서를 수동으로에 지 서버에 가져온 다음에 지 서버를 다시 시작 하세요. 에 지 서버에서 RTCMRAUTH 및 RTCSRV 서비스가 시작 된 것을 확인 한 후에는 호스트 서버로 돌아가 PowerShell 콘솔을 관리자 권한으로 시작한 후 다음 cmdlet을 실행 하 여 새 배포로 전환 합니다.
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **문제: Windows 업데이트를 적용 했을 때 호스트 서버가 다시 시작 되 고 서버에서 서비스를 제공 하는 통화가 실패 합니다.**
    
    **해결 방법:** 고가용성 환경을 배포한 경우 Microsoft는 Windows update를 수동으로 확인 하 고 설치할 때 하나의 호스트 컴퓨터 (배포 인스턴스)를 현재 토폴로지로 이동 하는 데 도움이 되는 cmdlet을 제공 합니다. 이 작업을 수행 하려면 다음 단계를 사용 합니다.
    
1. 호스트 서버에서 PowerShell 콘솔을 관리자 권한으로 시작 하 고 다음을 실행 합니다.
    
   ```powershell
   Enter-CcUpdate
   ```

2. 업데이트를 확인 하 고 사용 가능한 항목을 모두 설치 합니다.
    
3. PowerShell 콘솔에서 다음 cmdlet을 실행 합니다.
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **문제: PSTN 번호를 사용 하 여 비즈니스용 Skype 클라이언트에서 전화를 건 경우 통화를 다른 PSTN 번호를 초대 하 여 전화 회의로 전달할 수 없습니다.**
    
    **해결 방법:** 이 문제를 해결 하려면 [Configure online Hybrid 중재 Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)를 참조 하십시오.
    
- **문제: Active Directory server를 설치 하는 경우 Windows Update에 대 한 경고 메시지가 표시 됩니다.-"Windows 자동 업데이트가 사용 되도록 설정 되지 않았습니다. 새로 설치 된 역할 또는 기능이 자동으로 업데이트 되도록 하려면 Windows Update를 설정 합니다. "**
    
    **해결 방법:** 비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행 하 여 사이트의 _Enableautoupdate 업데이트_ 구성을 확인 합니다.
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    _Enableautoupdate 업데이트_ 를 **True**로 설정한 경우 CCEManagement 서비스는 가상 컴퓨터와 호스트 서버 둘 다에 대해 Windows 업데이트를 다운로드 하 고 설치 하는 것을 처리 하기 때문에이 경고 메시지를 무시 해도 됩니다. _Enableautoupdate 업데이트_ 를 **False**로 설정 하는 경우 다음 cmdlet을 실행 하 여 **True**로 설정 합니다.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    또는 수동으로 업데이트를 확인 하 고 설치할 수 있습니다. 다음 섹션을 참조하세요.
    
- **문제: 현재 입력/구성 \<SiteName\> 또는 \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 기존 기기와의 충돌 때문에 기기를 등록할 수 없습니다. 라는 오류 메시지가 표시 됩니다. 충돌 하는 기기를 제거 하거나 입력/구성 정보를 업데이트 한 다음 다시 등록 합니다. ' 등록-CcAppliance를 실행 하 여 현재 기기를 온라인에 등록할 수 있습니다.**
    
    **해결 방법:** 의 값 \<ApplianceName\> 이며, \<Mediation Server FQDN\> \<Mediation Server IP Address\> 고유 하 고 하나의 기기 등록에만 사용 해야 합니다. 기본적으로 \<ApplianceName\> 호스트 이름이 제공 됩니다. \<Mediation Server FQDN\>\<Mediation Server IP Address\>구성 ini 파일에 정의 되어 있습니다.
    
    예를 들어 (ApplianceName = MyserverNew, 중재 서버 FQDN = 10.10.10.10)를 사용 하 여 SiteName = 내 사이트에 등록 하지만 등록 된 기기가 있는 경우 (ApplianceName = Myserver, 중재 서버 FQDN =, 중재 서버 IP 주소 = 10.10.10.10)이 충돌을 받게 됩니다.
    
    먼저 ApplianceRoot directory 섹션에서 CloudConnector.ini 파일을 확인 하세요. \<SiteName\> \<Mediation Server FQDN\> 파일에 대 한 값을 얻게 됩니다 \<Mediation Server IP Address\> . \<ApplianceName\> 은 호스트 서버 이름입니다.
    
    그런 다음 비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 원격 PowerShell을 시작한 후 다음 cmdlet을 실행 하 여 등록 된 기기를 확인 합니다.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    충돌을 식별 한 후에는 등록 된 기기와 일치 하는 정보로 CloudConnector.ini 파일을 업데이트 하거나 기존 기기를 등록 취소 하 여 충돌을 해결할 수 있습니다.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **문제: 호스트에서 실행 되는 배포 된 기기가 있는 경우 CcRunningVersion cmdlet은 빈 값을 반환 합니다.**
    
  **해결 방법:** 1.3.4 또는 1.3.8에서 1.4.1으로 업그레이드할 때 이러한 상황이 발생할 수 있습니다. .Msi와 함께 버전 1.4.1을 설치한 후에는 `Register-CcAppliance` 다른 cmdlet을 실행 하기 전에 실행 해야 합니다. `Register-CcAppliance` module.ini 파일 을%UserProfile%\CloudConnector 에서%ProgramData%\CloudConnector.로 마이그레이션합니다. 이 파일을 놓치지 않으면%ProgramData%\CloudConnector 폴더에 새 module.ini 생성 되 고 1.3.4 또는 1.3.8의 실행/백업 버전 정보를 대체 합니다.
    
  %UserProfile%\CloudConnector 및%ProgramData%\CloudConnector 폴더의 module.ini 파일을 비교 합니다. 차이점이 있으면%ProgramData%\CloudConnector에서 module.ini 파일을 삭제 하 고 다시 실행  `Register-CcAppliance` 합니다. 올바른 실행 및 백업 버전으로 파일을 수동으로 수정할 수도 있습니다.
    
- **문제: CcVersion cmdlet을 실행 하 여 현재 스크립트 버전과 다른 이전 버전으로 전환한 후에는이 이전 버전에 대 한 고가용성이 지원 되지 않습니다.**
    
    **해결 방법:** 예를 들어 1.4.1에서 1.4.2으로 업그레이드 했습니다. 실행 중에 확인할 수 있는 현재 스크립트 버전 및 실행 중인 `Get-CcVersion` 버전  `Get-CcRunningVersion` 은 모두 1.4.2입니다. 현재 `Switch-CcVersion` 실행 중인 버전을 다시 1.4.1으로 전환 하기 위해 실행 하는 경우이 이전 버전에 대 한 고가용성 지원이 제공 되지 않습니다.
    
    전체 고가용성 지원을 받으려면 1.4.2으로 다시 전환 하 여 실행 중인 버전 및 스크립트 버전이 동일 해야 합니다. 1.4.2 배포에 문제가 있는 경우에는 가능한 한 빨리 제거한 후 다시 설치 하십시오.
    
- **문제: 중앙 관리 저장소, 중재 서버 및에 지 서버에 발급 된 인증 기관 인증서 또는 내부 인증서가 거의 만료 되었거나 손상 되었습니다.**
    
    **해결 방법:** 비즈니스용 Skype 인증 기관 인증서는 5 년 동안 유효 합니다. 중앙 관리 저장소, 중재 서버 및에 지 서버에 발급 된 내부 인증서는 2 년 동안 유효 합니다.
    
    > [!NOTE]
    > 클라우드 커넥터 버전 2.0 이상에서 CcServerCertificate cmdlet이 업데이트-CcServerCertificate로 변경 되었으며 CcCACertificate cmdlet이 CcCACertificate로 변경 되었습니다. 
  
    중앙 관리 저장소, 중재 서버 및에 지 서버에 발급 된 내부 인증서가 곧 만료 되거나 손상 되 면, CcServerCertificate 또는 업데이트-CcServerCertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.
    
    인증 기관 인증서가 곧 만료 되는 경우 CcCACertificate 또는 CcCACertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.
    
    **인증 기관 인증서가 손상 되 고 사이트에 하나의 어플라이언스만 있는 경우** 다음 단계를 수행 합니다.
    
1. Enter-CcUpdate cmdlet을 실행 하 여 서비스를 드레이닝 하 고 기기를 유지 관리 모드로 전환 합니다.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 다음 cmdlet를 실행 하 여 새 인증 기관 인증서와 모든 내부 서버 인증서를 다시 설정 하 고 만듭니다.
    
    2.0 이전 클라우드 커넥터 릴리스는 다음과 같습니다.
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    또는 클라우드 커넥터 릴리스 2.0 이상에 대해 다음을 수행 합니다.
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. 게이트웨이와 중재 서버 간에 TLS를 사용 하는 경우 기기에서 CcRootCertificate cmdlet을 실행 한 다음, 내보낸 인증서를 PSTN 게이트웨이에 설치 합니다. 게이트웨이에서 인증서를 다시 발급 해야 할 수도 있습니다.

   ```powershell
   Export-CcRootCertificate
   ```

4. 서비스를 시작 하 고 유지 관리 모드를 종료 하려면 CcUpdate cmdlet을 실행 합니다.

   ```powershell
   Exit-CcUpdate
   ```


    **인증 기관 인증서가 손상 되 고 사이트에 여러 기기가 있는 경우** 사이트의 각 기기에 대해 다음과 같은 순차적 단계를 수행 합니다.
    
    사용량이 많지 않은 시간에 이러한 단계를 수행 하는 것이 좋습니다.
    
1. 첫 번째 기기에서 CcCertificationAuthorityFile cmdlet을 실행 하 여 디렉터리에서 CA 백업 파일을 정리 \<SiteRoot\> 합니다.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Enter-CcUpdate cmdlet을 실행 하 여 서비스를 드레이닝 하 고 각 기기를 유지 관리 모드로 전환 합니다.

     ```powershell
     Enter-CcUpdate
     ```
    
3. 첫 번째 기기에서 다음 cmdlet을 실행 하 여 새 인증 기관 인증서와 모든 내부 서버 인증서를 다시 설정 하 고 만듭니다.
    
     2.0 이전 클라우드 커넥터 릴리스는 다음과 같습니다.
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     또는 클라우드 커넥터 릴리스 2.0 이상에 대해 다음을 수행 합니다.
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 첫 번째 기기에서 다음 cmdlet을 실행 하 여 CA 파일을 해당 폴더에 백업 합니다 \<SiteRoot\> .
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 같은 사이트에 있는 다른 모든 기기의 경우 다음 명령을 실행 하 여 CA 백업 파일을 사용 하 고 해당 기기가 모두 동일한 루트 인증서를 사용 하도록 설정한 다음 새 인증서를 요청 합니다. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 게이트웨이와 중재 서버 간에 TLS를 사용 하는 경우 사이트의 모든 기기에서 CcRootCertificate cmdlet을 실행 한 다음, 내보낸 인증서를 PSTN 게이트웨이에 설치 합니다. 게이트웨이에서 인증서를 다시 발급 해야 할 수도 있습니다.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 서비스를 시작 하 고 유지 관리 모드를 종료 하려면 CcUpdate cmdlet을 실행 합니다. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **문제: 클라우드 커넥터 관리 서비스 로그, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0: 상태를 온라인으로 보고할 때 예기치 않은 예외 발생: CmdletInvocationException: 사용자에 게 로그온 하지 \<Global Tenant Admin\> 못했습니다. 새 credential 개체를 만들어 올바른 사용자 이름과 암호를 사용 했는지 확인 하십시오. ---\>**
    
    **해결 방법:** 클라우드 커넥터 기기가 등록 된 이후 Microsoft 365 또는 Office 365 전역 테 넌 트 관리자 자격 증명이 변경 되었습니다. 클라우드 커넥터 기기에서 로컬로 저장 된 자격 증명을 업데이트 하려면 호스트 기기의 관리자 PowerShell에서 다음을 실행 합니다.
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **문제: 배포에 사용한 호스트 서버 계정의 암호를 변경한 후에는 "ConvertTo-SecureString: 키를 지정한 상태에서 사용할 수 없습니다." 라는 오류 메시지가 표시 됩니다. "for Business Cloud Connector Edition\ManagementService\CceManagementService.log 또는%ProgramFiles%\Skype Get-CcCredential cmdlet을 실행 합니다.**
    
    **해결 방법:** 모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials." 파일에 저장 됩니다 \<CurrentUser\> . xml "입니다. 호스트 서버의 암호가 변경 되 면 로컬로 저장 된 자격 증명을 업데이트 해야 합니다.
    
    **클라우드 커넥터 버전 1.4.2을 실행 하는 경우** 다음 단계를 수행 하 여 모든 클라우드 커넥터 암호를 다시 생성 합니다.
    
  1. 호스트 서버를 다시 시작 합니다.
    
  2. "%SystemDrive%\Programdata\Cloudconnector\credentials." 파일을 \<CurrentUser\> 삭제 합니다. xml "입니다.
    
  3. PowerShell 콘솔을 관리자 권한으로 시작한 다음 "레지스터-CcAppliance-Local"을 실행 하 여 설명에 해당 하는 암호를 다시 입력 합니다. 클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 합니다.
    
     **클라우드 커넥터 버전 2.0 이상을 실행 하는 경우** 다음 단계를 수행 하 여 모든 클라우드 커넥터 암호를 다시 생성 합니다.
    
  4. 호스트 서버를 다시 시작 합니다.
    
  5. "%SystemDrive%\Programdata\Cloudconnector\credentials." 파일을 \<CurrentUser\> 삭제 합니다. xml "입니다.
    
  6. PowerShell 콘솔을 관리자 권한으로 시작한 다음 "레지스터-CcAppliance-Local"을 실행 하 여 설명에 해당 하는 암호를 다시 입력 합니다. 
    
     클라우드 커넥터 버전 1.4.2를 사용 하 여 캐시 된 암호 파일을 생성 한 경우에는 메시지가 표시 되 면 CceService 암호에 대 한 VMAdmin 암호를 사용 합니다. 다른 모든 계정의 클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 합니다.
    
     클라우드 커넥터 버전 1.4.2와 함께 캐시 된 암호 파일을 생성 하 고 DomainAdmin 및 VMAdmin 암호가 서로 다른 경우에는 다음 단계를 수행 해야 합니다.
    
  7. Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.
    
  8. 이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
  9. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 DomainAdmin 암호의 암호를 입력 합니다.
    
     클라우드 커넥터 버전 2.0 이상으로 캐시 된 암호 파일을 생성 한 경우, 기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다. DomainAdmin 및 VMAdmin 암호를 변경한 경우에는 다음 단계를 수행 해야 합니다.
    
  10. Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.
    
       1. 이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
       2. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 DomainAdmin 암호의 암호를 입력 합니다.
    
  11. 다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.
    
       1. 이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
       2. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 VmAdmin 암호의 암호를 입력 합니다. 
    
- **문제: 클라우드 커넥터 버전 2.1 이상을 사용 하는 경우 기기에서 등록-CcAppliance 기타 cmdlet을 실행 하면 "For Each-Object:이 개체에서 ' Common ' 속성을 찾을 수 없습니다. 라는 오류 메시지가 표시 됩니다. 속성이 있는지 확인 합니다. C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**
    
    **해결 방법:** 클라우드 커넥터 2.1 이상에는 .NET Framework 4.6.1 이상이 필요 합니다. 기기의 .NET Framework를 버전 4.6.1 이상으로 업데이트 하 고 cmdlet을 다시 실행 하십시오.

- **문제: 클라우드 커넥터 에디션 2.1을 사용 하 여 설치-CcAppliance를 실행 하는 경우 "오류가 발생 하 여 새 인스턴스를 설치 하지 못했습니다." 라는 오류 메시지가 표시 됩니다. "State"를 설정할 수 없습니다.**

   **해결 방법:** Cloudconnector.ini의 [Common] 섹션에서 "State" config를 아래와 같이 추가 합니다 (CountryCode = US State = WA 구/군/시 = Redmond).

   "State" 줄의 값은 필수가 아니므로 Cloudconnector.ini 파일에서 "State" 줄을 제거할 수 없습니다.

- **문제: "WindowsImage: WindowsImage에 오류가 발생 하 여 다음 오류 메시지가 나타납니다. 클라우드 커넥터 버전을 설치 또는 업그레이드할 때 오류 코드 = 0xc1550115 "입니다.**
    
    **해결 방법:** PowerShell 콘솔을 관리자 권한으로 시작 하 고 "DISM-Cleanup-.Wim '"을 실행 합니다. 이렇게 하면 모든 troubled 이미지가 정리 됩니다. 설치-CcAppliance를 다시 실행 하거나 bits가 자동으로 업그레이드 될 때까지 기다립니다.
    
- **문제: HA 환경에서 첫 번째 클라우드 커넥터 기기의 배포가 실패 함**
    
    **해결 방법:** 수행 하는 단계는 배포에 실패 한 이유에 따라 다릅니다.
    
  - 첫 번째 클라우드 커넥터 기기가 실패 하 고 실패 이유를 확인할 수 없는 경우 배포가 성공할 때까지 기기를 다시 설치한 다음 다른 기기를 설치 해야 합니다.
    
  - 첫 번째 클라우드 커넥터 기기가 오류가 발생 하는 경우 (예: 외부 인증서 문제) 기기를 다시 설치 하지 않고도 문제를 해결할 수 있습니다. 그런 다음 테 넌 트 원격 PowerShell을 사용 하 여 배포를 다음과 같이 성공한 것으로 표시할 수 있습니다. (첫 번째 배포가 성공한 경우에는 다음 단계를 사용할 수도 있지만, 어떤 이유로 클라우드 커넥터가 성공으로 배포를 보고 하지 못할 수 있습니다.)
    
  - 첫 번째 클라우드 커넥터 기기의 Id (GUID)를 가져오려면 CsHybridPSTNAppliance cmdlet을 실행 합니다.
    
  - 기기를 성공적으로 배포 된 것으로 표시 하려면 다음과 같이 CsCceApplianceDeploymentStatus를 실행 합니다.
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **문제: 호스트 서버 또는 가상 컴퓨터에서 Windows 업데이트를 확인 하 고 수동으로 설치 해야 합니다.**
    
   **해결 방법:** 비즈니스용 Skype 클라우드 커넥터 Edition에서 제공 하는 자동화 된 OS 업데이트를 활용 하는 것이 좋습니다. 온라인 관리를 위해 기기가 등록 되 고 자동 OS 업데이트가 사용 하도록 설정 되 면 호스트 서버와 가상 컴퓨터는 OS 업데이트 시간 창 설정에 따라 Windows 업데이트를 자동으로 확인 하 고 설치 합니다.
    
   Windows 업데이트를 확인 하 고 설치 해야 하는 경우이 섹션의 배포 유형에 적용 되는 단계를 수행 합니다. 업데이트에 필요한 가동 중지 시간을 최소화 하기 위해 동시에 실행 되는 호스트 서버와 가상 컴퓨터를 모두 업데이트 하는 계획을 세워야 합니다.
    
   원하는 경우 WSUS (Windows Server Update Services) 서버를 사용 하 여 클라우드 커넥터 서버에 대 한 업데이트를 제공할 수 있습니다. Windows 업데이트가 자동으로 설치 **되지** 않도록 구성 해야 합니다.
    
   클라우드 커넥터 배포를 수동으로 업데이트 하는 방법에 대 한 자세한 내용은 다음 섹션을 참조 하십시오.
    
- **문제: 클라우드 커넥터가 새 빌드로 업데이트 되 면 클라우드 커넥터 cmdlet이 업데이트 되지 않습니다.** 자동 업데이트가 발생할 때 PowerShell 창이 열려 있으면이 문제가 발생할 수도 있습니다.
    
  **해결 방법:** 업데이트 된 cmdlet을 로드 하려면 다음 단계 중 하나를 수행 하면 됩니다.
    
   - 클라우드 커넥터 기기에서 PowerShell을 닫고 PowerShell을 다시 엽니다.
    
     - 또는 Import-Module CloudConnector-Force를 실행할 수 있습니다. 
 
-   **Issue: "' Stop-CsWindowsService ' 용어가 cmdlet, 함수, 스크립트 파일 또는 실행 가능한 프로그램의 이름으로 인식 되지 않습니다." 라는 오류가 발생 했습니다.**

    **해결 방법:** $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 파일을 삭제 합니다.
PowerShell은이 파일을 발견 하는 모듈의 cmdlet 캐시로 만들며, 따라서 시간이 오래 걸릴 때마다 모든 모듈을 다시 분석 하지 않아도 됩니다. 대부분의 경우 해당 캐시에서 다시 읽어 오는 경우 PowerShell에 잘못 된 결과가 제공 되는 일부 파일 손상이 있었습니다.

-   **문제: "Import-Module CloudConnector" 오류가 발생 합니다. "가져오기-모듈: 모듈 디렉터리에서 올바른 모듈 파일을 찾을 수 없기 때문에 지정 된 모듈" CloudConnector "가 로드 되지 않았습니다."**

    **해결 방법:**
    - 정말로 c:\Program Files\WindowsPowerShell\Modules에 있는 CloudConnector 모듈이 있는지 확인 합니다.
    
    - 이 위치에 CloudConnector 모듈이 있는지 확인 한 후에는 모듈 위치에 대 한 경로를 저장 하는 PSModulePath 환경 변수를 변경할 수 있습니다.
    
     a. 임시 변경: 관리자 권한으로 Powershell을 시작 하 고 $env:P SModulePath = $env:P SModulePath + "명령을 실행 합니다. C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 영구적으로 변경 하려면 PowerShell을 관리자 권한으로 시작 하 고 다음 명령을 하나씩 실행 합니다. $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + ";) C:\Program Files\WindowsPowerShell\Modules "," Machine ")

    
## <a name="install-windows-updates-manually"></a>수동으로 Windows 업데이트 설치

사용자 환경에서 자동 업데이트를 사용 하지 않으려면 다음 단계를 수행 하 여 Windows 업데이트를 수동으로 확인 하 고 적용 합니다. Windows 업데이트를 확인 하 고 설치 하려면 서버를 다시 시작 해야 할 수 있습니다. 호스트 서버를 다시 시작 하면 사용자가 클라우드 커넥터를 사용 하 여 전화를 걸거나 받을 수 없게 됩니다. 업데이트를 수동으로 확인 하 고 설치한 후 업데이트가 수행 되는 시기를 제어할 수 있으며, 서비스 중단을 방지 하기 위해 필요한 경우 컴퓨터를 다시 시작 해야 합니다.
  
업데이트를 수동으로 확인 하려면 각 호스트 서버에 연결 하 고 **제어판**을 엽니다. **시스템 및 보안 \> Windows Update**를 선택한 다음 환경에 맞게 업데이트 및 서버 다시 시작을 관리 합니다.
  
- 사이트에 기기가 하나뿐인 경우 각 가상 컴퓨터에 연결 하 고 **제어판**을 엽니다. **시스템 및 보안 \> Windows 업데이트**를 선택 하 고 적절 하 게 업데이트 및 서버 다시 시작을 구성 합니다.
    
- 사이트에 기기가 두 개 이상 있는 경우 업데이트 하 고 다시 시작 하는 인스턴스를 업데이트할 때 사용자가 액세스할 수 없습니다. 사용자는 모든 가상 컴퓨터와 모든 비즈니스용 Skype 서비스가 업데이트를 완료 한 후에 시작할 때까지 배포의 다른 인스턴스에 연결 합니다. 서비스 중단 가능성을 방지 하려면 업데이트를 적용 하는 동안 HA에서 인스턴스를 제거한 다음 완료 되 면 복원 하면 됩니다. 방법은 다음과 같습니다.
    
1. 각 호스트 서버에서 PowerShell 콘솔을 관리자 권한으로 엽니다.
    
2. 다음 cmdlet을 사용 하 여 HA에서 인스턴스를 제거 합니다.
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    단일 인스턴스에 대 한 단계를 수행 하 여 업데이트를 수동으로 적용 하 고 가상 컴퓨터를 다시 시작 합니다.
    
4. 다음 cmdlet을 사용 하 여 인스턴스를 다시 HA로 설정 합니다.
    
   ```powershell
   Exit-CcUpdate
   ```

다중 사이트 배포의 경우 배포의 각 사이트에 대해 단일 사이트에 대 한 단계를 수행 하 여 한 번에 한 사이트에 업데이트를 적용 합니다.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치할 때의 팁

클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치 해야 하는 경우 다음 제외 항목을 추가 해야 합니다.
  
- 각 컴퓨터의 로컬 기기 디렉터리
    
- 각 컴퓨터의 원격 사이트 디렉터리
    
- 컴퓨터의 로컬 사이트 디렉터리가 공유 사이트 루트 폴더를 호스팅합니다.
    
- 비즈니스용%ProgramFiles%\Skype Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- 프로세스 Microsoft.Rtc.CCE.ManagementService.exe입니다.
