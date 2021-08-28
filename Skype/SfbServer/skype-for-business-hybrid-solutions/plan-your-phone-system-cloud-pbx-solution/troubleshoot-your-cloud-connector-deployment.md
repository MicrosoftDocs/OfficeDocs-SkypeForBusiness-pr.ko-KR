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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 클라우드 커넥터 버전 배포 문제 해결
ms.openlocfilehash: 95a3a89e4ae593ffa972f7b5de3891ee94aaeff6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623410"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>클라우드 커넥터 배포 문제 해결

> [!Important]
> Cloud Connector Edition은 온라인과 함께 2021년 7월 31일 비즈니스용 Skype 있습니다. 조직에서 사용자 Teams 직접 라우팅을 사용하여 Teams 방법을 [확인합니다.](/MicrosoftTeams/direct-routing-landing-page)
 
클라우드 커넥터 버전 배포 문제 해결
  
이 항목에서는 Cloud Connector Edition 배포의 일반적인 문제에 대한 해결법을 설명합니다. PSTN(Public Switched Telephone Network)과의 통화에 문제가 있는 경우 이 항목에 설명된 솔루션에 따라 조사할 수 있습니다.
  
Cloud Connector는 일부 문제를 자동으로 해결하기 위한 기본 제공 메커니즘을 제공합니다. 자동 검색 프로세스는 Cloud Connector 어플라이언스에서 발생할 수 있는 문제를 검색하고 가능한 경우 관리자의 개입 없이 해당 문제를 해결하기 위한 수정 조치를 취합니다. 검색 프로세스는 다음과 같이 작동합니다.
  
- **검색 시퀀스:** 클라우드 커넥터 관리 서비스는 어플라이언스가 다운되어 있는지 감지하기 위해 60초마다 프로세스를 실행합니다. 클라우드 커넥터 버전 2.0 이상에서는 검색 프로세스에서 비즈니스용 Skype Corpnet 스위치를 사용하여 클라우드 커넥터 컴퓨터로 PowerShell을 연결합니다. 2.0 이전 버전에서는 검색 프로세스에서 Cloud Connector 관리 스위치를 사용했습니다.
    
    > [!NOTE]
    > 자동 복구가 성공하려면 호스트 네트워크 스위치를 통해 호스트와 가상 컴퓨터 간에 네트워크 연결이 있어야 합니다. 네트워크 연결을 확인하여 자동 검색 및 복구가 성공할 수 있는지 확인합니다. 
  
- **모니터링:** 다음 서비스는 클라우드 커넥터 버전 2.0 이상에서 모니터링됩니다.
    
  - 가상 컴퓨터는 클라우드 커넥터 회사 또는 인터넷 가상 스위치에 연결되지 않습니다.
    
  - 가상 컴퓨터가 저장된 상태 또는 중지됨 상태인 경우
    
  - 중앙 관리 서버 서비스: REPLICA, MASTER
    
  - 중재 서버 서비스: REPLICA, RTCSRV 및 MEDSVC
    
  - 에지 서버 서비스: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - 에지 서버의 CS RTCSRV, 중재 서버의 CS RTCMEDSRV에 대해 인바운드 방화벽 규칙을 사용하지 않도록 설정
    
    클라우드 커넥터 버전 1.4.2에서는 다음 서비스만 모니터링됩니다.
    
  - 중재 서버 서비스: RTCSRV 및 MEDSVC
    
  - 에지 서버 서비스: RTCSRV
    
- **복구 프로세스:** 모니터링된 서비스가 다운되면 어플라이언스가 다운된 것으로 표시되어 모든 문제를 해결할 수 있을 때까지 서비스가 중지 및 수동으로 표시됩니다. 이렇게 하면 통화가 실패할 수 있는 어플라이언스로 통화가 라우팅되지 않습니다.
    
    클라우드 커넥터 관리 서비스가 다음과 같이 자동 복구를 다시 시도합니다.
    
  - 초기 다시 시도 간격은 10초마다 최대 간격이 1시간입니다.
    
  - 처음 세 번의 복구 시도의 간격 시간은 10초입니다. 네 번째 다시 시도부터 간격 시간이 이전 간격 시간의 두 배로 증가합니다. 예를 들어 네 번째 다시 시도는 20초, 5번째는 40초 등입니다. 
    
  - 1시간의 최대 간격에 도달하면 한 시간마다 한 번 다시 검색이 계속됩니다.
    
  - 복구에 성공하면 간격과 다시 시도 횟수가 초기 값으로 설정됩니다.
    
  - 관리 서비스를 다시 시작하면 간격과 다시 시도 횟수가 초기 값으로 다시 설정됩니다.
    
