---
title: 영구 채팅 서버에 대한 준수 서비스 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 준수 서비스를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: a02384c68c04798ea453b94bf736a2c6ff276397
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991993"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="fcfe0-103">영구 채팅 서버에 대한 준수 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="fcfe0-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="fcfe0-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 준수 서비스를 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="fcfe0-105">영구 채팅 준수를 통해 관리자는 영구 채팅 메시지 및 활동을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="fcfe0-106">준수 서비스는 참가자가 다음을 비롯 한 각 영구 채팅 서버 대화와 관련 된 데이터를 기록 하 고 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="fcfe0-107">영구 대화방에 참가</span><span class="sxs-lookup"><span data-stu-id="fcfe0-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="fcfe0-108">채팅방을 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-108">Leaves a chat room</span></span>

- <span data-ttu-id="fcfe0-109">메시지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-109">Posts a message</span></span>

- <span data-ttu-id="fcfe0-110">채팅 기록 보기</span><span class="sxs-lookup"><span data-stu-id="fcfe0-110">Views chat history</span></span>

- <span data-ttu-id="fcfe0-111">파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-111">Uploads a file</span></span>

- <span data-ttu-id="fcfe0-112">파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-112">Downloads a file</span></span>

<span data-ttu-id="fcfe0-113">이 정보는 필요에 따라 준수 SQL 데이터베이스에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="fcfe0-114">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="fcfe0-115">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="fcfe0-116">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="fcfe0-117">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="fcfe0-118">Windows PowerShell을 사용 하 여 준수 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="fcfe0-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="fcfe0-119">토폴로지 작성기를 사용 하 여 준수 서비스를 사용 하도록 설정한 후 **CsPersistenChatComplianceConfiguration** cmdlet을 사용 하 여 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="fcfe0-120">또는</span><span class="sxs-lookup"><span data-stu-id="fcfe0-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="fcfe0-121">다음 매개 변수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-121">You can set the following parameters:</span></span>

- <span data-ttu-id="fcfe0-122">AdapterType-어댑터 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="fcfe0-123">어댑터는 준수 데이터베이스의 데이터를 특정 형식으로 변환 하는 타사 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="fcfe0-124">XML이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-124">XML is the default.</span></span>

- <span data-ttu-id="fcfe0-125">OneChatRoomPerOutputFile-이 매개 변수를 사용 하면 각 채팅방에 대해 별도의 보고서를 만들도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="fcfe0-126">AddChatRoomDetails-이 매개 변수를 사용 하면 데이터베이스의 각 채팅방에 대 한 추가 세부 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="fcfe0-127">이 설정은 데이터베이스 크기를 크게 증가 시킬 수 있으므로 기본적으로 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="fcfe0-128">AddUserDetails-사용 하는 경우이 매개 변수는 데이터베이스의 각 채팅방 사용자에 대 한 추가 세부 정보를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="fcfe0-129">이 설정은 데이터베이스 크기를 크게 증가 시킬 수 있으므로 기본적으로 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="fcfe0-130">Id-이 매개 변수는 전역, 사이트 및 서비스 수준을 포함 하 여 규정 준수 설정을 특정 컬렉션에 대해 범위 지정 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="fcfe0-131">기본값은 전역 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-131">The default is the global level.</span></span> 

