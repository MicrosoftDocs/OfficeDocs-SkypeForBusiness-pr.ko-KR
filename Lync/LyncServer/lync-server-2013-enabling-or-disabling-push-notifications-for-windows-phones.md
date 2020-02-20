---
title: 'Lync Server 2013: Windows phone에 대해 푸시 알림 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb64d01703b020e8abb983843e80980535373f6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="0df93-102">Lync Server 2013에서 Windows phone에 대해 푸시 알림 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0df93-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0df93-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0df93-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0df93-104">배지, 아이콘, 알림 형식의 푸시 알림은 모바일 응용 프로그램이 비활성 상태일 때도 Windows Phone으로 전송 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="0df93-105">푸시 알림은 신규/부재 중 IM 초대 및 음성 메일 등의 이벤트를 사용자에게 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="0df93-106">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 Windows Phone 장치에 대 한 푸시 알림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="0df93-107">Lync Server 제어판을 사용 하 여 Windows Phone에 대해 푸시 알림을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0df93-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0df93-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0df93-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0df93-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0df93-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0df93-111">왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **푸시 알림 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="0df93-112">**푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0df93-113">**Microsoft 푸시 알림 사용** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="0df93-114">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="0df93-115">Lync Server 제어판을 사용 하 여 Windows Phone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0df93-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0df93-116">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0df93-117">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0df93-118">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0df93-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0df93-119">왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **푸시 알림 구성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="0df93-120">**푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0df93-121">**Enable Microsoft push notifications**(Microsoft 푸시 알림 사용) 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="0df93-122">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0df93-123">Windows PowerShell Cmdlet을 사용 하 여 Windows Phone에 대해 푸시 알림 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0df93-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0df93-124">**Get-cspushnotificationconfiguration** cmdlet을 사용 하 여 Windows Phone에 대해 푸시 알림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="0df93-125">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0df93-126">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0df93-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="0df93-127">Windows Phone에 대해 푸시 알림을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0df93-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="0df93-128">Windows Phone에 대해 푸시 알림을 사용 하도록 설정 하려면 Enablemicro소프트 Pushnotificationservice 속성의 값을 True ($True)로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="0df93-129">예:</span><span class="sxs-lookup"><span data-stu-id="0df93-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="0df93-130">Windows Phone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0df93-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="0df93-131">Windows Phone에 대해 푸시 알림을 사용 하지 않으려면 Enablemicro소프트 Pushnotificationservice 속성의 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0df93-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="0df93-132">예:</span><span class="sxs-lookup"><span data-stu-id="0df93-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="0df93-133">자세한 내용은 [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0df93-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0df93-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0df93-134">See Also</span></span>


[<span data-ttu-id="0df93-135">Lync Server 2013에서 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="0df93-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

