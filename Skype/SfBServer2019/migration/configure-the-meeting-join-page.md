---
title: 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 사용자 컴퓨터에 이미 설치 되어 있는 클라이언트를 검색 합니다. 클라이언트가 이미 설치되어 있으면 클라이언트가 열리고 모임에 참가합니다. 클라이언트가 설치 되어 있지 않으면 기본적으로 웹 앱이 열립니다.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754028"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="0ce72-105">모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="0ce72-105">Configure the meeting join page</span></span>

<span data-ttu-id="0ce72-106">사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 사용자 컴퓨터에 이미 설치 되어 있는 클라이언트를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="0ce72-107">클라이언트가 이미 설치되어 있으면 클라이언트가 열리고 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="0ce72-108">클라이언트가 설치 되어 있지 않으면 기본적으로 웹 앱이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="0ce72-109">사용자가 모임에 참가할 수 있도록 하려면 모임 참가 페이지의 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="0ce72-110">이러한 구성 옵션은 제어판에서 제거 되었지만 Set-cswebserviceconfiguration cmdlet을 사용 하 여 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="0ce72-111">**모임 참가 페이지 CsWebServiceConfiguration 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="0ce72-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="0ce72-112">**CsWebServiceConfiguration 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="0ce72-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="0ce72-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="0ce72-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0ce72-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="0ce72-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="0ce72-115">True로 설정 하면 Lync 이외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 모임에 참가할 수 있는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="0ce72-116">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="0ce72-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="0ce72-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="0ce72-118">True로 설정 하면 온라인 회의에 참가 하는 데 사용할 수 있는 대체 옵션이 자동으로 확장 되어 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="0ce72-119">False (기본값)로 설정 된 경우에는 이러한 옵션을 사용할 수 있지만 사용자가 직접 옵션 목록을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="0ce72-120">비즈니스용 Skype 서버 2019 관리 셸을 사용 하 여 모임 참가 페이지를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="0ce72-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="0ce72-121">비즈니스용 Skype 서버 2019 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**를 차례로 클릭 한 다음 **비즈니스용 skype 서버 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0ce72-122">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="0ce72-123">이 cmdlet는 웹 서비스 구성 설정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="0ce72-124">기본 설정 (이 cmdlet의 매개 변수에 대 한 자세한 내용은 [비즈니스용 Skype 서버 관리 셸](../../SfbServer/manage/management-shell.md) 설명서 참조)에 따라 매개 변수를 True 또는 False로 설정한 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ce72-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


