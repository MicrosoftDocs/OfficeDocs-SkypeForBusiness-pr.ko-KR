---
title: Lync Server 2013에서 비즈니스용 Skype 클라이언트 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20980f0f0b6697eada6c237aa8d2297b0fd227d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503305"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="c4e8f-102">비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="c4e8f-102">Configure the client experience with Skype for Business</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4e8f-103">_**마지막으로 수정 된 항목:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="c4e8f-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="c4e8f-104">**요약:** 이 항목에서는 Lync Server 2013 환경에서 비즈니스용 Skype 클라이언트 사용자에 대 한 클라이언트 환경을 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="c4e8f-105">2013 년 12 2014 월 누적 업데이트 (5.0.8308.857) 이상이 설치 된 Lync Server를 실행 하는 경우에만 클라이언트 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="c4e8f-106">Lync Server 2013 업데이트에 대 한 자세한 내용은 [Lync server 2013에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?linkid=532651)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="c4e8f-107">비즈니스용 skype는 Skype 소비자 제품 환경을 기반으로 하는 새로운 사용자 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="c4e8f-108">Lync의 모든 기능 외에도 비즈니스용 Skype는 간소화 된 컨트롤 및 익숙한 아이콘과 함께 새로운 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="c4e8f-109">새 클라이언트 환경에 대 한 자세한 내용은 [now for The Lync To 비즈니스용 Skype--what 's new를 참조](https://go.microsoft.com/fwlink/?linkid=529022)하세요.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="c4e8f-110">Lync Server 2013는 Lync 클라이언트 환경 뿐만 아니라 새로운 비즈니스용 Skype 클라이언트 환경을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="c4e8f-111">관리자는 사용자를 위한 기본 클라이언트 환경을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="c4e8f-112">예를 들어 조직의 사용자가 새로운 비즈니스용 Skype 환경에서 완벽 하 게 교육을 받을 때까지 Lync 클라이언트 환경을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="c4e8f-113">또는 모든 사용자를 비즈니스용 Skype 서버 2015로 아직 업그레이드 하지 않은 경우 모든 사용자가 새 서버로 업그레이드 될 때까지 동일한 클라이언트 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c4e8f-114">조직에 비즈니스용 Skype 서버 2015과 Lync Server 2013이 배포 되어 있는 경우 서버 버전 및 UI 설정에 따라 기본 클라이언트 환경이 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="c4e8f-115">사용자가 비즈니스용 Skype를 처음 시작 하면 Lync 사용자 인터페이스를 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="c4e8f-116">몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="c4e8f-117">자세한 내용은이 항목 뒷부분의 <STRONG>첫 번째 시작 클라이언트 동작</STRONG> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c4e8f-118">Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="c4e8f-119">클라이언트 환경에서 Lync 2013 클라이언트를 사용 하도록 구성 하기 전에 클라이언트 버전에서 번호 16으로 시작 하지 않는지 확인 하십시오. 예: x.x.x.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="c4e8f-120">클라이언트 환경 구성</span><span class="sxs-lookup"><span data-stu-id="c4e8f-120">Configure the client experience</span></span>

<span data-ttu-id="c4e8f-121">EnableSkypeUI 매개 변수와 함께 **CSClientPolicy** cmdlet을 사용 하 여 조직의 사용자가 보게 될 클라이언트 환경을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="c4e8f-122">다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다 (사이트 또는 사용자 관련 정책이 전역 정책을 재정의 함).</span><span class="sxs-lookup"><span data-stu-id="c4e8f-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="c4e8f-123">다음 명령은 글로벌 정책에 의해 영향을 받는 조직의 모든 사용자에 대해 Lync 클라이언트 환경을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="c4e8f-124">다음 명령은 Redmond 사이트 내의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="c4e8f-125">조직 내의 특정 사용자에 대 한 클라이언트 환경을 구성 하려는 경우에는 **새로운 CsClientPolicy** cmdlet을 사용 하 여 새 사용자 정책을 만든 다음 **부여-csclientpolicy** cmdlet을 사용 하 여 특정 사용자에 게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="c4e8f-126">예를 들어 다음 명령은 비즈니스용 Skype 클라이언트 환경을 선택 하는 새 클라이언트 정책 (SalesClientUI)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="c4e8f-127">다음 명령은 Sales 부서의 모든 구성원에 게 정책 SalesClientUI를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="c4e8f-128">첫 번째 클라이언트 동작 시작</span><span class="sxs-lookup"><span data-stu-id="c4e8f-128">First launch client behaviors</span></span>

