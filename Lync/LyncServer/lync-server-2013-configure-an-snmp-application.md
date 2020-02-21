---
title: 'Lync Server 2013: SNMP 응용 프로그램 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252b6ec99d19b88259aacc2fc5681b585ae1bef2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Lync Server 2013에서 SNMP 응용 프로그램 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

Lync Server 2013에는 위치 정보 서비스를 포트 및 스위치 정보와 MAC 주소와 일치 하는 SNMP (Simple Network Management Protocol) 응용 프로그램에 연결 하는 데 사용할 수 있는 표준 웹 서비스 인터페이스가 포함 되어 있습니다.

SNMP 응용 프로그램을 설치 하 고 위치 정보 서비스가 위치 데이터베이스에서 일치 하는 항목을 찾지 못하는 경우 위치 정보 서비스는 클라이언트에서 제공 하는 MAC 주소를 사용 하 여 응용 프로그램을 자동으로 쿼리 합니다. 그런 다음 위치 정보 서비스는 SNMP 응용 프로그램에서 반환 하는 포트 및 스위치 정보를 사용 하 여 위치 데이터베이스를 다시 쿼리 합니다.

자세한 내용은 [set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)를 참조 하십시오.

<div>


> [!NOTE]  
> Windows 8을 실행 하는 컴퓨터에서는 MAC 주소를 사용할 수 없습니다.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>SNMP 응용 프로그램 URL을 구성하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  다음 cmdlet를 실행하여 SNMP 응용 프로그램에 대한 URL을 구성합니다.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

