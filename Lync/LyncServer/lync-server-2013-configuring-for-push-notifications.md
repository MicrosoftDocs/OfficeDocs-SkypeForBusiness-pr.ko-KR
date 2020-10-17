---
title: 'Lync Server 2013: 푸시 알림 구성'
description: 'Lync Server 2013: 푸시 알림을 구성 합니다.'
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
ms.openlocfilehash: 24c22ff42f666add9eac4966134c88b9bf680046
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548334"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Lync Server 2013에서 푸시 알림 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-12_

배지, 아이콘 또는 경고 형태의 푸시 알림은 모바일 응용 프로그램이 비활성 상태일 때도 모바일 장치로 발송될 수 있습니다. 푸시 알림은 신규/부재 중 IM 초대 및 음성 메일 등의 이벤트를 사용자에게 알려 줍니다. Lync Server 2013 Mobility Service는 클라우드 기반 Lync Server 푸시 알림 서비스에 알림을 보낸 다음 APNS (Apple Push Notification Service) (Lync 2010 모바일 클라이언트를 실행 하는 Apple 장치) 또는 Microsoft 푸시 알림 서비스 (MPNS) (Lync 2010 Mobile 또는 Lync 2013 모바일 클라이언트를 실행 하는 Windows Phone 장치)에 알림을 보냅니다.

<div>


> [!IMPORTANT]  
> Lync 2010 Mobile 또는 Lync 2013 모바일 클라이언트에서 Windows Phone을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.<BR>Apple 장치에서 Lync 2010 Mobile을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.<BR>Apple 장치에서 Lync 2013 Mobile을 사용 하는 경우에는 푸시 알림이 더 이상 필요 하지 않습니다.



</div>

다음을 수행하여 푸시 알림을 지원하도록 토폴로지를 구성합니다.

  - 사용자 환경에 Lync Server 2010 또는 Lync Server 2013에 지 서버가 있는 경우 새 호스팅 공급자 (Microsoft Lync Online)를 추가 하 고 조직과 Lync Online 간에 호스팅 공급자 페더레이션을 설정 해야 합니다.

  - 사용자 환경에 Office Communications Server 2007 R2에 지 서버가 있는 경우에는 push.lync.com을 사용 하 여 직접 SIP 페더레이션을 설정 해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com은 푸시 알림 서비스용 Microsoft Office 365 도메인입니다.

    
    </div>

  - 푸시 알림을 사용하도록 설정하려면 **Set-CsPushNotificationConfiguration** cmdlet을 실행해야 합니다. 기본적으로 푸시 알림은 해제됩니다.

  - 페더레이션 구성 및 푸시 알림을 테스트합니다.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Lync Server 2013 또는 Lync Server 2010에 지 서버를 사용 하 여 푸시 알림을 구성 하려면

1.  Lync Server 관리 셸 및 Ocscore RtcUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  Lync Server online 호스팅 공급자를 추가 합니다. 명령줄에 다음을 입력합니다.
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    예를 들면 다음과 같습니다.
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 단일 호스팅 공급자와 둘 이상의 페더레이션 관계를 설정할 수는 없습니다. 즉, 이미 sipfed.online.lync.com과의 페더레이션 관계가 있는 호스팅 공급자를 설정한 경우에는 호스팅 공급자의 ID가 LyncOnline이 아니더라도 다른 호스팅 공급자를 추가해서는 안 됩니다.

    
    </div>

4.  명령줄에 다음을 입력하여 Lync Online의 푸시 알림 서비스와 조직 간의 호스팅 공급자 페더레이션을 설정합니다.
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Office Communications Server 2007 R2에 지 서버를 사용 하 여 푸시 알림을 구성 하려면

1.  RtcUniversalServerAdmins 그룹의 구성원으로에 지 서버에 로그온 합니다.

2.  **시작**을 클릭하고 **모든 프로그램**과 **관리 도구**를 차례로 클릭한 다음 **컴퓨터 관리**를 클릭합니다.

3.  콘솔 트리에서 **서비스 및 응용 프로그램**을 확장하고 **Microsoft Office Communications Server 2007 R2**를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.

4.  **허용** 탭에서 **추가**를 클릭합니다.

5.  **페더레이션 파트너 추가** 대화 상자에서 다음을 수행합니다.
    
      - **페더레이션 파트너 도메인 이름**에 **push.lync.com**을 입력합니다.
    
      - **페더레이션 파트너 액세스 에지 서버**에 **sipfed.online.lync.com**을 입력합니다.
    
      - **확인**을 클릭합니다.

</div>

<div>

## <a name="to-enable-push-notifications"></a>푸시 알림을 사용하도록 설정하려면

1.  Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에 다음을 입력하여 푸시 알림을 사용하도록 설정합니다.
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  명령줄에 다음을 입력하여 페더레이션을 사용하도록 설정합니다.
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>페더레이션 및 푸시 알림을 테스트하려면

1.  Lync Server 관리 셸 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에 다음을 입력하여 페더레이션 구성을 테스트합니다.
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    예를 들면 다음과 같습니다.
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  명령줄에 다음을 입력하여 푸시 알림을 테스트합니다.
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    예를 들면 다음과 같습니다.
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>참고 항목


[Test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

