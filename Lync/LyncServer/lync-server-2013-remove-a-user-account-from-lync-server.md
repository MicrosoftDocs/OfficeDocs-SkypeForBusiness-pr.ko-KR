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
ms.openlocfilehash: 97ee26fd15eb9df9174fd33cf9a45a6fe49411af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>Lync Server 2013에서 사용자 계정 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

다음 절차를 사용 하 여 Lync Server 2013에서 이전에 추가 된 사용자 계정을 제거할 수 있습니다.

<div>


> [!NOTE]  
> 사용자를 제거 하면 사용자 계정에 대해 구성한 모든 설정이 손실 될 수 있습니다. 대신 사용자 계정을 일시적으로 사용 하지 않으려면 <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013에서 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</A>하는 방법 항목을 참조 하세요.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 사용자 계정을 제거 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하지 않도록 설정 하려는 사용자 계정의 URI (Uniform resource identifier)를 모두 또는 첫 번째 부분을 입력 한 다음 **찾기를**클릭 합니다.

5.  표에서 제거 하려는 사용자 계정을 클릭 합니다.

6.  **작업** 메뉴에서 **Lync Server에서 제거**를 선택 하면 대화 상자가 나타납니다.

7.  대화 상자에서 **확인** 을 선택 하 여 사용자를 제거 합니다.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 계정 제거

CsUser cmdlet을 사용 하 여 사용자 계정을 제거할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-user-account"></a>사용자 계정을 제거 하려면

  - 사용자 계정을 제거 하려면 Disable-CsUser cmdlet을 사용 합니다. 예를 들면 다음과 같습니다.
    
        Disable-CsUser -Identity "Ken Myer"
    
    이 명령이 실행 된 후에는 계정과 이전 설정을 다시 사용 하도록 설정할 수 있는 방법이 없습니다. 대신: 진구 Myer에 대 한 새 계정을 만들려면 Enable-CsUser cmdlet을 사용 해야 합니다.

</div>

자세한 내용은 [-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Lync Server 2013에 대 한 사용자 설정 및 해제](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

