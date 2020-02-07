---
title: Microsoft 팀에서 조직 전체 팀 만들기
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 팀에서 조직 전체 팀을 만들고 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 854294f1ddb8e677037c151e3f7b3cada6e31c16
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826756"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Microsoft 팀에서 조직 전체 팀 만들기

조직 전체 팀은 소규모에서 중간 규모 조직의 모든 사용자가 공동 작업을 위해 단일 팀의 일부로 자동으로 제공 됩니다.

전역 관리자는 조직 전체의 모든 사용자를 가져오는 공용 팀을 쉽게 만들 수 있으며 사용자가 조직에 참가 하 고 나갈 때 Active Directory를 사용 하 여 구성원을 최신 상태로 유지 합니다. 전역 관리자만 조직 전체 팀을 만들 수 있으며 현재 조직 차원의 팀은 5000 사용자가 아닌 조직으로 제한 됩니다. 테 넌 트 당 조직 차원의 팀 5 개에 대 한 제한도 있습니다. 이러한 요구 사항을 충족 하는 경우 전역 관리자는 팀을 만들 때 **팀을 처음부터 새로** 만들기를 선택 하는 옵션으로 **Org wide** 를 표시 합니다. 

![조직 차원의 팀을 만들기 위한 조직 차원의 옵션 스크린샷](media/create-org-wide-team.png "조직 차원의 팀을 만들기 위한 조직 차원의 옵션 스크린샷")

조직 차원의 팀이 만들어지면 모든 전역 관리자가 팀 소유자로 추가 되 고 모든 활성 사용자가 팀 구성원으로 추가 됩니다. 라이선스가 없는 사용자도 팀에 추가 됩니다. 라이선스가 없는 사용자가 처음으로 팀에 로그인 할 때 사용자에 게 Microsoft 팀 상업용 클라우드 평가판 라이선스가 할당 됩니다. 평가판 라이선스에 대 한 자세한 내용은 [팀 상업용 클라우드 평가판 제공 관리](iw-trial-teams.md)를 참조 하세요. 

이러한 유형의 계정은 조직 전체 팀에 추가 되지 않습니다.

- 로그인이 차단 된 계정
- 게스트 사용자
- 서비스 계정
- 회의실 또는 장비 계정
- 공유 사서함으로 지원 되는 계정

조직의 디렉터리가 새 활성 사용자를 포함 하도록 업데이트 되거나 사용자가 회사에서 더 이상 작동 하지 않고 해당 계정이 사용 되지 않도록 설정 되어 있으면 변경 내용이 자동으로 동기화 되 고 팀에서 사용자가 추가 되거나 제거 됩니다. 팀 구성원은 조직 차원의 팀을 나갈 수 없습니다. 팀 소유자는 필요한 경우 수동으로 사용자를 추가 하거나 제거할 수 있습니다.

> [!NOTE]
> - 팀을 만들 때 **조직 전체** 옵션이 표시 되지 않는 경우 전역 관리자 인 경우에는 해당 기능이 계속 배포 될 수 있으며, 다섯 개의 조직 전체 팀 제한에 도달 했거나 조직이 5000 구성원의 현재 크기 제한을 초과 했을 수 있습니다. 이번에는 향후에이 한도를 증가 하 고 있습니다.
> - 회의실 목록, 장비, 리소스 계정에 속하지 않는 채팅방은 조직 전체 팀에 추가 되거나 동기화 될 수 있습니다. 팀 소유자는 팀에서 이러한 계정을 쉽게 제거할 수 있습니다.
> - 구성원을 추가 하거나 제거 하는 시스템의 모든 작업이 일반 채널에 게시 됩니다. 또한 채널은 팀 클라이언트에 새 활동을 갖는 것으로 표시 됩니다.

## <a name="best-practices"></a>모범 사례

조직 전체 팀을 최대한 활용 하려면 팀 소유자가 다음을 수행 하는 것이 좋습니다.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>팀 소유자만 일반 채널에 게시할 수 있도록 허용

팀 소유자만 일반 채널에 게시 하 여 채널 소음을 줄일 수 있습니다. 팀으로 이동 하 고 **̇ ̇ ̇ 추가 옵션** > 을 클릭 하 여**팀 관리**를 선택 합니다. **설정** 탭에서 **구성원 권한을** 클릭 > **소유자만 메시지를 게시할 수 있음**을 선택 합니다.