## <a name="troubleshooting"></a>문제 해결

다음은 일반적으로 발생하는 문제에 대한 해결 방법입니다.
  
- **문제: 배포 스크립트를 실행하면 배포가 실패하거나 응답하지 않습니다. 각 VM에 로그온한 후 관리/내부/외부 NIC에 대한 IP 주소가 누락되거나 잘못되었습니다.**
    
    **해결:** 이 문제는 자동으로 해결할 수 없습니다. NI는 실행되는 동안 VM에 추가할 수 없습니다. hyper-v 관리자에서 이러한 VM을 종료하고 제거한 후 다음 cmdlet을 실행합니다.
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **문제: Active Directory 서버 및 포리스트가 설치되면 CMS 서버 및/또는 중재 서버가 도메인에 올바르게 가입되지 않았습니다.**
    
    **해결:** 이 문제를 해결하기 위해 다음 단계를 수행합니다.
    
  - Active Directory 서버에 로그온하고 도메인이 올바르게 만들어졌습니다.
    
  - CMS/중재 서버에 로그온하고 corpnet NIC에서 유효한 IP 주소가 할당되어 있으며 유효한 고정 IP 및 DNS가 AD 서버의 IP 주소로 구성되어 있는지 확인해야 합니다.
    
  - CMS/중재 서버에 로그온하고 명령 프롬프트를 여는 경우 Active Directory 서버의 FQDN 및 IP 주소를 ping할 수 있는지 확인합니다. 이 경우 IP 주소 충돌이 있을 수 있습니다. Active Directory에 대한 새 IP를 할당하고 그에 따라 CMS/중재 서버에서 DNS를 업데이트하십시오.
    
- **문제: "Remove-VMSwitch : 가상 이더넷 스위치를 제거하는 동안 실패했습니다. 오류 메시지가 표시됩니다. 가상 컴퓨터를 실행하거나 자식 풀에 할당하는 데 사용 중이기 때문에 가상 스위치 '클라우드 커넥터 관리 스위치'를 삭제할 수 없습니다."**
    
    **해결:** "클라우드 커넥터 관리 스위치"는 배포 후에 삭제되지 않습니다. 이 오류가 발생하면 Hyper-v 관리자로 이동하여 여전히 가상 컴퓨터에 연결되어 있지 않은지 확인하세요. 가상 컴퓨터도 계속 연결되어 있는 경우 연결을 끊고 관리 스위치를 삭제합니다. 관리 스위치를 삭제할 수 없는 경우 호스트 서버를 다시 시작하고 다시 시도하십시오.
    
- **문제: "서비스 RTCMRAUTH를 시작하지 못했습니다. 서비스가 사용하지 않도록 설정되어 있지 않은지 검사합니다."**
    
    > [!NOTE]
    > 이 문제는 1.4.2 이전의 클라우드 커넥터 버전에만 적용됩니다. 
  
    이 프런트 엔드 서버가 이전에 장애 조치(fail over)했기 때문에 시작에 실패할 수도 있습니다(컴퓨터 장애 조치(fail over) 사용). 이 경우 장애 조치(fail back)를 호출합니다(컴퓨터 장애 조치(fail back) 사용).
    
    **해결:** 이 문제는 에지 서버에서 루트 CA 인증서 또는 중간 CA 인증서를 신뢰할 수 없는 경우 에지 서버에서 발생합니다. 외부 인증서를 가져올 수 있지만 인증서 체인이 손상된 경우에도 이 조건에서는 RTCMRAUTH 및/또는 RTCSRV 서비스를 시작할 수 없습니다.
    
    외부 인증서의 루트 CA 인증서와 모든 중간 CA 인증서를 에지 서버로 수동으로 가져온 다음 에지 서버를 다시 시작하십시오. 에지 서버에서 RTCMRAUTH 및 RTCSRV 서비스가 시작된 후 호스트 서버로 돌아가 관리자 권한으로 PowerShell 콘솔을 시작한 후 다음 cmdlet을 실행하여 새 배포로 전환합니다.
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **문제: 업데이트가 적용된 Windows 호스트 서버가 다시 시작되고 서버에서 서비스하는 통화가 실패합니다.**
    
    **해결:** 고가용성 환경을 배포한 경우 Microsoft는 업데이트를 수동으로 확인하고 설치할 때 하나의 호스트 컴퓨터(배포 인스턴스)를 현재 토폴로지로 이동하거나 현재 토폴로지에서 이동하는 데 도움이 되는 cmdlet을 Windows 제공합니다. 이 작업을 수행하기 위해 다음 단계를 수행합니다.
    
