---
title: 내보내기 API를 Microsoft Teams 콘텐츠 내보내기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 이 문서에서는 Api 내보내기 api를 사용하여 Teams 콘텐츠를 Microsoft Teams 방법을 알아보겠습니다.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84f53b5c75c9e99e3a3bfc2877c096b32fe3b9c0
ms.sourcegitcommit: 26ce61afcb743c8b9e06b4fa048ad93ab70c31c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "60082868"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>내보내기 API를 Microsoft Teams 콘텐츠 내보내기

Teams API 내보내기에서는 1:1, 그룹 채팅, 모임 채팅 및 채널 메시지를 내보낼 수 Microsoft Teams. 조직에서 메시지를 내보내야 Microsoft Teams API 내보내기 API를 사용하여 Teams 수 있습니다. *채팅 메시지는* 채널 또는 채팅 내의 개별 채팅 [메시지를](/graph/api/resources/channel?view=graph-rest-beta) [나타내며](/graph/api/resources/chat?view=graph-rest-beta) 채팅 메시지는 루트 채팅 메시지 또는 채팅 메시지의 **replyToId** 속성에 의해 정의되는 회신 스레드의 일부일 수 있습니다.

이러한 내보내기 API를 사용하는 방법에 대한 몇 가지 예제는 다음과 같습니다.

- **예제 1:** 조직에서 Microsoft Teams 활성화하고 모든 메시지를 프로그래밍 Microsoft Teams 특정 사용자 또는 팀의 날짜 범위를 전달하여 프로그래밍식으로 날짜로 내보낼 수 있습니다.
- **예제 2:** 날짜 범위를 제공하여 매일 모든 사용자 또는 팀 메시지를 프로그래밍식으로 내보내는 경우. 내보내기 API는 지정한 날짜 범위 동안 생성되거나 업데이트된 모든 메시지를 검색할 수 있습니다.

## <a name="what-is-supported-by-the-teams-export-apis"></a>내보내기 API에서 지원되는 Teams 무엇입니까?

