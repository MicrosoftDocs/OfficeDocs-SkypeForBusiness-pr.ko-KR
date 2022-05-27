---
title: 비즈니스용 Skype 서버 통계 관리자 배포
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: '요약: 비즈니스용 Skype 서버 대한 Statistics Manager를 배포하는 방법을 알아보려면 이 항목을 읽어보세요.'
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675990"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>비즈니스용 Skype 서버 통계 관리자 배포

**요약:** 비즈니스용 Skype 서버 대한 Statistics Manager를 배포하는 방법을 알아보려면 이 항목을 참조하세요.

 비즈니스용 Skype 서버 대한 통계 관리자는 비즈니스용 Skype 서버 상태 및 성능 데이터를 실시간으로 볼 수 있는 강력한 도구입니다. 몇 초마다 수백 대의 서버에서 성능 데이터를 폴링하고 통계 관리자 웹 사이트에서 결과를 즉시 볼 수 있습니다.

Statistics Manager를 설치하기 전에 소프트웨어, 네트워킹 및 하드웨어 요구 사항에 대해 잘 알고 있어야 합니다. 자세한 내용은 [비즈니스용 Skype 서버 대한 통계 관리자 계획을](plan.md) 참조하세요.

> [!NOTE]
> 이전 버전의 Statistics Manager에서 업그레이드하는 경우 [비즈니스용 Skype 서버 대한 업그레이드 통계 관리자를](upgrade.md) 참조하세요.

> [!NOTE]
> Statistics Manager 웹 사이트가 테스트되었으며 Internet Explorer 11 이상, Edge 20.10240 이상 및 Chrome 46 이상(현재 상록 버전)에서 올바르게 작동합니다.

에서 Statistics Manager를 다운로드할 수 있습니다 [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).

이 항목에는 다음 섹션이 포함되어 있습니다.

