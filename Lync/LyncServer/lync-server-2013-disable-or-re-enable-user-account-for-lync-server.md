---
title: 'Lync Server 2013: Lync Server에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aea86048fa29e9b6a21aa040093edff3f53ffe27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Lync Server 2013의 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-04-04_

사용자 계정에 대해 구성한 Lync Server 설정을 잃지 않고 다음 절차를 사용 하 여 Lync Server 2013에서 이전에 사용 하도록 설정 된 사용자 계정을 사용 하지 않도록 설정할 수 있습니다. Lync Server 사용자 계정 설정이 손실 되지 않으므로 사용자 계정을 다시 구성할 필요 없이 이전에 설정 된 사용자 계정을 다시 사용할 수 있습니다.

<div>


> [!WARNING]  
> Active Directory에서 사용자 계정을 사용 하지 않도록 설정 해도 사용자가 Lync Server에 로그인 하거나 사용할 수 있는 것은 중지 <STRONG>되지</STRONG> 않습니다. 이는 Lync에서 인증 프로세스를 간소화 하는 인증서 인증을 사용 하는 것이 고,이 클라이언트 인증서는 180 일간 유효 합니다. Lync에 대 한 액세스를 사용 하도록 설정 된 비활성 Active Directory 계정을 중지 하려면이 문서에서 설명 하는 대로 lync 사용자를 사용 <STRONG>하지 않도록</STRONG> 설정 하거나 <STRONG>Lync Server 컨트롤 패널</STRONG> 을 사용 해야 합니다. Lync에서 사용자를 사용 하지 않도록 설정 하 고 중앙 관리 저장소가 환경에 복제 된 경우에는 사용자가 더 이상 로그인 할 수 없게 됩니다. 또한 로그인 한 사용자는 연결이 끊깁니다.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Lync Server에 대해 이전에 사용 하도록 설정 된 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하지 않도록 설정 하려는 사용자 계정의 URI (Uniform resource identifier)를 모두 또는 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.

5.  표에서 사용 하지 않도록 설정 하거나 다시 사용할 수 있도록 설정할 사용자 계정을 클릭 합니다.

6.  **작업** 메뉴에서 다음 중 하나를 수행 합니다.
    
      - Lync Server 2013의 사용자 계정을 일시적으로 사용 하지 않도록 설정 하려면 **Lync server에 대해 일시적으로 사용 안 함**을 클릭 합니다.
    
      - Lync Server 2013에 대 한 사용자 계정을 사용 하도록 설정 하려면 **Lync server에 대해 다시 사용**을 클릭 합니다.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows PowerShell을 사용 하 여 사용자 계정 비활성화 또는 다시 사용 하도록 설정

사용자 계정을 일시적으로 사용 하지 않도록 설정한 다음 나중에 **Set CsUser** cmdlet을 사용 하 여 다시 사용할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-disable-a-user-account"></a>사용자 계정을 사용 하지 않도록 설정 하려면

  - 사용자 계정을 일시적으로 사용 하지 않도록 설정 하려면 Enabled 속성의 값을 False ($False)로 설정 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>사용자 계정을 다시 사용 하도록 설정 하려면

  - 사용 하지 않도록 설정 된 사용자 계정을 다시 사용 하도록 설정 하려면 Enabled 속성의 값을 True ($True)로 설정 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

자세한 내용은 [집합 CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 사용자 계정 추가 및 설정](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Lync Server 2013에 대 한 사용자 설정 및 해제](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