- <span data-ttu-id="fcfe0-132">RunInterval-이 매개 변수는 서버가 다음 준수 출력 파일을 만들기 까지의 시간 (기본값은 15 분)을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="fcfe0-133">사용자 지정 준수 어댑터 사용</span><span class="sxs-lookup"><span data-stu-id="fcfe0-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="fcfe0-134">영구 채팅 서버와 함께 설치 된 XmlAdapter를 사용 하는 대신 사용자 지정 어댑터를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="fcfe0-135">이를 수행 하려면 **IComplianceAdapter** 인터페이스를 구현 하는 공용 클래스를 포함 하는 .net Framework 어셈블리를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="fcfe0-136">이 어셈블리는 영구 채팅 서버 풀에 있는 각 서버의 영구 채팅 서버 설치 폴더에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="fcfe0-137">규정 준수 서버 중 하나가 어댑터에 준수 데이터를 제공할 수 있지만, 규정 준수 서버는 어댑터의 여러 인스턴스에 대 한 중복 준수 데이터를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="fcfe0-138">인터페이스는 네임 스페이스 `Microsoft.Rtc.Internal.Chat.Server.Compliance`의 준수 .dll 어셈블리에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="fcfe0-139">인터페이스는 사용자 지정 어댑터에서 구현 해야 하는 두 가지 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="fcfe0-140">영구 채팅 준수 서버는 어댑터가 처음 로드 될 때 다음 메서드를 호출 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="fcfe0-141">에 `AdapterConfig` 는 준수 어댑터와 관련 된 지속적인 채팅 준수 구성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="fcfe0-142">영구 채팅 준수 서버는 변환할 새 데이터가 있는 경우 정기적으로 다음 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="fcfe0-143">이 시간 간격은 영구 채팅 준수 구성 `RunInterval` 에 설정 된 as와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="fcfe0-144">에 `ConversationCollection` 는이 메서드를 마지막으로 호출 했을 때 수집 된 대화 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="fcfe0-145">XSLT 정의 파일 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fcfe0-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="fcfe0-146">준수 데이터는 XML로 제공 되며, XSLT 정의 파일을 사용 하 여 조직에 가장 잘 맞는 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="fcfe0-147">이 항목에서는 규정 준수 서비스가 만드는 XML 파일에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="fcfe0-148">또한 XSLT 정의 및 출력 파일에 대 한 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="fcfe0-149">출력 형식</span><span class="sxs-lookup"><span data-stu-id="fcfe0-149">Output format</span></span>

<span data-ttu-id="fcfe0-150">준수 서비스 출력은 다음 코드 예제에 표시 된 것 처럼 대화 (대화 요소)와 메시지 (메시지 요소) 순으로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

<span data-ttu-id="fcfe0-151">대화 요소에는 4 개의 요소 (채널, FirstMessage, StartTimeUTC 및 EndTimeUTC)가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="fcfe0-152">채널 요소는 채팅방의 URI (Uniform Resource Identifier)를 포함 하 고 FirstMessage 요소는 Messages 요소의 첫 번째 메시지를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="fcfe0-153">StartTimeUTC 및 EndTimeUTC 요소는 다음 코드 예제에 표시 된 것 처럼 대화에 대 한 시작 및 종료 시간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```XML
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="fcfe0-154">Message 요소에는 두 개의 요소 (Sender 및 DateTimeUTC)와 세 가지 특성 (유형, 콘텐츠 및 ID)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="fcfe0-155">Sender 요소는 메시지를 보내는 사용자를 나타내고 DateTimeUTC 요소는 다음 코드 예제에 표시 된 대로 이벤트가 발생 하는 시기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```XML
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="fcfe0-156">다음 표에서는 메시지 특성 유형, 콘텐츠 및 ID에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="fcfe0-157">**메시지 요소 특성**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="fcfe0-158">**특성**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-158">**Attribute**</span></span>|<span data-ttu-id="fcfe0-159">**설명**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-159">**Description**</span></span>|<span data-ttu-id="fcfe0-160">**선택/필수**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcfe0-161">유형</span><span class="sxs-lookup"><span data-stu-id="fcfe0-161">Type</span></span>  <br/> |<span data-ttu-id="fcfe0-162">메시지 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-162">Specifies the message type.</span></span> <span data-ttu-id="fcfe0-163">메시지 유형은 메시지 요소 메시지 유형 테이블에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-163">The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="fcfe0-164">필수</span><span class="sxs-lookup"><span data-stu-id="fcfe0-164">Required</span></span>  <br/> |
|<span data-ttu-id="fcfe0-165">콘텐트가</span><span class="sxs-lookup"><span data-stu-id="fcfe0-165">Content</span></span>  <br/> |<span data-ttu-id="fcfe0-166">메시지의 내용이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-166">Contains the content of the message.</span></span> <span data-ttu-id="fcfe0-167">조인 또는 파트 유형의 메시지는이 특성을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-167">Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="fcfe0-168">선택</span><span class="sxs-lookup"><span data-stu-id="fcfe0-168">Optional</span></span>  <br/> |
|<span data-ttu-id="fcfe0-169">I</span><span class="sxs-lookup"><span data-stu-id="fcfe0-169">ID</span></span>  <br/> |<span data-ttu-id="fcfe0-170">콘텐츠의 고유 ID를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-170">Specifies the unique ID of the content.</span></span> <span data-ttu-id="fcfe0-171">이 특성은 채팅 유형의 메시지에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-171">This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="fcfe0-172">선택</span><span class="sxs-lookup"><span data-stu-id="fcfe0-172">Optional</span></span>  <br/> |

