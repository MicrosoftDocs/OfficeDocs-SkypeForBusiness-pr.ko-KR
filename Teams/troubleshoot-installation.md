---
title: Windows에서 Microsoft 팀 설치 및 업데이트 문제 해결
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Windows에서 팀 데스크톱 클라이언트 앱의 설치 및 업데이트 문제를 해결 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: f47edf351d6a55f57977fee823d670b749896049
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837628"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Windows에서 Microsoft 팀 설치 및 업데이트 문제 해결

이 문서에서는 Windows에서 실행 되는 팀 데스크톱 클라이언트 앱의 설치 및 업데이트 문제를 진단 하 고 해결 하는 방법에 대 한 지침을 제공 합니다.

## <a name="check-whether-teams-is-updated-successfully"></a>팀이 성공적으로 업데이트 되었는지 확인

팀 업데이트가 성공적으로 설치 되었는지 확인 하려면 다음 단계를 따르세요.

1. 팀에서 프로필 사진을 선택한 다음**버전** **정보** > 를 클릭 합니다.
2. 같은 메뉴에서 **업데이트 확인**을 클릭 합니다.
3. 앱의 맨 위에 있는 배너가 팀의 "새로 고침"이 필요한 지 여부를 기다립니다. 이 프로세스는 새 버전의 팀을 다운로드할 수 있으므로 약 1 분에 링크를 표시 해야 합니다. 또한 배너를 통해 최신 버전을 이미 실행 하 고 있는지 알 수 있습니다 (이 경우 업데이트는 필요 없음).
4. 배너의 새로 고침 링크를 클릭 합니다.
5. 팀이 다시 시작 될 때까지 기다린 다음 1 단계를 반복 하 여 앱이 업데이트 되었는지 확인 합니다.

실패 메시지가 표시 되거나 버전 번호가 4 단계와 동일한 경우 업데이트 프로세스가 실패 합니다.

## <a name="troubleshoot-installation-and-update-issues"></a>설치 및 업데이트 문제 해결

### <a name="troubleshoot-installation-issues"></a>설치 문제 해결

팀이 설치 되 면 팀 설치 관리자 가%LocalAppData%\SquirrelTemp\SquirrelSetup.log.에 이벤트 순서를 기록 합니다. 가장 먼저 찾을 사항은 오류 메시지 이거나 로그 끝에 있는 호출 스택입니다. 로그 시작 부분에 있는 호출 스택은 설치 문제가 없음을 의미 하지 않을 수 있습니다. 설치 성공 (다른 컴퓨터에도 해당)에서 로그를 로그와 비교 하 여 예상 되는 결과를 확인 하는 것이 더 쉬울 수 있습니다.

SquirrelSetup에서 원인을 표시 하지 않거나 문제 해결을 위해 추가 정보가 필요한 경우 [응용 프로그램 및 시스템 로그 수집 및 분석](#collect-and-analyze-application-and-system-logs)을 참조 하세요.

### <a name="troubleshoot-update-issues"></a>업데이트 문제 해결

팀이 성공적으로 설치 되 면 로그 위치가%LocalAppData%\SquirrelTemp 에서%AppData%\Microsoft\Teams.로 전환 됩니다. 이 위치에는 SquirrelSetup 및 .log의 두 가지 로그 파일이 있습니다.

- 이 위치의 SquirrelSetup 파일은 팀 앱을 서비스 하는 실행 파일인 update.exe로 기록 됩니다.
- Store.exe 파일은 팀 앱 (특히 팀)에서 중요 한 응용 프로그램 이벤트를 기록 하는 데 사용 됩니다. 오류 정보를 포함 하 고 있을 수 있습니다.

이러한 로그 파일에는 PII (개인 식별 정보)가 포함 되어 있으므로 Microsoft에 전송 되지 않습니다.

팀은 업데이트 프로세스 (정책에 따라 다름)를 자동으로 시작 하거나 사용자의 프로필 사진으로 이동해 업데이트를 **확인**하 여 수동으로 업데이트를 확인할 수 있습니다 >. 두 메서드 모두 다음 순서 대로 이벤트를 사용 합니다.

1. **업데이트를 확인**합니다. 팀은 웹 요청을 만들고 현재 앱 버전과 배포 링 정보를 포함 합니다. 이 단계의 목표는 다운로드 링크를 가져오는 것입니다. 이 단계에서 오류가 로그. t e x에 기록 됩니다.
2. **업데이트를 다운로드**합니다. 팀은 1 단계에서 얻은 다운로드 링크를 사용 하 여 업데이트를 다운로드 합니다. 다운로드가 완료 되 면 팀이 Update.exe를 호출 하 여 다운로드를 준비 합니다. 다운로드 오류도 로그 .txt에 기록 됩니다.
3. **업데이트를 준비**합니다. 다운로드 된 콘텐츠는 Update.exe에 의해 수행 되는 중간 폴더%LocalAppData%\Microsoft\Teams\stage)에 확인 되 고 압축을 풀었습니다. 이 단계의 오류는 SquirrelTemp에 기록 됩니다.
4. **업데이트를 설치**합니다. 팀을 시작 하는 방법에는 여러 가지가 있습니다. 사용자가 로그인 하면 시스템에서 자동으로 팀을 시작 하거나 바로 가기를 통해 팀을 시작할 수 있습니다. 이 단계에서는 Update.exe가 준비 폴더의 현재 상태를 확인 하 고, 콘텐츠를 다시 확인 하 고, 파일 작업을 수행 하 여 앱의 단계를 취소 합니다. %LocalAppData%\Microsoft\Teams\current의 이전 응용 프로그램 폴더 는%LocalAppData%\Microsoft\Teams\previous에 백업 되 고 스테이지 폴더의 이름은 "current"로 변경 됩니다. 이 단계의 오류는 SquirrelTemp에 기록 됩니다.

