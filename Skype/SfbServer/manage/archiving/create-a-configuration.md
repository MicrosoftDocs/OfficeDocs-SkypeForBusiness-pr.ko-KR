---
title: 비즈니스용 Skype 서버에서 보관 구성 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: '요약: 비즈니스용 Skype 서버에 대 한 보관 구성을 만드는 방법에 대해 알아봅니다.'
ms.openlocfilehash: bd2a139e7321542e3b13259ebc2ec1e4ba731caf
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992745"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="57c49-103">비즈니스용 Skype 서버에서 보관 구성 만들기</span><span class="sxs-lookup"><span data-stu-id="57c49-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="57c49-104">**요약:** 비즈니스용 Skype 서버에 대 한 보관 구성을 만드는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="57c49-105">제어판을 사용 하 여 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="57c49-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="57c49-106">특정 사이트 또는 풀에 대 한 보관 옵션을 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="57c49-107">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="57c49-108">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="57c49-109">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="57c49-110">**보관 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="57c49-111">사이트 보관 구성을 만들려면 **사이트 구성을**클릭 한 다음 **사이트 선택**에서 보관을 위해 구성할 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="57c49-112">풀 보관 구성을 만들려면 **풀 구성을**클릭 한 다음 **풀 선택**에서 보관을 위해 구성할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="57c49-113">**새 보관 설정**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="57c49-114">IM (인스턴트 메시징) 세션에 대해서만 보관을 사용 하도록 설정 하려면 **im 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="57c49-115">IM 세션과 웹 컨퍼런스 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 웹 회의 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="57c49-116">이 구성에 대 한 보관을 사용 하지 않도록 설정 하려면 **보관 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="57c49-117">또한 **새 보관 설정**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="57c49-118">보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="57c49-119">Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="57c49-120">데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="57c49-121">특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="57c49-122">내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="57c49-123">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="57c49-124">Windows PowerShell을 사용 하 여 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="57c49-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="57c49-125">**새 CsArchivingConfiguration** cmdlet을 사용 하 여 특정 사이트 또는 풀에 대 한 보관 옵션을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="57c49-126">다음 명령은 Redmond 사이트의 보관 구성 설정에 대 한 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="57c49-127">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="57c49-128">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="57c49-129">다음 예제에서는 기본적으로 메신저 대화 세션만 보관할 수 있는 보관 구성 설정의 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="57c49-130">여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-130">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="57c49-131">예를 들어이 명령은 메신저 대화 서비스를 보관 하기 위해 새로운 설정을 구성 하 고 보관 서비스의 인스턴트 메시지를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c49-131">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="57c49-132">자세한 내용은 [새 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57c49-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
