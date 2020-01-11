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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 클라우드 커넥터 에디션 배포 문제를 해결 합니다.
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002078"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>클라우드 커넥터 배포 문제 해결
 
클라우드 커넥터 에디션 배포 문제를 해결 합니다.
  
이 항목에서는 클라우드 커넥터 에디션 배포의 일반적인 문제에 대 한 해결 방법에 대해 설명 합니다. PSTN (공개 교환 전화 네트워크)에 대 한 호출과 관련 된 문제가 발생 하는 경우이 항목에 설명 된 해결 방법을 수행 하 여 조사해 볼 수 있습니다.
  
클라우드 커넥터는 일부 문제를 자동으로 해결 하기 위한 기본 제공 메커니즘을 제공 합니다. 자동 검색 프로세스는 클라우드 커넥터 기기와 관련 된 잠재적인 문제를 찾고, 가능한 경우 관리자의 개입 없이 이러한 문제를 해결 하기 위해 정정 작업을 수행 해야 합니다. 검색 프로세스는 다음과 같이 작동 합니다.
  
- **검색 순서:** 클라우드 커넥터 관리 서비스는 기기가 작동 하는지 여부를 감지 하기 위해 60 초 마다 프로세스를 실행 합니다. 클라우드 커넥터 버전 2.0 이상에서 검색 프로세스는 비즈니스용 Skype Corpnet 스위치를 사용 하 여 클라우드 커넥터 컴퓨터에 대 한 PowerShell 연결을 만듭니다. 2.0 이전 버전의 경우 검색 프로세스는 클라우드 커넥터 관리 스위치를 사용 합니다.
    
    > [!NOTE]
    > 자동 복구를 수행 하려면 호스트 네트워크 스위치를 통해 호스트와 가상 컴퓨터 간에 네트워크 연결이 필요 합니다. 자동 검색 및 복구가 성공할 수 있도록 네트워크 연결을 확인 해야 합니다. 
  
- **모니터링:** 다음 서비스는 클라우드 커넥터 버전 2.0 이상에서 모니터링 됩니다.
    
  - 가상 컴퓨터가 클라우드 커넥터에 연결 되어 있지 않음 회사 또는 인터넷 가상 스위치
    
  - 가상 머신이 저장 또는 중지 상태입니다.
    
  - 중앙 관리 서버 서비스: 복제본, 마스터
    
  - 중재 서버 서비스: REPLICA, RTCSRV 및 MEDSVC
    
  - Edge 서버 서비스: 복제본, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - 경계 서버에서 CS RTCSRV에 대 한 인바운드 방화벽 규칙을 사용할 수 없음, 중재 서버에서 CS RTCMEDSRV
    
    클라우드 커넥터 버전 1.4.2에서는 다음 서비스만 모니터링 됩니다.
    
  - 중재 서버 서비스: RTCSRV 및 MEDSVC
    
  - Edge 서버 서비스: RTCSRV
    
- **복구 프로세스:** 모니터링 되는 서비스가 중단 된 경우 기기는 아래로 표시 되며, 모든 문제를 해결할 수 있을 때까지 서비스가 중지 되 고 수동으로 표시 됩니다. 이렇게 하면 기기에 대 한 라우팅이 호출 실패를 유발할 수 있습니다.
    
    클라우드 커넥터 관리 서비스가 다음과 같이 자동 복구를 다시 시도 합니다.
    
  - 초기 다시 시도 간격은 최대 간격 시간인 1 시간이 10 초 간격입니다.
    
  - 처음 세 가지 복구 시도의 경우 간격 시간은 10 초입니다. 네 번째 다시 시도부터 간격 시간이 이전 간격의 두 배로 증가 합니다. 예를 들어 네 번째 다시 시도는 20 초, 5 번째 40 초에 발생 합니다. 
    
  - 1 시간의 최대 기간 시간에 도달 하면 시간 당 한 번씩 다시 시도 합니다.
    
  - 복구에 성공 하면 간격 및 재시도 횟수가 초기 값으로 설정 됩니다.
    
  - 관리 서비스를 다시 시작 하면 간격 및 재시도 횟수가 초기 값으로 다시 설정 됩니다.
    
## <a name="troubleshooting"></a>해결사

