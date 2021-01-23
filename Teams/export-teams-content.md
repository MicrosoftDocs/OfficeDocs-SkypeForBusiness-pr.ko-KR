---
title: Microsoft Teams 내보내기 API를 통해 콘텐츠 내보내기
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: vikramju
description: 이 문서에서는 Microsoft Teams 내보내기 API를 사용하여 Teams 콘텐츠를 내보내는 방법에 대해 배웠습니다.
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
ms.openlocfilehash: f4ea2d747d40c221d9e99b51fc7b15da8e2cdd12
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944603"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="30772-103">Microsoft Teams 내보내기 API를 통해 콘텐츠 내보내기</span><span class="sxs-lookup"><span data-stu-id="30772-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="30772-104">Teams 내보내기 API를 사용하면 Microsoft Teams에서 1:1, 그룹 채팅 및 채널 메시지를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-104">Teams Export APIs allow you to export 1:1, group chat, and channel messages from Microsoft Teams.</span></span> <span data-ttu-id="30772-105">조직에서 Microsoft Teams 메시지를 내보내야 하는 경우 Teams 내보내기 API를 사용하여 메시지를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-105">If your organization needs to export Microsoft Teams messages, you are able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="30772-106">*채팅 메시지는* 채널 또는 채팅 내의 개별 [채팅](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 메시지를 [나타 내는 것입니다.](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="30772-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="30772-107">채팅 메시지는 루트 채팅 메시지 또는 채팅 메시지의 **replyToId** 속성에 의해 정의된 회신 스레드의 일부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="30772-108">이러한 내보내기 API를 사용하는 방법에 대한 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="30772-109">**예제 1:** 조직에서 Microsoft Teams를 사용하도록 설정하고 특정 사용자 또는 팀의 날짜 범위를 전달하여 모든 Microsoft Teams 메시지를 프로그래밍으로 최신으로 내보내고 싶은 경우</span><span class="sxs-lookup"><span data-stu-id="30772-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user or team.</span></span>
- <span data-ttu-id="30772-110">**예제 2:** 날짜 범위를 제공하여 매일 모든 사용자 또는 팀 메시지를 프로그래밍으로 내보내는 경우</span><span class="sxs-lookup"><span data-stu-id="30772-110">**Example 2**: If you want to programmatically export all user or team messages daily by providing a date range.</span></span> <span data-ttu-id="30772-111">API 내보내기에서는 지정한 날짜 범위 동안 생성되거나 업데이트된 모든 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="30772-112">Teams 내보내기 API에서 지원되는 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="30772-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="30772-113">**Teams 메시지 대량 내보내기:** Teams 내보내기 API는 테넌트당 앱당 최대 200 RPS 및 애플리케이션에 대해 600 RPS를 지원하며, 이러한 제한으로 Teams 메시지를 대량으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="30772-114">**애플리케이션 컨텍스트:** Microsoft Graph를 호출하려면 앱이 Microsoft ID 플랫폼에서 액세스 토큰을 획득해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30772-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="30772-115">액세스 토큰에는 앱에 대한 정보와 Microsoft Graph를 통해 사용할 수 있는 리소스 및 API에 대한 권한이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="30772-116">액세스 토큰을 얻습니다. 앱을 Microsoft ID 플랫폼에 등록하고 필요한 Microsoft Graph 리소스에 액세스하기 위해 사용자 또는 관리자가 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30772-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="30772-117">토큰을 얻기 위해 Microsoft ID 플랫폼과 앱을 통합하는 데 [](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 이미 익숙한 경우 다음 단계 섹션에서 Microsoft Graph에 대한 정보와 샘플을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30772-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="30772-118">**하이브리드 환경:** API 내보내기에서는 하이브리드 환경(-프레미스 Exchange 및 Teams)에 프로비전된 사용자가 보낸 메시지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="30772-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="30772-119">하이브리드 환경에 대해 구성된 사용자가 보낸 모든 메시지는 내보내기 API를 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="30772-120">**사용자가 삭제한 메시지:** Teams 클라이언트에서 사용자가 삭제한 메시지는 삭제 후 최대 30일 동안 API 내보내기 기능을 사용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="30772-121">**메시지 첨부 파일:** API 내보내기에는 메시지의 일부로 전송되는 첨부 파일에 대한 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="30772-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="30772-122">API 내보내기 기능을 사용하여 메시지에 첨부된 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30772-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="30772-123">**채팅 메시지 속성:** Teams 내보내기 API가 지원하는 속성의 전체 목록을 [참조하세요.](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)</span><span class="sxs-lookup"><span data-stu-id="30772-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="30772-124">Teams 내보내기 API에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="30772-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="30772-125">**예제 1은** 필터 없이 사용자 또는 팀의 모든 메시지를 검색하는 간단한 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="30772-125">**Example 1** is a simple query to retrieve all the messages of a user or team without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```
     ```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages
    ```

- <span data-ttu-id="30772-126">**예제 2는** 날짜 시간 필터 및 상위 50개 메시지를 지정하여 사용자 또는 팀의 모든 메시지를 검색하는 샘플 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="30772-126">**Example 2** is a sample query to retrieve all the messages of a user or team by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
```HTTP
    GET https://graph.microsoft.com/beta/teams/{id}/channels/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```
>[!NOTE]
>The API returns response with next page link in case of multiple results. For getting next set of results, simply call GET on the url from @odata.nextlink. If @odata.nextlink is not present or null then all messages are retrieved.

## Prerequisites to access Teams Export APIs 

- Teams Export APIs are currently in preview. It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs. In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.
- Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs. Export APIs require that you have additional validation, beyond permissions and consent, before you can use them. To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).
- Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator. The following permissions are needed:

    - *Chat.Read.All*: enables access to all 1:1 and Group chat messages 
    - *User.Read.All*: enables access to the list of users for a tenant 

## JSON representation

The following example is a JSON representation of the resource:

Namespace: microsoft.graph

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
                    "id": "string (identifier)",
                    "displayName": "string",
                    "userIdentityType": "aadUser"                }
            },
"body": {"@odata.type": "microsoft.graph.itemBody"},
"summary": "string",
"chatId": "string (identifier)"
"attachments": \[{"@odata.type": "microsoft.graph.chatMessageAttachment"}\],
"mentions": \[{"@odata.type": "microsoft.graph.chatMessageMention"}\],
"importance": "string",
"locale": "string",
}
```

>[!NOTE]
><span data-ttu-id="30772-127">chatMessage 리소스에 대한 자세한 내용은 [chatMessage](https://docs.microsoft.com/graph/api/resources/chatmessage) 리소스 종류 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30772-127">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
