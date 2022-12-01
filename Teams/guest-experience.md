---
title: Microsoft Teams의 게스트 환경
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
description: 이 문서에서는 게스트가 사용할 수 있는 Microsoft Teams 기능에 대해 설명합니다.
ms.openlocfilehash: 960688d49f634ff5665fe4e1da2436e9bad669ac
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198910"
---
# <a name="guest-experience-in-teams"></a>Teams의 게스트 환경

게스트가 팀에 참여하도록 초대되면 환영 전자 메일 메시지를 받습니다. 이 메시지에는 팀에 대한 몇 가지 정보와 구성원이 되었으므로 예상되는 내용이 포함됩니다. 게스트는 팀 및 해당 채널에 액세스하려면 먼저 이메일 메시지에서 **Microsoft Teams 열기** 를 선택하여 초대를 수락해야 합니다.

> [!NOTE]
> 게스트가 팀에 추가된 후 액세스 권한이 부여되기까지 몇 시간이 걸릴 수 있습니다.
    
![환영 전자 메일 메시지의 예를 보여 주는 스크린샷](media/guest-experience-image1.png)
    
모든 팀 구성원은 채널 스레드에서 팀 소유자가 게스트를 추가했음을 알리는 메시지를 보고 게스트 이름을 제공합니다. 팀의 모든 사용자는 게스트가 누구인지 쉽게 식별할 수 있습니다. 채널 스레드의 오른쪽 위 모서리에 있는 태그는 팀의 게스트 수를 나타내고 **각 게스트 이름 옆에 (게스트)** 레이블이 표시됩니다.

![팀의 게스트 수를 나타내는 태그를 보여 주는 스크린샷](media/guest-experience-image2.png)

