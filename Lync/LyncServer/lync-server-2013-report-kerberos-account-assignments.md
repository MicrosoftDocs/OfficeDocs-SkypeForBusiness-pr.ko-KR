---
title: 'Lync Server 2013: Kerberos 계정 할당 보고'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b02eb3cae7a7d2bbeb4cc3b9dce0a7daa8ee5c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Lync Server 2013에서 Kerberos 계정 할당 보고

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-01-16_

이 절차를 성공적으로 완료 하려면 RTCUniversalServerAdmins 그룹의 구성원 인 사용자로 로그온 해야 합니다.

**Get-CsKerberosAccountAssignment** cmdlet을 사용 하 여 Kerberos 인증 계정 할당에 대 한 정보를 쿼리하고 배포의 현재 배정에 대 한 정보를 보고할 수 있습니다.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>사이트에 대 한 Kerberos 인증 계정 할당을 쿼리하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 Lync Server 2013를 실행 하는 도메인의 컴퓨터 또는 관리 도구가 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령줄에서 다음 명령 중 하나를 실행 합니다.
    
      - 조직에서 모든 Kerberos 인증 계정 과제를 쿼리하고 각각에 대 한 과제 정보를 반환 하려면 다음 매개 변수 없이 cmdlet을 실행 합니다.
        
            Get-CsKerberosAccountAssignment
    
      - 배포에서 모든 Kerberos 인증 계정 할당을 쿼리하고 각 사용자에 대 한 사이트 할당 정보를 반환 하려면 Id 매개 변수를 사용 하 여 cmdlet을 실행 합니다.
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        예를 들면 다음과 같습니다.
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - 모든 Kerberos 인증 계정 과제를 단일 사이트에 쿼리하여 각에 대 한 할당 정보를 반환 하려면 Filter 매개 변수를 사용 하 여 cmdlet을 실행 합니다.
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        예를 들면 다음과 같습니다.
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > * SiteName 필터 매개 변수를 지정 하면 사이트 식별자 (예: 사이트 식별자의 Redmond 문자열을 포함 하는 모든 사이트)에 지정 된 사이트 이름을 포함 하는 모든 사이트에 대 한 정보가 반환 됩니다.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