1. 호스트 서버에서 관리자 권한으로 PowerShell 콘솔을 시작한 다음 다음을 실행합니다.
    
   ```powershell
   Enter-CcUpdate
   ```

2. 업데이트를 확인하고 사용 가능한 업데이트를 설치합니다.
    
3. PowerShell 콘솔에서 다음 cmdlet을 실행합니다.
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **문제: PSTN 번호를 사용하여 비즈니스용 Skype 클라이언트에서 전화를 걸면 다른 PSTN 번호를 요청하여 전화가 전화 회의로 에스컬레이터될 수 없습니다.**
    
    **해결:** 이 문제를 해결 자세한 내용은 [Configure online hybrid Mediation Server 설정.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)
    
- **문제: Active Directory 서버를 설치할 때 Windows 업데이트에 대한 경고 메시지가 표시됩니다. "Windows 업데이트가 사용되지 않습니다. 새로 설치한 역할 또는 기능이 자동으로 업데이트되도록 Windows 켜야 합니다."**
    
    **해결:** 테넌트 관리자 자격 비즈니스용 Skype 사용하여 테넌트 원격 PowerShell 세션을 시작한 후 다음 cmdlet을 실행하여 _사이트의 EnableAutoUpdate_ 구성을 검사합니다.
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    _EnableAutoUpdate를_ **True로** 설정하면 CCEManagement 서비스가 가상 컴퓨터와 호스트 서버에 대한 Windows 업데이트 다운로드 및 설치를 처리하기 때문에 이 경고 메시지를 무시해도 됩니다. _EnableAutoUpdate를_ **False로** 설정하면 다음 cmdlet을 실행하여 **True로 설정하십시오.**
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    또는 업데이트를 수동으로 확인하고 설치할 수 있습니다. 다음 섹션을 참조하세요.
    