Teams의 게스트 환경에 대한 다음 비디오를 확인하세요.
- [게스트로 Teams 모임 참가](https://support.microsoft.com/office/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [Teams 모임에서 외부 게스트와 작업](https://support.microsoft.com/office/work-with-external-guests-180ed260-d3ef-4247-9f24-1984fc76d5f0)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>팀 구성원 및 게스트 기능 비교

다음 표에서는 조직의 팀 구성원과 게스트가 사용할 수 있는 Teams 기능을 비교합니다. Teams 관리자는 게스트가 사용할 수 있는 기능을 제어합니다.

| Teams의 기능 | 조직의 Teams 사용자 | 게스트 |
|:-----|:-----|:-----|
|채널 만들기  <br/>  *팀 소유자는 이 설정을 제어합니다.*  <br/> |&#x2713;|&#x2713;|
|비공개 채팅에 참여  <br/> |&#x2713;|&#x2713;|
|채널 대화에 참여  <br/> |&#x2713;|&#x2713;|
|메시지 게시, 삭제 및 편집  <br/> |&#x2713;|&#x2713;|
|채널 파일 공유  <br/> |&#x2713;|&#x2713;|
|SharePoint 파일 액세스<br/> |&#x2713;|&#x2713;|
|파일 첨부<br/> |&#x2713;|채널 게시물만|
|프라이빗 채팅 파일 다운로드<br/> |&#x2713;|&#x2713;|
|파일 내에서 검색<br/> |&#x2713;||
|채팅 파일 공유  <br/> |&#x2713;||
|앱 추가(탭, 봇 또는 커넥터)  <br/> |&#x2713;||
|모임 또는 액세스 일정 만들기  <br/> |&#x2713;||
|비즈니스용 OneDrive 스토리지에 액세스  <br/> |&#x2713;||
|테넌트 전체 및 팀/채널 게스트 액세스 정책 만들기  <br/> |&#x2713;||
|Microsoft 365 또는 Office 365 조직의 도메인 외부에 있는 사용자 초대 <br/>  *팀 소유자는 이 설정을 제어합니다.*  <br/> <br/> |&#x2713;||
|팀 만들기  <br/> |&#x2713;||
|공개 팀 검색 및 참가  <br/> |&#x2713;||
|조직도 보기  <br/> |&#x2713;||
|인라인 번역 사용  <br/> |&#x2713;||
|팀 소유자 되기  <br/> |&#x2713;||

다음 표에서는 다른 유형의 사용자에 비해 게스트가 사용할 수 있는 통화 및 모임 기능을 보여 줍니다.

| 호출 기능 | 게스트 | E1 및 E3 사용자 | E5 및 Enterprise Voice 사용자 |
| --------------- | ----- | -------------- | -------------- |
| VOIP 호출 | 예 | 예 | 예 |
| 그룹 호출 | 예 | 예 | 예 |
| 지원되는 핵심 통화 컨트롤(보류, 음소거, 비디오 켜기/끄기, 화면 공유) | 예 | 예 | 예 |
| 전송 대상 | 예 | 예 | 예 |
| 통화를 전송할 수 있습니다. | 예 | 예 | 예 |
| 상담 전이 가능 | 예 | 예 | 예 |
| VOIP를 통해 통화에 다른 사용자를 추가할 수 있습니다. | 예 | 예 | 예 |
| 전화 번호로 사용자를 통화에 추가할 수 있습니다. | 아니요 | 아니요 | 예 |
| 대상 전달 | 아니요 | 예 | 예 |
| 호출 그룹 대상 | 아니요 | 예 | 예 |
| 응답이 없는 대상 | 아니요 | 예 | 예 |
| 페더레이션 호출의 대상이 될 수 있습니다. | 아니요 | 예 | 예 |
| 페더레이션된 호출을 수행할 수 있습니다. | 아니요 | 예 | 예 |
| 통화를 즉시 전달할 수 있습니다. | 아니요 | 아니요 | 예 |
| 동시에 통화를 울릴 수 있습니다. | 아니요 | 아니요 | 예 |
| 응답되지 않은 통화를 라우팅할 수 있습니다. | 아니요 | 아니요 | 예 |
| 부재 중 전화는 음성 메일로 이동 가능 | 아니요 | 아니요<sup>1</sup> |예 |
| 전화를 받을 수 있는 전화 번호가 있습니다. | 아니요 | 아니요 | 예 |
| 전화 번호로 전화를 걸 수 있습니다. | 아니요 | 아니요 | 예 |
| 통화 설정에 액세스할 수 있습니다. | 아니요 | 아니요 | 예 |
| 음성 메일 인사말을 변경할 수 있습니다. | 아니요 | 아니요<sup>1</sup> | 예 |
| 벨소리를 변경할 수 있습니다. | 아니요 | 아니요  | 예 |
| TTY 지원 | 아니요 | 아니요 | 예 |
| 대리자를 가질 수 있습니다. | 아니요 | 아니요 | 예 |
|  대리자일 수 있습니다. | 아니요 | 아니요 | 예 |

<sup>1</sup> 이 기능은 곧 제공될 예정입니다.

> [!NOTE]
> Azure AD(Azure Active Directory)의 **게스트 사용자 액세스 제한** 정책은 디렉터리의 게스트에 대한 권한을 결정합니다. 세 개의 정책 옵션이 제공됩니다.
>  - **게스트 사용자는 구성원과 동일한 액세스 권한을 가짐(가장 포괄적)** 설정은 게스트가 디렉토리의 일반 사용자와 동일한 디렉토리 데이터 액세스 권한을 가짐을 의미합니다.
>  - **게스트 사용자는 디렉터리 개체 설정의 속성 및 구성원에 대한 액세스 권한이 제한되어 있음** 설정은 게스트가 Microsoft Graph를 사용하여 사용자, 그룹 또는 기타 디렉터리 리소스를 열거하는 것과 같은 특정 디렉터리 작업에 대한 권한이 없음을 의미합니다.
>  - **게스트 사용자 액세스는 자신의 디렉터리 개체의 속성 및 구성원으로 제한됨(가장 제한적)** 설정은 게스트가 자신의 디렉터리 개체에만 액세스 할 수 있음을 의미합니다.
>
>자세한 내용은 [Azure Active Directory의 기본 사용자 권한](/azure/active-directory/fundamentals/users-default-permissions)을 참조하세요.

## <a name="related-topics"></a>관련 주제

[조직을 게스트로 남겨 둡니다.](/azure/active-directory/b2b/leave-the-organization)

[게스트 액세스 및 외부 액세스를 사용하여 조직 외부 사용자와 공동 작업](communicate-with-users-from-other-organizations.md)
