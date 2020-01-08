---
title: 'Lync Server 2013: 마이그레이션된 사용자 롤백'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57462cee6c4996f0beb51290f8382a1736d3e635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Lync Server 2013에서 마이그레이션된 사용자 롤백

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-07_

통합 된 대화 상대 저장소 기능을 롤백해야 하는 경우 사용자를 Exchange 2010 또는 Lync Server 2010로 다시 이동 하는 경우에만 연락처를 롤백합니다. 롤백하려면 사용자에 대해 정책을 사용 하지 않도록 설정한 다음 **CsUcsRollback** cmdlet을 실행 합니다. 정책을 사용 하지 않도록 설정 하면 통합 된 대화 상대 저장소 마이그레이션이 다시 시작 되기 때문에 **CsUcsRollback** 단독으로 실행 하는 것 만으로는 영구 롤백을 보장할 수 없습니다. 예를 들어 Exchange 2013이 Exchange 2010로 롤백 된 후 사용자의 사서함이 Exchange 2013로 이동 하는 경우, 통합 된 대화 상대 저장소를 사용 하는 한, 통합 대화 저장소 마이그레이션이 롤백 후 7 일이 지난 후에 다시 시작 됩니다. 사용자 서비스 정책에서 계속 해 서 사용자에 게 사용 하도록 설정 되어 있습니다.

<div>


> [!IMPORTANT]  
> <STRONG>이동-csuser</STRONG> cmdlet은 다음과 같은 경우에 Exchange 2013에서 Lync Server 2013로 사용자의 연락처 저장소를 자동으로 롤백합니다. 
> <UL>
> <LI>
> <P>사용자가 Lync Server 2013에서 Lync Server 2010로 이동 하는 경우</P>
> <LI>
> <P>사용자가 Lync Online에서 Lync Server 2013 온-프레미스로 이동 하는 경우와 같이 사용자가 교차를 마이그레이션한 경우 또는 그 반대의 경우입니다.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 백업 데이터베이스에서 통합 된 연락처 저장소 데이터를 가져오면 통합 된 대화 상대 저장소 모드가 내보내기와 가져오기 간에 변경 된 경우 사용자 데이터가 손상 될 수 있습니다. 예를 들면 다음과 같습니다. 
> <UL>
> <LI>
> <P>사용자의 연락처가 Exchange 2013으로 마이그레이션될 때까지 연락처 목록을 내보낸 다음 마이그레이션 후 동일한 데이터를 가져오면 통합 된 연락처 저장소 데이터와 연락처 목록이 손상 됩니다.</P>
> <LI>
> <P>사용자를 Exchange 2013으로 마이그레이션하고 마이그레이션을 마이그레이션한 다음 마이그레이션 후에 데이터를 가져오는 이유 때문에 통합 된 연락처 저장소 데이터와 연락처 목록이 손상 될 수 있습니다.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Exchange 사서함을 exchange 2013에서 Exchange 2010로 이동 하기 전에 먼저 exchange 관리자가 Lync server 관리자가 lync server 사용자 연락처를 Exchange 2013에서 Lync Server로 롤백하는 지 확인 해야 합니다. 통합 된 대화 상대 저장소 연락처를 Lync Server로 롤백하려면이 섹션의 뒷부분에 있는 "Exchange 2013에서 Lync Server 2013로 통합 된 대화 상대 저장소를 롤백하는 방법" 절차를 참조 하세요.



</div>

다음 절차에서는 사용자 대화 상대를 롤백하는 방법을 설명 합니다. Lync Server 2013 및 Lync Server 2010 간에 사용자를 이동 하기 위해 **move-csuser** cmdlet을 사용 하는 경우이 단계를 건너뛸 수 있습니다. **csuser** Cmdlet이 사용자를 Lync Server 2013에서 lync server 2010로 이동할 때 자동으로 연결 되는 대화 상대 저장소를 전환 합니다. **이동-CsUser** 는 통합 된 대화 상대 저장소 정책을 사용 하지 않도록 설정 하지 않으므로 사용자가 다시 Lync Server 2013로 이동 하면 통합 된 대화 상대 저장소에 대 한 마이그레이션이 되풀이 됩니다.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Lync Server 2013에서 Lync Server 2010로 사용자 연락처를 롤백하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  롤백 후 다시 마이그레이션되지 않도록 사용자의 통합 된 대화 상대 저장소를 롤백할 수 없도록 설정 합니다. (이 단계는 앞으로 사용자가 remigrate 되지 않도록 하려는 경우에만 수행). 개별 사용자에 대해 통합 된 연락처 저장소를 사용 하지 않도록 설정 하려면 명령줄에 다음을 입력 합니다.
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    예를 들면 다음과 같습니다.
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  사용자를 Lync Server 2013에서 Lync Server 2010로 이동 하기 전에 Lync Server에서 지정 된 사용자에 대 한 버디 목록을 롤백합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이 단계를 생략 하면 친구 목록이 손실 됩니다.

    
    </div>

4.  지정 된 사용자를 롤백합니다. 명령줄에 다음을 입력 합니다.
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    예를 들면 다음과 같습니다.
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 롤백 기능을 강제 하려면 – Force 옵션을 사용 하지 않는 것이 좋습니다. 이 옵션을 사용 하면 사용자의 연락처가 손실 됩니다.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Exchange 2013에서 Lync Server 2013로 통합 된 대화 상대 저장소를 롤백하는 방법

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  롤백 후 다시 마이그레이션되지 않도록 사용자의 통합 된 대화 상대 저장소를 롤백할 수 없도록 설정 합니다. 개별 사용자에 대해 통합 된 연락처 저장소를 사용 하지 않도록 설정 하려면 명령줄에 다음을 입력 합니다.
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    예를 들면 다음과 같습니다.
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  지정 된 사용자를 롤백합니다. 명령줄에 다음을 입력 합니다.
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    예를 들면 다음과 같습니다.
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 먼저 Lync Server 사용자를 롤백하고 Exchange 2013 사서함을 이동 해야 합니다. Lync Server 롤백이 완료 될 때까지 Exchange 관리자가 Exchange를 롤백할 수 없도록 차단 됩니다. 롤백 기능을 강제 하려면 – Force 옵션을 사용 하지 않는 것이 좋습니다. 이 옵션을 사용 하면 사용자의 연락처가 손실 됩니다.

    
    </div>

4.  사용자를 Lync Server로 롤백하는 경우 exchange 관리자는 exchange 2013에서 exchange 2010로 Exchange 사용자를 롤백할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

