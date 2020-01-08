---
title: Exchange 통합 메시징 연락처 개체 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Exchange 통합 메시징 연락처 개체 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

자동 전화 교환 (AA) 및 SA (구독자 액세스) 연락처 개체를 새 Lync Server 2013 배포로 마이그레이션하려면 먼저 레거시 Office Communications Server 2007 R2 배포의 개체를 **Get-c고** umcontact 및 **Move-csexumcontact** cmdlet을 사용 하 여 Lync Server 2013 배포로 이동 합니다. Exchange 서버에서 **ExchUCUtil** Windows PowerShell 스크립트를 실행 하 여 새로 배포 된 Lync 풀에 대해 다음을 수행 합니다.

  - 통합 메시징 IP 게이트웨이에 추가 합니다.

  - 통합 메시징 헌트 그룹에 추가 합니다.

<div>


> [!NOTE]  
> <STRONG>Get-help</STRONG> 또는 <STRONG>Move-c고 umcontact</STRONG> Cmdlet을 사용 하려면 RTCUniversalUserAdmins 그룹의 구성원 이며 연락처 개체가 저장 된 OU에 대 한 ou (조직 구성 단위) 권한이 있어야 합니다. OU 권한은 <STRONG>부여-oupermission</STRONG> cmdlet을 사용 하 여 부여할 수 있습니다.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 연락처 개체 이동

1.  Lync Server 관리 셸을 엽니다.

2.  Exchange UM을 사용 하 여 등록 된 각 풀 (pool1.contoso.net는 Office Communications Server 2007 R2 배포의 풀이 고 pool2.contoso.net는 Lync Server 2013 배포의 풀 인 경우) 명령줄에 다음을 입력 합니다.
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    연락처 개체가 이동 되었는지 확인 하려면 **Get-CRegistrarPool Umcontact** cmdlet을 실행 하 고 현재 새 풀을 **가리키고 있는지 확인** 합니다.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>ExchUCUtil Windows PowerShell 스크립트를 실행 하려면

1.  Exchange 조직 관리자 권한이 있는 사용자로 Exchange UM 서버에 로그온 합니다.

2.  ExchUCUtil Windows PowerShell 스크립트로 이동 합니다.
    
    Exchange 2007에서 ExchUCUtil는 다음 위치에 있습니다: **% Program Files%\\Microsoft\\Exchange Server\\스크립트\\ExchUCUtil. ps1**
    
    Exchange 2010에서 ExchUCUtil는 다음 위치에 있습니다: **\\% Program Files% Microsoft\\Exchange Server\\V14\\스크립트\\ExchUCUtil. ps1**

3.  Exchange를 단일 포리스트에 배포 하는 경우 다음을 입력 합니다.
    
        exchucutil.ps1
    
    또는 Exchange가 여러 포리스트에 배포 된 경우 다음을 입력 합니다.
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    여기서 포리스트 FQDN은 Lync Server 2013을 배포 하는 포리스트를 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Exchucutil를 실행 <EM>한 후</EM> <STRONG>Lync Server 프런트 엔드</STRONG> 서비스 (rtcsrv)를 다시 시작 해야 합니다. 그렇지 않으면 Lync Server 2013이 토폴로지에서 통합 메시징을 검색 하지 않습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