다음은 일반적으로 발생 하는 문제에 대 한 해결 방법입니다.
  
- **문제: 배포 스크립트를 실행할 때 배포에 실패 하거나 응답을 중지 합니다. 각 VM에 로그온 한 후에는 관리/내부/외부 NIC에 대 한 IP 주소가 없거나 올바르지 않습니다.**
    
    **해결 방법:** 이 문제는 자동으로 해결 되지 않습니다. Nic를 실행 하는 동안 Vm에 추가할 수 없습니다. Hyper-v 관리자에서이 Vm을 종료 하 고 제거한 후 다음 cmdlet을 실행 하세요.
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **문제: Active Directory 서버 및 포리스트가 설치 된 후 CMS 서버 및/또는 중재 서버가 도메인에 올바르게 가입 하지 않았습니다.**
    
    **해결 방법:** 이 문제를 해결 하려면 다음 단계를 수행 합니다.
    
  - Active Directory 서버에 로그온 하 고 도메인이 올바르게 만들어졌는지 확인 합니다.
    
  - CMS/중재 서버에 로그온 하 고 corpnet NIC에서 유효한 IP 주소를 할당 하 고 유효한 고정 IP 및 DNS가 광고 서버의 IP 주소로 구성 되어 있는지 확인 합니다.
    
  - CMS/중재 서버에 로그온 하 고 명령 프롬프트를 엽니다. Active Directory 서버의 FQDN과 IP 주소를 ping 할 수 있는지 확인 합니다. 사용할 수 없는 경우 IP 주소 충돌이 있을 수 있습니다. Active Directory에 대 한 새 IP를 할당 하 고 그에 따라 CMS/조정 서버에서 DNS를 업데이트 해 보세요.
    
- **문제: "제거-VMSwitch: 가상 이더넷 스위치 제거 중에 실패 했습니다." 오류 메시지가 표시 됩니다. 가상 스위치 ' 클라우드 커넥터 관리 스위치 '는 가상 컴퓨터를 실행 하거나 자식 풀에 할당 되어 있어 삭제할 수 없습니다. "**
    
    **해결 방법:** "클라우드 커넥터 관리 스위치"는 배포 후 삭제 되지 않았습니다. 이 오류가 발생 하는 경우 Hyper-v 관리자로 이동 하 여 아직 연결 된 가상 머신이 없는지 확인 하세요. 아직 연결 된 가상 컴퓨터가 있으면 연결을 끊고 관리 스위치를 삭제 합니다. 여전히 관리 스위치를 삭제할 수 없는 경우 호스트 서버를 다시 시작 하 고 다시 시도 합니다.
    
- **문제: 다음 오류 메시지가 표시 되는 경우 "서비스 RTCMRAUTH을 시작 하지 못했습니다. 서비스를 사용할 수 있는지 확인 합니다. "**
    
    > [!NOTE]
    > 이 문제는 1.4.2 보다 이전의 클라우드 커넥터 버전에만 적용 됩니다. 
  
    이 프런트 엔드 서버를 이전에 장애 조치 (컴퓨터 장애 조치 사용) 했기 때문에 시작 하지 못할 수도 있습니다. 이 경우에는 장애 복구 (컴퓨터 장애 복구 사용)를 호출 하십시오.
    
    **해결 방법:** 이 문제는 edge 서버에서 루트 CA 인증서 또는 중개 CA 인증서를 신뢰 하지 않는 경우 Edge 서버에서 발생 합니다. 외부 인증서를 가져올 수 있지만 인증서 체인이 끊어지면 마찬가지입니다. 이 조건에서 RTCMRAUTH 및/또는 RTCSRV 서비스를 시작할 수 없습니다.
    
    외부 인증서의 루트 CA 인증서와 모든 중간 CA 인증서를 수동으로 Edge 서버에 가져온 다음 Edge 서버를 다시 시작 하세요. Edge 서버에서 RTCMRAUTH 및 RTCSRV 서비스가 시작 된 것을 확인 한 후에는 호스트 서버로 돌아가서 PowerShell 콘솔을 관리자로 실행 하 고 다음 cmdlet을 실행 하 여 새 배포로 전환 합니다.
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **문제: Windows 업데이트가 적용 되 고 서버에서 서비스를 제공 하는 호출이 실패 하는 경우 호스트 서버가 다시 시작 되었습니다.**
    
    **해결 방법:** 고가용성 환경을 배포한 경우 Microsoft에서는 Windows update를 수동으로 확인 하 고 설치할 때 호스트 컴퓨터 (배포 인스턴스)를 현재 토폴로지 안이나 밖으로 이동 하는 데 도움이 되는 cmdlet을 제공 합니다. 이 작업을 수행 하려면 다음 단계를 사용 합니다.
    
