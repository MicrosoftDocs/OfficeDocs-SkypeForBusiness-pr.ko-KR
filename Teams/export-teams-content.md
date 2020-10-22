---
title: Microsoft 팀에서 콘텐츠 내보내기 Api 내보내기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 이 문서에서는 Microsoft 팀 내보내기 Api를 사용 하 여 팀 콘텐츠를 내보내는 방법에 대해 설명 합니다.
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
ms.openlocfilehash: 026b7f238b059b4e310fa2216b482c68f2528780
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650981"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft 팀에서 콘텐츠 내보내기 Api 내보내기

팀 내보내기 Api를 사용 하 여 Microsoft 팀 으로부터 1:1 및 그룹 채팅 메시지를 내보낼 수 있습니다. 조직에서 Microsoft 팀 메시지를 내보내야 하는 경우에는 팀 내보내기 Api를 사용 하 여 추출할 수 있습니다. *채팅 메시지* 는 [채널](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 또는 [채팅](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)내의 개별 채팅 메시지를 나타냅니다. 채팅 메시지는 루트 채팅 메시지 이거나 채팅 메시지의 **replyToId** 속성으로 정의 된 회신 스레드의 일부일 수 있습니다.

다음은 이러한 내보내기 Api를 사용할 수 있는 방법에 대 한 몇 가지 예입니다.

- **예제 1**: 조직에서 microsoft 팀을 사용 하도록 설정한 경우 지정 된 사용자에 대 한 날짜 범위를 전달 하 여 프로그래밍 방식으로 모든 Microsoft 팀 메시지를 날짜별로 내보내야 합니다.
- **예제 2**: 날짜 범위를 제공 하 여 매일 모든 사용자 메시지를 프로그래밍 방식으로 내보내려면 합니다. Api 내보내기는 주어진 날짜 범위 중에 만들어지거나 업데이트 된 모든 메시지를 검색할 수 있습니다.

## <a name="what-is-supported-by-the-teams-export-apis"></a>팀 내보내기 Api에서 지원 되는 기능은 무엇입니까?

- **팀의 대량 내보내기 메시지:** 팀은 테 넌 트 당 앱 당 최대 200 RPS 및 응용 프로그램의 600 RPS에 대 한 Api 지원을 내보냅니다. 이러한 제한을 통해 팀 메시지를 대량으로 내보낼 수 있어야 합니다.
- **응용 프로그램 컨텍스트**: microsoft Graph를 호출 하려면 앱이 microsoft id 플랫폼에서 액세스 토큰을 얻어야 합니다. 액세스 토큰에는 앱에 대 한 정보와 Microsoft Graph를 통해 사용할 수 있는 리소스 및 Api에 대 한 사용 권한이 포함 됩니다. 액세스 토큰을 가져오려면 앱을 Microsoft id 플랫폼에 등록 하 고 사용자 또는 관리자가 필요한 Microsoft Graph 리소스에 액세스할 수 있도록 권한을 부여 받아야 합니다.

    Microsoft id 플랫폼을 사용 하 여 토큰을 가져오는 앱을 통합 하는 데 익숙한 경우 Microsoft Graph에 대 한 자세한 내용 및 예제는 [다음 단계](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 섹션을 참조 하세요.
- **하이브리드 환경:** 하이브리드 환경에서 프로 비전 된 사용자가 보낸 Api 지원 메시지를 내보냅니다 (온-프레미스 Exchange 및 팀). 하이브리드 환경에 대해 구성 된 사용자가 보내는 모든 메시지는 내보내기 Api를 사용 하 여 액세스할 수 있습니다.
- **사용자가 삭제 한 메시지:** 팀 클라이언트에서 사용자가 삭제 한 메시지는 삭제 시점부터 최대 30 일간 내보내기 Api를 사용 하 여 액세스할 수 있습니다.
- **메시지 첨부 파일:** Api 내보내기 메시지의 일부로 전송 되는 첨부 파일에 대 한 링크를 포함 합니다. Api 내보내기를 사용 하 여 메시지에 첨부 된 파일을 검색할 수 있습니다.
- **채팅 메시지 속성:** [여기](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)에서 팀이 Api 지원을 내보내는 전체 속성 목록을 참조 하세요.

## <a name="how-to-access-teams-export-apis"></a>팀 내보내기 Api에 액세스 하는 방법

- **예제 1** 은 필터 없이 사용자의 모든 메시지를 검색 하는 간단한 쿼리입니다.

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- **예제 2** 는 날짜 시간 필터 및 상위 50 메시지를 지정 하 여 사용자의 모든 메시지를 검색 하는 예제 쿼리입니다.

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
>API는 여러 결과가 발생 하는 경우 다음 페이지 링크가 포함 된 응답을 반환 합니다. 다음 결과 집합을 얻으려면 nextlink @odata의 url에 대해 GET을 호출 하면 됩니다. Nextlink가 없거나 null이 아니면 모든 메시지가 검색 됩니다. @odata

## <a name="prerequisites-to-access-teams-export-apis"></a>팀에 액세스 하기 위한 필수 구성 요소 Api 내보내기 

- 팀 내보내기 Api는 현재 미리 보기 상태입니다. Api에 대해 [필요한 라이선스가](https://aka.ms/teams-changenotification-licenses) 있는 사용자와 테 넌 트 에서만 사용할 수 있습니다. 앞으로 Microsoft는 사용자 또는 고객이 API를 통해 액세스 하는 데이터 양에 따라 추가 요금을 지불 하도록 요구할 수 있습니다.
- 중요 한 데이터에 액세스 하는 microsoft Graph Api는 보호 된 Api로 간주 됩니다. 내보내기 Api를 사용 하려면 권한 및 승인 이상의 추가 유효성 검사가 필요 합니다. 이러한 보호 된 Api에 대 한 액세스 권한을 요청 하려면 [요청 양식을](https://aka.ms/teamsgraph/requestaccess)작성 합니다.
- 응용 프로그램 사용 권한은 로그인 한 사용자 없이 실행 되는 앱에서 사용 됩니다. 응용 프로그램 권한은 관리자만 였음을 수 있습니다. 다음과 같은 사용 권한이 필요 합니다.

    - *채팅. 모두*: 모든 1:1 및 그룹 채팅 메시지에 대 한 액세스를 사용 하도록 설정 합니다. 
    - *사용자. 모두*: 테 넌 트의 사용자 목록에 대 한 액세스를 가능 하 게 합니다. 

## <a name="json-representation"></a>JSON 표현

다음 예제는 리소스의 JSON 표현입니다.

네임 스페이스: microsoft graph

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
                    "id": "0de69e5e-2da8-4cf2-821f-5e6585b2c65b",
                    "displayName": "User Name",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "19:0de69e5e-2da8-4cf2-821f-5e6585b2c65b_5c64e248-3269-4268-a36e-0f80314e9c39@unq.gbl.spaces"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
>자원 메시지 리소스에 대 한 자세한 내용은 [메시지 자원 형식](https://docs.microsoft.com/graph/api/resources/chatmessage) 문서를 참조 하세요.
