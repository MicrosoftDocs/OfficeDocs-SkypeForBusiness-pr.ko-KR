---
title: Microsoft Teams의 제한 사항 및 사양
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: 이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.
ms.localizationpriority: high
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee791259b938345876e9761344616fac7d1d9e45
ms.sourcegitcommit: 3056f95e9f654b78636949f43eacdde297e52c6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2023
ms.locfileid: "69990413"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams의 제한 사항 및 사양

이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.

## <a name="teams-and-channels"></a>팀 및 채널

|기능    | 최대 한도 |
|-----------|---------------|
|사용자가 만들 수 있는 팀의 수 | 250개체 제한 적용&sup1;         |
|사용자가 구성원이 될 수 있는 그룹 수|1,000&sup2;|
|팀의 구성원 수 | 25,000<sup>6</sup>     |
|팀당 소유자 수 | 100   |
|테넌트에 허용되는 조직 전체 팀 수 | 5&sup2;     |
|[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수 | 10,000       |
|전역 관리자가 만들 수 있는 팀의 수        |  500,000   |
|Microsoft 365 또는 Office 365 조직이 보유할 수 있는 팀 개수    | 500,000&sup3;     |
|팀당 채널 수    | 200(삭제된 채널 포함)<sup>4</sup>        |
|팀당 비공개 채널 수    |30(삭제된 채널 포함)<sup>4</sup>        |
|비공개 채널 회원수    |250|
|팀으로 가져올 수 있는 메일 그룹, 보안 그룹 또는 Microsoft 365 그룹의 최대 크기    |3,500|
|팀으로 변환할 수 있는 Microsoft 365 그룹의 최대 구성원 수    |10,000<sup>6</sup>     |
|채널 대화 게시 크기 | 게시물당 약 28KB<sup>5</sup> |

<sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](/graph/permissions-reference).

<sup>2</sup> 이 제한에는 보관된 팀이 포함됩니다. 

<sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant. Increase is only made for real-life production scenarios.

<sup>4</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.

<sup>5</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 커넥터 수, 반응이 포함되기 때문에 대략적인 한도입니다.

<sup>6</sup> 팀 외부의 공유 채널 구성원 수 제한에 도달했습니다. 또한 팀/채널 멘션은 10,000명이 넘는 구성원이 있는 팀에서 차단됩니다.

> [!NOTE]
> 공유 채널에 대한 제한은 [공유 채널에 대한 제한](/MicrosoftTeams/shared-channels#limits-for-shared-channels)을 참조하세요.

## <a name="messaging"></a>메시징

### <a name="chat"></a>채팅

Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)


|기능  | 최대 한도  |
|---------|---------|
|비공개 채팅에 참가 중인 사용자 수<sup>1</sup>  | 250<sup>2</sup> |
|채팅에서 영상 또는 음성 통화 중인 사용자 수 | 20 |
|첨부 파일 수<sup>3</sup>  |10     |
|채팅 크기 | 게시물당 약 28KB<sup>4</sup> |

<sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.

<sup>2</sup> Only 200 members at a time can be added to a group chat. [See this article for more information](/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).

<sup>3</sup> 첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.

<sup>4</sup> 28KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션 그리고 반응을 포함하기 때문에 대략적인 한도입니다.

### <a name="emailing-a-channel"></a>채널 전자 메일 보내기 

 If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.

|기능  | 최대 한도  |
|---------|---------|
|메시지 크기<sup>1<sup> | 24KB |
|첨부 파일 수<sup>2</sup>  |20     |
|각 첨부 파일의 크기 | 10MB 미만 |
|인라인 이미지 수<sup>2</sup> |50   |

> [!NOTE]
> 채널에 보낼 수 있는 전자 메일 수에는 제한이 있습니다. 제한은 사용자당 채널당 10초당 6개의 이메일이고 사용자당 테넌트당 10초당 8개의 이메일입니다.
<sup>1</sup>메시지가 이 한도를 초과하는 경우 미리 보기 메시지가 생성되고, 사용자에게 제공된 링크에서 원본 전자 메일을 다운로드하여 확인하라는 메시지가 표시됩니다.