1. 호스트 서버에서 PowerShell 콘솔을 관리자로 시작한 후 다음을 실행 합니다.
    
   ```powershell
   Enter-CcUpdate
   ```

2. 업데이트를 확인 하 고 사용 가능한 경우 설치 합니다.
    
3. PowerShell 콘솔에서 다음 cmdlet을 실행 합니다.
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **문제: PSTN 번호를 사용 하 여 비즈니스용 Skype 클라이언트에서 통화를 하는 경우, 다른 PSTN 번호를 초대 하 여 통화를 전화 회의로 전달할 수 없습니다.**
    
    **해결 방법:** 이 문제를 해결 하려면 [온라인 하이브리드 중재 서버 설정 구성을](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)참조 하세요.
    
- **문제: Active Directory server를 설치할 때 Windows 업데이트에 대 한 경고 메시지가 표시 됨-"Windows 자동 업데이트가 활성화 되지 않았습니다." 새로 설치 된 역할 또는 기능이 자동으로 업데이트 되도록 하려면 Windows Update를 설정 하세요. "**
    
    **해결 방법:** 비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 원격 PowerShell 세션을 실행 한 후 다음 cmdlet을 실행 하 여 사이트의 _Enableautoupdate 업데이트_ 구성을 확인 합니다.
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    _Enableautoupdate 업데이트_ 를 **True**로 설정 하면 CCEManagement 서비스에서 가상 컴퓨터와 호스트 서버 모두에 대해 Windows 업데이트를 다운로드 하 고 설치 하는 것을 처리 하기 때문에이 경고 메시지를 무시 해도 됩니다. _Enableautoupdate 업데이트_ 를 **False**로 설정한 경우 다음 cmdlet을 실행 하 여 **True**로 설정 합니다.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    또는 수동으로 업데이트를 확인 하 고 설치할 수 있습니다. 다음 섹션을 참조 하세요.
    
- **문제: 현재 \<입력/구성 SiteName\> 또는 \<ApplianceName\> 또는 \<중재 서버 FQDN\> 또는 \<중재 서버 IP 주소가\> 기존 기기와 충돌 하기 때문에 기기를 등록할 수 없습니다. 충돌 하는 기기를 제거 하거나 입력/구성 정보를 업데이트 한 다음 다시 등록 합니다. ' 등록-CcAppliance를 실행 하 여 현재 기기를 온라인에 등록할 수 있습니다.**
    
    **해결 방법:** \<\>ApplianceName, \<중재 서버\> FQDN 및 \<중재 서버 IP 주소\> 에 대 한 값은 고유 하 고 하나의 기기 등록에만 사용 해야 합니다. 기본적으로 \<ApplianceName\> 는 호스트 이름에서 가져옵니다. \<구성 ini 파일\> 에 \<정의 된 중재 서버\> FQDN 및 중재 서버 IP 주소
    
    예를 들어 (ApplianceName = MyserverNew, 중재 서버 FQDN = .com, 중재 서버 IP 주소 = 10.10.10.10)을 사용 하 여 SiteName에 등록 하는 경우 (ApplianceName = Myserver, 중재 서버 FQDN = ms.contoso.com, 중재 서버 IP 주소 = 10.10.10.10), 충돌을 받을 수 있습니다.
    
    먼저 ApplianceRoot directory 섹션의 CloudConnector .ini 파일을 확인 하세요. SiteName \<\> \<, 중재 서버 FQDN\> 및 \<중재 서버 IP 주소\> 값을 파일에 가져옵니다. \<ApplianceName\> 는 호스트 서버 이름입니다.
    
    그런 다음 비즈니스용 Skype 테 넌 트 관리자 자격 증명을 사용 하 여 테 넌 트 원격 PowerShell을 실행 한 후 다음 cmdlet을 실행 하 여 등록 된 기기를 확인 합니다.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    충돌을 식별 한 후 등록 된 기기와 일치 하는 정보를 사용 하 여 CloudConnector .ini 파일을 업데이트 하거나 기존 기기를 등록 취소 하 여 충돌을 해결할 수 있습니다.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **문제: 호스트에서 실행 되는 배포 된 기기가 있는 경우 CcRunningVersion cmdlet은 빈 값을 반환 합니다.**
    
  **해결 방법:** 1.3.4 또는 1.3.8에서 1.4.1으로 업그레이드할 때이 문제가 발생할 수 있습니다. .Msi와 함께 버전 1.4.1을 설치한 후에는 다른 cmdlet을 `Register-CcAppliance` 실행 하기 전에 실행 해야 합니다. `Register-CcAppliance`%UserProfile%\CloudConnector 에서%ProgramData%\CloudConnector.로 모듈 .ini 파일을 마이그레이션합니다. 이 파일을 놓친 경우%ProgramData%\CloudConnector 폴더에서 새 모듈 .ini가 만들어지고 1.3.4 또는 1.3.8의 실행 중인/백업 버전 정보를 바꿉니다.
    
  %UserProfile%\CloudConnector 및%ProgramData%\CloudConnector 폴더에서 모듈 .ini 파일을 비교 합니다. 차이점이 있으면%ProgramData%\CloudConnector에서 모듈 .ini 파일을 삭제 하 고 다시 실행 `Register-CcAppliance`합니다. 또한 올바른 실행 및 백업 버전으로 파일을 수동으로 수정할 수도 있습니다.
    
