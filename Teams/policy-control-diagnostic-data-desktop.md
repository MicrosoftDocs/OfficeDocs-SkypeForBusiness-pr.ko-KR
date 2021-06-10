---
title: Microsoft Teams의 필수 데스크톱 클라이언트 진단 데이터
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams의 정책 제어에 대한 모바일 속성 및 이벤트 목록입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c255fd02342eb6db1878608ad2da09683d7a83ec
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863229"
---
# <a name="required-desktop-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams의 필수 데스크톱 진단 데이터

다음 문서는 Microsoft Teams 데스크톱 이벤트 목록과 각 이벤트에서 수집하는 속성 목록을 포함합니다.

Microsoft로 전송되는 진단 데이터를 제어하는 방법을 포함하여 진단 데이터에 대한 자세한 내용은 [Teams 앱에서 Microsoft로 전송되는 진단 데이터](policy-control-overview.md#diagnostic-data-sent-from-the-teams-app-to-microsoft)를 참조하세요. Microsoft로 전송되는 진단 데이터를 보려면 [진단 데이터 뷰어](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855)를 사용할 수 있습니다.

## <a name="events"></a>이벤트

> [!NOTE]
> 아래에 나열된 모든 이벤트에 대한 공통 속성이 있습니다. 검토하려면 [모든 이벤트와 함께 전송된 속성](#properties-sent-with-all-events)을 참조하세요.

### <a name="logging"></a>로깅

> [!NOTE]
> 로깅 이벤트의 속성에 대한 자세한 내용은 [로깅 이벤트를 사용하여 전송된 속성](#properties-sent-with-logging-events)을 참조하세요.

- **adal-anonymous-mac.ts:this.logger.logError** - Mac 장치에서 익명으로 로그인할 때 일반 sso 오류가 발생했음을 기록합니다.
- **adalAnonymousUtil: loggingService-getInstance** - 앱에서 익명 사용자 인증을 시작할 수 없음을 기록하는 오류 문을 기록합니다.
- **adal-anonymous-windows.ts:this.logger.logError** - Windows 장치에서 익명으로 로그인할 때 일반 sso 오류가 발생했음을 기록합니다.
- **adalBase.ts:this.loggingService.logError** - 사용자 프로필이 Null인지 또는 비어 있는지를 확인확인 하는 데 필요한 정보를 기록합니다.
- **adal-impl-mac.ts:this.loggingService.logError** - 인증 동안 수신하는 원격 분석을 구문 분석할 때 문제 발생이나 Mac 장치에서 로그인할 때 발생하는 일반 sso 오류를 기록합니다.
- **adal-rigel-windows.ts:this.logger.logError** - 회의실 장치에서 로그인할 때 발생하는 일반 sso 오류를 나타내는 일반 로깅 문입니다.
- **adal-sso-windows.ts:this.loggingService.logError** - Windows 장치에서 로그인할 때 일반 sso 오류가 발생했음을 기록하고 채팅 서비스를 시작할 때 오류 또는 로그인 실패 정보를 기록합니다.
- **appOnlineService.ts:loggingService.getInstance** - 시작 시 구문 분석할 수 없는 설정 또는 사전 사용자 인증을 다운로드할 때 사전 승인된 설정으로 인한 오류 발생을 기록합니다.
- **appStart.ts:loggingService.logError** - 응용 프로그램을 시작할 수 없을 때 오류 발생, 디스크 공간 오류, 유효한 인증서 오류 또는 올바른 인증서를 찾을 수 없음과 앱 다시 시작을 기록합니다. 
- **browserWindowHttp.ts:this.loggingService.logError** - 파일 시스템 문제 때문에 응용 프로그램을 업데이트할 수 없음을 나타내는 정보를 기록합니다.
- **contextInstallService.ts:loggingService.getInstance** - 다음과 같은 경우에 발생하는 오류를 기록합니다.
  - 파일을 구문 분석하거나 읽거나 또는 컨텍스트 설치 기능에 중요한 URL을 확인하려는 경우.
  - URL Shortener에서 컨텍스트 설치 기능을 실행하려고 시도합니다.
- **crashManager.ts:loggingService.logError** - 응용 프로그램이 충돌할 때 오류의 원인을 파악하기 위해 정보를 기록합니다.
- **crashManager.ts:loggingService.logError** - 필수 부팅 데이터가 응용 프로그램을 실행하는 데 올바르게 로드되지 않는 경우에 발생하는 오류를 기록합니다.
- **logProviders\pageDumpProvider.ts:loggingService.getInstance** - 응용 프로그램이 충돌할 때 오류 정보를 기록합니다.
- **multiWindowManager.ts:this.logError** - 응용 프로그램을 실행하는 데 중요한 부팅 데이터가 제대로 로드되지 않는 경우 오류 발생을 기록합니다.
- **nativeElectronNotifications\osNotificationService.ts:this.loggingService.logError** - 해당 이벤트는 실패에 대한 알림을 시작할 때 발생하는 오류를 기록합니다.
- **OutlookMeetingAddinHelper.ts:loggingService.getInstance** - Outlook 모임 추가 기능을 사용하여 모임에 연결할 때 오류 발생을 기록합니다.
- **recoveryManager.ts:loggingService.getInstance** - 업데이트 롤백 중 발생하는 오류를 기록합니다.
- **renderer\startPage\startPage.ts:this.logger.logError** - 응용 프로그램 시작 페이지에 발생하는 오류를 기록합니다.
- **settingsService.ts:loggingService.getInstance** - 응용 프로그램 설정에 발생하는 오류를 기록합니다.
- **updateInfo.ts:loggingService.getInstance** - 업데이트를 전송하는 동안 발생하는 오류를 기록합니다.
- **updatenotification.js:this._loggingService.logError** - 디스크 공간 문제 발생을 기록합니다.
- **utility.ts:loggingService.logError** - 로컬 파일(응용 프로그램의 파일)에 액세스하는 동안 발생하는 오류를 기록합니다.
- **utility.ts:loggingService.getInstance** - 사용 가능한 디스크 공간의 오류, 디스플레이 문제, URL 문제, 쿠키 문제, 프로토콜 또는 응용 프로그램을 로드하기 위한 머신에 발생하는 regkey 문제를 기록합니다. 
- **windowmanager.js:this._loggingService.logError** - 쿠키 문제, 흰색 화면 문제, 데스크톱과 shell 통신 간 문제, URL 문제, 페이지 메시지 로딩 중 오류, 프로세스 렌더링 중 오류 및 네트워크 연결 문제를 기록합니다.
- **windowmanager.js:loggingService.getInstance** - 복구 창을 표시할 수 없음을 표시하기 위해 정보를 기록합니다.

### <a name="outlook-addin"></a>Outlook 추가 기능

> [!NOTE]
> Outlook 추가 기능 이벤트의 속성에 대한 자세한 내용은 [Outlook 추가 기능 이벤트를 사용하여 보낸 속성](#properties-sent-with-outlook-addin-events)을 참조하세요.

- **joinmeetingoperation** - 사용자를 모임에 참여하도록 하는 데 필요한 정보를 기록합니다.
- **meetingaddinapplifecycle** - 시작 또는 종료와 같은 앱 상태와 관련된 정보를 기록합니다.
- **meetingaddinloadtime** - Outlook에서 모임 정보를 로드하는 데 걸리는 시간을 기록합니다.
- **openmeetingoperation** - 예약된 모임을 여는 데 필요한 정보를 기록합니다.
- **savemeetingoperation** - 모임을 예약하는 동안 모임을 저장하는 데 필요한 정보를 기록합니다.

### <a name="scenario"></a>시나리오

> [!NOTE]
> 시나리오 이벤트의 속성에 대한 자세한 내용은 [시나리오 이벤트를 사용하여 전송된 속성](#properties-sent-with-scenario-events)을 참조하세요.

- **desktop_app_load** - 데스크톱 응용 프로그램이 시작되었는지, 서비스를 초기화해야 하는지, 해당 서비스를 초기화할 수 있는지를 확인하는 데 필요한 정보를 기록합니다.
- **desktop_app_not_ready** - 데스크톱 응용 프로그램이 작동할 준비가 되지 않았는지 확인하는 데 필요한 정보를 기록합니다.
- **desktop_install** - 데스크톱 응용 프로그램이 설치되었는지 또는 설치에 실패했는지를 확인하는 데 필요한 정보를 기록합니다.
- **desktop_previous_lifecycle_invalid** - 이전에 데스크톱 응용 프로그램을 실행하고 충돌한 후 해당 응용 프로그램이 다시 시작되었는지를 확인하는 데 필요한 정보를 기록합니다.

### <a name="tracking"></a>추적

> [!NOTE]
> 추적 이벤트의 속성에 대한 자세한 내용은 [추적 이벤트를 사용하여 전송된 속성](#properties-sent-with-tracking-events)을 참조하세요.

- **deeplink_scenario_missing** - Teams가 딥 링크에서 시작되었지만 원격 분석/진단이 없습니다.
- **desktop_app_initialized** - 데스크톱 응용 프로그램을 초기화할 때 응용 프로그램을 성공적으로 시작했는지 여부를 확인하는 데 필요한 정보를 기록합니다.
- **desktop_app_quit_exception** - 응용 프로그램이 종료되는 동안 작동이 중단됩니다.
- **desktop_blankScreenDetected** - 데스크톱 응용 프로그램에서 빈 화면을 렌더링할 때 오류를 확인하는 데 필요한 정보를 기록합니다.
- **desktop_blankScreenDetectedAfterRepaint** - 렌더링 시도를 검색하는 동안 페이지가 비어 있음이 감지되었습니다.
- **desktop_blankScreenRecoveredAfterRepaint** - 이전에 화면이 렌더링되지 않은 렌더링 문제에서 복구됩니다.
- **desktop_configuration_failed_to_save** - 데스크톱 설정을 저장하지 못한 경우 구성 오류를 확인하는 데 필요한 정보를 수집합니다.
- **desktop_navigation_error_recovery** - 5회 시도 후 페이지를 로드할 수 없는 경우 데스크톱 탐색 오류를 확인하는 데 필요한 정보를 수집합니다.
- **desktop_previous_gpu_crashed** - 데스크톱이 충돌할 때 그래픽 처리 장치 오류를 확인하는 데 필요한 정보를 기록합니다.
- **desktop_previous_plugin_host_crashed** - 데스크톱 응용 프로그램 충돌과 관련된 미디어 스택 문제를 확인하는 데 필요한 정보를 수집합니다.
- **desktop_recovery_cleared_user_data** - 응용 프로그램이 여러 번 중단되고 앱에서 복구할 로컬 캐시를 지워야 했음을 기록합니다.
- **desktop_settings_blank_on_load** - 응용 프로그램 설정이 존재하지 않기 때문에 오류가 발생했습니다.
- **desktop_settings_failed_to_load** - 데스크톱 설정을 로드할 수 없는 원인을 파악하는 데 필요한 정보를 수집합니다.
- **desktop_silent_restart** - 클라이언트 업데이트는 미리 구성되고 클라이언트는 사용자 중단 없이 업데이트됩니다.
- **desktop_terminated** - 사용자가 데스크톱 응용 프로그램을 닫을 때 프로세스 간 통신이 끊어졌는지를 확인하는 데 필요한 정보를 기록합니다.
- **desktop_uncaught_exception** 정의되지 않은 개체의 함수 호출이며 충돌/앱이 다시 시작됩니다.
- **desktop_write_storage_failed** - 데스크톱 응용 프로그램에서 저장소에 쓰지 못했을 때 디스크 오류를 확인하는 데 필요한 정보를 기록합니다.
- **registration_failed** - 추가 기능 등록 오류를 해결하는 데 필요한 정보를 기록합니다.
- **registration_success** - 추가 기능 등록 성공 여부를 확인하는 데 필요한 정보를 기록합니다.
- **security_unsupported_ipc_channel** - 허용되지 않은 프로세스 간 메시지가 인바운드되었습니다.
- **sfb_running_not_connected** - 비즈니스용 Skype 앱이 실행되고 있지 않음을 감지했습니다.
- **sfb_not_running** - 비즈니스용 Skype 호출의 ‘응답 대기’가 시간 초과되었음을 기록합니다.
- **sfb_never_replied** - 비즈니스용 Skype와 통신할 때 API 응답을 추적하지 않습니다.
- **server_error_hit** - 비즈니스용 Skype와 통신하는 ipc 파이프에서 발생한 오류를 추적합니다.
- **unexpected_sfb_ipc_disconnection** - 서비스에 연결하지 못하는 문제를 확인하는 데 필요한 정보를 기록합니다.
- **unregister_failed** - Outlook 모임 추가 기능을 등록 취소힐 때 발생하는 오류를 확인하는 데 필요한 정보를 기록합니다.

## <a name="userbi-panelaction"></a>UserBI panelaction

> [!NOTE]
> UserBI panelaction 이벤트의 속성에 대한 자세한 내용은 [UserBI panelaction 이벤트를 사용하여 전송된 속성](#properties-sent-with-userbi-panelaction-events)을 참조하세요.

- **inlinereply** - 사용자가 알림에서 회신했는지에 대한 정보를 기록합니다.
- **toastclick** - 토스트 알림에 대한 메시지 항목을 탐색하여 서비스 SLA를 모니터링하고 토스트 알림에 대한 적절한 응답을 로드하기 위한 사용자 클릭을 기록합니다.
- **toastdismiss** - 사용자가 토스트 알림의 렌더링을 해제할 때 발생하는 오류와 지연 사항을 확인하는 데 필요한 정보를 기록합니다.

- **toast_skip** - 지연된 토스트 알림을 전송하지 않는 데 필요한 정보를 기록합니다.
- **toasttimeout** - 토스트 알림의 렌더링이 시간 초과되었을 때의 오류와 지연 사항을 확인하는 데 필요한 정보를 기록합니다.

### <a name="userbi-panelview"></a>UserBI panelview

> [!NOTE]
> UserBI panelview 이벤트의 속성에 대한 자세한 내용은 [UserBI panelview 이벤트를 사용하여 전송된 속성](#properties-sent-with-userbi-panelview-events)을 참조하세요.

- **toastshow** - 토스트가 렌더링되었는지 확인하는 데 필요한 정보를 기록합니다.

## <a name="property-lists"></a>속성 목록

### <a name="properties-sent-with-all-events"></a>모든 이벤트와 함께 보낸 속성

| 속성 이름                              | 설명                                                        |
|--------------------------------------------|--------------------------------------------------------------------|
| EventInfo_Time                             | 이벤트 생성 시간                                              |
| EventInfo_Name                             | 이벤트 이름 - 이벤트 유형을 구분하는 데 사용됨             |
| EventInfo_BaseType/name                    | 이벤트 유형 - 이벤트에서 이벤트 유형을 구분하는 데 사용됩니다. |
| EventInfo_Sequence                         | 이벤트 순서                                              |
| userAgent                                  | 브라우저 에이전트 문자열                                               |
| userpdclevel                               | 사용자의 개인 정보 데이터 제어 설정                           |
| eventpdclevel                              | 이벤트의 개인 정보 데이터 제어 범주 수준             |
| AppInfo_Language                           | 앱 언어                                                       |
| clientType/AppInfo_ClientType              | 앱이 실행되는 클라이언트 유형                               |
| environment/AppInfo_Environment            | 사용자 요청을 제공한 엔지니어링 환경               |
| clientVersion/appversion/AppInfo_Version/desktopBuildVersion | 앱 버전                               |
| buildtime                                  | 앱이 엔지니어링 시스템에서 빌드된 타임스탬프            |
| osversion/DeviceInfo_OsVersion             | OS 버전                                                         |
| AppInfo_ProcessArchitecture                | 시스템 아키텍처(32비트/64비트)                                  |
| preferredLocales                           | 사용자에 대한 기본 설정 로캘                                      |
| locale/AppInfo_Locale                      | 앱 로캘                                                         |
| os/DeviceInfo_OsName                       | OS 이름                                                            |
| UserInfo_Language                          | 선택한 사용자 언어                                             |
| UserInfo_Id                                | 사용자 ID                                                            |
| UserInfo_TenantId/TenantId                 | 테넌트 ID                                                          |
| ring/UserInfo_Ring                         | 단계별 방식으로 응용 프로그램을 제공하는 데 도움이 되는 개념          |
| 지역                                     | 사용자의 요청을 제공한 데이터 센터 지역                       |
| UserInfo_ConfigIds/UserInfo_Etag           | 다른 실험/롤아웃에서 사용자를 식별하는 데 도움이 되는 ID     |
| DeviceInfo_BrowserName                     | 브라우저 이름                                                       |
| DeviceInfo_BrowserVersion                  | 브라우저 버전                                                    |
| DeviceInfo_Id/machineId/DeviceInfo_IdV2    | 장치를 식별하는 데 도움이 되는 ID                                  |
| totalMemory                                | 장치의 하드웨어 메모리                                      |
| cores                                      | 장치의 하드웨어 코어                                       |
| cpuspeed                                   | 장치의 하드웨어 CPU 속도                                   |
| DeviceInfo_CpuArchitecture/cpuarchitecture | 장치의 CPU 아키텍처                                     |
| UserRole                                   | 테넌트에서 사용자 역할을 식별하는 데 도움이 됩니다.                               |
| DeviceInfo_WindowsMode                     | Windows 보안 모드를 식별하는 데 도움이 됩니다.                               |
| desktopSession/Session_Id                  | 세션을 식별하는 데 도움이 됩니다.                                           |
| dbOpen                                     | 로컬 데이터베이스의 상태를 캡처합니다.                               |
| UserInfo_Upn                               | 사용자 식별자의 단면 해시                                  |

### <a name="properties-sent-with-logging-events"></a>로깅 이벤트를 사용하여 보낸 속성

| 속성 이름         | 설명                                                        |
|-----------------------|--------------------------------------------------------------------|
| message               | 로그에 대한 자세한 메시지를 캡처합니다.                          |

### <a name="properties-sent-with-scenario-events"></a>시나리오 이벤트와 함께 보낸 속성

| 속성 이름                     | 설명                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------|
| Scenario_Status                   | 시나리오 상태                                                               |
| Scenario_Step                     | 시나리오의 단계                                                                 |
| sequence                          | 시나리오의 일련 번호                                                    |
| delta                             | 시나리오에서 다양한 단계를 완료하는 데 소요된 시간                               |
| elapsed                           | 시나리오가 시작된 이후의 시간                                                    |
| scenario                          | 시나리오를 고유하게 식별                                                       |
| Scenario_Name                     | 시나리오 이름                                                               |
| errorInfo                         | 시나리오를 진행하는 동안 발생했을 수 있는 오류의 정보                       |
| session                           | 고유 세션 ID                                                                  |
| freeMemory                        | 사용 가능한 메모리를 캡처합니다.                                                     |
| processMemory                     | 프로세스 메모리를 캡처합니다.                                                            |
| scenarioDelta                     | 2개 시나리오 사이의 다른 시간을 캡처합니다.                                   |
| Session_DesktopId                 | 고유 세션 ID                                                                  |
| machineLocked                     | 머신이 잠겼는지 여부를 캡처합니다.                                          |
| windowIsVisible                   | 앱 창이 사용할 수 있도록 표시되었는지 캡처합니다.                                      |
| appStates/webAppStates            | 앱이 통과한 앱 상태 목록을 기록합니다. 앱의 상태를 확인할 수 있으므로 충돌 조사에 도움이 됩니다. |
| crashDesktopSession               | 손상된 세션의 ID를 캡처합니다.                                                 |
| appRuntime                        | 앱의 런타임을 캡처합니다.                                                        |
| diagnosticEvents                  | 앱 충돌 전 마지막 50개 웹앱                                 |
| activities                        | 충돌 전 발생한 마지막 50개 사용자 시나리오                            |
| crashSession                      | 손상된 세션의 ID를 캡처합니다.                                                 |
| crashId                           | 손상된 세션의 ID를 캡처합니다.                                                 |
| isPreviousLifecycleValid          | 이전 앱이 완전히 초기화되었으며 올바르게 종료되었는지 여부             |
| isSettingValid                    | 사전 인증 설정이 유효한지 여부                                                 |
| rollbackReason                    | 앱이 롤백된 이유                                            |
| deeplinkType                      | 딥 링크 유형                                                               |
| watchdogCrash                     | 중단으로 앱이 충돌했는지 여부                                                    |
| protocols                         | 앱을 시작하는 데 사용되는 프로토콜                                                    |
| electronBuild                     | 전자 앱 빌드 버전                                                      |
| distribution                      |  Teams가 exe, msi, dmg 또는 pkg 등으로 설치되었는지 여부                    |
| updateTimeOfDay                   | 앱이 업데이트된 시간                                                           |
| launchPath                        | Teams가 %LOCALAPPDATA%, %PROGRAMFILES% 또는 기타 위치에 설치되었는지 여부   |
| loggedIn                          | 사용자가 로그인한 경우                                                          |
| envType/complianceEnvironmentType | 상업적 클라우드 또는 비공개(예: DoD, GCC-High 등)                              |
| cpuusage                          | CPU 사용량                                                                          |
| installationSource                | 설치 사용자의 유형                                                      |
| adalVersion                       | 인증 라이브러리 버전                                                        |
| asyncStart                        | 동기 또는 비동기 시작을 사용하는 앱인지 여부                                 |
| attempts                          | 차단 화면을 표시하기 전에 사용자에게 수행한 온라인 검사 시도 횟수 |

### <a name="properties-sent-with-tracking-events"></a>추적 이벤트를 사용하여 보낸 속성

| 속성 이름                      | 설명                                                                      |
|------------------------------------|----------------------------------------------------------------------------------|
| name2                              | 추적 이벤트의 이름을 캡처합니다.                                              |
| numVisibleNotifications            | 표시되는 응용 프로그램 알림 횟수                                      |
| giphyEnabled                       | Giphy 서비스를 사용하도록 설정했는지 여부                                                |
| error                              | 추적 이벤트와 관련된 오류 세부 정보를 캡처합니다.                             |
| method                             | 프로토콜 메소드 GET 또는 POST                                                      |
| channel                            | 앱 내에서 프로세스간 통신 채널을 캡처합니다.                      |
| windowTitle                        | 이벤트와 연결된 표시 창 유형                                     |
| message                            | 오류 메시지의 유형                                                        |
| crashSession/crashDesktopSession/crashId/Session_DesktopId/Session_DesktopBackgroundId | 세션 디버그를 위해 고유 ID를 캡처합니다. |
| responseCode                       | 서비스 콜에 대한 응답 코드를 캡처합니다.                                      |
| errorUrl                           | 로드에 실패한 URL                                                      |
| Errorcode                          | 오류 코드를 캡처합니다.                                                              |
| ssoEventData                       | 인증 상태                                                  |
| correlationId                      | 디버깅을 위해 이벤트를 서비스 측과 상관시키는 ID                      |
| errorDescription                   | 오류 코드 설명을 캡처합니다.                                            |
| source                             | Teams 앱을 가져온 방법과 Teams가 설치된 패키지 유형       |
| windowIsDestroyed                  | 이벤트 중에 응용 프로그램 창의 참/거짓 상태                             |
| windowIsFocused                    | 이벤트 중에 응용 프로그램 창의 참/거짓 상태                             |
| windowIsVisible                    | 이벤트가 발생했을 때 응용 프로그램이 표시되었는지 여부                                  |
| windowIsMinimized                  | 이벤트 중에 응용 프로그램 창의 참/거짓 상태                             |
| windowIsMaximized                  | 이벤트 중에 응용 프로그램 창의 참/거짓 상태                             |
| windowIsFullscreen                 | 이벤트 중에 응용 프로그램 창의 참/거짓 상태                             |
| distSrc                            | 앱을 시작하는 사용자의 배포 원본을 캡처합니다.                    |
| retries                            | 끝점에 연결할 때 다시 시도 횟수                            |
| uses_slimcore                      | 웹 통화가 slimcore를 사용하는 경우 True 또는 false                                      |
| persistCookieExpiresIn             | 웹 응용 프로그램 쿠기에 대한 유효한 남은 시간                             |
| tenantName                         | 응용 프로그램 사용자의 테넌트 이름                                       |
| appStartReason                     | 사용자 시작, 업데이트 후 등과 같은 응용 프로그램 세션이 시작되는 방법입니다. |
| machineLocked                      | 이벤트를 진행하는 동안 머신이 잠겼는지 여부                        |
| data                               | 시나리오 조사를 위한 기술 데이터를 캡처합니다.                               |
| appRuntime                         | 앱의 런타임을 캡처합니다.                                                      |
| activities                         | 충돌 전 발생한 마지막 50개 사용자 시나리오                          |
| timeSinceActivity                  | 마지막 사용자 작업 이후 경과된 시간                                                    |
| appStates                          | 데스크톱 앱에서 수행한 앱 상태의 목록을 기록합니다. 이 기능은 데스크톱 앱의 상태를 보여 주기 때문에 충돌 조사에 도움이 됩니다. |
| timeSinceAppState                  | 앱 상태가 변경된 이후의 시간                                                 |
| webAppStates                       | 웹 클라이언트가 수행한 앱 상태의 목록을 기록합니다. 이 기능은 웹 클라이언트 앱의 상태를 보여 주기 때문에 충돌 조사에 도움이 됩니다. |
| timeSinceWebAppState               | 웹앱 상태가 변경된 이후의 시간                                             |
| diagnosticEvents                   | 앱 충돌 전 마지막 50개 웹앱                               |
| timeSinceLastDiagnosticEvent       | 마지막 진단 이벤트를 보낸 이후의 시간                                            |
| timeSinceSecondLastDiagnosticEvent | 마지막 두 번째 진단 이벤트를 보낸 이후의 시간                                     |
| appInitialized                     | WebApplication이 시작되었는지 여부                                               |
| targetVersion                      | 버전 응용 프로그램이 업데이트되는 버전                                    |
| port                               | 인터넷 메시지 포트 번호                                                     |
| originalUrl                        | 렌더링할 페이지의 원래 위치                                         |
| deeplinkId                         | Teams 링크에 대한 대상 유형의 GUID 링크                                          |
| appSessionEnd                      | 응용 프로그램 세션이 종료될 때 이벤트 발생 여부                             |
| eventData                          | 문제가 발생할 경우 디버깅하는 데 도움이 되도록 컴퓨터 상태 및 앱 구성을 캡처합니다.        |
| deeplinkType                       | 딥 링크 유형(채팅, 모임, 채널)                                    |
| previousUpdateUrl                  | 응용 프로그램이 마지막으로 업데이트를 검색한 위치                        |
| previousUpdateVersion              | 마지막 버전 응용 프로그램이 업데이트된 버전                                          |
| previousUpdateTime                 | 응용 프로그램 바이너리가 마지막으로 업데이트된 시간                                      |
| protocol                           | 파일 또는 이미지와 같은 링크에 대한 처리기 유형                                     |
| files                              | 이벤트와 연결된 파일 유형(예: 응용 프로그램 캐시 또는 GPU 캐시)    |
| Perf_WorkingSetSizeKB              | 메모리 캐시 크기                                                             |
| isTimeboxingWebAppInitialize       | 시간 상자 카운터가 소진되기 전에 앱이 초기화되었는지 여부                          |
| isExp                              | 사용 중인 앱 버전이 실험의 일부인지 여부                          |
| deviceType                         | 장치의 유형을 캡처합니다.                                                      |
| sanitizedErr                       | 삭제된 버전의 오류 정보를 캡처합니다.                              |
| rigelVersion                       | 리겔 장치를 캡처합니다.                                                 |
| DeviceInfo_OsSku                   | OS SKU 정보를 캡처합니다.                                                      |
| isLoggedOut                        | 사용자가 로그아웃된 경우 캡처합니다.                                               |
| complianceEnvironmentType          | 상업적 클라우드 또는 비공개(예: DoD, GCC-High 등)                           |
| restartTimes                       | 이전의 다시 시작에 대한 정확한 시간                                                 |
| Skype_ResultCode                   | Skype와 Teams 간 Interop 통신 결과를 캡처합니다.                 |
| cpumodel                           | CPU 모델을 캡처합니다.                                                            |
| isSlimCoreRunningOutproc           | Slimcore 구성 요소가 자체 프로세스에서 실행 중인지 여부                         |
| isSlimCoreStartedAsync             | 내장형 오디오/비디오(A/V) 스택의 출시 유형                               |
| networkState                       | 네트워크 상태를 캡처합니다.                                                    |
| desktopBuildAge                    | 이벤트 시간에서 응용 프로그램 빌드가 사용된 기간                                   |
| vdiMode                            | 앱이 VDI 모드로 실행되고 있는 경우 캡처합니다.                                       |

### <a name="properties-sent-with-userbi-panelview-events"></a>UserBI panelview 이벤트를 사용하여 보낸 속성

| 속성           | 설명                                              |
|--------------------|----------------------------------------------------------|
| Panel_Uri          | 사용자에게 전달된 패널의 Uri                   |
| Panel_Type         | 사용자가 액세스하는 패널 유형                          |
| Team_Id            | 사용자가 수행한 작업의 팀 ID |
| Thread_Id          | 사용자가 액세스한 스레드의 ID               |
| Panel_PreviousUri  | 이전 패널의 URI                                |
| Panel_Region       | 패널을 앱에서 호스팅한 영역             |
| Panel_LaunchMethod | 패널을 시작한 방법              |
| Panel_PreviousType | 이전 패널의 유형                               |
| Thread_Type        | 사용자가 액세스한 스레드 유형                          |
| Panel_LaunchSource | 시작한 패널의 소스 정보        |
| Tab_Type           | 사용자가 액세스한 탭의 유형                         |
| Team_Type          | 사용자가 액세스한 팀의 유형                            |

### <a name="properties-sent-with-userbi-panelaction-events"></a>UserBI panelaction 이벤트를 사용하여 보낸 속성

| 속성 이름         | 설명                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | 사용자 작업으로 액세스하는 리소스의 Uri                  |
| Panel_Uri             | 사용자에게 전달된 패널의 Uri                             |
| Action_Gesture        | 앱에서 사용자가 수행한 제스처 유형                       |
| Action_ScenarioType   | 기능에 대한 비즈니스 메트릭과 관련된 기능 그룹화       |
| Panel_Type            | 사용자가 액세스하는 패널 유형                                    |
| Action_Outcome        | 사용자가 수행한 작업의 결과                            |
| Team_Id               | 사용자가 수행한 작업의 팀 ID           |
| Module_Type           | 사용자 작업을 호스팅한 모듈 유형                        |
| Module_Name           | 사용자 작업을 호스팅한 모듈 이름                        |
| Module_Summary        | 사용자 작업을 호스트한 모듈 요약                       |
| Thread_Id             | 사용자가 액세스한 스레드의 ID                         |
| Panel_PreviousUri     | 이전 패널의 URI                                          |
| Panel_Region          | 패널을 앱에서 호스팅한 영역                       |
| Panel_LaunchMethod    | 패널을 시작한 방법                        |
| Panel_PreviousType    | 이전 패널의 유형                                         |
| Thread_Type           | 사용자가 액세스한 스레드 유형                                    |
| Module_State          | 사용자가 액세스한 모듈의 상태                               |
| Action_Scenario       | 비즈니스 메트릭과 관련된 기능 그룹 내의 기능 |
| Panel_LaunchSource    | 시작한 패널의 소스 정보                  |
| Tab_Type              | 사용자가 액세스한 탭의 유형                                   |
| Team_Type             | 사용자가 액세스한 팀의 유형                                      |

### <a name="properties-sent-with-outlook-addin-events"></a>Outlook 추가 기능 이벤트를 사용하여 보낸 속성

| 속성 이름                   | 설명                                                              |
|---------------------------------|--------------------------------------------------------------------------|
| AccountComparisonFailedReason   | Addin에서 계정과 Teams 계정을 비교하여 만들기가 허용되는지를 확인하고, 비교에 실패하는 경우 해당 이벤트를 보냅니다. |
| AccountComparisonSuccessful     | Addin에서 계정과 Teams 계정을 비교하여 만들기가 허용되는지를 확인하고, 비교에 성공하는 경우 해당 이벤트를 보냅니다. |
| AdalVersion                     | 사용된 인증 라이브러리 버전                               |
| AddinBitness                    | 추가 기능 버전                                                         |
| AddinLanguage                   | 사용 중인 추가 기능 문자열의 언어                                     |
| AggregatorSetupCompletedTime    | 추가 기능 로더의 설정 시간                                              |
| AppDomainCreatedTime            | 추가 기능 로더가 앱 도메인을 초기화하는 시간                            |
| AppointmentDisplayTime          | 모임 만들기 도중 약속 항목이 표시된 시간 |
| AuthenticationCompletedTime     | 지정된 요청에 대한 인증이 제공된 시간            |
| ConnectionMode                  | 사용자의 기본 Exchange 계정에 대한 연결 모드를 나타냅니다.     |
| ConnectionStartedTime           | Outlook에서 OnConnection를 호출하는 시간                                     |
| ErrorDetails                    | 오류 세부 정보를 캡처합니다.                                            |
| ErrorName                       | 오류의 이름을 캡처합니다.                                               |
| ExchangeVersion                 | Exchange의 버전을 캡처합니다.                                             |
| IsSmtpFormatError               | SMTP 주소에 오류 발생                                                    |
| IsTeamsRunning                  | Teams 프로세스를 실행 중인 경우 캡처합니다.                             |
| IsTeamsUserLoggedOut            | 사용자가 Teams에서 로그아웃된 경우 캡처합니다.                              |
| LanguageSetupCompletedTime      | 언어 설정이 완료된 시간                               |
| ManagedConnectTime              | 관리형 추가 기능이 연결 콜백을 수신한 시간               |
| ManagedOnStartupTime            | 시작 시간을 관리한 시간                                    |
| MTFetchCompleted                | MT 모임 옵션 요청이 완료된 시간                        |
| NetFrameworkVersion             | 사용된 .NET Framework                                                      |
| NetworkAvailable                | 네트워크 사용 가능                                                     |
| OperationStartTime              |  여러 작업이 시작되는 시간                                  |
| OsBitness                       | OS 비트 수                                                            |
| OutlookLanguage                 | Outlook 앱 언어를 캡처합니다.                                     |
| OutlookVersion                  | Outlook 앱의 버전을 캡처합니다.                                          |
| OwnerResolutionTime             | 모임 소유자를 확인하는 시간                                        |
| ParseResponseCompletedTime      | 응답 구문 분석이 완료된 시간                                  |
| RecipientResolutionError        | 받는 사람을 확인할 때 발생하는 오류 세부 정보                                 |
| RecipientsResolutionTime        | 받는 사람을 모두 확인하는 총 시간                                     |
| RehydrateCompletedTime          | Outlook에서 속성을 읽는 시간                               |
| SaveToOutlookCompletedTime      | Outlook에 속성이 저장된 시간                                |
| ServiceRequestStartTime         | 서비스 요청의 시작 시간                                        |
| ServiceResponseReceiveTime      | 서비스의 응답 시간                                        |
| SettingsInitializeCompletedTime | 설정이 초기화되는 시간                                           |
| SetupLoggingCompletedTime       | 로깅이 설정된 시간                                             |
| ShutdownBeginTime               | 추가 기능 종료가 시작되는 시간                                       |
| ShutdownCompletedTime           | 종료가 완료된 시간                                             |
| StartupBeginTime                | 추가 기능 시작이 시작되는 시간                                        |
| StartupCompletedTime            | 시작이 완료되는 시간                                              |
| TeamsDeployment                 | Teams 클라이언트(Dev, Prod) 배포                                   |
| TeamsRing                       | Teams 클라이언트에 로그인한 현재 사용자의 벨소리                            |
| TeamsVersion                    | Teams 앱 버전을 캡처합니다.                                            |
| TelemetrySetupCompletedTime     | 원격 분석 설치가 완료되는 시간                                   |
| UpnMismatch                     | Outlook과 Teams 간에 UPN 불일치가 있는지 여부                  |
| UserDomain                      | 사용자의 도메인                                                       |
| ViewUpdatedTime                 | 보기가 업데이트된 시간                                           |
