---
title: 'Lync Server 2013: 푸시 알림 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08492aaa6fc8c9fb6569ad6ad642a5cc1157a2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Lync Server 2013의 푸시 알림 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-12_

배지, 아이콘 또는 알림 형식의 푸시 알림은 모바일 응용 프로그램이 비활성화 된 경우에도 모바일 장치에 보낼 수 있습니다. 푸시 알림은 새로운 또는 부재 중 메신저 대화 초대 및 음성 메일 등의 이벤트를 사용자에 게 알립니다. Lync Server 2013 모바일 서비스는 클라우드 기반 Lync Server 푸시 알림 서비스에 알림을 보내고,이를 통해 APNS (Apple 푸시 알림 서비스) (Lync 2010 모바일 클라이언트를 실행 하는 Apple 디바이스의 경우) 또는 Microsoft 푸시 알림 서비스 (MPNS) (Lync 2010 모바일 또는 Lync 2013 모바일 클라이언트를 실행 하는 Windows Phone 장치인 경우)

<div>


> [!IMPORTANT]  
> Lync 2010 휴대폰 또는 Lync 2013 모바일 클라이언트와 함께 Windows Phone을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.<BR>Apple 장치에서 Lync 2010 Mobile을 사용 하는 경우 푸시 알림은 중요 한 고려 사항입니다.<BR>Apple 장치에서 Lync 2013 Mobile을 사용 하는 경우 더 이상 푸시 알림이 필요 하지 않습니다.



</div>

다음을 수행 하 여 푸시 알림을 지원 하도록 토폴로지를 구성 합니다.

  - 환경에 Lync Server 2010 또는 Lync Server 2013 Edge 서버가 있는 경우 새 호스팅 공급자, Microsoft Lync Online을 추가 하 고 조직과 Lync Online 간에 호스팅 공급자 페더레이션을 설정 해야 합니다.

  - 환경에 Office Communications Server 2007 R2 Edge 서버가 있는 경우 push.lync.com를 사용 하 여 직접 SIP 페더레이션을 설정 해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com는 푸시 알림 서비스에 대 한 Microsoft Office 365 도메인입니다.

    
    </div>

  - 푸시 알림을 사용 하도록 설정 하려면 **CsPushNotificationConfiguration** cmdlet을 실행 해야 합니다. 기본적으로 푸시 알림은 꺼져 있습니다.

  - 페더레이션 구성 및 푸시 알림을 테스트 합니다.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Lync Server 2013 또는 Lync Server 2010 Edge 서버를 사용 하 여 푸시 알림을 구성 하려면

1.  Lync Server Management Shell 및 Ocscore RtcUniversalServerAdmins 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  Lync Server online 호스팅 공급자를 추가 합니다. 명령줄에 다음을 입력 합니다.
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    예를 들면 다음과 같습니다.
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > 단일 호스팅 공급자에 두 개 이상의 페더레이션 관계를 사용할 수 없습니다. 즉, sipfed.online.lync.com와 페더레이션 관계가 있는 호스팅 공급자를 이미 설정한 경우 호스팅 공급자의 id가 L를 사용 하는 것 외에는 다른 호스팅 공급자를 추가 하지 않아야 합니다.

    
    </div>

4.  Lync Online에서 조직과 푸시 알림 서비스 간에 호스팅 공급자 페더레이션을 설정 합니다. 명령줄에 다음을 입력 합니다.
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Office Communications Server 2007 R2 Edge 서버를 사용 하 여 푸시 알림을 구성 하려면

1.  RtcUniversalServerAdmins 그룹의 구성원으로 Edge 서버에 로그온 합니다.

2.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **컴퓨터 관리**를 클릭 합니다.

3.  콘솔 트리에서 **서비스 및 응용 프로그램**을 확장 하 고 **Microsoft Office Communications Server 2007 R2**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

4.  **허용** 탭에서 **추가**를 클릭 합니다.

5.  **페더레이션 파트너 추가** 대화 상자에서 다음을 수행 합니다.
    
      - **페더레이션 파트너 도메인 이름**에 **push.lync.com**를 입력 합니다.
    
      - **페더레이션된 파트너 액세스에 지 서버**에 **sipfed.online.lync.com**를 입력 합니다.
    
      - **확인**을 클릭합니다.

</div>

<div>

## <a name="to-enable-push-notifications"></a>푸시 알림을 사용 하도록 설정 하려면

1.  Lync Server Management Shell 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  푸시 알림을 사용 하도록 설정 합니다. 명령줄에 다음을 입력 합니다.
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  페더레이션을 사용 합니다. 명령줄에 다음을 입력 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>페더레이션 및 푸시 알림을 테스트 하려면

1.  Lync Server Management Shell 및 Ocscore CsAdministrator 역할의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  페더레이션 구성을 테스트 합니다. 명령줄에 다음을 입력 합니다.
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    예를 들면 다음과 같습니다.
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  푸시 알림을 테스트 합니다. 명령줄에 다음을 입력 합니다.
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    예를 들면 다음과 같습니다.
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[테스트-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

