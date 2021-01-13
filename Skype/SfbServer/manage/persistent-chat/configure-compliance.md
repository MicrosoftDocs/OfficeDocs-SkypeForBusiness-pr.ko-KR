---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대한 준수 서비스 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 준수 서비스를 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: ee7dbc3ad8e7eedcadcc60850e35b753c5fadb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815068"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="41e41-103">비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대한 준수 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="41e41-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="41e41-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 준수 서비스를 구성하는 방법을 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="41e41-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="41e41-105">관리자는 영구 채팅 준수를 통해 활동뿐만 아니라 영구 채팅 메시지의 보관 파일을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="41e41-106">준수 서비스는 참가자가 다음을 비롯한 각 영구 채팅 서버 대화와 관련된 데이터를 기록하고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="41e41-107">영구 채팅방에 참가</span><span class="sxs-lookup"><span data-stu-id="41e41-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="41e41-108">대화방 나가기</span><span class="sxs-lookup"><span data-stu-id="41e41-108">Leaves a chat room</span></span>

- <span data-ttu-id="41e41-109">메시지 게시</span><span class="sxs-lookup"><span data-stu-id="41e41-109">Posts a message</span></span>

- <span data-ttu-id="41e41-110">채팅 기록 보기</span><span class="sxs-lookup"><span data-stu-id="41e41-110">Views chat history</span></span>

- <span data-ttu-id="41e41-111">파일 업로드</span><span class="sxs-lookup"><span data-stu-id="41e41-111">Uploads a file</span></span>

- <span data-ttu-id="41e41-112">파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="41e41-112">Downloads a file</span></span>

<span data-ttu-id="41e41-113">이 정보는 필요한 경우 Compliance SQL 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="41e41-114">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="41e41-115">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="41e41-116">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="41e41-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="41e41-117">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="41e41-118">다음을 사용하여 준수 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41e41-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="41e41-119">토폴로지 작성기를 사용하여 준수 서비스를 사용하도록 설정한 후 **Set-CsPersistenChatComplianceConfiguration** cmdlet을 사용하여 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="41e41-120">또는</span><span class="sxs-lookup"><span data-stu-id="41e41-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="41e41-121">다음 매개 변수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-121">You can set the following parameters:</span></span>

- <span data-ttu-id="41e41-122">AdapterType - 어댑터 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="41e41-123">어댑터는 준수 데이터베이스의 데이터를 특정 형식으로 변환하는 타사 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="41e41-124">XML이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-124">XML is the default.</span></span>

- <span data-ttu-id="41e41-125">OneChatRoomPerOutputFile - 이 매개 변수를 사용하여 각 대화방에 대해 별도의 보고서를 만들 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="41e41-126">AddChatRoomDetails - 이 매개 변수를 사용하도록 설정하면 데이터베이스의 각 대화방에 대한 추가 세부 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="41e41-127">이 설정은 데이터베이스 크기를 크게 늘 수 있기 때문에 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="41e41-128">AddUserDetails - 이 매개 변수를 사용하도록 설정하면 데이터베이스의 각 대화방 사용자에 대한 추가 세부 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="41e41-129">이 설정은 데이터베이스 크기를 크게 늘 수 있기 때문에 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="41e41-130">IDENTITY - 이 매개 변수를 사용하면 전역, 사이트 및 서비스 수준을 포함하여 특정 컬렉션에 대한 준수 설정의 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="41e41-131">기본값은 전역 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-131">The default is the global level.</span></span> 

