---
title: 영구 채팅 추가 기능
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 영구 채팅 페이지의 추가 기능 섹션을 사용하여 URL을 영구 채팅방과 연결할 수 있습니다. 이러한 URL은 대화 Extensibility 창의 대화방에 있는 클라이언트에 표시됩니다. 관리자는 등록된 추가 기능 목록에 추가 기능을 추가해야 합니다. 채팅방 관리자/작성자는 채팅방을 등록된 추가 기능 중 하나와 연결해야 사용자가 클라이언트에서 이 업그레이드를 볼 수 있습니다.
ms.openlocfilehash: c90383a26c658e8da73df09368a5d8fe04cfe69b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099504"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="5226e-105">영구 채팅 추가 기능</span><span class="sxs-lookup"><span data-stu-id="5226e-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="5226e-106">영구 채팅  페이지의 추가 기능  섹션을 사용하여 URL을 영구 채팅방과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="5226e-107">이러한 URL은 대화 Extensibility 창의 대화방에 있는 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="5226e-108">관리자는 등록된 추가 기능 목록에 추가 기능을 추가해야 합니다. 채팅방 관리자/작성자는 채팅방을 등록된 추가 기능 중 하나와 연결해야 사용자가 클라이언트에서 이 업그레이드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="5226e-109">추가 기능은 방 내의 환경을 확장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="5226e-110">일반적인 추가 기능으로는 주식 시세 표시가 대화방에 게시될 때 가로채고 주식 기록을 Extensibility 창에 표시하는 Silverlight 응용 프로그램을 표시하는 URL이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="5226e-111">또 다른 예로는 OneNote 2013 URL을 채팅방에 추가 기능으로 포함하여 "관심 항목" 또는 "오늘의 항목"과 같은 일부 공유 컨텍스트를 포함하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="5226e-112">영구 채팅방에 대한 추가 기능을 만들 내용은 [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015을 참조하세요.](../../manage/persistent-chat/configure-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="5226e-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="5226e-113">영구 채팅 관리자인 경우 제어판 또는 cmdlet을 사용하여 추가 기능을 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="5226e-114">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="5226e-114">Tasks that you can perform</span></span>

<span data-ttu-id="5226e-115">**추가 기능** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="5226e-116">비즈니스용 Skype 서버 2015에서 영구 채팅방에 대한 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="5226e-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="5226e-117">채팅방에 대해 추가 기능을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="5226e-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="5226e-118">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="5226e-119">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="5226e-120">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 열고 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5226e-121">제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 [Open Lync Server Administrative Tools를 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)</span><span class="sxs-lookup"><span data-stu-id="5226e-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span>

3. <span data-ttu-id="5226e-122">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **추가 기능** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="5226e-123">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절한 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="5226e-124">**추가 기능** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="5226e-125">서비스 **선택에서** 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당하는 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="5226e-126">추가 기능은 풀 간에 이동하거나 서로 다른 풀 간에 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="5226e-127">**새 추가 기능** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="5226e-128">**이름** 에서 새 추가 기능의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="5226e-p107">**URL** 에서 추가 기능과 연결할 URL을 지정합니다. http 및 https 프로토콜의 URL만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="5226e-131">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5226e-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5226e-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5226e-132">See also</span></span>

<span data-ttu-id="5226e-133">영구 채팅 서버 기능에 대한 자세한 내용은 [Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)및 [Manage Persistent Chat Server in Skype for Business Server 2015를](../../manage/persistent-chat/persistent-chat.md)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5226e-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>