- **Teams 메시지의 대량 내보내기:** Teams 내보내기 API는 테넌트당 최대 200 RPS, 애플리케이션에 대해 600 RPS를 지원하며, 이러한 제한을 통해 메시지의 대량 내보내기 Teams 수 있습니다.
- **애플리케이션 컨텍스트:** Microsoft Graph 호출하려면 앱에서 액세스 토큰을 Microsoft ID 플랫폼. 액세스 토큰에는 앱에 대한 정보와 Microsoft 웹앱을 통해 사용할 수 있는 리소스 및 API에 대한 권한이 Graph. 액세스 토큰을 얻게하려면 앱에 Microsoft ID 플랫폼 사용자 또는 관리자가 필요한 Microsoft 리소스에 Graph 권한을 부여해야 합니다.

    토큰을 얻기 위해 앱과 앱을 Microsoft ID 플랫폼 익숙한 경우 다음 [](/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 단계 섹션을 참조하세요. Microsoft Graph.
- **하이브리드 환경:** 내보내기 API는 하이브리드 환경에 프로비전된 사용자가 보낸 메시지를 Exchange 및 Teams. 하이브리드 환경으로 구성된 사용자가 보낸 모든 메시지는 내보내기 API를 사용하여 액세스할 수 있습니다.
- **사용자 삭제된 메시지:** 클라이언트에서 사용자가 삭제한 메시지는 삭제 Teams 최대 21일까지 내보내기 API를 사용하여 액세스할 수 있습니다.
- **메시지 첨부 파일:** 내보내기 API에는 메시지의 일부로 전송되는 첨부 파일에 대한 링크가 포함됩니다. API 내보내기 를 사용하면 메시지에 연결된 파일을 검색할 수 있습니다.
- **채팅 메시지 속성:** 내보내기 API를 지원하는 Teams 전체 목록을 [참조하세요.](/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

>[!NOTE]
>내보내기 API는 반응을 *지원하지 않습니다.*

## <a name="how-to-access-teams-export-apis"></a>Api 내보내기 Teams 액세스하는 방법

- **예제 1은** 필터 없이 사용자 또는 팀의 모든 메시지를 검색하는 간단한 쿼리입니다.

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
    ```

- **예제 2는** 날짜 시간 필터와 상위 50개 메시지를 지정하여 사용자 또는 팀의 모든 메시지를 검색하는 샘플 쿼리입니다.

    ```HTTP
    GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>API는 여러 결과의 경우 다음 페이지 링크가 있는 응답을 반환합니다. 다음 결과 집합을 얻은 경우 url에서 GET을 @odata.nextlink를 호출합니다. @odata.nextlink가 존재하지 않는 경우 또는 null이면 모든 메시지가 검색됩니다.

## <a name="prerequisites-to-access-teams-export-apis"></a>API 내보내기 Teams 액세스하는 전제품 

- Microsoft Teams Microsoft의 API Graph 액세스하는 API는 보호된 API로 간주됩니다. API 내보내기 사용 전에 사용 권한 및 동의를 초과하는 추가 유효성 검사가 필요합니다. 이러한 보호된 API에 대한 액세스를 요청하기 위해 요청 양식을 [작성합니다.](https://aka.ms/teamsgraph/requestaccess)
- 애플리케이션 사용 권한은 로그인한 사용자 존재 없이 실행된 앱에서 사용됩니다. 애플리케이션 사용 권한은 관리자만 동의할 수 있습니다. 다음 사용 권한이 필요합니다.

    - *Chat.Read.All*: 모든 1:1, 그룹 채팅 및 모임 채팅 메시지에 액세스할 수 있습니다. 
    - *ChannelMessage.Read.All*: 모든 채널 메시지에 액세스할 수 있습니다.  
    - *User.Read.All*: 테넌트에 대한 사용자 목록에 액세스할 수 있습니다.

## <a name="license-requirements-for-teams-export-apis"></a>내보내기 API에 Teams 라이선스 요구 사항

Export API는 모델 쿼리 매개 변수를 통해 S+C(보안 및 규정 준수) 및 일반 사용 시나리오를 지원합니다. S+C 시나리오(모델 A)는 시드 용량을 포함하며 E5 구독 및 일반 사용 시나리오(모델 B)를 모든 구독에 사용할 수 있으며 사용만 필요합니다. 시드 용량 및 소비 요금에 대한 자세한 내용은 Microsoft api에 [대한 라이선스 및 Graph Teams 참조하세요.](/graph/teams-licenses)

### <a name="scmodel-a-scenarios"></a>S+C/모델 A 시나리오

보안 및/또는 규정 준수 기능을 수행하는 애플리케이션으로 제한되는 사용자는 이 기능을 사용하여 시드 용량을 받기 위해 특정 E5 라이선스가 있어야 합니다. 시드 용량은 사용자당 있으며 월별로 계산하며 테넌트 수준에서 집계됩니다. 시드 용량을 초과하는 사용량의 경우 앱 소유자는 API 사용량에 대해 청구됩니다. 모델 A는 할당된 E5 라이선스를 사용하여 사용자의 메시지에만 액세스할 수 있습니다.

### <a name="general-usagemodel-b-scenarios"></a>일반 사용/모델 B 시나리오

S+C가 아닌 모든 시나리오에서 사용할 수 있는 라이선스 요구 사항 또는 시드 용량이 없습니다. 사용량 미터를 사용할 수 있는 경우 앱 소유자는 모든 월별 API 호출에 대해 요금이 청구됩니다. 

### <a name="evaluation-mode-default"></a>평가 모드(기본값)

평가 목적으로 각 요청 애플리케이션당 사용량이 제한된 API에 액세스할 수 있는 모델 선언은 없습니다. 

## <a name="json-representation"></a>JSON 표현

다음 예제는 리소스의 JSON 표현입니다.

네임스페이스: microsoft.graph

```JSON
{
"id": "string (identifier)",
"replyToId": "string (identifier)",
"from": {"@odata.type": "microsoft.graph.identitySet"},
"etag": "string",
"messageType": "string",
"createdDateTime": "string (timestamp)",
"lastModifiedDateTime": "string (timestamp)",
"deletedDateTime": "string (timestamp)",
"subject": "string",
"from": {
                "application": null,
                "device": null,
                "conversation": null,
                "user": {

                    "id": \[{"@odata.type": "microsoft.graph.user"}\],
                    "displayName": "User Name",

                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",

"chatId": \[{"@odata.type": "microsoft.graph.chat"}\]

"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>chatMessage 리소스에 대한 자세한 내용은 [chatMessage](/graph/api/resources/chatmessage) 리소스 유형 문서를 참조하세요.