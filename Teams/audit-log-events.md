---
title: 감사 로그에서 이벤트 검색을 Microsoft Teams
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
description: 감사 로그에서 Microsoft Teams 데이터를 검색하는 방법을 Microsoft 365 규정 준수 센터.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e769de858a7c0cb1ab14a538b1b1dc2a6559b21f
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356476"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>감사 로그에서 이벤트 검색을 Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

감사 로그는 여러 서비스에서 특정 활동을 Microsoft 365 수 있습니다. Microsoft Teams 감사되는 몇 가지 활동은 다음과 같습니다.

- 팀 만들기
- 팀 지우기
- 채널 추가
- 삭제된 채널
- 채널 설정 변경

감사되는 Teams 활동의 전체 목록은 Teams 작업 [](#teams-activities) 및 교대 근무 Teams [참조하세요.](#shifts-in-teams-activities)

> [!NOTE]
> 사설 채널의 감사 이벤트도 팀 및 표준 채널에 대해 기록됩니다.

## <a name="turn-on-auditing-in-teams"></a>에서 감사를 Teams

감사 데이터를 보기 전에 먼저 감사를 설정해야 Microsoft 365 규정 준수 센터. 자세한 내용은 감사 켜기 또는 해제를 [참조하세요.](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

> [!IMPORTANT]
> 감사 데이터는 감사를 설정한 시점에서만 사용할 수 있습니다.

## <a name="retrieve-teams-data-from-the-audit-log"></a>감사 Teams 데이터 검색

1. 작업의 감사 로그를 검색하려면 Teams 로 <https://compliance.microsoft.com> 이동하고 감사 를 **선택합니다.**

2. 검색 **페이지에서** 감사할 활동, 날짜 및 사용자를 필터링합니다.

3. 추가 분석을 위해 결과를 Excel 내보낼 수 있습니다.

단계별 지침은 준수 센터의 감사 [로그 검색을 참조하세요.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

> [!IMPORTANT]
> 감사 데이터는 감사가 켜져 있는 경우 감사 로그에만 표시됩니다.

감사 레코드를 보존하고 감사 로그에서 검색할 수 있는 기간은 구독 또는 Microsoft 365 Office 365, 특히 사용자에게 할당된 라이선스 유형에 따라 다릅니다. 자세한 내용은 보안 & [준수 센터 서비스 설명 을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="tips-for-searching-the-audit-log"></a>팁 로그를 검색하는 데 사용할 수 있습니다.

다음은 감사 로그에서 Teams 검색하는 팁입니다.

![준수 센터의 감사 로그 검색 페이지의 스크린샷](media/audit-log-search-page.png)

- 하나 이상의 활동 옆에 있는 확인란을 클릭하여 검색할 특정 활동을 선택할 수 있습니다. 활동을 선택하면 이 작업을 클릭하여 선택을 취소할 수 있습니다. 검색 상자를 사용하여 입력하는 키워드가 포함된 활동을 표시할 수도 있습니다.

  ![감사 로그 검색 페이지의 활동 드롭다운 목록 스크린샷](media/audit-log-search.png)

- cmdlet을 사용하여 실행된 활동에 대한 이벤트를 표시하려면 활동 목록의 모든 활동에 **대한** 결과 표시를 **선택합니다.** 이러한 활동에 대한 작업 이름을 알고 있는 경우 검색 상자에 입력하여 활동을 표시한 다음 선택합니다.

- 현재 검색 조건을 지우려면 모두 **지우기 를 클릭합니다.** 날짜 범위는 지난 7일의 기본값으로 반환됩니다.

- 5,000개 결과가 발견된 경우 검색 조건을 충족하는 이벤트가 5,000개가 넘는 것으로 가정할 수 있습니다. 검색 조건을 구체화하고 검색을 다시하여 더 적은 수의 결과를 반환하거나 모든 결과 다운로드 내보내기 를 선택하여 모든 검색 결과를 내보낼  >  **수 있습니다.** 감사 로그를 내보내는 단계별 지침은 파일로 검색 [결과 내보내기 를 참조하세요.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file)

오디오 로그 [검색을 사용하려면](https://www.youtube.com/embed/UBxaRySAxyE) 이 비디오를 체크 아웃합니다. 사용자에 대한 감사 로그 검색을 Teams 프로그램을 위한 프로그램 관리자인 Ansuman Acharya에 Teams.

## <a name="teams-activities"></a>Teams 활동

다음은 감사 로그의 사용자 및 관리자 활동에 대해 기록된 Teams Microsoft 365 목록입니다. 표에는 활동 열에 표시되는 친숙한  이름과 검색 결과를 내보낼 때 감사 레코드의 자세한 정보 및 CSV 파일에 표시되는 해당 작업의 이름이 포함됩니다.

|친숙한 이름  |작업 |설명 |
|:---------|:---------|:---------|
|팀에 봇 추가   |BotAddedToTeam        |사용자가 팀에 봇을 추가합니다.        |
|채널 추가   |ChannelAdded         |사용자가 팀에 채널을 추가합니다.         |
|커넥터 추가  |ConnectorAdded          |사용자가 채널에 커넥터를 추가합니다.        |
|모임에 대한 Teams 추가되었습니다.|MeetingDetail|Teams 시작 시간, 종료 시간 및 모임에 참가할 URL을 포함하여 모임에 대한 정보를 추가했습니다.|
|모임 참가자에 대한 추가 정보|MeetingParticipantTrack|Teams 각 참가자의 사용자 ID, 참가자가 모임에 참가한 시간 및 참가자가 모임을 나간 시간을 포함하여 모임 참가자에 대한 정보를 추가했습니다.|
|멤버 추가    |MemberAdded         |팀 소유자는 팀, 채널 또는 그룹 채팅에 구성원을 추가합니다.         |
|탭 추가    |TabAdded         |사용자가 채널에 탭을 추가합니다.        |
|채널 설정 변경    |ChannelSettingChanged         |ChannelSettingChanged 작업은 팀 구성원이 다음 작업을 수행할 때 기록됩니다. 이러한 각 활동에 대해 변경된 설정에 대한 설명(괄호에 표시된)은 감사 로그 검색 결과의 항목 열에 표시됩니다.  <ul><li>팀 채널의 이름 **변경(채널 이름)**</li><li>팀 채널의 변경 **설명(채널 설명)**</li> </ul>      |
|변경된 조직 설정   |TeamsTenantSettingChanged         |TeamsTenantSettingChanged 작업은 다음 작업을 수행하면 해당 팀의 전역 관리자가 Microsoft 365 관리 센터. 이러한 활동은 전체 설정에 Teams 영향을 미치고 있습니다. 자세한 내용은 조직의 Teams [관리 를 참조하세요.](enable-features-office-365.md) <br>이러한 각 활동에 대해 감사 로그 검색 결과의 항목 열에 변경된 설정에  대한 설명(괄호로 표시)이 표시됩니다.<ul><li>조직에 대한 Teams(Microsoft Teams).</li><li>조직에 대한 Microsoft Teams 및 비즈니스용 Skype 상호 비즈니스용 Skype 사용 또는 사용하지 **않도록 설정합니다.**</li><li>클라이언트에서 조직도 보기를 활성화하거나 **Microsoft Teams(조직도** 보기).</li><li>팀 구성원이 비공개 모임을 예약할 수 있는 기능을 설정하거나 사용하지 **않도록 설정합니다(개인** 모임 일정).</li><li>팀 구성원이 채널 모임을 예약할 수 있는 기능을 설정하거나 사용하지 **않도록 설정합니다(채널** 모임 일정).</li><li>모임에서 화상 통화를 Teams 설정하거나 사용하지 않도록 설정합니다(Skype **비디오).**</li><li>조직에 대한 Microsoft Teams 모임에서 화면 공유를 활성화하거나 사용하지 않도록 설정(Skype **모임에** 대한 화면 공유).</li><li>애니메이션 이미지(Giphys라고도 불리는)를 대화(애니메이션 이미지)에 추가하는 Teams **비활성화합니다.**</li><li>조직의 콘텐츠 등급 설정을 **변경합니다(콘텐츠 등급).** 콘텐츠 등급은 대화에 표시할 수 있는 애니메이션 이미지 유형을 제한합니다.</li><li>팀 구성원이 인터넷에서 팀 대화(인터넷에서 사용자 지정 가능한 이미지)에 사용자 지정 가능한 이미지(사용자 지정 mes)를 추가할 수 **있습니다.**</li><li>팀 구성원이 팀 대화(편집 가능한 이미지)에 편집 가능한 이미지(스티커라고도 하는)를 추가하는 기능을 활성화하거나 **사용하지 않도록 설정합니다.**</li><li>팀 구성원이 채팅 및 채널에서 봇을 사용할 수 Microsoft Teams(조직 전체 봇)를 활성화하거나 사용하지 **않도록 설정합니다.**</li><li>특정 봇을 Microsoft Teams. 조직에 대해 봇을 사용할 수 있는 Teams 도움말 봇(개별 봇)은 T-봇을 포함하지 **않습니다.**</li><li>팀 구성원이 확장 또는 탭(확장 또는 탭)을 추가할 수 있는 기능을 설정하거나 **사용하지 않도록 설정합니다.**</li><li>봇의 측면 로드)에 대한 Microsoft Teams 봇의 사이드 로드를 활성화하거나 사용하지 **않도록 설정합니다.**</li><li>사용자가 전자 메일 메시지를 다른 채널로 보낼 수 있도록 설정하거나 **Microsoft Teams(채널** 전자 메일).</li></ul>|
|팀 구성원의 역할 변경    |MemberRoleChanged         |팀 소유자는 팀의 구성원 역할을 변경합니다. 다음 값은 사용자에게 할당된 역할 유형을 나타냅니다. <br><br>**1** - 멤버 역할을 나타냅니다.<br>**2** - 소유자 역할을 나타냅니다.<br>**3** - 게스트 역할을 나타냅니다.<br><br>멤버 속성에는 조직의 이름과 구성원의 전자 메일 주소도 포함됩니다.        |
|팀 설정 변경    |TeamSettingChanged        |TeamSettingChanged 작업은 팀 소유자가 다음 작업을 수행할 때 기록됩니다. 이러한 각 활동에 대해 감사 로그 검색 결과의 항목 열에 변경된 설정에  대한 설명(괄호로 표시)이 표시됩니다.<ul><li>팀의 액세스 유형을 변경합니다. Teams 개인 또는 공용으로 설정할 **수 있습니다(팀 액세스 유형).** 팀이 비공개인 경우(기본 설정) 사용자는 초대를 통해만 팀에 액세스할 수 있습니다. 팀이 공개된 경우 누구나 검색할 수 있습니다.</li><li>팀의 정보 **분류(팀 분류)를 변경합니다.** 예를 들어 팀 데이터는 높은 비즈니스 영향, 중간 비즈니스 영향 또는 낮은 비즈니스 영향으로 분류될 수 있습니다.</li><li>팀 **이름(팀 이름)을 변경합니다.**</li><li>팀 **설명(팀 설명)을 변경합니다.**</li><li>팀 설정에 대한 변경 내용입니다. 이러한 설정에 액세스하려면 팀 소유자가 팀을 마우스 오른쪽 단추로 클릭하고 팀 관리를 선택한 다음, 탭을 **설정** 있습니다. 이러한 활동의 경우 변경된 설정의 이름이 감사  로그 검색 결과의 항목 열에 표시됩니다.</li></ul>         |
|채팅 <sup>생성 1, </sup> <sup>2</sup>|    ChatCreated|    Teams 채팅이 생성되었습니다.|
|만든 팀    |TeamCreated         |사용자가 팀을 만듭니다.         |
|메시지 삭제  |MessageDeleted |채팅 또는 채널의 메시지가 삭제되었습니다.|
|모든 조직 앱 삭제|DeletedAllOrganizationApps           |카탈로그에서 모든 조직 앱을 삭제했습니다.     |
|삭제된 앱 |AppDeletedFromCatalog           |앱이 카탈로그에서 삭제되었습니다.     |
|삭제된 채널     |ChannelDeleted         |사용자가 팀에서 채널을 삭제합니다.         |
|삭제된 팀  |TeamDeleted            |팀 소유자가 팀을 삭제합니다.      |
|URL 링크가 있는 메시지를 Teams     |MessageEditedHasLink         |사용자가 메시지를 편집하고 해당 메시지에 URL 링크를 Teams.         |
|내보낼 메시지 <sup>1, </sup> <sup>2</sup> |    MessagesExported |채팅 또는 채널 메시지를 내보낼 수 있습니다.|
|인치된 채팅 <sup>1, </sup> <sup>2</sup>   |ChatRetrieved  |Microsoft Teams 채팅이 검색됩니다.|
|메시지<sup>1,</sup> <sup>2의</sup> 호스팅된 모든 콘텐츠 인치 |MessageHostedContentsListed    |메시지의 모든 호스팅 콘텐츠(예: 이미지 또는 코드)가 검색됩니다.|
|설치된 앱 |AppInstalled         |앱이 설치되었습니다.   |
|카드에서 수행된 작업|PerformedCardAction|사용자가 채팅 내에서 적응형 카드에 대해 조치를 취했습니다. 적응형 카드는 일반적으로 채팅에서 다양한 정보 및 상호 작용을 표시하도록 봇에서 사용됩니다. <br/><br/>**참고:** 채팅 내부의 적응형 카드의 인라인 입력 작업만 감사 로그에서 사용할 수 있습니다. 예를 들어 사용자가 설문 조사 봇에서 생성한 적응형 카드의 채널 대화에서 설문 조사 응답을 제출하는 경우를 예로 들 수 있습니다. 대화 상자를 열 수 있는 "결과 보기"처럼 사용자 작업 또는 대화 상자 내부의 사용자 작업은 감사 로그에서 사용할 수 없습니다.|
|새 메시지 <sup>게시 1, </sup> <sup>2</sup>   |MessageSent|   채팅 또는 채널에 새 메시지가 게시됩니다.|
|게시된 앱 |AppPublishedToCatalog           |앱이 카탈로그에 추가되었습니다.     |
|메시지 <sup>읽기 1, </sup> <sup>2</sup> |MessageRead    |채팅 또는 채널의 메시지가 검색됩니다.|
|메시지 <sup>1, </sup> <sup>2의 호스팅된 콘텐츠 읽기</sup>   |MessageHostedContentRead   |메시지에 호스팅된 콘텐츠(예: 이미지 또는 코드)가 검색됩니다.|
|팀에서 봇 제거   |BotRemovedFromTeam         |사용자가 팀에서 봇을 제거합니다.       |
|제거된 커넥터     |ConnectorRemoved         |사용자가 채널에서 커넥터를 제거합니다.         |
|제거된 멤버    |MemberRemoved        |팀 소유자는 팀, 채널 또는 그룹 채팅에서 구성원을 제거합니다.         |
|제거된 탭    |TabRemoved         |사용자가 채널에서 탭을 제거합니다.         |
|검색된 메시지 <sup>1, </sup> <sup>2</sup> |MessagesListed |채팅 또는 채널의 메시지가 검색됩니다.|
|URL 링크가 있는 메시지를 Teams |MessageCreatedHasLink|사용자가 URL 링크가 포함된 메시지를 Teams.|
|메시지 만들기에 대한 변경 알림 <sup>보내기 1, </sup> <sup>2</sup>  |MessageCreatedNotification |구독된 수신기 애플리케이션에 새 메시지를 알리기 위해 변경 알림이 전송됩니다.|
|메시지 지우기 <sup>1,</sup> <sup>2에</sup> 대한 변경 알림 전송  |MessageDeletedNotification |구독 수신기 애플리케이션에 삭제된 메시지를 알리기 위해 변경 알림이 전송되었습니다.|
|메시지 업데이트 <sup>1,</sup> <sup>2에</sup> 대한 변경 알림 전송    |MessageUpdatedNotification |업데이트된 메시지의 구독 수신기 애플리케이션에 알리기 위해 변경 알림이 전송되었습니다.|
|메시지 변경 알림 <sup>1, </sup> <sup>2 구독</sup> |SubscribedToMessages   |메시지에 대한 변경 알림을 수신기 애플리케이션에서 수신기 애플리케이션에 의해 생성되었습니다.|
|제거된 앱 |AppUninstalled           |앱이 제거됩니다.     |
|업데이트된 앱 |AppUpdatedInCatalog           |앱이 카탈로그에서 업데이트되었습니다.     |
|채팅 <sup>1, 2 </sup> <sup>업데이트</sup> |ChatUpdated    |Teams 채팅이 업데이트되었습니다.|
|메시지 <sup>1, 2 </sup> <sup>업데이트</sup>  |MessageUpdated |채팅 또는 채널의 메시지가 업데이트되었습니다.|
|업데이트된 커넥터    |ConnectorUpdated         |사용자가 채널에서 커넥터를 수정한 것입니다.         |
|업데이트된 탭   |TabUpdated         |사용자가 채널에서 탭을 수정한 것입니다.         |
|업그레이드된 앱 |AppUpgraded           |앱이 카탈로그의 최신 버전으로 업그레이드되었습니다.     |
|사용자가 로그인하여 Teams     |TeamsSessionStarted         |사용자가 클라이언트에 Microsoft Teams 합니다. 이 이벤트는 토큰 새로 고침 활동을 캡처하지 않습니다.         |


> [!NOTE]
> <sup>1</sup> 이 이벤트에 대한 감사 레코드는 Microsoft Graph 호출하여 작업이 수행될 때만 기록됩니다. 클라이언트에서 작업이 수행되는 Teams 감사 레코드는 기록되지 않습니다.<br/><br/><sup>2</sup> 이 이벤트는 고급 감사에서만 사용할 수 있습니다. 즉, 이러한 이벤트가 감사 로그에 기록되기 전에 사용자에게 적절한 라이선스를 할당해야 합니다. 고급 감사에서만 사용할 수 있는 활동에 대한 자세한 내용은 에서 고급 [감사를 Microsoft 365.](/microsoft-365/compliance/advanced-audit#advanced-audit-events) 고급 감사 라이선스 요구 사항은 의 감사 [솔루션을 Microsoft 365.](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements)

## <a name="shifts-in-teams-activities"></a>작업의 Teams 이동

**(미리 보기 중)**

조직에서 Shifts 앱을 사용하는 Teams Shifts 앱과 관련된 활동에 대한 감사 로그를 검색할 수 있습니다. 다음은 감사 로그의 작업에서 Shifts 활동에 Teams 모든 Microsoft 365 목록입니다.

|친숙한 이름  |작업  |설명  |
|---------|---------|---------|
|추가된 일자 그룹 |ScheduleGroupAdded          |사용자가 일정에 새 일정 그룹을 성공적으로 추가합니다.|
|편집된 일자 그룹     |ScheduleGroupEdited         |사용자가 성공적으로 스컬링 그룹을 편집합니다.          |
|삭제된 스컬링 그룹         |ScheduleGroupDeleted              |사용자가 일정에서 예약 그룹을 성공적으로 삭제합니다.|
|일정을 변경하지 않습니다. |ScheduleWithdrawn              |사용자가 게시된 일정을 성공적으로 철회합니다.|
|교대 근무 추가      |ShiftAdded          |사용자가 교대 근무를 성공적으로 추가합니다.           |
|편집된 교대 근무       |ShiftEdited       |사용자가 교대 근무를 성공적으로 편집합니다.        |
|삭제된 교대 근무          |ShiftDeleted          | 사용자가 교대 근무를 성공적으로 삭제합니다.               |
|끄기 시간 추가      |TimeOffAdded          |사용자가 일정에 끄기 시간을 성공적으로 추가합니다.          |
|편집된 시간 끄기         |TimeOffEdited           |사용자가 끄기 시간을 성공적으로 편집합니다.          |
|삭제된 시간 끄기     |TimeOffDeleted              |사용자가 끄기 시간을 성공적으로 삭제합니다.           |
|개방형 교대 근무 추가     |OpenShiftAdded          |사용자가 성공적으로 열린 교대 근무를 스컬링 그룹에 추가합니다.          |
|편집된 열린 교대 근무    |OpenShiftEdited          |사용자가 성공적으로 열린 교대 근무를 스컬링 그룹에서 편집합니다.          |
|삭제된 열려 있는 교대 근무      |OpenShiftDeleted          |사용자가 성공적으로 열린 교대 근무를 일임 그룹에서 삭제합니다.         |
|공유 일정     |ScheduleShared                  |사용자가 날짜 범위에 대한 팀 일정을 성공적으로 공유했습니다.          |
|시계를 사용하여 클록         |ClockedIn          |사용자가 Time clock을 사용하여 성공적으로 클록합니다.          |
|시간 시계를 사용하여 클록 아웃      |ClockedOut          |사용자가 Time clock을 사용하여 성공적으로 클록아웃합니다.          |
|시간 시계를 사용하여 휴식 시작      |BreakStarted          |사용자가 활성 시간 시계 세션 중에 휴식을 성공적으로 시작합니다.          |
|시간 시계를 사용하여 종료된 휴식    |BreakEnded          |사용자가 활성 시간 시계 세션 중에 휴식을 성공적으로 종료합니다.          |
|시간 시계 항목이 추가되었습니다.     |TimeClockEntryAdded          |사용자가 Time Sheet에 새 수동 시계 항목을 성공적으로 추가합니다.          |
|편집된 시간 시계 항목     | TimeClockEntryEdited             |사용자가 Time Sheet에서 시간 시계 항목을 성공적으로 편집합니다.          |
|삭제된 시간 시계 항목    |TimeClockEntryDeleted              |사용자가 Time Sheet에서 시간 시계 항목을 성공적으로 삭제합니다.          |
|교대 근무 요청 추가         |RequestAdded              |사용자가 교대 근무 요청을 추가합니다.          |
|교대 근무 요청에 응답     |RequestRespondedTo                  |사용자가 교대 근무 요청에 응답합니다.          |
|취소된 교대 근무 요청         |RequestCancelled               |사용자가 교대 근무 요청을 취소합니다.          |
|변경된 일정 설정      |ScheduleSettingChanged          |사용자는 Shifts 설정에서 설정을 변경합니다.         |
|인력 통합 추가      |WorkforceIntegrationAdded                  | Shifts 앱은 타사 시스템과 통합됩니다.         |
|수락된 교대 근무 메시지         |OffShiftDialogAccepted          |사용자는 교대 근무 시간 후에 액세스하기 위해 오프시프트 Teams 인정합니다.           |

## <a name="office-365-management-activity-api"></a>Office 365 관리 활동 API

관리 활동 API를 사용하여 Office 365 이벤트에 대한 정보를 검색할 Teams 있습니다. 에 대한 관리 활동 API Teams 자세한 내용은 Teams [를 참조합니다.](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema)

## <a name="attribution-in-teams-audit-logs"></a>감사 로그의 Teams 기여

Azure AD(Azure Active Directory), Microsoft 365 관리 포털 또는 Microsoft 365 그룹 Graph API를 통해 만든 사용자(예: 추가 또는 삭제)에 대한 멤버 자격 변경은 감사 메시지 및 Teams 감사 메시지 및 일반 채널에 표시됩니다. Teams 팀의 기존 소유자가 아니라 작업의 실제 시작자에 해당하지 않습니다. 이러한 시나리오에서는 Azure AD 또는 Microsoft 365 그룹 감사 [로그를](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 참조하여 관련 정보를 봐야 합니다.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Cloud App Security 정책 설정

Microsoft Cloud App Security [](/cloud-app-security/what-is-cloud-app-security) 통합을 사용하여 앱 공급자의 API를 사용하여 광범위한 자동화된 프로세스를 적용하기 위해 활동 정책을 설정할 수 있습니다. [](/cloud-app-security/user-activity-policies) 이러한 정책을 사용하면 다양한 사용자가 수행한 특정 활동을 모니터링하거나 특정 유형의 활동 중 예기치 않게 높은 비율을 따를 수 있습니다.

활동 검색 정책을 설정한 후 경고를 생성하기 시작합니다. 경고는 정책을 만든 후에 발생하는 활동에만 생성됩니다. 다음은 활동 정책을 사용하여 작업 Cloud App Security 모니터링하는 Teams 시나리오입니다.

### <a name="external-user-scenario"></a>외부 사용자 시나리오

비즈니스 관점에서 주시할 수 있는 한 가지 시나리오는 외부 사용자를 사용자 환경에 추가하는 Teams 있습니다. 외부 사용자가 사용하도록 설정되어 있는 경우 해당 사용자의 현재 상태 모니터링을 사용하는 것이 좋습니다.  잠재적 위협을 [식별하는](/cloud-app-security/what-is-cloud-app-security) 데 Cloud App Security 수 있습니다.

![외부 사용자 추가를 모니터링하는 정책입니다.](media/TeamsExternalUserAddPolicy.png)

외부 사용자 추가를 모니터링하는 이 정책의 스크린샷을 사용하면 정책의 이름을 지정하고, 비즈니스 요구에 따라 심각도를 설정하고, 이를 단일 활동으로 설정한 다음, 비 내부 사용자의 추가만 모니터링하는 매개 변수를 설정하고, 이 활동을 제한할 수 Teams.

이 정책의 결과는 활동 로그에서 볼 수 있습니다.

![외부 사용자 정책에 의해 트리거된 이벤트입니다.](media/TeamsExternalUserList.png)

여기에서 설정한 정책과 일치를 검토하고, 필요한 경우 조정하거나 다른 곳에서 사용할 결과를 내보낼 수 있습니다.

### <a name="mass-delete-scenario"></a>대량 삭제 시나리오

앞에서 설명한 대로, 지우기 시나리오를 모니터링할 수 있습니다. 사이트의 대량 지우기를 모니터링하는 정책을 만들 Teams 있습니다. 이 예제에서는 경고 기반 정책이 설정되어 30분 동안 팀의 대량 지우기를 검색합니다.

![대량 팀 지우기 검색에 대한 정책 설정을 보여주는 정책입니다.](media/TeamsMassDeletePolicy.png)

스크린샷에서 볼 수 있는 것 처럼 심각도, 단일 또는 반복 작업 및 이로 제한하는 매개 변수를 포함하여 이 정책에 대한 여러 가지 매개 변수를 Teams 및 사이트 Teams 수 있습니다. 이 방법은 템플릿과 독립적으로 수행될 수 있습니다. 또는 조직 요구에 따라 이 정책을 기본으로 만들 수 있는 템플릿이 있을 수 있습니다.

비즈니스에 대해 작동하는 정책을 설정한 후 이벤트가 트리거될 때 활동 로그의 결과를 검토할 수 있습니다.

![대량의 지우기에서 트리거된 스크린샷 이벤트.](media/TeamsMassDeleteList.png)

설정한 정책으로 필터링하여 해당 정책의 결과를 볼 수 있습니다. 활동 로그에 있는 결과가 만족스러울 수 없는 경우(많은 결과가 표시되거나 전혀 없는 경우) 쿼리를 세밀하게 조정하여 필요한 작업과 더 관련성이 높은 쿼리를 만드는 데 도움이 될 수 있습니다.

### <a name="alert-and-governance-scenario"></a>경고 및 거버넌스 시나리오

활동 정책이 트리거될 때 경고를 설정하고 관리자 및 다른 사용자에게 전자 메일을 보낼 수 있습니다. 사용자를 일시 중단하거나 사용자가 자동화된 방식으로 다시 로그인하도록 만드는 등의 자동화된 거버넌스 작업을 설정할 수 있습니다. 이 예제에서는 활동 정책이 트리거될 때 사용자 계정을 일시 중단할 수 있는 방법을 보여 주며 사용자가 30분 동안 두 개 이상의 팀을 삭제한 것을 확인할 수 있습니다.

![활동 정책에 대한 경고 및 거버넌스 작업 스크린샷.](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Cloud App Security 검색 정책을 설정하는 데 사용할 수 있습니다.

클라우드 [Cloud App Security](/cloud-app-security/anomaly-detection-policy) UEBA(사용자 및 엔터티 행동 분석) 및 머신 러닝(ML)을 제공하여 클라우드 환경 전반에서 고급 위협 감지를 즉시 실행할 수 있습니다. 자동으로 사용하도록 설정되어 있기 때문에 새 이상 감지 정책은 즉각적인 검색을 제공하여 사용자와 네트워크에 연결된 컴퓨터 및 디바이스 전체에 걸쳐 다양한 동작 이상을 대상으로 하여 즉각적인 결과를 제공합니다. 또한 새 정책은 검색 엔진의 Cloud App Security 더 많은 데이터를 노출하여 조사 프로세스의 속도를 향상하고 지속적인 위협을 포함할 수 있습니다.

에미리트는 Teams 검색 정책에 통합하기 위해 작업 중입니다. 지금은 다른 제품에 대한 이상 검색 정책을 설정하고 해당 Office 사용자에 대한 작업 항목을 취할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [로그에서 감사 로그를 Microsoft 365 규정 준수 센터](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