- **문제: 현재 스크립트 버전과 다른 이전 버전으로 전환 하는 Switch-CcVersion cmdlet을 실행 한 후에는이 이전 버전에 대 한 고가용성 지원이 제공 되지 않습니다.**
    
    **해결 방법:** 예를 들어 1.4.1에서 1.4.2로 업그레이드 했습니다. 실행으로 확인할 `Get-CcVersion`수 있는 현재 스크립트 버전 및 실행 중인 버전이 모두 1.4.2를 확인할 `Get-CcRunningVersion` 수 있습니다. 이번에는 실행 중인 버전을 `Switch-CcVersion` 1.4.1로 다시 전환 하면 이전 버전에 대 한 고가용성 지원이 제공 되지 않습니다.
    
    고가용성 지원을 받으려면 1.4.2으로 다시 전환 하 여 실행 중인 버전 및 스크립트 버전이 동일 해야 합니다. 1.4.2 배포에 문제가 발생 하는 경우 최대한 빨리 제거 하 고 다시 설치 하세요.
    
- **문제: 중앙 관리 저장소, 중재 서버 및 Edge 서버에 발급 된 인증 기관 인증서 또는 내부 인증서가 거의 만료 되거나 손상 되었습니다.**
    
    **해결 방법:** Skype for Business 인증 기관 인증서는 5 년 동안 유효 합니다. 중앙 관리 저장소, 중재 서버 및 Edge 서버에 발급 된 내부 인증서는 2 년 동안 유효 합니다.
    
    > [!NOTE]
    > 클라우드 커넥터 버전 2.0 이상에서 CcServerCertificate cmdlet이 업데이트-CcServerCertificate로 변경 되었으며 CcCACertificate cmdlet이 업데이트-CcCACertificate으로 변경 되었습니다. 
  
    중앙 관리 저장소, 중재 서버 및 Edge 서버에 발급 된 내부 인증서가 거의 만료 되거나 손상 된 경우에는 CcServerCertificate 갱신 또는 업데이트-CcServerCertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.
    
    인증 기관 인증서가 곧 만료 되는 경우 갱신-CcCACertificate 또는 업데이트-CcCACertificate cmdlet을 실행 하 여 인증서를 갱신 합니다.
    
    **인증 기관 인증서가 손상 되 고 사이트에 하나의 기기만 있는 경우** 다음 단계를 수행 합니다.
    
