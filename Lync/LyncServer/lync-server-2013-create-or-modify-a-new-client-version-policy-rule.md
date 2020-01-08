---
title: 'Lync Server 2013: 새 클라이언트 버전 정책 규칙 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="041ac-102">Lync Server 2013에서 새 클라이언트 버전 정책 규칙 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="041ac-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="041ac-103">_**마지막으로 수정한 주제:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="041ac-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="041ac-104">클라이언트 버전 정책 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온 하려고 할 때 수행 해야 하는 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="041ac-105">Lync Server 2013 제어판에서 클라이언트 버전 정책에 대 한 개별 규칙을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="041ac-106">규칙은 우선 순위 순서 대로 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="041ac-107">예를 들어 버전 1.5를 실행 하는 클라이언트가 연결할 수 있도록 허용 하 고 2.0 이전 버전을 실행 하는 클라이언트를 차단 하는 규칙을 적용 한 경우 첫 번째 규칙이 우선권을 가지 며 버전 1.5를 실행 하는 클라이언트는 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="041ac-108">Lync Server 제어판을 사용 하 여 클라이언트 버전 정책 규칙을 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="041ac-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="041ac-109">Lync server 제어판을 사용 하 여 [Lync server 2013에서 새 클라이언트 버전 정책을 만들거나 수정](lync-server-2013-create-or-modify-a-new-client-version-policy.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="041ac-110">**클라이언트 버전 정책 편집** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="041ac-111">**새로** 만들기를 클릭 하 여 새 클라이언트 버전 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="041ac-112">목록에서 정의 된 클라이언트 유형 중 하나를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="041ac-113">와일드 카드를 사용 하 여 클라이언트 형식을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="041ac-114">**사용자 에이전트**에서 클라이언트 종류를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="041ac-115">**버전 번호**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="041ac-116">**주 버전**에서 클라이언트의 주요 릴리스에 해당 하는 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="041ac-117">**부 버전**에서 클라이언트의 부 릴리스에 해당 하는 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="041ac-118">**빌드**에 클라이언트의 주 및 부 릴리스에 해당 하는 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="041ac-119">**업데이트**에서 클라이언트의 업데이트 된 릴리스에 해당 하는 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="041ac-120">와일드 카드를 사용 하 여 클라이언트 버전 번호를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="041ac-121">앞의 단계에서 지정한 클라이언트 버전에 대해 일치 하는 작업을 지정 하려면 **비교 작업**에서 다음 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="041ac-122">**같음**</span><span class="sxs-lookup"><span data-stu-id="041ac-122">**Same as**</span></span>
    
      - <span data-ttu-id="041ac-123">**일치하지 않음**</span><span class="sxs-lookup"><span data-stu-id="041ac-123">**Is not**</span></span>
    
      - <span data-ttu-id="041ac-124">**보다 최근임**</span><span class="sxs-lookup"><span data-stu-id="041ac-124">**Newer than**</span></span>
    
      - <span data-ttu-id="041ac-125">**보다 최근이거나 같음**</span><span class="sxs-lookup"><span data-stu-id="041ac-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="041ac-126">**보다 오래됨**</span><span class="sxs-lookup"><span data-stu-id="041ac-126">**Older than**</span></span>
    
      - <span data-ttu-id="041ac-127">**보다 오래되거나 같음**</span><span class="sxs-lookup"><span data-stu-id="041ac-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="041ac-128">앞 단계의 조건이 충족 될 때 수행할 작업을 지정 하려면 다음 중 한 가지 **작업**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="041ac-129">클라이언트가 로그온 할 수 있도록 허용 하려면 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="041ac-130">클라이언트가 Windows Server Update 서비스 또는 Microsoft 업데이트에서 로그온 하 고 업데이트를 받을 수 있도록 허용 하려면 **허용 및 업그레이드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="041ac-131">이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="041ac-132">이 작업을 선택 하면 다음에 사용자가 Lync 2013에 로그인 할 때 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="041ac-133">알림에는 Windows Server Update Service 또는 Microsoft Update에 업데이트가 아직 게시되지 않았더라도 사용할 수 있는 업데이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="041ac-134">혼란을 방지하기 위해서는 업데이트를 사용할 수 있는 경우에만 이 작업을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="041ac-135">클라이언트가 로그온 할 수 있도록 하 고 다른 클라이언트 버전을 다운로드할 위치에 대 한 메시지를 표시 하려면 **URL로 허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="041ac-136">이 절차의 뒷부분에서 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="041ac-137">클라이언트가 로그온 할 수 없도록 하려면 **Block**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="041ac-138">클라이언트가 Windows Server Update 서비스 또는 Microsoft 업데이트에서 업데이트를 받도록 허용 하 고 클라이언트가 로그온 하지 못하도록 하려면 **차단 및 업그레이드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="041ac-139">이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="041ac-140">클라이언트가 로그온 할 수 없도록 하 고 다른 클라이언트 버전을 다운로드할 위치에 대 한 메시지를 표시 하려면 **URL로 차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="041ac-141">이 절차의 뒷부분에서 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="041ac-142">) 이전 단계에서 url 및 **블록** 을 포함 하 여 **허용** 을 클릭 한 경우 **url**에 메시지에 포함할 클라이언트 다운로드 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="041ac-143">**확인**을 클릭 한 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="041ac-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

