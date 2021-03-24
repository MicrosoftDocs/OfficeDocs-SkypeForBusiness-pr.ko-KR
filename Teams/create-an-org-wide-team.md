---
title: Microsoft Teams에서 조직 전체 팀 만들기
author: cichur
ms.author: v-cichur
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Teams에서 조직 전체 팀을 만들고 관리하는 방법을 알아보고 중소 규모 조직의 모든 사용자가 공동 작업할 수 있는 자동 방법을 제공합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28a03f045aa6db2567feb8990b9b9267706c7e8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111164"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Microsoft Teams에서 조직 전체 팀 만들기

조직 전체 팀은 중소규모 조직에 속한 모든 사용자에게 공동 작업을 위한 단일 팀의 일원이 될 수 있도록 자동적인 방법을 제공합니다.

조직 전체 팀을 사용하여 전역 관리자는 조직의 모든 사용자를 가져오고 사용자가 조직에 참여하고 나갈 때 Active Directory를 사용하여 구성원을 최신 상태로 유지하는 공개 팀을 쉽게 만들 수 있습니다. 전 세계 관리자만 조직 전체 팀을 만들 수 있으며 현재 조직 전체 팀은 사용자 수가 10,000명을 넘지 않습니다. 테넌트 당 조직 전체 팀의 수도 5개로 제한되어 있습니다. 이러한 요구 사항을 충족하는 경우 전역 관리자가 팀을 만드는 과정에서 **팀을 처음부터 구축** 을 선택할 때 **조직 전체** 를 옵션으로 볼 수 있습니다. 

![조직 전체 팀을 만들기 위한 조직 전체 옵션의 스크린샷](media/create-org-wide-team.png "조직 전체 팀을 만들기 위한 조직 전체 옵션의 스크린샷")

조직의 전체 팀이 만들어지면 모든 전역 관리자 및 Teams 서비스 관리자가 팀 소유자로 추가되고 모든 활성 사용자가 팀 구성원으로 추가됩니다. 라이선스가 없는 사용자도 팀에 추가됩니다. 라이선스가 없는 사용자가 Teams에 처음 로그인할 때 사용자에게 Microsoft Teams Exploratory 라이선스가 할당됩니다. Exploratory 라이선스에 대한 자세한 내용은 [Microsoft Teams Exploratory](teams-exploratory.md)라이선스 관리를 체크 아웃합니다. 

다음 유형의 계정은 조직 전체 팀에 추가할 수 없습니다.

- 로그인이 차단된 계정
- 게스트 사용자
- 리소스 또는 서비스 계정(예: 자동 참석자 및 호출 큐와 연결된 계정)
- 회의실 또는 장비 계정
- 공유 사서함으로 지원되는 계정

조직의 디렉토리가 새 활성 사용자를 포함하도록 업데이트된 경우 또는 사용자가 회사에서 더 이상 일하지 않고 계정이 비활성화된 경우 변경 내용이 자동으로 동기화되고 팀에서 사용자가 추가 또는 제거됩니다. 팀 구성원은 조직 전체 팀에서 나갈 수 없습니다. 팀 소유자는 필요한 경우 수동으로 사용자를 추가하거나 제거할 수 있습니다.

> [!NOTE]
> - 팀을 만들 때  조직 전체 옵션이 표시되지 않는 경우 전체 관리자인 경우 조직 전체의 5개 팀 제한에 도달하거나 조직에 현재 크기 제한이 10,000명을 초과할 수 있습니다. 향후에는 이 제한을 높이도록 노력하고 있습니다. 조직 전체 팀은 아직 교육용 Teams에서 사용할 수 없습니다.
> - 대화방 목록, 장비 및 리소스 계정에 속하지 않는 대화방은 조직 전체 팀에 추가 하거나 동기화 할 수 있습니다. 팀 소유자는 팀에서 이러한 계정을 쉽게 제거할 수 있습니다.
> - 시스템에서 구성원을 추가하거나 제거하는 모든 작업이 일반 채널에 게시됩니다. 채널은 또한 Teams 클라이언트에 새 활동이 있는 것으로 표시됩니다.
> - 조직이 Teams에 새로 시작되고 사용자 수가 10,000명을 넘지 않습니다. 팀 이름은 테넌트 이름을 반영하고 일반 채널을 갖게 됩니다. 전역 관리자는 여느 팀처럼 이 팀을 편집할 수 있습니다. 

## <a name="best-practices"></a>모범 사례

조직 전체 팀을 최대한 활용하려면 팀 소유자가 다음을 수행하는 것이 좋습니다.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>팀 소유자만 일반 채널에 게시하도록 허용