- [통계 관리자 배포](deploy.md#BKMK_Deploy)

- [배포 문제 해결](deploy.md#BKMK_Troubleshoot)

- [자체 서명된 인증서 만들기](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>통계 관리자 배포
<a name="BKMK_Deploy"> </a>

Statistics Manager를 배포하려면 다음 단계를 수행합니다.

1. Redis 메모리 내 캐싱 시스템을 설치하고 적절한 인증서를 설치했는지 확인하여 수신기 호스트 컴퓨터를 준비합니다.

2. 호스트 컴퓨터에 수신기 서비스를 설치합니다.

3. 호스트 컴퓨터에 웹 사이트를 설치합니다.

4. 모니터링하려는 각 비즈니스용 Skype 서버 컴퓨터에 에이전트를 설치합니다.

5. 모니터링하는 서버에 대한 토폴로지 가져오기

> [!NOTE]
> Redis, 수신기 서비스 및 웹 사이트는 모두 동일한 호스트 컴퓨터에 설치되어야 합니다. 호스트 컴퓨터에 비즈니스용 Skype 서버 설치되어 있지 않은지 확인합니다.

### <a name="prepare-the-listener-host-machine"></a>수신기 호스트 컴퓨터 준비

호스트 컴퓨터를 준비하려면 Redis 메모리 내 캐싱 시스템을 설치하고 유효한 인증서가 컴퓨터에 있는지 확인해야 합니다. 안정적인 최신 Redis 3.0 빌드를 설치하는 것이 좋습니다. Statistics Manager 버전 2.0은 Redis 3.2.100으로 테스트되었습니다.

1. 다음 사이트에서 [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis)Redis를 다운로드합니다.

    서명되지 않은 설치 관리자는 에서 다운로드할 수 있습니다. [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    서명된 이진 파일은 인기 있는 패키지 관리자 [인 Nuget](https://www.nuget.org/packages/Redis-64/) 및 [Choclatey](https://chocolatey.org/packages/redis-64)를 통해 사용할 수 있습니다.

   - 제공된 msi를 실행하고 프롬프트를 따릅니다.

   - 방화벽 규칙을 추가하려면 확인란을 선택하지 마세요.

2. 수신기 서비스에는 인증서가 필요합니다. 신뢰할 수 있는 인증 기관에서 서명한 인증서가 있는 것이 좋습니다.

    랩에서 테스트 목적으로 자체 서명된 인증서를 사용하려는 경우(예: [자체 서명된 인증서 만들기](deploy.md#BKMK_SelfCert))를 참조하세요.

    에이전트는 체인 확인 대신 인증서 지문 확인을 사용합니다. 자체 서명된 인증서를 사용할 수 있으므로 전체 인증서 유효성 검사를 수행하지 않습니다.

### <a name="install-the-listener-service"></a>수신기 서비스 설치

StatsManPerfAgentListener.msi 실행하고 다음을 지정하여 호스트 컴퓨터에 수신기 서비스를 설치합니다.

1. 사용권 계약을 검토하고 동의한 경우 **사용권 계약에 동의** 한 다음 **다음** 을 클릭합니다.

2. 다음 페이지에서 다음 정보를 지정합니다.

   - **서비스 암호:** 이 암호는 원격 에이전트에서 수신기 서비스에 인증하는 데 사용됩니다.

   - **서비스 포트:** 이 HTTPS 포트 번호는 수신기에서 에이전트와 통신하는 데 사용됩니다. 설치하는 동안 이 포트는 로컬 방화벽을 통해 허용되고, URL ACL이 생성되고, SSL 인증서가 이 포트에 바인딩됩니다. 기본값은 8443입니다.

   - **인증서 지문:** 이 인증서는 수신기에서 HTTPS 프로토콜을 암호화하는 데 사용됩니다. 네트워크 서비스에는 프라이빗 키에 대한 읽기 권한이 있어야 합니다.

     **[선택]** 단추를 클릭하여 지문을 선택합니다.

     인증서 관리자를 사용하거나 다음 PowerShell 명령을 사용하여 인증서 지문을 찾을 수 있습니다.

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **Dir 설치:** 이 디렉터리가 설치되는 위치입니다. **찾아보기...** 단추를 사용하여 기본값에서 변경할 수 있습니다.

   - **AppData Dir:** 이 디렉터리에서는 Logs 폴더 및 기타 데이터가 저장됩니다. 기본값에서 변경할 수 있습니다. 제거하면 삭제되지 않습니다.

3. **설치** 를 클릭합니다.

설치의 유효성을 검사하려면 다음 단계를 수행합니다.

1. 브라우저를 열고 `https://localhost:<service-port>/healthcheck/`(으)로 이동합니다.

    기본적으로 서비스 포트는 8443입니다(다른 포트를 지정하지 않은 경우).

2. 수신기가 제대로 설치되었는지 확인하려면 다음을 찾습니다.

   - 상태 검사 페이지가 표시되면 수신기 설치에 성공했습니다.

   - KnownServerCount가 1 이상인 경우 Redis에 대한 연결이 설정됩니다.

   - 몇 분 정도 기다린 후 에이전트가 하나 이상 설치되면 ValuesWritten 카운터가 증가되는지 확인합니다.

### <a name="install-the-website"></a>웹 사이트 설치

StatsManWebSite.msi 실행하여 호스트 컴퓨터에 웹 사이트를 설치합니다([비즈니스용 Skype 서버, Real-Time Statistics Manager(64비트)에 포함됨)](https://www.microsoft.com/download/details.aspx?id=57518).

1. 사용권 계약을 검토하고 동의한 경우 **사용권 계약에 동의** 한 다음 **다음** 을 클릭합니다.

2. 다음 페이지에서 다음 정보를 지정합니다.

   - **서비스 포트:** 이 TCP 포트는 웹 사이트에서 수신 대기하는 위치입니다. 나중에 IIS 관리자 바인딩을 사용하여 변경할 수 있습니다. 설치하는 동안 이 포트는 로컬 방화벽을 통해 허용됩니다.

   - **Dir 설치:** 이 디렉터리가 설치되는 위치입니다. **찾아보기...** 단추를 사용하여 기본값에서 변경할 수 있습니다.

   - **AppData Dir:** 이 디렉터리에서는 Logs 폴더 및 기타 데이터가 저장됩니다. 기본값에서 변경할 수 있습니다. 제거하면 삭제되지 않습니다.

3. **설치** 를 클릭합니다.

웹 사이트를 보려면 브라우저를 열고 다음 `http://<localhost:webport/>`으로 이동합니다.

상태 정보만 보려면 브라우저를 열고 다음 `http://localhost:<webport>/healthcheck/`으로 이동합니다.

기본적으로 웹 포트 번호는 8080입니다. IIS 관리자를 사용하여 웹 사이트의 포트 바인딩을 변경할 수 있습니다.

웹 설치 관리자는 StatsManWebSiteUsers라는 로컬 보안 그룹을 추가합니다. 이 보안 그룹에 계정을 추가하여 웹 사이트에 대한 액세스 권한을 부여할 수 있습니다.

### <a name="install-the-agents"></a>에이전트 설치

StatsManPerfAgent.msi 실행하여 모니터링하려는 각 비즈니스용 Skype 서버 에이전트를 설치합니다.

1. 사용권 계약을 검토하고 동의한 경우 **사용권 계약에 동의** 한 다음 **다음** 을 클릭합니다.

2. 다음 페이지에서 다음 정보를 지정합니다.

   - **서비스 암호:** 이 암호는 원격 에이전트에서 수신기 서비스에 인증하는 데 사용됩니다.

   - **서비스 URI:** 이 URL은 수신기가 있는 위치입니다. 형식을 `https://name:port` 사용합니다.

     NETBIOS 이름 또는 FQDN을 사용할 수 있습니다. 수신기 서비스에서 인증서의 **주체** 또는 **주체 대체 이름으로** 도 지정된 이름을 사용할 수 있지만 이는 요구 사항이 아닙니다.

   - **서비스 지문:** 이 SS: 인증서는 수신기에서 사용됩니다. 에이전트는 이 지문을 사용하여 수신기에 인증합니다. 자체 서명된 인증서를 사용할 수 있으므로 전체 인증서 유효성 검사를 수행하지 않습니다.

   - **Dir 설치:** 이 디렉터리가 설치되는 위치입니다. **찾아보기...** 단추를 사용하여 기본값에서 변경할 수 있습니다.

   - **AppData Dir:** 이 디렉터리에서는 Logs 폴더와 암호화된 password.txt 파일이 저장됩니다. 기본값에서 변경해 주실 수 있습니다. 제거하면 삭제되지 않습니다.

3. **설치** 를 클릭합니다.

수많은 컴퓨터에 에이전트를 설치하는 경우 무인 모드에서 이 작업을 수행할 수 있습니다. 예:

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>토폴로지 가져오기
<a name="BKMK_ImportTopology"> </a>

Statistics Manager를 설치하고 실행한 후 통계 관리자가 각 서버의 사이트, 풀 및 역할을 알 수 있도록 비즈니스용 Skype 서버 토폴로지를 가져와야 합니다. 비즈니스용 Skype 서버 토폴로지 가져오기 위해 [Get-CsPool](/powershell/module/skype/get-cspool) cmdlet을 사용하여 조직에서 사용 중인 각 풀에 대한 정보를 검색한 다음 이 정보를 Statistics Manager로 가져옵니다.

비즈니스용 Skype 서버 토폴로지 가져오기를 수행하려면 다음 단계를 수행합니다.

1. 비즈니스용 Skype 서버 PowerShell cmdlet이 있는 호스트에서 다음을 수행합니다.

    a. 다음 명령을 실행합니다.

   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```

    b. 수신기를 실행하는 서버에 "mypoolinfo.xml" 파일을 복사합니다.

2. 수신기를 실행하는 호스트에서:

   a. PowerShell을 실행합니다.

   b. 수신기가 설치된 디렉터리로 이동합니다. 기본값은 다음과 같습니다.

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. 추가 및 업데이트되는 서버를 확인하려면 다음 명령을 실행합니다.

   ```console
   .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

다음 명령을 사용하면 모든 옵션을 볼 수 있습니다.

```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed
```

현재 가져온 서버 정보를 보려면 다음 스크립트를 실행합니다.

```powershell
.\Get-StatsManServerInfo.ps1
```

비즈니스용 Skype 서버 토폴로지(예: Exchange Server)에 없는 서버를 모니터링하려는 경우 수신기를 실행하는 호스트에서 단일 서버 가져오기를 수행할 수 있습니다. 단일 서버 가져오기를 수행하려면 다음 단계를 수행합니다.

1. 수신기가 설치된 디렉터리로 이동합니다. 기본값은 다음과 같습니다.

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. 다음 명령을 실행합니다.

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>배포 문제 해결
<a name="BKMK_Troubleshoot"> </a>

에이전트를 시작하지 못하는 경우 다음 문제를 확인합니다.

- 에이전트가 Statistics Manager에 등록되어 있나요?

   1. 토폴로지 가져오기에 대한 지침을 따랐는지 확인합니다. [토폴로지 가져오기를 참조하세요](deploy.md#BKMK_ImportTopology).

   2. 에이전트가 토폴로지(예: SQL AlwaysOn 클러스터의 노드)에 나열되지 않은 서버에 있는 경우 [토폴](deploy.md#BKMK_ImportTopology)로지 가져오기의 지침에 따라 에이전트를 수동으로 추가해야 합니다.

- 에이전트가 수신기에 연결할 수 있나요?

   1. 수신기 서비스가 실행 중인지 확인합니다.

      실행되고 있지 않으면 Redis가 실행 중인지 확인한 다음 수신기를 다시 시작합니다.

   2. 포트가 수신기 서비스에 열려 있고 에이전트 컴퓨터가 포트와 통신할 수 있는지 확인합니다.

- Statistics Manager가 데이터를 수집하고 있는지 확인하려면 다음과 같이 CSV 파일을 확인할 수 있습니다.

    다음 명령은 카운터 스토리지 이름을 검색합니다.

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    다음 명령은 지정된 카운터의 값을 검색합니다.

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

애플리케이션 이벤트 로그에 표시할 수 있는 모든 이벤트에 대한 자세한 내용은 [비즈니스용 Skype 서버 대한 통계 관리자 문제 해결을](troubleshoot.md) 참조하세요.

## <a name="create-a-self-signed-certificate"></a>자체 서명된 인증서 만들기
<a name="BKMK_SelfCert"> </a>

신뢰할 수 있는 인증 기관에서 서명한 인증서를 사용하는 것이 좋습니다. 그러나 테스트 목적으로 자체 서명된 인증서를 사용하려는 경우 다음 단계를 수행합니다.

1. 관리자 권한으로 로그온하는 동안 PowerShell 콘솔에서 다음 명령을 실행합니다.

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. 를 입력합니다  `certlm.msc`. 그러면 로컬 컴퓨터에 대한 인증서 관리자가 열립니다.

3. **개인** 으로 이동한 다음 **인증서를** 엽니다.

4. **StatsManListener를 마우스 오른쪽 단추로 클릭합니다. \> 모든 작업 - \>프라이빗 키 관리...**

5. **추가** 를 클릭합니다.

6. **선택할 개체 이름 입력** 상자에 다음 텍스트를 입력합니다. 네트워크 서비스

7. **확인** 을 클릭합니다.

8. **모든 권한** 에서 **허용** 확인란을 선택 취소합니다. (읽기 권한만 필요합니다.)

9. **확인** 을 클릭합니다.

## <a name="for-more-information"></a>자세한 내용
<a name="BKMK_SelfCert"> </a>

자세한 내용은 아래 항목을 참조하세요.

- [비즈니스용 Skype 서버 통계 관리자에 대한 계획](plan.md)

- [비즈니스용 Skype 서버 통계 관리자 업그레이드](upgrade.md)

- [비즈니스용 Skype 서버 통계 관리자 문제 해결](troubleshoot.md)