<sup>2</sup>첨부 파일이나 이미지 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.

자세한 내용은 [Exchange Online 제한](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)을 참조하세요.

> [!NOTE]
> Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.

## <a name="channel-names"></a>채널 이름

채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.

|유형|예제|
|---------|---------|
|문자     | ~ # % & * { } + / \ : < > ? &#124; ' " , ..        |
|이러한 범위에 있는 문자    | 0~1F<br>80~9F        |
|단어     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;|

또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.

## <a name="meetings-and-calls"></a>모임 및 통화

|기능     | 최대 한도 |
|------------|---------------|
|모임에 참가 중인 사용자 수(채팅 및 전화를 걸 수 있음)  | 1000에는 GCC, GCCH 및 DoD가 포함되지만 A1(300)은 포함되지 않습니다.|
|채팅에서 영상 또는 음성 통화 중인 사용자 수 | 20 |
|최대 PowerPoint 파일 크기 | 2GB|
|Teams는 Microsoft Stream에 업로드되지 않은 [모임 녹화](cloud-recording.md)를 보관하며 로컬로 다운로드할 수 있습니다. | 20일 |
| 모임 녹음/녹화 최대 길이 | 4시간 또는 1.5GB. 이 한도에 도달하면 녹음/녹화가 종료되고 자동으로 다시 시작됩니다.

자세한 내용은 [모임, 웨비나 및 라이브 이벤트를 참조하세요](/microsoftteams/quick-start-meetings-live-events).  
  
> [!NOTE]
> 소규모 회의실은 참석자 수가 300명 미만인 모임에서만 만들 수 있습니다. 또한 모임에 소규모 회의실을 만들면 모임 참석자 수가 자동으로 300명으로 제한됩니다. 최종 사용자에게 300명 이상의 참가자가 필요한 모임에서 소규모 회의실을 시작하지 않도록 권고하세요. 대규모 Teams 모임에 대한 자세한 내용은 [대규모 Teams 모임 대한 모범 사례](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16) 지침을 최종 사용자와 공유하세요.

### <a name="meeting-expiration"></a>모임 만료

> [!NOTE]
> A meeting URL will never stop working. The expiry only relates to any PSTN dial-in numbers, CVI coordinates, and/or underlying meeting policies and settings.

|모임 유형  |이만큼 시간이 지나면 모임이 만료됩니다.  |모임을 시작하거나 업데이트할 때마다 만료 시간이 이 시간만큼 연장됩니다.  |
|---------|---------|---------|
|모임 시작     |시작 시간 + 8시간         |해당 없음         |
|정규(종료 시간 없음)     |시작 시간 + 60일         | 60일        |
|정규(종료 시간 있음)     |종료 시간 + 60일         |60일         |
|되풀이(종료 시간 없음)     |시작 시간 + 60일         |60일         |
|되풀이(종료 시간 있음)     |마지막 발생 항목의 종료 시간 + 60일         |60일         |

> [!NOTE]
> Microsoft Teams 모임의 제한 시간은 30시간입니다.

## <a name="live-events"></a>라이브 이벤트
  
라이브 이벤트는 조직에서 최대 20,000명의 대규모 온라인 대상 그룹에게 스트리밍되는 이벤트를 예약하고 제작할 수 있는 구조화된 모임입니다. 라이브 이벤트에서 대상 그룹과의 상호 작용은 관리되는 질문 및 답변 환경입니다.

|기능     | 최대 한도 |
|------------|---------------|
|대상 그룹 크기 | 최대 20,000명의 참석자 <sup>1</sup> |
|이벤트 기간 | 4시간 |
|Microsoft 365 또는 Office 365 조직 <sup>2</sup>에서 실행되는 동시 라이브 이벤트 | 15 |

