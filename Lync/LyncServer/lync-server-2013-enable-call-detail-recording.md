---
title: 'Lync Server 2013: 통화 정보 기록 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b033827600fc962ab5ea9df5c8848ed1533c75e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a>Lync Server 2013에서 통화 정보 기록 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

CDR (통화 정보 기록)는 인스턴스 메시징, VoIP (Voice over 인터넷 프로토콜) 통화, 응용 프로그램 공유, 파일 전송, 모임 등 피어 투 피어 활동에 대 한 사용 및 진단 정보를 기록 합니다. 사용 현황 데이터는 ROI (투자 수익률)를 계산 하는 데 사용할 수 있으며, 진단 데이터를 사용 하 여 피어 투 피어 활동 및 모임 문제를 해결할 수 있습니다.

조직의 전체 조직 또는 각 사이트에 대해 CDR를 사용 하도록 설정 하려면 다음 절차를 사용 합니다.

<div>


> [!NOTE]  
> CDR를 사용 하려면 모니터링과 모니터링 데이터베이스를 구성 해야 합니다. 자세한 내용은 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013에서 모니터링 배포</A>를 참조 하세요.



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a>Lync Server 제어판에서 CDR를 사용 하도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.

4.  **통화 정보 기록** 페이지의 표에서 해당 사이트를 클릭 하 고 **작업**을 클릭 한 다음 **CDR 사용**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > CDR는 기본적으로 사용 하도록 설정 되어 있습니다.

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 사용

Windows PowerShell 및 **Set-CsCdrConfiguration** cmdlet을 사용 하 여 CDR를 사용 하도록 설정할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-cdr-for-a-single-location"></a>단일 위치에 대해 CDR를 사용 하도록 설정 하려면

  - CDR를 사용 하지 않으려면 EnableCDR 매개 변수를 True ($True)로 설정 합니다.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a>단일 위치에 대해 CDR를 사용 하지 않도록 설정 하려면

  - CDR를 사용 하지 않으려면 EnableCDR 매개 변수를 False ($False)로 설정 합니다. CDR를 사용 하지 않도록 설정 하면 모니터링이 제거 되지 않습니다. 이 메서드는 CDR 데이터의 수집 및 저장소를 일시 중지 합니다.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>단일 명령을 사용 하 여 여러 위치에서 CDR를 사용 하도록 설정 하려면

  - 이 명령은 현재 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR를 사용 하도록 설정 합니다.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

자세한 내용은 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 모니터링 계획](lync-server-2013-planning-for-monitoring.md)  
[Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

