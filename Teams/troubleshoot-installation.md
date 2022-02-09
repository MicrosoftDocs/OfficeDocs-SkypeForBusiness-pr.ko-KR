---
title: Windows에서 Microsoft Teams 설치 및 업데이트 문제 해결
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Windows에서 Teams 데스크톱 클라이언트 앱의 설치 및 문제를 해결하는 방법에 대해 알아봅니다.
ms.openlocfilehash: beed5767c459e4f758af002ce881c8490d5cff16
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401172"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Windows에서 Microsoft Teams 설치 및 업데이트 문제 해결

이 자료에서는 Windows에서 실행 중인 Teams 데스크톱 클라이언트 앱의 설치 및 문제를 진단하고 해결하는 방법에 대한 지침을 제공합니다.

## <a name="check-whether-teams-is-updated-successfully"></a>Teams가 제대로 업데이트되었는지 확인

다음 단계에 따라 Teams 업데이트가 설치되었는지 확인합니다.

1. Teams에서 프로필 그림을 선택한 다음  > **버전** 에 대한 **정보** 를 클릭합니다.
2. 같은 메뉴에서 **업데이트 확인** 을 클릭합니다.
3. 앱 상단에 있는 배너가 Teams에 "새로 고침"이 필요함을 나타낼 때까지 기다립니다. 이 프로세스는 새 버전의 Teams를 다운로드하므로 링크가 약 1분 후에 표시됩니다. 또한 최신 버전을 이미 실행 중인지 여부를 배너를 통해 알 수 있으며, 이 경우 업데이트할 필요가 없습니다.
4. 배너에서 [새로 고침] 링크를 클릭합니다.
5. Teams가 다시 시작될 때까지 기다렸다가 1단계를 반복하여 앱이 업데이트되었는지 확인합니다.

오류 메시지가 표시되거나 버전 번호가 4단계와 같으면 업데이트 프로세스가 실패한 것입니다.

## <a name="troubleshoot-installation-and-update-issues"></a>설치 및 업데이트 문제 해결

### <a name="troubleshoot-installation-issues"></a>설치 문제 해결

Teams가 설치된 경우 Teams 설치 관리자는 이벤트 순서를 %LocalAppData%\SquirrelTemp\SquirrelSetup.log에 기록합니다. 가장 먼저 찾아야 할 것은 로그의 끝 근처에 있는 오류 메시지 또는 호출 스택입니다. 로그의 시작 부분에 있는 호출 스택은 설치 문제가 존재함을 의미하지 않을 수 있습니다. 다른 컴퓨터에서도 성공적인 설치에서 얻은 로그와 로그를 비교하여 예상한 내용을 쉽게 확인할 수 있습니다.

SquirelSetup.log에서 원인을 표시하지 않거나 문제를 해결하는 데 필요한 추가 정보가 필요한 경우 [응용 프로그램 및 시스템 로그 수집 및 분석을 참조하세요](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>업데이트 문제 해결

Teams가 성공적으로 설치되면 로그 위치가 %LocalAppData%\SquirrelTemp to %LocalAppData%\Microsoft\Teams로 전환됩니다. 이 위치에는 SquirrelSetup.log 및 logs.txt라는 두 로그 파일이 있습니다.

- 이 위치의 SquirrelSetup.log 파일은 Teams 앱을 서비스하는 실행 파일인 Update.exe에 의해 작성됩니다.
- Logs.txt 파일은 Teams 앱(특히 Teams.exe)에서 중요한 응용 프로그램 이벤트를 기록하는 데 사용됩니다. 오류 정보가 포함될 수 있습니다.

이러한 로그 파일에는 PII(개인 식별 가능 정보)가 포함되어 있으므로 Microsoft로 전송되지 않습니다.

Teams는 정책에 따라 자동으로 업데이트 프로세스를 시작하거나 사용자가 프로파일 그림 > **업데이트 확인** 으로 이동하여 업데이트를 수동으로 확인할 수 있습니다. 두 방법 모두 다음 이벤트 순서를 사용합니다.

1. **업데이트 확인**. Teams는 웹 요청을 하고 현재 앱 버전 및 배포 링 정보를 포함합니다. 이 단계의 목표는 다운로드 링크를 가져오는 것입니다. 이 단계에서 오류가 로그에 기록됩니다.
2. **업데이트를 다운로드합니다**. Teams는 1단계에서 얻은 다운로드 링크를 사용하여 업데이트를 다운로드합니다. 다운로드가 완료되면 Teams는 Update.exe를 호출하여 다운로드를 준비합니다. 또한 다운로드 오류가 로그에 기록됩니다.
3. **업데이트를 준비합니다**. 다운로드한 콘텐츠는 Update.exe에서 수행되는 중간 폴더 %LocalAppData%\Microsoft\Teams\stage)로 확인되고 압축이 풀립니다. 이 단계의 실패는 SquirrelTemp.log에 기록됩니다.
4. **업데이트를 설치합니다**. Teams를 시작하는 방법에는 여러 가지가 있습니다. 사용자가 로그인하거나 바로 가기를 통해 Teams를 시작할 수있을 때 시스템이 자동으로 Teams를 시작합니다. 이 단계에서 Update.exe는 준비 폴더가 있는지 확인하고 콘텐츠를 다시 확인한 다음 파일 작업을 수행하여 앱의 스테이지를 해제합니다. %LocalAppData%\Microsoft\Teams\current의 이전 응용 프로그램 폴더는 %LocalAppData%\Microsoft\Teams\previous에 백업되고 스테이지 폴더의 이름은 "current"로 변경됩니다. 이 단계의 실패는 SquirrelTemp.log에 기록됩니다.

