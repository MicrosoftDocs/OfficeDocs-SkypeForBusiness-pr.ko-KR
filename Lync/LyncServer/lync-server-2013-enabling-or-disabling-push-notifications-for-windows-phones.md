---
title: 'Lync Server 2013: Windows phone의 푸시 알림 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b25594948f1d88caaca3dd07ca035b20f9f00079
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>Lync Server 2013에서 Windows phone의 푸시 알림 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

배지, 아이콘 또는 알림 형식의 푸시 알림은 모바일 응용 프로그램이 비활성화 되어 있는 경우에도 Windows Phone으로 보낼 수 있습니다. 푸시 알림은 새로운 또는 부재 중 메신저 대화 초대 및 음성 메일 등의 이벤트를 사용자에 게 알립니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 Windows Phone 장치에 대 한 푸시 알림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 Windows Phone에 대해 푸시 알림을 사용 하도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **푸시 알림 구성** 탐색 단추를 클릭 합니다.

4.  **푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **Microsoft 푸시 알림 사용** 확인란을 클릭 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 Windows Phone 용 푸시 알림을 사용 하지 않도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **푸시 알림 구성** 탐색 단추를 클릭 합니다.

4.  **푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **Microsoft 푸시 알림 사용** 확인란의 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 Windows Phone의 푸시 알림 사용 또는 사용 안 함

**CsPushNotificationConfiguration** cmdlet을 사용 하 여 Windows Phone에 대 한 푸시 알림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>Windows Phone에 대해 푸시 알림을 사용 하도록 설정 하려면

  - Windows Phone에 대해 푸시 알림을 사용 하려면 Enablemicro소프트 Pushservice 속성 값을 True ($True)로 설정 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>Windows Phone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면

  - Windows Phone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면 Enablemicro소프트 푸시 Notificationservice 속성 값을 False ($False)로 설정 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

자세한 내용은 [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.

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

