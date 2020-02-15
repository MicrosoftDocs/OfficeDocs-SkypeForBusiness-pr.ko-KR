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
ms.openlocfilehash: f92ae27b919df6a32f06921df97746680a68b030
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="128ec-102">Lync Server 2013에서 푸시 알림 구성</span><span class="sxs-lookup"><span data-stu-id="128ec-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="128ec-103">_**마지막으로 수정 된 항목:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="128ec-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="128ec-104">배지, 아이콘 또는 경고 형태의 푸시 알림은 모바일 응용 프로그램이 비활성 상태일 때도 모바일 장치로 발송될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="128ec-105">푸시 알림은 신규/부재 중 IM 초대 및 음성 메일 등의 이벤트를 사용자에게 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="128ec-106">Lync Server 2013 Mobility Service는 클라우드 기반 Lync Server 푸시 알림 서비스에 알림을 보낸 다음 APNS (Apple Push Notification Service) (Lync 2010 모바일 클라이언트를 실행 하는 Apple 장치)에 알림을 전송 합니다. Microsoft MPNS (푸시 알림 서비스) (Lync 2010 Mobile 또는 Lync 2013 모바일 클라이언트를 실행 하는 Windows Phone 장치용)</span><span class="sxs-lookup"><span data-stu-id="128ec-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="128ec-107">Lync 2010 Mobile 또는 Lync 2013 모바일 클라이언트에서 Windows Phone을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="128ec-108">Apple 장치에서 Lync 2010 Mobile을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="128ec-109">Apple 장치에서 Lync 2013 Mobile을 사용 하는 경우에는 푸시 알림이 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="128ec-110">다음을 수행하여 푸시 알림을 지원하도록 토폴로지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="128ec-111">사용자 환경에 Lync Server 2010 또는 Lync Server 2013에 지 서버가 있는 경우 새 호스팅 공급자 (Microsoft Lync Online)를 추가 하 고 조직과 Lync Online 간에 호스팅 공급자 페더레이션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="128ec-112">사용자 환경에 Office Communications Server 2007 R2에 지 서버가 있는 경우에는 push.lync.com을 사용 하 여 직접 SIP 페더레이션을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="128ec-113">Push.lync.com은 푸시 알림 서비스용 Microsoft Office 365 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="128ec-114">푸시 알림을 사용하도록 설정하려면 **Set-CsPushNotificationConfiguration** cmdlet을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="128ec-115">기본적으로 푸시 알림은 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="128ec-116">페더레이션 구성 및 푸시 알림을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="128ec-117">Lync Server 2013 또는 Lync Server 2010에 지 서버를 사용 하 여 푸시 알림을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="128ec-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="128ec-118">Lync Server 관리 셸 및 Ocscore RtcUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="128ec-119">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="128ec-120">Lync Server online 호스팅 공급자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="128ec-121">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="128ec-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="128ec-p104">단일 호스팅 공급자와 둘 이상의 페더레이션 관계를 설정할 수는 없습니다. 즉, 이미 sipfed.online.lync.com과의 페더레이션 관계가 있는 호스팅 공급자를 설정한 경우에는 호스팅 공급자의 ID가 LyncOnline이 아니더라도 다른 호스팅 공급자를 추가해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-p104">You cannot have more than one federation relationship with a single hosting provider. That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="128ec-p105">명령줄에 다음을 입력하여 Lync Online의 푸시 알림 서비스와 조직 간의 호스팅 공급자 페더레이션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-p105">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online. At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="128ec-127">Office Communications Server 2007 R2에 지 서버를 사용 하 여 푸시 알림을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="128ec-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="128ec-128">RtcUniversalServerAdmins 그룹의 구성원으로에 지 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="128ec-129">**시작**을 클릭하고 **모든 프로그램**과 **관리 도구**를 차례로 클릭한 다음 **컴퓨터 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="128ec-130">콘솔 트리에서 **서비스 및 응용 프로그램**을 확장하고 **Microsoft Office Communications Server 2007 R2**를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="128ec-131">**허용** 탭에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="128ec-132">**페더레이션 파트너 추가** 대화 상자에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="128ec-133">**페더레이션 파트너 도메인 이름**에 **push.lync.com**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="128ec-134">**페더레이션 파트너 액세스 에지 서버**에 **sipfed.online.lync.com**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="128ec-135">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="128ec-136">푸시 알림을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="128ec-136">To enable push notifications</span></span>

1.  <span data-ttu-id="128ec-137">Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="128ec-138">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="128ec-p106">명령줄에 다음을 입력하여 푸시 알림을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-p106">Enable push notifications. At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="128ec-p107">명령줄에 다음을 입력하여 페더레이션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-p107">Enable federation. At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="128ec-143">페더레이션 및 푸시 알림을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="128ec-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="128ec-144">Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="128ec-145">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="128ec-p108">명령줄에 다음을 입력하여 페더레이션 구성을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-p108">Test the federation configuration. At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="128ec-148">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="128ec-p109">명령줄에 다음을 입력하여 푸시 알림을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-p109">Test push notifications. At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="128ec-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="128ec-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="128ec-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="128ec-152">See Also</span></span>


[<span data-ttu-id="128ec-153">Test-csfederatedpartner</span><span class="sxs-lookup"><span data-stu-id="128ec-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="128ec-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="128ec-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

