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
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bddd4ffb268e641a7c89fe1ffd33efb91aba0b11
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361648"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft Teams의 제한 사항 및 사양

이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.

## <a name="teams-and-channels"></a>팀 및 채널

|기능    | 최대 한도 |
|-----------|---------------|
|사용자가 만들 수 있는 팀의 수 | 250개체 제한 적용&sup1;         |
|사용자가 구성원이 될 수 있는 그룹 수|1,000&sup2;|
|팀의 구성원 수 | 10,000       |
|팀당 소유자 수 | 100   |
|테넌트에 허용되는 조직 전체 팀 수 | 5     |
|[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수 | 5,000       |
|전역 관리자가 만들 수 있는 팀의 수        |  500,000   |
|Microsoft 365 또는 Office 365 조직이 보유할 수 있는 팀 개수    | 500,000&sup2;     |
|팀당 채널 수    | 200(삭제된 채널 포함)&sup3;         |
|팀당 비공개 채널 수    |30|
|비공개 채널 회원수    |250|
|Office 365 그룹에서 팀으로 전환할 수 있는 최대 구성원 수    |10,000|
|채널 대화 게시 크기 | 게시물당 28 KB<sup>4</sup> |

<sup>1</sup> Azure Active Directory의 모든 디렉터리 개체는 이 제한에 포함됩니다. 전역 관리자는 [응용 프로그램 사용 권한](https://docs.microsoft.com/graph/permissions-reference)을 사용하여 Microsoft Graph를 호출하는 앱과 마찬가지로 이 제한에서 제외됩니다.

<sup>2</sup>이 제한에는 보관된 팀이 포함됩니다. 최대 한도를 초과하는 경우 Microsoft 지원에 문의해야 합니다.

<sup>3</sup>삭제된 채널은 30일 이내에 복원될 수 있습니다. 이 30일 동안에는 삭제된 채널이 팀당 200채널 한도에 계속 포함됩니다. 30일 후에는 삭제된 채널과 해당 콘텐츠가 영구적으로 삭제되고 채널이 더 이상 팀당 200채널 한도에 포함되지 않습니다.

<sup>4</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 커넥터 숫자, 반응이 포함되기 때문에 대략적인 한도입니다.

## <a name="messaging"></a>메시징

### <a name="chat"></a>채팅

Teams의 채팅 목록의 일부인 대화에 참여하는 사용자는 관리자가 채팅 대화를 검색할 수 있도록 Exchange Online(클라우드 기반) 사서함이 있어야 합니다. 채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장되기기 때문입니다. 채팅 참가자에게 Exchange Online 사서함이 없는 경우 관리자는 채팅 대화에 대한 보류 또는 저장을 수행할 수 없습니다. 예를 들어 Exchange 하이브리드 배포에서는 온-프레미스 사서함이 있는 사용자가 Teams 채팅 목록에 포함된 대화에 참여할 수 있습니다. 하지만 이 경우에는 사용자에게 클라우드 기반 사서함이 없으므로 이 대화의 콘텐츠를 검색할 수 없고 보류 상태로 둘 수 없습니다. (자세한 내용은 [Exchange와 Microsoft Teams의 상호 작용 방식](exchange-teams-interact.md)을 참조하세요.)

Teams 채팅은 Microsoft Exchange 백 엔드에서 작동하므로 Exchange 메시징 제한은 Teams 내의 채팅 기능에 적용됩니다.

|기능  | 최대 한도  |
|---------|---------|
|비공개 채팅에 참가 중인 사용자 수<sup>1</sup>  | 250 |
|채팅에서 영상 또는 음성 통화 중인 사용자 수 | 20 |
|첨부 파일 수<sup>2</sup>  |10     |
|채팅 크기 | 게시물당 28 KB<sup>3</sup> |

<sup>1</sup>채팅에 20명 이상의 사용자가 있는 경우 다음과 같은 채팅 기능이 꺼집니다. Outlook 자동 회신 및 Teams 상태 메시지, 입력 표시기, 비디오 및 오디오 통화, 공유, 읽음 확인. 개인 그룹 채팅에 20명 이상의 구성원이 포함 된 경우에도 "배달 옵션 설정" 단추 (!)가 제거 됩니다.

<sup>2</sup>첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.

<sup>3</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 반응이 포함되기 때문에 대략적인 한도입니다.

### <a name="emailing-a-channel"></a>채널 전자 메일 보내기 

 사용자가 Teams의 채널에 전자 메일을 보내려면 채널 전자 메일 주소를 사용합니다. 전자 메일이 채널의 일부인 경우 누구나 답장을 보내 대화를 시작할 수 있습니다. 다음은 채널에 전자 메일을 보낼 때 적용되는 몇 가지 제한 사항입니다.

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
> 모든 Microsoft 365 및 Office 365 라이선스에서 메시지 크기, 첨부 파일 및 인라인 이미지 제한이 동일합니다.

## <a name="channel-names"></a>채널 이름

채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.

|||
|---------|---------|
|문자     | ~ # % & * { } + / \ : < > ? &#124; ' " , .        |
|해당 범위에 있는 문자    | 0~1F<br>80~9F        |
|단어     | forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;|

또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.

## <a name="meetings-and-calls"></a>모임 및 통화

> [!IMPORTANT]
> **Microsoft 365 라이브 이벤트 한도가 늘어납니다**
>
> **고객 지원을 돕기 위해 2021년 1월 1일까지 Teams, Stream 및 Yammer에서 주최하는 라이브 이벤트에 대해 임시 제한 증가를 연장합니다(** 포함).
>
>- 이벤트당 최대 20,000명의 참석자가 참석합니다.
>- Teams 테넌트당 최대 50개의 동시 이벤트입니다.
>- 브로드캐스트당 최대 16시간입니다.
>
> 추가로 참가자 100,000명 이상의 라이브 이벤트는 Microsoft 365 지원 프로그램을 통해 계획 할 수 있습니다. 팀에서 각 요청을 평가하고 사용자와 작업을 수행하여 사용 가능한 옵션을 결정합니다. [자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions)를 확인합니다. **2021년 1월 1일 이후 이러한 제한 증가가 필요한 고객은 [고급 통신 추가 기능](teams-add-on-licensing/advanced-communications.md)을 구입해야 합니다.**


|기능     | 최대 한도 |
|------------|---------------|
|모임에 참가 중인 사용자 수(채팅 및 전화를 걸 수 있음)  | 300 |
|채팅에서 영상 또는 음성 통화 중인 사용자 수 | 20 |
|최대 PowerPoint 파일 크기 | 2GB|
|Teams는 Microsoft Stream에 업로드되지 않은 [모임 녹화](cloud-recording.md)를 보관하며 로컬로 다운로드할 수 있습니다. | 20일 |

>[!Note]
> Microsoft Stream에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](tmr-meeting-recording-change.md)로의 변경은 단계별로 접근합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 새 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.

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

<sup>1</sup> 여러 라이브 이벤트를 원하는 대로 예약할 수 있지만, 한 번에 15개만 실행할 수 있습니다. 프로듀서가 라이브 이벤트에 참가하는 즉시 실행 중인 것으로 간주합니다. 16번째 라이브 이벤트에 참가하려고 시도하는 프로듀서는 오류 메시지를 받습니다.

라이브 이벤트와 Teams 라이브 이벤트와 Skype 모임 브로드캐스트 비교에 대한 자세한 내용은 [Teams 라이브 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참조하세요.

> [!IMPORTANT]
> **Microsoft 365 라이브 이벤트 한도가 늘어납니다**
>
> 고객이 급변하는 커뮤니케이션 요구를 충족할 수 있도록 Teams, Stream, Yammer에서 주최하는 라이브 이벤트에 대해 2021년 1월 1일까지 한시적으로 기본값 제한을 상향 조정하겠습니다.
>
> - 참석자 제한: 이벤트는 최대 20,000명의 참석자를 지원할 수 있습니다.
> - 동시 이벤트: 한 테넌트에 걸쳐 동시에 50개의 이벤트 호스트가 가능
> - 이벤트 기간: 이벤트 시간이 브로드캐스트 당 16시간으로 늘어났습니다.
>
> 또한 Microsoft 라이브 이벤트 지원 프로그램을 통해 최대 100,000명의 참석자가 참여하는 라이브 이벤트를 계획할 수 있습니다. [자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions)를 확인합니다. **2021년 1월 1일 이후 이러한 제한 증가가 필요한 고객은 [고급 통신 추가 기능](teams-add-on-licensing/advanced-communications.md)을 구입해야 합니다.**

## <a name="presence-in-outlook"></a>Outlook에서의 현재 상태

Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다. 팀의 현재 상태에 대해 자세히 알아보려면 [팀의 사용자 현재 상태](presence-admins.md)를 참조하세요.

## <a name="storage"></a>저장소

Microsoft Teams의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에 폴더가 있습니다. 대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.

> [!NOTE]
> 각 [개인 채널](https://docs.microsoft.com/microsoftteams/private-channels)에는 고유한 SharePoint 사이트 모음이 있습니다.

테넌트에서 SharePoint Online을 사용하지 않는 경우 Microsoft Teams 사용자는 팀에서 파일을 공유할 수 없습니다. 비즈니스용 OneDrive(SharePoint 라이선스에 연결됨)가 해당 기능에 필요하므로 개인 채팅 사용자도 파일을 공유할 수 없습니다.

SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다. (자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.)

Teams는 파일 공유를 위해 SharePoint Online 백 엔드에서 실행되므로 SharePoint 제한 사항은 팀 내의 파일 섹션에 적용됩니다. 다음은 SharePoint Online에 적용할 수 있는 저장소 용량 한도입니다.

|기능                 |Microsoft 365 Business Basic  |Microsoft 365 Business Standard   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|저장소                 |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB 및 구매한 라이선스당 10GB   |조직당 1TB 및 구매한 라이선스당 10GB |조직당 1TB 및 구매한 라이선스당 10GB  |조직당 1TB           |
|Teams 파일용 저장소 |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |사이트 모음 또는 그룹당 최대 25TB |
|파일 업로드 제한(파일당)    |100GB    |100GB    |100GB    |100GB    |100GB    |100GB    |

채널은 팀을 위해 만든 SharePoint Online 사이트 모음의 폴더에 의해 지원되므로 채널 내의 파일 탭은 속해 있는 팀의 저장소 용량 한도를 공유 합니다.

자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.

## <a name="class-teams"></a>수업 팀

교육용 Microsoft Teams는 강의실 교육과 같은 고유한 교육 시나리오를 위해 설계된 템플릿을 제공합니다. 수업 팀을 포함한 팀 유형에 대한 자세한 내용은 [Microsoft Teams에서 공동 작업할 팀 유형 선택](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)에서 확인할 수 있습니다.

수업 팀은 추가 앱이 포함된 템플릿 유형이며, 팀 구성원 수에는 제한이 있습니다.

> [!NOTE]
> 수업 팀을 사용하려면 [Office 365 Education 라이선스](https://www.microsoft.com/education/products/office)가 필요합니다.

수업 팀 제한은 다음 표에 나열되어 있습니다.

|기능  |최대 한도  |
|---------|---------|
|팀의 구성원 수    | 이 문서의 [Teams 및 채널](#teams-and-channels) 섹션을 참조합니다.        |
|수업 팀에서 할당을 사용할 구성원 수    | 200        |
|수업 팀에서 OneNote 클래스 노트북을 사용할 구성원 수     |200         |

한 학급 팀이 200명 이상의 구성원을 지원할 수 있습니다. 그러나 팀 내에서 Assignments 앱 또는 Class Notebook 앱을 사용하려는 경우 구성원 수를 위의 최대 제한 이하로 유지해야 합니다.


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

Teams 사용자는 조직의 Active Directory에 있는 모든 사용자와 커뮤니케이션할 수 있으며, 조직의 Active Directory에 있는 모든 사용자를 **채팅** > **연락처** 또는 **통화** > **연락처**로 이동하여 대화 상대 및 대화 상대 목록에 추가할 수 있습니다.

팀 사용자는 조직 내의 Active Directory에 없는 사용자를 **통화** > **연락처**로 이동하여 연락처로 추가할 수도 있습니다.

## <a name="browsers"></a>브라우저

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>운영 체제

운영 체제 요구 사항에 대한 자세한 내용은 [Microsoft Teams용 클라이언트 다운로드](get-clients.md)를 참조하세요.
