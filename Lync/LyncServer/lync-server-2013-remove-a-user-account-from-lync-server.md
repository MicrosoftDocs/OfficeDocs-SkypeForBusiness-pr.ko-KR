---
title: 'Lync Server 2013: Lync Server에서 사용자 계정 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0699733bdfeb860aafa2b56086bf62988f18bbf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Lync Server 2013에서 사용자 계정 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

다음 절차에 따라 Lync Server 2013에서 이전에 추가 된 사용자 계정을 제거할 수 있습니다.

<div>


> [!NOTE]  
> 사용자를 제거하면 사용자 계정에 대해 구성한 모든 설정이 손실됩니다. 대신 사용자 계정을 일시적으로 사용 하지 않도록 설정 하려면 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013에 대해 사용 안 함 또는 다시 사용 사용자 계정</A>항목을 참조 하십시오.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Lync Server 관리 셸을 사용 하 여 사용자 계정을 제거 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭합니다.

4.  **사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기**를 클릭합니다.

5.  표에서 제거할 사용자 계정을 클릭합니다.

6.  **동작** 메뉴에서 **Lync Server에서 제거**를 선택하면 대화 상자가 나타납니다.

7.  대화 상자에서 **확인**을 선택하여 사용자를 제거합니다.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 계정 제거

사용 안 함-CsUser cmdlet을 사용 하 여 사용자 계정을 제거할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-user-account"></a>사용자 계정을 제거 하려면

  - 사용자 계정을 제거하려면 Disable-CsUser cmdlet을 사용합니다. 예를 들면 다음과 같습니다.
    
        Disable-CsUser -Identity "Ken Myer"
    
    이 명령을 실행한 후에는 계정 및 이전 설정을 다시 사용하도록 설정할 수 없습니다. 대신 Enable-CsUser cmdlet을 사용하여 Ken Myer에 대해 새 계정을 만들어야 합니다.

</div>

자세한 내용은 [CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Lync Server 2013에 대 한 사용자 사용 및 사용 안 함](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