1. 서비스를 드레이닝 하기 위해 Enter-CcUpdate cmdlet을 실행 하 여 기기를 유지 관리 모드로 전환 합니다.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 다음 cmdlet을 실행 하 여 새 인증 기관 인증서 및 모든 내부 서버 인증서를 재설정 하 고 만듭니다.
    
    클라우드 커넥터 릴리스 2.0:
    
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
    
1. 첫 번째 기기에서 CcCertificationAuthorityFile cmdlet을 실행 하 여 \<SiteRoot\> directory에서 CA 백업 파일을 정리 합니다.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. 서비스를 드레이닝 하 고 각 기기를 유지 관리 모드로 전환 하려면 Enter-CcUpdate cmdlet을 실행 합니다.

     ```powershell
     Enter-CcUpdate
     ```
    
3. 첫 번째 기기에서 다음 cmdlet을 실행 하 여 새 인증 기관 인증서 및 모든 내부 서버 인증서를 재설정 하 고 만듭니다.
    
     클라우드 커넥터 릴리스 2.0:
    
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

4. 첫 번째 기기에서 다음 cmdlet을 실행 하 여 CA 파일을 \<SiteRoot\> 폴더에 백업 합니다.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 동일한 사이트의 다른 모든 기기의 경우 다음 명령을 실행 하 여 CA 백업 파일을 사용 하 고, 기기가 모두 동일한 루트 인증서를 사용 하도록 한 다음 새 인증서를 요청 합니다. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 게이트웨이와 중재 서버 간에 TLS를 사용 하는 경우 사이트의 모든 기기에서 Export-CcRootCertificate cmdlet을 실행 한 다음, 내보낸 인증서를 PSTN 게이트웨이에 설치 합니다. 게이트웨이에서 인증서를 다시 발급 해야 할 수도 있습니다.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 서비스를 시작 하 고 유지 관리 모드를 종료 하려면 CcUpdate cmdlet을 실행 합니다. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **문제: 클라우드 커넥터 관리 서비스 로그, "비즈니스용 Files\Skype 클라우드 커넥터 Edition\ManagementService\CceManagementService.log": CceService 오류: 0: 온라인 상태를 보고할 때 예기치 않은 예외가 발생 함:: 사용자 \<전역 테 넌 트 관리자\>에 대 한 로그온이 실패 했습니다. 새 자격 증명 개체를 만들어 올바른 사용자 이름 및 암호를 사용 했는지 확인 하십시오. ---\>**
    
    **해결 방법:** 클라우드 커넥터 기기가 등록 된 이후 Office 365 전역 테 넌 트 관리자 자격 증명이 변경 되었습니다. 클라우드 커넥터 기기에서 로컬로 저장 된 자격 증명을 업데이트 하려면 호스트 기기에서 다음을 실행 합니다.
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **문제: 배포에 사용 된 호스트 서버 계정의 암호를 변경한 후에는 "ConvertTo-SecureString: 키를 지정 된 상태에서 사용 하도록 올바르지 않습니다." 라는 오류 메시지가 나타납니다. "비즈니스용 클라우드 커넥터%ProgramFiles%\Skype Edition\ManagementService\CceManagementService.log 또는-CcCredential cmdlet을 실행 중입니다.**
    
    **해결 방법:** 모든 클라우드 커넥터 자격 증명이 다음 파일에 저장 됩니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>". 호스트 서버의 암호가 변경 되 면 로컬로 저장 된 자격 증명을 업데이트 해야 합니다.
    
    **클라우드 커넥터 버전 1.4.2를 실행 하는 경우** 다음 단계에 따라 모든 클라우드 커넥터 암호를 다시 생성 합니다.
    
  1. 호스트 서버를 다시 시작 합니다.
    
  2. 다음 파일을 삭제%SystemDrive%\Programdata\Cloudconnector\credentials.. \<CurrentUser\>".
    
  3. PowerShell 콘솔을 관리자로 실행 한 다음 "등록-CcAppliance-로컬"을 실행 하 여 설명 다음에 암호를 다시 입력 합니다. 클라우드 커넥터 배포에 대해 이전에 입력 한 암호를 입력 합니다.
    
     **클라우드 커넥터 버전 2.0 이상을 실행 하는 경우** 다음 단계에 따라 모든 클라우드 커넥터 암호를 다시 생성 합니다.
    
  4. 호스트 서버를 다시 시작 합니다.
    
  5. 다음 파일을 삭제%SystemDrive%\Programdata\Cloudconnector\credentials.. \<CurrentUser\>".
    
  6. PowerShell 콘솔을 관리자로 실행 한 다음 "등록-CcAppliance-로컬"을 실행 하 여 설명 다음에 암호를 다시 입력 합니다. 
    
     클라우드 커넥터 버전 1.4.2를 사용 하 여 캐시 된 암호 파일을 생성 한 경우에는 메시지가 표시 되 면 CceService password의 VMAdmin 암호를 사용 합니다. 다른 모든 계정의 클라우드 커넥터 배포에 대해 이전에 입력 한 암호를 입력 합니다.
    
     클라우드 커넥터 버전 1.4.2를 사용 하 여 캐시 된 암호 파일을 생성 하 고 DomainAdmin 및 VMAdmin 암호가 서로 다른 경우 다음 단계를 수행 해야 합니다.
    
  7. 다음과 같이 Set-CcCredential-AccountType DomainAdmin을 실행 합니다.
    
  8. 이전 계정 자격 증명을 묻는 메시지가 나타나면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
  9. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 DomainAdmin 암호의 암호를 입력 합니다.
    
     캐시 된 암호 파일이 클라우드 커넥터 버전 2.0 이상으로 생성 된 경우, 기본적으로 VmAdmin 및 DomainAdmin에서 CceService와 동일한 암호를 사용 합니다. DomainAdmin 및 VMAdmin 암호를 변경한 경우 다음 단계를 수행 해야 합니다.
    
  10. 다음과 같이 Set-CcCredential-AccountType DomainAdmin을 실행 합니다.
    
       1. 이전 계정 자격 증명을 묻는 메시지가 나타나면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
       2. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 DomainAdmin 암호의 암호를 입력 합니다.
    
  11. 다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.
    
       1. 이전 계정 자격 증명을 묻는 메시지가 나타나면 CceService 암호에 사용한 자격 증명을 입력 합니다.
    
       2. 새 계정 자격 증명을 묻는 메시지가 표시 되 면 이전에 사용한 VmAdmin 암호의 암호를 입력 합니다. 
    
