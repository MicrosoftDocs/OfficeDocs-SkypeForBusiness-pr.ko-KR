---
title: 비즈니스용 Skype 2015 클라이언트 환경 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '요약: 비즈니스용 Skype 사용자에 대 한 클라이언트 환경을 구성 하는 방법을 알아보려면이 항목을 참조 하세요.'
ms.openlocfilehash: bf6245b5b26875c7437990f09dd101ece01b1b47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196948"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="af12b-103">비즈니스용 Skype 2015 클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="af12b-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="af12b-104">**요약:** 비즈니스용 Skype 2015 사용자에 대 한 클라이언트 환경을 구성 하는 방법을 알아보려면이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af12b-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="af12b-105">비즈니스용 skype 2015는 Skype 소비자 제품 환경을 기반으로 하는 새로운 사용자 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="af12b-106">Lync의 모든 기능 외에도 비즈니스용 Skype는 간단한 컨트롤과 친숙 한 아이콘과 함께 새로운 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="af12b-107">새로운 클라이언트 환경에 대 한 자세한 내용은 [비즈니스용 Skype 살펴보기](https://go.microsoft.com/fwlink/?LinkId=529022)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af12b-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="af12b-108">비즈니스용 skype 서버는 Lync 클라이언트 환경을 비롯 하 여 새로운 비즈니스용 Skype 클라이언트 환경을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="af12b-109">관리자는 사용자를 위해 기본 클라이언트 환경을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="af12b-110">예를 들어 조직의 사용자가 새로운 비즈니스용 Skype 환경에서 완벽 하 게 교육을 받을 때까지 Lync 클라이언트 환경을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="af12b-111">또는 모든 사용자를 비즈니스용 Skype 서버에 아직 업그레이드 하지 않은 경우 모든 사용자가 새로운 서버로 업그레이드 될 때까지 동일한 클라이언트 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af12b-112">조직에서 비즈니스용 Skype 서버와 Lync Server를 배포한 경우 서버 버전과 UI 설정에 따라 기본 클라이언트 환경이 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="af12b-113">사용자가 비즈니스용 Skype를 처음 실행할 때 Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="af12b-114">몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="af12b-115">자세한 내용은이 항목의 뒷부분에 나오는 **첫 번째 클라이언트 동작 시작** 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af12b-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af12b-116">Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전 이상에 대 한 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="af12b-117">Lync 2013 클라이언트를 사용 하도록 클라이언트 환경을 구성 하기 전에 클라이언트 버전을 확인 하 여 숫자 16으로 시작 되지 않는지 확인 하세요. 예: x.x.x.</span><span class="sxs-lookup"><span data-stu-id="af12b-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="af12b-118">클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="af12b-118">Configure the client experience</span></span>

<span data-ttu-id="af12b-119">조직의 사용자가 EnableSkypeUI 매개 변수가 있는 **Set CSClientPolicy** cmdlet을 사용 하 여 볼 클라이언트 환경을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="af12b-120">여기서 XdsIdentity는 글로벌 정책 또는 명명 된 사이트 정책을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="af12b-121">다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다 (사이트 또는 사용자 특정 정책이 전역 정책 보다 우선 하는 경우 유의 함).</span><span class="sxs-lookup"><span data-stu-id="af12b-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="af12b-122">다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 Lync 클라이언트 환경을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="af12b-123">다음 명령은 Redmond 사이트 내의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="af12b-124">조직 내 특정 사용자에 대 한 클라이언트 환경을 구성 하려는 경우 **새 csclientpolicy** cmdlet을 사용 하 여 새 사용자 정책을 만든 다음 **부여-csclientpolicy** 를 사용 하 여 특정 사용자에 게 정책을 할당할 수 있습니다. 은.</span><span class="sxs-lookup"><span data-stu-id="af12b-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="af12b-125">예를 들어 다음 명령은 비즈니스용 Skype 클라이언트 환경을 선택 하는 새 클라이언트 정책, SalesClientUI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="af12b-126">다음 명령은 Sales 부서의 모든 구성원에 게 정책, SalesClientUI를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="af12b-127">첫 번째 클라이언트 동작 시작</span><span class="sxs-lookup"><span data-stu-id="af12b-127">First launch client behaviors</span></span>

<span data-ttu-id="af12b-128">기본적으로 사용자가 처음으로 비즈니스용 Skype 2015을 실행 하는 경우 EnableSkypeUI 매개 변수 값을 설정 하 여 Lync 클라이언트 환경을 선택한 경우에도 설명 된 대로 $False에는 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다. 앞서.</span><span class="sxs-lookup"><span data-stu-id="af12b-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="af12b-129">몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="af12b-130">사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스를 표시 하려는 경우 클라이언트를 업데이트 한 후 처음 시작 하기 전에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="af12b-131">앞에서 설명한 대로 사용 `EnableSkypeUI` 하 고 있는 정책의 값이 $False으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="af12b-132">사용자의 컴퓨터에서 시스템 레지스트리를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="af12b-133">사용자가 비즈니스용 Skype 클라이언트를 처음 시작 하기 전에이 작업을 수행 하 고이 작업을 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="af12b-134">도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리를 업데이트 하는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 있는 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af12b-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="af12b-135">**[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 키에서 새 **이진** 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="af12b-136">**값 이름은** **EnableSkypeUI**이어야 하며 **값 데이터** 를 **00 00 00 00**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="af12b-137">키의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="af12b-138">이제 사용자가 비즈니스용 Skype 클라이언트를 처음 실행할 때 Lync 사용자 인터페이스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="af12b-139">시작 화면 자습서의 표시 제어</span><span class="sxs-lookup"><span data-stu-id="af12b-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="af12b-140">사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 *가장 사용자가 질문 하는 7 가지 간단한 팁*을 포함 하는 시작 화면을 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="af12b-141">시작 화면 표시를 해제할 수 있지만, 클라이언트 컴퓨터에서 다음 레지스트리 값을 추가 하 여 사용자가 자습서에 액세스 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="af12b-142">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="af12b-143">**값 이름은** **IsBasicTutorialSeenByUser**이어야 하며 **값 데이터** 는 **1**로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="af12b-144">키의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="af12b-145">클라이언트 자습서 끄기</span><span class="sxs-lookup"><span data-stu-id="af12b-145">Turn off the client tutorial</span></span>

<span data-ttu-id="af12b-146">사용자가 자습서에 액세스할 수 없게 하려면 다음 레지스트리 값을 사용 하 여 클라이언트 자습서를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="af12b-147">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 키에서 새 **dword(32 (32 비트) 값**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="af12b-148">**값 이름은** **TutorialFeatureEnabled**이어야 하며 **값 데이터** 는 **0**으로 설정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="af12b-149">Lync</span><span class="sxs-lookup"><span data-stu-id="af12b-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="af12b-150">**값 데이터** 를 **1**로 설정 하 여 자습서를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="af12b-151">기본 클라이언트 동작</span><span class="sxs-lookup"><span data-stu-id="af12b-151">Default client behaviors</span></span>

<span data-ttu-id="af12b-152">조직에 비즈니스용 Skype 서버와 Lync Server가 배포 되어 있는 경우 클라이언트 환경은 서버 버전과 Skype UI 설정에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="af12b-153">다음 표에는 서버 버전과 UI 설정을 기반으로 하는 초기 클라이언트 환경이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="af12b-154">**서버 버전**</span><span class="sxs-lookup"><span data-stu-id="af12b-154">**Server version**</span></span>|<span data-ttu-id="af12b-155">**EnableSkypeUI 설정**</span><span class="sxs-lookup"><span data-stu-id="af12b-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="af12b-156">**클라이언트 환경**</span><span class="sxs-lookup"><span data-stu-id="af12b-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af12b-157">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="af12b-157">Skype for Business Server</span></span> |<span data-ttu-id="af12b-158">기본값</span><span class="sxs-lookup"><span data-stu-id="af12b-158">Default</span></span>  <br/> |<span data-ttu-id="af12b-159">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="af12b-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="af12b-160">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="af12b-160">Skype for Business Server</span></span>  |<span data-ttu-id="af12b-161">False</span><span class="sxs-lookup"><span data-stu-id="af12b-161">True</span></span>  <br/> |<span data-ttu-id="af12b-162">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="af12b-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="af12b-163">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="af12b-163">Skype for Business Server</span></span>  |<span data-ttu-id="af12b-164">해제</span><span class="sxs-lookup"><span data-stu-id="af12b-164">False</span></span>  <br/> |<span data-ttu-id="af12b-165">사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경 하면 나중에 비즈니스용 Skype로 전환할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="af12b-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="af12b-166">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="af12b-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="af12b-167">기본값</span><span class="sxs-lookup"><span data-stu-id="af12b-167">Default</span></span>  <br/> |<span data-ttu-id="af12b-168">사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경 하면 나중에 비즈니스용 Skype로 전환할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="af12b-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="af12b-169">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="af12b-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="af12b-170">False</span><span class="sxs-lookup"><span data-stu-id="af12b-170">True</span></span>  <br/> |<span data-ttu-id="af12b-171">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="af12b-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="af12b-172">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="af12b-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="af12b-173">해제</span><span class="sxs-lookup"><span data-stu-id="af12b-173">False</span></span>  <br/> |<span data-ttu-id="af12b-174">사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경 하면 나중에 비즈니스용 Skype로 전환할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="af12b-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="af12b-175">Lync Server 2010 또는 Lync Server 2013 (패치 없이)</span><span class="sxs-lookup"><span data-stu-id="af12b-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="af12b-176">기본값</span><span class="sxs-lookup"><span data-stu-id="af12b-176">Default</span></span>  <br/> |<span data-ttu-id="af12b-177">사용자가 Lync 모드로 전환 요청 (사용자가 나중에 비즈니스용 Skype로 전환할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="af12b-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="af12b-178">다음 표에는 관리자가 Skype UI 환경에 대 한 초기 설정을 변경할 때 클라이언트 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="af12b-179">**서버 버전**</span><span class="sxs-lookup"><span data-stu-id="af12b-179">**Server version**</span></span>|<span data-ttu-id="af12b-180">**EnableSkypeUI 설정**</span><span class="sxs-lookup"><span data-stu-id="af12b-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="af12b-181">**클라이언트 UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="af12b-181">**Client UI = Lync**</span></span>|<span data-ttu-id="af12b-182">**클라이언트 UI = 비즈니스용 Skype**</span><span class="sxs-lookup"><span data-stu-id="af12b-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="af12b-183">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="af12b-183">Skype for Business Server</span></span> |<span data-ttu-id="af12b-184">False</span><span class="sxs-lookup"><span data-stu-id="af12b-184">True</span></span>  <br/> |<span data-ttu-id="af12b-185">사용자가 비즈니스용 Skype로 전환 하도록 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="af12b-186">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="af12b-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="af12b-187">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="af12b-187">Skype for Business Server</span></span> |<span data-ttu-id="af12b-188">해제</span><span class="sxs-lookup"><span data-stu-id="af12b-188">False</span></span>  <br/> |<span data-ttu-id="af12b-189">Lync 모드</span><span class="sxs-lookup"><span data-stu-id="af12b-189">Lync mode</span></span>  <br/> |<span data-ttu-id="af12b-190">사용자가 Lync 모드로 전환 요청</span><span class="sxs-lookup"><span data-stu-id="af12b-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="af12b-191">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="af12b-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="af12b-192">False</span><span class="sxs-lookup"><span data-stu-id="af12b-192">True</span></span>  <br/> |<span data-ttu-id="af12b-193">사용자가 비즈니스용 Skype로 전환 하도록 요청 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="af12b-194">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="af12b-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="af12b-195">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="af12b-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="af12b-196">해제</span><span class="sxs-lookup"><span data-stu-id="af12b-196">False</span></span>  <br/> |<span data-ttu-id="af12b-197">Lync 모드</span><span class="sxs-lookup"><span data-stu-id="af12b-197">Lync mode</span></span>  <br/> |<span data-ttu-id="af12b-198">사용자가 Lync 모드로 전환 요청</span><span class="sxs-lookup"><span data-stu-id="af12b-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="af12b-199">Lync Server 2010 또는 Lync Server 2013 (패치 없이)</span><span class="sxs-lookup"><span data-stu-id="af12b-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="af12b-200">기본값</span><span class="sxs-lookup"><span data-stu-id="af12b-200">Default</span></span>  <br/> |<span data-ttu-id="af12b-201">Lync 모드 (비즈니스용 Skype로 전환할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="af12b-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="af12b-202">Lync 모드 (비즈니스용 Skype로 전환할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="af12b-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="af12b-203">비즈니스용 Skype 클라이언트의 구성을 관리 하는 데 필요한 패치 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="af12b-204">Lync Server 2010-Lync Server 2010에 대 한 4.0.7577.710 (2015 년 2 월 누적 업데이트).</span><span class="sxs-lookup"><span data-stu-id="af12b-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="af12b-205">자세한 내용은 [Lync Server 2010 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532771) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af12b-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="af12b-206">Lync Server 2013-Lync Server 2013 용 5.0.8308.857 (2014 누적 업데이트)</span><span class="sxs-lookup"><span data-stu-id="af12b-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="af12b-207">자세한 내용은 [Lync Server 2013에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?LinkId=532772)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af12b-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="af12b-208">도메인에 가입 된 컴퓨터에서 그룹 정책 개체를 만들어 레지스트리 수정</span><span class="sxs-lookup"><span data-stu-id="af12b-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="af12b-209">사용자가 처음으로 비즈니스용 Skype 2015 클라이언트를 시작할 때 Lync 클라이언트 환경을 표시 하는 레지스트리 업데이트는 한 번만 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="af12b-210">GPO (그룹 정책 개체)를 사용 하 여 레지스트리를 업데이트 하는 경우 값 데이터를 업데이트 하는 대신 새 값을 만들기 위해 개체를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="af12b-211">GPO가 적용 되 면 새 값이 없는 경우 GPO가 생성 하 고 값 데이터를 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="af12b-212">다음 절차에서는 사용자가 비즈니스용 Skype 2015 클라이언트를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 레지스트리를 수정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="af12b-213">또한 앞에서 설명한 대로이 절차를 사용 하 여 레지스트리를 업데이트 하 여 시작 화면 자습서를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="af12b-214">GPO를 만들려면</span><span class="sxs-lookup"><span data-stu-id="af12b-214">To create the GPO</span></span>

1. <span data-ttu-id="af12b-215">**그룹 정책 관리 콘솔**을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="af12b-216">그룹 정책 관리 콘솔을 사용 하는 방법에 대 한 자세한 내용은 [그룹 정책 관리 콘솔](https://go.microsoft.com/fwlink/?LinkId=532759)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af12b-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="af12b-217">**그룹 정책 개체** 노드를 마우스 오른쪽 단추로 클릭 하 고 메뉴에서 **새로 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="af12b-218">**새 gpo** 대화 상자에서 GPO 이름 (예: MakeLyncDefaultUI)을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="af12b-219">방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="af12b-220">**그룹 정책 관리 편집기**에서 **사용자 구성**, **기본 설정**, **Windows 설정을**차례로 확장 한 다음 **레지스트리** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="af12b-221">**레지스트리** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새** > **레지스트리 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="af12b-222">**새 레지스트리 속성** 대화 상자에서 다음을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="af12b-223">**칸**</span><span class="sxs-lookup"><span data-stu-id="af12b-223">**Field**</span></span>|<span data-ttu-id="af12b-224">**선택 하거나 입력할 값**</span><span class="sxs-lookup"><span data-stu-id="af12b-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="af12b-225">**함수**</span><span class="sxs-lookup"><span data-stu-id="af12b-225">**Action**</span></span> <br/> |<span data-ttu-id="af12b-226">**만드는**</span><span class="sxs-lookup"><span data-stu-id="af12b-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="af12b-227">**벌**</span><span class="sxs-lookup"><span data-stu-id="af12b-227">**Hive**</span></span> <br/> | <span data-ttu-id="af12b-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="af12b-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="af12b-229">**키 경로**</span><span class="sxs-lookup"><span data-stu-id="af12b-229">**Key Path**</span></span> <br/> |<span data-ttu-id="af12b-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="af12b-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="af12b-231">**값 이름**</span><span class="sxs-lookup"><span data-stu-id="af12b-231">**Value name**</span></span> <br/> |<span data-ttu-id="af12b-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="af12b-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="af12b-233">**값 형식**</span><span class="sxs-lookup"><span data-stu-id="af12b-233">**Value type**</span></span> <br/> |<span data-ttu-id="af12b-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="af12b-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="af12b-235">**값 데이터**</span><span class="sxs-lookup"><span data-stu-id="af12b-235">**Value data**</span></span> <br/> |<span data-ttu-id="af12b-236">00000000</span><span class="sxs-lookup"><span data-stu-id="af12b-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="af12b-237">**확인** 을 클릭 하 여 변경 내용을 저장 한 다음 GPO를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="af12b-238">다음에는 OU와 같이 정책을 할당 하려는 사용자의 그룹에 만든 GPO를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="af12b-239">GPO를 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="af12b-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="af12b-240">그룹 정책 관리 콘솔에서 정책을 할당 하려는 OU를 마우스 오른쪽 단추로 클릭 한 다음 **기존 GPO에 연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="af12b-241">**Gpo 선택** 대화 상자에서 사용자가 만든 gpo를 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="af12b-242">대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="af12b-243">명령 프롬프트에서 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="af12b-244">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="af12b-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="af12b-245">아래에 표시 한 GPO의 이름과 함께 "할당 된 그룹 정책 개체"가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="af12b-246">또한, 레지스트리를 검사 하 여 GPO가 사용자 컴퓨터의 레지스트리를 성공적으로 업데이트 했는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="af12b-247">레지스트리 편집기를 열고 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 키로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="af12b-248">GPO가 성공적으로 레지스트리를 업데이트 하면 값이 0 인 EnableSkypeUI 이라는 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af12b-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

