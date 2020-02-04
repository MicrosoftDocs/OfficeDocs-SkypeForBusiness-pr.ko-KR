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
ms.openlocfilehash: f13bbc63d65786823ae49895358216a903878192
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-cdr-configuration-information-in-lync-server-2013"></a>Lync Server 2013에서 CDR 구성 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.

Microsoft Lync Server 2013을 설치 하면 사용자를 위해 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다. 또한 관리자는 개별 사이트에 적용할 수 있는 사용자 지정 설정 모음을 만드는 옵션도 있습니다. Lync Server 제어판 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) cmdlet을 사용 하 여 조직에서 사용 중인 CDR 구성 설정을 볼 수 있습니다.

<div>

## <a name="to-view-cdr-configuration-information-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 CDR 구성 정보를 보려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.

2.  모든 CDR 구성 설정 목록은 **통화 정보 기록** 탭에 표시 됩니다. 각 설정 컬렉션에 대해 컬렉션 **이름이**표시 됩니다. CDR가 사용 하도록 설정 되었는지 여부 ( **cdr** 속성) ( **CDR 지우기** 속성)를 사용 하 여 제거 여부를 지정 합니다. 컬렉션에 대 한 자세한 정보를 보려면 모음을 두 번 클릭 하거나 해당 모음을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다. 한 번에 CDR 구성 설정의 단일 컬렉션에 대 한 자세한 정보만 볼 수 있습니다.

</div>

<div>

## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 정보 보기

Windows PowerShell 및 CsCdrConfiguration cmdlet을 사용 하 여 CDR 구성 설정을 볼 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-cdr-configuration-information"></a>CDR 구성 정보를 보려면

  - 모든 CDR 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsCdrConfiguration
    
    이는 다음과 같은 정보를 반환 합니다.
    
        Identity               : Global
        EnableCDR              : True
        EnablePurging          : True
        KeepCallDetailForDays  : 90
        KeepErrorReportForDays : 60
        PurgeHourOfDay         : 2

</div>

자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration) 을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

