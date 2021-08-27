---
title: 게스트 액세스 및 외부 액세스를 사용하여 조직 외부 사용자와 공동 작업
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
description: 외부 액세스(페더레이션) 및 게스트 액세스를 사용하여 Microsoft Teams에서 외부 조직의 사용자와 통화, 채팅, 검색 및 추가하는 방법을 알아봅니다.
ms.openlocfilehash: b2a8b7a4fb7042596b5f96ab8ac59b65c5b2df58
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582412"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>게스트 액세스 및 외부 액세스를 사용하여 조직 외부 사용자와 공동 작업

조직 외부의 사용자와 의사 소통 및 공동 작업을 해야 하는 경우 Microsoft Teams에서는 다음 두 가지 옵션을 제공합니다.

- **외부 액세스** - 다른 조직의 사용자를 찾고, 통화하고, 채팅할 수 있는 페더레이션 유형입니다. 이러한 사용자는 게스트로 초대되지 않는 한 팀에 추가할 수 없습니다.
- **게스트 액세스** - 게스트 액세스를 통해 조직 외부의 사용자를 팀에 초대할 수 있습니다. 초대된 사용자는 Azure Active Directory에서 게스트 계정을 갖게 됩니다.

Teams를 사용하면 조직 외부의 사용자들을 모임에 초대할 수 있습니다. 이 경우 외부 또는 게스트 액세스를 구성할 필요가 없습니다.

## <a name="external-access-federation"></a>외부 액세스(페더레이션)

Teams, 비즈니스용 Skype(온라인 또는온-프레미스) 또는 Skype를 사용하는 조직 외부 사용자와의 모임을 검색, 통화, 채팅, 설정해야 하는 경우 외부 액세스를 설정하세요. 

기본적으로 Outlook 액세스는 모든 도메인에서 사용됩니다. 특정 도메인을 허용 또는 차단하거나 해제하여 외부 액세스를 제한할 수 있습니다.

![외부 액세스 설정 스크린샷](media/external-access-federation-settings.png)

외부 액세스를 구성하는 경우 [외부 액세스 관리](manage-external-access.md)를 참조하세요. 

>[!NOTE]
>Microsoft Teams 무료 라이선스는 외부 액세스를 지원하지 않습니다.

## <a name="guest-access"></a>게스트 액세스

게스트 액세스를 사용하여 조직 외부의 사람을 팀에 추가하여 채팅, 통화, 미팅, 파일 공동 작업을 할 수 있습니다. 게스트는 기본 팀 구성원과 거의 동일한 모든 Teams 기능을 제공받을 수 있습니다.

게스트는 조직의 Azure Active Directory에 B2B 사용자로 추가되며 게스트 계정을 사용하여 Teams에 로그인해야 합니다. 즉, 조직에 로그인하기 위해 자신의 조직에서 로그아웃해야 할 수 있습니다.

Teams에서 게스트 액세스를 구성하려면 [팀에서 게스트와 공동 작업](/microsoft-365/solutions/collaborate-as-team)을 참조하세요.

## <a name="compare-external-and-guest-access"></a>외부 및 게스트 액세스 비교

다음 표에서는 외부 액세스(페더레이션) 사용과 게스트 사용 간의 차이점을 보여줍니다. 두 경우 모두 조직 외부 사용자는 외부에 있는 사용자로 식별됩니다.

### <a name="things-your-users-can-do"></a>사용자가 할 수 있는 일

| 사용자가 할 수 있음 | 외부 액세스 사용자 | 게스트 |
|---------|-----------------------|--------------------|
| 다른 조직에서 다른 사용자와 채팅 | 예 | 예 |
| 다른 조직에서 다른 사용자와 통화 | 예 | 예 |
| 다른 조직의 다른 사용자가 전화 또는 채팅을 할 수 있는지 확인 | 예 | 예<sup>1</sup> |
| 다른 조직의 사용자 검색 | 예<sup>2</sup> | 아니요 |
| 파일 공유 | 아니요 | 예 |
| 다른 조직의 사용자 부재 중 메시지 보기 | 아니요 | 예 |
| 다른 조직의 사용자 차단  | 아니요 | 예 |
| @멘션 사용 | 예<sup>3</sup> | 예 |

### <a name="things-people-outside-your-organization-can-do"></a>조직 외부 사용자가 할 수 있는 일

| 조직 외부 사용자가 할 수 있음 | 외부 액세스 사용자 | 게스트 |
|---------|-----------------------|--------------------|
| Teams 리소스에 액세스 | 아니요 | 예 |
| 그룹 채팅에 추가하기 | 예 | 예 |
| 모임에 초대하기 | 예 | 예 |
| 개인 전화 걸기 | 예 | 예<sup>5</sup> |
| 전화 접속 모임 참가자의 전화 번호 보기 | 아니요<sup>4</sup> | 예 |
| IP 비디오 사용 | 예 | 예<sup>5</sup> |
| 화면 공유 사용 | 예<sup>3</sup> | 예<sup>5</sup> |
| 모임 시작 사용 | 아니요 | 예<sup>5</sup> |
| 보낸 메시지 편집 | 예<sup>3</sup> | 예<sup>5</sup> |
| 보낸 메시지 삭제 | 예<sup>3</sup> | 예<sup>5</sup> |
| 대화에서 Giphy 사용 | 예<sup>3</sup> | 예<sup>5</sup> |
| 대화에서 밈 사용 | 예<sup>3</sup> | 예<sup>5</sup> |
| 대화에서 스티커 사용 | 예<sup>3</sup> | 예<sup>5</sup> |
| 현재 상태가 표시됩니다. | 예 | 예 |
| @멘션 사용 | 예<sup>3</sup> | 예 |

<br>

<sup>1</sup> 사용자가 게스트로 추가되어 있고 게스트 계정으로 로그인되어 있는 경우 제공됩니다.<br>
<sup>2</sup> 전자 메일 또는 SIP(Session Initiation Protocol) 주소만 해당됩니다.<br>
<sup>3</sup> 서로 다른 두 조직의 Teams 전용 사용자에게 Teams 전용 1:1 채팅이 지원됩니다. <br>
<sup>4</sup> 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음). 자세한 내용은 [Microsoft Teams에서 모임에 대한 입장 및 퇴장 알림 켜기 혹은 끄기](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)를 읽어보세요. <br>
<sup>5</sup> 기본적으로 허용되지만 Teams 관리자가 해제할 수 있습니다

## <a name="related-topics"></a>관련 항목

[Teams의 외부 액세스](manage-external-access.md)

[Teams의 게스트 액세스](guest-access.md)