<span data-ttu-id="c4e8f-129">기본적으로 사용자가 비즈니스용 Skype를 처음 시작 하면 EnableSkypeUI 매개 변수 값을 이전에 설명한 $False으로 설정 하 여 Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="c4e8f-130">몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="c4e8f-131">사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 사용자 인터페이스를 표시 하려면 클라이언트를 업데이트 한 후 처음 시작 하기 전에 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="c4e8f-132">`EnableSkypeUI`앞에서 설명한 대로 사용 중인 정책에서 값이 $False으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="c4e8f-133">사용자 컴퓨터에서 시스템 레지스트리를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="c4e8f-134">처음 사용자가 비즈니스용 Skype 클라이언트를 시작 하기 전에이 작업을 수행 해야 하며, 한 번만 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="c4e8f-135">도메인에 가입 된 컴퓨터에서 레지스트리를 업데이트 하는 그룹 정책 개체를 만드는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="c4e8f-136">\*\* \[ HKEY \_ 현재 \_ 사용자 \\ 소프트웨어 \\ Microsoft \\ Office \\ Lync \] \*\* 키에서 새 **이진** 값을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="c4e8f-137">**값 이름은** **EnableSkypeUI**이어야 하며 **값 데이터** 를 **00 00 00 00**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="c4e8f-138">키의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="c4e8f-139">이제 사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 사용자 인터페이스가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="c4e8f-140">시작 화면 자습서의 표시 제어</span><span class="sxs-lookup"><span data-stu-id="c4e8f-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="c4e8f-141">사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 *대부분의 사용자가 요청 하는 7 가지 빠른 팁*을 포함 하는 시작 화면을 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="c4e8f-142">시작 화면이 표시 되지 않도록 설정할 수 있지만 사용자는 클라이언트 컴퓨터에 다음 레지스트리 값을 추가 하 여 자습서에 액세스 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="c4e8f-143">\*\* \[ HKEY \_ 현재 \_ 사용자 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \] \*\* 키에서 새 **dword(32 (32 비트) 값**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="c4e8f-144">**값 이름은** **IsBasicTutorialSeenByUser**이어야 하며 **값 데이터** 를 **1**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="c4e8f-145">키의 모양은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="c4e8f-146">클라이언트 자습서 해제</span><span class="sxs-lookup"><span data-stu-id="c4e8f-146">Turn off the client tutorial</span></span>

