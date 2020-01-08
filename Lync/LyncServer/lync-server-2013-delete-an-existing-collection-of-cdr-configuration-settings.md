---
title: 'Lync Server 2013: 기존 CDR 구성 설정 모음 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 기존 CDR 구성 설정 모음 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.

Microsoft Lync Server 2013을 설치 하면 사용자를 위해 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다. 또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다. 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 하므로 디자인에 따라 적용 됩니다. 사이트 범위 설정을 삭제 하는 경우에는 전역 설정을 사용 하 여 해당 사이트에서 CDR가 관리 됩니다.

전역 설정을 "삭제" 할 수도 있습니다. 그러나 전역 설정은 실제로 제거 되지 않습니다. 대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정 됩니다. 예를 들어, CDR 구성 설정 컬렉션에서 기본적으로 제거를 사용할 수 있습니다. 제거를 사용할 수 없도록 전역 컬렉션을 수정 한다고 가정 합니다. 나중에 전역 설정을 삭제 하면 모든 속성이 기본값으로 다시 설정 됩니다. 이 경우 제거를 다시 사용할 수 있습니다.

Lync Server 제어판 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet을 사용 하 여 CDR 구성 설정을 제거할 수 있습니다.

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Lync Server 제어판에서 CDR 구성 설정을 제거 하려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.

2.  **통화 정보 기록** 탭에서 제거할 CDR 설정 모음 (또는 컬렉션)을 선택 합니다. 여러 컬렉션을 선택 하려면 첫 번째 컬렉션을 클릭 하 고 Ctrl 키를 누른 상태에서 추가 모음을 클릭 합니다.

3.  **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

4.  Lync Server 제어판 대화 상자에서 **확인**을 클릭 합니다.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 제거

Windows PowerShell 및 **CsCdrConfiguration** cmdlet을 사용 하 여 통화 정보 기록 구성 설정을 삭제할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>지정 된 CDR 구성 설정 모음을 제거 하려면

  - 이 명령은 Redmond 사이트에 적용 된 CDR 구성 설정을 제거 합니다.
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 하려면

  - 이 명령은 사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 합니다.
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>통화 정보 기록을 사용 하지 않도록 설정 하는 모든 CDR 구성 설정을 제거 하려면

  - 이 명령은 통화 세부 기록이 비활성화 된 모든 CDR 구성 설정을 제거 합니다.
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

자세한 내용은 [제거 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

