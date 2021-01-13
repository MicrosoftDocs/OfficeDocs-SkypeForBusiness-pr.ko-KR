---
title: 비즈니스용 Skype 2015를 통해 클라이언트 환경 구성
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
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: '요약: 이 항목을 읽고 비즈니스용 Skype 사용자에 대한 클라이언트 환경을 구성하는 방법을 배워 읽습니다.'
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805958"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="bc314-103">비즈니스용 Skype 2015를 통해 클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="bc314-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="bc314-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 2015 사용자에 대한 클라이언트 환경을 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="bc314-105">비즈니스용 Skype 2015는 Skype 소비자 제품 환경을 기반으로 하는 새로운 사용자 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="bc314-106">비즈니스용 Skype는 Lync의 모든 기능 외에도 간소화된 컨트롤 및 친숙한 아이콘이 있는 새로운 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="bc314-107">새 클라이언트 경험에 대한 자세한 내용은 비즈니스용 [Skype 탐색을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=529022)</span><span class="sxs-lookup"><span data-stu-id="bc314-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="bc314-108">비즈니스용 Skype 서버는 새로운 비즈니스용 Skype 클라이언트 환경과 Lync 클라이언트 환경을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="bc314-109">관리자는 사용자의 기본 클라이언트 환경을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="bc314-110">예를 들어 조직의 사용자가 새 비즈니스용 Skype 환경을 완전히 교육할 때까지 Lync 클라이언트 환경을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="bc314-111">또는 일부 사용자를 비즈니스용 Skype 서버로 아직 업그레이드하지 않은 경우 모든 사용자가 새 서버로 업그레이드될 때까지 모든 사용자가 동일한 클라이언트 환경을 사용할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bc314-112">조직에 비즈니스용 Skype 서버와 Lync Server가 모두 배포된 경우 기본 클라이언트 환경은 서버 버전 및 UI 설정에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="bc314-113">사용자가 처음으로 비즈니스용 Skype를 시작하면 Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="bc314-114">몇 분이 지난 후 사용자에게 Lync 모드로 전환할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="bc314-115">자세한 내용은 이 항목의 **부분에 있는** 첫 번째 시작 클라이언트 동작을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc314-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc314-116">Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전 이상에 대한 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="bc314-117">Lync 2013 클라이언트를 사용하도록 클라이언트 환경을 구성하기 전에 클라이언트 버전을 확인하여 번호 16으로 시작하지 않는지 확인하시기 바랍니다. 예: 16.x.x.x</span><span class="sxs-lookup"><span data-stu-id="bc314-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="bc314-118">클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="bc314-118">Configure the client experience</span></span>

<span data-ttu-id="bc314-119">EnableSkypeUI 매개 변수와 함께 **Set-CSClientPolicy** cmdlet을 사용하여 조직의 사용자가 볼 수 있는 클라이언트 환경을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="bc314-120">여기서 XdsIdentity는 글로벌 정책 또는 명명된 사이트 정책을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="bc314-121">다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택합니다(사이트 또는 사용자별 정책은 글로벌 정책보다 됨).</span><span class="sxs-lookup"><span data-stu-id="bc314-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="bc314-122">다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 Lync 클라이언트 환경을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="bc314-123">다음 명령은 Redmond 사이트 내의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="bc314-124">조직 내의 특정 사용자에 대해 클라이언트 환경을 구성하려는 경우 **New-CsClientPolicy** cmdlet을 사용하여 새 사용자 정책을 만든 다음 **Grant-CsClientPolicy** cmdlet을 사용하여 특정 사용자에게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="bc314-125">예를 들어 다음 명령은 비즈니스용 Skype 클라이언트 환경을 선택하는 새 클라이언트 정책 SalesClientUI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="bc314-126">다음 명령은 Sales 부서의 모든 구성원에게 정책 SalesClientUI를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="bc314-127">첫 번째 시작 클라이언트 동작</span><span class="sxs-lookup"><span data-stu-id="bc314-127">First launch client behaviors</span></span>

