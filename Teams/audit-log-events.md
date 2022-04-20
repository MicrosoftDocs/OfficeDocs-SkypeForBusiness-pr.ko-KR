---
title: Microsoft Teams 감사 로그에서 이벤트 검색
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
description: Microsoft Purview 규정 준수 포털의 감사 로그에서 Microsoft Teams 데이터를 검색하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 744a18f2a8f7f2ed406853ef7efbc9842d0096f5
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922639"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Microsoft Teams 감사 로그에서 이벤트 검색

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

감사 로그는 Microsoft 365 서비스에서 특정 활동을 조사하는 데 도움이 될 수 있습니다. Microsoft Teams 감사되는 몇 가지 활동은 다음과 같습니다.

- 팀 만들기
- 팀 삭제
- 채널 추가됨
- 삭제된 채널
- 변경된 채널 설정

감사되는 Teams 활동의 전체 목록은 [Teams 활동](#teams-activities) 및 [Teams 활동의 교대 근무](#shifts-in-teams-activities)를 참조하세요.

> [!NOTE]
> 비공개 채널의 감사 이벤트도 팀 및 표준 채널에 대해 기록됩니다.

## <a name="turn-on-auditing-in-teams"></a>Teams 감사 켜기

감사 데이터를 살펴보려면 먼저 Microsoft Purview 규정 준수 포털에서 감사를 켜야 합니다. 자세한 내용은 [감사 설정 또는 해제를 참조하세요](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> 감사 데이터는 감사를 설정한 시점부터만 사용할 수 있습니다.

## <a name="retrieve-teams-data-from-the-audit-log"></a>감사 로그에서 Teams 데이터 검색

1. Teams 활동에 대한 감사 로그를 검색하려면 감사로 <https://compliance.microsoft.com> **이동하여 선택합니다.**

2. **검색** 페이지에서 감사하려는 활동, 날짜 및 사용자를 필터링합니다.

3. 추가 분석을 위해 결과를 Excel 내보냅니다.

단계별 지침은 [규정 준수 센터에서 감사 로그 검색을](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log) 참조하세요.

> [!IMPORTANT]
> 감사 데이터는 감사가 켜져 있는 경우에만 감사 로그에 표시됩니다.

감사 레코드가 유지되고 감사 로그에서 검색 가능한 기간은 Microsoft 365 또는 Office 365 구독, 특히 사용자에게 할당된 라이선스 유형에 따라 달라집니다. 자세한 내용은 [보안 & 준수 센터 서비스 설명을](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 참조하세요.

## <a name="tips-for-searching-the-audit-log"></a>감사 로그 검색을 위한 팁

다음은 감사 로그에서 Teams 활동을 검색하기 위한 팁입니다.

:::image type="content" alt-text="규정 준수 센터의 감사 로그 검색 페이지 스크린샷" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- 하나 이상의 활동 옆에 있는 확인란을 클릭하여 검색할 특정 활동을 선택할 수 있습니다. 활동을 선택한 경우 해당 활동을 클릭하여 선택을 취소할 수 있습니다. 검색 상자를 사용하여 입력한 키워드가 포함된 활동을 표시할 수도 있습니다.

  ![감사 로그 검색 페이지의 활동 드롭다운 목록 스크린샷](media/audit-log-search.png)

- cmdlet을 사용하여 실행되는 활동에 대한 이벤트를 표시하려면 **활동 목록의** **모든 활동에 대한 결과 표시** 를 선택합니다. 이러한 활동에 대한 작업의 이름을 알고 있는 경우 검색 상자에 입력하여 활동을 표시한 다음 선택합니다.

- 현재 검색 조건을 지우려면 **모두 지우** 기를 클릭합니다. 날짜 범위는 지난 7일의 기본값으로 돌아갑니다.

- 5,000개의 결과가 발견되면 검색 조건을 충족하는 이벤트가 5,000개 이상 있다고 가정할 수 있습니다. 검색 조건을 구체화하고 검색을 다시 실행하여 더 적은 결과를 반환하거나 **ExportDownload 모든 결과를 선택하여 모든 검색 결과를** **내보낼** >  수 있습니다. 감사 로그를 내보내는 단계별 지침은 [검색 결과를 파일로 내보내기를](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file) 참조하세요.

오디오 로그 검색을 사용하려면 [이 비디오를](https://www.youtube.com/embed/UBxaRySAxyE) 확인하세요. Teams 프로그램 관리자인 Ansuman Acharya에 합류하여 Teams 대한 감사 로그 검색을 수행하는 방법을 보여 줍니다.

## <a name="teams-activities"></a>Teams 활동

다음은 Microsoft 365 감사 로그의 Teams 사용자 및 관리자 활동에 대해 기록되는 모든 이벤트 목록입니다. 테이블에는 **활동** 열에 표시되는 친숙한 이름과 검색 결과를 내보낼 때 감사 레코드의 자세한 정보 및 CSV 파일에 표시되는 해당 작업의 이름이 포함됩니다.

|친숙한 이름  |작업 |설명 |
|:---------|:---------|:---------|
|팀에 봇 추가   |BotAddedToTeam        |사용자가 팀에 봇을 추가합니다.        |
|채널 추가됨   |ChannelAdded         |사용자가 팀에 채널을 추가합니다.         |
|커넥터 추가됨  |ConnectorAdded          |사용자가 채널에 커넥터를 추가합니다.        |
|Teams 모임 <sup>2</sup>에 대한 세부 정보 추가|MeetingDetail|Teams 모임에 참가할 시작 시간, 종료 시간 및 URL을 포함하여 모임에 대한 정보를 추가했습니다.|
|모임 참가자 <sup>2</sup>에 대한 추가 정보|MeetingParticipantDetail|Teams 각 참가자의 사용자 ID, 참가자가 모임에 참가한 시간 및 참가자가 모임을 떠난 시간을 포함하여 모임 참가자에 대한 정보를 추가했습니다.|
|멤버 추가됨    |MemberAdded         |팀 소유자는 팀, 채널 또는 그룹 채팅에 구성원을 추가합니다.         |
|추가된 탭    |TabAdded         |사용자가 채널에 탭을 추가합니다.        |
|변경된 채널 설정    |ChannelSettingChanged         |ChannelSettingChanged 작업은 팀 구성원이 다음 활동을 수행할 때 기록됩니다. 이러한 각 활동에 대해 변경된 설정에 대한 설명(괄호로 표시됨)은 감사 로그 검색 결과의 **항목** 열에 표시됩니다. <ul><li>팀 채널의 이름 변경(**채널 이름**)</li><li>팀 채널에 대한 설명 변경(**채널 설명**)</li> </ul>      |
|변경된 조직 설정   |TeamsTenantSettingChanged         |TeamsTenantSettingChanged 작업은 Microsoft 365 관리 센터 전역 관리자가 다음 활동을 수행할 때 기록됩니다. 이러한 활동은 조직 전체의 Teams 설정에 영향을 줍니다. 자세한 내용은 [조직의 Teams 설정 관리를 참조하세요](enable-features-office-365.md). <br>이러한 각 활동에 대해 변경된 설정에 대한 설명(괄호로 표시됨)이 감사 로그 검색 결과의 **항목** 열에 표시됩니다.<ul><li>조직(Microsoft Teams)에 대한 **Teams** 사용하거나 사용하지 않도록 설정합니다.</li><li>조직에 대한 Microsoft Teams 및 비즈니스용 Skype 간의 상호 운용성을 사용하거나 사용하지 않도록 **설정합니다(비즈니스용 Skype 상호 운용성**).</li><li>Microsoft Teams 클라이언트에서 조직도 보기를 사용하거나 사용하지 않도록 설정합니다(**조직도 보기**).</li><li>팀 구성원이 비공개 모임(**비공개 모임 일정**)을 예약하는 기능을 사용하거나 사용하지 않도록 설정합니다.</li><li>팀 구성원이 채널 모임(채널 **모임 일정**)을 예약하는 기능을 사용하거나 사용하지 않도록 설정합니다.</li><li>Teams 모임에서 화상 통화를 사용하거나 사용하지 않도록 설정합니다(**Skype 모임용 비디오**).</li><li>조직의 Microsoft Teams 모임에서 화면 공유를 사용하거나 사용하지 않도록 설정합니다(**Skype 모임의 화면 공유**).</li><li>애니메이션 이미지(Giphys라고 함)를 추가하여 대화(**애니메이션** 이미지)를 Teams 기능을 사용하거나 사용하지 않도록 설정합니다.</li><li>조직의 콘텐츠 등급 설정을 변경합니다(**콘텐츠 등급**). 콘텐츠 등급은 대화에 표시할 수 있는 애니메이션 이미지의 유형을 제한합니다.</li><li>팀 구성원이 인터넷에서 팀 대화(인터넷에서 사용자 지정 가능한 이미지)에 사용자 지정 가능한 이미지(사용자 지정 밈이라고 함)를 추가할 **수** 있는 기능을 사용하거나 사용하지 않도록 설정합니다.</li><li>팀 구성원이 편집 가능한 이미지(스티커라고 함)를 팀 대화(**편집 가능한** 이미지)에 추가할 수 있는 기능을 사용하거나 사용하지 않도록 설정합니다.</li><li>팀 구성원이 Microsoft Teams 채팅 및 채널(**조직 전체 봇)에서 봇** 을 사용하는 기능을 사용하거나 사용하지 않도록 설정합니다.</li><li>Microsoft Teams 특정 봇을 사용하도록 설정합니다. 여기에는 조직(개별 봇)에 대해 봇을 사용하도록 설정할 때 사용할 수 있는 도움말 봇을 Teams T-**봇** 이 포함되지 않습니다.</li><li>팀 구성원이 확장 또는 탭(**확장 또는 탭**)을 추가할 수 있는 기능을 사용하거나 사용하지 않도록 설정합니다.</li><li>Microsoft Teams(봇의 측면 로드)에 대한 독점 **봇의 사이드 로드를** 사용하거나 사용하지 않도록 설정합니다.</li><li>사용자가 Microsoft Teams 채널(**채널 전자 메일**)에 전자 메일 메시지를 보낼 수 있는 기능을 사용하거나 사용하지 않도록 설정합니다.</li></ul>|
|팀 구성원의 역할 변경    |MemberRoleChanged         |팀 소유자가 팀의 멤버 역할을 변경합니다. 다음 값은 사용자에게 할당된 역할 유형을 나타냅니다. <br><br>**1** - 멤버 역할을 나타냅니다.<br>**2** - 소유자 역할을 나타냅니다.<br>**3** - 게스트 역할을 나타냅니다.<br><br>멤버 속성에는 조직의 이름과 구성원의 전자 메일 주소도 포함됩니다.        |
|변경된 팀 설정    |TeamSettingChanged        |TeamSettingChanged 작업은 팀 소유자가 다음 활동을 수행할 때 기록됩니다. 이러한 각 활동에 대해 변경된 설정에 대한 설명(괄호로 표시됨)이 감사 로그 검색 결과의 **항목** 열에 표시됩니다.<ul><li>팀의 액세스 유형을 변경합니다. Teams 프라이빗 또는 퍼블릭(**팀 액세스 유형**)으로 설정할 수 있습니다. 팀이 비공개(기본 설정)인 경우 사용자는 초대를 통해서만 팀에 액세스할 수 있습니다. 팀이 공개되면 누구나 검색할 수 있습니다.</li><li>팀의 정보 분류를 변경합니다(**팀 분류**). 예를 들어 팀 데이터는 높은 비즈니스 영향, 중간 비즈니스 영향 또는 낮은 비즈니스 영향으로 분류할 수 있습니다.</li><li>팀 이름(**팀 이름**)을 변경합니다.</li><li>팀 설명을 변경합니다(**팀 설명**).</li><li>팀 설정이 변경되었습니다. 이러한 설정에 액세스하려면 팀 소유자가 팀을 마우스 오른쪽 단추로 클릭하고 **팀 관리를** 선택한 다음 **설정** 탭을 클릭할 수 있습니다. 이러한 활동의 경우 변경된 설정의 이름이 감사 로그 검색 결과의 **항목** 열에 표시됩니다.</li></ul>         |
|채팅 <sup>만들기 1, </sup> <sup>2</sup>|    ChatCreated|    Teams 채팅이 만들어졌습니다.|
|만든 팀    |TeamCreated         |사용자가 팀을 만듭니다.         |
|메시지 삭제됨  |MessageDeleted |채팅 또는 채널의 메시지가 삭제되었습니다.|
|모든 조직 앱 삭제|DeletedAllOrganizationApps           |카탈로그에서 모든 조직 앱을 삭제했습니다.     |
|삭제된 앱 |AppDeletedFromCatalog           |앱이 카탈로그에서 삭제되었습니다.     |
|삭제된 채널     |ChannelDeleted         |사용자가 팀에서 채널을 삭제합니다.         |
|삭제된 팀  |TeamDeleted            |팀 소유자가 팀을 삭제합니다.      |
|Teams URL 링크가 있는 메시지를 편집했습니다.     |MessageEditedHasLink         |사용자가 메시지를 편집하고 Teams URL 링크를 추가합니다.         |
|내보낸 메시지 <sup>1, </sup> <sup>2</sup> |    MessagesExported |채팅 또는 채널 메시지를 내보냅니다.|
|공유 채널3에 대한 초대의 유효성을 검사하지 못했습니다<sup>.</sup> | FailedValidation |사용자가 공유 채널에 대한 초대에 응답하지만 초대 유효성 검사에 실패했습니다. |
|가져온 채팅 <sup>1, </sup> <sup>2</sup>   |ChatRetrieved  |Microsoft Teams 채팅이 검색되었습니다.|
|<sup>message1, </sup> <sup>2</sup>의 호스트된 모든 콘텐츠를 페치했습니다. |MessageHostedContentsListed    |메시지의 모든 호스팅된 콘텐츠(예: 이미지 또는 코드 조각)가 검색되었습니다.|
|설치된 앱 |AppInstalled         |앱이 설치되었습니다.   |
|카드에서 수행된 작업|PerformedCardAction|사용자가 채팅 내의 적응형 카드에 대해 조치를 취했습니다. 적응형 카드는 일반적으로 봇에서 채팅에서 다양한 정보 및 상호 작용을 표시하는 데 사용됩니다. <br/><br/>**참고:** 채팅 내의 적응형 카드에 대한 인라인 입력 작업만 감사 로그에서 사용할 수 있습니다. 예를 들어 사용자가 설문 조사 봇에서 생성된 적응형 카드의 채널 대화에서 설문 조사 응답을 제출하는 경우입니다. 대화 상자를 여는 "결과 보기"와 같은 사용자 작업 또는 대화 상자 내의 사용자 작업은 감사 로그에서 사용할 수 없습니다.|
|새 메시지 <sup>게시 1, </sup> <sup>2</sup>   |MessageSent|   새 메시지가 채팅 또는 채널에 게시되었습니다.|
|게시된 앱 |AppPublishedToCatalog           |앱이 카탈로그에 추가되었습니다.     |
|메시지 <sup>읽기 1, </sup> <sup>2</sup> |MessageRead    |채팅 또는 채널의 메시지가 검색되었습니다.|
|메시지 <sup>1, </sup> <sup>2</sup>의 호스트된 콘텐츠 읽기   |MessageHostedContentRead   |메시지의 호스트된 콘텐츠(예: 이미지 또는 코드 조각)가 검색되었습니다.|
|팀에서 봇 제거   |BotRemovedFromTeam         |사용자가 팀에서 봇을 제거합니다.       |
|제거된 커넥터     |ConnectorRemoved         |사용자가 채널에서 커넥터를 제거합니다.         |
|제거된 멤버    |MemberRemoved        |팀 소유자는 팀, 채널 또는 그룹 채팅에서 구성원을 제거합니다.         |
|팀 채널<sup>3</sup>의 공유가 제거됨 | TerminatedSharing |팀 또는 채널 소유자가 공유 채널에 대한 공유를 사용하지 않도록 설정했습니다. |
|팀 채널<sup>3</sup>의 복원된 공유 | SharingRestored | 팀 또는 채널 소유자가 공유 채널에 대한 공유를 다시 사용하도록 설정했습니다. |
|제거된 탭    |TabRemoved         |사용자가 채널에서 탭을 제거합니다.         |
|공유 채널<sup>3</sup>에 대한 초대에 응답 | InviteeResponded | 사용자가 공유 채널 초대에 응답했습니다. |
|공유 채널<sup>3</sup>에 초대된 응답에 응답 | ChannelOwnerResponded |채널 소유자가 공유 채널 초대에 응답한 사용자의 응답에 응답했습니다. |
|검색된 메시지 <sup>1, </sup> <sup>2</sup> |MessagesListed |채팅 또는 채널의 메시지가 검색되었습니다.|
|Teams URL 링크가 포함된 메시지 보내기 |MessageCreatedHasLink|사용자가 Teams URL 링크가 포함된 메시지를 보냅니다.|
|메시지 만들기 <sup>1, </sup> <sup>2</sup>에 대한 변경 알림 전송  |MessageCreatedNotification |구독된 수신기 애플리케이션에 새 메시지를 알리기 위해 변경 알림이 전송되었습니다.|
|메시지 삭제 <sup>1, </sup> <sup>2</sup>에 대한 변경 알림 전송  |MessageDeletedNotification |구독된 수신기 애플리케이션에 삭제된 메시지를 알리기 위해 변경 알림이 전송되었습니다.|
|메시지 업데이트 <sup>1, </sup> <sup>2</sup>에 대한 변경 알림 전송    |MessageUpdatedNotification |업데이트된 메시지를 구독한 수신기 애플리케이션에 알리기 위해 변경 알림이 전송되었습니다.|
|공유 채널<sup>3</sup>에 대한 초대 보내기 | InviteSent |채널 소유자 또는 멤버가 공유 채널에 초대를 보냅니다. 채널 정책이 외부 사용자와 채널을 공유하도록 구성된 경우 조직 외부 사용자에게 공유 채널 초대를 보낼 수 있습니다.  |
|메시지 변경 알림 구독 <sup>1, </sup> <sup>2</sup> |SubscribedToMessages   |메시지에 대한 변경 알림을 받기 위해 수신기 애플리케이션에서 구독을 만들었습니다.|
|제거된 앱 |AppUninstalled           |앱이 제거되었습니다.     |
|업데이트된 앱 |AppUpdatedInCatalog           |카탈로그에서 앱이 업데이트되었습니다.     |
|채팅 <sup>업데이트 1, </sup> <sup>2</sup> |ChatUpdated    |Teams 채팅이 업데이트되었습니다.|
|메시지 <sup>업데이트 1, </sup> <sup>2</sup>  |MessageUpdated |채팅 또는 채널의 메시지가 업데이트되었습니다.|
|업데이트된 커넥터    |ConnectorUpdated         |사용자가 채널에서 커넥터를 수정했습니다.         |
|업데이트된 탭   |TabUpdated         |사용자가 채널의 탭을 수정했습니다.         |
|업그레이드된 앱 |AppUpgraded           |앱이 카탈로그의 최신 버전으로 업그레이드되었습니다.     |
|사용자가 Teams 로그인     |TeamsSessionStarted         |사용자가 Microsoft Teams 클라이언트에 로그인합니다. 이 이벤트는 토큰 새로 고침 활동을 캡처하지 않습니다.         |
||||

> [!NOTE]
> <sup>1</sup> 이 이벤트에 대한 감사 레코드는 Microsoft Graph API 호출하여 작업을 수행할 때만 기록됩니다. 작업이 Teams 클라이언트에서 수행되는 경우 감사 레코드가 기록되지 않습니다.<br/><sup>2</sup> 이 이벤트는 고급 감사에서만 사용할 수 있습니다. 즉, 이러한 이벤트가 감사 로그에 기록되기 전에 사용자에게 적절한 라이선스가 할당되어야 합니다. 고급 감사에서만 사용할 수 있는 활동에 대한 자세한 내용은 [Microsoft 365 고급 감사를](/microsoft-365/compliance/advanced-audit#advanced-audit-events) 참조하세요. 고급 감사 라이선스 요구 사항은 [Microsoft 365 감사 솔루션을](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements) 참조하세요. <br/> <sup>3</sup> 이 이벤트는 공개 미리 보기로 제공됩니다.

## <a name="shifts-in-teams-activities"></a>Teams 활동의 변화

**(미리 보기 중)**

조직에서 Teams Shifts 앱을 사용하는 경우 감사 로그에서 Shifts 앱과 관련된 활동을 검색할 수 있습니다. 다음은 Microsoft 365 감사 로그의 Teams Shifts 활동에 대해 기록되는 모든 이벤트 목록입니다.

|친숙한 이름  |작업  |설명  |
|---------|---------|---------|
|예약 그룹 추가됨 |ScheduleGroupAdded          |사용자가 일정에 새 일정 그룹을 성공적으로 추가합니다.|
|편집된 일정 그룹     |ScheduleGroupEdited         |사용자가 예약 그룹을 성공적으로 편집합니다.          |
|삭제된 일정 그룹         |ScheduleGroupDeleted              |사용자가 일정에서 예약 그룹을 성공적으로 삭제합니다.|
|철회된 일정 |ScheduleWithdrawn              |사용자가 게시된 일정을 성공적으로 철회합니다.|
|교대 근무 추가      |ShiftAdded          |사용자가 교대 근무를 추가했습니다.           |
|편집된 교대 근무       |ShiftEdited       |사용자가 교대 근무를 성공적으로 편집합니다.        |
|삭제된 교대 근무          |ShiftDeleted          | 사용자가 교대 근무를 성공적으로 삭제합니다.               |
|추가된 제한 시간      |TimeOffAdded          |사용자가 일정에 따라 휴가를 성공적으로 추가합니다.          |
|편집된 제한 시간         |TimeOffEdited           |사용자가 휴가를 성공적으로 편집합니다.          |
|삭제된 시간     |TimeOffDeleted              |사용자가 휴가를 성공적으로 삭제합니다.           |
|열린 교대 근무가 추가됨     |OpenShiftAdded          |사용자가 예약 그룹에 열린 교대 근무를 성공적으로 추가합니다.          |
|편집된 열린 교대 근무    |OpenShiftEdited          |사용자가 예약 그룹의 열린 교대조를 성공적으로 편집합니다.          |
|열린 교대 근무가 삭제됨      |OpenShiftDeleted          |사용자가 예약 그룹에서 열린 교대 근무를 성공적으로 삭제합니다.         |
|공유 일정     |ScheduleShared                  |사용자가 날짜 범위에 대한 팀 일정을 성공적으로 공유했습니다.          |
|시간 클록을 사용하여 클록         |ClockedIn          |사용자가 Time clock을 사용하여 시계에 성공했습니다.          |
|시간 시계를 사용하여 클록 아웃      |ClockedOut          |사용자가 시간 시계를 사용하여 성공적으로 클록 아웃합니다.          |
|시간 시계를 사용하여 중단 시작      |BreakStarted          |사용자가 활성 시간 클록 세션 중에 휴식을 성공적으로 시작합니다.          |
|시간 시계를 사용하여 중단 종료    |BreakEnded          |사용자가 활성 시간 클록 세션 중에 중단을 성공적으로 종료합니다.          |
|시간 클록 항목 추가됨     |TimeClockEntryAdded          |사용자가 Time Sheet에 새 수동 시간 시계 항목을 성공적으로 추가합니다.          |
|편집된 시간 클록 항목     | TimeClockEntryEdited             |사용자가 Time Sheet에서 시간 클록 항목을 성공적으로 편집합니다.          |
|삭제된 시간 클록 항목    |TimeClockEntryDeleted              |사용자가 Time Sheet에서 시간 클록 항목을 성공적으로 삭제합니다.          |
|교대 근무 요청이 추가됨         |RequestAdded              |사용자가 교대 근무 요청을 추가했습니다.          |
|교대 근무 요청에 응답     |RequestRespondedTo                  |사용자가 교대 근무 요청에 응답했습니다.          |
|취소된 교대 근무 요청         |RequestCancelled               |사용자가 교대 근무 요청을 취소했습니다.          |
|변경된 일정 설정      |ScheduleSettingChanged          |사용자가 Shifts 설정의 설정을 변경합니다.         |
|인력 통합 추가      |WorkforceIntegrationAdded                  | Shifts 앱은 타사 시스템과 통합됩니다.         |
|수락된 끄기 시프트 메시지         |OffShiftDialogAccepted          |사용자가 교대 근무 시간 후 Teams 액세스하는 오프 시프트 메시지를 승인합니다.           |

## <a name="office-365-management-activity-api"></a>Office 365 관리 작업 API

Office 365 관리 활동 API를 사용하여 Teams 이벤트에 대한 정보를 검색할 수 있습니다. Teams 대한 관리 작업 API 스키마에 대한 자세한 내용은 [Teams 스키마](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema)를 참조하세요.

## <a name="attribution-in-teams-audit-logs"></a>Teams 감사 로그의 특성

Azure Active Directory(Azure AD), Microsoft 365 관리 포털 또는 Microsoft 365 그룹 Graph API 통해 수행된 Teams(예: 추가 또는 삭제된 사용자)의 멤버 자격 변경이 Teams  작업의 실제 개시자가 아닌 팀의 기존 소유자에 대한 특성을 사용하여 일반 채널에서 메시지를 감사합니다. 이러한 시나리오에서는 Azure AD 또는 [Microsoft 365 그룹 감사 로그를](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 참조하여 관련 정보를 확인합니다.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>클라우드용 Defender 앱을 사용하여 활동 정책 설정

[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) 통합을 사용하면 앱 공급자의 API를 사용하여 다양한 자동화된 프로세스를 적용하도록 [활동 정책을](/cloud-app-security/user-activity-policies) 설정할 수 있습니다. 이러한 정책을 사용하면 다양한 사용자가 수행한 특정 활동을 모니터링하거나 특정 유형의 활동 중 예기치 않게 높은 비율을 따를 수 있습니다.

활동 검색 정책을 설정하면 경고 생성이 시작됩니다. 경고는 정책을 만든 후에 발생하는 활동에 대해서만 생성됩니다. 다음은 클라우드용 Defender 앱에서 활동 정책을 사용하여 Teams 활동을 모니터링하는 방법에 대한 몇 가지 예제 시나리오입니다.

### <a name="external-user-scenario"></a>외부 사용자 시나리오

비즈니스 관점에서 볼 때 주의해야 할 한 가지 시나리오는 외부 사용자를 Teams 환경에 추가하는 것입니다. 외부 사용자를 사용하는 경우 현재 상태를 모니터링하는 것이 좋습니다.  [클라우드용 Defender 앱을](/cloud-app-security/what-is-cloud-app-security) 사용하여 잠재적인 위협을 식별할 수 있습니다.

:::image type="content" alt-text="외부 사용자 추가를 모니터링하는 정책입니다." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

외부 사용자 추가를 모니터링하는 이 정책의 스크린샷을 통해 정책의 이름을 지정하고, 비즈니스 요구에 따라 심각도를 설정하고, 단일 작업으로 설정한 다음, 내부가 아닌 사용자 추가만 특별히 모니터링하는 매개 변수를 설정하고, 이 활동을 Teams 제한할 수 있습니다.

이 정책의 결과는 활동 로그에서 볼 수 있습니다.

:::image type="content" alt-text="외부 사용자 정책에 의해 트리거되는 이벤트입니다." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

여기에서 설정한 정책과 일치하는 항목을 검토하고 필요에 따라 조정하거나 다른 곳에서 사용할 결과를 내보낼 수 있습니다.

### <a name="mass-delete-scenario"></a>대량 삭제 시나리오

앞에서 설명한 대로 삭제 시나리오를 모니터링할 수 있습니다. Teams 사이트의 대량 삭제를 모니터링하는 정책을 만들 수 있습니다. 이 예제에서는 30분 동안 팀의 대량 삭제를 감지하도록 경고 기반 정책이 설정됩니다.

:::image type="content" alt-text="대량 팀 삭제 검색에 대한 정책 설정을 보여 주는 정책입니다." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

스크린샷에서 볼 수 있듯이 심각도, 단일 또는 반복 작업, Teams 및 사이트 삭제로 제한하는 매개 변수를 포함하여 Teams 삭제를 모니터링하도록 이 정책에 대한 다양한 매개 변수를 설정할 수 있습니다. 이 작업은 템플릿과 독립적으로 수행하거나 조직의 요구 사항에 따라 이 정책을 기반으로 하는 템플릿을 만들 수 있습니다.

비즈니스에 적합한 정책을 설정한 후에는 이벤트가 트리거될 때 활동 로그의 결과를 검토할 수 있습니다.

:::image type="content" alt-text="대량 삭제로 트리거되는 이벤트 스크린샷" source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

설정한 정책으로 필터링하여 해당 정책의 결과를 볼 수 있습니다. 활동 로그에서 가져오는 결과가 만족스럽지 않은 경우(결과가 많이 표시되거나 전혀 표시되지 않을 수 있음) 쿼리를 미세 조정하여 필요한 작업과 더 관련성을 높이는 데 도움이 될 수 있습니다.

### <a name="alert-and-governance-scenario"></a>경고 및 거버넌스 시나리오

활동 정책이 트리거될 때 경고를 설정하고 관리자 및 다른 사용자에게 전자 메일을 보낼 수 있습니다. 사용자를 일시 중단하거나 사용자가 자동화된 방식으로 다시 로그인하도록 하는 것과 같은 자동화된 거버넌스 작업을 설정할 수 있습니다. 이 예제에서는 활동 정책이 트리거될 때 사용자 계정을 일시 중단하는 방법을 보여 줍니다. 30분 만에 두 개 이상의 팀을 삭제한 사용자를 결정합니다.

![활동 정책에 대한 경고 및 거버넌스 작업의 스크린샷](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>클라우드용 Defender 앱을 사용하여 변칙 검색 정책 설정

클라우드용 Defender 앱의 [변칙 검색 정책은](/cloud-app-security/anomaly-detection-policy) 클라우드 환경에서 고급 위협 검색을 즉시 실행할 수 있도록 기본 제공 사용자 및 UEBA(엔터티 동작 분석) 및 기계 학습(ML)을 제공합니다. 자동으로 사용하도록 설정되므로 새로운 변칙 검색 정책은 즉각적인 검색을 제공하여 사용자와 네트워크에 연결된 컴퓨터 및 디바이스에서 수많은 동작 변칙을 대상으로 하여 즉각적인 결과를 제공합니다. 또한 새로운 정책은 클라우드용 Defender 앱 검색 엔진에서 더 많은 데이터를 노출하여 조사 프로세스를 가속화하고 지속적인 위협을 포함하도록 지원합니다.

Teams 이벤트를 변칙 검색 정책에 통합하기 위해 노력하고 있습니다. 지금은 다른 Office 제품에 대한 변칙 검색 정책을 설정하고 해당 정책과 일치하는 사용자에 대해 작업 항목을 수행할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft Purview 규정 준수 포털에서 감사 로그 검색](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