SquirrelTemp 또는 .log에 충분 한 정보가 포함 되어 있지 않은 경우에도 문제 해결을 위한 자세한 정보가 필요 하며,이에 대 한 자세한 내용은 [응용 프로그램 및 시스템 로그 수집 및 분석](#collect-and-analyze-application-and-system-logs)을 참조 하세요.

## <a name="collect-and-analyze-application-and-system-logs"></a>응용 프로그램 및 시스템 로그 수집 및 분석

이 섹션에서는 응용 프로그램 및 시스템 로그를 수집 하 고 분석 하 여 문제 해결에 대 한 자세한 정보를 확인 하는 방법에 대해 설명 합니다. Sysinternals 도구를 사용 하 여 이러한 단계를 완료 합니다. 자세히 알아보려면 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)을 참조 하세요.

### <a name="collect-logs"></a>로그 수집

1. [Sysinternals 도구](https://download.sysinternals.com/files/SysinternalsSuite.zip)를 다운로드 합니다.
2. 로컬 드라이브 의% TEMP% 폴더에 zip 파일의 압축을 풉니다.
3. 관리자 권한 명령 프롬프트를 열고 다음을 수행 합니다.

    1. TEMP 폴더로 이동 하려면 다음을 실행 합니다.

        ```
        cd /d %TEMP%
        ```
    2. 설정 및 응용 프로그램 로그를 복사 합니다. 실패 시점에 따라 일부 로그는 표시 되지 않을 수 있습니다.

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. 다음을 실행 하 여 열린 핸들을 캡처합니다.

        ```
        handle > handles.txt
        ```

    4. 다음을 실행 하 여 열린 Dll을 캡처합니다.

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. 실행 중인 드라이버를 캡처하려면 다음을 실행 합니다.

        ```
        driverquery /v > driverquery.txt
        ```

    6. 다음을 실행 하 여 팀 폴더의 Acl (액세스 제어 목록)을 캡처합니다.

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>로그 분석 (고급 사용자 용)

업데이트에 실패 하면 예기치 않은 앱 동작이 발생할 수 있습니다. 예를 들어 사용자가 팀을 종료 하거나 오래 된 버전의 팀을 사용 하거나 팀을 시작할 수 없는 경우가 있습니다. 업데이트 중에 문제가 발생 하는 경우 원인을 찾기 위한 첫 번째 위치는 SquirrelTemp입니다. 다음은 가장 일반적으로 사용 되는 여러 가지 유형의 업데이트 실패와 로그를 사용 하 여 분석 하 고 문제를 해결 하는 방법입니다.

#### <a name="unable-to-exit-teams"></a>팀을 종료할 수 없음

팀에서 새 버전으로 자신을 업데이트 해야 하는 것으로 판단 하는 경우 새로운 앱을 다운로드 하 고 진행 한 다음 컴퓨터가 유휴 상태일 때 다시 시작 될 때까지 기다립니다. 이 프로세스 중에 발생 하는 일반적인 문제는 다른 프로세스나 파일 시스템 드라이버가 팀 .exe 프로세스를 잠그고이로 인해 excel.exe가 종료 되지 않도록 하는 것입니다. 결과적으로, 팀 앱을 새로 다운로드 및 준비 된 앱으로 바꿀 수 없습니다.

문제 해결 팁:

- 발생 한 문제를 확인 하려면 작업 표시줄에서 팀을 마우스 오른쪽 단추로 클릭 하 고 **종료**를 클릭 하 여 팀을 종료 합니다. 그런 다음 Windows에서 작업 관리자를 열어 팀 인스턴스가 계속 실행 중인지 확인 합니다.  
- 이 문제가 있는 컴퓨터에 있지 않은 경우이 문제가 발생 하는 컴퓨터에서 수집 된 SquirrelTemp를 검사 하 여 "프로그램: 로그에서 프로세스를 종료할 수 없습니다" 항목을 찾습니다.
- At.exe를 종료 하지 못하도록 막는 기능을 확인 하려면 Dll (.txt) 및 핸들 .txt 로그를 참조 하세요. 팀에서 종료 하지 못하도록 하는 프로세스에 대해 설명 합니다.
- 팀 종료를 방지할 수 있는 또 다른 원인으로는 커널 모드 파일 시스템 필터 드라이버가 있습니다. SysInternals 도구, [Procdump](https://docs.microsoft.com/sysinternals/downloads/procdump)를 사용 하 여 커널 모드 프로세스 덤프를 수집 합니다 ```procdump -mk <pid>```(여기서 <pid> 작업 관리자에서 가져온 프로세스 ID). Driverquery 로그 파일을 검사 하 여 팀에 방해할 수 있는 활성 필터 드라이버를 확인할 수도 있습니다.
- 이 상태에서 복구 하려면 컴퓨터를 다시 시작 합니다.

#### <a name="file-permissions"></a>파일 사용 권한

팀은 설치 및 업데이트 프로세스 전체에서 사용자의 프로필에 많은 하위 폴더 및 파일을 만듭니다. 앱과 업데이트는 비관리자 수준의 사용자로 실행 되므로 다음 폴더에 대 한 읽기 및 쓰기 권한을 부여 해야 합니다.

|폴더  |에서 사용 됨  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | 설치 단계 중의 팀 설치 관리자 (예: Teams_Windows_x64)        |
|%LocalAppData%\Microsoft\Teams  | 업데이트 프로세스 중에 앱 패키지를 추출 하 고 스테이지 하는 팀 업데이트 업데이트 (update.exe)        |
|%AppData%\Microsoft\Teams   |  팀 앱 (팀)-설정, 앱 상태 및 (미리 준비 됨) 다운로드 된 업데이트 패키지를 저장 합니다.       |

파일에 쓸 수 없기 때문에 팀의 액세스가 거부 되는 경우 다른 소프트웨어 응용 프로그램이 간섭 하거나 보안 설명자 항목이 폴더에 대 한 쓰기 권한을 제한할 수 있습니다.

문제 해결 팁:

- SquirrelTemp 또는 .log에서 "액세스 거부" 증명 정보를 찾습니다. 이 파일을 확인 하 여 실패 한 파일에 쓰려는 시도가 있는지 여부를 확인 합니다.
- Icacls을 열고 관리자가 아닌 사용자가 쓰기 작업을 차단 하는 ACE (유효 액세스 제어 항목)를 찾습니다. 일반적으로이는 DACL 항목 중 하나에 있습니다. 자세한 내용은 [icacls 설명서](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)를 참조 하세요.

#### <a name="file-corrupted"></a>파일이 손상 됨

일부 경우에는 암호화 소프트웨어 에서%LocalAppData%\Microsoft\Teams 폴더의 파일을 변경할 수 있으며,이 경우 팀이 시작 되지 않을 수 있습니다. 이 문제는 앱이 업데이트 되지 않는 경우에도 언제 든 지 발생할 수 있습니다. 불행 하 게도 파일이 손상 되 면이 상태에서 복구 하는 유일한 방법은 팀을 제거 하 고 다시 설치 하는 것입니다.

> [!NOTE]
> 이러한 단계 중 하나를 사용 하 여 문제의 근본 원인을 확인할 수 없는 경우 [프로세스 모니터](https://docs.microsoft.com/sysinternals/downloads/procmon) 세션을 시도해 볼 수 있습니다. 프로세스 모니터는 레지스트리와 파일 시스템에 대 한 액세스를 기록 하는 Sysinternals 도구입니다.

## <a name="related-topics"></a>관련 항목

- [Teams용 클라이언트 가져오기](get-clients.md)
- [Teams 클라이언트 업데이트](teams-client-update.md)