- <span data-ttu-id="41e41-132">RunInterval - 이 매개 변수는 서버에서 다음 준수 출력 파일을 만드는 시간(기본값은 15분)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="41e41-133">사용자 지정된 준수 어댑터 사용</span><span class="sxs-lookup"><span data-stu-id="41e41-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="41e41-134">영구 채팅 서버와 함께 설치된 XmlAdapter를 사용하는 대신 사용자 지정 어댑터를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="41e41-135">이렇게 하려면 **IComplianceAdapter** 인터페이스를 구현하는 공용 클래스가 포함된 .NET Framework 어셈블리를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="41e41-136">이 어셈블리는 영구 채팅 서버 풀에 있는 각 서버의 영구 채팅 서버 설치 폴더에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="41e41-137">준수 서버 중 하나가 어댑터에 준수 데이터를 제공할 수 있지만, 준수 서버가 여러 어댑터 인스턴스에 대해 중복 준수 데이터를 제공하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="41e41-138">인터페이스는 네임스페이스의 Compliance.dll 어셈블리에 정의되어  `Microsoft.Rtc.Internal.Chat.Server.Compliance` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="41e41-139">이 인터페이스는 사용자 지정 어댑터가 구현해야 하는 두 개의 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="41e41-140">영구 채팅 준수 서버는 어댑터를 처음 로드할 때 다음 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="41e41-141">준수 어댑터와 관련된 영구 채팅 준수  `AdapterConfig` 구성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="41e41-142">영구 채팅 준수 서버는 변환할 새 데이터가 있는 한 주기적인 간격으로 다음 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="41e41-143">이 시간 간격은 영구 채팅 준수 구성에 설정된  `RunInterval` 간격과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="41e41-144">이 메서드를 마지막으로 호출한 시간부터 수집된 대화  `ConversationCollection` 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="41e41-145">XSLT 정의 파일 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="41e41-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="41e41-146">준수 데이터는 XSLT 정의 파일을 사용하여 조직에 가장 적합한 형식으로 변환할 수 있는 XML로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="41e41-147">이 항목에서는 준수 서비스가 만드는 XML 파일에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="41e41-148">또한 XSLT 정의 및 출력 파일에 대한 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="41e41-149">출력 형식</span><span class="sxs-lookup"><span data-stu-id="41e41-149">Output format</span></span>

<span data-ttu-id="41e41-150">준수 서비스 출력은 다음 코드 예제와 같이 대화(Conversation 요소)와 메시지(Messages 요소)로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

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

<span data-ttu-id="41e41-151">Conversation 요소에는 Channel, FirstMessage, StartTimeUTC 및 EndTimeUTC의 네 가지 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="41e41-152">Channel 요소에는 대화방의 URI(Uniform Resource Identifier)가 포함되며 FirstMessage 요소는 Messages 요소의 첫 번째 메시지를 기술합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="41e41-153">StartTimeUTC 및 EndTimeUTC 요소는 다음 코드 샘플과 같이 대화의 시작 및 종료 시간을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="41e41-154">Message 요소에는 Sender 및 DateTimeUTC의 두 가지 요소와 Type, Content 및 ID의 세 가지 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="41e41-155">Sender 요소는 메시지를 보내는 사용자를 나타내며 DateTimeUTC 요소는 다음 코드 예제와 같이 이벤트가 발생하는 경우를 나타내며,</span><span class="sxs-lookup"><span data-stu-id="41e41-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="41e41-156">다음 표에서는 메시지 특성 유형, 콘텐츠 및 ID에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="41e41-157">**Messages 요소 특성**</span><span class="sxs-lookup"><span data-stu-id="41e41-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="41e41-158">**특성**</span><span class="sxs-lookup"><span data-stu-id="41e41-158">**Attribute**</span></span>|<span data-ttu-id="41e41-159">**설명**</span><span class="sxs-lookup"><span data-stu-id="41e41-159">**Description**</span></span>|<span data-ttu-id="41e41-160">**선택 사항/필수**</span><span class="sxs-lookup"><span data-stu-id="41e41-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41e41-161">유형</span><span class="sxs-lookup"><span data-stu-id="41e41-161">Type</span></span>  <br/> |<span data-ttu-id="41e41-p114">메시지 유형을 지정합니다. 메시지 유형은 Message 요소 메시지 유형 테이블에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="41e41-164">필수</span><span class="sxs-lookup"><span data-stu-id="41e41-164">Required</span></span>  <br/> |
|<span data-ttu-id="41e41-165">콘텐츠</span><span class="sxs-lookup"><span data-stu-id="41e41-165">Content</span></span>  <br/> |<span data-ttu-id="41e41-p115">메시지 콘텐츠를 포함합니다. 유형이 Join 또는 Part인 메시지는 이 특성을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="41e41-168">선택</span><span class="sxs-lookup"><span data-stu-id="41e41-168">Optional</span></span>  <br/> |
|<span data-ttu-id="41e41-169">ID</span><span class="sxs-lookup"><span data-stu-id="41e41-169">ID</span></span>  <br/> |<span data-ttu-id="41e41-p116">콘텐츠의 고유한 ID를 지정합니다. 이 특성은 유형이 Chat인 메시지에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="41e41-172">선택</span><span class="sxs-lookup"><span data-stu-id="41e41-172">Optional</span></span>  <br/> |