- **문제: 클라우드 커넥터 버전 2.1 이상을 사용 하는 경우 기기에서 Register-CcAppliance 또는 기타 cmdlet을 실행 하는 경우 다음과 같은 오류 메시지가 표시 됩니다 (각 개체에 대해 ' 공용 ' 속성을 찾을 수 없습니다.). 속성이 있는지 확인 합니다. C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char: 14 "**
    
    **해결 방법:** 클라우드 커넥터 2.1 이상에는 .NET Framework 4.6.1 이상이 필요 합니다. 기기의 .NET Framework를 버전 4.6.1 이상으로 업데이트 하 고 cmdlet을 다시 실행 하세요.

- **문제: Cloud Connector Edition 2.1를 사용 하는 경우 설치-CcAppliance를 실행할 때 "다음과 같은 오류 메시지가 표시 됩니다. 오류로 인해 새 인스턴스를 설치 하지 못했습니다. 문자열만 값으로 사용할 수 있으므로" State "를 설정할 수 없습니다.**

   **해결 방법:** Cloudconnector .ini의 [Common] 섹션 아래에 "State" 구성을 아래와 같이 추가 합니다. CountryCode = US 상태 = WA 구/군/시 = Redmond

   "State" 줄에 값이 있어야 하는 것은 아니지만, Cloudconnector .ini 파일에서 "State" 줄을 제거할 수 없습니다.

- **문제: "WindowsImage: WindowsImage에 오류가 발생 하 여 다음 오류 메시지가 나타납니다. 클라우드 커넥터 에디션을 설치 또는 업그레이드할 때 발생 하는 오류 코드 = 0xc1550115 ".**
    
    **해결 방법:** PowerShell 콘솔을 관리자로 시작 하 고 "DISM-Cleanup-Wim '"을 실행 합니다. 모든 troubled 이미지를 정리 합니다. 설치-CcAppliance를 다시 실행 하거나 비트가 자동으로 업그레이드 될 때까지 기다립니다.
    