- **문제: 현재 입력/구성 또는 기존 어플라이언스와 충돌하거나 충돌하여 어플라이언스를 등록할 수 \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 없습니다. 충돌 어플라이언스를 제거하거나 입력/구성 정보를 업데이트한 다음 다시 등록합니다. ' when run Register-CcAppliance to register current appliance to online.**
    
    **해결:** 에 대한 값은 고유해야 하며 하나의 어플라이언스 \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 등록에만 사용됩니다. 기본적으로 호스트 \<ApplianceName\> 이름에서 온 것입니다. \<Mediation Server FQDN\> 및 \<Mediation Server IP Address\> 는 구성 ini 파일에 정의되어 있습니다.
    
    예를 들어 (ApplianceName= MyserverNew, 중재 서버 FQDN=ms.contoso.com, SiteName=MySite에 등록할 중재 서버 IP 주소=10.10.10.10이지만 등록된 어플라이언스(ApplianceName= Myserver, 중재 서버 FQDN=ms.contoso.com, 중재 서버 IP 주소=10.10.10.10)가 있는 경우 충돌이 있습니다.
    
    먼저 ApplianceRoot 디렉터리 섹션에서 CloudConnector.ini 파일을 확인합니다. 파일에 \<SiteName\> 및 \<Mediation Server FQDN\> 값이 \<Mediation Server IP Address\> 표시됩니다. \<ApplianceName\> 는 호스트 서버 이름입니다.
    
    둘째, 비즈니스용 Skype 테넌트 관리자 자격 증명을 사용하여 테넌트 원격 PowerShell을 시작한 후 다음 cmdlet을 실행하여 등록된 어플라이언스를 검사합니다.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    충돌을 식별한 후 등록된 어플라이언스와 일치하는 정보로 CloudConnector.ini 파일을 업데이트하거나 기존 어플라이언스 등록을 등록을 해소하여 충돌을 해결할 수 있습니다.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **문제: Get-CcRunningVersion 배포된 어플라이언스가 호스트에서 실행되는 경우 이 cmdlet은 빈 값을 반환합니다.**
    
  **해결:** 이 경우 1.3.4 또는 1.3.8에서 1.4.1로 업그레이드할 수 있습니다. 버전 1.4.1을 설치한 .msi 먼저 실행해야 다른 `Register-CcAppliance` cmdlet을 실행해야 합니다. `Register-CcAppliance` %UserProfile%\cloudConnector에서 %ProgramData%\CloudConnector로 module.ini 파일을 마이그레이션합니다. 이 폴더를 놓친 경우 새 module.ini %ProgramData%\CloudConnector 폴더에 만들어지며 1.3.4 또는 1.3.8에 대한 실행 중인/백업 버전 정보를 대체합니다.
    
  %module.ini%\CloudConnector 및 %ProgramData%\CloudConnector 폴더의 파일 비교 차이점이 있는 경우 %ProgramData%\cloudConnector에서 module.ini 파일을 삭제하고 다시  `Register-CcAppliance` 실행합니다. 또한 파일을 올바른 실행 및 백업 버전으로 수동으로 수정할 수도 있습니다.
    
- **문제: Switch-CcVersion cmdlet을 실행하여 현재 스크립트 버전과 다른 이전 버전으로 전환한 후 이 이전 버전에 대한 고가용성 지원은 없습니다.**
    
    **해결:** 예를 들어 1.4.1에서 1.4.2로 업그레이드한 경우를 예로 들 수 있습니다. 를 실행하여 결정될 수 있는 현재 스크립트 버전과 실행하여 결정될 수 있는 실행 중인 버전은 `Get-CcVersion`  `Get-CcRunningVersion` 모두 1.4.2입니다. 현재 실행 중인 버전을 다시 1.4.1로 전환하기 위해 실행하면 이 이전 버전에 대한 고가용성 `Switch-CcVersion` 지원이 없습니다.
    
    전체 고가용성 지원을 얻습니다. 다시 1.4.2로 전환하여 실행 중인 버전과 스크립트 버전이 동일합니다. 1.4.2 배포에 문제가 있는 경우 최대한 빨리 제거한 후 다시 설치하세요.
    
- **문제: 중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 인증 기관 인증서 또는 내부 인증서가 만료에 가까운 경우 또는 손상된 것입니다.**
    
    **해결:** 비즈니스용 Skype 인증 기관 인증서는 5년 동안 유효합니다. 중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 내부 인증서는 2년 동안 유효합니다.
    
    > [!NOTE]
    > 클라우드 커넥터 버전 2.0 이상에서는 Renew-CcServerCertificate cmdlet이 Update-CcServerCertificate 변경되어 Renew-CcCACertificate cmdlet이 Update-CcCACertificate로 변경되었습니다. 
  
    중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 내부 인증서가 만료되거나 손상된 경우 Renew-CcServerCertificate 또는 Update-CcServerCertificate cmdlet을 실행하여 인증서를 갱신합니다.
    
    인증 기관 인증서가 만료에 가까운 경우 인증서를 Renew-CcCACertificate 또는 Update-CcCACertificate cmdlet을 실행하여 인증서를 갱신합니다.
    
    **인증 기관 인증서가** 손상되어 사이트에 어플라이언스가 하나만 있는 경우 다음 단계를 수행합니다.
    
1. 서비스 Enter-CcUpdate 실행하여 서비스를 드레인하고 어플라이언스를 유지 관리 모드로 전환합니다.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. 다음 cmdlet을 실행하여 새 인증 기관 인증서와 모든 내부 서버 인증서를 다시 설정하고 만들 수 있습니다.
    
    클라우드 커넥터가 2.0 이전 릴리스인 경우:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    또는 클라우드 커넥터 릴리스 2.0 이상용:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. 게이트웨이와 중재 서버 간에 TLS를 사용하는 경우 어플라이언스에서 Export-CcRootCertificate cmdlet을 실행한 다음 내보낼 인증서를 PSTN 게이트웨이에 설치합니다. 게이트웨이에서 인증서를 다시 발급해야 할 수도 있습니다.

   ```powershell
   Export-CcRootCertificate
   ```

4. 서비스 Exit-CcUpdate 실행하여 서비스를 시작하고 유지 관리 모드를 종료합니다.

   ```powershell
   Exit-CcUpdate
   ```


    **인증 기관 인증서가** 손상되어 사이트에 여러 어플라이언스가 있는 경우 사이트의 각 어플라이언스에서 다음 단계를 수행합니다.
    
    사용량이 많은 시간 동안에는 이러한 단계를 수행하는 것이 좋습니다.
    
1. 첫 번째 어플라이언스에서 Remove-CcCertificationAuthorityFile cmdlet을 실행하여 디렉터리의 CA 백업 파일을 \<SiteRoot\> 정리합니다.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. 서비스 Enter-CcUpdate cmdlet을 실행하여 서비스를 드레인하고 각 어플라이언스를 유지 관리 모드로 전환합니다.

     ```powershell
     Enter-CcUpdate
     ```
    
3. 첫 번째 어플라이언스에서 다음 cmdlet을 실행하여 새 인증 기관 인증서와 모든 내부 서버 인증서를 다시 설정하고 만들 수 있습니다.
    
     클라우드 커넥터가 2.0 이전 릴리스인 경우:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     또는 클라우드 커넥터 릴리스 2.0 이상용:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. 첫 번째 어플라이언스에서 다음 cmdlet을 실행하여 CA 파일을 폴더에 \<SiteRoot\> 백업합니다.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. 동일한 사이트에 있는 다른 모든 어플라이언스에서 다음 명령을 실행하여 CA 백업 파일을 사용하게 하여 어플라이언스가 모두 동일한 루트 인증서를 사용할 수 있도록 한 다음 새 인증서를 요청합니다. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. 게이트웨이와 중재 서버 간에 TLS를 사용하는 경우 사이트의 모든 어플라이언스에서 Export-CcRootCertificate cmdlet을 실행한 다음 내보낼 인증서를 PSTN 게이트웨이에 설치합니다. 게이트웨이에서 인증서를 다시 발급해야 할 수도 있습니다.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. 서비스 Exit-CcUpdate 실행하여 서비스를 시작하고 유지 관리 모드를 종료합니다. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **문제: 클라우드 커넥터 관리 서비스 로그 "C:\Program Files\비즈니스용 Skype 클라우드 커넥터 버전\ManagementService\CceManagementService.log"에 다음 오류 메시지가 표시됩니다. CceService 오류: 0 : 온라인에 상태를 보고하는 경우 예기치 않은 예외: System.Management.Automation.CmdletInvocationException: 사용자에 대해 로그온에 \<Global Tenant Admin\> 실패했습니다. 올바른 사용자 이름과 암호를 사용 하도록 확인 하 여 새 자격 증명 개체를 만들면 합니다. ---\>**
    
    **해결:** 클라우드 Microsoft 365 Office 365 전역 테넌트 관리자 자격 증명 또는 전역 테넌트 관리자 자격 증명이 변경된 경우 클라우드 커넥터 어플라이언스에서 로컬에 저장된 자격 증명을 업데이트하기 위해 호스트 어플라이언스의 관리자 PowerShell에서 다음을 실행합니다.
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **문제: 배포에 사용한 호스트 서버 계정의 암호를 변경한 후 %ProgramFiles%\비즈니스용 Skype 클라우드 커넥터 버전\ManagementService\CceManagementService.log 또는 Get-CcCredential cmdlet을 실행하는 동안 "ConvertTo-SecureString : 키가 지정된 상태로 사용할 수 없습니다." 오류 메시지가 표시됩니다.**
    
    **해결:** 모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials 파일에 저장됩니다. \<CurrentUser\>.xml". 호스트 서버의 암호가 변경되는 경우 로컬에 저장된 자격 증명을 업데이트해야 합니다.
    
    **클라우드 커넥터 버전 1.4.2를** 실행하는 경우 다음 단계를 수행하여 모든 클라우드 커넥터 암호를 다시 생성합니다.
    
  1. 호스트 서버를 다시 시작합니다.
    
  2. 다음 파일을 삭제합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml".
    
  3. 관리자 권한으로 PowerShell 콘솔을 시작한 다음 "Register-CcAppliance -Local"을 실행하여 설명에 따라 암호를 다시 입력합니다. 클라우드 커넥터 배포 전에 입력한 암호를 입력합니다.
    
     **클라우드 커넥터 버전 2.0** 이상을 실행하는 경우 다음 단계를 수행하여 모든 클라우드 커넥터 암호를 다시 생성합니다.
    
  4. 호스트 서버를 다시 시작합니다.
    
  5. 다음 파일을 삭제합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml" .
    
  6. 관리자 권한으로 PowerShell 콘솔을 시작한 다음 "Register-CcAppliance -Local"을 실행하여 설명에 따라 암호를 다시 입력합니다. 
    
     캐시된 암호 파일이 클라우드 커넥터 버전 1.4.2를 사용하여 생성된 경우 메시지가 표시될 때 CceService 암호에 VMAdmin 암호를 사용하세요. 다른 모든 계정에 대해 클라우드 커넥터 배포에 대해 입력한 암호와 동일한 암호를 입력합니다.
    
     캐시된 암호 파일이 클라우드 커넥터 버전 1.4.2로 생성되어 DomainAdmin 및 VMAdmin 암호가 다른 경우 다음 단계를 수행해야 합니다.
    
  7. 다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.
    
  8. 이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.
    
  9. 새 계정 자격 증명을 입력하라는 메시지가 표시될 때 전에 사용한 DomainAdmin 암호의 암호를 입력합니다.
    
     캐시된 암호 파일이 클라우드 커넥터 버전 2.0 이상에서 생성된 경우 기본적으로 VmAdmin 및 DomainAdmin는 CceService와 동일한 암호를 사용하게 됩니다. DomainAdmin 및 VMAdmin 암호를 변경한 경우 다음 단계를 수행해야 합니다.
    
  10. 다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.
    
       1. 이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.
    
       2. 새 계정 자격 증명을 입력하라는 메시지가 표시될 때 전에 사용한 DomainAdmin 암호의 암호를 입력합니다.
    
  11. 다음과 Set-CcCredential -AccountType VmAdmin을 실행합니다.
    
       1. 이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.
    
       2. 새 계정 자격 증명을 입력하라는 메시지가 표시될 때 앞에서 사용한 VmAdmin 암호의 암호를 입력합니다. 
    
- **문제: 클라우드 커넥터 버전 2.1 이상에서 어플라이언스에서 Register-CcAppliance 또는 기타 cmdlet을 실행하면 "for Each-Object : The property 'Common'은 이 개체에서 찾을 수 없습니다. 속성이 있는지 확인 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **해결:** Cloud Connector 2.1 이상을 사용하려면 .NET Framework 4.6.1 이상이 필요합니다. 어플라이언스 .NET Framework 4.6.1 이상 버전으로 업데이트하고 cmdlet을 다시 실행하세요.

- **문제: Cloud Connector Edition 2.1에서 Install-CcAppliance를 실행하면 "오류로 새 인스턴스를 설치하지 못했습니다. 문자열만 XmlNode 속성을 설정하는 값으로 사용할 수 있기 때문에 "State"를 설정할 수 없습니다."와 같은 오류 메시지가 표시됩니다.**

   **해결:** 다음 Cloudconnector.ini [Common] 섹션에서 아래와 같은 "상태" 구성을 추가하세요. CountryCode=US State=WA City=Redmond

   "State" 줄에 반드시 값을 두는 것은 아니지만 "State" 줄은 파일에서 제거할 Cloudconnector.ini 없습니다.

- **문제: 다음 오류 메시지 "Dismount-WindowsImage : Dismount-WindowsImage 실패했습니다. Cloud Connector Edition을 0xc1550115 오류 코드 = "에디션"을 입력합니다.**
    
    **해결:** 관리자 권한으로 PowerShell 콘솔을 시작하고 "DISM -Cleanup-Wim'"을 실행합니다. 그러면 문제가 있는 모든 이미지가 정리됩니다. 다시 Install-CcAppliance 실행하거나 비트가 자동으로 업그레이드될 때까지 기다릴 수 있습니다.
    
- **문제: HA 환경에서 첫 번째 클라우드 커넥터 어플라이언스 배포 실패**
    
    **해결:** 배포에 실패한 이유에 따라 단계를 수행합니다.
    
  - 첫 번째 Cloud Connector 어플라이언스가 실패하고 실패 이유를 확인할 수 없는 경우 배포에 성공할 때까지 어플라이언스를 다시 설치한 다음 다른 어플라이언스를 설치해야 합니다.
    
  - 첫 번째 Cloud Connector 어플라이언스가 외부 인증서 문제와 같은 사소한 문제로 실패하면 어플라이언스를 다시 설치하지 않고도 문제를 해결할 수 있습니다. 그런 다음 테넌트 원격 PowerShell을 사용하여 배포를 다음과 같이 성공적으로 표시할 수 있습니다. 첫 번째 배포가 성공한 경우 다음 단계를 사용할 수도 있지만, 어떤 이유로 클라우드 커넥터가 배포를 성공으로 보고하지 못합니다.
    
  - 첫 번째 Cloud Connector 어플라이언스의 ID(GUID)를 얻습니다. Get-CsHybridPSTNAppliance 실행합니다.
    
  - 어플라이언스를 성공적으로 배포된 것으로 표시하기 위해 다음과 Set-CsCceApplianceDeploymentStatus 실행합니다.
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **문제: 호스트 서버 또는 가상 Windows 수동으로 업데이트 업데이트를 확인하고 설치해야 합니다.**
    
   **해결:** 사용자들이 제공하는 자동화된 OS 업데이트를 활용하는 비즈니스용 Skype 클라우드 커넥터 버전. 어플라이언스를 온라인 관리에 등록하고 자동 OS 업데이트를 사용하도록 설정하면 호스트 서버와 가상 컴퓨터는 OS 업데이트 시간 창 설정에 따라 Windows 업데이트를 자동으로 확인하고 설치합니다.
    
   Windows 업데이트를 확인하고 설치해야 하는 경우 이 섹션의 단계를 수행하여 배포 유형에 적용됩니다. 업데이트에 필요한 종료 시간을 최소화하기 위해 호스트 서버와 호스트 서버에서 실행되는 가상 컴퓨터를 동시에 업데이트할 계획을 세우는 것이 좋습니다.
    
   원하는 경우 WSUS(Windows Server Update Services) 서버를 사용하여 클라우드 커넥터 서버에 대한 업데이트를 제공할 수 있습니다. 업데이트가 자동으로 설치되지 Windows **구성해야** 합니다.
    
   클라우드 커넥터 배포를 수동으로 업데이트하는 방법에 대한 자세한 내용은 다음 섹션을 참조하세요.
    
- **문제: 클라우드 커넥터가 새 빌드로 업데이트될 때 클라우드 커넥터 cmdlet이 업데이트되지 않습니다.** 자동 업데이트가 발생할 때 PowerShell 창이 열린 경우에 이 문제가 발생할 수 있습니다.
    
  **해결:** 업데이트된 cmdlet을 로드하기 위해 다음 단계 중 하나를 수행하면 됩니다.
    
   - 클라우드 커넥터 어플라이언스에서 PowerShell을 닫은 다음 PowerShell을 다시 열 수 있습니다.
    
     - 또는 CloudConnector -force를 Import-Module 실행할 수 있습니다. 
 
-   **문제: cmdlet을 실행하려고 할 때 "'Stop-CsWindowsService'라는 용어가 cmdlet, 함수, 스크립트 파일 또는 작동할 수 있는 프로그램의 이름으로 인식되지 않습니다." 오류가 Enter-CcUpdate 있습니다.**

    **해결:** $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 파일을 삭제합니다.
PowerShell에서는 모듈에서 찾은 cmdlet의 캐시로 이 파일을 만들어 매월 모든 모듈을 다시 분석하지는 않습니다. 이렇게 하면 속도가 매우 느려질 수 있습니다. 대부분의 경우 해당 캐시에서 다시 읽을 때 PowerShell에 잘못된 결과를 제공하는 일부 파일 손상이 있을 수 있습니다.

-   **문제: "Import-Module CloudConnector"가 "Import-Module: 모듈 디렉터리에서 유효한 모듈 파일을 찾을 수 없는 경우 지정된 모듈 "CloudConnector"가 로드되지 않았습니다." 오류가 발생합니다.**

    **해결 방법:**
    - c:\Program Files\WindowsPowerShell\Modules 아래에 CloudConnector 모듈이 존재하는지 확인
    
    - CloudConnector 모듈이 이 위치에 존재하는지 확인한 후 모듈 위치에 대한 경로를 저장하는 PSModulePath 환경 변수를 변경할 수 있습니다.
    
     a. 임시 변경: 관리자 권한으로 Powershell을 시작하고 $env:PSModulePath = $env:PSModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. 영구 변경의 경우 관리자 권한으로 PowerShell을 시작하고 다음 명령을 하나씩 실행합니다. $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>수동으로 Windows 업데이트 설치

환경에서 자동 업데이트를 사용하지 않을 경우 다음 단계에 따라 수동으로 업데이트 업데이트를 Windows 합니다. 업데이트를 확인하고 설치하려면 Windows 다시 시작해야 할 수 있습니다. 호스트 서버가 다시 시작되는 경우 사용자는 클라우드 커넥터를 사용하여 전화를 걸거나 받을 수 없습니다. 업데이트를 수동으로 확인하고 설치하여 업데이트가 수행될 때를 제어한 다음 서비스 중단을 방지하기 위해 선택한 시간 동안 필요한 경우 컴퓨터를 다시 시작할 수 있습니다.
  
업데이트를 수동으로 확인하려면 각 호스트 서버에 연결하고 **제어판 을 니다.** 시스템 **및 보안 Windows \> 를** 선택한 다음 환경에 따라 업데이트 및 서버 다시 시작을 관리합니다.
  
- 사이트에 어플라이언스가 하나뿐인 경우 각 가상 컴퓨터에 연결하고 **제어판을 니다.** 시스템 **및 보안 Windows \> 를** 선택한 다음 업데이트 및 서버 다시 시작을 적절하게 구성합니다.
    
- 사이트에 어플라이언스가 두 개 이상 있는 경우 업데이트 및 다시 시작되는 인스턴스는 업데이트하는 동안 사용자가 액세스할 수 없습니다. 사용자는 모든 가상 컴퓨터 및 모든 비즈니스용 Skype 업데이트가 완료된 후 가상 컴퓨터에 시작될 때까지 배포의 다른 인스턴스에 연결합니다. 서비스가 중단되지 않도록 업데이트를 적용하는 동안 HA에서 인스턴스를 제거한 다음 완료되면 복원하면 됩니다. 방법은 다음과 같습니다.
    
1. 각 호스트 서버에서 관리자 권한으로 PowerShell 콘솔을 여는 경우
    
2. 다음 cmdlet을 사용하여 HA에서 인스턴스를 제거합니다.
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    단일 인스턴스에 대한 단계에 따라 업데이트를 수동으로 적용하고 가상 컴퓨터를 다시 시작합니다.
    
4. 다음 cmdlet을 통해 인스턴스를 다시 HA로 설정하십시오.
    
   ```powershell
   Exit-CcUpdate
   ```

다중 사이트 배포의 경우 배포의 각 사이트에 대해 한 단계씩 수행하여 한 사이트에 업데이트를 적용합니다.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>팁 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치할 때 사용할 수 있는 방법

클라우드 커넥터 호스트 컴퓨터에 바이러스 백신 소프트웨어를 설치해야 하는 경우 다음 제외를 추가해야 합니다.
  
- 각 컴퓨터의 Local Appliance 디렉터리
    
- 각 컴퓨터의 원격 사이트 디렉터리입니다.
    
- 컴퓨터의 로컬 사이트 디렉터리는 공유 사이트 루트 폴더를 호스트합니다.
    
- %ProgramFiles%\비즈니스용 Skype 클라우드 커넥터 버전
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- 프로세스가 Microsoft.Rtc.CCE.ManagementService.exe.