<span data-ttu-id="c4e8f-147">사용자가 자습서에 액세스 하지 못하게 하려면 다음 레지스트리 값을 사용 하 여 클라이언트 자습서를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="c4e8f-148">\*\* \[ HKEY \_ 현재 \_ 사용자 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \] \*\* 키에서 새 **dword(32 (32 비트) 값**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="c4e8f-149">**값 이름은** **TutorialFeatureEnabled**이어야 하며 **값 데이터** 를 **0**으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="c4e8f-150">**값 데이터** 를 **1**로 설정 하 여 자습서를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="c4e8f-151">기본 클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="c4e8f-151">Default client experiences</span></span>

<span data-ttu-id="c4e8f-152">조직에 비즈니스용 Skype 서버 2015 및 Lync Server가 배포 되어 있는 경우 서버 버전과 Skype UI 설정에 따라 클라이언트 환경이 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="c4e8f-153">다음 표에는 서버 버전 및 UI 설정을 기반으로 하는 초기 클라이언트 환경이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c4e8f-154">서버 버전</span><span class="sxs-lookup"><span data-stu-id="c4e8f-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="c4e8f-155">EnableSkypeUI 설정</span><span class="sxs-lookup"><span data-stu-id="c4e8f-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="c4e8f-156">클라이언트 환경</span><span class="sxs-lookup"><span data-stu-id="c4e8f-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4e8f-157">Business Server 2015용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-158">기본</span><span class="sxs-lookup"><span data-stu-id="c4e8f-158">Default</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-159">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e8f-160">Business Server 2015용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-161">True</span><span class="sxs-lookup"><span data-stu-id="c4e8f-161">True</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-162">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e8f-163">Business Server 2015용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-164">False</span><span class="sxs-lookup"><span data-stu-id="c4e8f-164">False</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-165">사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경한 경우 나중에 비즈니스용 Skype로 전환할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e8f-166">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-167">기본</span><span class="sxs-lookup"><span data-stu-id="c4e8f-167">Default</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-168">사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경한 경우 나중에 비즈니스용 Skype로 전환할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e8f-169">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-170">True</span><span class="sxs-lookup"><span data-stu-id="c4e8f-170">True</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-171">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e8f-172">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-173">False</span><span class="sxs-lookup"><span data-stu-id="c4e8f-173">False</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-174">사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경한 경우 나중에 비즈니스용 Skype로 전환할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e8f-175">Lync Server 2010 또는 Lync Server 2013 (패치 없음)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-176">기본</span><span class="sxs-lookup"><span data-stu-id="c4e8f-176">Default</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-177">사용자가 Lync 클라이언트 환경으로 전환 하기를 요청 했습니다 (나중에 비즈니스용 Skype로 전환할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="c4e8f-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4e8f-178">다음 표에는 관리자가 Skype UI 환경의 초기 설정을 변경할 때의 클라이언트 환경이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c4e8f-179">서버 버전</span><span class="sxs-lookup"><span data-stu-id="c4e8f-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="c4e8f-180">Skype UI 설정</span><span class="sxs-lookup"><span data-stu-id="c4e8f-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="c4e8f-181">클라이언트 UI = Lync</span><span class="sxs-lookup"><span data-stu-id="c4e8f-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="c4e8f-182">클라이언트 UI = 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4e8f-183">Business Server 2015용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-184">True</span><span class="sxs-lookup"><span data-stu-id="c4e8f-184">True</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-185">비즈니스용 Skype로 전환 하 라는 사용자에 게 요청</span><span class="sxs-lookup"><span data-stu-id="c4e8f-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-186">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e8f-187">Business Server 2015용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-188">False</span><span class="sxs-lookup"><span data-stu-id="c4e8f-188">False</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-189">Lync UI</span><span class="sxs-lookup"><span data-stu-id="c4e8f-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-190">Lync UI로 전환 하 라는 사용자에 게 요청</span><span class="sxs-lookup"><span data-stu-id="c4e8f-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e8f-191">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-192">True</span><span class="sxs-lookup"><span data-stu-id="c4e8f-192">True</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-193">비즈니스용 Skype로 전환 하 라는 사용자에 게 요청</span><span class="sxs-lookup"><span data-stu-id="c4e8f-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-194">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="c4e8f-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4e8f-195">Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-196">False</span><span class="sxs-lookup"><span data-stu-id="c4e8f-196">False</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-197">Lync UI</span><span class="sxs-lookup"><span data-stu-id="c4e8f-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-198">Lync UI로 전환 하 라는 사용자에 게 요청</span><span class="sxs-lookup"><span data-stu-id="c4e8f-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4e8f-199">Lync Server 2010 또는 Lync Server 2013 (패치 없음)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-200">기본</span><span class="sxs-lookup"><span data-stu-id="c4e8f-200">Default</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-201">Lync 모드 (비즈니스용 Skype로 전환할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="c4e8f-202">Lync UI (비즈니스용 Skype로 전환할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c4e8f-203">비즈니스용 Skype 클라이언트의 구성을 관리 하는 데 필요한 패치 버전은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="c4e8f-204">Lync Server 2010-Lync Server 2010의 경우 2015 4.0.7577.710 (누적 업데이트)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="c4e8f-205">자세한 내용은 [Lync Server 2010에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?linkid=532771) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="c4e8f-206">Lync Server 2013-Lync Server 2013의 경우 12 월 2014 5.0.8308.857 (누적 업데이트)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="c4e8f-207">자세한 내용은 [Lync Server 2013에 대 한 업데이트](https://go.microsoft.com/fwlink/p/?linkid=532772)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="c4e8f-208">도메인에 가입 된 컴퓨터에서 레지스트리를 수정 하는 그룹 정책 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="c4e8f-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="c4e8f-209">사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 클라이언트 환경을 표시 하기 위한 레지스트리 업데이트는 한 번만 수행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="c4e8f-210">GPO (그룹 정책 개체)를 사용 하 여 레지스트리를 업데이트 하는 경우 값 데이터를 업데이트 하는 대신 새 값을 만들려면 개체를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="c4e8f-211">GPO가 적용 되 면 새 값이 없는 경우 GPO가이를 만들고 값 데이터를 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="c4e8f-212">다음 절차에서는 사용자가 비즈니스용 Skype를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 레지스트리를 수정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="c4e8f-213">또한이 절차를 사용 하 여 앞에서 설명한 것 처럼 시작 화면 자습서를 사용 하지 않도록 레지스트리를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="c4e8f-214">**GPO를 만들려면**</span><span class="sxs-lookup"><span data-stu-id="c4e8f-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="c4e8f-215">**그룹 정책 관리 콘솔**을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="c4e8f-216">그룹 정책 관리 콘솔을 사용 하는 방법에 대 한 자세한 내용은 [그룹 정책 관리 콘솔](https://go.microsoft.com/fwlink/?linkid=532759)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="c4e8f-217">**그룹 정책 개체** 노드를 마우스 오른쪽 단추로 클릭 하 고 메뉴에서 **새로 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="c4e8f-218">**새 gpo** 대화 상자에서 GPO의 이름 (예: **MakeLyncDefaultUI**)을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="c4e8f-219">방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="c4e8f-220">**그룹 정책 관리 편집기**에서 **사용자 구성**, **기본 설정**, **Windows 설정을**차례로 확장 한 다음 **레지스트리** 노드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="c4e8f-221">**레지스트리** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새** \> **레지스트리 항목**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="c4e8f-222">**새 레지스트리 속성** 대화 상자에서 다음을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c4e8f-223">필드</span><span class="sxs-lookup"><span data-stu-id="c4e8f-223">Field</span></span></th>
    <th><span data-ttu-id="c4e8f-224">선택 하거나 입력할 값</span><span class="sxs-lookup"><span data-stu-id="c4e8f-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c4e8f-225"><strong>작업</strong></span><span class="sxs-lookup"><span data-stu-id="c4e8f-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="c4e8f-226"><strong>만들기</strong></span><span class="sxs-lookup"><span data-stu-id="c4e8f-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c4e8f-227"><strong>벌</strong></span><span class="sxs-lookup"><span data-stu-id="c4e8f-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="c4e8f-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="c4e8f-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c4e8f-229"><strong>키 경로</strong></span><span class="sxs-lookup"><span data-stu-id="c4e8f-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="c4e8f-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="c4e8f-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c4e8f-231"><strong>Value name</strong></span><span class="sxs-lookup"><span data-stu-id="c4e8f-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="c4e8f-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="c4e8f-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c4e8f-233"><strong>값 형식</strong></span><span class="sxs-lookup"><span data-stu-id="c4e8f-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="c4e8f-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="c4e8f-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c4e8f-235"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="c4e8f-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="c4e8f-236">00000000</span><span class="sxs-lookup"><span data-stu-id="c4e8f-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="c4e8f-237">**확인** 을 클릭 하 여 변경 내용을 저장 하 고 GPO를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="c4e8f-238">다음으로, 만든 GPO를 정책을 할당 하려는 사용자 그룹 (예: OU)에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="c4e8f-239">**GPO를 사용 하 여 정책을 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="c4e8f-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="c4e8f-240">그룹 정책 관리 콘솔에서 정책을 할당 하려는 OU를 마우스 오른쪽 단추로 클릭 한 다음 **기존 GPO에 연결**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="c4e8f-241">**Gpo 선택** 대화 상자에서 만든 gpo를 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="c4e8f-242">대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="c4e8f-243">**gpupdate/target: 사용자**</span><span class="sxs-lookup"><span data-stu-id="c4e8f-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="c4e8f-244">"정책 업데이트 중 ..." 메시지 GPO가 적용 되는 동안 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="c4e8f-245">완료 되 면 "사용자 정책 업데이트가 완료 되었습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="c4e8f-246">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="c4e8f-247">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="c4e8f-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="c4e8f-248">아래에 표시 된 GPO 이름을 사용 하 여 "할당 된 그룹 정책 개체"를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="c4e8f-249">또한 레지스트리를 검사 하 여 GPO가 사용자 컴퓨터의 레지스트리를 성공적으로 업데이트 했는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="c4e8f-250">레지스트리 편집기를 열고 \*\* \[ HKEY \_ 현재 \_ 사용자 \\ Software \\ Microsoft \\ Office \\ Lync \] \*\* 키로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="c4e8f-251">GPO가 레지스트리를 성공적으로 업데이트 한 경우 값이 0 인 EnableSkypeUI 라는 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

