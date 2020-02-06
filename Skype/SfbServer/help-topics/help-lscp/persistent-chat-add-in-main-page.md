---
title: 영구 채팅 추가 기능 기본 페이지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: 영구 채팅 페이지의 추가 기능 섹션을 사용 하 여 Url을 영구 채팅방과 연결할 수 있습니다. 이러한 URL은 클라이언트에서 채팅방의 대화 확장성 창에 표시됩니다. 관리자가 등록된 추가 기능 목록에 추가 기능을 추가하고, 채팅방 관리자/생성자가 등록된 추가 기능 중 하나와 채팅방을 연결해야 사용자가 클라이언트에서 이 업그레이드를 확인할 수 있습니다.
ms.openlocfilehash: 60cf60c6f6691725161182c5cc4e5c2fd38a0576
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822581"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="22e6e-105">영구 채팅 추가 기능 기본 페이지</span><span class="sxs-lookup"><span data-stu-id="22e6e-105">Persistent Chat Add-in Main Page</span></span>

<span data-ttu-id="22e6e-106">**영구 채팅** 페이지의 **추가 기능** 섹션을 사용 하 여 url을 영구 채팅방과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="22e6e-107">이러한 URL은 클라이언트에서 채팅방의 대화 확장성 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="22e6e-108">관리자가 등록된 추가 기능 목록에 추가 기능을 추가하고, 채팅방 관리자/생성자가 등록된 추가 기능 중 하나와 채팅방을 연결해야 사용자가 클라이언트에서 이 업그레이드를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="22e6e-109">추가 기능은 채팅방 내 환경을 확장하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="22e6e-110">일반적인 추가 기능에는 주식 시세 표시기가 채팅방에 게시 되는 경우를 가로채는 Silverlight 응용 프로그램을 가리키는 URL이 포함 될 수 있으며, 확장성 창에 주식 기록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="22e6e-111">다른 예로는 "Top of mind" 또는 "Topic of the day"와 같이 몇 가지 공유 컨텍스트를 포함하도록 채팅방에 OneNote 2013 URL을 추가 기능으로 포함하는 것을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="22e6e-112">영구 채팅방 용 추가 기능을 만들려면 비즈니스용 [Skype 서버 2015에서 영구 채팅방에 대 한 추가 기능 구성을](../../manage/persistent-chat/configure-add-ins.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22e6e-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="22e6e-113">영구 채팅 관리자 인 경우 제어판 또는 Windows PowerShell cmdlet을 사용 하 여 추가 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="22e6e-114">수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="22e6e-114">Tasks you can perform</span></span>

<span data-ttu-id="22e6e-115">**추가 기능** 페이지에서는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="22e6e-116">영구 채팅방에 대해 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="22e6e-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="22e6e-117">채팅방의 추가 기능을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="22e6e-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="22e6e-118">다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="22e6e-119">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="22e6e-120">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="22e6e-121">제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22e6e-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="22e6e-122">왼쪽 탐색 모음에서 **영구 채팅**을 클릭한 다음 **추가 기능**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="22e6e-123">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="22e6e-124">**추가 기능** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="22e6e-125">**서비스 선택**에서 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="22e6e-126">추가 기능은 한 풀에서 다른 풀로 이동하거나 여러 풀 간에 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="22e6e-127">**새 추가 기능**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="22e6e-128">**이름**에 새 추가 기능 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="22e6e-p107">**URL**에 추가 기능과 연결할 URL을 지정합니다. URL은 http 및 https 프로토콜로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="22e6e-131">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22e6e-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="22e6e-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22e6e-132">See also</span></span>

<span data-ttu-id="22e6e-133">영구 채팅 서버 기능 및 기능에 대 한 자세한 내용은 비즈니스용 skype Server 2015의 영구 채팅 서버에 [대 한 계획](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), 비즈니스용 [skype Server 2015의 영구 채팅 서버 배포](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)및 비즈니스용 [Skype Server 2015에서 영구 채팅 서버 관리](../../manage/persistent-chat/persistent-chat.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22e6e-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


