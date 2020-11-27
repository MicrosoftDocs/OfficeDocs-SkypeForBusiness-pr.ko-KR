---
title: Microsoft Teams의 제한 사항 및 사양
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6132f9ec0936a4c076520b8e7a900a7d496f3aec
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420928"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams의 제한 사항 및 사양

이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.

## <a name="teams-and-channels"></a>팀 및 채널

|기능    | 최대 한도 |
|-----------|---------------|
|사용자가 만들 수 있는 팀의 수 | 250개체 제한 적용&sup1;         |
|사용자가 구성원이 될 수 있는 그룹 수|1,000&sup2;|
|팀의 구성원 수 | 10,000<sup>5</sup>     |
|팀당 소유자 수 | 100   |
|테넌트에 허용되는 조직 전체 팀 수 | 5     |
|[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수 | 5,000       |
|전역 관리자가 만들 수 있는 팀의 수        |  500,000   |
|Microsoft 365 또는 Office 365 조직이 보유할 수 있는 팀 개수    | 500,000&sup2;     |
|팀당 채널 수    | 200(삭제된 채널 포함)&sup3;         |
|팀당 비공개 채널 수    |30| (삭제된 채널 포함)&sup3;
|비공개 채널 회원수    |250|
|Office 365 그룹에서 팀으로 전환할 수 있는 최대 구성원 수    |10,000<sup>5</sup>     |
|채널 대화 게시 크기 | 게시물당 28 KB<sup>4</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).

<sup>2</sup> 이 제한에는 보관된 팀이 포함됩니다. Microsoft 365 또는 Office 365 조직에 포함할 수 있는 최대 팀 수를 초과하려면 Microsoft 지원팀에 문의해야 합니다.

<sup>3</sup> 삭제된 채널은 30일 이내에 복원할 수 있습니다. 30일 동안에는 삭제된 채널이 계속해서 팀당 200개 채널이나 30개의 개인 채널에 포함됩니다. 30일 후에는 삭제된 채널과 해당 콘텐츠가 영구적으로 삭제되고 채널은 더 이상 팀당 한도에 포함되지 않습니다.

<sup>4</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 커넥터 수, 반응이 포함되기 때문에 대략적인 한도입니다.

<sup>5</sup> GCC Teams에서는 5,000명만 수용할 수 있고 GCCH/DoD Teams에서는 2,500명만 수용할 수 있습니다.

## <a name="messaging"></a>메시징

### <a name="chat"></a>채팅

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)

Teams 채팅은 Microsoft Exchange 백 엔드에서 작동하므로 Exchange 메시징 제한은 Teams 내의 채팅 기능에 적용됩니다.

|기능  | 최대 한도  |
|---------|---------|
|비공개 채팅에 참가 중인 사용자 수<sup>1</sup>  | 250 |
|채팅에서 영상 또는 음성 통화 중인 사용자 수 | 20 |
|첨부 파일 수<sup>2</sup>  |10     |
|채팅 크기 | 게시물당 28 KB<sup>3</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup>첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.

<sup>3</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 반응이 포함되기 때문에 대략적인 한도입니다.

### <a name="emailing-a-channel"></a>채널 전자 메일 보내기 

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|기능  | 최대 한도  |
|---------|---------|
|메시지 크기<sup>1<sup> | 24KB |
|첨부 파일 수<sup>2</sup>  |20     |
|각 첨부 파일의 크기 | 10MB 미만 |
|인라인 이미지 수<sup>2</sup> |50   |

<sup>1</sup>메시지가 이 한도를 초과하는 경우 미리 보기 메시지가 생성되고, 사용자에게 제공된 링크에서 원본 전자 메일을 다운로드하여 확인하라는 메시지가 표시됩니다.

<sup>2</sup>첨부 파일이나 이미지 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.

자세한 내용은 [Exchange Online 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)을 참조하세요.

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>채널 이름

채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.

|유형|예제|
|---------|---------|
|문자     | ~ # % & * { } + / \ : < > ? &#124; ' " , .        |
|이러한 범위에 있는 문자    | 0~1F<br>80~9F        |
|단어     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;|

또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.

## <a name="meetings-and-calls"></a>모임 및 통화