<span data-ttu-id="bc314-128">기본적으로 사용자가 비즈니스용 Skype 2015를 처음 시작하면 이전에 설명한 바와 같이 EnableSkypeUI 매개 변수의 값을 $False Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="bc314-129">몇 분 후 사용자에게 Lync 모드로 전환할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="bc314-130">사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 사용자 인터페이스를 표시하려는 경우 클라이언트가 업데이트된 후 처음으로 시작되기 전에 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="bc314-131">값이 앞서 설명한 $False 정책에서 해당 값으로  `EnableSkypeUI` 설정되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="bc314-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="bc314-132">사용자 컴퓨터에서 시스템 레지스트리를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-132">Update the system registry on the user's computer.</span></span> <span data-ttu-id="bc314-133">사용자가 비즈니스용 Skype 클라이언트를 처음 시작하기 전에 이 작업을 한 번만 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-133">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="bc314-134">그룹 정책 개체를 만들어 도메인에 가입된 컴퓨터에서 레지스트리를 업데이트하는 방법에 대한 자세한 내용은 항목의 부분에 있는 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bc314-134">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="bc314-135">**[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** 키에서 새 **Binary 값을** 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="bc314-136">값 **이름은** **EnableSkypeUI와** **값** 데이터를 **00 00 00 00으로 설정해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc314-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="bc314-137">키는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-137">The key should look like the following:</span></span>
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

<span data-ttu-id="bc314-138">사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작하면 Lync 사용자 인터페이스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="bc314-139">시작 화면 자습서의 표시 제어</span><span class="sxs-lookup"><span data-stu-id="bc314-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="bc314-140">사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 대부분의 사용자가  *요청하는 7개* 빠른 팁이 포함된 시작 화면을 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="bc314-141">시작 화면의 표시를 해제할 수 있지만 클라이언트 컴퓨터에서 다음 레지스트리 값을 추가하여 사용자가 자습서에 액세스할 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="bc314-142">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 키에 새 **DWORD(32비트) 값을 생성합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc314-142">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="bc314-143">값 **이름은** **IsBasicTutorialSeenByUser** 및 **값** 데이터를 **1로** 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-143">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="bc314-144">키는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="bc314-145">클라이언트 자습서 끄기</span><span class="sxs-lookup"><span data-stu-id="bc314-145">Turn off the client tutorial</span></span>

