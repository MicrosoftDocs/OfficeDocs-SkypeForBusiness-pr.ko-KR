---
title: Exchange 2013 Outlook Web App 및 IM 통합 기능 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69df3f33f0671d3014e90859fd39cc2b85f9558b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Exchange 2013 Outlook Web App 및 IM 통합 기능 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

Lync Server 2013와 함께 Exchange 2013 OWA (Outlook Web Access) 및 IM (인스턴트 메시징) 통합을 사용 하도록 설정 하려면 2013 Exchange 클라이언트 액세스 서버 (CAS) 서버를 Lync Server 2013 토폴로지에 신뢰할 수 있는 응용 프로그램 서버로 추가 해야 합니다.

<div>

## <a name="to-create-a-trusted-application-pool"></a>신뢰할 수 있는 응용 프로그램 풀 만들기

1.  Lync Server 2013 관리 셸을 시작 합니다.

2.  다음 cmdlet을 실행 합니다.
    
        Get-CsSite
    
    이는 풀을 만들고 있는 siteName에 대 한 siteID를 반환 합니다. 자세한 내용은 Lync Server 2013 관리 셸 설명서에서 [Get CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 를 참조 하세요.

3.  다음 cmdlet을 실행 합니다.
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    자세한 내용은 Lync Server 2013 관리 셸 설명서의 [CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 을 참조 하세요.
    
    Exchange Server FQDN은 Exchange OWA 인증서 주체 이름 (SN) 또는 주체 대체 이름 (SAN)으로 구성 되어야 합니다.
    
    Exchange OWA에서 풀의 FQDN도 신뢰할 수 있는지 확인 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > CAS 서버가 Exchange 2013 UM (통합 메시징)를 실행 하는 동일한 서버에 collocated <EM>되지 않은</EM> 경우이 절차의 나머지 단계를 건너뛰고이 항목의 뒷부분에 나오는 "EXCHANGE 2013 CAS 서버용 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 합니다. CAS 서버가 Exchange 2013 UM (통합 메시징)를 실행 하는 동일한 서버에 collocated이 절차의 단계를 완료 하 고이 항목의 뒷부분에 나오는 "Exchange 2013 CAS 서버용 신뢰할 수 있는 응용 프로그램 만들기" 절차를 수행 하지 않습니다.

    
    </div>

4.  **Enable-CsTopology**을 실행 합니다.

5.  토폴로지 작성기를 열고 기존 토폴로지를 다운로드 합니다.

6.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**에 도달할 때까지 트리를 확장 합니다.

7.  **신뢰할 수 있는 응용 프로그램 서버** 노드를 확장 합니다.

8.  이제 신뢰할 수 있는 응용 프로그램 서버로 나열 된 Exchange 2013 CAS 서버가 표시 됩니다.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Exchange 2013 CAS 서버에 대 한 신뢰할 수 있는 응용 프로그램을 만들려면

1.  Lync Server 2013 관리 셸을 시작 합니다.

2.  CAS 서버가 Exchange 2013 UM (통합 메시징)를 실행 하는 동일한 서버에 collocated *있지 않은* 경우 다음 cmdlet을 실행 합니다.
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    자세한 내용은 Lync Server 2013 관리 셸 설명서의 [New CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 항목을 참조 하세요.

3.  **Enable-CsTopology**을 실행 합니다.

4.  토폴로지 작성기의 왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**에 도달할 때까지 트리를 확장 합니다.

5.  **신뢰할 수 있는 응용 프로그램 서버** 노드를 확장 합니다.

6.  이제 신뢰할 수 있는 응용 프로그램 서버로 나열 된 Exchange 2013 CAS 서버가 표시 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

