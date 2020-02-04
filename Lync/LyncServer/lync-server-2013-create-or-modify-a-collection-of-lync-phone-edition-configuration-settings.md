---
title: Lync Phone Edition 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="797f0-102">Lync Server 2013에서 Lync Phone Edition 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="797f0-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="797f0-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="797f0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="797f0-104">Lync Server를 설치할 때 Lync Phone Edition 설정의 전역 모음을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="797f0-105">이러한 설정은 배포에서 Lync Phone Edition을 실행 하는 모든 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="797f0-106">이러한 설정은 언제 든 지 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-106">You can change these settings at any time.</span></span> <span data-ttu-id="797f0-107">특정 사이트의 장치에 적용 되는 새 설정 모음을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="797f0-108">전역 설정 보다 사이트 설정이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="797f0-109">구성 설정은 컬렉션 이름, 범위 (전역 또는 사이트), SIP 보안 설정, 로깅 수준, 보이스 서비스 품질 (QoS) 수준, 전화 잠금 설정, 전화 잠금 세부 정보, 즉 a의 시간이 개인 식별 번호를 잠금 해제 하는 것으로 구성 됩니다 ( 핀)은 잠금 하기 전에 유휴 상태로 유지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="797f0-110">Lync Phone Edition 구성 설정 모음을 만들거나 기존 컬렉션에 대 한 설정 편집</span><span class="sxs-lookup"><span data-stu-id="797f0-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="797f0-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="797f0-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="797f0-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="797f0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="797f0-114">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="797f0-115">**장치 구성** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="797f0-116">Lync Phone Edition 구성 설정의 새 모음을 만들려면 **새로 만들기**를 클릭 하 고 사이트를 선택한 다음 **확인**을 클릭 하 고 기본 설정을 검토 한 다음 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="797f0-117">기존 컬렉션의 설정을 편집 하려면 모음을 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 변경 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="797f0-118">전역 컬렉션에 대 한 기본 설정 사용으로 돌아가려면 전역 컬렉션을 클릭 하 고 <STRONG>편집</STRONG> 메뉴를 클릭 한 다음 <STRONG>삭제</STRONG>를 클릭 하 고 <STRONG>확인</STRONG>을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="797f0-119">전역 수집은 삭제 되지 않습니다. 이렇게 하면 설정을 기본값으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="797f0-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="797f0-121">Windows PowerShell Cmdlet을 사용 하 여 새 Lync Phone Edition 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="797f0-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="797f0-122">Windows PowerShell 및 **새 CsUCPhoneConfiguration** cmdlet을 사용 하 여 Lync Phone Edition 구성 설정을 만들 수 있습니다 (사이트 범위에만 해당).</span><span class="sxs-lookup"><span data-stu-id="797f0-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="797f0-123">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="797f0-124">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="797f0-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="797f0-125">기본 값을 사용 하는 새 Lync Phone Edition 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="797f0-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="797f0-126">이 명령은 Redmond 사이트에 대 한 새로운 UC 전화 구성 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="797f0-127">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="797f0-128">새 Lync Phone Edition 구성 설정을 만들 때 단일 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="797f0-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="797f0-129">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="797f0-130">예를 들어 기본적으로 전화 잠금이 필요한 UC 전화 구성 설정 모음을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="797f0-131">새 Lync Phone Edition 구성 설정을 만들 때 여러 속성 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="797f0-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="797f0-132">여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="797f0-133">예를 들어이 명령은 전화 잠금을 적용 하 고 최소 PIN 길이를 8 자리로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="797f0-134">자세한 내용은 [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="797f0-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="797f0-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="797f0-135">See Also</span></span>


[<span data-ttu-id="797f0-136">Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="797f0-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="797f0-137">Lync Server 2013에서 Lync Phone 에디션에 대 한 보안 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="797f0-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="797f0-138">Lync Server 2013에서 전화 잠금 적용</span><span class="sxs-lookup"><span data-stu-id="797f0-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

