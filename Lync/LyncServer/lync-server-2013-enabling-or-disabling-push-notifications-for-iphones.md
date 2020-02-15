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
ms.openlocfilehash: f0b091910fa62c52e7ee0dd98862095995b4abe6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a>Lync Server 2013에서 Iphone에 대해 푸시 알림 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

배지, 아이콘 또는 경고 형태의 푸시 알림은 모바일 응용 프로그램이 비활성 상태인 경우에도 iPhone으로 보낼 수 있습니다. 푸시 알림은 신규/부재 중 IM 초대 및 음성 메일 등의 이벤트를 사용자에게 알려 줍니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 iPhone에 대해 푸시 알림을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 iPhone에 대해 푸시 알림을 사용 하도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **푸시 알림 구성**을 클릭합니다.

4.  **푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.

5.  **Apple 푸시 알림 사용** 확인란을 클릭합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 iPhone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **푸시 알림 구성**을 클릭합니다.

4.  **푸시 알림 구성** 페이지에서 편집 하려는 사이트를 클릭 하 고 **편집** 메뉴를 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.

5.  **Apple 푸시 알림 사용** 확인란의 선택을 취소합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 iPhone에 알림 푸시 사용 또는 사용 안 함

Apple iPhone에 대 한 푸시 알림은 **get-cspushnotificationconfiguration** cmdlet을 사용 하 여 사용 하거나 사용 하지 않도록 설정할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-push-notifications-for-iphone"></a>IPhone에 대해 푸시 알림을 사용 하도록 설정 하려면

  - IPhone에 푸시 알림을 사용 하도록 설정 하려면 EnableApplePushNotificationService 속성의 값을 True ($True)로 설정 합니다. 예:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a>IPhone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면

  - IPhone에 대해 푸시 알림을 사용 하지 않도록 설정 하려면 EnableApplePushNotificationService 속성의 값을 False ($False)로 set 합니다. 예:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

자세한 내용은 [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet에 대한 도움말 항목을 참조하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 푸시 알림 구성](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