> [!IMPORTANT]
> **Microsoft 365 라이브 이벤트 한도가 늘어납니다**
>
> **고객 지원을 돕기 위해 2021년 1월 1일까지 Teams, Stream 및 Yammer에서 주최하는 라이브 이벤트에 대해 임시 제한 증가를 연장합니다.**
>
>- 이벤트당 최대 20,000명의 참석자가 참석합니다.
>- Teams 테넌트당 최대 50개의 동시 이벤트입니다.
>- 브로드캐스트당 최대 16시간
>
> 추가로 참가자 최대 100,000명의 라이브 이벤트는 Microsoft 365 지원 프로그램을 통해 계획할 수 있습니다. 팀에서 각 요청을 평가하고 사용자와 작업을 수행하여 사용 가능한 옵션을 결정합니다. [자세히 알아보세요](https://aka.ms/Stream/Blog/LiveEventOptions). **2021년 1월 1일 이후 이 한도 증가를 피요로 하는 고객은 [고급 통신 추가 항목](teams-add-on-licensing/advanced-communications.md)을 구매해야 합니다.**

|기능     | 최대 한도 |
|------------|---------------|
|모임에 참가 중인 사용자 수(채팅 및 전화를 걸 수 있음)  | 350 |
|채팅에서 영상 또는 음성 통화 중인 사용자 수 | 20 |
|최대 PowerPoint 파일 크기 | 2GB|
|Teams는 Microsoft Stream에 업로드되지 않는 [모임 녹음/녹화](cloud-recording.md)를 보관하여 로컬로 다운로드할 수 있습니다. | 20일 |

>[!Note]
> Microsoft Stream의 사용에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](tmr-meeting-recording-change.md)로의 변경은 단계별 접근 방식을 사용합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우, 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.

### <a name="meeting-expiration"></a>모임 만료

|모임 유형  |이만큼 시간이 지나면 모임이 만료됩니다.  |모임을 시작하거나 업데이트할 때마다 만료 시간이 이 시간만큼 연장됩니다.  |
|---------|---------|---------|
|모임 시작     |시작 시간 + 8시간         |해당 없음         |
|정규(종료 시간 없음)     |시작 시간 + 60일         | 60일        |
|정규(종료 시간 있음)     |종료 시간 + 60일         |60일         |
|되풀이(종료 시간 없음)     |시작 시간 + 60일         |60일         |
|되풀이(종료 시간 있음)     |마지막 발생 항목의 종료 시간 + 60일         |60일         |

> [!NOTE]
> Microsoft Teams 모임의 제한 시간은 24시간입니다.

## <a name="teams-live-events"></a>Teams 라이브 이벤트

|기능     | 최대 한도 |
|------------|---------------|
|대상 그룹 크기 | 10,000 참석자 |
|이벤트 기간 | 4시간 |
|Microsoft 365 또는 Office 365 조직에서 실행되는 동시 발생 라이브 이벤트 <sup>1</sup> | 15 |

<sup>1</sup> 여러 라이브 이벤트를 원하는 대로 예약할 수 있지만, 한 번에 15개만 실행할 수 있습니다. 프로듀서가 라이브 이벤트에 참가하는 즉시 실행 중인 것으로 간주합니다. 16번째 라이브 이벤트에 참가하려고 시도하는 프로듀서는 오류 메시지를 받게 됩니다.