<span data-ttu-id="41e41-p117">각 Sender 요소에는 사용자 이름, ID, 전자 메일, 내부 및 URI의 5가지 특성이 포함됩니다. 이러한 특성은 다음 표에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="41e41-175">**Sender 요소 특성**</span><span class="sxs-lookup"><span data-stu-id="41e41-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="41e41-176">**특성**</span><span class="sxs-lookup"><span data-stu-id="41e41-176">**Attribute**</span></span>|<span data-ttu-id="41e41-177">**설명**</span><span class="sxs-lookup"><span data-stu-id="41e41-177">**Description**</span></span>|<span data-ttu-id="41e41-178">**선택 사항/필수**</span><span class="sxs-lookup"><span data-stu-id="41e41-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41e41-179">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="41e41-179">Username</span></span>  <br/> |<span data-ttu-id="41e41-180">보낸 사람의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="41e41-181">선택</span><span class="sxs-lookup"><span data-stu-id="41e41-181">Optional</span></span>  <br/> |
|<span data-ttu-id="41e41-182">ID</span><span class="sxs-lookup"><span data-stu-id="41e41-182">ID</span></span>  <br/> |<span data-ttu-id="41e41-183">보낸 사람 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="41e41-184">필수</span><span class="sxs-lookup"><span data-stu-id="41e41-184">Required</span></span>  <br/> |
|<span data-ttu-id="41e41-185">전자 메일</span><span class="sxs-lookup"><span data-stu-id="41e41-185">Email</span></span>  <br/> |<span data-ttu-id="41e41-186">보낸 사람 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="41e41-187">선택</span><span class="sxs-lookup"><span data-stu-id="41e41-187">Optional</span></span>  <br/> |
|<span data-ttu-id="41e41-188">내부</span><span class="sxs-lookup"><span data-stu-id="41e41-188">Internal</span></span>  <br/> |<span data-ttu-id="41e41-p118">사용자가 내부 사용자 또는 페더레이션 사용자인지를 확인합니다. 값이 True로 설정된 경우 사용자가 내부 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="41e41-191">선택</span><span class="sxs-lookup"><span data-stu-id="41e41-191">Optional</span></span>  <br/> |
|<span data-ttu-id="41e41-192">Uri</span><span class="sxs-lookup"><span data-stu-id="41e41-192">Uri</span></span>  <br/> |<span data-ttu-id="41e41-193">사용자의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="41e41-194">필수</span><span class="sxs-lookup"><span data-stu-id="41e41-194">Required</span></span>  <br/> |

<span data-ttu-id="41e41-195">다음 예에서는 Messages 요소에 포함될 수 있는 메시지 유형을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="41e41-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="41e41-196">또한 각 요소가 사용되는 방법에 대한 예도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="41e41-197">Join - 사용자가 채팅방에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="41e41-198">부분 - 사용자가 대화방에서 나 퇴장합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="41e41-199">Chat - 보낸 사람 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="41e41-200">Backchat - 사용자가 채팅 기록에서 콘텐츠를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="41e41-201">파일 업로드 - 사용자가 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="41e41-202">파일 다운로드 - 사용자가 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="41e41-203">기본 영구 채팅 출력 XSD 및 예제 XSL 변환</span><span class="sxs-lookup"><span data-stu-id="41e41-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="41e41-204">다음 코드 예제에는 준수 서버의 기본 출력이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-204">The following code sample contains the default output from the Compliance Server:</span></span>

```xml
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

<span data-ttu-id="41e41-205">다음 코드 샘플에는 샘플 XSL 변환이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41e41-205">The following code sample contains a sample XSL transform:</span></span>

```xml
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
