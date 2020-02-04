---
title: 'Lync Server 2013: 푸시 알림 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="aeb79-102">Lync Server 2013의 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="aeb79-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb79-103">_**마지막으로 수정한 주제:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="aeb79-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="aeb79-104">배지, 아이콘 또는 알림 형식의 푸시 알림은 모바일 응용 프로그램이 비활성화 된 경우에도 모바일 장치에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="aeb79-105">푸시 알림은 새로운 또는 부재 중 메신저 대화 초대 및 음성 메일 등의 이벤트를 사용자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="aeb79-106">Lync Server 2013 모바일 서비스는 클라우드 기반 Lync Server 푸시 알림 서비스에 알림을 보내고,이를 통해 APNS (Apple 푸시 알림 서비스) (Lync 2010 모바일 클라이언트를 실행 하는 Apple 디바이스의 경우) 또는 Microsoft 푸시 알림 서비스 (MPNS) (Lync 2010 모바일 또는 Lync 2013 모바일 클라이언트를 실행 하는 Windows Phone 장치인 경우)</span><span class="sxs-lookup"><span data-stu-id="aeb79-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aeb79-107">Lync 2010 휴대폰 또는 Lync 2013 모바일 클라이언트와 함께 Windows Phone을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="aeb79-108">Apple 장치에서 Lync 2010 Mobile을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="aeb79-109">Apple 장치에서 Lync 2013 Mobile을 사용 하는 경우 더 이상 푸시 알림이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="aeb79-110">다음을 수행 하 여 푸시 알림을 지원 하도록 토폴로지를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="aeb79-111">환경에 Lync Server 2010 또는 Lync Server 2013 Edge 서버가 있는 경우 새 호스팅 공급자, Microsoft Lync Online을 추가 하 고 조직과 Lync Online 간에 호스팅 공급자 페더레이션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="aeb79-112">환경에 Office Communications Server 2007 R2 Edge 서버가 있는 경우 push.lync.com를 사용 하 여 직접 SIP 페더레이션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aeb79-113">Push.lync.com는 푸시 알림 서비스에 대 한 Microsoft Office 365 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="aeb79-114">푸시 알림을 사용 하도록 설정 하려면 **CsPushNotificationConfiguration** cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="aeb79-115">기본적으로 푸시 알림은 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="aeb79-116">페더레이션 구성 및 푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="aeb79-117">Lync Server 2013 또는 Lync Server 2010 Edge 서버를 사용 하 여 푸시 알림을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="aeb79-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="aeb79-118">Lync Server Management Shell 및 Ocscore RtcUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="aeb79-119">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aeb79-120">Lync Server online 호스팅 공급자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="aeb79-121">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="aeb79-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aeb79-123">단일 호스팅 공급자에 두 개 이상의 페더레이션 관계를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="aeb79-124">즉, sipfed.online.lync.com와 페더레이션 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 id가 L를 사용 하는 것 외에는 다른 호스팅 공급자를 추가 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="aeb79-125">Lync Online에서 조직과 푸시 알림 서비스 간에 호스팅 공급자 페더레이션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="aeb79-126">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="aeb79-127">Office Communications Server 2007 R2 Edge 서버를 사용 하 여 푸시 알림을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="aeb79-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="aeb79-128">RtcUniversalServerAdmins 그룹의 구성원으로 Edge 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="aeb79-129">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **컴퓨터 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="aeb79-130">콘솔 트리에서 **서비스 및 응용 프로그램**을 확장 하 고 **Microsoft Office Communications Server 2007 R2**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="aeb79-131">**허용** 탭에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="aeb79-132">**페더레이션 파트너 추가** 대화 상자에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="aeb79-133">**페더레이션 파트너 도메인 이름**에 **push.lync.com**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="aeb79-134">**페더레이션된 파트너 액세스에 지 서버**에 **sipfed.online.lync.com**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="aeb79-135">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="aeb79-136">푸시 알림을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="aeb79-136">To enable push notifications</span></span>

1.  <span data-ttu-id="aeb79-137">Lync Server Management Shell 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="aeb79-138">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aeb79-139">푸시 알림을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-139">Enable push notifications.</span></span> <span data-ttu-id="aeb79-140">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="aeb79-141">페더레이션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-141">Enable federation.</span></span> <span data-ttu-id="aeb79-142">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="aeb79-143">페더레이션 및 푸시 알림을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="aeb79-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="aeb79-144">Lync Server Management Shell 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="aeb79-145">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aeb79-146">페더레이션 구성을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-146">Test the federation configuration.</span></span> <span data-ttu-id="aeb79-147">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="aeb79-148">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="aeb79-149">푸시 알림을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-149">Test push notifications.</span></span> <span data-ttu-id="aeb79-150">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="aeb79-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aeb79-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aeb79-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aeb79-152">See Also</span></span>


[<span data-ttu-id="aeb79-153">테스트-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="aeb79-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="aeb79-154">테스트-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="aeb79-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