<span data-ttu-id="fcfe0-173">각 보낸 사람 요소에는 사용자 이름, ID, 전자 메일, 내부, URI의 다섯 가지 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-173">Each Sender element contains five attributes: the user name, ID, email, internal, and URI.</span></span> <span data-ttu-id="fcfe0-174">다음 표에서는 이러한 특성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-174">These attributes are described in the following table.</span></span>

<span data-ttu-id="fcfe0-175">**보낸 사람 요소 특성**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="fcfe0-176">**특성**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-176">**Attribute**</span></span>|<span data-ttu-id="fcfe0-177">**설명**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-177">**Description**</span></span>|<span data-ttu-id="fcfe0-178">**선택/필수**</span><span class="sxs-lookup"><span data-stu-id="fcfe0-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcfe0-179">사용자</span><span class="sxs-lookup"><span data-stu-id="fcfe0-179">Username</span></span>  <br/> |<span data-ttu-id="fcfe0-180">보낸 사람의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="fcfe0-181">선택</span><span class="sxs-lookup"><span data-stu-id="fcfe0-181">Optional</span></span>  <br/> |
|<span data-ttu-id="fcfe0-182">I</span><span class="sxs-lookup"><span data-stu-id="fcfe0-182">ID</span></span>  <br/> |<span data-ttu-id="fcfe0-183">보낸 사람의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="fcfe0-184">필수</span><span class="sxs-lookup"><span data-stu-id="fcfe0-184">Required</span></span>  <br/> |
|<span data-ttu-id="fcfe0-185">메일 주소</span><span class="sxs-lookup"><span data-stu-id="fcfe0-185">Email</span></span>  <br/> |<span data-ttu-id="fcfe0-186">보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="fcfe0-187">선택</span><span class="sxs-lookup"><span data-stu-id="fcfe0-187">Optional</span></span>  <br/> |
|<span data-ttu-id="fcfe0-188">내부용</span><span class="sxs-lookup"><span data-stu-id="fcfe0-188">Internal</span></span>  <br/> |<span data-ttu-id="fcfe0-189">사용자가 내부 사용자 인지 페더레이션 사용자 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-189">Determines whether the user is an internal user or a federated user.</span></span> <span data-ttu-id="fcfe0-190">값이 true로 설정 되 면 사용자는 내부용입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-190">If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="fcfe0-191">선택</span><span class="sxs-lookup"><span data-stu-id="fcfe0-191">Optional</span></span>  <br/> |
|<span data-ttu-id="fcfe0-192">Url</span><span class="sxs-lookup"><span data-stu-id="fcfe0-192">Uri</span></span>  <br/> |<span data-ttu-id="fcfe0-193">사용자의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="fcfe0-194">필수</span><span class="sxs-lookup"><span data-stu-id="fcfe0-194">Required</span></span>  <br/> |

<span data-ttu-id="fcfe0-195">다음 예제에서는 Messages 요소에 포함 될 수 있는 메시지 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="fcfe0-196">또한 각 요소를 사용 하는 방법에 대 한 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="fcfe0-197">참가-사용자가 채팅방에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-197">Join - A user joins a chat room.</span></span>

```XML
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="fcfe0-198">파트-사용자가 채팅방을 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-198">Part - A user leaves a chat room.</span></span>

```XML
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="fcfe0-199">채팅-보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-199">Chat - The sender's email address.</span></span>

```XML
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="fcfe0-200">배경 채팅-사용자가 채팅 기록에서 콘텐츠를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-200">Backchat - A user requests content from chat history.</span></span>

```XML
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="fcfe0-201">파일 업로드-사용자가 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-201">File upload - A user uploads a file.</span></span>

```XML
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="fcfe0-202">파일 다운로드-사용자가 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-202">File download - A user downloads a file.</span></span>

```XML
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="fcfe0-203">기본 영구 채팅 출력 XSD 및 예제 XSL 변환</span><span class="sxs-lookup"><span data-stu-id="fcfe0-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="fcfe0-204">다음 코드 샘플에는 준수 서버의 기본 출력이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-204">The following code sample contains the default output from the Compliance Server:</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="fcfe0-205">다음 코드 샘플에는 샘플 XSL 변환이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcfe0-205">The following code sample contains a sample XSL transform:</span></span>

```XML
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