### <a name="turn-off-team-and-team-name-mentions"></a>@Team 및 @ [팀 이름] 멘 션 끄기

 전체 조직에 과부하가 되는 것을 방지 하기 위해 @mentions를 줄입니다. 팀으로 이동 하 고 **̇ ̇ ̇ 추가 옵션** > 을 클릭 하 여**팀 관리**를 선택 합니다. **설정** 탭에서 <strong>@mentions</strong> > 클릭 **하 여 구성원 표시 옵션을 @team 또는 @ [팀 이름]으로**설정 해제 합니다. 

### <a name="automatically-show-important-channels"></a>중요 한 채널을 자동으로 표시

조직의 모든 사용자가 특정 대화에서 관여 하도록 중요 한 채널을 표시 합니다. 자세한 내용은 [팀 전체에 대 한 자동 즐겨찾기 채널](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)을 참조 하세요. 

### <a name="set-up-channel-moderation"></a>채널 중재 설정

채널 중재를 설정 하 고 특정 팀 구성원에 게 중재자 기능을 제공 하는 것이 좋습니다. (중재가 설정 되 면 팀 소유자는 자동으로 중재자 기능을 제공 합니다.) 중재자는 채널에서 새 게시물을 시작할 수 있는 사용자를 제어 하 고, 중재자를 추가 및 제거 하 고, 팀 구성원이 기존 채널 메시지에 회신할 수 있는지 여부를 제어 하 고, 인공 지능 및 커넥터의 채널 메시지 제출 가능 여부를 제어할 수 자세한 내용은 [Microsoft 팀에서 채널 중재 설정 및 관리](manage-channel-moderation-in-teams.md)를 참조 하세요.

### <a name="remove-accounts-that-might-not-belong"></a>속해 있지 않을 수 있는 계정 제거

구성원이 조직 차원의 팀을 팀 소유자로 남겨둘 수는 없지만 자신이 속해 있지 않은 계정을 제거 하 여 팀 명단을 관리할 수 있습니다. **팀을 사용 하 여 조직 전체 팀에서 사용자를 제거**해야 합니다. Microsoft 365 관리 센터 또는 Outlook의 그룹에서 사용자를 제거 하는 다른 방법을 사용 하는 경우 사용자가 조직 전체 팀에 다시 추가 될 수 있습니다.

## <a name="faq"></a>FAQ

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>팀 클라이언트를 사용 하는 것 외에도 조직 전체 팀을 만들 수 있는 방법이 있나요?

전역 관리자는 팀 클라이언트를 사용 하 여 조직 차원의 팀만 만들 수 있습니다. 조직에서 PowerShell을 사용 하 여 팀을 만드는 것이 제한 되는 경우, 팀을 만들 수 있는 사용자의 보안 그룹에 전역 관리자를 추가 하는 것이 좋습니다. 자세한 내용은 [Office 365 그룹을 만들 수 있는 사용자 관리](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)를 참조하세요.

이 옵션이 선택 되어 있지 않은 경우 PowerShell을 사용 하 여 공용 팀을 만들고 전역 관리자를 팀 소유자로 추가할 수 있습니다. 그런 다음 전역 관리자가 팀 이름 옆에 있는 **추가 옵션** 을 클릭 하 고 **팀 편집**을 클릭 한 다음 조직 전체에 대 한 개인 정보를 변경 하 고 **조직의 모든 사용자가 자동으로 추가**됩니다. 팀 소유자만 **팀 편집** 옵션에 액세스할 수 있고 전역 관리자만 **조직 전체** 옵션을 볼 수 있습니다.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>기존 팀을 조직 전체 팀으로 변환 하는 방법이 있나요?

전역 관리자는 팀 클라이언트에서 기존 팀을 편집 하 여 조직 전체 팀으로 변환할 수 있습니다. 팀 이름으로 이동 하 고 **추가 옵션** > 을 클릭 하 여**팀을 편집**합니다.

## <a name="see-also"></a>참고 항목

[Microsoft 팀에서 회사 차원의 팀 만들기](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)에 대 한 비디오를 시청 하세요.
