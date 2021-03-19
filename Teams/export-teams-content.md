---
title: Microsoft Teams 내보내기 API를 통해 콘텐츠 내보내기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 이 문서에서는 Microsoft Teams 내보내기 API를 사용하여 Teams 콘텐츠를 내보내는 방법에 대해 알아보겠습니다.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1bca4eb70bff07e809630e1b997f377064b5e0e
ms.sourcegitcommit: b4b2c7e79679cce6cf5f863ddf708e50164f9a9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50861412"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams 내보내기 API를 통해 콘텐츠 내보내기

Teams Export API를 사용하면 Microsoft Teams에서 1:1, 그룹 채팅 및 채널 메시지를 내보낼 수 있습니다. 조직에서 Microsoft Teams 메시지를 내보내야 하는 경우 Teams 내보내기 API를 사용하여 해당 메시지를 추출할 수 있습니다. *채팅 메시지는* 채널 또는 채팅 내의 개별 채팅 [메시지를](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) [나타내며](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta) 채팅 메시지는 루트 채팅 메시지 또는 채팅 메시지의 **replyToId** 속성에 의해 정의되는 회신 스레드의 일부일 수 있습니다.

이러한 내보내기 API를 사용하는 방법에 대한 몇 가지 예제는 다음과 같습니다.

- **예제 1:** 조직에서 Microsoft Teams를 사용하도록 설정하고 특정 사용자 또는 팀의 날짜 범위를 전달하여 모든 Microsoft Teams 메시지를 프로그래밍식으로 날짜로 내보내고자 하는 경우
- **예제 2:** 날짜 범위를 제공하여 매일 모든 사용자 또는 팀 메시지를 프로그래밍식으로 내보내는 경우. 내보내기 API는 지정한 날짜 범위 동안 생성되거나 업데이트된 모든 메시지를 검색할 수 있습니다.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams Export API에서 지원되는 것은 무엇입니까?

- **Teams 메시지의 대량 내보내기:** Teams Export API는 테넌트당 최대 200 RPS, 애플리케이션에 대해 600 RPS를 지원하며, 이러한 제한은 Teams 메시지를 대량으로 내보낼 수 있습니다.
- **애플리케이션 컨텍스트:** Microsoft Graph를 호출하려면 앱이 Microsoft ID 플랫폼에서 액세스 토큰을 획득해야 합니다. 액세스 토큰에는 앱에 대한 정보와 Microsoft Graph를 통해 사용할 수 있는 리소스 및 API에 대한 권한이 포함되어 있습니다. 액세스 토큰을 얻게하려면 앱이 Microsoft ID 플랫폼에 등록되어야 합니다. 사용자가나 관리자가 필요한 Microsoft Graph 리소스에 대한 액세스 권한을 부여해야 합니다.

    토큰을 얻기 위해 Microsoft ID 플랫폼과 앱을 통합하는 데 [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 이미 익숙한 경우 다음 단계 섹션에서 Microsoft Graph 관련 정보와 샘플을 참조하세요.
- **하이브리드 환경:** 내보내기 API는 하이브리드 환경(프레미스 Exchange 및 Teams)에서 프로비전된 사용자가 보낸 메시지를 지원합니다. 하이브리드 환경으로 구성된 사용자가 보낸 모든 메시지는 내보내기 API를 사용하여 액세스할 수 있습니다.
- **사용자 삭제된 메시지:** Teams 클라이언트에서 사용자가 삭제한 메시지는 삭제 시 최대 30일까지 내보내기 API를 사용하여 액세스할 수 있습니다.
- **메시지 첨부 파일:** 내보내기 API에는 메시지의 일부로 전송되는 첨부 파일에 대한 링크가 포함됩니다. API 내보내기 를 사용하면 메시지에 연결된 파일을 검색할 수 있습니다.
- **채팅 메시지 속성:** Teams Export API가 여기에서 지원하는 속성의 전체 목록을 [참조하세요.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)

## <a name="how-to-access-teams-export-apis"></a>Teams Export API에 액세스하는 방법

- **예제 1은** 필터 없이 사용자 또는 팀의 모든 메시지를 검색하는 간단한 쿼리입니다.

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages
    ```

- **예제 2는** 날짜 시간 필터와 상위 50개 메시지를 지정하여 사용자 또는 팀의 모든 메시지를 검색하는 샘플 쿼리입니다.

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
    ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/getallMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>API는 여러 결과의 경우 다음 페이지 링크가 있는 응답을 반환합니다. 다음 결과 집합을 얻은 경우 url에서 GET을 @odata.nextlink를 호출합니다. @odata.nextlink가 존재하지 않는 경우 또는 null이면 모든 메시지가 검색됩니다.

## <a name="prerequisites-to-access-teams-export-apis"></a>Teams Export API에 액세스하기 위한 전제적 요구 

- Teams Export API는 현재 미리 보기 상태입니다. API에 필요한 라이선스가 있는 사용자 및 테넌트만 [사용할](https://aka.ms/teams-changenotification-licenses) 수 있습니다. 향후 Microsoft는 사용자 또는 고객이 API를 통해 액세스하는 데이터의 양에 따라 추가 요금을 지불할 것을 요구할 수 있습니다.
- 중요한 데이터에 액세스하는 Microsoft Graph의 Microsoft Teams API는 보호된 API로 간주됩니다. API 내보내기 사용 전에 사용 권한 및 동의를 초과하는 추가 유효성 검사가 필요합니다. 이러한 보호된 API에 대한 액세스를 요청하기 위해 요청 양식을 [작성합니다.](https://aka.ms/teamsgraph/requestaccess)
- 애플리케이션 사용 권한은 로그인한 사용자 존재 없이 실행된 앱에서 사용됩니다. 애플리케이션 사용 권한은 관리자만 동의할 수 있습니다. 다음 사용 권한이 필요합니다.

    - *Chat.Read.All*: 모든 1:1 및 그룹 채팅 메시지에 액세스할 수 있습니다. 
    - *User.Read.All*: 테넌트에 대한 사용자 목록에 액세스할 수 있습니다. 

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
>chatMessage 리소스에 대한 자세한 내용은 [chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) 리소스 유형 문서를 참조하세요.
