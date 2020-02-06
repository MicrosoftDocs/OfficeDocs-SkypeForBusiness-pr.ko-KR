---
title: 영구 채팅방에 대해 추가 기능 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: '요약: 비즈니스용 Skype Server 2015에서 영구 채팅 서버 채팅방의 추가 기능을 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 01e58422f28d0027114f5bc424f01eb9ef3d9e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817294"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="61b01-103">영구 채팅방에 대해 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="61b01-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="61b01-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 채팅방의 추가 기능을 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="61b01-105">추가 기능은 Url을 채팅방과 연결 하 여 채팅방의 환경을 확장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="61b01-106">이러한 Url은 클라이언트 대화 확장 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="61b01-107">일반적인 추가 기능에는 주식 시세 표시기가 채팅방에 게시 되는 경우를 가로채는 Silverlight 응용 프로그램을 가리키는 URL이 포함 될 수 있으며, 확장성 창에 주식 기록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="61b01-108">다른 예로는 "Top of mind" 또는 "Topic of the day"와 같이 몇 가지 공유 컨텍스트를 포함하도록 채팅방에 OneNote 2013 URL을 추가 기능으로 포함하는 것을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="61b01-109">사용자가 클라이언트에서 추가 기능을 볼 수 있으려면 먼저 등록 된 추가 기능 목록에 추가 기능을 추가 하 고 채팅방 관리자 또는 작성자가 채팅방과 추가 기능을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61b01-110">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="61b01-111">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="61b01-112">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="61b01-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="61b01-113">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="61b01-114">제어판을 사용 하 여 채팅방에 대 한 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="61b01-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="61b01-115">제어판을 사용 하 여 채팅방의 추가 기능을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="61b01-116">CsPersistentChatAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포의 임의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="61b01-117">**시작** 메뉴에서 비즈니스용 Skype 서버 제어판을 선택 하거나 브라우저 창을 연 다음 관리 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="61b01-118">왼쪽 탐색 모음에서 **영구 채팅**을 클릭한 다음 **추가 기능**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="61b01-119">여러 영구 채팅 서버 풀 배포의 경우 드롭다운 목록에서 적절 한 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="61b01-120">**추가 기능** 페이지에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="61b01-121">**서비스 선택**에서 추가 기능을 만들어야 하는 영구 채팅 서버 풀에 해당 하는 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="61b01-122">추가 기능은 한 풀에서 다른 풀로 이동하거나 여러 풀 간에 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="61b01-123">**새 추가 기능**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="61b01-124">**이름**에 새 추가 기능 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="61b01-125">**URL**에 추가 기능과 연결할 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="61b01-126">Url은 http 및 https 프로토콜로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="61b01-127">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="61b01-128">Windows PowerShell을 사용 하 여 추가 기능 구성</span><span class="sxs-lookup"><span data-stu-id="61b01-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="61b01-129">다음 Windows PowerShell cmdlet을 사용 하 여 채팅방에 대 한 추가 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="61b01-130">사용 가능한 모든 매개 변수를 포함 하 여 구문에 대 한 자세한 내용은 비즈니스용 [Skype Server 2015 관리 셸을](../management-shell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61b01-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="61b01-131">**은**</span><span class="sxs-lookup"><span data-stu-id="61b01-131">**Cmdlet**</span></span>|<span data-ttu-id="61b01-132">**설명**</span><span class="sxs-lookup"><span data-stu-id="61b01-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61b01-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61b01-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61b01-134">새 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="61b01-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="61b01-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61b01-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61b01-136">기존 추가 기능에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="61b01-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="61b01-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61b01-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61b01-138">추가 기능에 대 한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="61b01-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="61b01-139">제거-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="61b01-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="61b01-140">추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="61b01-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="61b01-141">새 추가 기능 만들기</span><span class="sxs-lookup"><span data-stu-id="61b01-141">Create a new add-in</span></span>

<span data-ttu-id="61b01-142">**새 CsPersistentChatAddin** cmdlet을 사용 하 여 새 추가 기능을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="61b01-143">예를 들어 다음 명령을 사용 하 여 풀 atl-cs-001.contoso.com에 대 한 새 추가 기능 (이름 ITPersistentChatAddin)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="61b01-144">URL 매개 변수 및 매개 변수 값 http://atl-cs-001.contoso.com/itchat 은 추가 기능 웹 페이지의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="61b01-145">기존 추가 기능에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="61b01-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="61b01-146">**Set-CsPersistentChatAddIn** cmdlet을 사용 하 여 기존 추가 기능에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="61b01-147">예를 들어 다음 명령은 영구 채팅 추가 기능 ITPersistentChatAddin에 할당 된 URL을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="61b01-148">이 경우에는 URL이 다음과 같이 변경 됩니다.http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="61b01-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="61b01-149">추가 기능에 대 한 정보 검색</span><span class="sxs-lookup"><span data-stu-id="61b01-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="61b01-150">**CsPersistentChatAddin** cmdlet을 사용 하 여 추가 기능에 대 한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="61b01-151">예를 들어 다음 명령은 조직에서 사용 하도록 구성 된 모든 영구 채팅 추가 기능에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="61b01-152">추가 기능 제거</span><span class="sxs-lookup"><span data-stu-id="61b01-152">Remove an add-in</span></span>

<span data-ttu-id="61b01-153">**제거-CsPersistentChatAddIn** cmdlet을 사용 하 여 추가 기능을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="61b01-154">예를 들어 다음 명령은 풀 atl-cs-001.contoso.com에서 찾을 수 있는 영구 채팅 추가 기능을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b01-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


