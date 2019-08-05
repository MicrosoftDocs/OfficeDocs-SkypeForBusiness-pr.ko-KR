---
title: 비즈니스용 Skype 서버에 대 한 통계 관리자 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '요약: 비즈니스용 Skype 서버용 통계 관리자를 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: b16334558fb64223e305effe533addca91683a81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191208"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 통계 관리자 배포
 
**요약:** 비즈니스용 Skype 서버용 통계 관리자를 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
 비즈니스용 Skype Server의 통계 관리자는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구입니다. 여러 서버에서 성능 데이터를 몇 초 마다 폴링하거나 통계 관리자 웹 사이트에서 즉시 결과를 볼 수 있습니다.
  
통계 관리자를 설치 하려고 하기 전에 소프트웨어, 네트워킹 및 하드웨어 요구 사항에 대해 잘 알고 있어야 합니다. 자세한 내용은 [비즈니스용 Skype 서버에 대 한 통계 관리자 계획](plan.md)을 참조 하세요.
  
> [!NOTE]
> 이전 버전의 통계 관리자에서 업그레이드 하는 경우 [비즈니스용 Skype 서버용 업데이트 통계 관리자](upgrade.md)를 참조 하세요. 
  
> [!NOTE]
> 통계 관리자 웹 사이트는 Internet Explorer 11 이상, Edge 20.10240 +, Chrome 46 + (현재 11 번째 버전)에서 테스트 되어 올바르게 작동 합니다. 
  
에서 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload)다운로드 가능한 통계 관리자를 찾을 수 있습니다. 
  
이 항목에서는 다음 섹션을 다룹니다.
  