팀 소유자만 일반 채널에 게시하여 채널 "소음"을 줄일 수 있습니다. 팀으로 이동하여 일반 채널을 찾은 다음, 채널 **관리 ̇ ̇ ̇ 옵션을**  >  **선택합니다.** 채널 설정 **탭에서** 사용 권한을 **클릭한** 다음 **소유자만 메시지를 게시할 수** 있습니다.

### <a name="turn-off-team-and-team-name-mentions"></a>@팀 및 @[팀 이름] 멘션 해제

 전체 조직에 과부하가 되는 것을 방지하기 위해 @멘션을 줄입니다. 팀으로 이동하여 **̇ ̇ ̇ 추가 옵션** > **팀 관리** 를 클릭합니다. 설정 탭에서 @멘션 클릭 > **구성원에게 @팀 또는 @[팀 이름] 옵션 표시** 를 해제합니다. 

### <a name="automatically-show-important-channels"></a>중요한 채널 자동 표시

중요한 채널을 표시하여 조직의 모든 사용자가 특정 대화에 참여할 수 있도록 합니다. 자세한 내용은 [전체 팀에 대해 채널을 자동으로 즐겨찾기에 추가](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)를 참조하세요. 

### <a name="set-up-channel-moderation"></a>채널 중재 설정

채널 중재를 설정하고 특정 팀 구성원에게 중재자 역할을 제공할 수 있습니다. (중재가 설정되면 팀 소유자에게 중재자 역할이 자동으로 부여됩니다.) 중재자가 채널에서 새 게시물을 시작할 수 있는 사용자를 제어하고 중재자를 추가 및 제거하며 팀 구성원의 기존 채널 메시지 회신 가능 여부, 봇 및 커넥터에서 채널 메시지의 전송 가능 여부를 제어할 수 있도록 채널 중재를 설정합니다. 자세한 정보는 [Microsoft Teams에서 채널 조정 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조하세요.

### <a name="remove-accounts-that-might-not-belong"></a>소속되지 않은 계정 삭제

구성원이 전체 팀을 떠날 수 없는 경우에도 팀 소유자는 소속되지 않은 계정을 제거하여 팀명단을 관리할 수 있습니다. **Teams를 사용하여 조직 전체 팀에서 사용자를 제거하도록 합니다**. Microsoft 365 관리 센터 또는 Outlook의 그룹과 같은 다른 방법을 사용하여 사용자를 제거하는 경우 조직 전체 팀에 사용자가 다시 추가될 수 있습니다.

## <a name="faq"></a>FAQ

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Teams 클라이언트를 사용하지 않고 조직 전체 팀을 만들 수 있는 방법이 있나요?

전역 관리자는 Teams 클라이언트를 사용해서만 조직 전체 팀을 만들 수 있습니다. 조직에서 팀 만들기를 PowerShell 사용으로 제한하는 경우 권장되는 해결 방법은 전역 관리자를 팀을 만들 수있는 보안 사용자 그룹에 추가하는 것입니다. 자세한 내용은 그룹을 [만들 수 있는 사용자 관리를 참조하세요.](/microsoft-365/admin/create-groups/manage-creation-of-groups)

이 방식을 사용할 수 없는 경우 PowerShell을 사용하여 공개 팀을 만들고 전역 관리자를 팀 소유자로 추가할 수 있습니다. 그런 다음 전역 관리자가 팀 이름 옆에 있는 **기타 옵션** 을 클릭하고 **팀 편집** 을 클릭한 다음 개인 정보 보호를 **조직 전체로 변경하면 조직의 모든 사용자가 자동으로 추가됩니다**. 팀 소유자만 팀 편집 옵션에 액세스할 수 있으며 전역 관리자만 **조직 전체** 옵션을 볼 수 있습니다.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>기존 팀을 조직 전체 팀으로 변환하는 방법이 있나요?

전역 관리자는 Teams 클라이언트에서 기존 팀을 편집하여 조직 전체 팀으로 전환할 수 있습니다. 팀 이름으로 이동하여 **기타 옵션** > **팀 편집** 을 클릭합니다.

### <a name="can-i-create-an-org-wide-team-using-a-team-template"></a>팀 템플릿을 사용하여 오그 전체 팀을 만들 수 있나요?

팀 템플릿은 전체 팀을 만드는 데 사용할 수 없습니다. 이 기능에 대한 작업은 현재 진행 중입니다. 

## <a name="see-also"></a>참고 항목

Microsoft Teams에서 회사 전체 팀 만들기에 대한 [비디오를 시청합니다.](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)