---
title: 'Lync Server 2013: Kerberos 계정 할당 보고'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9576d772aa340e7d578186974fb00418479ea691
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Lync Server 2013에서 Kerberos 계정 할당 보고

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-01-16_

이 절차를 성공적으로 완료하려면 RTCUniversalServerAdmins 그룹의 구성원인 사용자로 로그온해야 합니다.

**Get-CsKerberosAccountAssignment** cmdlet을 사용하여 Kerberos 인증 계정 지정에 대한 정보를 쿼리하고 배포의 현재 지정에 대한 정보를 보고할 수 있습니다.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>사이트에 대한 Kerberos 인증 계정 지정을 쿼리하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013 또는 관리 도구가 설치 된 컴퓨터에 있는 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령줄에서 다음 명령 중 하나를 실행합니다.
    
      - 조직의 모든 Kerberos 인증 계정 지정을 쿼리하고 각 계정에 대한 지정 정보를 반환하려면 매개 변수 없이 cmdlet을 실행합니다.
        
            Get-CsKerberosAccountAssignment
    
      - 배포의 모든 Kerberos 인증 계정 지정을 쿼리하고 각 계정에 대한 사이트 지정 정보를 반환하려면 ID 매개 변수를 사용하여 cmdlet을 실행합니다.
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        예:
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 단일 사이트의 모든 Kerberos 인증 계정 지정을 쿼리하고 각 계정에 대한 지정 정보를 반환하려면 필터 매개 변수를 사용하여 cmdlet을 실행합니다.
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        예:
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > 필터 매개 변수에 대해 *SiteName을 지정하면 사이트 식별자에서 임의의 위치에 지정한 사이트 이름이 포함된 모든 사이트(예: 사이트 식별자에 Redmond 문자열이 포함된 모든 사이트)에 대한 정보가 반환됩니다.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