- [통계 관리자 배포](deploy.md#BKMK_Deploy)
    
- [배포 문제 해결](deploy.md#BKMK_Troubleshoot)
    
- [자체 서명 된 인증서 만들기](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>통계 관리자 배포
<a name="BKMK_Deploy"> </a>

통계 관리자를 배포 하려면 다음 단계를 따릅니다.
  
1. Redis 메모리 내 캐싱 시스템을 설치 하 고 적절 한 인증서가 설치 되었는지 확인 하 여 수신기 호스트 컴퓨터를 준비 합니다.
    
2. 호스트 컴퓨터에 수신기 서비스를 설치 합니다. 
    
3. 호스트 컴퓨터에 웹 사이트를 설치 합니다.
    
4. 모니터링할 각 비즈니스용 Skype 서버 컴퓨터에 에이전트를 설치 합니다.
    
5. 모니터링 하는 서버에 대 한 토폴로지를 가져옵니다.
    
> [!NOTE]
> Redis, 수신기 서비스 및 웹 사이트가 모두 동일한 호스트 컴퓨터에 설치 되어 있어야 합니다. 호스트 컴퓨터에 비즈니스용 Skype 서버가 설치 되어 있지 않은지 확인 합니다. 
  
### <a name="prepare-the-listener-host-machine"></a>수신기 호스트 컴퓨터 준비

호스트 컴퓨터를 준비 하려면 Redis 메모리 내 캐싱 시스템을 설치 하 고 올바른 인증서가 컴퓨터에 있는지 확인 해야 합니다. Microsoft는 Redis 3.0의 최신 안정적인 빌드를 설치 하는 것이 좋습니다. 통계 관리자 버전 2.0 Redis 3.2.100에서 테스트를 거쳤습니다. 
  
1. 다음 사이트에서 Redis을 다운로드 합니다 [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    서명 되지 않은 설치 관리자는 다음에서 다운로드할 수 있습니다.[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    필요한 경우 인기 있는 패키지 관리자: [Nuget](https://www.nuget.org/packages/Redis-64/) 및 [Choclatey](https://chocolatey.org/packages/redis-64)에서 서명 된 이진 파일을 사용할 수 있습니다.
    
   - 제공 된 msi를 실행 하 고 화면의 지시를 따릅니다.
    
   - 방화벽 규칙 추가 확인란을 선택 하지 마세요.
    
2. 수신기 서비스에는 인증서가 필요 합니다. Microsoft는 신뢰할 수 있는 인증 기관에서 서명한 인증서를 사용 하는 것이 좋습니다. 
    
    랩에서 테스트 목적으로 자체 서명 된 인증서를 사용 하려는 경우 (예: [자체 서명 된 인증서 만들기](deploy.md#BKMK_SelfCert))를 참조 하세요.
    
    에이전트는 체인 확인 대신 인증서 지문 확인을 사용 합니다. 자체 서명 된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 수행 하지 않습니다.
    
### <a name="install-the-listener-service"></a>수신기 서비스 설치

Stats마나트 Cpagentlistener를 실행 하 고 다음을 지정 하 여 호스트 컴퓨터에 수신기 서비스를 설치 합니다.
  
1. 사용권 계약을 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **다음**을 클릭 합니다. 
    
2. 다음 페이지에서 다음 정보를 지정 합니다.
    
   - **서비스 비밀 번호:** 원격 에이전트가 수신기 서비스에 인증 하는 데 사용할 암호입니다.
    
   - **서비스 포트:** 이는 수신기가 에이전트와 통신 하는 데 사용할 HTTPS 포트 번호입니다. 설치 중에이 포트는 로컬 방화벽을 통해 허용 되 고, URL ACL이 만들어지고, SSL 인증서가이 포트에 바인딩됩니다. 기본값은 8443입니다.
    
   - **인증서 지문:** 이는 수신기가 HTTPS 프로토콜을 암호화 하는 데 사용할 인증서 지문입니다. 네트워크 서비스에는 개인 키에 대 한 읽기 권한이 있어야 합니다.
    
     **선택 ...** 단추를 클릭 하 여 지문을 선택 합니다.
    
     인증서 관리자를 사용 하거나 다음 PowerShell 명령을 사용 하 여 인증서 지문을 찾을 수 있습니다.
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **설치 디렉터리:** 바이너리가 설치 될 디렉터리입니다. **찾아보기를** 클릭 하 여 기본값을 변경할 수 있습니다.
    
   - **AppData Dir:** 로그 폴더와 다른 데이터가 저장 되는 디렉터리입니다. 기본값에서 변경할 수 있습니다. 제거 시에 삭제 되지 않습니다.
    
3. **설치**를 클릭 합니다.
    
설치의 유효성을 검사 하려면 다음 단계를 수행 합니다.
  
1. 브라우저를 열고 다음으로 이동 합니다.https://localhost:\<service-port\>/healthcheck/
    
    기본적으로 서비스 포트는 8443입니다 (다른 포트를 지정 하지 않는 경우).
    
2. 수신기가 제대로 설치 되었는지 확인 하려면 다음을 확인 합니다.
    
   - Healthcheck 페이지가 표시 되 면 수신기가 성공적으로 설치 된 것입니다.
    
   - KnownServerCount가 1 이상인 경우 Redis에 대 한 연결이 설정 됩니다.
    
   - 몇 분 정도 기다렸다가 하나 이상의 에이전트가 설치 된 후에는 Value쓰여진 카운터가 증가 하 고 있는지 확인 합니다.
    
### <a name="install-the-website"></a>웹 사이트 설치

[비즈니스용 Skype Server, 실시간 통계 관리자 (64 비트)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) 및 다음을 지정 하 여 Stats마나트 웹 사이트 (msi)를 실행 하 여 호스트 컴퓨터에 웹 사이트를 설치 합니다.
  
1. 사용권 계약을 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **다음**을 클릭 합니다. 
    
2. 다음 페이지에서 다음 정보를 지정 합니다.
    
   - **서비스 포트:** 웹 사이트가 수신 대기 하는 포트 번호입니다. 나중에 IIS 관리자 바인딩을 사용 하 여 변경할 수 있습니다. 설치 중에이 포트는 로컬 방화벽을 통해 허용 됩니다.
    
   - **설치 디렉터리:** 바이너리가 설치 되는 디렉터리입니다. **찾아보기를** 클릭 하 여 기본값을 변경할 수 있습니다.
    
   - **AppData Dir:** 로그 폴더와 다른 데이터가 저장 되는 디렉터리입니다. 기본값에서 변경할 수 있습니다. 제거 시에 삭제 되지 않습니다.
    
3. **설치**를 클릭 합니다.
    
웹 사이트를 보려면 브라우저를 열고 http://localhost,, webport\>/.를 탐색 합니다.
  
상태 정보만 보려면 브라우저를 열고 다음 http://localhost:\<webport\>/healthcheck/으로 이동 합니다.
  
기본적으로 웹 포트 번호는 8080입니다. IIS 관리자를 사용 하 여 웹 사이트의 포트 바인딩을 변경할 수 있습니다.
  
웹 설치 관리자가 StatsManWebSiteUsers 이라는 로컬 보안 그룹을 추가 합니다. 이 보안 그룹에 계정을 추가 하 여 웹 사이트에 대 한 액세스 권한을 부여할 수 있습니다. 
  
### <a name="install-the-agents"></a>에이전트 설치

Stats Perfagent를 실행 하 고 다음을 지정 하 여 모니터링할 각 비즈니스용 Skype 서버에 에이전트를 설치 합니다.
  
1. 사용권 계약을 검토 하 고 동의할 경우 **사용권 계약에 동의 함을**선택 하 고 **다음**을 클릭 합니다. 
    
2. 다음 페이지에서 다음 정보를 지정 합니다.
    
   - **서비스 비밀 번호:** 원격 에이전트가 수신기 서비스에 인증 하는 데 사용할 암호입니다.
    
   - **서비스 URI:** 수신기가 상주 하는 URI입니다. https://name:port 형식을 사용 해야 합니다.
    
     NETBIOS 이름 또는 FQDN을 사용할 수 있습니다. 수신기 서비스에서 인증서의 주체 또는 **주체의 대체 이름** 으로 **** 도 지정 된 이름을 사용할 수 있지만, 반드시 그럴 필요는 없습니다.
    
   - **서비스 지문:** 수신기가 사용 하는 SSL 인증서의 지문입니다. 에이전트는이 지문을 사용 하 여 수신기를 인증 합니다. (자체 서명 된 인증서를 사용할 수 있기 때문에 전체 인증서 유효성 검사를 수행 하지 않습니다.)
    
   - **설치 디렉터리:** 바이너리가 설치 될 디렉터리입니다. **찾아보기를** 클릭 하 여 기본값을 변경할 수 있습니다.
    
   - **AppData Dir:** 로그 폴더와 암호화 된 암호 .txt 파일이 저장 되는 디렉터리입니다. 기본값에서 변경할 수 있습니다. 제거 시에 삭제 되지 않습니다.
    
3. **설치**를 클릭 합니다.
    
여러 컴퓨터에 에이전트를 설치 하는 경우 무인 모드에서이 작업을 수행 하는 것이 좋습니다. 예를 들면 다음과 같습니다. 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>토폴로지 가져오기
<a name="BKMK_ImportTopology"> </a>

통계 관리자를 설치 하 고 실행 한 후에는 통계 관리자가 각 서버의 사이트, 풀 및 역할을 인식할 수 있도록 비즈니스용 Skype 서버 토폴로지를 가져와야 합니다. 비즈니스용 Skype 서버 토폴로지를 가져오려면 [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet을 사용 하 여 조직에서 사용 중인 각 풀에 대 한 정보를 검색 한 다음이 정보를 통계 관리자로 가져옵니다.
  
비즈니스용 Skype 서버 토폴로지를 가져오려면 다음 단계를 따르세요.
  
1. 비즈니스용 Skype Server PowerShell cmdlet이 있는 호스트에서 다음을 수행 합니다.
    
    에서. 다음 명령을 실행 합니다. 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. "Mypoolinfo" 파일을 수신기를 실행 하는 서버에 복사 합니다.
    
2. 수신기를 실행 하는 호스트에서 다음을 수행 합니다.
    
   에서. PowerShell을 실행 합니다.
    
   b. 수신기가 설치 된 디렉터리로 이동 합니다. 기본값은 다음과 같습니다. 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 추가 되 고 업데이트 되는 서버를 확인 하려면 다음 명령을 실행 합니다.
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

다음 명령을 사용 하 여 모든 옵션을 볼 수 있습니다.
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

현재 가져온 서버 정보를 보려면 다음 스크립트를 실행 합니다. 
  
```
.\Get-StatsManServerInfo.ps1
```

비즈니스용 Skype 서버 토폴로지에 없는 서버 (예: Exchange 서버)를 모니터링 하려는 경우 수신기를 실행 하는 호스트에서 단일 서버 가져오기를 수행할 수 있습니다. 단일 서버 가져오기를 수행 하려면 다음 단계를 따릅니다.
  
1. 수신기가 설치 된 디렉터리로 이동 합니다. 기본값은 다음과 같습니다. 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 다음 명령을 실행 합니다.
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>배포 문제 해결
<a name="BKMK_Troubleshoot"> </a>

에이전트가 시작 되지 않으면 다음을 확인 합니다. 
  
- 에이전트가 통계 관리자에 등록 되어 있습니까?
    
1. 토폴로지 가져오기에 대 한 지침을 따랐는지 확인 합니다. [토폴로지 가져오기를](deploy.md#BKMK_ImportTopology)참조 하세요.
    
2. 에이전트가 토폴로지에 나열 되지 않은 서버 (예: SQL AlwaysOn 클러스터의 노드)에 있는 경우 [토폴로지 가져오기](deploy.md#BKMK_ImportTopology)의 지침에 따라 에이전트를 수동으로 추가 해야 합니다.
    
- 에이전트가 수신기에 연결할 수 있습니까?
    
1. 수신기 서비스가 실행 중인지 확인 합니다. 
    
    실행 중이지 않은 경우 Redis가 실행 중인지 확인 한 다음 수신기를 다시 시작 해 봅니다.
    
2. 포트가 수신기 서비스에 열려 있고 에이전트 컴퓨터가 포트와 통신할 수 있는지 확인 합니다.
    
- 통계 관리자가 데이터를 수집 하 고 있는지 확인 하려면 다음과 같이 CSV 파일을 확인 하면 됩니다. 
    
    다음 명령은 카운터 저장소 이름을 검색 합니다. 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    다음 명령은 지정 된 카운터의 값을 검색 합니다. 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

응용 프로그램 이벤트 로그에 표시 될 수 있는 모든 이벤트에 대 한 자세한 내용은 비즈니스용 [Skype 서버에 대 한 통계 관리자 문제 해결](troubleshoot.md)을 참조 하세요.
  
## <a name="create-a-self-signed-certificate"></a>자체 서명 된 인증서 만들기
<a name="BKMK_SelfCert"> </a>

Microsoft는 신뢰할 수 있는 인증 기관에서 서명한 인증서를 사용 하는 것이 좋습니다. 그러나 테스트 목적으로 자체 서명 된 인증서를 사용 하려는 경우에는 다음을 수행 합니다. 
  
1. 관리자로 로그온 한 상태에서 PowerShell 콘솔에서 다음을 입력 합니다.
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 형식을 `certlm.msc`입력 합니다. 로컬 컴퓨터의 인증서 관리자가 열립니다.
    
3. **개인**으로 이동한 다음 **인증서**를 엽니다.
    
4. **Stats마나트 수신기\>-모든 작업-\>개인 키 관리 ...** 를 마우스 오른쪽 단추로 클릭 합니다.
    
5. **추가**를 클릭 합니다.
    
6. **선택할 개체 이름 입력** 상자에 다음을 입력 합니다. 네트워크 서비스
    
7. **확인**을 클릭합니다.
    
8. **모든 권한**에서 **허용** 확인란의 선택을 취소 합니다. (읽기 액세스만 필요 합니다.)
    
9. **확인**을 클릭합니다.
    
## <a name="for-more-information"></a>자세한 내용은
<a name="BKMK_SelfCert"> </a>

자세한 내용은 다음을 참조 하세요.
  
- [비즈니스용 Skype 서버에 대 한 통계 관리자 계획](plan.md)
    
- [비즈니스용 Skype 서버에 대 한 업그레이드 통계 관리자](upgrade.md)
    
- [비즈니스용 Skype Server ß의 통계 관리자 문제 해결](troubleshoot.md)
