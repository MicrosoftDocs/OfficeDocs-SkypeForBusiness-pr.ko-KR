---
title: 'Lync Server 2013: Lync Server에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 합니다.'
description: 'Lync Server 2013: Lync Server에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 합니다.'
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
ms.openlocfilehash: 1b30d83d7a7f38b84f8e669ac06947eebf4a8545
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568174"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-04-04_

다음 절차에 따라 사용자 계정에 대해 구성한 Lync Server 설정을 잃지 않고 Lync Server 2013에서 이전에 사용 하도록 설정 된 사용자 계정을 사용 하지 않도록 설정할 수 있습니다. Lync Server 사용자 계정 설정이 손실 되지 않으므로 사용자 계정을 다시 구성 하지 않고도 이전에 설정한 사용자 계정을 다시 사용 하도록 설정할 수 있습니다.

<div>


> [!WARNING]  
> Active Directory에서 사용자 계정을 사용 하지 않도록 설정 하면 사용자가 Lync Server에 로그인 하거나 사용할 수 없게 <STRONG>됩니다</STRONG> . 이는 Lync에서 인증 프로세스를 간소화 하는 인증서 인증을 사용 하기 때문 이며, 이러한 클라이언트 인증서는 180 일 동안 유효 합니다. Lync Server에 대 한 액세스 권한을 부여 받은 <STRONG>사용자</STRONG> 에 게 사용 하도록 설정 된 Active Directory 계정을 사용 하지 않도록 설정 하려면이 문서에서 설명 하는 대로 Lync <STRONG>server 제어판</STRONG> 을 사용 해야 합니다. 사용자가 Lync에서 사용 하지 않도록 설정 되 고 중앙 관리 저장소가 환경에 복제 된 후에는 사용자가 더 이상 로그인 할 수 없게 됩니다. 또한 로그인 한 사용자는 연결 해제 됩니다.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Lync Server에 대해 이전에 사용 하도록 설정 된 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭합니다.

4.  **사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기**를 클릭합니다.

5.  표에서 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정을 클릭합니다.

6.  **동작** 메뉴에서 다음 중 하나를 수행합니다.
    
      - Lync Server 2013에 대 한 사용자 계정을 일시적으로 사용 하지 않도록 설정 하려면 **Lync server에 대해 일시적으로 사용 안 함을**클릭 합니다.
    
      - Lync Server 2013에 대 한 사용자 계정을 사용 하도록 설정 하려면 **Lync server에 대해 다시 사용**을 클릭 합니다.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows PowerShell을 사용 하 여 사용자 계정 사용/사용 안 함 설정

사용자 계정을 일시적으로 사용 하지 않도록 설정 했다가 나중에 다시 사용할 수 있도록 설정 하려면 **csuser** cmdlet을 사용 합니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-disable-a-user-account"></a>사용자 계정을 사용 하지 않도록 설정 하려면

  - 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 Enabled 속성의 값을 False($False)로 설정합니다. 예를 들면 다음과 같습니다.
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>사용자 계정을 다시 사용 하도록 설정 하려면

  - 사용하지 않도록 설정된 사용자 계정을 다시 사용하도록 설정하려면 Enabled 속성의 값을 True($True)로 설정합니다. 예를 들면 다음과 같습니다.
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

자세한 내용은 [CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대해 사용자 계정 추가 및 사용](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Lync Server 2013에 대 한 사용자 사용 및 사용 안 함](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