- **문제: HA 환경에서 첫 번째 클라우드 커넥터 기기의 배포에 실패 함**
    
    **해결 방법:** 수행 하는 단계는 배포 실패 원인에 따라 달라 집니다.
    
  - 첫 번째 클라우드 커넥터 기기에 오류가 발생 하 여 실패의 원인을 확인할 수 없는 경우에는 배포가 성공할 때까지 기기를 다시 설치 하 고 다른 기기를 설치 해야 합니다.
    
  - 첫 번째 클라우드 커넥터 기기에 외부 인증서 문제 등의 사소한 문제가 발생 하는 경우 기기를 다시 설치 하지 않고도 문제를 해결할 수 있습니다. 그런 다음 테 넌 트 원격 PowerShell을 사용 하 여 배포를 다음과 같이 성공적으로 표시할 수 있습니다. 첫 번째 배포에 성공한 경우 다음 단계를 사용할 수도 있지만, 경우에 따라 클라우드 커넥터에서 배포를 성공으로 보고할 수 없는 이유가 있습니다.
    
  - 첫 번째 클라우드 커넥터 기기의 Id (GUID)를 가져오려면 CsHybridPSTNAppliance cmdlet을 실행 합니다.
    
  - 기기를 성공적으로 배포 된 것으로 표시 하려면 다음과 같이 Set-CsCceApplianceDeploymentStatus를 실행 합니다.
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **문제: 호스트 서버 또는 가상 컴퓨터에서 Windows 업데이트를 수동으로 확인 하 고 설치 해야 합니다.**
    
   **해결 방법:** 비즈니스용 Skype 클라우드 커넥터 에디션이 제공 하는 자동화 된 OS 업데이트를 이용 하는 것이 좋습니다. 온라인 관리에 기기를 등록 하 고 자동 OS 업데이트를 사용 하도록 설정한 후에는 호스트 서버와 가상 컴퓨터가 OS 업데이트 시간 창 설정에 따라 Windows 업데이트를 자동으로 확인 하 고 설치 합니다.
    
   Windows 업데이트를 수동으로 확인 하 고 설치 해야 하는 경우에는 배포 유형에 적용 되는 단계를 따르세요. 호스트 서버와 동시에 실행 되는 가상 컴퓨터를 업데이트 하는 계획을 세워야 업데이트에 필요한 하위 시간을 최소화할 수 있습니다.
    
   원하는 경우 WSUS (Windows Server Update Services) 서버를 사용 하 여 클라우드 커넥터 서버에 대 한 업데이트를 제공할 수 있습니다. Windows 업데이트가 자동으로 설치 **되지** 않도록 구성 하는 것입니다.
    
   클라우드 커넥터 배포를 수동으로 업데이트 하는 방법에 대 한 자세한 내용은 다음 섹션을 참조 하세요.
    
- **문제: 클라우드 커넥터가 새 빌드로 업데이트 되 면 클라우드 커넥터 cmdlet이 업데이트 되지 않습니다.** 이는 자동 업데이트가 발생할 때 PowerShell 창이 열려 있는 경우에 발생할 수 있습니다.
    
  **해결 방법:** 업데이트 된 cmdlet을 로드 하려면 다음 단계 중 하나를 수행 하면 됩니다.
    
   - 클라우드 커넥터 기기에서 PowerShell을 닫은 다음 PowerShell을 다시 엽니다.
    
     - 또는 가져오기-모듈 CloudConnector-Force를 실행할 수 있습니다. 
 
-   **문제: "' Stop-CsWindowsService ' 라는 용어는 cmdlet, 함수, 스크립트 파일 또는 실행할 수 있는 프로그램의 이름으로 인식 되지 않습니다."-CcUpdate cmdlet을 실행 하려고 할 때 발생 하는 오류입니다.**

    **해결 방법:** $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 파일을 삭제 합니다.
PowerShell은 발견 되는 모든 모듈을 다시 분석할 필요가 없도록 해당 모듈의 cmdlet 캐시로이 파일을 생성 하 여 실제로 성능이 느려지는 것을 확인 합니다. 대부분의 경우, 해당 캐시에서 다시 읽어 온 경우 PowerShell에 잘못 된 결과가 제공 되는 일부 파일이 손상 되었을 수 있습니다.

