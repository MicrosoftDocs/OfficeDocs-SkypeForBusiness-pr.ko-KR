---
title: 비즈니스용 Skype 서버에서 보관 구성 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: '요약: 비즈니스용 Skype 서버에 대한 보관 구성을 만드는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817658"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="185f9-103">비즈니스용 Skype 서버에서 보관 구성 만들기</span><span class="sxs-lookup"><span data-stu-id="185f9-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="185f9-104">**요약:** 비즈니스용 Skype 서버의 보관 구성을 만드는 방법을 자세히 알아보는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="185f9-105">제어판을 사용하여 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="185f9-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="185f9-106">특정 사이트 또는 풀에 대한 보관 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="185f9-107">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="185f9-108">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="185f9-109">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="185f9-110">**보관 구성** 페이지에서 **새로 만들기** 를 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="185f9-111">사이트 보관 구성을 만들려면 사이트 구성을 클릭한 다음 사이트 선택에서 보관에 대해 구성할 사이트를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="185f9-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="185f9-112">풀 보관 구성을 만들려면 풀 구성을 클릭한 다음 풀 선택에서 보관에 대해 구성할 풀을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="185f9-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="185f9-113">**새 보관 설정 만들기** 의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="185f9-114">메신저 대화 세션에 대해서만 보관을 사용하도록 설정하려면 **메신저 대화 세션 보관** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="185f9-115">메신저 대화 세션 및 웹 회의 모두에 대해 보관을 사용하도록 설정하려면 **메신저 대화 및 웹 회의 세션 보관** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="185f9-116">이 구성에 대해 보관을 사용하지 않도록 설정하려면 보관 사용 **안 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="185f9-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="185f9-117">또한 **새 보관 설정** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="185f9-118">보관을 사용할 수 없을 경우 작업을 차단하려면 **보관에 실패할 경우 메신저 대화 또는 웹 회의 세션 차단** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="185f9-119">보관 Microsoft Exchange Server 데이터를 저장하려면 Microsoft Exchange 통합 **확인란을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="185f9-120">데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="185f9-121">특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제** 를 클릭한 다음 일 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="185f9-122">내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제** 를 클릭합니다,</span><span class="sxs-lookup"><span data-stu-id="185f9-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="185f9-123">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="185f9-124">보관 옵션을 구성하는 방법을 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="185f9-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="185f9-125">**New-CsArchivingConfiguration** cmdlet을 사용하여 특정 사이트 또는 풀에 대한 보관 옵션을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="185f9-126">다음 명령을 실행하면 레드몬드 사이트에 대해 새 보관 구성 설정 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="185f9-127">이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="185f9-128">다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="185f9-129">다음 예에서는 기본적으로 인스턴트 메시징 세션만 보관할 수 있는 보관 구성 설정 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="185f9-p102">여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 메신저 대화 세션을 보관하고 보관 서비스를 사용할 수 없는 메신저 대화는 차단하는 새로운 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185f9-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="185f9-132">자세한 내용은 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="185f9-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
