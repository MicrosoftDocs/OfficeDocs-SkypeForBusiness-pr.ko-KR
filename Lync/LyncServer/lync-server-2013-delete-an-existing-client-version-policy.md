---
title: 'Lync Server 2013: 기존 클라이언트 버전 정책 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a5a35bf5b6d669d25cd5c91fe318c3de6bcdd03
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>Lync Server 2013에서 기존 클라이언트 버전 정책 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

이전에 구성한 클라이언트 버전 정책을 삭제 하려면 Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 삭제할 수 있습니다.

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 버전 정책을 삭제 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 정책** 탐색 단추를 클릭 합니다.

4.  **클라이언트 버전 정책** 페이지에서 삭제할 클라이언트 버전 정책 또는 정책을 선택 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 정책 삭제

**제거-CsClientVersionPolicy** cmdlet을 사용 하 여 클라이언트 버전 정책을 삭제할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>특정 클라이언트 버전 정책을 제거 하려면

  - 이 명령은 Redmond 사이트에 적용 된 클라이언트 버전 정책을 삭제 합니다.
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 클라이언트 버전 정책을 제거 하려면

  - 이 명령은 사이트 범위에서 구성 된 모든 클라이언트 버전 정책을 제거 합니다.
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>특정 사용자 에이전트를 포함 하지 않는 클라이언트 버전 정책을 제거 하려면

  - 그리고이 명령은 Windows Phone Lync (WPLync) 사용자 에이전트에 대 한 규칙을 포함 하지 않는 모든 클라이언트 버전 정책을 제거 합니다.
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

자세한 내용은 [제거-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

