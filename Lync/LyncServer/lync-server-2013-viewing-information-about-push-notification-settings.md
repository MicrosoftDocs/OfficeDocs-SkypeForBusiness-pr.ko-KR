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

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Lync Server 2013에서 푸시 알림 설정에 대 한 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

배지, 아이콘 또는 알림 형식의 푸시 알림은 모바일 응용 프로그램이 비활성화 된 경우에도 모바일 장치에 보낼 수 있습니다. 푸시 알림은 새로운 또는 부재 중 메신저 대화 초대 및 음성 메일 등의 이벤트를 사용자에 게 알립니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 모바일 장치에 대 한 정보 푸시 알림 설정을 볼 수 있습니다.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Lync Server 제어판에서 푸시 알림 정보를 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **푸시 알림 구성** 탐색 단추를 클릭 합니다.

4.  **푸시 알림 구성** 페이지에서 보려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 푸시 알림 정보 보기

Windows PowerShell 및 **CsPushNotificationConfiguration** cmdlet을 사용 하 여 푸시 알림 구성 설정을 볼 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-push-notification-configuration-information"></a>푸시 알림 구성 정보를 보려면

  - 모든 푸시 알림 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsPushNotificationConfiguration
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) 을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 푸시 알림 구성](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

