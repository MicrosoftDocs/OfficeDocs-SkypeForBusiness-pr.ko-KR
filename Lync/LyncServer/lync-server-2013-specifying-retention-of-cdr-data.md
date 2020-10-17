---
title: 'Lync Server 2013: CDR 데이터 보존 지정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc5d09e2ebb417f801ddab3f7fb8f444957e9d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519565"
---
# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>Lync Server 2013에서 CDR 데이터 보존 지정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

기본적으로 CDR(통화 정보 기록) 데이트는 60일 이후에 삭제됩니다. **통화 정보 기록** 페이지의 설정을 사용하여 데이터를 60일 이상 보존하거나 60일보다 짧게 보존할 수 있습니다. CDR을 사용하지 않도록 설정한 경우 CDR을 사용하도록 설정하기 전에 캡처한 데이터도 삭제됩니다.

<div>


> [!NOTE]  
> CDR 및 QoE(체감 품질)의 데이터 보존 일수는 동일하게 구성해야 합니다. 모니터링 서버 보고서 홈 페이지에 있는 CDR(통화 정보 보고서)의 각 통화에는 CDR 및 QoE 정보가 포함됩니다. CDR 및 QoE의 삭제 기간이 다를 경우 일부 통화에는 CDR 데이터만 포함되고 또 다른 일부 통화에는 QoE 데이터만 포함될 수 있습니다.



</div>

CDR 데이터에 대한 삭제 설정을 구성하려면 다음 절차를 따릅니다.

<div>

## <a name="to-specify-retention-of-cdr-data"></a>CDR 데이터 보존 기간을 지정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **통화 정보 기록**을 클릭합니다.

4.  **통화 정보 기록** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.

5.  삭제를 설정하려면 **CDR(통화 정보 기록) 삭제 사용**을 선택합니다.

6.  **최대 기간(일) 동안 통화 정보 기록 유지:** 에서 통화 정보 기록을 보존할 최대 일수를 선택합니다.

7.  **최대 기간(일) 동안 오류 보고서 데이터 유지:** 에서 오류 보고서를 보존할 최대 일수를 선택합니다.

8.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 CDR 보존 지정

Windows PowerShell 및 Set-CsCdrConfiguration cmdlet을 사용하여 CDR 보존 설정을 만들 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>특정 위치에 대한 CDR 보존을 지정하려면

  - 이 명령은 Redmond 사이트에 대해 CDR 데이터 삭제를 사용하도록 설정하고 20일 동안 CDR 데이터 및 오류 보고서 데이터를 유지하도록 구성합니다.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>여러 위치에 대한 CDR 보존을 지정하려면

  - 이 명령은 조직에서 사용 중인 모든 CDR 구성 설정에 대해 CDR 보존을 구성합니다.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

자세한 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 CDR (통화 정보 기록)](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

