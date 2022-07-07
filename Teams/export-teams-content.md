---
title: Microsoft Teams 내보내기 API를 사용하여 콘텐츠 내보내기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 이 문서에서는 Microsoft Teams 내보내기 API를 사용하여 Teams 콘텐츠를 내보내는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: b508b368629ce716a1269380eb1fffe2137620c8
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647650"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a>Microsoft Teams 내보내기 API를 사용하여 콘텐츠 내보내기

Teams 내보내기 API를 사용하면 Microsoft Teams에서 1:1, 그룹 채팅, 모임 채팅 및 채널 메시지를 내보낼 수 있습니다. 조직에서 Microsoft Teams 메시지를 내보내야 하는 경우 Teams 내보내기 API를 사용하여 추출할 수 있습니다. *채팅 메시지는* [채널](/graph/api/resources/channel) 또는 채팅 내의 개별 [채팅](/graph/api/resources/chat) 메시지를 나타냅니다. 채팅 메시지는 루트 채팅 메시지 또는 채팅 메시지의 **replyToId** 속성에 의해 정의된 회신 스레드의 일부일 수 있습니다.

다음은 이러한 내보내기 API를 사용하는 방법에 대한 몇 가지 예입니다.

- **예제 1**: 조직에서 Microsoft Teams를 사용하도록 설정하고 지정된 사용자 또는 팀의 날짜 범위를 전달하여 모든 Microsoft Teams 메시지를 프로그래밍 방식으로 날짜로 내보내려는 경우
- **예제 2**: 날짜 범위를 제공하여 모든 사용자 또는 팀 메시지를 프로그래밍 방식으로 매일 내보내려는 경우 내보내기 API는 지정된 날짜 범위 동안 생성되거나 업데이트된 모든 메시지를 검색할 수 있습니다.

## <a name="what-is-supported-by-the-teams-export-apis"></a>Teams 내보내기 API에서 지원되는 것은 무엇인가요?