<sup>1</sup> 일반적인 10,000은 2023년 6월 30일까지 20,000으로 증가합니다. Yammer 및/또는 Microsoft Stream의 라이브 이벤트로 더 많은 수를 예약할 수 있습니다. 자세한 내용은 [Microsoft 365의 라이브 이벤트](/stream/live-event-m365)를 참조하세요. 참석자가 20,000명이 넘는 이벤트에는 [라이브 이벤트 지원 프로그램](/stream/live-events-assistance)이 필요합니다.  
  
<sup>2</sup> 원하는 만큼 라이브 이벤트를 예약할 수 있지만 한 번에 15개만 실행할 수 있습니다. 프로듀서가 라이브 이벤트에 참가하는 즉시 실행 중인 것으로 간주합니다. 16번째 라이브 이벤트에 참가하려고 시도하는 프로듀서는 오류 메시지를 받습니다.

라이브 이벤트에 대한 자세한 내용은 [Teams 라이브 이벤트](teams-live-events/plan-for-teams-live-events.md#teams-live-events)로 이동하세요. [Teams 라이브 이벤트 예약](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)을 참조하세요.

> [!IMPORTANT]
> **Microsoft 365 라이브 이벤트 한도 증가**
>
> **고객의 요구 사항을 계속 지원하기 위해 다음을 포함하여 2023년 6월 30일까지 라이브 이벤트에 대한 임시 제한 증가를 연장합니다.**
>
>- 최대 20,000명의 참석자를 위한 이벤트 지원
>- 한 테넌트에 걸쳐 동시에 50개의 이벤트가 호스트될 수 있습니다.
>- 브로드캐스트당 16시간의 이벤트 시간
>
> Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

## <a name="presence-in-outlook"></a>Outlook에서의 현재 상태

Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).

## <a name="storage"></a>저장소

Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.

> [!NOTE]
> 각 [개인 채널](./private-channels.md)에는 고유한 SharePoint 사이트 모음(이전에 “사이트 모음”이라 불림)이 있습니다.

If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.

By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)

Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.

|기능                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|저장소                 |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB 및 구매한 라이선스당 10GB   |조직당 1TB 및 구매한 라이선스당 10GB |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB           |
|Teams 파일용 저장소 |사이트 또는 그룹당 최대 25TB |사이트 또는 그룹당 최대 25TB |사이트 또는 그룹당 최대 25TB |사이트 또는 그룹당 최대 25TB |사이트 또는 그룹당 최대 25TB |사이트 또는 그룹당 최대 25TB |
|파일 업로드 제한(파일당)    |250GB    |250GB    |250GB    |250GB    |250GB    |250GB    |

채널은 팀에 대해 생성된 SharePoint Online 사이트 모음(이전에 “사이트 모음”이라 불림) 내의 폴더로 백업되므로 채널 내의 파일 탭은 자신이 속한 팀의 저장소 제한을 공유합니다.

자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.

## <a name="class-teams"></a>수업 팀

Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).

한 개의 수업 팀은 추가 앱이 포함된 템플릿 유형이며, 팀 구성원의 수에 제한이 있습니다.

> [!NOTE]
> 수업 팀을 사용하려면 [Office 365 Education 라이선스](https://www.microsoft.com/education/products/office)가 필요합니다.

수업 팀 제한은 다음 표에 나열되어 있습니다.

|기능  |최대 한도  |
|---------|---------|
|팀의 구성원 수    | 이 문서의 [Teams 및 채널](#teams-and-channels) 섹션을 참조합니다.        |
|수업 팀에서 할당을 사용할 구성원 수    | 300        |
|수업 팀에서 OneNote 클래스 노트북을 사용할 구성원 수     |300         |

A class team can support more than 300 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.

## <a name="tags"></a>태그

|기능  |최대 한도  |
|---------|---------|
|팀당 태그 수    | 100        |
|팀당 제안된 기본 태그 수    | 25        |
|태그에 할당되는 팀 구성원 수    |200         |
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
