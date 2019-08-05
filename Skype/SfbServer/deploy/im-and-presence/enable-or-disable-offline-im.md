---
title: 비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM) 사용 또는 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM)를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 77078b6092dc1d23dde1315c505c5baf26798b86
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191535"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="924ee-103">비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM) 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="924ee-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="924ee-104">비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM)를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="924ee-105">비즈니스용 Skype 서버에서 오프 라인 인스턴트 메시지 (IM) 사용</span><span class="sxs-lookup"><span data-stu-id="924ee-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="924ee-106">오프 라인 IM은 비즈니스용 skype 클라이언트 (2016 C2R 빌드 16.0.6701.1000 이상)에 기본으로 제공 되는 클라이언트측 기능으로, EWS (Exchange Web Services)를 사용 하 여 사용자의 Exchange 사서함으로 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="924ee-107">오프 라인 IM은 비즈니스용 Skype 클라이언트에서 받는 사람 사서함으로 오프 라인 메시지를 보내는 데 사용 됩니다 (Exchange Web Services (EWS)).</span><span class="sxs-lookup"><span data-stu-id="924ee-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="924ee-108">EWS는 비즈니스용 Skype 클라이언트에서 오프 라인 메시지를 보내기 위해 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="924ee-109">인스턴트 메시지 및 현재 상태에 대 한 계획 수립에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 인스턴트 메시지 및 현재 상태에 대 한 계획](../../plan-your-deployment/instant-messaging-and-presence.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="924ee-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="924ee-110">사용자의 사서함이 Exchange 온-프레미스에 호스팅되는 경우 비즈니스용 Skype 클라이언트 (2016 C2R build 16.0.6920.1000)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="924ee-111">비즈니스용 Skype 서버에서 오프 라인 메신저 기능을 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="924ee-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="924ee-112">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="924ee-113">다음 명령을 실행 하 여 오프 라인 IM을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-113">Run the following command to enable Offline IM.</span></span>
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="924ee-114">비즈니스용 Skype Server 2015 CU3 이상의 EnableOfflineIM 옵션은 기본적으로 $True으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="924ee-115">사용 하지 않으려면이 값을 $False로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="924ee-116">다음 명령을 실행 하 여 오프 라인 메신저 대화를 저장 하는 기능이 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="924ee-117">Exchange와의 오프 라인 IM 통합</span><span class="sxs-lookup"><span data-stu-id="924ee-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="924ee-118">대화 내용 폴더에 오프 라인 메시지 자동 저장을 사용 하지 않도록 설정 하는 클라이언트 정책이 있는 경우 보낸 사람에 게 오프 라인 IM을 사용할 수 없습니다 (EnableIMAutoArchiving = $false).</span><span class="sxs-lookup"><span data-stu-id="924ee-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="924ee-119">받는 사람이 오프 라인 메시지를 받을 수 있는지 확인 하는 메커니즘은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="924ee-120">동일한 조직 내에서 보낸 오프 라인 메시지의 경우 IM의 메시지 클래스를 사용 하 여 전자 메일 메시지로 수신 됩니다. 참고. 대화는 Outlook **부재 중 대화** 폴더에 포함 되며, 비즈니스용 Skype 클라이언트의 최근 목록/대화 내용 탭에서 선택 되는 대화 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="924ee-121">페더레이션 조직에서 보낸 오프 라인 메시지의 경우 IM을 사용 하지 않고 전자 메일 메시지로 수신 됩니다. MisssedConversation는 부재 중 대화 또는 대화 내용 폴더에 선택 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="924ee-122">해결사</span><span class="sxs-lookup"><span data-stu-id="924ee-122">Troubleshooting</span></span>

<span data-ttu-id="924ee-123">오프 라인 메시지를 선택 하 고 처리 하는 경우에는 2 분 타이머가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="924ee-124">오프 라인 메시지를 처리할 수 없는 경우 다음 디렉터리에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="924ee-125">기본 비즈니스용 Skype ETL 로그에는 오프 라인 메시지 처리에 대 한 정보가 포함 되며 조사/문제 해결을 위한 가장 좋은 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="924ee-126">오프 라인 메시지를 보낼 수 없고 ' 임시 보관 함 ' 폴더가 메시지로 채워져 있는 동안 문제가 보고 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="924ee-127">Exchange 온-프레미스 사서함에서 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="924ee-128">6/14/2016의 모든 C2R 채널에서 문제가 해결 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="924ee-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
