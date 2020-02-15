---
title: Exchange 2013 Outlook Web App 및 IM 통합 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a67dd3c18525d7a39678b5871d087ea79c502fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Exchange 2013 Outlook Web App 및 IM 통합 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

Lync Server 2013과의 Exchange 2013 OWA (Outlook Web Access) 및 IM (인스턴트 메시징) 통합을 사용 하도록 설정 하려면 2013 Exchange 클라이언트 액세스 서버 (CAS) 서버를 Lync Server 2013 topology에 트러스트 된 응용 프로그램 서버로 추가 해야 합니다.

<div>

## <a name="to-create-a-trusted-application-pool"></a>트러스트된 응용 프로그램 풀을 만들려면

1.  Lync Server 2013 관리 셸을 시작 합니다.

2.  다음 cmdlet을 실행합니다.
    
        Get-CsSite
    
    그러면 풀을 만들려는 siteName의 siteID가 반환됩니다. 자세한 내용은 Lync Server 2013 관리 셸 설명서의 [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 를 참조 하십시오.

3.  다음 cmdlet을 실행합니다.
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    자세한 내용은 Lync Server 2013 관리 셸 설명서의 [new-cstrustedapplicationpool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 를 참조 하십시오.
    
    Exchange Server FQDN은 Exchange OWA 인증서 SN(주체 이름) 또는 SAN(주체 대체 이름)으로 구성되어야 합니다.
    
    Exchange OWA에서 풀의 FQDN도 신뢰할 수 있는지 확인합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > CAS 서버가 Exchange 2013 UM (통합 메시징)을 실행 하는 동일한 서버에 배치 된 <EM>되지 않은</EM> 경우이 절차의 나머지 단계를 건너뛰고이 항목 뒷부분에 나오는 "EXCHANGE 2013 CAS 서버에 대 한 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 합니다. CAS 서버가 Exchange 2013 UM (통합 메시징)을 실행 하는 동일한 서버에 배치 된 경우이 절차의 단계를 완료 하 고이 항목 뒷부분에 나오는 "Exchange 2013 CAS 서버에 대해 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 하지 마십시오.

    
    </div>

4.  **Enable-CsTopology**를 실행합니다.

5.  토폴로지 작성기를 열고 기존 토폴로지를 다운로드합니다.

6.  왼쪽 창에서 **트러스트된 응용 프로그램 서버**가 표시될 때까지 트리를 확장합니다.

7.  **신뢰할 수 있는 응용 프로그램 서버** 노드를 확장합니다.

8.  이제 Exchange 2013 CAS 서버가 신뢰할 수 있는 응용 프로그램 서버로 나열 됩니다.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Exchange 2013 CAS 서버에 대해 신뢰할 수 있는 응용 프로그램을 만들려면

1.  Lync Server 2013 관리 셸을 시작 합니다.

2.  CAS 서버가 Exchange 2013 UM (통합 메시징)을 실행 하는 동일한 서버에 배치 된 *되지 않은* 경우 다음 cmdlet을 실행 합니다.
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    자세한 내용은 Lync Server 2013 관리 셸 설명서의 [new-cstrustedapplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 항목을 참조 하십시오.

3.  **Enable-CsTopology**를 실행합니다.

4.  토폴로지 작성기의 왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**가 표시될 때까지 트리를 확장합니다.

5.  **신뢰할 수 있는 응용 프로그램 서버** 노드를 확장합니다.

6.  이제 Exchange 2013 CAS 서버가 신뢰할 수 있는 응용 프로그램 서버로 나열 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

