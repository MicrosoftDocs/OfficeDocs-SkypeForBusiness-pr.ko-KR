---
title: 비즈니스용 Skype 서버 2015에서 영구 채팅방에 대한 추가 기능 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 대화방에 대한 추가 기능을 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815084"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="c11c1-103">비즈니스용 Skype 서버 2015에서 영구 채팅방에 대한 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="c11c1-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c11c1-104">**요약:** 영구 채팅 서버 채팅방에 대해 추가 기능을 구성하는 방법을 비즈니스용 Skype 서버 2015에서 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c11c1-105">추가 기능에서는 URL을 대화방과 연결하여 방 내 환경을 확장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="c11c1-106">이러한 URL은 클라이언트 대화 extensibility 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="c11c1-107">일반적인 추가 기능으로는 주식 시세 표시가 대화방에 게시될 때 가로채고 주식 기록을 Extensibility 창에 표시하는 Silverlight 응용 프로그램을 지정하는 URL이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="c11c1-108">또 다른 예로는 OneNote 2013 URL을 채팅방에 추가 기능으로 포함하여 "관심 항목" 또는 "오늘의 항목"과 같은 일부 공유 컨텍스트를 포함하는 경우를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="c11c1-109">사용자가 클라이언트에서 추가 기능을 볼 수 있도록 등록된 추가 기능 목록에 추가 기능을 추가해야 합니다. 대화방 관리자 또는 작성자는 채팅방을 추가 기능과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c11c1-110">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c11c1-111">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="c11c1-112">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="c11c1-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c11c1-113">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="c11c1-114">제어판을 사용하여 채팅방에 대한 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="c11c1-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="c11c1-115">제어판을 사용하여 채팅방에 대한 추가 기능을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="c11c1-116">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c11c1-117">시작 **메뉴에서** 비즈니스용 Skype 서버 제어판을 선택하거나 브라우저 창을 연 다음 관리 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="c11c1-118">왼쪽 탐색 모음에서 **영구 채팅** 을 클릭하고 **추가 기능** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="c11c1-119">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절한 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="c11c1-120">**추가 기능** 페이지에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="c11c1-121">서비스 **선택에서** 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당하는 서비스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="c11c1-122">추가 기능은 풀 간에 이동하거나 서로 다른 풀 간에 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="c11c1-123">**새 추가 기능** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="c11c1-124">**이름** 에서 새 추가 기능의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="c11c1-125">**URL** 에서 추가 기능과 연결할 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="c11c1-126">URL은 http 및 https 프로토콜로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="c11c1-127">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="c11c1-128">다음을 사용하여 추가 기능 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c11c1-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="c11c1-129">다음 cmdlet을 사용하여 채팅방에 대한 추가 기능을 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="c11c1-130">사용 가능한 모든 매개 변수를 포함하여 구문에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015 관리 셸을 참조하세요.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="c11c1-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="c11c1-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="c11c1-131">**Cmdlet**</span></span>|<span data-ttu-id="c11c1-132">**설명**</span><span class="sxs-lookup"><span data-stu-id="c11c1-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c11c1-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c11c1-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c11c1-134">새 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="c11c1-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="c11c1-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c11c1-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c11c1-136">기존 추가 기능의 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c11c1-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="c11c1-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c11c1-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c11c1-138">추가 기능 관련 정보 검색</span><span class="sxs-lookup"><span data-stu-id="c11c1-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="c11c1-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c11c1-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c11c1-140">추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="c11c1-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="c11c1-141">새 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="c11c1-141">Create a new add-in</span></span>

<span data-ttu-id="c11c1-142">**New-CsPersistentChatAddin cmdlet을** 사용하여 새 추가 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="c11c1-143">예를 들어 다음 명령은 풀 이름 ITPersistentChatAddin을 사용하여 새 추가 기능을 atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c11c1-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="c11c1-144">URL 매개 변수와 매개 변수 값은 추가 기능 웹 페이지 위치를 http://atl-cs-001.contoso.com/itchat 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="c11c1-145">기존 추가 기능의 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c11c1-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="c11c1-146">**Set-CsPersistentChatAddIn** cmdlet을 사용하여 기존 추가 기능의 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="c11c1-147">예를 들어 다음 명령은 영구 채팅 추가 기능 ITPersistentChatAddin에 할당된 URL을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="c11c1-148">이 경우 URL이 다음으로 변경됩니다. http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="c11c1-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="c11c1-149">추가 기능 관련 정보 검색</span><span class="sxs-lookup"><span data-stu-id="c11c1-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="c11c1-150">**Get-CsPersistentChatAddin cmdlet을** 사용하여 추가 기능 관련 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="c11c1-151">예를 들어 다음 명령은 조직에서 사용하도록 구성된 모든 영구 채팅 추가 기능의 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="c11c1-152">추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="c11c1-152">Remove an add-in</span></span>

<span data-ttu-id="c11c1-153">**Remove-CsPersistentChatAddIn** cmdlet을 사용하여 추가 기능을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c11c1-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="c11c1-154">예를 들어 다음 명령은 풀에서 찾은 영구 채팅 추가 기능 ITChatAddin을 atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c11c1-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


