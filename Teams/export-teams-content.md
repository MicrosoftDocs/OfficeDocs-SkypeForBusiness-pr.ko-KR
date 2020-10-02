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
ms.openlocfilehash: bbb03fc030361419e5f42b2e792e752f2007e6d2
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333494"
---
# <a name="export-content-with-the-microsoft-teams-export-apis"></a><span data-ttu-id="82f4b-103">Microsoft 팀에서 콘텐츠 내보내기 Api 내보내기</span><span class="sxs-lookup"><span data-stu-id="82f4b-103">Export content with the Microsoft Teams Export APIs</span></span>

<span data-ttu-id="82f4b-104">팀 내보내기 Api를 사용 하 여 Microsoft 팀 으로부터 1:1 및 그룹 채팅 메시지를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-104">Teams Export APIs allow you to export 1:1 and group chat messages from Microsoft Teams.</span></span> <span data-ttu-id="82f4b-105">조직에서 Microsoft 팀 메시지를 내보내야 하는 경우 팀 내보내기 Api를 사용 하 여 파일을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-105">If your organization needs to export Microsoft Teams messages, you can be able to extract them using Teams Export APIs.</span></span> <span data-ttu-id="82f4b-106">*채팅 메시지* 는 [채널](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) 또는 [채팅](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta)내의 개별 채팅 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-106">*Chat Message* represents an individual chat message within a [channel](https://docs.microsoft.com/graph/api/resources/channel?view=graph-rest-beta) or [chat](https://docs.microsoft.com/graph/api/resources/chat?view=graph-rest-beta).</span></span> <span data-ttu-id="82f4b-107">채팅 메시지는 루트 채팅 메시지 이거나 채팅 메시지의 **replyToId** 속성으로 정의 된 회신 스레드의 일부일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-107">The chat message can be a root chat message or part of a reply thread that is defined by the **replyToId** property in the chat message.</span></span>

<span data-ttu-id="82f4b-108">다음은 이러한 내보내기 Api를 사용할 수 있는 방법에 대 한 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-108">Here are some examples on how you can use these export APIs:</span></span>

- <span data-ttu-id="82f4b-109">**예제 1**: 조직에서 microsoft 팀을 사용 하도록 설정한 경우 지정 된 사용자에 대 한 날짜 범위를 전달 하 여 프로그래밍 방식으로 모든 Microsoft 팀 메시지를 날짜별로 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-109">**Example 1**: If you have enabled Microsoft Teams in your organization and want to export all the Microsoft Teams messages to date programmatically by passing the date range for a given user.</span></span>
- <span data-ttu-id="82f4b-110">**예제 2**: 날짜 범위를 제공 하 여 매일 모든 사용자 메시지를 프로그래밍 방식으로 내보내려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-110">**Example 2**: If you want to programmatically export all user messages daily by providing a date range.</span></span> <span data-ttu-id="82f4b-111">Api 내보내기는 주어진 날짜 범위 중에 만들어지거나 업데이트 된 모든 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-111">Export APIs can retrieve all the messages created or updated during the given date range.</span></span>

## <a name="what-is-supported-by-the-teams-export-apis"></a><span data-ttu-id="82f4b-112">팀 내보내기 Api에서 지원 되는 기능은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="82f4b-112">What is supported by the Teams Export APIs?</span></span>

