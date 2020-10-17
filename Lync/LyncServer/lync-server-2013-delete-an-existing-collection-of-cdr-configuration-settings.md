---
title: 'Lync Server 2013: 기존 CDR 구성 설정 모음 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebf7ce01e435a0a47d3468509485e96fa669192a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514645"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 기존 CDR 구성 설정 모음 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.

Microsoft Lync Server 2013을 설치 하면 CDR 구성 설정의 단일 전역 모음이 만들어집니다. 관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다. 사이트 범위에서 구성된 설정은 기본적으로 전역 범위에서 구성된 설정보다 우선 적용됩니다. 사이트 범위 설정을 삭제할 경우 해당 사이트에서 전역 설정을 사용하여 CDR이 관리됩니다.

또한 전역 설정도 "삭제"할 수 있습니다. 하지만 전역 설정이 실제로 제거되지는 않습니다. 대신 해당 컬렉션의 모든 속성이 기본값으로 다시 설정됩니다. 예를 들어, CDR 구성 설정의 컬렉션에서는 기본적으로 삭제를 사용할 수 있도록 설정되어 있습니다. 삭제를 사용하지 않도록 전역 컬렉션을 수정한다고 가정해보겠습니다. 나중에 전역 설정을 삭제하면 모든 속성이 해당 기본값으로 다시 설정됩니다. 따라서 이 경우에는 삭제를 다시 사용할 수 있도록 설정됩니다.

Lync Server 제어판 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet을 사용 하 여 CDR 구성 설정을 제거할 수 있습니다.

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>Lync Server 제어판에서 CDR 구성 설정을 제거 하려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.

2.  **통화 정보 기록** 탭에서 제거하려는 CDR 설정의 컬렉션을 선택합니다. 여러 컬렉션을 선택하려면 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 추가 컬렉션을 클릭합니다.

3.  **편집**을 클릭한 다음 **삭제**를 클릭합니다.

4.  Lync Server 제어판 대화 상자에서 **확인**을 클릭 합니다.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 제거

Windows PowerShell 및 **get-cscdrconfiguration** cmdlet을 사용 하 여 통화 정보 기록 구성 설정을 삭제할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>CDR 구성 설정의 지정된 컬렉션을 제거하려면

  - 이 명령은 Redmond 사이트에 적용된 CDR 구성 설정을 제거합니다.
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 CDR 구성 설정을 제거 하려면

  - 이 명령은 사이트 범위에 적용된 모든 CDR 구성 설정을 제거합니다.
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>통화 정보 기록을 사용하지 않도록 설정하는 모든 CDR 구성 설정을 제거하려면

  - 이 명령은 통화 정보 기록이 사용하지 않도록 설정된 모든 CDR 구성 설정을 제거합니다.
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

자세한 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

