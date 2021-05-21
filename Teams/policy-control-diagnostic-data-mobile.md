---
title: Microsoft Teams의 필수 모바일 진단 데이터
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
ms.openlocfilehash: 93a58b878443943b2dbd8322dc710bf59d3827e9
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569236"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams의 필수 모바일 진단 데이터

다음 문서는 Microsoft Teams 모바일 이벤트 목록과 각 이벤트에서 수집하는 속성 목록을 포함합니다.

## <a name="events"></a>이벤트

> [!NOTE]
> 아래에 나열된 모든 이벤트에 대한 공통 속성이 있습니다. 이를 검토하려면 [모든 이벤트와 함께 전송된 속성](#properties-sent-with-all-events)을 참조하세요.

### <a name="panelaction"></a>PanelAction

> [!NOTE]
> PanelAction 이벤트의 속성에 대한 자세한 내용은 [panelaction 이벤트를 사용하여 전송된 속성](#properties-sent-with-panelaction-events)을 참조하세요.

- **accessibilityUserConfiguration** - 사용자가 접근성 기능을 토글할 때 사용합니다.
- **acknowledgeSettingChange** - 업데이트된 알림 설정 대화 상자에서 업데이트를 승인합니다. 이는 업데이트 알림을 승인하고 전체적인 알림 안정성을 결정하는 데 사용되는 기능 성공 메트릭입니다.
- **actionComposeMenu**
  - 메시지 확장 사용 생성.
  - 작업 메시지 확장 사용.
- **active_session_banner_dismissed** - 위치 공유 활성 알림 배너가 해제되었습니다.
- **activityChatClicked** - **활동** 탭에서 비 실시간 채팅을 선택하거나 분할 보기가 표시될 때 트리거됩니다.
- **activityContextMenu** - 활동 피드의 오버플로 작업입니다.
- **activityFeedClick** - 활동 피드 항목을 탭하고 봇 채팅으로 이동합니다.
- **activityFeedLongPress** - 피드 항목에서 길게 누르기 제스처를 캡처합니다.
- **activityFeedSwipe** - 피드 항목에서 살짝 밀기 제스처를 캡쳐합니다.
- **activityFilterClick** - 활동 필터 사용법을 캡처합니다.
- **activityFilterOptionsClick** - 활동 필터 사용량을 캡처합니다.
- **activityFilterOptionsClicked** - 활동 필터 사용법을 캡처합니다.
- **activityLiveChatClicked** - **활동** 탭의 라이브 모임에서 채팅을 선택하면 트리거됩니다.
- **activityLiveDetailsClicked** - **활동** 탭의 라이브 모임에서 **세부 사항** 을 선택할 때 트리거됩니다.
- **activityTabClicked** - 다음 사항 결정에 도움이 됩니다.
  - **활동** 탭이 표시됩니다.
  - Teams에서 **활동** 탭 이벤트를 캡쳐.
- **activityTypeDropdown** - **내 활동** 과 **피드** 사이를 전환하기 위해 활동 필터 사용법을 캡쳐합니다.
- **addChannel** - 채널을 추가합니다. 이 항목은 성공적인 채널 만들기에 대한 성공 데이터를 제공합니다.
- **addMember** - **자세히** 메뉴에서 **사용자 초대** 단추 선택을 트리거합니다.
- **addMembers** - 팀 또는 비공개 채널에 구성원을 추가합니다.
- **addToCalendar** - 개인 일정에 없는 일정 이벤트에 **일정에 추가** 단추를 선택합니다.
- **addToList** - 연락처 목록에 연락처를 추가합니다.
- **addToMeeting** - 모임 참가자 목록에 **모임에 추가** 단추를 선택합니다(채팅에 참가한 참가자의 경우).
- **addUserAsContact** - 연락처의 프로필 카드에 **연락처 추가** 아이콘을 선택하여 연락처를 추가할 수 있습니다.
- **admitAll** - 대기실 섹션에서 **모두 입장 허용** 단추가 선택된 횟수입니다.
- **admitParticipant** - 모임 명단에서 모임에 입장이 허용된 횟수입니다.
- **alertsNavAlert** - 피드 항목을 탭합니다.
- **android: null** - 봇 채팅을 음소거 또는 음소거 해제합니다. 이는 채팅에 대한 기존의 원격 분석을 향상시키고 응용 프로그램 정보만을 추가합니다.
- **anonymousMeetingJoin** - 익명 참가 제공 이름 페이지에서 **모임 참가** 를 선택하거나 이름 대화 상자에서 **확인** 을 탭합니다.
- **anonymousMeetingJoinWelcome** - 익명 참가 방문 페이지에서 **게스트로 참가** 를 선택합니다.
- **anonymousMeetingPostMeetingChat** - 통화 종료 화면에 사용자가 조회한 채팅 횟수입니다.
- **anonymousMeetingPostMeetingRejoin** - 익명 사용자가 모임에 다시 참가하려고 시도한 횟수입니다.
- **anonymousMeetingSignIn** - 사용자가 이름 입력 화면에 로그인하려고 탐색한 횟수입니다.
- **anonymousMeetingSignInWelcome** - 익명 참여 방문 페이지에서 **로그인 및 참가** 를 선택합니다.
- **anonymousMeetingToggleMuted** - 음소거 토글 단추를 선택한 횟수입니다.
- **anonymousMeetingToggleVideo** - 비디오 토클 단추를 선택한 횟수입니다.
- **appKilled** - 응용 프로그램이 종료됩니다.
- **approveTimeOffRequest** -  FLW(일선 직원) 관리자가 일선 직원의 휴가 요청을 승인할 때 입니다.
- **assigneeChange** - 새 담당자가 작업 항목에 추가될 때 트리거됩니다.
- **assignmentPickerClicked** - **할당 대상** 단추가 선택되어 담당자 선택 페이지가 열립니다.
- **assignmentRemoved** - **x**(담당자를 제거하는 유일한 방법)를 선택하여 작업 항목에서 담당자를 제거할 때 트리거됩니다.
- **attachmentAdded** - 작업의 첨부 파일이 성공적으로 추가되었는지 확인합니다.
- **attachmentDeleted** - 작업의 첨부 파일이 성공적으로 삭제되었는지 확인합니다.
- **attachmentUpdated** - 작업의 첨부 파일이 성공적으로 업데이트되었는지 확인합니다.
- **audioOnlyLowBatteryBanner** - 배터리 부족 배너로 인해 **오디오 전용** 이 선택됩니다.
- **audioOnlyPoorNetworkBanner** - 연결 배너가 불량하여 **비디오 끄기** 옵션이 선택됩니다.
- **audioUserDoubleTap** - 오디오 참가자를 두 번 탭합니다.
- **autoReconnectCallmebackCallDrop** - 종료 화면에서 **콜백** 단추를 선택한 횟수입니다.
- **autoReconnectDialIn**
  - UFD를 다시 연결하는 데 **전화 접속** 단추가 선택됩니다.
  - 다시 연결되는 동안 **전화 접속** 단추를 선택한 횟수입니다.
- **autoReconnectDialInonCallDrop** - 통화 연결이 끊긴 UFD에서 **전화 통화** 단추가 선택됩니다.
- **autoReconnectDialOut** - UDF를 다시 연결하는 데 **콜백** 단추가 선택됩니다.
- **autoReconnectRejoinonCallDrop** - 통화 종료 화면에서 **다시 참가** 또는 **재다이얼** 단추를 선택한 횟수입니다.
- **backFromCallMePSTN** - 콜백 PSTN 번호 흐름이 완료되지 않았습니다.
- **backToPhotoShare** - 카메라로 돌아갑니다.
- **backToStageFromWhiteboard** - 화이트보드에서 통화 화면으로 돌아갑니다.
- **backToWhiteboardFromStage** - 통화 화면에서 화이트보드로 이동합니다.
- **blockAnonymous** - 사용하는 경우:
  - 설정에서 발신자 ID가 없는 통화를 차단하는 통화 설정을 사용합니다.
  - 설정에서 발신자 ID가 없는 통화를 차단하는 통화 설정을 사용하지 않습니다..
  - 작업 시트에서 발신자 ID가 없는 통화를 차단하는 통화 설정을 사용합니다.
  - 작업 시트에서 발신자 ID가 없는 통화를 차단하는 통화 설정을 사용하지 않습니다.
- **blockCaller** - 차단:
  - 새로운 iOS 통화 작업 시트의 번호 및 연락처.
  - 연락처 카드의 연락처 및 번호.
  - 설정시 번호.
- **blockChat** - 봇 채팅 차단. 이는 채팅에 대한 기존 원격 분석을 향상시키고 응용 프로그램 정보만 추가합니다.
- **botClickCardAction** - 커넥터 카드 사용.
- **brbFeedback** - BRB 피드백 양식의 성능과 관련됩니다.
- **brbFormCancelled** - BRB 피드백 양식이 취소되고 사용자가 앱으로 돌아올 때 전송되는 이벤트입니다.
- **brbFormOpened** - BRB 양식이 열릴 때 전송되는 이벤트입니다.
- **brbFormSubmit** - 사용자가 피드백 양식에서 **제출** 을 선택할 때 전송되는 이벤트입니다.
- **breakStartEndClicked** - 시계 화면에서 **시작** 또는 **휴식 종료** 단추가 선택됩니다.
- **breakStartEndTriggered** - 휴식 시작 또는 종료를 사용하도록 선택하는 사용자를 등록합니다.
- **bucketSelected** - 버킷이 성공적으로 선택되었는지 확인합니다.
- **bucketUnselected** - 버킷이 성공적으로 선택 취소되었는지 확인합니다.
- **bucketPickerClicked** - 버킷 선택기가 성공적으로 시작되었는지 확인합니다.
- **BYOELiveEventJoin** - 사용자가 BYOE(broadcast your own event) 라이브 이벤트에 참가합니다.
- **calendarLiveChatClicked** - **일정** 탭의 라이브 모임에서 채팅합니다.
- **calendarMeetingJoin** - 일정에서 **모임 참가** 단추를 선택합니다.
- **calendarTab** - 아래 레일에서 **모임** 탭을 선택합니다. 일정 사용법을 이해하고 아래 레일에 있는 다른 앱과 비교하거나 하단 표시줄에서 선택한 후 일정 게시물을 렌더링하는 데 실패했는지 여부를 확인하는 데 유용합니다.
- **calendarTabClicked** - 아래 나열된 상황에서 일정 사용법이 표시되며 아래 레일에서 다른 탐색 모음 앱과 비교할 수 있습니다. 다음과 같이 오류가 있었는지 확인하는 데 사용할 수 있습니다.
  - **일정** 탭이 표시됩니다.
  - **모임** 탭이 아래 레일에서 선택됩니다.
- **calendarUpcomingChatClicked** - **일정** 탭에서 예정된 모임에서 채팅합니다.
- **callAccepted** - 통화가 수락되었습니다.
- **callAcceptedSFB** - 통화가 수락되었습니다.
- **callAppPreference** - 선호하는 통화 앱이 선택됩니다.
- **callControlsManualDismiss** - 통화 제어는 수동으로 해제됩니다.
- **callControlsManualInvoke** - 통화 제어는 수동으로 호출됩니다.
- **callHistoryItemExpand** - 통화 내역 항목이 확장되었습니다.
- **callHistoryTab** - 통화에서 **CallHistory** 탭이 선택됩니다.
- **callInProgressShown** - **_통화 중_* 배너가 표시됩니다.
- **callMePSTNConnected** - **통화** 가 성공되었습니다.
- **callOrMeetUpAddParticipants** - 트리거되는 경우:
  - 1:1 통화 화면에서 참가자 추가 단추를 탭합니다.
  - 참가자 추가에서 사용자(VoIP)를 선택합니다.
  - 참가자 추가에서 PSTN을 선택합니다.
  - 라이브 비공개 모임에 사용자를 추가합니다.
  - 라이브 비공개 모임에 PSTN을 선택합니다.
  - 라이브 비공개 모임에서 회사 연락처를 선택합니다.
  - 라이브 비공개 모임에서 장치 연락처를 선택합니다.
  - 라이브 비공개 모임에서 참가자 완료를 추가합니다.
  - 라이브 채널 모임에서 사용자를 추가합니다.
  - 라이브 채널 모임에서 PSTN을 선택합니다.
  - 라이브 채널 모임에서 팀 구성원을 선택합니다.
  - 라이브 채널 모임에서 장치 연락처를 선택합니다.
  - 라이브 채널 모임에서 참가자 완료를 추가합니다.
- **callOrMeetUpAddParticipantsDone** - 사용자가 참가자 추가를 완료합니다.
- **callOrMeetUpAddRoom** - 트리거되는 경우:
  - 명단에서 **회의실 추가** 가 선택됩니다.
  - 회의실 추가에서 검색 결과가 선택됩니다.
  - 근처에 대해 **해제** 가 선택됩니다.
  - 근처에 대해 **BT 사용** 또는 **위치** 가 선택됩니다.
  - 회의실 추가에서 근처 회의실 결과가 선택됩니다.
  - 회의실 추가에서 제안된 회의실 결과가 선택됩니다.
  - 회의실 추가에서 **완료** 가 선택됩니다.
- **callOrMeetUpAudioOffSwitch** - 라이브 통화 또는 모임에서 동반자 참가 모드에 있는 동안 **오디오 끄기** 단추를 넘깁니다.
- **callOrMeetUpAutoReconnect** - 네트워크 성능이 저하되면 사용자 장치가 자동 재연결 모드로 전환됩니다.
- **callOrMeetUpCallAccepted** - 트리거되는 경우:
  - 전화를 받습니다.
  - PSTN 통화를 수락합니다.
- **callOrMeetUpCallEnded** - 트리거되는 경우:
  - **통화 종료** 단추를 탭합니다.
  - callOrMeetupLive 중에 **통화 종료** 단추를 탭합니다.
  - lockScreen 중에 **통화 종료** 단추를 탭합니다.
  - notification 중에 **통화 종료** 단추를 탭합니다.
  - inApp 중에 **통화 종료** 단추를 탭합니다.
  - callKit 중에 **통화 종료** 단추를 탭합니다.
  - PSTN용 **통화 종료** 단추를 탭합니다.
- **callOrMeetUpChatWithParticipants** - 라이브 모임 또는 통화 중 채팅을 토글합니다.
- **callOrMeetUpDeviceAudioSwitch** - 트리거되는 경우:
  - 오디오 소스를 스피커로 전환합니다.
  - 오디오 소스를 장치로 전환합니다.
  - 오디오 소스를 Bluetooth로 전환합니다.
  - 오디오 소스를 오디오 끄기로 전환합니다.
  - 라이브 모임 또는 통화 중에 스피커를 전환합니다.
  - 라이브 모임 또는 통화 중에 스피커를 오디오 끄기로 전환합니다.
  - 라이브 통화 또는 모임에서 동반자 참가 모드에 있는 중에 **오디오 끄기** 단추를 넘깁니다.
  - PSTN 중에 장치 오디오 전환.
- **callOrMeetUpEnterDriveMode** - **...** 메뉴에서 수동으로 드라이브 모드로 전환합니다.
- **callOrMeetupExitDriveMode** - **주행 모드 종료** 단추를 탭합니다.
- **callOrMeetUpHold** - 트리거되는 경우:
  - 라이브 모임 또는 통화 중에 **대기** 단추를 탭합니다.
  - PSTN에서 통화 대기
- **callOrMeetUpIncomingVideoSwitch** - 라이브 모임 또는 통화 중에 IncomingVideo를 끕니다.
- **callOrMeetUpInvitedParticipants** - 트리거되는 경우:
  - 비공개 라이브 모임 중에 **기타 초대된** 참가자 그룹 맨 아래에서 **모두 보기** 를 클릭했습니다.
  - 라이브 채널 모임 중에 **기타 초대된** 참가자 그룹 맨 아래에서 **모두 보기** 를 클릭했습니다.
- **callOrMeetUpJoinedParticipants** - 트리거되는 경우:
  - 비공개 라이브 모임 중 **모임** 참가자 그룹 아래에 있는 **모두 보기** 를 클릭했습니다.
  - 라이브 채널 모임 중 **모임** 참가자 그룹 아래에 있는 **모두 보기** 를 클릭했습니다.
- **callOrMeetUpLobbyParticipants** - 트리거되는 경우:
  - 비공개 라이브 모임 중 **대기실** 참가자 그룹 아래에 있는 **모두 보기** 를 클릭했습니다.
  - 라이브 채널 모임 중 **대기실** 참가자 그룹 아래에 있는 **모두 보기** 를 클릭했습니다.
- **callOrMeetUpMicrophoneSwitch** - 트리거되는 경우:
  - 마이크를 켭니다.
  - 마이크를 끕니다.
  - 라이브 모임 또는 통화 중 **마이크** 단추를 선택합니다.
  - PSTN 중에 마이크를 전환합니다.
- **callOrMeetUpMuteParticipant** - 원격 참가자가 음소거되었습니다.
- **callOrMeetUpMuteParticipants** - 라이브 모임 또는 통화 중에 참가자가 음소거되었습니다.
- **callOrMeetUpParticipants** - 라이브 모임 또는 통화 중에 참가자를 토글합니다.
- **callOrMeetUpRemoteMuteUFD** - UFD가 음소거되었습니다.
- **callOrMeetUpResume** 트리거되는 경우:
  - 라이브 모임 또는 통화 중 **계속하기** 단추가 선택됩니다.
  - PSTN에서 통화를 계속합니다.
- **callOrMeetUpSearchParticipants** - 트리거되는 경우:
  - 비공개 라이브 모임 중에 모임 참가자에서 **검색** 을 클릭했습니다.
  - 비공개 모임 중에 **대기실** 참가자 그룹을 본 후 **검색** 을 클릭했습니다.
  - 비공개 모임 중에 **모임 참가 중** 인 참가자 그룹을 본 후 **검색** 을 클릭했습니다.
  - 비공개 모임 중에 **기타 초대된** 참가자 그룹을 본 후 **검색** 을 클릭했습니다.
  - 라이브 채널 모임 중에 모임 참가자에서 **검색** 을 클릭했습니다.
  - 라이브 채널 모임 중에 **대기실** 참가자 그룹을 본 후 **검색** 을 클릭했습니다.
  - 라이브 채널 모임 중에 **모임 참가 중** 인 참가자 그룹을 본 후 **검색** 을 클릭했습니다.
  - 라이브 채널 모임 중에 **기타 초대된** 참가자 그룹을 본 후 **검색** 을 클릭했습니다.
- **callOrMeetUpVideoSwitch** - 트리거되는 경우:
  - 비디오를 켭니다.
  - 비디오를 끕니다.
  - 라이브 모임 또는 통화 중에 비디오 단추가 선택됩니다.
- **callPark** - 트리거되는 경우:
  - **...** 메뉴에서 **통화 대기** 가 선택됩니다.
  - **검색** 단추가 선택됩니다.
  - 검색 대화 상자에서 **받기** 가 선택됩니다.
  - 검색 대화 상자에서 **취소** 가 선택됩니다.
- **callPreferenceSetting** - 통화 선호도 앱 설정입니다.
- **callsTabNewCall** - **통화** 탭에서 **새 통화** 를 선택합니다.
- **callTransfer** - 통화 전송을 시작합니다.
- **callVoicemailTab** - 통화에서 **음성 사서함** 탭이 선택됩니다.
- **cameraPermissionCancel** - 카메라 사용 권한 대화 상자에서 **취소** 를 선택합니다.
- **cameraPermissionGoToSettings** - 카메라 사용 권한 대화 상자에서 **설정** 으로 이동합니다.
- **cancelEditMeeting** - **모임 편집** 을 선택한 후 일정 페이지에서 **닫기** 단추를 선택합니다. 사용자가 모임 편집 선택을 중단하면 기록에 남습니다.
- **cancelFileShare** - 확인 대화 상자에서 **취소** 가 선택됩니다.
- **cancelFileUpload** - **x** 가 업로드 대화 상자에서 선택됩니다.
- **cancelMeeting** - 모임 세부 정보 페이지에서 **이벤트 취소** 를 선택합니다. 취소된 모임 수에 대한 집계 데이터를 가져오는 데 사용됩니다.
- **cancelNavigationToLink** - 탐색 취소가 선택되었습니다.
- **cancelRequestToJoinTeam** - 팀 참가 요청을 취소합니다.
- **cancelRequestToJoinTeamError** - 참가 요청 취소에 오류가 있습니다.
- **cancelNewMeeting** - 중단된 모임 선택을 기록하고 다음과 같이 원인을 확인합니다. 
  - 모임 스케줄러 페이지에서 **닫기** 단추가 선택됩니다.
  - **모임 편집** 을 선택한 후 모임 스케줄러 페이지에서 **닫기** 단추가 선택됩니다.
- **cardView - 할당된 AS 없음** - 카드 보기 및 카드 렌더링. 카드는 키 플랫폼 구조이며 플랫폼 사용을 이해하고 클라이언트 측에서 발생할 수 있는 잠재적인 문제 확인을 위한 사용법 및 패턴 측정에 필요합니다. 이 항목은 팀 참가와 관련된 오류 측정에 필요합니다.
- **castPpt** - 이벤트가 트리거되는 경우:
  - PowerPoint 옵션이 선택됩니다.
  - 특정 PowerPoint가 선택됩니다.
  - 파일 선택기 페이지에서 Teams 및 채널 폴더가 선택됩니다.
  - 파일 선택기 페이지에서 OneDrive 폴더를 선택합니다.
  - 캐스팅 세션을 중지합니다.
  - 멀티태스킹 PiP에 탭합니다.
  - 파일 보기에서 표시 옵션을 선택합니다.
- **castScreen** - 참조 사항:
  - 공유 화면 옵션에 탭합니다.
  - 화면 공유 세션을 중지합니다.
  - 파일 보기에서 표시 옵션을 선택합니다.
- **center_on_team_clicked** - 사용자가 그룹에서 지도를 중앙에 성공적으로 배치합니다.
- **channelFollow** - 채널에 대해 알림을 켭니다.
- **channelUnfollow** - 채널에 대해 알림을 끕니다.
- **channelsActiveSetting** - **데스크톱에서 활성 상태일 때 알림** 설정이 변경되었습니다.
- **chatCreation** - 성공적인 채팅을 만듭니다.
- **changeIsActiveSetting** - 데스크톱 활동 기반 알림을 변경합니다.
- **channel** - 채팅에서 새 메시지 단추 또는 텍스트 상자입니다.
- **channelDetails** - 채널 탐색 정보가 필요한 경우:
  - 채널 머리글이 선택됩니다.
  - 채널 세부 정보 페이지로 이동합니다.
- **channelFollow/channelUnfollow** - 채널을 팔로우하거나 팔로우 해제합니다.
- **channelNav** - 어디서나 채널로 이동합니다.
- **channelNavTab** - 다음과 같은 경우 Teams의 파일에 대한 성공 및 검색 기능 데이터를 제공합니다.
  - 채널에서 **파일** 탭이 선택됩니다.
  - 커넥터 카드 회신이 있습니다.
- **channelNotificationSettings** - 트리거되는 경우:
  - **새 알림 설정** 대화 상자가 선택됩니다.
  - 채널 보기에서 채널 알림 설정 단추가 선택됩니다.
  - 채널 알림 설정이 선택됩니다.
- **channelSelected** - 새 계획에 대해 채널이 성공적으로 선택되었는지 확인합니다.
- **channelSendMessage** - 트리거되는 경우:
  - 채널 메시지가 전송됩니다.
  - 봇은 작성 상자에서 @멘션됩니다.
- **channelTabOverflow** - 채널에서 **자세히** 탭을 선택합니다.
- **채팅** - 참조 사항:
  - 채팅에서 새 메시지 단추 또는 텍스트 상자입니다.
  - callHistory 항목에서 1:1 채팅이 선택됩니다.
  - 통화 목록에서 1:1 채팅이 선택됩니다.
- **chat - AS가 지정되지 않음** - 읽지 않은 채팅 또는 채팅 명단 편집, 특히 다음과 같은 경우:
  - 사용자를 채팅에 추가할 때 **완료** 단추를 선택합니다.
  - 읽지 않은 상태를 필터링하기 위해 채팅 목록 필터가 선택됩니다.
- **chatAddChat** - 탭한 채팅 단추에서 구성원을 추가합니다(1:1 채팅 및 그룹 채팅의 경우와 동일합니다).
- **chatAllowJoinViaLink** - 채팅 세부 정보 페이지에서 참가 링크 기능을 켜거나 끕니다.
- **chatAvatarEdit** - 채팅 세부 정보 페이지에서 아바타를 변경하는 그룹 수를 추적합니다.
- **chatAvatarEditCamera** - 사용자가 라이브 카메라 피드에서 아바타를 편집할 때 트리거됩니다.
- **chatAvatarEditGallery** - 사용자가 휴대폰에서 아바타를 편집할 때 트리거됩니다.
- **chatAvatarEditView** - 사용자가 기존 아바타 이미지를 볼 때 트리거됩니다.
- **chatListNavConversations** - 사용자가 채팅 목록 항목을 탭할 때입니다.
- **chatCancelAudioCall** - 그룹 음성 통화 취소 - 확인 대화 상자.
- **chatCancelVideoCall** - 그룹 화상 통화 취소 - 확인 대화 상자.
- **chatCM_CopyText** - 채팅 컨텍스트 메뉴에서 **텍스트 복사** 를 탭합니다.
- **chatCM_DeleteMessage** - 채팅 컨텍스트 메뉴에서 **메시지 삭제** 를 탭합니다.
- **chatCM_edit** - 채팅 컨텍스트 메뉴에서 **편집** 을 탭합니다.
- **chatCM_Forward** - 채팅 컨텍스트 메뉴에서 **전달** 을 탭합니다.
- **chatCM_markUnread** - 채팅 컨텍스트 메뉴에서 **읽지 않은 상태로 표시** 를 탭합니다.
- **chatCM_save** - 채팅 컨텍스트 메뉴에서 **저장** 을 탭합니다.
- **chatCM_SeenBy** - 컨텍스트 메뉴 옵션에서 **확인함** 을 탭합니다. 읽음 확인(수신인이 읽음).
- **chatContactsEnter** - **채팅 연락처** 탭이 입력됩니다.
- **chatDetails** - 다음과 같은 경우 채팅 세부 정보 페이지에 대한 성공 및 검색 기능 데이터를 제공합니다.
  - 채팅 머리글이 선택됩니다.
  - 채팅 세부 정보 페이지로 이동합니다.
- **chatRecentEnter** - **채팅 최근** 탭이 입력됩니다.
- **chatSendMessage** - 채팅 메시지를 보냅니다.
- **chatShareLink** 그룹 초대 링크를 보내는 사용자 수를 추적합니다.
- **chatStartAudioCall** - 트리거되는 경우:
  - 1:1 음성 통화 단추를 탭합니다.
  - 검색 결과에서 **오디오** 단추를 탭합니다.
  - 오른쪽에 있는 **통화 시작** 단추를 탭합니다.
  - callHistory 항목에서 1:1 음성 통화를 탭합니다.
  - 음성 사서함 항목에서 1:1 음성 통화를 탭합니다.
  - 그룹 음성 통화 걸기 - 확인 대화 상자.
- **chatStartAudioCallOnBehalfOf** - 대리인이 작업 시트에서 상사로서 통화를 시작합니다.
- **chatStartAudioCallOnBehalfOfMyself** - 대리인이 작업 시트에서 나 자신으로 통화를 시작합니다.
- **chatStartAudioCallSFB** - 1:1 음성 통화 단추를 탭합니다.
- **chatStartVideoCall** - 트리거되는 경우:
  - 1:1 화상 통화 단추를 탭합니다.
  - 검색 결과에서 비디오 단추를 탭합니다.
  - callHistory 항목에서 1:1 화상 통화를 탭합니다.
  - 그룹 화상 통화 걸기 - 확인 대화 상자.
- **chatStartVideoCallSFB** - 1:1 화상 통화 단추를 탭합니다.
- **chatWithMeetingParticipants** - 모임 세부 정보 페이지에서 **채팅** 탭을 선택합니다.
- **checkListAddClicked** - 체크리스트 섹션의 작업 세부 정보 보기에서 **항목 추가** 가 선택됩니다.
- **checkListItemAdded** - 작업에 대한 체크리스트 항목을 만듭니다.
- **checkListItemDeleted** - 작업에서 체크리스트 항목이 삭제됩니다.
- **checkListItemUpdated** - 작업에 대한 체크리스트 항목이 업데이트됩니다.
- **channelPickerClicked** - 채널 선택기가 성공적으로 시작되었는지 확인합니다.
- **checklistSeeAllClicked** 모든 체크리스트 항목을 보기 위해 작업 세부 정보 내에서 **모두 보기** 를 선택한 경우입니다.
- **chicletExpand** - 모바일에서 카드 미리 보기 방법 및 미리 보기 닫기 동작을 이해합니다.
- **clearFilter** - 작업 목록을 보는 동안 모든 필터가 지워진 경우입니다.
- **clickPhotoOfficeLens** - **사진 찍기** - 카메라 시작(Android만 해당)을 선택합니다.
- **clockInEntryTeamSelectionShown** - 사용자가 출근 시간을 기록하지 않은 상태에서 출퇴근 시간기록계에 팀을 선택합니다.
- **clockInOutClicked** - 출근 시간 기록 화면에서 **출근 기록** 또는 **퇴근 기록** 단추가 선택됩니다.
- **clockInOutTriggered** - 사용자의 출퇴근 기록을 등록합니다. 위치가 필요하다고 가정되면 위치가 확인될 때까지 트리거되지 않습니다.
- **closedBannerMessage** - 알림 배너 메시지가 닫힐 때 트리거됩니다.
- **closeLobbyBanner** - **닫기** 단추를 사용하여 대기실 알림을 닫은 횟수입니다.
- **commentAdded** - 작업에 메모가 추가되었음을 확인합니다.
- **commentsClicked** - 메모 보기가 성공적으로 시작되었는지 확인합니다.
- **commentUpdated** - 작업에 메모가 성공적으로 업데이트되었는지 확인합니다.
- **companionBannerJoin** - 최상위 배너에서 **참가** 를 선택합니다.
- **companionDismiss** - 도우미 배너를 해제합니다.
- **companionDismissProximity** - 도우미 배너를 해제합니다.
- **companionJoin** - 시트에서 도우미로 참가 옵션이 선택되었습니다.
- **companionJoinProximity** - 도우미 배너를 통해 참가했습니다.
- **completionStateChange** - 작업 목록에서 필터 보기가 완료되거나 완료되지 않은 필터 토글이 선택되면 트리거됩니다.
- **composeExpandComposer** - **형식** 단추를 탭합니다.
- **composeFilePick** - 네이티브 파일 선택기가 실행되었습니다.
- **composeImagePicker** - **이미지** 단추를 탭합니다.
- **composeLocation** - 편지 쓰기에서 **위치** 단추를 탭합니다.
- **composeMention** - @멘션.
- **composeOpenEmoticonPicker** - 이모티콘 선택기를 탭합니다.
- **composeOpenFunPicker** - 재미있는 선택기를 탭합니다.
- **composeParticipantAdded** - 참가자가 교대 근무 앱에 추가된 경우입니다.
- **composeSearchResult** - 앱 검색 결과 관련성을 이해하는 데 도움을 주는 메시지 확장 결과 선택입니다. 또한 앱 데이터로 메시지 전송 원격 분석을 개선합니다.
- **composeSelectExtension** - ME 앱에 탭합니다.
- **composeSendSmartReply** - 스마트 회신 항목을 클릭합니다.
- **composeSendMessage** - 앱 데이터로 메시지 전송 원격 분석을 개선합니다.
- **confirmAudioOn** - 사용자가 오디오를 켜고 싶다고 확인합니다.
- **confirmFileShare** - 확인 대화 상자에서 **공유** 가 선택됩니다.
- **consultTransfer** - 트리거되는 경우:
  - **전송** > **먼저 문의** 를 선택합니다
  - 전송 대상을 개인으로 설정합니다
  - 전송 대상을 전화 번호로 설정합니다.
- **consultTransferCall** - 트리거되는 경우:
  - 문의 전화가 시작됩니다.
  - 전송 확인 대화 상자에서 확인이 선택됩니다.
  - 전송 확인 대화 상자에서 취소가 선택됩니다.
  - **배너 전송** 단추가 선택됩니다.
  - **배너 다시 시작** 단추가 선택됩니다.
- **consultTransferChat** - 트리거되는 경우:
  - 문의 채팅이 시작됩니다.
  - 전송 확인 대화 상자에서 확인이 선택됩니다.
  - 전송 확인 대화 상자에서 확인이 선택됩니다.
  - **배너 전송** 단추 또는 **배너 다시 시작** 단추가 선택됩니다.
- **consumeVoiceMessage** - 음성 메시지가 재생되었습니다.
- **ContactCard_SeeMoreOOF** - 긴 OOF 메시지에 대해 자세히 확인합니다.
- **contactOrganizer** - 선택된 **연락처 주최자** 입니다.
- **conversation, tabs** - 탭이 선택됩니다.
- **copyLink** - 채널 게시물에 대한 링크를 복사합니다.
- **contactActivity** - 연락처 카드에서 사용자 활동을 보는 단추가 선택되었을 때입니다.
- **conversation** - 사용자가 **채팅** 또는 **게시물** 탭으로 이동하는 경우입니다.
- **cortanaClose** - 사용자가 수동으로 Cortana 캔버스를 끝내는 경우입니다.
- **cortanaEduCategorySelect** - 사용자가 교육 팁 범주의 항목을 클릭하는 경우입니다.
- **cortanaEduOpen** - 교육 페이지가 Cortana 캔버스에 표시되는 경우입니다.
- **cortanaInvoke** - Cortana가 의견을 경청하기 시작하는 경우입니다.
- **cortanaKWSwitchToggle** - 사용자가 Cortana 설정 페이지에서 KWS 스위치를 탭하는 경우입니다.
- **cortanaMicPermissionDialogButtonClick** - 사용자가 Cortana 캔버스에서 마이크 사용 권한을 부여하거나 거절하는 경우입니다.
- **cortanaOpen** - 사용자가 Cortana 캔버스를 여는 경우입니다.
- **cortanaOptionsOpen** - 사용자가 Cortana 캔버스의 옵션 버튼을 탭하는 경우를 말합니다.
- **cortanaSafetyFirstActions** - 사용자가 안전 제일 선언을 수락하는 경우를 말합니다.
- **cortanaSafetyFirstLaunch** - 사용자가 첫 실행 경험이 완료된 후에 처음으로 Cortana를 여는 때를 말합니다.
- **cortanaSettingsOpen** - 사용자가 Cortana 캔버스에서 Cortana 설정 버튼을 클릭하여 Cortana 설정 페이지를 여는 경우를 말합니다.
- **cortanaStopResponding** - 사용자가 Cortana 캔버스의 취소 버튼을 클릭하는 경우입니다.
- **cortanaUserSettingsLaunch** - 사용자가 Teams 설정에서 Cortana 설정을 여는 경우입니다.
- **cortanaVoiceSelect** - 사용자가 Cortana 설정 페이지에서 Cortana 음성 글꼴을 선택하는 경우입니다.
- **createChannel** - 다음과 같은 경우 새 채널에 대한 성공적인 생성 또는 폐기 작업에 대한 성공 데이터를 제공합니다.
  - **채널 만들기** 페이지에서 **완료** 단추가 선택됩니다.
  - **채널 만들기** 페이지에서 **취소** 단추가 선택됩니다.
- **createComposeExtension** - 메시지 확장 사용 또는 작업 ME 사용을 만듭니다.
- **createConversationClicked** - 다른 작업자와 대화를 할 경우입니다.
- **createDefaultPlannerPlan** - 공유 목록은 해당 그룹에서 사용자가 처음 작업 앱을 열 때 자동으로 생성되며, Planner 서비스로 만들어진 자동 목록을 확인합니다. 사용자가 처음 공유 작업 목록을 만들려고 할 때 Planner에서 기본 공유 작업 목록이 성공적으로 만들어졌는지 확인합니다.
- **createOrJoinTeam** - **+** 단추는 팀을 만들거나 팀에 참가하기 위해 선택됩니다.
- **createPersonalPlan** - 개인 목록이 만들어지고 ToDo 서비스로 만들어진 목록을 확인합니다. ToDo에 새 개인 작업 목록이 만들어졌는지 확인합니다.
- **createPersonalSubtask** - 개인 하위 작업이 성공적으로 만들어졌는지 확인합니다.
- **createPersonalTask** - 개인 작업이 성공적으로 만들어졌는지 확인합니다.
- **createPlan** - 공유된 작업 목록이 성공적으로 만들어졌는지 확인합니다. 중간 계층을 통해 공유 계획이 성공적으로 만들어졌는지 확인합니다.
- **createPlannerPlan** - 공유 목록이 만들어지고 Planner 서비스로 만들어진 목록을 확인합니다. Planner에서 새 공유 작업 목록이 만들어졌는지 확인합니다.
- **createPlannerTask** - Planner 서비스에 대한 통화를 확인합니다. 공유 작업 목록에서 작업이 성공적으로 만들어졌는지 확인합니다.
- **createShiftClicked** - 관리자가 **교대 근무 만들기** 를 선택한 경우입니다.
- **createShiftOrTimeOffClicked** - **교대 근무** 또는 **휴가** 를 선택할 경우 트리거됩니다.
- **createTask** - 작업을 만들 수 없을 경우, Planner 서비스 호출 확인에 사용됩니다. 작업 생성 작업이 실패했는지 확인합니다.
- **createTaskList** - 사용자가 홈 보기에서 계획 보기 만들기로 이동하는 경우입니다.
- **createTeam** - 다음과 같은 경우, 새 팀 만들기에 대한 성공적인 생성 또는 폐기 작업에 대한 성공 데이터를 제공합니다.
  - **팀 만들기** 페이지에서 **완료** 단추가 선택됩니다.
  - **팀 만들기** 페이지에서 **취소** 단추가 선택됩니다.
- **createTeam, createChannel** - 다음과 같은 경우 성공적인 구성원 추가 및 새 팀 만들기에 대한 성공 데이터를 제공합니다.
  - **구성원 추가** 페이지(먼저 기존 내용 확인)에서 **건너 뛰기** 단추가 선택됩니다.
  - **구성원 추가** 페이지(먼저 기존 내용 확인)에서 **완료** 단추가 선택됩니다.
  - 팀 또는 채널 만들기 승인을 표시합니다.
- **crossCloudDialogCancel** - 클라우드 간 대화 상자에 대해 **취소** 가 선택됩니다.
- **crossCloudDialogJoin** - 클라우드 간 대화 상자에 대해 **게스트로 참가** 가 선택됩니다.
- **dashboardNav** - 사용자가 채팅 대시보드의 타일로 이동합니다.
- **dateChanged** - 사용자가 교대 근무 날짜를 수정했습니다.
- **datePickerLaunch** - 날짜 선택기가 성공적으로 시작되었는지 확인합니다.
- **dayClicked** - 사용자가 교대 근무를 볼 때 일 보기를 선택합니다.
- **daySaved** - 사용자는 일일 가용성을 저장하여 교대 근무일을 저장합니다.
- **declineTimeOffRequest** - 사용자가 휴가 요청을 거절할 경우입니다. 관리자가 휴가 요청을 거절하는 것은 휴가에 있어 핵심 기능입니다.
- **deleteClicked** - 작업 세부 정보에서 **삭제** 를 선택하면 확인 대화 상자가 나타납니다.
- **deleteContact** - 사용자가 기존 비공개 연락처를 삭제합니다.
- **deleteMeeting** -모임 세부 정보 페이지에서 **삭제** 단추를 선택합니다.
- **deletePersonalTask** - 개인 작업이 성공적으로 삭제되었는지 확인합니다.
- **deletePersonalSubtask** - 개인 하위 작업이 성공적으로 삭제되었는지 확인합니다.
- **deletePlannerTask** - 공유 작업 삭제 연산이 성공적으로 완료되었는지 확인합니다.
- **deleteShift** - 교대 근무 삭제.
- **duration_picker_dismissed** - 기간 선택기를 해제할 경우입니다.
- **deleteTask** - Planner 서비스에서 삭제 작업이 성공했는지 실패했는지 확인합니다. 작업 삭제가 실패했는지, 즉 작업 삭제가 성공하지 못했음을 확인합니다.
- **deleteVoicemail** - 탭한 음성 사서함 항목을 삭제합니다.
- **demotedToAttendee** - 사용자가 발표자를 강등합니다 - 대화 상자의 **변경** 단추.
- **denyParticipant** - 사용자가 명단에서 누군가 입력을 거부한 횟수입니다.
- **descriptionChanged** - 공유 작업 설명이 성공적으로 변경되었는지 확인합니다.
- **descriptionClicked** - 사용자가 작업 세부 정보에서 **설명 보기** 를 선택하는 경우입니다.
- **detailsTabClicked** - 모임에서 **세부 정보** 탭이 선택됩니다.
- **deviceAddressBookSync** - 설정 페이지에서 주소록 동기화가 켜져있을 때 실행됩니다. 
- **deviceAddressBookUnsync** - 설정 페이지에서 주소록 동기화가 꺼져있을 때 실행됩니다. 
- **dialIn** - 사용자가 모임에 전화를 걸려면 선택합니다(여러 위치).
- **dialInBadNetworkBanner** - 연결 상태가 좋지 않은 배너에 **전화 접속** 이 선택됩니다.
- **dialInBadNetworkBannerCancel** - 네이티브 대화 상자에서 **전화 접속** 이 취소됩니다.
- **dialInBadNetworkBannerConfirm** - 네이티브 대화 상자에서 **전화 접속** 이 확인됩니다.
- **dialInCall** - **전화 접속** 팝업에서 **통화** 가 선택됩니다.
- **dialInCancel** - **전화 접속** 팝업에서 **취소** 가 선택됩니다.
- **dialOutCall** - 트리거되는 경우:
  - 운전 모드로 참가합니다.
  - **콜백** 팝업에서 **전화 걸기** 를 선택합니다.
- **dialOutCallAAD** - 작업 시트의 **내 번호** 에서 번호를 선택한 경우입니다.
- **dialOutCallRecent** - 작업 시트의 이전 최근 번호에서 번호를 선택한 경우입니다.
- **dialOutCancel** - **콜백** 팝업에서 **취소** 가 선택됩니다.
- **dialOutDialog** - **새 번호** 는 작업 시트에서 선택됩니다.
- **dialOutFailRetry** - 실패 배너에서 **다시 시도** 가 선택됩니다.
- **DialPad** - 통화 목록에서 **다이얼패드** 단추가 선택됩니다.
- **disableCategory** - 알림 유형이나 수신 전화 알림을 사용하지 않도록 설정합니다.
- **disabled** - FRE(첫 실행 경험)에서 **알림 건너뛰기** 가 선택됩니다. 이는 FRE 흐름에서 알림 건너뛰기에 대해 주요 성공 데이터를 제공합니다.
- **disableQuietDays** - 조용한 날을 사용하지 않게 설정합니다. 조용한 날에 대한 성공 원격 분석 기능입니다.
- **disableQuietHours** - 방해 금지 모드를 사용하지 않게 설정합니다.
- **discoverTeams** - Teams 페이지 찾아보기 및 참가로 이동합니다.
- **Dismiss_earlycancelledCQF** - CQF 조기 취소 통화 양식이 해제됩니다.
- **Dismiss_ratemycallCQF** - CQF 비율 내 통화 양식이 해제됩니다.
- **Dismiss_ratemyliveeventCQF** - CQF 비율 내 라이브 이벤트 양식이 해제됩니다.
- **dismissBadNetworkBanner** - 연결 상태가 좋지 않은 배너에 대해 **해제** 가 선택됩니다.
- **dismissFlyout** - **해제** 단추가 선택됩니다.
- **dismissModality** - 양식 선택기가 공유없이 종료됩니다.
- **dismissModalityPicker** - **양식 선택기** 단추가 선택됩니다.
- **dismissReadReceiptsNotice** - 기능 공지에서 **확인** 이 선택됩니다.
- **dismissStartRecording** - 녹음/녹화시 오류를 해제합니다.
- **dismissStopRecording** - 녹음/녹화 중지시 오류를 해제합니다.
- **dismissUseWifiForVideoBanner** - 사용자가 배너를 해제할 경우 트리거됩니다.
  - 이는 사용자에게 원격 참가자 비디오가 차단되었음을 알리며, 사용자가 이를 보려면 WiFi로 전환해야합니다.
  - 이는 사용자가 비디오를 공유하려면 WiFi로 전환하도록 알려줍니다.
- **DLPDelete** - 사용자가 차단된 메시지를 삭제했습니다.
- **DLPEdit** - 사용자가 차단된 메시지를 편집했습니다.
- **DLPOverride** - 사용자가 차단된 메시지를 무시했습니다.
- **DLPOverrideReport** - 사용자가 가양성을 보고했고 메시지를 무시했습니다.
- **DLPReport** - 사용자가 가양성을 보고했습니다.
- **DLPResolve** - 사용자가 DLP 메시지 해결을 시도했습니다.
- **DLPSeeOriginal** - 사용자가 원본 메시지를 보려고 탭합니다.
- **downloadFile** - 도움이 되는 경우:
  - 다운로드 작업이 시작되었는지 확인합니다.
  - 파일이 성공적으로 다운로드되었는지 확인합니다.
- **dragDatePickerHandle**
- **dtmfPSTNCall** - 다이얼패드의 DTMF 단추를 탭합니다.
- **dueDateChanged** - 사용자가 작업에 기한을 할당할 때 트리거됩니다.
- **dueDatePickerClicked** - 작업 세부 정보에서 **기한** 단추를 선택하고 기한 선택기 페이지를 열면 트리거됩니다.
- **dueDateSelected** - 사용자가 작업 목록을 보는 동안 기한별로 필터를 적용할 때 트리거됩니다.
- **dueDateUnselected** - 사용자가 작업 목록을 보는 동안 기한별로 필터를 적용 취소할 때 트리거됩니다.
- **edit** - 채팅 메시지의 **편집** 단추입니다.
- **editChannel** - 사용자가 소유하거나 관리하는 채널을 편집하려고 단추를 선택합니다.
- **editContact** - 사용자가 기존 비공개 연락처를 편집합니다. 이 작업은 연락처 카드로 이동하여 수행할 수 있습니다.
- **editMeetingResponse** - 모임 세부 정보 페이지에서 모임 응답을 편집합니다.
- **editNavigation** - **자세히** 메뉴에서 하위 모음 앱의 순서를 편집하기 위해 **다시 정렬** 이 선택됩니다.
- **editRsvpMeetingOptions** - 기존 선택에서 변경하려면 **참석 여부 알림 요청** 을 선택합니다.
- **editShiftClicked** - 교대 근무를 편집합니다.
- **editSmartReply** - 스마트 회신 항목을 편집합니다.
- **editTeam** - 사용자가 단추를 눌러 자신이 소유하거나 관리하는 팀을 편집합니다.
- **editTeam, editChannel** - 다음은 팀 구성원의 성공적인 추가 및 기존 팀의 성공적인 생성과 관련된 경우입니다.
  - **구성원 추가** 페이지(기존 팀 또는 채널)에서 **취소** 단추가 선택됩니다.
  - **구성원 추가** 페이지(기존 팀 또는 채널)에서 **완료** 단추가 선택됩니다.
- **emergencyCall** - 통화 플랜에서 건 긴급 전화입니다.
- **emergencyCallDirectRouting** - 직접 라우팅에서 건 긴급 전화입니다.
- **emergencyCallLocationPolicyBased** - 다이얼패드를 사용하는 DialEmergency입니다.
- **emergencycallSecurityDeskNotify** - 긴급 전화가 걸리고 보안 팀에 알려집니다.
- **enableCategory** - 알림 설정 사용 관련:
  - 알림 유형.
  - 수신 전화 알림.
- **enabled** - FRE(첫 실행 경험) 흐름에서 알림 사용 관련:
  - FRE(첫 실행 경험)에서 **알림 사용** 이 선택됩니다.
  - 미리 알림을 사용하도록 설정합니다.
- **enabled/disabled** - 통화 권한 또는 연락처 권한입니다(Android만 해당)
- **enabled, notNow** - 알림 권한 프롬프트 **수락** 단추, FRE(첫 실행 경험) 알림 권한(iOS)입니다. 알림 기능을 사용하게 설정한 사람 수를 캡쳐하고 그 정보를 제공합니다.
- **enablediOSPrompt** - 사용자는 실제로 iOS 알림 권한 프롬프트에서 알림을 사용하도록 설정합니다. 이는 알림 권한 프롬프트에서 실제로 iOS에서 알림을 사용하게 한 사용자에 대한 정보를 제공합니다.
- **enabledQuietDays** - 조용한 날을 사용하도록 설정합니다.
- **enableLocationPermission** - 사용자가 위치 공유 기능에 대한 위치 권한을 사용할 경우입니다.
- **enableQuietDays** - 사용자가 조용한 날을 사용하도록 설정합니다.
- **enableQuietHours** - 방해 금지 모드를 사용하도록 설정합니다.
- **endEditing** - **저장** 단추를 누릅니다.
- **endFileShare** - 파일 공유 대화 상자에서 **뒤로 이동** 이 선택됩니다.
- **endMyShift** - 공유 모드의 장치 수 또는 로그아웃된 횟수입니다.
- **endPhotoShare** - 사진 공유에서 **x** 아웃합니다.
- **entryPointClicked** - **일정** 탭에서 **요청** 을 선택합니다. 여기서 요청은, FLW(일선 직원)가 교대 근무 시간 등을 요청하는 경우입니다.
- **endPSTNCallSelected** - 사용자가 PSTN 및 콘텐츠 통화를 종료합니다.
- **endPSTNCallShown** - 사용자에게 PSTN 또는 콘텐츠 통화를 종료하라는 메시지가 표시됩니다.
- **endVideoShare** - 비디오 공유에서 **x** 아웃합니다.
- **errorShown** - 오류가 표시됩니다.
- **expand/collapse** - 장치 연락처 또는 회사 연락처 섹션입니다.
- **expandCollapseSection** - 섹션 머리글을 탭해서 섹션을 확장하거나 축소합니다.
- **Expected: atMention - Android: chatSendMessage - iOS: sendMsg** - 작성 상자에서 봇을 @멘션합니다.
- **Expected: botClickCardAction - Android: showCard - iOS: missing** - 카드 단추를 탭합니다. 카드는 키 플랫폼 구조이며 플랫폼 사용을 이해하고 클라이언트 측에서 발생할 수 있는 잠재적인 문제 확인을 위한 사용법 및 패턴 측정에 필요합니다.
- **Expected: chatSendMessage - iOS: composeSendMessage** - 채널에서 **회신** 에 탭하여 봇 채팅에 회신합니다.
- **Expected: composeSendMessage - Android: replyChannel - iOS: missing** - 채널에서 **회신** 에 탭하여 봇 채팅에 회신합니다.
- **Expected: messageLike - Android: reactLike_CM** - 봇 메시지에 좋아요를 표시합니다.
- **Expected: messageUnread - Android: markAsLastUnread** - 봇 메시지에 대한 메시지 컨텍스트 메뉴 옵션입니다.
- **federatedUpgradeNewChat** - 레거시 채팅이 네이티브로 업그레이드됩니다.
- **files** - 채팅 및 채널 파일 탭에서 파일 목록이 성공적으로 완료되었는지 추적합니다.
- **fileSelected** - PowerPoint 프레젠테이션이 선택됩니다.
- **fileThumbnailPreviewDownloaded** - 파일의 미리 보기가 성공적으로 렌더링되었는지 식별하는 데 도움이 됩니다.
- **fileThumbnailPreviewFromCache** - 미리 보기가 캐시에서 성공적으로 표시되는지 캡쳐하고, 파일의 미리 보기가 성공적으로 렌더링되었는지 식별하는 데 도움이 됩니다.
- **fileThumbnailPreviewNotAvailable** - 파일의 미리 보기가 성공적으로 렌더링되었는지 식별하는 데 도움이 됩니다.
- **fillFrameVideo** - 작업 시트에서 프레임을 채웁니다.
- **firstTimeSignedIn** 다음에 의해 트리거된 로그인 또는 가입 이벤트:
  - 로그인에 성공합니다.
  - 첫 로그인에 성공합니다.
  - 로그인 오류는 사용자에게 표시됩니다.
  - 최초 로그인시 구현된 MAM/MDM 정책에 대한 원격 분석을 기록합니다.
  - 최초 로그인 성공 후 앱 설치 참조 페이지 매개 변수를 기록합니다.
- **fitToFrameVideo** - 작업 시트에서 프레임에 맞춥니다.
- **flipCamera** - 카메라를 플리핑합니다.
- **forcedUpdateAccept** - 사용자가 강제 업데이트 대화 상자에서 앱 버전 업데이트를 수락합니다.
- **forcedUpdateExit** - 사용자가 강제 업데이트 대화 상자에서 앱 버전을 업데이트하는 대신 앱을 닫습니다.
- **forcedUpdatePrompt** - 최신 보안 및 개인 정보 수정이 없는 오래된 버전의 사용자에게 연락해야하는 상황에서 사용됩니다.
- **formattingBold** - 사용자가 굵게 서식을 선택합니다.
- **formattingHighlight** - 사용자가 강조 서식을 선택합니다.
- **formattingImportant** - 사용자가 중요도를 선택합니다.
- **formattingItatlics** - 사용자가 기울임꼴을 선택합니다.
- **formattingTextColor** - 사용자가 텍스트 색 서식을 선택합니다.
- **formattingUnderline** - 사용자가 밑줄을 선택합니다.
- **FRE - No AS Assigned** - 앱 시작시 MAM/MDM 정책에 대한 원격 분석을 기록합니다. MAM 및 MDM의 Intune 통합에 대한 원격 분석입니다. FRE(첫 실행 경험) 동안 실패에 대한 성공 데이터를 제공합니다.
- **freActionClicked** - **시작**, **나중에 시도**, 또는 **닫기**(GPS)가 FRE(첫 실행 경험)에서 선택됩니다.
- **freDone** - FRE(첫 실행 경험)이 완료되었습니다.
- **freTriggered** - 사용자가 FRE(첫 실행 경험)에서 출퇴근 시간기록계를 봅니다.
- **funSearchQueryEntered** - Giphy 쿼리가 입력되었습니다. Teams의 Giphy 첨부 기능에 대한 성공 데이터입니다.
- **funSelectItem** - Giphy 이미지가 선택됩니다. Teams의 Giphy 첨부 기능에 대한 성공 데이터입니다.
- **galleryImage** - 이미지 업로드 됨 - 갤러리.
- **get_directions_clicked** - **길 찾기** 단추가 선택됩니다.
- **goToNotificationSettings** - **업데이트된 알림 설정** 대화 상자에서 알림 설정 페이지로 이동합니다.
- **GPSPromptClicked** - OS 프롬프트에서 **허용** 또는 **허용 안 함** 이 선택됩니다. GPS를 허용하거나 허용하지 않습니다.
- **group_map_closed** - 사용자가 채팅에서 지도 보기를 엽니다.
- **group_map_open** - 사용자가 지도 보기를 닫습니다.
- **groupCallJoin** - 사용자가 그룹 전화에 참가합니다.
- **groupClicked** - 사용자가 교대 근무 그룹을 선택할 때 추적합니다.
- **guideMe** - 사용자가 3P 앱 차단 알림에 대해 알리고 문제 해결 지침을 제공하는 배너를 선택합니다.
- **hamburgerMenu** - 햄버거 메뉴로 이동합니다. 햄버거 메뉴에는 계정 전환, 알림 설정, 데이터 설정 및 프로필 설정과 같은 중요한 작업을 포함합니다.
- **handoffComplete** - 이 장치에서 모임 또는 통화가 전달되었습니다.
- **handoffJoin** 작업 시트에서 모임 전달 옵션이 선택됩니다.
- **hardwareAudioOff** - 하드웨어 단추를 통해 오디오를 끕니다.
- **hardwareAudioOn** - 하드웨어 단추를 통해 오디오를 켭니다.
- **hide** - 채팅을 숨깁니다.
- **hideChannel** - 팀 및 채널 목록에서 채널을 숨깁니다.
- **image** - 이미지.
- **immediateCallForward** - 즉시 착신 전환 대상이 설정되거나 즉시 착신 전환을 사용합니다(전화 벨소리는 사용 안 함)
- **importanceToggleClicked** - **!** 필드가 작업 항목 세부 정보 내에서 토글될 때 트리거됩니다.
- **importantMessage_select** - 사용자가 우선순위 상황에 맞는 메뉴에서 중요한 메시지를 선택합니다.
- **importantMessageSend** - 사용자가 중요한 메시지를 보냅니다.
- **inCallDialOut** - 사용자가 통화 중 추가 옵션에서 **콜백** 단추를 선택합니다.
- **initiatePhotoShare** - 사진 공유를 시작합니다.
- **initiateVideoShare** - 비디오 공유를 시작합니다.
- **install** - 설치 또는 설치 이벤트입니다.
- **installReferrer** - 최초 설치 후 앱 참조 페이지 매개 변수를 기록합니다.
- **invisionWhiteboardClicked** - 다음 경우 Invision 화이트보드가 선택됩니다.
  - **채널 파일** 탭.
  - 모임 **채팅 파일** 탭.
- **inviteFreemium** - 초대 화면에서 **+** 단추를 탭합니다.
- **inviteGuest** - 초대 화면에서 **+** 단추를 탭합니다.
- **joinFromDeeplinkInTeams** - Teams 앱 내에서 딥 링크를 통해 참가한 사용자입니다.
- **joinFromDeeplinkOutsideTeams** - Teams 앱 외부에서 딥 링크를 통해 참가한 사용자입니다.
- **joinFromJoinLauncher** - 참가 시작 관리자에서 참가한 사용자입니다.
- **joinFromNudge** - 넛지에서 참가한 사용자입니다.
- **joinFromStore** - 앱 스토어에서 앱을 다운로드한 후 참가한 사용자입니다.
- **joinMeeting** - 다음 상황의 경우, 일정에서 모임 참가의 성공 또는 실패를 감지합니다.
  - 전화 접속을 통해 모임에 참가합니다.
  - 콜백을 통해 모임에 참가합니다.
  - 모임 콘텐츠에만 참가합니다.
  - 안건 보기에서 **모임 참가** 단추를 선택합니다.
- **joinOptionsEdu** - EDU 사용자가 예약된 모임에 참가하기위해 옵션을 선택하면 적절한 옵션이 표시됩니다.
- **joinTeam** - **참가** 단추를 누릅니다.
- **joinViaCode** - 사용자가 코드를 통해 모임에 참가합니다.
- **labelPickerClicked** - 레이블 선택기가 성공적으로 시작되었는지 확인합니다.
- **labelSelected** - 레이블이 성공적으로 선택되었는지 확인합니다.
- **labelUnselected** - 레이블이 성공적으로 선택 취소되었는지 확인합니다.
- **launchLinksGallery** - 사용자가 대시보드에서 링크 갤러리를 입력하는 경우입니다.
- **직접, 링크, appShortcut와 같은 시작 소스** - 직접 또는 링크를 통해 시작합니다(활성 사용자에 대한 데이터 수집을 위해 앱 시작시 MAM(모바일 응용 프로그램 관리) 또는 MDM(모바일 장치 관리) 원격 분석을 기록).
- **leaveChat** - 채팅 나가기를 확인합니다.
- **legacyChatLink** - 레거시 채팅에 대한 링크가 선택됩니다.
- **likeAppDismiss** - 사용자가 앱을 좋아하는지 여부를 묻는 메시지가 응답없이 해제되는 경우입니다.
- **likeAppNo** - 사용자가 앱을 좋아하는지 묻는 메시지에 아니요로 응답을 받는 경우입니다.
- **likeAppYes** - 사용자가 앱을 좋아하는지 묻는 메시지에 예로 응답을 받는 경우입니다.
- **likeMsg** - **좋아요** 를 선택합니다.
- **linkPreviewCancel** - 미리 보기 종료 동작을 이해합니다.
- **listUserClicked** - 사용자가 지금 작업에서 사용자를 선택할 경우입니다.
- **liveCaptions** - 라이브 캡션이 켜져 있거나 꺼져 있습니다.
- **liveEventAdditonalLink** - 추가 링크가 선택됩니다.
- **liveEventInfo** - **정보** 단추가 선택됩니다.
- **liveEventJoin** - 사용자가 라이브 이벤트에 참가합니다.
- **liveEventLeave** - **나가기** 단추를 누릅니다.
- **liveEventPresenterJoin** - 발표자가 라이브 이벤트에 참가합니다.
- **liveEventPresenterJoinAsAttendee** - 라이브 이벤트 발표자가 참석자로 참가했습니다.
- **liveEventQnA** - **질문 및 답변** 아이콘이 선택됩니다.
- **liveEventYammer** - **Yammer** 아이콘이 선택됩니다.
- **liveMeetingPushNotificationClicked** - 푸시 알림이 선택됩니다.
- **liveMeetingToastClicked** - 인앱 알림이 선택됩니다.
- **live_location_in_chats_from_profile_clicked** - 프로필 보기에서 **실제 위치** 가 선택됩니다.
- **lobbyPickAudio** - 대기실에서 사용자가 오디오 출력을 전환하는 횟수입니다.
- **lobbyToggleMuted** - 대기실에서 사용자가 마이크를 켜거나 끈 횟수입니다.
- **lobbyToggleVideo** - 대기실에서 사용자가 비디오를 켜거나 끈 횟수입니다.
- **logOutClicked** - 사용자가 로그아웃하는 경우입니다.
- **location_active_tracking** - 사용자의 장치가 활성 추적으로 전환됩니다.
- **locationCard** - 위치 카드를 선택합니다.
- **location_family_sync** - MSA 가족 앱에서 만들어진 가족 그룹 구성원을 표시합니다. 동의를 받을 수있는 모든 가족 구성원이 표시되는지 확인합니다.
- **location_group_map_sync** - 지도 보기가 열립니다.
- **location_map_load** - 지도 보기가 로딩됩니다.
- **location_map_markers_load** - 지도 보기가 로드됩니다. 적극적으로 공유하는 모든 사용자의 위치 표시가 지도 보기에 제대로 표시되는지 확인합니다.
- **location_message_send** - 사용자가 위치 공유 세션을 시작합니다.
- **location_data_use_privacy_denied** - 사용자가 TFL의 위치 데이터 사용을 설명하는 팝업에서 **나중에** 를 해제하거나 선택합니다.
- **location_data_use_privacy_granted** - 사용자가 TFL의 위치 데이터 사용을 설명하는 팝업에서 **허용** 을 선택합니다. 
- **location_settings_open** - 사용자가 위치 설정을 엽니다.
- **location_sharing_start** - 사용자가 채팅에서 자신의 실제 위치를 공유합니다.
- **location_sharing_stop** - 사용자가 채팅에서 자신의 실제 위치 공유를 중지합니다.
- **loginFailed** - 사용자가 로그인할 수 없습니다.
- **loginSuccess** - 사용자가 로그인할 수 있습니다.
- **manageBlockedNumbers** - 설정을 통해 차단된 번호에 액세스합니다.
- **manualSendMessage** - 메시지가 수동으로 전송됩니다.
- **mapAppPicker** - 사용자가 위치 카드에 탭할 때 사용할 매핑 앱을 선택하는 경우입니다.
- **markAsRead** - 읽은 상태로 표시됩니다.
- **markAsUnread** - 읽지 않은 상태로 표시됩니다.
- **markChannelRead** - 사용자가 채널을 읽은 상태로 표시합니다.
- **messageBookmarkMessage** - 커넥터 카드를 저장합니다. 앱 관련 데이터로 기존 원격 분석을 사용합니다. 또는 봇 메시지를 저장합니다.
- **markAsLastUnread** - 커넥터 카드 컨텍스트 메뉴입니다.
- **maskCallerId** - 사용자는 호출자 ID를 마스킹하기 위해 통화 설정을 사용하거나 사용하지 않도록 설정합니다.
- **meetingAttachmentFileClick** - 모임 첨부 파일 항목을 클릭합니다.
- **meetingAttachmentFileOptions** - 모임 첨부 파일 항목 옵션을 클릭합니다.
- **meetingAttachmentSeeMoreClick** - 모임 첨부 파일 자세히 보기 버튼을 클릭합니다.
- **meetingDetailCalendarList** - calendarList에서 선택한 모임 세부 정보 페이지 또는 모임 세부 정보 페이지에서 **세부 정보** 탭을 선택합니다.
- **meetingDetailChatWithParticipants** - 모임 세부 정보 페이지에서 참가자와 채팅합니다.
- **meetingDetailDeleteMeetingforSelf** - 자신의 모임 세부 정보 페이지에서 모임을 삭제합니다.
- **meetingDetailJoin** - 모임 세부 정보 페이지에서 **모임 참가** 단추가 선택됩니다.
- **meetingDetailParticipants** - 모임 세부 정보 페이지에서 모든 참가자를 확인합니다.
- **meetingDetailScheduledMeeting** - 예약된 모임 개체 (**…**)에서 선택한 모임 세부 정보 페이지 또는 예약된 모임의 **세부 정보** 탭을 선택합니다.
- **meetingDetailSearchParticipants** - 모임 일정에서 모임 참가자 **검색** 을 선택합니다.
- **meetingInsightFileClick** - 모임 관련 파일 항목을 클릭합니다.
- **meetingInsightFileLocatorClick** - 모임 관련 콘텐츠 로케이터 팁 버튼을 클릭합니다.
- **meetingInsightFileOptions** - 모임 관련 파일 항목 옵션을 클릭합니다.
- **meetingInsightSeeMoreClick** - 모임 관련 콘텐츠 자세히 보기 버튼을 클릭합니다.
- **meetingJoinLeave** - 탭한 상태로 두기 -> **참가** 단추를 탭한 후 **x** 를 탭합니다.
- **meetingJoinNow** -  **지금 VOIP에 참가** 가 선택됩니다.
- **meetingJoinNowWithCallMe** - 사용자가 **전화** 를 사용하여 모임에 참가합니다.
- **meetingJoinNowWithPSTN** - 사용자가 전화 접속으로 모임에 참가합니다.
- **meetingLeaveChat** - 채팅에서 나갑니다.
- **meetingMuteChat** - 채팅을 음소거합니다.
- **meetingNotesCreatedInChatLink** - 치클릿에서 **만들어진 모임 메모** 는 비공개 모임 채팅 또는 채널 모임 채팅에서 선택됩니다.
- **meetingNotesMentionCharLink** - @멘션 링크는 비공개 모임 채팅에서 선택됩니다.
- **meetingNotesMentionChatLink** - @멘션 링크는 채널 모임 채팅에서 선택됩니다.
- **meetingNotesTabEntryPoint** - **모임 메모** 탭은 비공개 모임 또는 채널에서 선택됩니다.
- **meetingNotificationSettingsAccepted** - 알림 설정 옵션이 수락 전용으로 변경되었습니다.
- **meetingNotificationSettingsAll** - 알림 설정 옵션이 모두로 변경되었습니다.
- **meetingNotificationSettingsNone** - 알림 설정 옵션이 없음으로 변경되었습니다.
- **messagePriority_select** - 메시지 우선 순위 진입점이 선택됩니다.
- **messageSeeOriginal** - 사용자가 번역된 메시지를 원래대로 되돌립니다.
- **meetingSeeParticipantsChatDetails** - 모든 참가자를 봅니다.
- **memberListLoadMore** - 아래로 스크롤하여 내용을 더 로드합니다.
- **messagedEditMessage** - 사용자가 메시지를 편집합니다.
- **messageShareMessage** - 메시지를 공유합니다.
- **messageTranslate** - 사용자가 메시지를 번역합니다.
- **messageUnabletoEdit** - 사용자가 메시지를 편집할 수 없습니다.
- **meetingUserAnonB2B** - 익명의 B2B가 모임에 참가했습니다.
- **meetingUserAnonB2C** - 익명의 B2C가 모임에 참가했습니다.
- **meetingUserDialIn** - PSTN(전화 접속) 사용자가 모임에 참가했습니다.
- **meetingUserDialOut** - PSTN 콜백 사용자가 모임에 참가했습니다.
- **meetingUserFederated** - 페더레이션 사용자가 모임에 참가했습니다.
- **meetingUserFreemium** - Freemium 사용자가 모임에 참가했습니다.
- **meetingUserGuest** - 게스트 사용자가 모임에 참가했습니다.
- **meetingUserTenant** - 테넌트 내 사용자가 모임에 참가했습니다.
- **messageCopyMessage** - 메시지를 복사합니다.
- **messageDelete** - 메시지를 삭제합니다.
- **messageEditMessage** - 메시지를 편집합니다.
- **messageForwardMessage** - 사용자가 메시지 컨텍스트 메뉴에서 전달 진입점을 선택합니다.
- **messageLike/messageUnlike** - 좋아요 또는 좋아요 취소 메시지.
- **messageMuteSender** - 발신자를 음소거 또는 음소거 해제합니다.
- **messageLike** - 커넥터 카드와 같습니다.  앱 관련 데이터로 기존 원격 분석을 사용합니다.
- **messageScheduledMeeting** - 선택된 채널의 모임 개체입니다(예약된 개체뿐만 아니라).
- **messageTriggered** - 메시지에 대한 알림이 트리거되는 경우입니다.
- **micPermissionCancel** - 마이크 권한 대화 상자에서 **취소** 가 선택됩니다.
- **micPermissionGoToSettings** - 사용자가 마이크 권한 대화 상자에서 설정으로 이동합니다.
- **MicrosoftWhiteboardClicked** - Microsoft 화이트보드는 **채널 파일** 탭 또는 **모임 채팅 파일** 탭에서 선택됩니다.
- **moreOptionsClicked** - 작업 항목 편집기 화면에서 오른쪽 상단의 **...** 메뉴를 선택할 때 트리거됩니다.
- **moveTaskClicked** - 옵션 내 작업 항목 추가 옵션 목록.
- **multiCallEndFromUFD** - 사용자가 다중 통화 시나리오에서 대기 중인 통화를 종료하는 횟수입니다.
- **multiCallResumeFromUFD** - 사용자가 대기 중인 통화를 계속하기 위해 선택한 횟수입니다.
- **multiCallSwitch** - 사용자가 통화 전환 옵션을 선택하고 대기 중인 통화 목록을 표시하는 횟수입니다.
- **multipleAccounts** - 사용자의 계정 수입니다.
- **multipleTenants** - 계정당 테넌트의 수입니다.
- **mute** - 채팅을 음소거합니다.
- **muteOnWhiteboard** - 사용자가 화이트보드 화면에서 음소거 또는 음소거 해제합니다.
- **muteParticipant** - 참가자를 음소거합니다(작업 시트로 이동).
- **my_location_button_clicked** - 사용자가 **내 위치** 단추를 선택하여 자신의 위치를 지도 중심에 둡니다.
- **my_location_clicked** - 사용자가 지도에서 **파란색 점** 을 선택하여 자신의 위치를 지도 중심에 둡니다.
- **myShiftPickerClicked** - 전송 중인 요청은 바꾸기 또는 제안인 경우에만 기록됩니다. **My Shift** 선택기가 선택됩니다.
- **nameGroupChat** - 이름 그룹 채팅입니다.
- **nativeTimeClockBreak** - 출퇴근 시간기록계의 휴식 시간입니다.
- **nativeChatLink** - 네이티브 채팅에 대한 링크가 선택됩니다.
- **navActivity**- 활동 피드 페이지로 이동합니다.

- **navBookmark** - 사용자가 하단 표시줄 또는 앱 트레이에서 **저장됨** 탭 또는 앱으로 이동합니다.
- **navCalendar** - 사용자가 일정으로 이동하는지 측정합니다.
- **navCallingSettings** - 사용자가 통화 설정으로 이동합니다.
- **navCalls** - **통화** 탭을 탭합니다.
- **navCamera** - 사용자가 하단 표시줄 또는 앱 트레이에서 **카메라** 탭 또는 앱으로 이동합니다.
- **navChat** - 사용자가 하단 표시줄 또는 앱 트레이에서 **채팅** 탭 또는 앱으로 이동합니다.
- **navContacts** - 사용자가 하단 표시줄 또는 앱 트레이에서 **연락처** 또는 **피플** 탭, 혹은 앱으로 이동합니다.
- **navDashboardTab** - 사용자가 대화 내에서 **대시보드** 탭으로 이동합니다.
- **navDynamics365** - Dynamics365 앱이 열릴 때 트리거됩니다.
- **navFiles** - 파일 앱이 선택되면 사용자가 앱 트레이에서 파일 앱을 시작할 수 있는지 추적합니다(iOS).
- **navFilesTab** - 파일 앱이 선택되면 사용자가 하단 탐색 모음에서 파일 앱을 시작할 수 있는지 추적합니다(iOS).
- **navMeetings** - **일정** 탭을 탭합니다.
- **navNotes** - 메모 앱이 열릴 때 트리거됩니다.
- **navOrganization** - 조직 앱이 열릴 때 트리거됩니다.
- **navOrgChart** - Orgchahrt 앱이 열릴 때 트리거됩니다.
- **navPeople** - 피플 앱이 열릴 때 이벤트가 트리거됩니다.
- **navPeopleSettings** - 설정 메뉴에서 **피플** 범주로 이동할 때 트리거됩니다.
- **navPersonalFiles** - 파일 앱이 선택되면 사용자가 하단 탐색 모음에서 파일 앱을 시작할 수 있는지 추적합니다(Android).
- **navPhotoTab** - **사진** 탭입니다.
- **navSaved** - 사용자가 하단 표시줄 또는 앱 트레이에서 **저장됨** 탭 또는 앱으로 이동합니다.
- **navSelectPlan** - 사용자가 홈 보기에서 탐색할 공유 플랜을 선택한 경우입니다.
- **navSelectPersonalList** - 사용자가 홈 보기에서 탐색할 개인 플랜을 선택한 경우입니다.
- **navSelectSmartList** - 사용자가 홈 보기에서 탐색할 스마트 플랜을 선택한 경우입니다.
- **navTasks** - 작업 앱이 열릴 때 트리거됩니다.
- **navTeams** - **모두 보기** 를 탭합니다.
- **navVideocamera** - 사용자 하단 표시줄 또는 앱 트레이의 **카메라** 탭 또는 앱으로 이동합니다.
- **navVideoTab** - **비디오** 탭입니다.
- **navVoicemail** - 사용자가 음성 사서함 페이지로 이동합니다.
- **navWalkieTalkie** - 사용자가 워키 토키 앱을 열었습니다.
- **navWiki** - Wiki 앱이 열릴 때 트리거됩니다.
- **newChat** - 사용자가 채팅을 만듭니다.
- **newCall** - **새 통화** 단추를 탭합니다.
- **newCallDialPad** - 탭에서 **다이얼패드** 단추를 탭합니다.
- **newCallPeople** - 탭에서 **피플** 단추를 탭합니다.
- **noBGActivityDetected** - 백그라운드 활동 실패에 대한 임계값을 초과합니다.
- **notBlockedDevice** - 사용자가 30일 이내에 백그라운드 활동 실패에 대한 임계값에 도달하지 않습니다.
- **notNow** - 미리 알림에서 **나중에** 가 선택됩니다.
- **notNowUpdate** - UpdateDefer.
- **notificationNavChannelConversation** - 채널 대화에 대한 알림을 사용하여 앱을 시작합니다.
- **notificationNavChannelThreadConversation** - 채널 대화에서 특정 메시지에 대한 알림을 사용하여 앱을 시작합니다.
- **notificationSettingTurnedOff** - Teams Android 앱에 대한 푸시 알림을 끕니다.
- **notificationNavPreCall** - 사용자가 선택에 있어 사전 통화 화면으로 이동하는 모임 시작 알림을 받습니다.
- **ocvFeedback** - OCV 피드백 양식의 성능과 관련됩니다.
- **ocvFormCancelled** - OCV 피드백 양식이 취소되고 사용자가 앱으로 돌아올 때 전송되는 이벤트입니다.
- **ocvFormOpened** - OCV 양식이 열릴 때 전송되는 이벤트입니다.
- **ocvFormSubmit** - OCV 피드백 양식에서 사용자가 제출을 클릭할 때 전송되는 이벤트입니다.
- **offerRecipientClicked** - 전송 중인 요청이 제안인 경우에만 기록됩니다. 사용자가 팀 구성원 선택기에 들어가서 교대 근무를 제안합니다. 여기서 제안은 휴가 근무 일정을 의미합니다.
- **offerSwapShiftFromL1** -사용자가 교대 근무 목록에서 제공하거나 바꾸려는 교대 근무 유형입니다. iOS 작업은 **SwipedRight** 이고 Android 작업은 **LongPressed** 입니다.
- **offerSwapShiftFromL1Triggered** - 사용자가 다른 사용자와 교대 근무를 바꾸도록 제안합니다.
- **officeLens** - 앱이 officeLens 카메라 기능을 시작할 때 다음과 같은 경우 실행합니다.
  - 사용자가 메시지에 사진 첨부를 시도합니다.
  - 사용자가 사진을 찍고 갤러리에 직접 업로드를 시도합니다.
- **officeLens or cameraImage**- 선택한 카메라 사진-표준 카메라 또는 사무실 렌즈.
- **onBackClicked** - 페이지 뒤로 이동하기 위해 매번 뒤로 화살표를 선택하는 경우입니다.
- **oneNote** - 사용자가 OneNote 앱을 열 때입니다.
- **open** - 알림 설정 탭입니다.
- **open edit** - Wiki 사용 원격 분석 - 사용자가 wiki 편집을 선택합니다.
- **openApp** - 개인 앱을 엽니다.
- **openAppDrawer** - 앱 서랍을 열려면 하단 표시줄의 **자세히** 를 선택합니다.
- **openEditMeetingForm** - 모임 세부 정보 페이지에서 **편집** 단추가 선택됩니다.
- **openFile** - 도움이 되는 경우:
  - 파일을 채팅에서 성공적으로 열 수 있었는지 식별합니다.
  - 파일을 파일 목록에서 열 수 있었는지 식별합니다.
  - OneDrive 목록에서 파일을 열 수 있는지 확인합니다.
  - 채널 목록에서 열린 파일을 열 수 있는지 식별합니다.
  - 그룹 채팅에서 파일을 열 수 있는지 확인합니다.
  - 파일 앱에서 파일을 성공적으로 열 수 있는지 확인합니다.
  - 치클릿에서 메시지 파일을 성공적으로 열 수 있는지 확인합니다.
  - 최근 목록의 파일에서 성공적으로 열 수 있는지 확인합니다.
  - 파일 목록에서 성공적으로 열 수 있는지 확인합니다.
  - 메시지 파일 치클릿에서 파일을 열 수 있는지 확인합니다.
  - 파일 목록에서 파일을 성공적으로 열 수 있는지 확인니다.
- **openInAppClicked** -옵션 내 작업 항목 추가 옵션 목록으로 개인 작업에만 사용할 수 있습니다.
- **opensCalendarView** - **일정** 탭에서 **교대 근무 열기** 를 탭합니다.
- **openContactCard** - 사용자가 **연락처** 아이콘 또는 피플 앱의 연락처를 탭하여 해당 연락처의 프로필 카드를 시작합니다.
- **openContactCard_ReactionSummary** - 반응 요약 페이지에서 연락처 카드로 이동합니다.
- **openFileInApp** - 사용자가 Teams 내부와 비교하여 Teams 외부 파일을 열기로 선택했는지 식별하도록 돕습니다.
- **openHamburgerMenu** - 설정, 현재 상태 및 테넌트 전환기에 액세스를 위한 사이드 메뉴를 열기 위해 **햄버거** 아이콘(왼쪽 상단)이 선택됩니다.
- **openInStream** - Stream에서 비디오를 엽니다.
- **openMeetingDetails** - 특정 모임의 모임 세부 정보 열기 또는 모임 세부 정보 페이지 열기입니다.
- **openModalityPicker** - X = ChatsAndChannels는 채팅 및 채널을 위한 것입니다.
- **openNewMeetingForm** - 개인 하위 작업이 성공적으로 업데이트되었는지 확인합니다.
- **openNewMeetingForm** - 새 모임을 설정하는 동안 스케줄러를 엽니다.
- **openPhotoLibrary** - 사진 라이브러리를 선택합니다.
- **openQuietDays** - 조용한 날 페이지로 이동합니다.
- **openQuietHours** - 방해 금지 모드 페이지로 이동합니다.
- **openReactionHoverBubble** - 반응 요약 페이지에서 **반응 추가** 단추를 누릅니다.
- **openReactionSummary** - 반응 요약 서랍을 호출합니다.
- **openSettingsSetUpInstructions** - 지침에서 **설정** 을 엽니다.
- **openSharedLink** - 사용자가 대시보드 링크 타일 또는 링크 갤러리에서 링크를 열 경우입니다.
- **openShiftsClicked** - **일정** 아이콘을 탭하는 사용자 수입니다.
- **orgChart - 할당된 AS 없음** - 조직도에 대한 기본 사용 원격 분석입니다.
- **pageEntered** - 사용자가 페이지를 입력했습니다.
- **parental_consent_grant** - 사용자가 MSFamily에서 미성년자에게 TFL의 실제 위치 기능을 사용하는 권한을 부여합니다.
- **parental_consent_remove** - 사용자가 MSFamily에서 미성년자에게 TFL의 실제 위치 기능을 사용하는 권한을 취소합니다.
- **pauseVoicemail** - 음성 사서함 항목에서 **일시 중지** 를 탭합니다.
- **peoplePickerInvoked** - 인물 선택기는 다음을 포함한 Teams 모바일의 7곳(이에 국한되지 않음)에서 사용됩니다.
  - 새 채팅 선택기.
  - 메시지 전달.
  - 모임에 참가자 추가.
- **personalAppNavBotChat** - 개인 앱 내에서 봇으로 이동합니다.
- **personalAppNavTab** - 개인 앱 내의 탭으로 이동합니다.
- **photoLibraryPicker** - 이미지 선택기 내부의 **사진 라이브러리 열기** 를 탭합니다.
- **pickGalleryPhoto** - 갤러리에서 사진을 선택합니다.
- **pickParticipantChatDetails** - 목록에서 사용자를 선택합니다.
- **pickRecentPhoto** - 공유할 최근 이미지를 선택합니다.
- **pinChannel** - 채널을 고정하여 팀 및 채널 목록 위에 표시합니다.
- **pinSelf** - 작업 시트에 자신을 고정합니다.
- **pinUser** - 작업 시트에 사용자를 고정합니다.
- **play** - 녹음/녹화를 재생합니다.
- **playVoicemail** - 음성 사서함 항목에서 **재생** 을 탭합니다.
- **plusButtonClicked** - **더하기 단추**(**+**)를 선택합니다.
- **pptNextSlide** - 발표자 또는 비공개 보기로 다음 슬라이드로 이동합니다.
- **pptPreviousSlide** - 발표자 또는 비공개 보기로 이전 슬라이드로 이동합니다.
- **pptReturnToPresenter** - **라이브** 슬라이드(발표자와 모든 사람이 있는 슬라이드)로 이동합니다.
- **pptStopPresenting** - 발표를 중지합니다.
- **pptTakeControl** - 제어를 합니다.
- **preJoinAddRoom** - 사전 참가 드롭다운에서 **회의실 추가** 단추를 선택하고, **회의실 추가** 시나리오에서 **참가** 를 선택합니다.
- **preJoinAudioOff** - 사전 참가 드롭다운에서 **오디오 끄기** 단추가 선택됩니다.
- **preJoinAutoAddRoom** - 회의실이 근처에 있으면 **지금 참가** 가 선택됩니다.
- **preJoinBack** - **뒤로** 또는 **닫기** 단추가 선택됩니다.
- **preJoinDenied** - 사용자가 모임에 참가할 수 없습니다.
- **preJoinDeviceAudio** - 드롭다운에서 **장치 오디오를 사용하여 참가** 가 선택됩니다.
- **preJoinDialIn** - 사전 참가 드롭다운에서 **전화 걸기** 단추가 선택됩니다.
- **preJoinDialInCall** - 사용자가 사전 참가 요청에서 **전화 걸기** 를 확인합니다.
- **preJoinDialInCancel** - 사용자가 사전 참가 요청에서 **전화 걸기** 를 취소합니다.
- **preJoinDialOut** - 사전 참가 드롭다운에서 **콜백** 단추가 선택됩니다.
- **preJoinDialOutCall** - 사용자가 사전 참가에서 **콜백** 요청을 확인합니다.
- **preJoinDialOutCancel** - 사용자가 사전 참가에서 **콜백** 요청을 취소합니다.
- **preJoinPSTNOptions** - 사용자가 다른 참가 옵션에 대한 드롭다운을 선택합니다.
- **priorityChange** - 작업 목록을 보는 동안 우선 순위 필터가 적용될 때 트리거됩니다.
- **priorityPickerClicked** - 사용자가 작업 목록 필터 화면에서 우선 순위 필터 선택기로 이동할 때 트리거됩니다.
- **privateMeetingJoin** - 비공개 모임 채팅에서 **모임 참가** 단추를 탭합니다.
- **processInBG** - 백그라운드에서 수신 알림을 처리합니다(Android).
- **processInFG** - 포그라운드에서 수신 알림을 처리합니다(Android).
- **progressItemClicked** - 사용자가 작업에 대한 진행률 선택기를 성공적으로 열었는지 확인합니다.
- **promotedToPresenter** - 사용자가 참석자 승격 - 대화 상자의 **변경** 단추.
- **provideFeedbackDismiss** - 사용자가 앱을 좋아하지 않는 이유에 대한 피드백을 보낼 것인지 묻는 메시지를 해제합니다.
- **provideFeedbackNo** - 사용자가 앱을 좋아하지 않는 이유에 대한 피드백을 보낼 것인지 묻는 메시지에 아니요로 응답합니다.
- **provideFeedbackYes** - 사용자가 앱을 좋아하지 않는 이유에 대한 피드백을 보낼 것인지 묻는 메시지에 예로 응답합니다.
- **provideRatingDismiss** - 사용자가 앱을 좋아요라고 말한 후 앱 스토어에 대해 평가할 것인지 묻는 메시지를 해제합니다.
- **provideRatingNo** - 사용자가 앱을 좋아요라고 말한 후 앱 스토어에 대해 평가할 것인지 묻는 메시지에 아니요로 응답합니다.
- **provideRatingYes** - 사용자가 앱을 좋아요라고 말한 후 앱 스토어에 대해 평가할 것인지 묻는 메시지에 예로 응답합니다.
- **proximityPermissionDismissed** - 사용 권한 배너가 해제됩니다.
- **proximityPermissionGranted** - 팝업에 대한 권한이 부여됩니다.
- **proximityPermissionViewed** - 사용 권한 배너를 탭합니다.
- **pushNotification** - 이벤트가 트리거되는 경우:
  - 알림을 통해 시작합니다.
  - 푸시 알림이 선택됩니다.
  - 재연결 푸시 알림을 탭합니다.
  - **Reconnect failed** - 푸시 알림을 탭합니다.
- **quickNotificationAction** - 사용자가 알림에 대한 빠른 작업 응답 중 하나와 상호 작용하는 경우입니다(예: 푸시 알림에서 직접 메시지에 좋아요 기능).
- **quickSelectImagePicker** - 빠른 선택.
- **quickStartLiveEventJoin** - 사용자가 빠른 시작 라이브 이벤트에 참가합니다.
- **quietHoursValues** - 뒤로 단추 탐색에서 방해 금지 모드 상태를 캡쳐합니다.
- **quotedReplySent** - 사용자가 컨텍스트 유형으로 회신 메시지를 보냈습니다.
- **reactAngry_CM** - 컨텍스트 메뉴에서 화난 표정으로 반응합니다.
- **reactAngry_HB** - 풍선 가리키기에서 화난 표정으로 반응합니다.
- **reactHeart_CM** - 컨텍스트 메뉴에서 하트로 반응합니다.
- **reactHeart_HB** - 풍선 가리키기에서 하트로 반응합니다.
- **reactLaugh_CM** - 컨텍스트 메뉴에서 크게 웃는 표정으로 반응합니다.
- **reactLaugh_HB** - 풍선 가리키기에서 크게 웃는 표정으로 반응합니다.
- **reactLike_CM** - 컨텍스트 메뉴 또는 봇 메시지에서 좋아요로 반응합니다.
- **reactLike_doubleTap** - 두 번 탭하여 좋아요로 반응합니다.
- **reactLike_HB** - 풍선 가리키기에서 좋아요로 반응합니다.
- **reactSad_CM** - 컨텍스트 메뉴에서 슬픈 표정으로 반응합니다.
- **reactSad_HB** - 풍선 가리키기에서 슬픈 표정으로 반응합니다.
- **reactSurprised_CM** - 컨텍스트 메뉴에서 놀라운 표정으로 반응합니다.
- **reactSurprised_HB** - 풍선 가리키기에서 놀라운 표정으로 반응합니다.
- **reactRemoved_HB** - 사용자가 반응 요약 페이지 환경을 통해 반응을 제거하는 경우입니다.
- **readReceipts** - 사용자가 기능을 사용으로 설정합니다.
- **redeemInvite** - 인앱을 상환합니다.
- **Refresh캘린더 목록** -아래로 당겨 안건 보기를 새로 고칩니다.
- **refreshLinksGallery** - 사용자가 아래로 살짝 밀어 링크 갤러리를 새로 고치는 경우입니다.
- **removeAssignee** - (할당 선택기 보기에서 *x* 를 선택할 때 트리거되는 **assignmentRemoved** 와는 반대로) 할당 선택기 보기에서 할당자가 제거되었는지 확인합니다.
- **removeMeeting** - 취소된 모임의 모임 세부 정보 페이지에서 **일정에서 제거** 를 선택합니다.
- **removeParticipantFromEditMeeting** - 모임 세부 정보 페이지에서 **모임 편집** 을 선택한 후 참가자를 제거합니다.
- **removeParticipantFromNewMeeting** - 새 모임을 설정하는 동안 스케줄러 페이지에서 참가자를 제거합니다.
- **removeReplyObject** - 사용자가 작성에서 회신 개체를 제거했습니다.
- **removeUser** - (할당 선택기 보기에서 *x* 를 선택할 때 트리거되는 **assignmentRemoved** 와는 반대로) 할당 선택기 보기 내에서 할당자가 제거되었는지 확인합니다.
- **removeUser_CM** - 사용자가 채팅 참가자 목록을 통해 누군가를 제거하는 경우입니다.
- **removeUserConfirm** - 사용자가 사용자 제거 대화 상자를 확인했습니다.
- **removeUserContextMenu** - 사용자가 컨텍스트 메뉴를 통해 참가자를 제거했습니다.
- **removeUserSwipe** - 사용자가 살짝 밀어서 참가자를 제거했습니다.
- **reorderChannelItem** - 사용자가 고정된 채널을 다시 정렬합니다.
- **reportAbuseConfirmation** - 사용자가 확인 화면에서 **완료** 단추를 선택한 경우입니다.
- **reportAbuseOpen** - 컨텍스트 메뉴에서 **우려 사항 신고** 단추가 선택된 횟수입니다.
- **reportAbuseSend** - 사용자가 **보고서** 단추를 선택한 경우, 원격 분석은 선택한 보고서 유형을 저장해야합니다.
- **replyChain** - 회신 체인(스레드)에서 **새 메시지** 단추 또는 텍스트 상자를 선택합니다.
- **replyChannel** - 채널에서 **회신** 단추를 선택합니다.
- **replyNavigation** - 참조된 게시물로 이동하기 위해 회신 개체가 선택되었습니다.
- **replySendMessage** - 채널 회신을 보냅니다.
- **replyViaMsgOptions** - 사용자가 컨텍스트 메뉴를 통해 회신을 시작했습니다.
- **replyViaSwipe** - 사용자가 살짝 밀어 회신을 시작했습니다.
- **requestActedOn** - 관리자가 열린 교대 근무 요청에 대해 조치를 취할 때 트리거됩니다.
- **requestActionClicked** - 예를 들면, 교대 근무 요청이 선택되어 사용자가 작업을 요청할 경우입니다(FLW(일선 직원) 관리자 보기 또는 일선 직원).
- **requestDetailsClicked** - 교대 근무 요청을 선택한 경우입니다(FLW(일선 직원) 관리자 보기 또는 일선 직원).
- **requestJoinTeam** - **요청** 단추를 눌렀습니다.
- **requestSent** - 요청이 전송되었는지를 기록합니다.
- **requestToJoinTeam** - 팀 참가를 요청합니다(공개 또는 비공개).
- **requestToJoinTeamError** - 참가 요청에 오류가 있습니다.
- **requestTypeClicked** - 요청 선택기에서 사람들이 선택하는 요청 유형을 결정합니다.
- **resolveIssue** - 알림 문제 해결사 플라이아웃에서 **해결** 을 선택하여 차단 앱으로 이동합니다.
- **responseClicked** - 사용자가 응답 페이지를 선택합니다.
- **retryButtonClicked** - **다시 시도** 단추가 선택됩니다.
- **returnToMessage** - **돌아가기** 단추를 선택하여 메시지로 돌아갑니다.
- **runningLate** - 사용자가 늦습니다.
- **safeLink** - 링크가 안전한 것으로 확인되었습니다.
- **saveEditMeeting** - 모임을 업데이트한 후 모임 스케줄러 페이지에서 **저장** 단추를 선택합니다.
- **saveNewMeeting** - 모임 스케줄러 페이지에서 **저장** 단추를 선택합니다. 성공적으로 저장된 모임 및 클라이언트 측 또는 서비스 오류로 인해 만들지 못한 모임의 비율을 기록합니다.
- **savePlanClicked** - 앱의 기본 열기에서 **만들기** 가 새 계획 생성자에서 선택될 때 트리거됩니다.
- **scheduledMeetingJoin** - **모임 참가** 단추는 예약된 모임 개체에서 선택됩니다.
- **scrollCalendarList** - 일정에서 스크롤을 측정합니다.
- **scrollDatePicker** - 일정 날짜 선택 컨트롤을 스크롤합니다.
- **searchAbandoned** - 검색이 중단되었는지 확인합니다.
- **searchCancelled** - 다음 경우를 확인:
  - 검색이 성공했거나 사용자가 검색을 중단한 경우입니다.
  - 검색 쿼리가 성공한 경우입니다.
- **searchContacts** - 통화 목록에서 검색합니다.
- **searchIcon** - 다음을 확인:
  - 검색이 트리거될 수 있는 경우입니다.
  - 검색 트리거의 소스를 확인합니다.
  - 관련 결과가 성공적으로 발견된 경우입니다.
- **searchInitiated** - 검색을 트리거할 수 있는지 여부와 검색 트리거의 소스를 결정합니다.
- **searchMeetingParticipants** - 스케줄러 양식 내에서 추가할 참가자를 검색합니다. 만들어진 약속 수 대 모임 수를 구분합니다.
- **searchResultsClicked** - 다음을 확인:
  - 관련 결과를 성공적으로 찾을 수 있는 경우.
  - 검색 결과가 개별 도메인와 비교하여 모든 탭에서 나온 경우.
- **searchTab** - 다음을 확인:
  - 사람, 채팅, 메시지 및 파일에 대한 검색 결과의 도메인 정보.
  - 검색 결과가 개별 도메인와 비교하여 모든 탭에서 나온 경우.
- **searchTabClicked** - 다음을 확인:
  - 사람, 채팅, 메시지 및 파일에 대한 검색 결과의 도메인 정보.
  - 관련 결과가 성공적으로 발견된 경우.
- **seeAllMeetingParticipants** - 모임 세부 정보 페이지에서 **모두 보기** 를 선택하거나 모든 참가자를 봅니다. 일정 모임 세부 정보가 중요한 역할을하는 일정 유입 경로에서 사용자 데이터를 기록하는 데, 이는 전화 접속, Teams 모임, 참석 여부 알림 요청 등에 대한 선택의 유효성을 검사하는 데 도움을 줍니다.
- **seeMeetingDescription** - 모임 세부 정보 페이지를 열거나 모임 세부 정보 페이지의 모임 설명에서 **자세히 보기** 를 선택합니다. 데이터는 일정 유입 경로를 거쳐 기록되며 일정 모임 세부 정보가 중요한 역할을 하는 데, 이는 전화 접속, Teams 모임, 참석 여부 알림 요청 등에 대한 선택의 유효성을 검사하는 데 도움을 줍니다.
- **seeRsvpMeetingOptions** - 참석 여부 알림 요청 팝업에서 **주최자에게 알림** 을 선택하거나 모임 세부 정보 페이지에서 **참석 여부 알림 요청** 옵션을 선택합니다.
- **selectActivityType** - 피드 항목에서 선택한 제스처를 캡처합니다.
- **selectCalendarDate** - 일정 날짜 선택기 컨트롤에서 특정 날짜를 선택합니다.
- **selectDevice** - 디스플레이 앱에서 특정 장치를 선택합니다.
- **selectGeneralSetting** - 일반 설정으로 이동합니다.
- **selection** - 장치 연락처가 선택되었거나 회사 연락처가 선택되었습니다.
- **selectMeetingChicklet** | 모임.
- **selectMeetingRsvpOption** - **참석 여부 알림 요청** 단추를 선택하여 옵션을 선택합니다.
- **selectMeetingRsvpOptions** - **참석 여부 알림 요청** 단추를 선택하여 옵션을 선택합니다.
- **selectPersonalList** - 사용자가 개인 작업 목록을 탭하여 성공적으로 탐색했는지 확인합니다.
- **selectPlannerList** - 사용자가 공유 작업 목록을 탭하여 성공적으로 탐색했는지 확인합니다.
- **selectSettingOption** - 햄버거 메뉴에서 **설정** 탭으로 이동합니다.
- **selectTheme** - 어두운 테마를 사용합니다.
- **selectUser** - 작업 담당자가 성공적으로 선택되었는지 확인합니다.
- **selfLongPress** - 자신을 길게 누릅니다.
- **Send_earlycancelledCQF** - 사용자가 CQF 조기 취소 통화 양식에 대한 피드백을 제출합니다.
- **send_map_pin_clicked** - 사용자가 정적 위치를 보냅니다.
- **Send_ratemycallCQF** - 사용자가 내 통화 양식 CQF 평가에 대한 피드백을 제출합니다.
- **Send_ratemyliveeventCQF** - 사용자가 내 라이브 이벤트 양식 CQF 평가에 대한 피드백을 제출합니다.
- **sendForward** - 사용자가 전달 선택기에서 전달 메시지 보내기를 확인합니다.
- **sendImage** - 이미지를 보냅니다.
- **sendLocation** - 위치를 알립니다.
- **sendMsg** - 회신에서 **전송** 을 선택합니다.
- **sendRequestBulkClicked** - 이는 각 대량 요청 전송에 대해 한 번씩 기록됩니다.
- **sendRequestClicked** - **교대 근무 요청 전송됨** 이 선택됩니다.
- **sendVoiceMessage** - **녹화/녹음** 단추가 릴리스됩니다.
- **Setting/Dismiss** - 장치 연락처 설정입니다.
- **settingsNavReadReceiptNotice** - 사용자가 기능 공지에서 설정으로 이동했습니다.
- **settingsOpened** - 이는 사용자의 장치 시간대가 팀 시간대와 일치하지 않고 사용자가 설정으로 이동할 때 트리거됩니다.
- **shareFile** - **공유 파일** 이 선택될 때 트리거됩니다. 또한 다음 사항을 확인하는 데 도움이 됩니다:
  - 사용자가 파일 공유 작업을 시작할 수 있었습니다.
  - 사용자가 파일을 성공적으로 공유할 수 있습니다.
- **shareHistory** - 공유 기록 선택기를 선택했습니다.
- **shareInto** - 사용자가 다른 앱의 항목을 Teams로 공유합니다.
- **sharePlanToChat** - 공유 목록은 수동으로 작업 앱에서 치클릿으로 그룹 채팅에 공유되며, 백엔드 메시징 서비스를 통해 전송된 치클릿을 확인합니다.
- **sharePPTFromChannels** - **Teams 및 채널** 이 선택됩니다.
- **sharePPTFromOneDrive** - **OneDrive** 가 선택됩니다.
- **shareRecording** - 녹음/녹화를 공유합니다.
- **shareScreen** - 화면 공유를 시작하거나 중지합니다.
- **shareShift** - 교대 근무를 공유할 때 제공되는 정보입니다.
- **shareShiftsClicked** - 열린 교대 근무의 세부 정보입니다.
- **shareTray** - **공유…** 가 작업 시트에서 선택됩니다.
- **shiftAssigneeClicked** - 교대 근무 일정 보기에서 특정 교대 근무 세부 정보를 보여줍니다.
- **shiftDetails** - 이를 통해 교대 근무의 세부 정보를 볼 수 있습니다.
- **shiftDetailsCalendar** - 사용자가 교대 근무 세부 정보로 이동합니다.
- **shiftDetailsMyShifts** - **일정** 탭에서 **일정** 을 탭합니다.
- **shiftDetailsTodaysCoworkers** - 시계 화면에서 **시작** 또는 **휴식 종료** 단추가 선택됩니다.
- **shortCircuitContactCount** - 연락처 가져오기에서 받은 주소록과 일치하는 단락된 연락처의 수입니다.
- **showBanner** - **WiFi 연결됨, 인터넷 없음** 배너가 나타나는 횟수입니다.
- **showCard** - 카드 단추를 탭합니다. 카드는 키 플랫폼 구조이며 플랫폼 사용을 이해하고 클라이언트 측에서 발생할 수 있는 잠재적인 문제 확인을 위한 사용법 및 패턴 측정에 필요합니다.
- **shownReadReceiptNotice** - 사용자에게 설정 옵션과 함께 기능 알림이 표시됩니다.
- **signIn** - 환영 페이지에서 **로그인** 을 선택하거나 **로그인** 단추를 탭합니다.
- **signUp** - **무료 계정 만들기** 또는 **무료 가입** 이 선택됩니다.
- **simultaneousCallForward** - 트리거되는 경우:
  - 동시 착신 전환 대상이 설정됩니다.
  - 동시 착신 전환을 사용하도록 설정됩니다(전화 벨소리가 사용하도록 설정되고 벨소리도 설정됨).
- **skipVerificationForLink** - 사용자가 확인을 건너 뛰도록 선택했습니다.
- **smartReply** - 스마트 회신 토글 단추를 클릭합니다.
- **SMSSendMessage** - 사용자가 SMS 메시지를 보냅니다.
- **sortChanged** - 사용자가 작업 목록을 보는 동안 정렬 순서를 변경할 때 트리거됩니다.
- **startEditing** - **편집** 단추가 선택됩니다.
- **startPresentPhoto** - 사진 발표를 시작합니다.
- **startPresentVideo** - 비디오 발표를 시작합니다.
- **startPSTNCall** - 다음을 이유로 트리거됩니다.
  - 글로벌 검색의 PSTN 결과(인물 정보).
  - 장치 contactCard에서 건 PSTN 전화.
  - callList에서 건 PSTN 전화.
  - 다이얼패드를 사용하는 DialPSTN 번호.
- **startRecording** - 녹음/녹화를 시작합니다.
- **startVoicemailCall** - **음성 사서함 인사말 변경** 을 선택합니다.
- **static_place_selected** - 사용자가 지도를 끌어서 정적 장소를 선택합니다.
- **statusCheckBoxClicked** - 작업 항목이 완료되거나 완료되지 않은 경우 트리거됩니다.
- **statusMsgCancel** - 사용자가 상태 메시지 변경을 취소합니다.
- **statusMsgExpiry** - 사용자가 만료 시간을 설정합니다.
- **statusMsgSet** - 사용자가 새 상태 메시지를 설정합니다.
- **statusPageViaContactCard** - 사용자가 연락처 카드를 통해 상태 작성 환경을 입력합니다.
- **statusPageViaHamburger** - 사용자는 햄버거를 통해 상태 작성 환경에 들어갑니다.
- **stop_location_sharing_logout** - 사용자가 앱에서 로그 아웃합니다.
- **stopMeetingButton** - 사용자가 모임에 입장하지 않고 대기실을 떠난 횟수입니다.
- **stopPresentPhoto** - 사진 발표를 중지합니다.
- **stopPresentVideo** - 비디오 발표를 중지합니다.
- **stopRecording** - 녹음/녹화를 중지합니다.
- **structuredMeetingsBannerDismiss** - 사용자가 모임 역할에 대해 알려주는 배너를 해제합니다.
- **stuckOnConnectingDialInSelected** - 서랍에서 **전화 접속** 이 선택됩니다.
- **stuckOnConnectingRetrySelected** - 서랍에서 **다시 시도** 가 선택됩니다.
- **stuckOnConnectingShownDismissed** - 사용자가 서랍을 해제합니다.
- **suggested_place_selected** - 사용자가 제안된 장소를 선택하여 정적 위치를 공유합니다.
- **switchTeamAction** - 사용자는 출퇴근 시간기록계 내에서 팀을 전환합니다. 이는 사용자가 전환할 팀을 선택한 후에 실행해야합니다.
- **switchTeamsDialogTriggered** - 사용자가 **교대 근무** 탭을 봅니다.
- **tabActionCopyLink** - 사용자가 모바일에서 탭 복사 링크를 발견하고 사용하는 방법입니다.
- **tabActionMoreOptions** - 탭 내에서 줄임표(**...**) 사용법을 이해합니다.
- **tabActionOpenInBrowser** - 브라우저 사용에서 엽니다. 이는 사용자가 Teams 외부에서 탭을 여는 것을 선호하는지 이해하는 데 필요합니다.
- **tabActionOpenInBrowserFromTab** - 검색 가능성 및 사용법과 같은 더 많은 옵션을 보려면 탭 내에서 브라우저 사용에서 열기를 이해하도록 합니다.
- **tabActionOpenInTeams** - 사용 현황에서 엽니다. 이는 탭이 기본적으로 Teams에서 열리도록 설정할 수 있는지 이해하는 데 중요합니다.
- **tabActionRemove** - 삭제 옵션의 검색 가능성과 기능 사용을 이해합니다.
- **tabActionRename** - 검색 가능한 이름 변경 방법과 기능 사용을 이해합니다.
- **tabActionSetting, Android - fix** - 사용자가 모바일에서 탭 구성을 검색하고 사용하는 방법입니다.
- **table** - 테이블을 선택합니다.
- **tabListMoreOptions** - 탭에 대한 더 많은 옵션 사용을 이해합니다.
- **tabOpen** - 탭을 여는 데 성공했거나 탭을 여는 방식에 문제가있는 경우 기록합니다.
- **tabViewed** - 전송 중인 요청이 바꾸기인 경우에만 **팀 교대 근무** 선택기에 기록됩니다.
- **takePhoto** - 사진을 찍습니다.
- **takePhotoPicker** - 이미지 선택기 내에서 선택한 **사진 찍기** 입니다.
- **tapChicletExpand** - 사용자가 모바일에서 카드를 미리 보는 방법입니다.
- **tapDatePickerHandle** - 일정 날짜 선택기 컨트롤을 확장합니다.
- **tapSettings** - 모바일에서 앱을 재구성하는 사용자의 수입니다.
- **tasksAppLaunchAdaptiveCard** - 작업 앱은 그룹 채팅의 적응형 카드에서 열리며 IC3 서비스의 URL을 통해 앱 시작을 확인합니다.
- **tasksAppLaunchComposeExtension** - 작업 앱은 그룹 채팅의 작성 확장 프로그램에서 열리며 MT 서비스를 통해 앱 시작을 확인합니다.
- **tasksAppLaunchDashboard** - 작업 앱은 대시보드 타일 또는 특정 계획에서 열리며 MT 서비스를 통해 앱 시작을 확인합니다.
- **tasksAppLaunchDashboardSeeAll** - 대시보드에서 작업 앱이 열립니다. 대시보드에서 **모두 보기** 단추, MT 서비스를 통해 앱 시작을 확인합니다.
- **tasksAppLaunchDefault** - 작업 앱은 하단 서랍에서 열리며, MT 서비스를 통해 앱 시작을 확인합니다.
- **tabCalendarClicked** - 사용자가 팀 선택기에서 팀을 선택했습니다.
- **teamChannelChanged** - 사용자가 계획 목록에서 계획을 선택하고 탐색할 때 트리거됩니다. Aria가 아닌 appInsights로 전송됩니다.
- **teamCreate** - 사용자가 새 팀 만들기 옵션을 선택합니다.
- **teamEdit** - 사용자가 소유하거나 관리하는 팀의 일부 측면을 편집합니다.
- **teamNav** - 팀에 대한 보기 옵션입니다.
- **teamsDeviceCallResumed** - Bluetooth로 연결된 주변기기(휴대폰 도크)가 있는 사용자가 대기에서 통화를 다시 활성화합니다.
- **teamSelectedClicked** - 사용자가 작업표에 대해 **선택된 팀** 을 선택하는 경우입니다.
- **teamShiftPickerClicked** - 사용자가 새 중단 항목을 추가 하는 경우입니다. 사용자가 변경 사항을 저장하면 이벤트가 기록됩니다.
- **tenantSwitch** - 변환 테넌트에서. MTMA(다중 테넌트 및 다중 계정) 기능에 대한 기능 성공 메트릭은 문제를 사전에 식별하고 해결하여 원활한 전환 환경을 제공하는 데 도움이 됩니다.
- **tenantSwitchUnsupportedError** - 지원되지 않는 테넌트 오류입니다(사용자가 오류를 볼 때).. MTMA(다중 테넌트 및 다중 계정)에 대한 기능 성공 메트릭은 계정 또는 테넌트 전환 오류에 대한 원격 분석을 제공하므로 문제를 사전에 식별하고 수정하여 원활한 전환 환경을 제공할 수 있습니다.
- **timeClockClicked** - 사용자가 내 교대 근무 탭에서 **출퇴근 시간기록계** 단추를 선택합니다.
- **timeOffReasonClicked** - 휴가 사유가 인용된 이유를 확인합니다.
- **timesheetAddClicked** - 사용자가 휴식 시간 편집에 메모를 추가하는 경우입니다. 사용자가 변경 사항을 저장하면 이벤트가 기록됩니다.
 **timesheetBreakAdded** - 새로운 기록계 항목을 추가합니다. 변경 내용이 저장되면 이벤트가 기록됩니다.
- **timesheetBreakEdited** - 사용자가 작업표를 확인하는 경우입니다. 사용자가 모달에서 확인을 누르면 이벤트가 기록됩니다.
- **timesheetBreakNoteAdded** - 사용자가 작업표를 삭제하는 경우입니다. 사용자가 모달에서 삭제를 확인하는 경우 이벤트가 기록됩니다.
- **timesheetClockAdded** - 사용자가 작업표에 대해 편집을 선택한 경우입니다.
- **timesheetClockEdited** - 사용자가 편집된 작업표에서 저장을 선택한 경우입니다.
- **timesheetConfirmed** - 사용자가 작업표 편집 내용에 메모를 추가하는 경우입니다. 사용자가 변경 사항을 저장하면 이벤트가 기록됩니다.
- **timesheetDeleted** - 사용자가 교대 근무 미리 알림을 설정하거나 설정하지 않은 경우, 교대 근무 전에 사용자가 알림을 받기 원하는 시간(분)입니다.
- **timesheetEditClicked** - 사용자 구성 원격 분석입니다.
- **timesheetEditSaved** - 사용자는 사용자 프로필에서 작업 시간표를 탭하여 해당 사용자의 작업 시간표를 엽니다.
- **timesheetNoteAdded** - 승인된 휴가 요청을 봅니다.
- **titleChanged** - 작업 항목 제목이 변경될 때 트리거되고, 모든 문자가 변경될 때 트리거됩니다.
- **toast** - 인앱 알림이 선택됩니다.
- **toggleChannelsInChat** - 기능을 켜거나 끕니다. 통합 채팅 및 채널 환경에 대한 성공 메트릭을 제공합니다.
- **toggleClicked** - 토글이 선택됩니다.
- **transferNow** - 트리거되는 경우:
  - 사용자가 **전송** > **지금 전송** 을 선택합니다.
  - 전송 대상이 개인으로 설정됩니다.
  - 전송 대상이 전화 번호로 설정됩니다.
- **translateFailed** - 번역을 하지 못했습니다(오프라인 제외). 메시지 번역 기능에 대한 기능 성공 메트릭입니다.
- **unansweredCallForward** - 응답이 없는 착신 전환 대상이 설정됩니다. 또한 응답하지 않은 착신 전환을 사용하도록 설정됩니다(전화 벨소리를 사용하도록 설정되고 응답하지 않는 경우 사용할 수 있음).
- **unblockCaller** - 차단 해제:
  - 작업 시트의 연락처 또는 번호.
  - 연락처 카드의 연락처 또는 번호.
  - 설정시 번호
- **unblockChat** - 봇 채팅을 차단 해제합니다.
- **unpinChannel** - 채널을 고정 해제합니다.
- **unpinSelf** - 작업 시트에서 자신을 고정 해제합니다.
- **unpinUser** - 작업 시트에서 사용자를 고정 해제합니다.
- **unsafeLink** - 링크가 안전하지 않은 것으로 확인되었습니다.
- **updatePersonalTask** - 개인 작업이 성공적으로 업데이트되었는지 확인합니다.
- **updatePlaybackSpeedVoicemail** - 음성 사서함 재생 속도값이 변경됩니다.
- **updateTask** - 업데이트 작업 작업이 실패했는지 확인합니다.
- **updateTaskState** - 작업 상태가 업데이트되었는지 확인합니다. 작업.
- **upgrade** - **자세히** 메뉴에서 **업그레이드** 단추를 선택합니다.
- **uploadFile** - 사용자가 **장치에서 업로드** 를 선택합니다.
- **uploadSelectedFile** - 다음 상황에서 트리거됩니다.
  - 채널에서 파일을 성공적으로 업로드.
  - 채팅에서 파일을 성공적으로 업로드.
  - 회신 창에서 파일을 업로드.
  - 그룹 채팅에서 파일을 성공적으로 업로드.
  - 핵심 시나리오 사용.
  - 채널에서 업로드 시나리오 시작.
  - 채팅에서 업로드 시나리오 시작.
  - 채널에서 업로드 시나리오 종료의 시작.
  - **파일** 탭에 파일을 성공적으로 업로드.
  - 파일 업로드 중에 프롬프트가 표시되는 경우.
  - 선택한 파일이 성공적으로 업로드된 경우.
- **uploadSelectFile** - 성공적으로 파일을 선택합니다; 성공적으로 **파일 업로드** 단추를 선택합니다.
- **urgentMessageSelect** - 우선 순위 컨텍스트 메뉴에서 긴급 메시지를 선택합니다.
- **urgentMessageSend** - 긴급 메시지를 보냅니다.
- **url** - URL.
- **urlPreview** - URL 미리 보기.
- **urlPreviewAdd** - URL 미리 보기를 추가합니다.
- **urlPreviewOpen** - URL 미리 보기를 엽니다.
- **urlPreviewRemove** - URL 미리 보기를 제거했습니다.
- **userConfiguration** - 보류 중인 휴가 요청을 봅니다.
- **userJoinedViaShareLink** - 사용자가 링크에서 모임에 참가했습니다.
- **userLongPress** - 참가자를 길게 누릅니다.
- **userProfileOpened** - 사용자가 **사용자** 아이콘을 선택하여 사용자 프로필을 엽니다.
- userTimesheetOpened - 사용자가 사용자 프로필에서 작업 시간표를 선택하여 해당 사용자의 작업 시간표를 엽니다.
- **useWifiForAudioDialog** - 시스템이 메시지를 표시하는 동안 사용자는 **확인** 을 선택하고, 관리자가 휴대폰에서 오디오 및 화상 통화를 차단했습니다.
- **useWifiForVideoDialog** - 트리거되는 경우:
  - 시스템이 메시지를 표시하는 동안 **확인** 이 선택되고, 관리자가 셀룰러에서 화상 통화를 차단했습니다.
  - 모임에서 비디오 활성화를 시도하는 동안 관리자가 셀룰러에서 비디오를 차단했습니다.
  - 시스템이 메시지를 표시하는 동안 **확인** 이 선택되고 관리자가 셀룰러 모임에서 비디오를 차단했습니다.
- **videoUserDoubleTap** - 비디오 참가자에 두 번 탭합니다.
- **viewChannelMembers** - 채널 구성원 목록을 봅니다.
- **viewContactCard** - 다음에서 ContactCard가 선택됩니다:
  - callHistory 항목.
  - 음성 사서함 항목.
  - 통화 목록.
- **viewed** - 사용자가 페이지를 봅니다. 
- **viewFullAllDayMeetingList** - 모바일에서 안건 보기.
- **viewLobbyFromBanner** - 사용자가 알림 배너에서 **대기실 보기** 를 선택한 횟수입니다.
- **viewMeetingDetails** - 모임 세부 정보 페이지에서 **...** 를 선택합니다. 모바일 일정의 **자세히** 메뉴 사용과 관련이 있습니다.
- **viewMeetingOccurrence** - 되풀이 모임 인스턴스의 모임 세부 정보를 엽니다. 일정 모임 세부 정보가 중요한 역할을 하는 일정 유입 경로에서 사용자 데이터를 기록하는 원격 분석은 전화 접속 선택, Teams 모임, 참석 여부 알림 요청 등에 대한 유효성을 검사하는 데 도움을 줍니다.
- **viewMeetingSeries** - 다음 상황에서 모임 시리즈의 성공적인 렌더링을 기록합니다.
  - 인스턴스에서 시리즈 모임 세부 정보 페이지로 전환하는 경우.
  - 모임 세부 정보 페이지에서 **시리즈 보기** 를 선택하는 경우.
- **viewOrgChart** - 조직도에 대한 기본 사용 원격 분석입니다.
- **viewRequests** - **요청 보기** 단추를 누릅니다.
- **voiceDataCollectionOptOut** - 사용자가 배너를 클릭하여 모바일에서 녹음/녹화를 옵트아웃합니다.
- **voicemail - No AS Assigned** - 발표자가 음성 사서함 항목을 탭합니다.
- **whiteboardUsed** - 사용자가 화이트보드에 주석을 추가합니다(웹 보기의 모든 작업).
- **wiki - 할당된 AS 없음** - Wiki 사용 원격 분석.

### <a name="panelview"></a>PanelView

> [!NOTE]
> PanelView 이벤트의 속성에 대한 자세한 내용은 [panelview 이벤트를 사용하여 전송된 속성](#properties-sent-with-panelview-events)을 참조하세요.

- **fileDeleteFailed** - 파일 삭제 작업이 실패할 때 트리거됩니다.
- **fileDeleteSuccess** - 파일 삭제 작업이 성공할 때 트리거됩니다.
- **filePreview** - 다음 시나리오에서 트리거됩니다.
  - 공유 옵션이 파일 미리 보기 화면에서 선택된 경우
  - 복사 옵션이 파일 미리 보기 화면에서 선택된 경우
  - 다운로드 옵션이 파일 미리 보기 화면에서 선택된 경우
  - 파일 미리 보기가 로드된 경우
- **files** - 다음 시나리오에서 트리거됩니다.
  - Teams 앱 내에서 파일을 미리 볼 수 있는 경우
  - OneDrive 파일 화면에서 파일 업로드 옵션이 선택된 경우
  - 파일 미리 보기 화면에서 "링크 복사" 옵션이 선택된 경우
  - 파일 공유 화면이 해제된 경우
  - 파일 옵션 메뉴가 열리거나 이 메뉴의 옵션 중 하나가 매핑된 경우
  - "통화 중" 파일 화면이 열린 경우
  - 파일을 열기 위해 선택된 경우
- **filesChannel** - 채널 파일 화면이 열릴 때 트리거됩니다.
- **fileSources** - 파일 옵션 메뉴가 열리거나 이 메뉴의 옵션 중 하나가 매핑된 경우 트리거됩니다.
- **filesPersonal** - 파일 일괄 처리나 최근 파일 화면이 OneDrive에 로드될 때 트리거됩니다.
- **fileUploadDeleteTriggered** - 파일 첨부 파일이 삭제되거나 메시지 영역에서 첨부 해제될 때 트리거됩니다.
- **fileUploadFailed** - 파일 업로드 작업이 실패할 때 트리거됩니다.
- **fileUploadIndividualNotification** - 파일 업로드 알림 내용이 변경되거나 알림이 상호 작용할 때 트리거됩니다. 상호 작용에는 알림을 해제하기 위해 스위프하거나 알림을 누르는 등의 제스처가 포함될 수 있습니다.
- **fileUploadSuccess** - 파일 업로드 작업이 성공할 때 트리거됩니다.
- **fileUploadSummaryNotification** - 파일 업로드 요약 알림 내용이 변경되거나 알림이 상호 작용할 때 트리거됩니다. 상호 작용에는 알림을 해제하기 위해 스위프하거나 알림을 누르는 등의 제스처가 포함될 수 있습니다.
- **meetingFiles** - 모임 파일 알림 화면이 열릴 때 트리거됩니다.
- **navPersonalFiles** - 파일 화면 탬식이 수행될 때 트리거됩니다.

### <a name="scenario"></a>시나리오

> [!NOTE]
> PanelAction 이벤트의 속성에 대한 자세한 내용은 [panelaction 시나리오 이벤트를 사용하여 전송된 속성](#properties-sent-with-scenario-events)을 참조하세요.

- **chat_add_giphy** - Giphy GIF 렌더링 작업이 성공했는지 실패했는지 확인합니다.
- **cortanaError** Cortana의 오류 발생을 모니터링합니다.
- **cortanaView** - Cortana 캔버스 표시를 모니터링합니다.
- **cortanaRestart** Cortana의 다시 시작을 모니터링합니다.
- **cortanaSetNewConversation** Cortana에서 설정하는 새 대화를 모니터링합니다.
- **cortanaSpeechRecognization** Cortana 음성 인식 대기 시간을 모니터링합니다.
- **cortanaStart** Cortana의 백 엔드 시작을 모니터링합니다.
- **cortanaStartListening** Cortana의 의견 청취 시작을 모니터링합니다.
- **cortanaStopListening** Cortana의 의견 청취 중단을 모니터링합니다.
- **cortanaThinking** Cortana 상태의 숙고 중(서비스 응답 대기) 변경을 모니터링합니다.
- **cortanaTokenRefresh** 전경의 Cortana 토큰 새로 고침을 모니터링합니다.
- **cortanaWarmingUp** Cortana의 작동 준비 시작(Cortana는 열려 있지만 아직 토큰을 가져오는 중)을 모니터링합니다.
- **cortana_admin_policy_refresh** - Cortana의 관리 정책 새로 고침을 모니터링합니다.
- **cortana_background_token_refresh** - Cortana 토큰 새로 고침을 모니터링합니다.
- **cortana_initialization** - Cortana의 초기화 단계를 모니터링합니다.
- **cortana_sdk_events** - Cortana 전환 관련 이벤트를 모니터링합니다.
- **cortana_skill_action_execution** - Cortana의 작업 실행을 모니터링합니다.
- **cortana_skill_action_delay** - 작업 연기 시작을 확인합니다.
- **cortana_watchdog** - Cortana의 감시 복구 프로세스를 모니터링합니다.
- **create_default_plan_and_nav_to_view** - 기본 공유 작업 목록이 성공적으로 만들어졌는지 확인하고 사용자가 작업 후 결과 보기에 도달하는 데 걸린 시간을 확인합니다.
- **create_personal_plan_and_nav_to_view** - 개인 작업 목록을 성공적으로 만들고 사용자가 작업 후 결과 보기에 도달하는 데 걸린 시간을 확인합니다.
- **create_personal_task** - 개인 작업 항목이 성공적으로 만들어졌는지 확인합니다.
- **create_planner_plan_and_nav_to_view** - 공유 작업 목록이 성공적으로 만들어졌는지 확인하고 사용자가 작업 후 결과 보기에 도달하는 데 걸린 시간을 확인합니다.
- **create_planner_task** - 공유 작업 항목이 성공적으로 만들어졌는지 확인합니다.
- **forwardExistingAmsObject** 미디어 전달 작업이 성공했는지 실패했는지 확인합니다.
- **delete_personal_plan** - 개인 작업 목록이 성공적으로 삭제되었는지 확인합니다.
- **delete_personal_task** - 개인 작업 항목이 성공적으로 삭제되었는지 확인합니다.
- **delete_planner_plan** - 공유 작업 목록이 성공적으로 삭제되었는지 확인합니다.
- **delete_planner_task** - 공유 작업 항목이 성공적으로 삭제되었는지 확인합니다.
- **get_sender_sub_scenario** - 활동에서 발신인 하위 시나리오를 가져옵니다.
- **load_chat_plans_list** - 채팅의 계획 보기에 대한 계획자 계획을 성공적으로 가져 왔는지 확인합니다.
- **load_home_page** - 기본 홈 보기에 대한 개인 및 공유 작업 목록을 모두 성공적으로 가져왔는지 확인합니다.
- **load_personal_task_list** - 작업 목록 보기에 대한 개인 작업 목록의 작업을 성공적으로 가져왔는지 확인합니다.
- **load_shared_task_list** - 작업 목록 보기에 대한 공유 작업 목록의 작업을 성공적으로 가져왔는지 확인합니다.
- **load_smart_task_list** - 작업 목록 보기에 대한 스마트 작업 목록의 작업을 성공적으로 가져왔는지 확인합니다.
- **meetingAttachmentRender** - 모임 첨부 파일이 렌더링되는지 확인합니다.
- **meetingInsightFetch** - 모임 관련 콘텐츠 가져오기를 확인합니다.
- **meetingInsightLocatorRender** - 모임 관련 콘텐츠 로케이터 팁의 렌더링을 확인합니다.
- **meetingInsightRender** - 모임 관련 콘텐츠의 렌더링을 확인합니다.
- **meetingInsightVisible** - 모임 관련 콘텐츠의 시각적 표시 여부를 확인합니다.
- **open_image** 전체 화면 이미지 렌더링이 성공했는지 실패했는지 확인합니다.
- **rename_personal_plan** - 개인 작업 목록의 성공적인 이름 변경을 확인합니다.
- **rename_planner_plan** - 공유 작업 목록의 성공적인 이름 변경을 확인합니다.
- **save_image** 이미지 저장 작업이 성공했는지 실패했는지 확인합니다.
- **share_image** 이미지 공유 작업이 성공했는지 실패했는지 확인합니다.
- **smart_reply_enabled** - 현재 사용자에 대해 스마트 회신이 사용하도록 설정되어 있는지 확인합니다.
- **smart_reply_received** - 스마트 회신 제안이 수신되었는지 확인할 수 있습니다.
- **smart_reply_banned** - 현재 사용자에 대해 스마트 회신을 표시할 수 없는지 확인합니다.
- **update_planner_task_and_nav_to_view** - 공유 작업 항목의 성공적인 업데이트와 사용자가 작업 후 결과 보기에 도달하는 데 걸린 시간을 확인합니다.
- **update_personal_task_and_nav_to_view** - 개인 작업 항목의 성공적인 업데이트와 사용자가 후 결과 보기에 도달하는 데 걸린 시간을 확인합니다. 
- **updatePlannerTask** - 사용자가 공유 작업 목록에서 작업을 성공적으로 업데이트했는지 확인합니다.
- **upload_images** 이미지 업로드 작업이 성공했는지 실패했는지 확인합니다.
- **upload_voice_messages** 음성 메시지 업로드 작업이 성공했는지 실패했는지 확인합니다.
- **voiceMessageUpload** 음성 메시지 업로드 작업이 성공했는지 실패했는지 확인합니다.

## <a name="property-lists"></a>속성 목록

### <a name="properties-sent-with-all-events"></a>모든 이벤트와 함께 보낸 속성

| 속성 이름                    | 설명                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | 이벤트 생성 시간                                                |
| EventInfo_Name                   | 이벤트 이름 - 이벤트 유형을 구분하는 데 사용됨               |
| EventInfo_BaseType/name          | 이벤트 유형 - 이벤트에서 이벤트 유형을 구분하는 데 사용됨   |
| EventInfo_Source                 | 이벤트 생성 소스                                       |
| AppInfo_Language                 | 앱 언어                                                         |
| AppInfo_ETag                     | 사용자에 게 할당된 실험 ID                                     |
| DeviceInfo_OsBuild               | OS의 빌드 버전                                              |
| UserInfo_Mri                     | 사용자 ID 입력                                                       |
| Session_RunId                    | 세션 ID 유형                                                 |
| DeviceInfo_DetailModel           | 장치의 모델                                                  |
| UserInfo_TimeZone                | 사용자의 표준 시간대                                                |
| DeviceInfo_OsName                | 장치 OS 이름                                                       |
| DeviceInfo_NetworkProvider       | 장치 네트워크 공급자                                              |
| DeviceInfo_Model                 | 장치 모델                                                         |
| DeviceInfo_NetworkType           | 장치 네트워크 정보                                                  |
| UserInfo_Language                | 사용자 언어 - 앱 언어와 유사                              |
| client_ring/UserInfo_Ring        | 얼리어답터에게 기능을 릴리스하는 데 도움이 되는 사용자 링           |
| UserInfo_Id                      | 사용자 ID                                                              |
| UserInfo_TenantId                | 테넌트 ID                                                            |
| EventInfo_SdkVersion             | 이벤트 생성에 사용된 SDK 버전                               |
| DeviceInfo_Id                    | 장치 OS에서 제공하는 장치 ID                                      |
| eventpriority                    | 이벤트 우선 순위                                                 |
| DeviceInfo_Make                  | 장치 제조업체                                                  |
| AppInfo_Version                  | 앱 버전                                                   |
| DeviceInfo_OsVersion             | 장치 OS 버전                                                    |
| Session_Id/SessionId             | 요청의 세션 ID                                            |
| Session_Environment              | 세션 환경                                                  |
| isNetworkIssue                   | 요청을 처리하는 동안 네트워크 문제가 있는 경우 정보를 캡처 |
| UserRole                         | 테넌트의 사용자 역할                                                |
| Tenant_Model                     | 계정이 freemium 또는 기업 계정일 경우 캡쳐          |
| licenseType/UserInfo_LicenseType | 사용자에게 할당된 라이선스 유형                                    |
| UserLocale                       | 앱에 액세스되는 로캘                                |
| Intune_sdkVersion                | Intune SDK 버전                                            |
| Intune_sdkBundleVersion          | Intune SDK 상세 버전                                   |
| AppInfo_Environment              | 앱이 액세스되는 환경                         |

### <a name="properties-sent-with-panelaction-events"></a>panelaction 이벤트를 사용하여 보낸 속성

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
| Module_Summary        | 사용자 작업을 호스팅한 모듈 요약                      |
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

### <a name="properties-sent-with-panelview-events"></a>panelview 이벤트를 사용하여 보낸 속성

| Panel_Uri          | 사용자에게 전달된 패널의 Uri                   |
|--------------------|----------------------------------------------------------|
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

### <a name="properties-sent-with-scenario-events"></a>시나리오 이벤트와 함께 보낸 속성

| 속성 이름        | 설명 |
|----------------------|-------------|
| Scenario_Status      | 시나리오의 상태 - 중단/확인/오류 |
| Scenario_Step        | 시나리오에 서로 다른 여러 단계의 실패 지점이 있는 경우, 이 속성은 단계에 대한 세부 정보를 캡처합니다. |
| Scenario_StatusCode  | 속성은 시나리오 성공 또는 실패를 기반으로 시나리오의 상태 코드를 기록합니다. |

### <a name="properties-sent-with-trace-events"></a>추적 이벤트를 사용하여 보낸 속성

| 속성 이름 | 설명                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | 오류 문자열 및 오류가 발생했을 수 있는 원인에 대한 세부 정보를 포함합니다. |