- <span data-ttu-id="82f4b-113">**팀의 대량 내보내기 메시지:** 팀은 테 넌 트 당 앱 당 최대 200 RPS 및 응용 프로그램의 600 RPS에 대 한 Api 지원을 내보냅니다. 이러한 제한을 통해 팀 메시지를 대량으로 내보낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-113">**Bulk Export of Teams Message:** Teams Export APIs support up to 200 RPS Per App Per tenant and 600 RPS for an Application, with these limits you should be able to bulk export of Teams messages.</span></span>
- <span data-ttu-id="82f4b-114">**응용 프로그램 컨텍스트**: microsoft Graph를 호출 하려면 앱이 microsoft id 플랫폼에서 액세스 토큰을 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-114">**Application Context**: To call Microsoft Graph, your app must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="82f4b-115">액세스 토큰에는 앱에 대 한 정보와 Microsoft Graph를 통해 사용할 수 있는 리소스 및 Api에 대 한 사용 권한이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-115">The access token contains information about your app and the permissions it has for the resources and APIs available through Microsoft Graph.</span></span> <span data-ttu-id="82f4b-116">액세스 토큰을 가져오려면 앱을 Microsoft id 플랫폼에 등록 하 고 사용자 또는 관리자가 필요한 Microsoft Graph 리소스에 액세스할 수 있도록 권한을 부여 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-116">To get an access token, your app must be registered with the Microsoft identity platform and be authorized by either a user or an administrator for access to the Microsoft Graph resources it needs.</span></span>

    <span data-ttu-id="82f4b-117">Microsoft id 플랫폼을 사용 하 여 토큰을 가져오는 앱을 통합 하는 데 익숙한 경우 Microsoft Graph에 대 한 자세한 내용 및 예제는 [다음 단계](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82f4b-117">If you are already familiar with integrating an app with the Microsoft identity platform to get tokens, see the [Next Steps](https://docs.microsoft.com/graph/auth/auth-concepts?view=graph-rest-1.0#next-steps) section for information and samples specific to Microsoft Graph.</span></span>
- <span data-ttu-id="82f4b-118">**하이브리드 환경:** 하이브리드 환경에서 프로 비전 된 사용자가 보낸 Api 지원 메시지를 내보냅니다 (온-프레미스 Exchange 및 팀).</span><span class="sxs-lookup"><span data-stu-id="82f4b-118">**Hybrid Environment:** Export APIs support messages sent by users who are provisioned on Hybrid Environment (on-premises Exchange and Teams).</span></span> <span data-ttu-id="82f4b-119">하이브리드 환경에 대해 구성 된 사용자가 보내는 모든 메시지는 내보내기 Api를 사용 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-119">Any messages that are sent by users who are configured for hybrid environment will be accessible using Export APIs.</span></span>
- <span data-ttu-id="82f4b-120">**사용자가 삭제 한 메시지:** 팀 클라이언트에서 사용자가 삭제 한 메시지는 삭제 시점부터 최대 30 일간 내보내기 Api를 사용 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-120">**User Deleted Messages:** Messages that are deleted by user from Teams client can be accessed using export APIs up to 30 days from the time of deletion.</span></span>
- <span data-ttu-id="82f4b-121">**메시지 첨부 파일:** Api 내보내기 메시지의 일부로 전송 되는 첨부 파일에 대 한 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-121">**Message Attachments:** Export APIs include the links to the attachments that are sent as part of messages.</span></span> <span data-ttu-id="82f4b-122">Api 내보내기를 사용 하 여 메시지에 첨부 된 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-122">Using Export APIs you can retrieve the files attached in the messages.</span></span>
- <span data-ttu-id="82f4b-123">**채팅 메시지 속성:** [여기](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties)에서 팀이 Api 지원을 내보내는 전체 속성 목록을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82f4b-123">**Chat Message Properties:** Refer to the complete list of properties that Teams Export APIs support [here](https://docs.microsoft.com/graph/api/resources/chatmessage?view=graph-rest-beta#properties).</span></span>

## <a name="how-to-access-teams-export-apis"></a><span data-ttu-id="82f4b-124">팀 내보내기 Api에 액세스 하는 방법</span><span class="sxs-lookup"><span data-stu-id="82f4b-124">How to access Teams Export APIs</span></span>

- <span data-ttu-id="82f4b-125">**예제 1** 은 필터 없이 사용자의 모든 메시지를 검색 하는 간단한 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-125">**Example 1** is a simple query to retrieve all the messages of a user without any filters:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages
    ```

- <span data-ttu-id="82f4b-126">**예제 2** 는 날짜 시간 필터 및 상위 50 메시지를 지정 하 여 사용자의 모든 메시지를 검색 하는 예제 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-126">**Example 2** is a sample query to retrieve all the messages of a user by specifying date time filters and top 50 messages:</span></span>

    ```HTTP
    GET https://graph.microsoft.com/beta/users/{id}/chats/allMessages?$top=50&$filter=lastModifiedDateTime gt 2020-06-04T18:03:11.591Z and lastModifiedDateTime lt 2020-06-05T21:00:09.413Z
    ```

>[!NOTE]
><span data-ttu-id="82f4b-127">API는 여러 결과가 발생 하는 경우 다음 페이지 링크가 포함 된 응답을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-127">The API returns response with next page link in case of multiple results.</span></span> <span data-ttu-id="82f4b-128">다음 결과 집합을 얻으려면 nextlink @odata의 url에 대해 GET을 호출 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-128">For getting next set of results, simply call GET on the url from @odata.nextlink.</span></span> <span data-ttu-id="82f4b-129">Nextlink가 없거나 null이 아니면 모든 메시지가 검색 됩니다. @odata</span><span class="sxs-lookup"><span data-stu-id="82f4b-129">If @odata.nextlink is not present or null then all messages are retrieved.</span></span>

## <a name="prerequisites-to-access-teams-export-apis"></a><span data-ttu-id="82f4b-130">팀에 액세스 하기 위한 필수 구성 요소 Api 내보내기</span><span class="sxs-lookup"><span data-stu-id="82f4b-130">Prerequisites to access Teams Export APIs</span></span> 

- <span data-ttu-id="82f4b-131">팀 내보내기 Api는 현재 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-131">Teams Export APIs are currently in preview.</span></span> <span data-ttu-id="82f4b-132">Api에 대해 [필요한 라이선스가](https://aka.ms/teams-changenotification-licenses) 있는 사용자와 테 넌 트 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-132">It will only be available to users and tenants that have the [required licenses](https://aka.ms/teams-changenotification-licenses) for APIs.</span></span> <span data-ttu-id="82f4b-133">앞으로 Microsoft는 사용자 또는 고객이 API를 통해 액세스 하는 데이터 양에 따라 추가 요금을 지불 하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-133">In the future, Microsoft may require you or your customers to pay additional fees based on the amount of data accessed through the API.</span></span>
- <span data-ttu-id="82f4b-134">중요 한 데이터에 액세스 하는 microsoft Graph Api는 보호 된 Api로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-134">Microsoft Teams APIs in Microsoft Graph that access sensitive data are considered protected APIs.</span></span> <span data-ttu-id="82f4b-135">내보내기 Api를 사용 하려면 권한 및 승인 이상의 추가 유효성 검사가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-135">Export APIs require that you have additional validation, beyond permissions and consent, before you can use them.</span></span> <span data-ttu-id="82f4b-136">이러한 보호 된 Api에 대 한 액세스 권한을 요청 하려면 [요청 양식을](https://aka.ms/teamsgraph/requestaccess)작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-136">To request access to these protected APIs, complete the [request form](https://aka.ms/teamsgraph/requestaccess).</span></span>
- <span data-ttu-id="82f4b-137">응용 프로그램 사용 권한은 로그인 한 사용자 없이 실행 되는 앱에서 사용 됩니다. 응용 프로그램 권한은 관리자만 였음을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-137">Application permissions are used by apps that run without a signed-in user present; application permissions can only be consented by an administrator.</span></span> <span data-ttu-id="82f4b-138">다음과 같은 사용 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-138">The following permissions are needed:</span></span>

    - <span data-ttu-id="82f4b-139">*채팅. 모두*: 모든 1:1 및 그룹 채팅 메시지에 대 한 액세스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-139">*Chat.Read.All*: enables access to all 1:1 and Group chat messages</span></span> 
    - <span data-ttu-id="82f4b-140">*사용자. 모두*: 테 넌 트의 사용자 목록에 대 한 액세스를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-140">*User.Read.All*: enables access to the list of users for a tenant</span></span> 

## <a name="json-representation"></a><span data-ttu-id="82f4b-141">JSON 표현</span><span class="sxs-lookup"><span data-stu-id="82f4b-141">JSON representation</span></span>

<span data-ttu-id="82f4b-142">다음 예제는 리소스의 JSON 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="82f4b-142">The following example is a JSON representation of the resource:</span></span>

<span data-ttu-id="82f4b-143">네임 스페이스: microsoft graph</span><span class="sxs-lookup"><span data-stu-id="82f4b-143">Namespace: microsoft.graph</span></span>

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
><span data-ttu-id="82f4b-144">자원 메시지 리소스에 대 한 자세한 내용은 [메시지 자원 형식](https://docs.microsoft.com/graph/api/resources/chatmessage) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82f4b-144">For more details on chatMessage resource, see the [chatMessage resource type](https://docs.microsoft.com/graph/api/resources/chatmessage) article.</span></span>
