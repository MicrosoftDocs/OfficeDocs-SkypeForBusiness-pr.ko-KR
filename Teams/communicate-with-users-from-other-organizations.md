---
title: Microsoft Teams에서 다른 조직의 사용자와 의사소통하기
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 외부 액세스 (페더레이션) 및 게스트 액세스를 사용하여 Microsoft Teams에서 다른 조직의 사용자와 의사소통하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 8676c45a386a9fb36571e3262a8c70769f45f0a6
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785280"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>Microsoft Teams에서 다른 조직의 사용자와 의사소통하기
======================================================

조직 외부의 사용자와 의사소통하고 공동 작업을 해야 하는 경우 Microsoft Teams에서 이 작업을 수행하는 두 가지 방법을 제공합니다. 첫 번째 – **외부 액세스** (페더레이션) - 다른 도메인의 사용자를 찾고, 사용자와 통화하고, 채팅할 수 있습니다 (예: contoso.com). 두 번째 – **게스트 액세스** - 전자 메일 주소를 사용하여 사용자를 게스트로 팀에 추가할 수 있습니다. 조직의 다른 사용자와 마찬가지로 게스트와 공동 작업을 할 수 있습니다.

원하는 경우에는 외부 액세스와 게스트 액세스를 모두 사용할 수 있습니다. 이들은 서로 방해되지 않습니다.

높은 수준에서 선택하는 방법 (자세한 비교를 위해 [외부 및 게스트 액세스 비교](#compare-external-and-guest-access)로 이동하세요):

## <a name="external-access"></a>외부 액세스

다른 도메인의 외부 사용자가 찾기, 전화하기, 채팅 및 모임을 설정할 수 있도록 허용하는 솔루션이 필요한 경우 **외부 액세스** (페더레이션)를 사용합니다. 외부 사용자는 조직의 팀 또는 팀 자원에 액세스할 수 없습니다. 비즈니스용 Skype (온라인 또는 온 프레미스) 나 Skype (2020년 초 제공예정)를 계속 사용하고 있는 외부 사용자와 의사소통하려는 경우 외부 액세스를 선택합니다. 

외부 액세스는 Teams에서 기본적으로 활성화되어 있습니다. 즉, 조직에서 모든 외부 도메인과 의사소통할 수 있습니다. Teams 관리자가 이 기능을 해제하거나 포함할(또는 제외) 도메인을 지정할 수 있습니다. 자세한 내용은 [외부 액세스 관리](manage-external-access.md)를 참조하세요. 

외부 사용자가 팀과 채널에 액세스할 수 있도록 하려면 [게스트 액세스](#guest-access)를 사용하는 것이 좋습니다. 


## <a name="guest-access"></a>게스트 액세스

**게스트 액세스**를 사용하여 개인 사용자(도메인에 상관없이)를 팀에 추가할 수 있으며, 팀에서 Microsoft 365이나 Office 365 앱(예: Word, Excel 또는 PowerPoint)을 사용하여 채팅, 전화, 모임 및 조직 파일 (SharePoint 또는 비즈니스용 OneDrive에 저장된)에 공동작업할 수 있습니다. 게스트 사용자는 기존 팀 구성원과 같은 거의 모든 Teams 권한을 부여받을 수 있습니다. 자세한 내용은 [Teams의 게스트 액세스](guest-access.md)를 참조하세요.

- 게스트는 조직의 Active Directory에 추가됩니다.
- 게스트와 의사소통하려면 게스트는 게스트 계정을 사용하여 Teams에 로그인해야 합니다. 즉, 게스트는 사용자의 Teams 계정에 로그인하기 위해 자신의 Teams 계정에서 로그아웃해야 합니다.
- 게스트 사용자는 외부 액세스 (페더레이션) 사용자 보다 Teams에서 더 많은 리소스 (예: 파일, 팀 및 채널)에 액세스할 수 있습니다.
- Teams 관리자는 Teams 관리 센터에서 게스트가 수행할 수 있는 (또는 수행할 수 없는) 모든 항목을 제어합니다. 자세한 내용은 [게스트 액세스 관리](manage-guests.md)를 참조하세요.

조직에서 게스트 액세스를 활성화할 준비가 되면 [게스트 액세스 검사 목록](guest-access-checklist.md)에서 시작합니다.


## <a name="compare-external-and-guest-access"></a>외부 및 게스트 액세스 비교

| 기능 | 외부 액세스 사용자 | 게스트 액세스 사용자 |
|---------|-----------------------|--------------------|
| 사용자는 다른 회사의 사용자와 채팅할 수 있습니다. | 예 |예 |
| 사용자는 다른 회사의 사용자와 통화할 수 있습니다. | 예 | 예 |
| 사용자는 다른 회사의 다른 사용자가 전화를 하거나 채팅을 할 수 있는지 확인할 수 있습니다. | 예 | 예<sup>1</sup> |
| 사용자가 외부 테넌트에서 사용자를 검색할 수 있습니다. | 예<sup>2</sup> | 아니요 |
| 사용자는 파일을 공유할 수 있습니다. | 아니요 | 예 |
| 사용자는 Teams 자원에 액세스할 수 있습니다. | 아니요 | 예 |
| 그룹 채팅에 사용자를 추가할 수 있습니다. | 아니요 | 예 |
| 사용자를 모임에 초대할 수 있습니다. | 예 | 예 |
| 외부 사용자와의 채팅에 다른 사용자를 추가할 수 있습니다. | 아니요<sup>3</sup> | 해당 없음 |
| 사용자는 외부 대상으로 식별됩니다. | 예 | 예 |
| 현재 상태가 표시됩니다. | 예 | 예 |
| 부재 중 메시지가 표시됩니다. | 아니요 | 예 |
| 개별 사용자를 차단할 수 있습니다. | 아니요 | 예 |
| @멘션을 지원합니다. | 예<sup>4</sup> | 예 |
| 개인 전화 걸기 | 예 | 예 |
| 전화 접속 모임 참가자의 전화 번호 보기 | 아니요<sup>5</sup> | 예 |
| IP 비디오 허용 | 예 | 예 |
| 화면 공유 모드 | 예<sup>4</sup> | 예 |
| 모임 시작 허용 | 아니요 | 예 |
| 보낸 메시지 편집 | 예<sup>4</sup> | 예 |
| 보낸 메시지를 삭제할 수 있습니다. | 예<sup>4</sup> | 예 |
| 대화에서 Giphy 사용 | 예<sup>4</sup> | 예 |
| 대화에서 밈 사용 | 예<sup>4</sup> | 예 |
| 대화에서 스티커 사용 | 예<sup>4</sup> | 예 |
||||

<sup>1</sup> 사용자가 게스트로 추가되어 있고 게스트 테넌트에 게스트로 로그인되어 있는 경우.<br>
<sup>2</sup> 전자 메일 또는 SIP(Session Initiation Protocol) 주소만 해당.<br>
<sup>3</sup> 외부 (페더레이션) 채팅은 1:1만 허용합니다.<br>
<sup>4</sup> Teams의 1:1 채팅은 Teams에서만, 다른 두 조직의 사용자만 지원됩니다. <br>
<sup>5</sup> 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음). 자세한 내용은 [Microsoft Teams에서 모임에 대한 입장 및 퇴장 알림 켜기 혹은 끄기](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)를 읽어보세요.

## <a name="related-topics"></a>관련 항목

[Teams의 외부 액세스](manage-external-access.md)

[Teams의 게스트 액세스](guest-access.md)