SquirrelTemp.log 또는 Logs.txt에 근본적인 원인을 판별하기에 충분한 정보가 없고 문제점을 해결하기 위해 추가 정보가 필요한 경우 [ 응용 프로그램 및 시스템 로그 수집 및 분석](#collect-and-analyze-application-and-system-logs)으로 이동하세요.

## <a name="collect-and-analyze-application-and-system-logs"></a>응용 프로그램 및 시스템 로그 수집 및 분석

이 섹션에서는 응용 프로그램 및 시스템 로그를 수집 및 분석하여 문제를 해결하기 위한 보다 포괄적인 정보를 얻는 방법에 대해 설명합니다. Sysinternals 도구를 사용하여 이 단계를 완료합니다. 자세한 내용은 [Windows Sysinternals](/sysinternals/)를 참조하세요.

### <a name="collect-logs"></a>로그 수집

1. [Sysinternals 도구](https://download.sysinternals.com/files/SysinternalsSuite.zip)를 다운로드합니다.
2. zip 파일을 로컬 드라이브의 %TEMP% 폴더로 추출합니다.
3. 관리자 권한 명령 프롬프트를 열고 다음을 수행합니다.

    1. 다음을 실행하여 TEMP 폴더로 이동합니다.

        ```console
        cd /d %TEMP%
        ```
    2. 설정 및 응용 프로그램 로그를 복사합니다. 실패 지점에 따라 이러한 로그 중 일부가 없을 수도 있습니다.

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. 열린 핸들을 캡처하려면 다음을 실행합니다.

        ```console
        handle > handles.txt
        ```

    4. 열린 DLL을 캡처하려면 다음을 실행합니다.

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. 다음을 실행하여 실행 중인 드라이버를 캡처합니다.

        ```console
        driverquery /v > driverquery.txt
        ```

    6. Teams 폴더의 ACL(액세스 제어 목록)을 캡처하려면 다음을 실행합니다.

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>로그 분석(고급 사용자용)

업데이트에 실패하면 예측할 수 없는 앱 동작이 발생할 수 있습니다. 예를 들어, 사용자가 Teams를 종료할 수 없거나, 오래된 버전의 Teams를 보유하고 있거나, Teams를 시작할 수 없을 수 있습니다. 업데이트 중에 문제가 발생하는 경우 원인을 찾을 수 있는 첫 번째 위치는 SquirrelTemp.log입니다. 다음은 가장 일반적인 업데이트 오류가 나열된 여러 가지 유형과 로그를 사용하여 해당 업데이트를 분석하고 해결하는 방법입니다.

#### <a name="unable-to-exit-teams"></a>Teams를 종료할 수 없음

Teams를 스스로 최신 버전으로 업데이트해야 한다고 판단함에 따라 새 앱을 다운로드하고 스테이징한 다음, 시스템이 유휴 상태일 때 다시 시작될 기회를 기다립니다. 이 프로세스 중에 발생하는 일반적인 문제는 다른 프로세스 또는 파일 시스템 드라이버가 Teams.exe 프로세스를 잠가 Teams.exe가 종료되지 않는 경우입니다. 결과적으로 Teams 앱은 새로 다운로드하여 준비된 앱으로 대체할 수 없습니다.

문제 해결 팁:

- 겪고 있는 문제가 이에 해당되는지 확인하려면, Teams를 종료합니다(작업 표시 줄에서 Teams를 마우스 오른쪽 단추로 클릭한 후 **종료** 를 클릭합니다). 그런 다음 Windows에서 [작업 관리자]를 열어 Teams 인스턴스가 아직 실행 중인지 확인합니다.  
- 이 문제가 있는 컴퓨터에 있지 않은 경우 이 문제가 발생한 컴퓨터에서 수집한 SquirrelTemp.log를 검사하고 "프로그램 : 로그에서 프로세스를 종료할 수 없음"항목을 찾습니다.
- Teams.exe가 종료할 수 없는 원인을 확인하려면 Dlls.txt 및 Handles.txt 로그를 확인합니다. 이는 Teams를 종료할 수 없는 프로세스를 알려줍니다.
- Teams를 종료하지 못하게 할 수 있는 또 다른 원인은 커널 모드 파일 시스템 필터 드라이버입니다. SysInternals 도구 [ ProcDump ](/sysinternals/downloads/procdump)를 사용하여 ```procdump -mk <pid>```을 실행하여 커널 모드 프로세스 덤프를 수집합니다. 여기서 \<pid>는 작업 관리자에서 얻은 프로세스 ID입니다. Driverquery.txt 로그 파일을 검사하여 Teams를 방해할 수 있는 활성 필터 드라이버를 확인할 수도 있습니다.
- 이 상태에서 복구하려면 컴퓨터를 다시 시작합니다.

#### <a name="file-permissions"></a>파일 사용 권한

Teams는 설치 및 업데이트 프로세스 동안 사용자의 프로필에 여러 개의 하위 폴더와 파일을 생성합니다. 앱과 업데이트 프로그램이 비사용 사용자로 실행되므로 다음 폴더에 대한 읽기 및 쓰기 권한이 부여되어야 합니다.

|폴더  |사용자  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | 설치 단계 중 Teams 설치 프로그램(예 : Teams_Windows_x64.exe)        |
|%LocalAppData%\Microsoft\Teams  | 업데이트 프로세스 중에 앱 패키지를 추출하고 준비하기 위한 Teams 업데이트 프로그램(Update.exe)        |
|%AppData%\Microsoft\Teams   |  설정, 앱 상태 및 다운로드된(사전 준비된) 업데이트 패키지를 저장하는 Teams 앱(Teams.exe)       |

Teams에서 파일에 쓸 수 없어 액세스가 거부되는 경우 다른 소프트웨어 응용 프로그램이 간섭하거나 보안 설명자 항목이 폴더에 대한 쓰기 액세스를 제한할 수 있습니다.

문제 해결 팁:

- SquirrelTemp.log 또는 Logs.txt에서 "액세스 거부" 증거를 찾습니다. 이 파일을 확인하여, 파일에 쓰려고 시도했으나 실패한 기록이 있는지 확인합니다.
- Icacls.txt를 열고 관리자가 아닌 사용자의 쓰기 작업을 차단하는 효과적인 ACE(액세스 제어 항목)를 찾습니다. 일반적으로 DACL 항목 중 하나에 있습니다. 자세한 내용을 보려면 [icacls 설명서](/windows-server/administration/windows-commands/icacls)를 참조하세요.

#### <a name="file-corrupted"></a>파일이 손상됨

경우에 따라 암호화 소프트웨어가 %LocalAppData%\Microsoft\Teams 폴더의 파일을 변경하여 Teams가 시작되지 않을 수 있습니다. 앱이 업데이트되지 않은 경우에도 언제든지 발생할 수 있습니다. 안타깝게도 파일이 손상된 경우 이 상태에서 복구하는 유일한 방법은 Teams를 제거하고 다시 설치하는 것입니다.

> [!NOTE]
> 다음 단계 중 하나를 사용하여 문제의 근본 원인을 확인할 수 없는 경우 [프로세스 모니터링](/sysinternals/downloads/procmon) 세션을 시도할 수 있습니다. 프로세스 모니터링은 레지스트리 및 파일 시스템에 대한 액세스를 기록하는 Sysinternals 도구입니다.

## <a name="related-topics"></a>관련 항목

- [Teams용 클라이언트 가져오기](get-clients.md)
- [Teams 클라이언트 업데이트](teams-client-update.md)
- [Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