-   **문제: "Import-module CloudConnector" 오류 생성 "가져오기-모듈: 모듈 디렉터리에서 올바른 모듈 파일을 찾을 수 없으므로 지정 된 모듈" CloudConnector "가 로드 되지 않았습니다."**

    **확인과**
    - 이 (가) CloudConnector 모듈이 c:\Program Files\WindowsPowerShell\Modules에 존재 하는지 확인 합니다.
    
    - 이 위치에 CloudConnector 모듈이 있는지 확인 한 후 모듈 위치에 대 한 경로를 저장 하는 PSModulePath 환경 변수는 다음과 같이 변경 될 수 있습니다.
    
     에서. 임시 변경: Powershell을 관리자로 시작 하 고 다음 명령을 실행 합니다 ($env:P SModulePath = $env:P SModulePath + "). C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 영구 변경의 경우 PowerShell을 관리자로 시작 하 고 다음 명령을 하나씩 ($CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + ") 합니다. C:\Program Files\WindowsPowerShell\Modules "," Machine ")

    
## <a name="install-windows-updates-manually"></a>수동으로 Windows 업데이트 설치

환경에서 자동 업데이트를 사용 하지 않으려는 경우 다음 단계에 따라 Windows 업데이트를 수동으로 확인 하 고 적용 합니다. Windows 업데이트를 확인 하 고 설치 하려면 서버를 다시 시작 해야 할 수 있습니다. 호스트 서버를 다시 시작 하면 사용자가 클라우드 커넥터를 사용 하 여 전화를 걸거나 받을 수 없게 됩니다. 업데이트를 수동으로 확인 하 고 설치한 다음 서비스 중단을 방지 하기 위해 필요에 따라 컴퓨터를 다시 시작할 수 있습니다.
  
수동으로 업데이트를 확인 하려면 각 호스트 서버에 연결 하 고 **제어판**을 엽니다. **시스템 및 보안 \>Windows 업데이트**를 선택한 다음 환경에 맞게 업데이트 및 서버 다시 시작을 관리 합니다.
  
- 사이트에 하나의 기기만 있는 경우 각 가상 컴퓨터에 연결 하 고 **제어판**을 엽니다. **시스템 및 보안 \>Windows 업데이트**를 선택한 다음 적절 하 게 업데이트 및 서버 다시 시작을 구성 합니다.
    
- 사이트에 둘 이상의 기기가 있는 경우 업데이트 하는 동안 사용자가 업데이트 및 다시 시작 하는 인스턴스에 액세스할 수 없습니다. 업데이트를 완료 한 후 모든 가상 컴퓨터와 모든 비즈니스용 Skype 서비스가 시작 될 때까지 사용자는 배포의 다른 인스턴스에 연결 합니다. 잠재적인 서비스 중단을 방지 하기 위해 업데이트를 적용 하는 동안 HA에서 인스턴스를 제거한 다음 완료 되 면 복원할 수 있습니다. 실행할 작업:
    
1. 각 호스트 서버에서 PowerShell 콘솔을 관리자로 엽니다.
    
2. 다음 cmdlet을 사용 하 여 HA에서 인스턴스를 제거 합니다.
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    단일 인스턴스에서 수동으로 업데이트를 적용 하 고 가상 컴퓨터를 다시 시작 하는 단계를 따르세요.
    
4. 다음 cmdlet을 사용 하 여 인스턴스를 HA로 다시 설정 합니다.
    
   ```powershell
   Exit-CcUpdate
   ```

다중 사이트 배포의 경우 한 번에 하나의 사이트에 업데이트를 적용 하 여 배포의 각 사이트에 대 한 단일 사이트에 대 한 단계를 수행 합니다.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치할 때의 팁

클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치 해야 하는 경우 다음 제외를 추가 해야 합니다.
  
- 각 컴퓨터의 로컬 기기 디렉터리
    
- 각 컴퓨터의 원격 사이트 디렉터리
    
- 컴퓨터의 로컬 사이트 디렉터리가 공유 사이트 루트 폴더를 호스팅합니다.
    
- 비즈니스용%ProgramFiles%\Skype Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- CCE. ManagementService를 처리 합니다.