라이브 이벤트 및 Teams 라이브 이벤트와 Skype 모임 브로드캐스트 비교에 대한 자세한 내용은 [Teams 라이브 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참조하세요. 또한 [Teams 라이브 이벤트 예약](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)을 참조하세요.

> [!IMPORTANT]
> **Microsoft 365 라이브 이벤트 한도 증가**
>
> **고객 지원을 돕기 위해 2021년 1월 1일까지 Teams, Stream 및 Yammer에서 주최하는 라이브 이벤트에 대해 임시 제한 증가를 연장합니다.**
>
> - 이벤트당 최대 20,000명의 참석자가 참석합니다.
> - Teams 테넌트당 최대 50개의 동시 이벤트입니다.
> - 브로드캐스트당 최대 16시간
>
> 추가로 참가자 최대 100,000명의 라이브 이벤트는 Microsoft 365 지원 프로그램을 통해 계획할 수 있습니다. 팀에서 각 요청을 평가하고 사용자와 작업을 수행하여 사용 가능한 옵션을 결정합니다. [자세히 알아보세요](https://aka.ms/Stream/Blog/LiveEventOptions). **2021년 1월 1일 이후 이 한도 증가를 피요로 하는 고객은 [고급 통신 추가 항목](teams-add-on-licensing/advanced-communications.md)을 구매해야 합니다.**

## <a name="presence-in-outlook"></a>Outlook에서의 현재 상태

Outlook에서의 Teams 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다. Teams의 현재 상태에 대해 자세히 알아보려면 [Teams에서 사용자 현재 상태](presence-admins.md)를 참조하세요..

## <a name="storage"></a>저장소

Microsoft Teams의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에 폴더가 있습니다. 대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에서 설정된 사용 권한 및 파일 보안 옵션은 Teams 내에서 자동으로 반영됩니다.

> [!NOTE]
> 각 [개인 채널](https://docs.microsoft.com/microsoftteams/private-channels)에는 고유한 SharePoint 사이트 모음이 있습니다.

테넌트에서 SharePoint Online을 사용하도록 설정하지 않은 경우, Microsoft Teams 사용자는 팀에서 파일을 항상 공유할 수 없습니다. 비즈니스용 OneDrive(SharePoint 라이선스에 연결됨)가 해당 기능에 필요하므로 개인 채팅 사용자도 파일을 공유할 수 없습니다.

SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면, 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다. (자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.) 

Teams는 파일 공유를 위해 SharePoint Online 백 엔드에서 실행되므로 SharePoint 제한 사항은 Teams 내의 파일 섹션에 적용됩니다. 다음은 SharePoint Online에 적용되는 저장소 용량 한도입니다.

|기능                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|저장소                 |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB 및 구매한 라이선스당 10GB   |조직당 1TB 및 구매한 라이선스당 10GB |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB           |
|Teams 파일용 저장소 |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |
|파일 업로드 제한(파일당)    |2GB    |2GB    |2GB    |2GB    |2GB    |2GB    |

채널은 팀에 대해 생성된 SharePoint Online 사이트 모음 내의 폴더로 백업되므로 채널 내의 파일 탭은 자신이 속한 팀의 저장소 제한을 공유합니다.

자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.

## <a name="class-teams"></a>수업 팀

교육용 Microsoft Teams는 교실 수업과 같은 고유한 교육 시나리오를 위해 설계된 템플릿을 제공합니다. 수업 팀을 포함한 팀 유형에 대한 자세한 내용은 [Microsoft Teams에서 공동 작업할 팀 유형 선택](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)에서 확인할 수 있습니다.

한 개의 수업 팀은 추가 앱이 포함된 템플릿 유형이며, 팀 구성원의 수에 제한이 있습니다.

> [!NOTE]
> 수업 팀을 사용하려면 [Office 365 Education 라이선스](https://www.microsoft.com/education/products/office)가 필요합니다.

수업 팀 제한은 다음 표에 나열되어 있습니다.

|기능  |최대 한도  |
|---------|---------|
|팀의 구성원 수    | 이 문서의 [Teams 및 채널](#teams-and-channels) 섹션을 참조합니다.        |
|수업 팀에서 할당을 사용할 구성원 수    | 200        |
|수업 팀에서 OneNote 클래스 노트북을 사용할 구성원 수     |200         |

한 개의 수업 팀은 200명 이상의 구성원을 지원할 수 있습니다. 그러나 팀 내에서 과제 앱 또는 수업용 전자 필기장 앱을 사용하려는 경우, 구성원 수를 위의 최대 한도 이하로 유지해야 합니다.

## <a name="tags"></a>태그

|기능  |최대 한도  |
|---------|---------|
|팀당 태그 수    | 100        |
|팀당 제안된 기본 태그 수    | 25        |
|태그에 할당되는 팀 구성원 수    |100         |
|사용자에게 할당되는 태그 수    |25         |

## <a name="contacts"></a>연락처

Teams에서 사용하는 연락처:

- 조직의 Active Directory에 있는 연락처
- 사용자의 Outlook 기본 폴더에 추가된 연락처

Teams 사용자는 조직의 Active Directory에 있는 모든 사용자와 커뮤니케이션할 수 있으며, 조직의 Active Directory에 있는 모든 사용자를 **채팅** > **연락처** 또는 **통화** > **연락처** 로 이동하여 대화 상대 및 대화 상대 목록에 추가할 수 있습니다.

팀 사용자는 조직 내의 Active Directory에 없는 사용자를 **통화** > **연락처** 로 이동하여 연락처로 추가할 수도 있습니다.

## <a name="browsers"></a>브라우저

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>운영 체제

운영 체제 요구 사항에 대한 자세한 내용은 [Microsoft Teams용 클라이언트 다운로드](get-clients.md)를 참조하세요.
