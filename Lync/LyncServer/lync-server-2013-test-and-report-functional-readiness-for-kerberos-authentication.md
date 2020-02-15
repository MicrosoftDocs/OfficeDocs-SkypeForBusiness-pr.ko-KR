---
title: Kerberos 인증에 대 한 기능 준비 상태 테스트 및 보고
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 870c0e19e2134c1a827485a5cacf2c055f99b0d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Lync Server 2013에서 Kerberos 인증에 대 한 기능 준비 상태 테스트 및 보고

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-01-16_

이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.

**Get-cskerberosaccountassignment** Windows PowerShell cmdlet을 사용 하 여 Kerberos 인증에 대 한 사이트 할당의 기능 준비 상태를 테스트 하 고 보고할 수 있습니다. 이 명령은 필수 Identity 매개 변수에서 지정된 사이트를 쿼리합니다. Optional Report 매개 변수를 지정 하면 cmdlet이 명령이 실행 되는 컴퓨터의\\C: 로그에 HTML 보고서를 작성 합니다. 선택적 Verbose 매개 변수는 작업 정보를 화면에 보고합니다.

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>사이트에 대한 Kerberos 인증을 위해 기능 준비를 테스트 및 보고하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음 명령을 실행합니다.
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    예를 들면 다음과 같습니다.
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

