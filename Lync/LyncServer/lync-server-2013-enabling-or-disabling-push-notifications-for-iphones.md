---
title: 'Lync Server 2013: Iphone에 대 한 푸시 알림 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a73d0f32da5063f98da662e85ec531de6801a428
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="1a2f6-102">Lync Server 2013에서 Iphone에 대 한 푸시 알림 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1a2f6-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a2f6-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1a2f6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1a2f6-104">배지, 아이콘 또는 알림 형식의 푸시 알림은 모바일 응용 프로그램이 비활성화 된 경우에도 iPhone으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="1a2f6-105">푸시 알림은 새로운 또는 부재 중 메신저 대화 초대 및 음성 메일 등의 이벤트를 사용자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="1a2f6-106">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 iPhone에 대 한 푸시 알림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="1a2f6-107">Lync Server 제어판을 사용 하 여 iPhone 용 푸시 알림을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1a2f6-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1a2f6-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a2f6-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a2f6-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a2f6-111">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **푸시 알림 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1a2f6-112">**푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1a2f6-113">**Apple 푸시 알림 사용** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="1a2f6-114">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="1a2f6-115">Lync Server 제어판을 사용 하 여 iPhone 용 푸시 알림을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1a2f6-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1a2f6-116">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a2f6-117">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a2f6-118">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a2f6-119">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **푸시 알림 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1a2f6-120">**푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1a2f6-121">**Apple 푸시 알림 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="1a2f6-122">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1a2f6-123">Windows PowerShell Cmdlet을 사용 하 여 iPhone에 대 한 푸시 알림 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1a2f6-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1a2f6-124">**CsPushNotificationConfiguration** cmdlet을 사용 하 여 Apple iPhone에 대 한 푸시 알림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="1a2f6-125">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a2f6-126">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="1a2f6-127">IPhone에 대해 푸시 알림을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1a2f6-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="1a2f6-128">IPhone에 대해 푸시 알림을 사용 하려면 EnableApplePushNotificationService 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="1a2f6-129">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="1a2f6-130">IPhone의 푸시 알림을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="1a2f6-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="1a2f6-131">IPhone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면 EnableApplePushNotificationService 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="1a2f6-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="1a2f6-133">자세한 내용은 [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a2f6-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a2f6-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a2f6-134">See Also</span></span>


[<span data-ttu-id="1a2f6-135">Lync Server 2013의 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="1a2f6-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