<span data-ttu-id="bc314-146">사용자가 자습서에 액세스하지 못하게 하려는 경우 다음 레지스트리 값으로 클라이언트 자습서를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="bc314-147">**[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** 키에 새 **DWORD(32비트) 값을 생성합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc314-147">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="bc314-148">값 **이름은** **TutorialFeatureEnabled가** 되어야  합니다. 값 데이터는 **0으로** 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-148">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="bc314-149">Lync</span><span class="sxs-lookup"><span data-stu-id="bc314-149">Lync</span></span>
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="bc314-150">값 데이터를 **1로** 설정하여 자습서를 **다시 설정할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="bc314-151">기본 클라이언트 동작</span><span class="sxs-lookup"><span data-stu-id="bc314-151">Default client behaviors</span></span>

<span data-ttu-id="bc314-152">조직에 비즈니스용 Skype 서버와 Lync Server가 모두 배포된 경우 클라이언트 환경은 서버 버전 및 Skype UI 설정에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="bc314-153">다음 표에는 서버 버전 및 UI 설정에 따라 초기 클라이언트 환경이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="bc314-154">**서버 버전**</span><span class="sxs-lookup"><span data-stu-id="bc314-154">**Server version**</span></span>|<span data-ttu-id="bc314-155">**EnableSkypeUI 설정**</span><span class="sxs-lookup"><span data-stu-id="bc314-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="bc314-156">**클라이언트 환경**</span><span class="sxs-lookup"><span data-stu-id="bc314-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bc314-157">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="bc314-157">Skype for Business Server</span></span> |<span data-ttu-id="bc314-158">기본</span><span class="sxs-lookup"><span data-stu-id="bc314-158">Default</span></span>  <br/> |<span data-ttu-id="bc314-159">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bc314-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="bc314-160">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="bc314-160">Skype for Business Server</span></span>  |<span data-ttu-id="bc314-161">True</span><span class="sxs-lookup"><span data-stu-id="bc314-161">True</span></span>  <br/> |<span data-ttu-id="bc314-162">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bc314-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="bc314-163">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="bc314-163">Skype for Business Server</span></span>  |<span data-ttu-id="bc314-164">False</span><span class="sxs-lookup"><span data-stu-id="bc314-164">False</span></span>  <br/> |<span data-ttu-id="bc314-165">사용자에게 Lync 모드로 전환하도록 요청했습니다(UI 설정을 Lync 모드로 변경하는 경우 나중에 사용자가 비즈니스용 Skype로 전환할 수 $true)</span><span class="sxs-lookup"><span data-stu-id="bc314-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="bc314-166">Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)</span><span class="sxs-lookup"><span data-stu-id="bc314-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="bc314-167">기본</span><span class="sxs-lookup"><span data-stu-id="bc314-167">Default</span></span>  <br/> |<span data-ttu-id="bc314-168">사용자에게 Lync 모드로 전환하도록 요청했습니다(UI 설정을 Lync 모드로 변경하는 경우 나중에 사용자가 비즈니스용 Skype로 전환할 수 $true)</span><span class="sxs-lookup"><span data-stu-id="bc314-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="bc314-169">Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)</span><span class="sxs-lookup"><span data-stu-id="bc314-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="bc314-170">True</span><span class="sxs-lookup"><span data-stu-id="bc314-170">True</span></span>  <br/> |<span data-ttu-id="bc314-171">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bc314-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="bc314-172">Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)</span><span class="sxs-lookup"><span data-stu-id="bc314-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="bc314-173">False</span><span class="sxs-lookup"><span data-stu-id="bc314-173">False</span></span>  <br/> |<span data-ttu-id="bc314-174">사용자에게 Lync 모드로 전환하도록 요청했습니다(UI 설정을 Lync 모드로 변경하는 경우 나중에 사용자가 비즈니스용 Skype로 전환할 수 $true)</span><span class="sxs-lookup"><span data-stu-id="bc314-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="bc314-175">Lync Server 2010 또는 Lync Server 2013(패치가 없는 경우)</span><span class="sxs-lookup"><span data-stu-id="bc314-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="bc314-176">기본</span><span class="sxs-lookup"><span data-stu-id="bc314-176">Default</span></span>  <br/> |<span data-ttu-id="bc314-177">사용자에게 Lync 모드로 전환하도록 요청했습니다(사용자가 나중에 비즈니스용 Skype로 전환할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="bc314-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="bc314-178">다음 표에는 관리자가 Skype UI 환경의 초기 설정을 변경할 때의 클라이언트 환경이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="bc314-179">**서버 버전**</span><span class="sxs-lookup"><span data-stu-id="bc314-179">**Server version**</span></span>|<span data-ttu-id="bc314-180">**EnableSkypeUI 설정**</span><span class="sxs-lookup"><span data-stu-id="bc314-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="bc314-181">**클라이언트 UI = Lync**</span><span class="sxs-lookup"><span data-stu-id="bc314-181">**Client UI = Lync**</span></span>|<span data-ttu-id="bc314-182">**클라이언트 UI = 비즈니스용 Skype**</span><span class="sxs-lookup"><span data-stu-id="bc314-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc314-183">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="bc314-183">Skype for Business Server</span></span> |<span data-ttu-id="bc314-184">True</span><span class="sxs-lookup"><span data-stu-id="bc314-184">True</span></span>  <br/> |<span data-ttu-id="bc314-185">사용자에게 비즈니스용 Skype로 전환하도록 요청한 경우</span><span class="sxs-lookup"><span data-stu-id="bc314-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="bc314-186">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bc314-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="bc314-187">비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="bc314-187">Skype for Business Server</span></span> |<span data-ttu-id="bc314-188">False</span><span class="sxs-lookup"><span data-stu-id="bc314-188">False</span></span>  <br/> |<span data-ttu-id="bc314-189">Lync 모드</span><span class="sxs-lookup"><span data-stu-id="bc314-189">Lync mode</span></span>  <br/> |<span data-ttu-id="bc314-190">사용자에게 Lync 모드로 전환하도록 요청했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="bc314-191">Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)</span><span class="sxs-lookup"><span data-stu-id="bc314-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="bc314-192">True</span><span class="sxs-lookup"><span data-stu-id="bc314-192">True</span></span>  <br/> |<span data-ttu-id="bc314-193">사용자에게 비즈니스용 Skype로 전환하도록 요청한 경우</span><span class="sxs-lookup"><span data-stu-id="bc314-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="bc314-194">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bc314-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="bc314-195">Lync Server 2010 또는 Lync Server 2013(올바른 패치 사용)</span><span class="sxs-lookup"><span data-stu-id="bc314-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="bc314-196">False</span><span class="sxs-lookup"><span data-stu-id="bc314-196">False</span></span>  <br/> |<span data-ttu-id="bc314-197">Lync 모드</span><span class="sxs-lookup"><span data-stu-id="bc314-197">Lync mode</span></span>  <br/> |<span data-ttu-id="bc314-198">사용자에게 Lync 모드로 전환하도록 요청했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="bc314-199">Lync Server 2010 또는 Lync Server 2013(패치가 없는 경우)</span><span class="sxs-lookup"><span data-stu-id="bc314-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="bc314-200">기본</span><span class="sxs-lookup"><span data-stu-id="bc314-200">Default</span></span>  <br/> |<span data-ttu-id="bc314-201">Lync 모드(비즈니스용 Skype로 전환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="bc314-202">Lync 모드(비즈니스용 Skype로 전환할 수 없습니다)</span><span class="sxs-lookup"><span data-stu-id="bc314-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="bc314-203">비즈니스용 Skype 클라이언트의 구성을 관리하는 데 필요한 패치 버전은</span><span class="sxs-lookup"><span data-stu-id="bc314-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="bc314-204">Lync Server 2010 - Lync Server 2010용 2015년 2월 누적 업데이트(4.0.7577.710)입니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="bc314-205">자세한 내용은 [Lync Server 2010용 업데이트를 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="bc314-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="bc314-206">Lync Server 2013 - Lync Server 2013용 2014년 12월 누적 업데이트(5.0.8308.857)</span><span class="sxs-lookup"><span data-stu-id="bc314-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="bc314-207">자세한 내용은 [Lync Server 2013용 업데이트를 참조하십시오.](https://go.microsoft.com/fwlink/p/?LinkId=532772)</span><span class="sxs-lookup"><span data-stu-id="bc314-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="bc314-208">도메인에 가입된 컴퓨터에서 레지스트리를 수정하는 그룹 정책 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="bc314-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="bc314-209">사용자가 비즈니스용 Skype 2015 클라이언트를 처음 시작하면 Lync 클라이언트 환경을 표시하는 레지스트리 업데이트가 한 번만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="bc314-210">GPO(그룹 정책 개체)를 사용하여 레지스트리를 업데이트하는 경우 값 데이터를 업데이트하는 대신 새 값을 만들 개체를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="bc314-211">GPO를 적용하면 새 값이 없는 경우 GPO에서 GPO를 만들고 값 데이터를 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="bc314-212">다음 절차에서는 사용자가 비즈니스용 Skype 2015 클라이언트를 처음 시작하면 Lync 클라이언트 환경이 표시될 수 있도록 레지스트리를 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="bc314-213">이 절차를 사용하여 앞에서 설명한 대로 시작 화면 자습서를 사용하지 않도록 레지스트리를 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="bc314-214">GPO를 만들 경우</span><span class="sxs-lookup"><span data-stu-id="bc314-214">To create the GPO</span></span>

1. <span data-ttu-id="bc314-215">그룹 정책 **관리 콘솔을 시작합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc314-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="bc314-216">그룹 정책 관리 콘솔을 사용하는 방법에 대한 자세한 내용은 그룹 정책 관리 [콘솔을 참조하십시오.](https://go.microsoft.com/fwlink/?LinkId=532759)</span><span class="sxs-lookup"><span data-stu-id="bc314-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="bc314-217">그룹 정책 개체 **노드를 마우스** 오른쪽 단추로 클릭하고 메뉴에서 **새로** 고침을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="bc314-218">새 **GPO** 대화 상자에서 GPO의 이름(예: MakeLyncDefaultUI)을 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc314-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="bc314-219">방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭한 다음 메뉴에서 **편집을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="bc314-220">그룹 **정책** 관리 편집기에서 사용자 **구성을** 확장하고, 기본 설정을 확장하고,  **Windows** 설정을 확장한 다음 레지스트리 **노드를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="bc314-221">레지스트리 노드를 마우스 오른쪽 단추로 **클릭한** 다음 새 레지스트리 **항목을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc314-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="bc314-222">새 레지스트리 속성 **대화 상자에서** 다음을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="bc314-223">**필드**</span><span class="sxs-lookup"><span data-stu-id="bc314-223">**Field**</span></span>|<span data-ttu-id="bc314-224">**선택하거나 입력할 값**</span><span class="sxs-lookup"><span data-stu-id="bc314-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="bc314-225">**작업**</span><span class="sxs-lookup"><span data-stu-id="bc314-225">**Action**</span></span> <br/> |<span data-ttu-id="bc314-226">**만들기**</span><span class="sxs-lookup"><span data-stu-id="bc314-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="bc314-227">**Hive**</span><span class="sxs-lookup"><span data-stu-id="bc314-227">**Hive**</span></span> <br/> | <span data-ttu-id="bc314-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="bc314-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="bc314-229">**키 경로**</span><span class="sxs-lookup"><span data-stu-id="bc314-229">**Key Path**</span></span> <br/> |<span data-ttu-id="bc314-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="bc314-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="bc314-231">**Value name**</span><span class="sxs-lookup"><span data-stu-id="bc314-231">**Value name**</span></span> <br/> |<span data-ttu-id="bc314-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="bc314-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="bc314-233">**값 형식**</span><span class="sxs-lookup"><span data-stu-id="bc314-233">**Value type**</span></span> <br/> |<span data-ttu-id="bc314-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="bc314-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="bc314-235">**Value data**</span><span class="sxs-lookup"><span data-stu-id="bc314-235">**Value data**</span></span> <br/> |<span data-ttu-id="bc314-236">00000000</span><span class="sxs-lookup"><span data-stu-id="bc314-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="bc314-237">**확인을** 클릭하여 변경 내용을 저장한 다음 GPO를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="bc314-238">그런 다음 만든 GPO를 OU와 같이 정책을 할당하려는 사용자 그룹에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="bc314-239">GPO를 사용하여 정책을 할당</span><span class="sxs-lookup"><span data-stu-id="bc314-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="bc314-240">그룹 정책 관리 콘솔에서 정책을 할당할 OU를 마우스 오른쪽 단추로 클릭한 다음 기존 **GPO에** 대한 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="bc314-241">**GPO 선택 대화** 상자에서 만든 GPO를 선택하고 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc314-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="bc314-242">대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="bc314-243">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="bc314-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="bc314-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="bc314-245">아래에 표시된 GPO의 이름을 사용하여 "할당된 그룹 정책 개체"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="bc314-246">레지스트리를 검사하여 GPO가 사용자 컴퓨터에서 레지스트리를 성공적으로 업데이트한지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-246">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="bc314-247">레지스트리 편집기를 열고 **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync] 키로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-247">Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key.</span></span> <span data-ttu-id="bc314-248">GPO가 레지스트리를 성공적으로 업데이트하면 EnableSkypeUI라는 값이 0으로 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc314-248">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

