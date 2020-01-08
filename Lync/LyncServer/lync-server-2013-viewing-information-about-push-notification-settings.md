---
title: 'Lync Server 2013: 푸시 알림 설정에 대 한 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da9279d09ab3b344514a472f3fb0f38e7071aabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="77ee7-102">Lync Server 2013에서 푸시 알림 설정에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="77ee7-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77ee7-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="77ee7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="77ee7-104">배지, 아이콘 또는 알림 형식의 푸시 알림은 모바일 응용 프로그램이 비활성화 된 경우에도 모바일 장치에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="77ee7-105">푸시 알림은 새로운 또는 부재 중 메신저 대화 초대 및 음성 메일 등의 이벤트를 사용자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="77ee7-106">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 모바일 장치에 대 한 정보 푸시 알림 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="77ee7-107">Lync Server 제어판에서 푸시 알림 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="77ee7-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="77ee7-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="77ee7-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="77ee7-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77ee7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="77ee7-111">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **푸시 알림 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="77ee7-112">**푸시 알림 구성** 페이지에서 보려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="77ee7-113">Windows PowerShell Cmdlet을 사용 하 여 푸시 알림 정보 보기</span><span class="sxs-lookup"><span data-stu-id="77ee7-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="77ee7-114">Windows PowerShell 및 **CsPushNotificationConfiguration** cmdlet을 사용 하 여 푸시 알림 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="77ee7-115">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="77ee7-116">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77ee7-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="77ee7-117">푸시 알림 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="77ee7-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="77ee7-118">모든 푸시 알림 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="77ee7-119">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77ee7-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="77ee7-120">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77ee7-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77ee7-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77ee7-121">See Also</span></span>


[<span data-ttu-id="77ee7-122">Lync Server 2013의 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="77ee7-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

