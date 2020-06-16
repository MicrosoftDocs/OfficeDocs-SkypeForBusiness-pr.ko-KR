---
title: Exchange 통합 메시징 대화 상대 개체 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b3091a342b46b5c1aad1d456aa9159d951a4ba
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>Exchange 통합 메시징 대화 상대 개체 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

자동 전화 교환 (AA) 및 SA (구독자 액세스) 연락처 개체를 새 Lync Server 2013 배포로 마이그레이션하려면 먼저 이전 Office Communications Server 2007 R2 배포의 개체를 **Get-csexumcontact** 및 **Move-csexumcontact** cmdlet을 사용 하 여 Lync Server 2013 배포로 이동 합니다. Exchange 서버에서 **Exchucutil.ps1** Windows PowerShell 스크립트를 실행 하 여 새로 배포 된 Lync 풀에 대해 다음을 수행 합니다.

  - Unified Messaging IP 게이트웨이에 개체 추가

  - Unified Messaging 헌트 그룹에 개체 추가

<div>


> [!NOTE]  
> In order to use the <STRONG>Get-CsExUmContact</STRONG> and <STRONG>Move-CsExUmContact</STRONG> cmdlets, you must be a member of the RTCUniversalUserAdmins group and have organizational unit (OU) permission to the OU where the contacts objects are stored. OU permission can be granted using the <STRONG>Grant-OUPermission</STRONG> cmdlet.



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>Lync Server 관리 셸을 사용하여 대화 상대 개체를 이동하려면

1.  Lync Server 관리 셸을 엽니다.

2.  Exchange UM에 등록 된 각 풀 (여기서 pool1.contoso.net은 Office Communications Server 2007 R2 배포의 풀이 고 pool2.contoso.net는 Lync Server 2013 배포의 풀)에 명령줄에서 다음을 입력 합니다.
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    대화 상대 개체가 이동되었는지 확인하려면 **Get-CsExumContact** cmdlet을 실행하고 **RegistrarPool**이 이제 새 풀을 가리키는지 확인합니다.

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>ExchUCUtil Windows PowerShell 스크립트를 실행하려면

1.  Exchange 조직 관리자 권한이 있는 사용자로 Exchange UM 서버에 로그온합니다.

2.  Exchucutil.ps1 Windows PowerShell 스크립트로 이동 합니다.
    
    Exchange 2007에서 ExchUCUtil.ps1는 **% Program Files% \\ Microsoft \\ Exchange Server \\ 스크립트 \\ ** 에 있습니다ExchUCUtil.ps1
    
    Exchange 2010에서 ExchUCUtil.ps1의 위치는 **% Program Files% \\ Microsoft \\ Exchange Server \\ v 14 \\ Scripts \\ExchUCUtil.ps1**

3.  Exchange가 단일 포리스트에 배포된 경우 다음을 입력합니다.
    
        exchucutil.ps1
    
    또는 Exchange가 여러 포리스트에 배포된 경우 다음을 입력합니다.
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    여기서 포리스트 FQDN은 Lync Server 2013이 배포 되는 포리스트를 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > exchucutil.ps1을 실행한 <EM>후</EM><STRONG>Lync Server 프런트 엔드</STRONG> 서비스(rtcsrv.exe)를 다시 시작해야 합니다. 그렇지 않으면 Lync Server 2013이 토폴로지에서 통합 메시징을 검색 하지 않습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