- **Teams 대량 내보내기 메시지:** Teams 내보내기 API는 테넌트당 앱당 최대 200 RPS, 애플리케이션에 대해 600 RPS를 지원하며, 이러한 제한으로 Teams 메시지를 대량으로 내보낼 수 있습니다.
- **애플리케이션 컨텍스트**: Microsoft Graph를 호출하려면 앱이 Microsoft ID 플랫폼 액세스 토큰을 획득해야 합니다. 액세스 토큰에는 앱에 대한 정보와 Microsoft Graph를 통해 사용할 수 있는 리소스 및 API에 대한 사용 권한이 포함됩니다. 액세스 토큰을 가져오려면 앱이 Microsoft ID 플랫폼 등록되고 사용자 또는 관리자가 필요한 Microsoft Graph 리소스에 액세스할 수 있도록 권한을 부여받아야 합니다.

    토큰을 가져오기 위해 앱을 Microsoft ID 플랫폼 통합하는 데 이미 익숙한 경우 [다음 단계](/graph/auth/auth-concepts#next-steps) 섹션에서 Microsoft Graph와 관련된 정보 및 샘플을 참조하세요.
- **하이브리드 환경:** 내보내기 API는 하이브리드 환경(온-프레미스 Exchange 및 Teams)에서 프로비전된 사용자가 보낸 메시지를 지원합니다. 하이브리드 환경에 대해 구성된 사용자가 보낸 모든 메시지는 내보내기 API를 사용하여 액세스할 수 있습니다.
- **사용자 삭제된 메시지:** Teams 클라이언트에서 사용자가 삭제한 메시지는 삭제 시점부터 최대 21일까지 내보내기 API를 사용하여 액세스할 수 있습니다.
- **메시지 첨부 파일:** 내보내기 API에는 메시지의 일부로 전송되는 첨부 파일에 대한 링크가 포함됩니다. 내보내기 API를 사용하여 메시지에 첨부된 파일을 검색할 수 있습니다.
- **반응:** 내보내기 API는 Teams 메시지에서 사용자가 초기화한 반응을 지원합니다. 현재 지원되는 반응은 심장, 화가, 슬픈, 놀라움, 웃음입니다.
- **채팅 메시지 속성:** Teams Export API에서 지원하는 속성의 전체 목록을 [참조하세요](/graph/api/resources/chatmessage#properties).


## <a name="how-to-access-teams-export-apis"></a>Teams 내보내기 API에 액세스하는 방법

- **예제 1** 은 필터 없이 사용자 또는 팀의 모든 메시지를 검색하는 간단한 쿼리입니다.

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages
  ```

- **예제 2** 는 날짜 시간 필터 및 상위 50개 메시지를 지정하여 사용자 또는 팀의 모든 메시지를 검색하는 샘플 쿼리입니다.

  ```HTTP
  GET https://graph.microsoft.com/v1.0/users/{id}/chats/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

  ```HTTP
  GET https://graph.microsoft.com/v1.0/teams/{id}/channels/getAllMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
  ```

> [!NOTE]
> API는 여러 결과가 발생하는 경우 다음 페이지 링크가 포함된 응답을 반환합니다. 다음 결과 집합을 가져오려면 @odata.nextlink의 URL에서 GET을 호출하기만 하면됩니다. @odata.nextlink가 없거나 null이면 모든 메시지가 검색됩니다.

## <a name="prerequisites-to-access-teams-export-apis"></a>Teams 내보내기 API에 액세스하기 위한 필수 구성 요소

- 중요한 데이터에 액세스하는 Microsoft Graph의 Microsoft Teams API는 보호되는 API로 간주됩니다. API 내보내기를 사용하려면 사용 권한 및 동의 이외의 추가 유효성 검사가 필요합니다. 이러한 보호된 API에 대한 액세스를 요청하려면 [요청 양식을](https://aka.ms/teamsgraph/requestaccess) 완료합니다.
- 애플리케이션 권한은 로그인한 사용자 없이 실행되는 앱에서 사용됩니다. 애플리케이션 권한은 관리자만 동의할 수 있습니다. 필요한 권한은 다음과 같습니다.
  - *Chat.Read.All*: 모든 1:1, 그룹 채팅 및 모임 채팅 메시지에 액세스할 수 있습니다.
  - *ChannelMessage.Read.All*: 모든 채널 메시지에 액세스할 수 있습니다.
  - *User.Read.All*: 테넌트에 대한 사용자 목록에 액세스할 수 있습니다.

## <a name="license-requirements-for-teams-export-apis"></a>Teams 내보내기 API에 대한 라이선스 요구 사항

Export API는 모델 쿼리 매개 변수를 통해 S+C(보안 및 규정 준수) 및 일반 사용 시나리오를 지원합니다. S+C 시나리오(모델 A)에는 시드된 용량이 포함되며 E5 구독이 필요하며 일반 사용 시나리오(모델 B)는 모든 구독에 사용할 수 있으며 사용량에만 사용됩니다. 시드된 용량 및 사용 요금에 대한 자세한 내용은 [Microsoft Graph Teams API에 대한 라이선스 및 지불 요구 사항을 참조하세요](/graph/teams-licenses).

### <a name="scmodel-a-scenarios"></a>S+C/모델 A 시나리오

보안 및/또는 규정 준수 기능을 수행하는 애플리케이션으로 제한되는 사용자는 이 기능을 사용하고 시드된 용량을 받으려면 특정 E5 라이선스가 있어야 합니다. 시드된 용량은 사용자당이며 매월 계산되며 테넌트 수준에서 집계됩니다. 시드된 용량을 초과하는 사용량의 경우 앱 소유자는 API 사용량에 대해 요금이 청구됩니다. 모델 A는 할당된 E5 라이선스를 가진 사용자의 메시지에만 액세스할 수 있습니다.

### <a name="general-usagemodel-b-scenarios"></a>일반 사용량/모델 B 시나리오

모든 비 S+C 관련 시나리오에 사용할 수 있으며 라이선스 요구 사항 또는 시드된 용량이 없습니다. 사용량 측정기를 사용할 수 있게 되면 앱 소유자는 모든 월간 API 호출에 대해 요금이 청구됩니다.

### <a name="evaluation-mode-default"></a>평가 모드(기본값)

모델 선언을 통해 각 요청 애플리케이션당 사용량이 제한된 API에 대한 액세스를 평가 목적으로 사용할 수 없습니다.

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

> [!NOTE]
> chatMessage 리소스에 대한 자세한 내용은 [chatMessage 리소스 종류](/graph/api/resources/chatmessage) 문서를 참조하세요.
