---
title: 'Lync Server 2013: CDR 구성 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View CDR configuration information
ms:assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688096(v=OCS.15)
ms:contentKeyID: 49733695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eff8985832d9bb6e8aa4e06b777944417c7b8bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>Lync Server 2013에서 CDR 구성 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

CDR(통화 정보 기록)을 사용하면 피어 투 피어 인스턴트 메시징 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.

Microsoft Lync Server 2013을 설치 하면 CDR 구성 설정의 단일 전역 모음이 만들어집니다. 관리자는 또한 개별 사이트에 적용할 수 있는 사용자 지정 설정 컬렉션을 만들 수 있습니다. Lync Server 제어판 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet을 사용 하 여 조직에서 사용 중인 CDR 구성 설정을 볼 수 있습니다.

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 CDR 구성 정보를 보려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.

2.  모든 CDR 구성 설정에 대한 목록은 **통화 정보 기록** 탭에 표시됩니다. 설정의 각 컬렉션에 대해 컬렉션 **이름**이 표시되고, CDR이 설정되었는지 여부(**CDR** 속성), 삭제가 설정되었는지 여부(**CDR 삭제** 속성)가 표시됩니다. 컬렉션에 대한 자세한 내용을 보려면 해당 컬렉션을 두 번 클릭하거나 적합한 컬렉션을 선택하고, **편집**을 클릭한 후 **세부 정보 표시**를 클릭합니다. CDR 구성 설정은 한 번에 하나의 단일 컬렉션에 대한 자세한 정보만 확인할 수 있습니다.

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 정보 보기

Windows PowerShell 및 Get-cscdrconfiguration cmdlet을 사용 하 여 CDR 구성 설정을 볼 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-cdr-configuration-information"></a>CDR 구성 정보를 보려면

  - 모든 CDR 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsCdrConfiguration
    
    그러면 다음과 같은 정보가 반환됩니다.
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

자세한 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

