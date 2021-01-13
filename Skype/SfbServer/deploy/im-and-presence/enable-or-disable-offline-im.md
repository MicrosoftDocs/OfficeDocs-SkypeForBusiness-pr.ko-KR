---
title: 비즈니스용 Skype 서버에서 오프라인 IM(인스턴트 메시징)을 사용하도록 설정하거나 사용하지 않도록 설정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: 비즈니스용 Skype 서버에서 오프라인 IM(인스턴트 메시징)을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801948"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="36ad9-103">비즈니스용 Skype 서버에서 오프라인 IM(인스턴트 메시징)을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="36ad9-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="36ad9-104">비즈니스용 Skype 서버에서 오프라인 IM(인스턴트 메시징)을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="36ad9-105">비즈니스용 Skype 서버에서 오프라인 IM(인스턴트 메시징) 사용</span><span class="sxs-lookup"><span data-stu-id="36ad9-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="36ad9-106">오프라인 IM은 비즈니스용 Skype 클라이언트(2016 C2R 빌드 16.0.6701.1000 이상)에서 기본 제공되는 클라이언트 쪽 기능으로, EWS(Exchange 웹 서비스)를 활용하여 비즈니스용 Skype 클라이언트에서 사용자의 Exchange 사서함으로 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="36ad9-107">오프라인 IM은 EWS(Exchange 웹 서비스)를 사용하여 비즈니스용 Skype 클라이언트에서 받는 사람의 사서함으로 오프라인 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="36ad9-108">오프라인 메시지를 보내기 위해 비즈니스용 Skype 클라이언트에서 EWS를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="36ad9-109">인스턴트 메시징 및 현재 상태 계획에 대한 자세한 내용은 비즈니스용 Skype 서버의 인스턴트 메시징 및 현재 상태 계획을 [참조하세요.](../../plan-your-deployment/instant-messaging-and-presence.md)</span><span class="sxs-lookup"><span data-stu-id="36ad9-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36ad9-110">사용자의 사서함이 Exchange On-Premises에서 호스팅되는 경우 비즈니스용 Skype 클라이언트(2016 C2R 빌드 16.0.6920.1000)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="36ad9-111">비즈니스용 Skype 서버에서 오프라인 IM을 사용하도록 설정하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="36ad9-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="36ad9-112">비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="36ad9-113">다음 명령을 실행하여 오프라인 IM을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="36ad9-114">비즈니스용 Skype 서버 2015 CU3에서 EnableOfflineIM 옵션은 기본적으로 $True 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="36ad9-115">사용하지 않도록 설정하기 위해 이 값을 $False.</span><span class="sxs-lookup"><span data-stu-id="36ad9-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="36ad9-116">다음 명령을 실행하여 오프라인 IM을 저장할 수 있는 설정이 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="36ad9-117">Exchange와 오프라인 IM 통합</span><span class="sxs-lookup"><span data-stu-id="36ad9-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="36ad9-118">오프라인 메시지를 대화 기록 폴더에 자동 저장하지 않도록 설정하는 클라이언트 정책이 있는 경우 보낸 사람이 오프라인 IM을 사용할 수 없습니다(EnableIMAutoArchiving = $false.</span><span class="sxs-lookup"><span data-stu-id="36ad9-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="36ad9-119">받는 사람이 오프라인 메시지를 받을 수 없는지 확인할 수 있는 메커니즘은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="36ad9-120">동일한 조직 내에서 전송된 오프라인 메시지의 경우 메시지 클래스가 IM.Note.MissedConversation인 전자 메일 메시지로 수신되고 Outlook **부재** 중 대화 폴더와 비즈니스용 Skype 클라이언트의 최근 목록/대화 기록 탭에서 선택될 대화 기록에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="36ad9-121">페더타 조직에서 보낸 오프라인 메시지의 경우 IM.Note.MisssedConversation이 없는 전자 메일 메시지로 수신됩니다. 부재 중 대화 또는 대화 기록 폴더에서 선택되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="36ad9-122">문제 해결</span><span class="sxs-lookup"><span data-stu-id="36ad9-122">Troubleshooting</span></span>

<span data-ttu-id="36ad9-123">오프라인 메시지가 선택 및 처리된 경우부터 2분의 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="36ad9-124">오프라인 메시지를 처리하지 못하면 다음 디렉터리에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="36ad9-125">기본 비즈니스용 Skype ETL 로그는 오프라인 메시지 처리에 대한 정보를 포함하며 조사/문제 해결을 위한 최상의 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="36ad9-126">오프라인 메시지가 보내지 못하고 '임시 저장' 폴더가 메시지로 채워지고 있는 문제가 보고되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="36ad9-127">Exchange On-Premises 사서함에서 이 일어났습니다.</span><span class="sxs-lookup"><span data-stu-id="36ad9-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="36ad9-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span><span class="sxs-lookup"><span data-stu-id="36ad9-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
