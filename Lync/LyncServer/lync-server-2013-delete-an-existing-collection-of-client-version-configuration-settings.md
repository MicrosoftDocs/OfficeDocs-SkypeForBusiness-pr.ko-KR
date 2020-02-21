---
title: 클라이언트 버전 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37a513a4c603a062b7aa2a596921e76f9f96cce1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 클라이언트 버전 구성 설정의 기존 컬렉션 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

사이트에 대해 이전에 구성 된 클라이언트 구성 설정을 제거 하려는 경우 Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 설정을 제거할 수 있습니다.

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 구성 설정을 제거 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.

4.  사이트를 선택 하 고 **편집**, **삭제**를 차례로 클릭 한 다음 **확인**을 클릭 합니다.

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 구성 설정 제거

클라이언트 버전 구성 설정은 **Remove-CsClientVersionConfiguration** cmdlet을 사용 하 여 삭제할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>클라이언트 버전 구성 설정의 지정 된 컬렉션을 제거 하려면

  - 다음 명령은 Redmond 사이트에 적용 된 클라이언트 버전 구성 설정을 제거 합니다.
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 클라이언트 버전 구성 설정을 제거 하려면

  - 이 명령은 사이트 범위에서 구성 된 모든 클라이언트 버전 구성 설정을 제거 합니다.
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>DefaultAction 속성 값을 기반으로 모든 클라이언트 버전 구성 설정을 제거 하려면

  - 그리고이 명령은 기본 동작이 "Block"으로 설정 된 모든 클라이언트 버전 구성 설정을 제거 합니다.
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

자세한 내용은 [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

