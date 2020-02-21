---
title: 'Lync Server 2013: 마이그레이션된 사용자 롤백'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05678690718563dac9187ee275d3809016b78d33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Lync Server 2013에서 마이그레이션된 사용자 롤백

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-07_

통합 연락처 저장소 기능을 롤백해야 하는 경우 사용자를 다시 Exchange 2010 또는 Lync Server 2010로 이동 하는 경우에만 연락처를 롤백합니다. 롤백하려면 사용자에 대 한 정책을 사용 하지 않도록 설정한 다음 **invoke-csucsrollback** cmdlet을 실행 합니다. 정책이 사용 하지 않도록 설정 되어 있지 않은 경우 통합 된 연락처 저장소 마이그레이션은 다시 시작 되므로, **invoke-csucsrollback** 단독으로 실행 하는 것 만으로는 영구 롤백을 보장할 수 없습니다. 예를 들어 Exchange 2013이 exchange 2010로 롤백 되 고 사용자의 사서함이 Exchange 2013로 이동 된 경우 통합 연락처 저장소 마이그레이션은 통합 연락처 저장소 보다 7 일 후에 다시 시작 됩니다. 은 사용자 서비스 정책에서 해당 사용자에 대해 계속 사용 하도록 설정 되어 있습니다.

<div>


> [!IMPORTANT]  
> 다음 경우에는 <STRONG>csuser</STRONG> p s i c s i c s i c e r t s e r t 사용자의 연락처 저장소가 Exchange 2013에서 Lync Server 2013로 자동 롤백됩니다. 
> <UL>
> <LI>
> <P>사용자가 Lync Server 2013에서 Lync Server 2010로 이동 하는 경우</P>
> <LI>
> <P>사용자가 Lync Online에서 Lync Server 2013 온-프레미스로 이동 하는 경우와 같이 사용자가 크로스 프레미스로 마이그레이션될 때 또는 그 반대의 경우입니다.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 백업 데이터베이스에서 통합 연락처 저장소 데이터를 가져올 경우 통합 연락처 저장소 모드가 내보내기와 가져오기 간에 변경되면 통합 연락처 저장소 데이터 및 사용자 데이터가 손상될 수 있습니다. 예를 들면 다음과 같습니다. 
> <UL>
> <LI>
> <P>사용자의 대화 상대가 Exchange 2013로 마이그레이션될 때까지 연락처 목록을 내보낸 다음, 마이그레이션 후 같은 데이터를 가져오면 통합 연락처 저장소 데이터 및 연락처 목록이 손상 됩니다.</P>
> <LI>
> <P>사용자를 Exchange 2013로 마이그레이션하고 마이그레이션 후 마이그레이션을 롤백하는 경우, 마이그레이션 후 데이터를 가져오는 몇 가지 이유로 인해 통합 연락처 저장소 데이터 및 연락처 목록이 손상 됩니다.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Exchange 사서함을 Exchange 2013에서 Exchange 2010로 이동 하기 전에 먼저 Exchange 관리자가 lync server 사용자 연락처를 Exchange 2013에서 Lync Server로 롤백 했는지 확인 해야 합니다. 통합 연락처 저장소 연락처를 Lync Server로 롤백하려면이 섹션의 뒷부분에 나오는 "Exchange 2013에서 통합 연락처 저장소를 Lync Server 2013로 롤백하는 방법" 절차를 참조 하십시오.



</div>

다음 절차에서는 사용자 연락처를 롤백하는 방법을 설명 합니다. 온 **-CsUser** cmdlet을 사용 하 여 lync server 2013와 lync server 2010 간에 사용자를 이동 하는 경우, 사용자 이동 **-csuser** cmdlet은 Lync Server 2013에서 lync server 2010로 이동할 때 공동 작업 연락처 저장소가 자동으로 롤백하여 이러한 단계를 건너뛸 수 있습니다. **이동-CsUser** 는 통합 연락처 저장소 정책을 사용 하지 않도록 설정 하지 않으므로 사용자가 다시 Lync Server 2013로 이동 하는 경우 통합 연락처 저장소로의 마이그레이션이 반복 됩니다.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>Lync Server 2013에서 Lync Server 2010로 사용자 연락처를 롤백하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  사용자가 롤백 후 다시 마이그레이션되지 않도록, 롤백할 사용자의 통합 연락처 저장소를 사용하지 않도록 설정합니다. 이후에 사용자가 다시 마이그레이션되지 않도록 하려는 경우에만 이 단계를 수행합니다. 개별 사용자의 통합 연락처 저장소를 사용하지 않도록 설정하려면 명령줄에 다음을 입력합니다.
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    예:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Lync server 2013에서 Lync Server 2010로 사용자를 이동 하기 전에 Lync Server에서 지정 된 사용자에 대 한 버디 목록을 롤백합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이 단계를 생략할 경우 대화 상대 목록이 손실됩니다.

    
    </div>

4.  명령줄에 다음을 입력하여 지정된 사용자를 롤백합니다.
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    예:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > -Force 옵션을 사용하여 강제로 롤백하는 것은 좋지 않습니다. 이 옵션을 사용할 경우 사용자의 대화 상대가 손실됩니다.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>Exchange 2013에서 Lync Server 2013로 통합 연락처 저장소 연락처를 롤백하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  사용자가 롤백 후 다시 마이그레이션되지 않도록, 롤백할 사용자의 통합 연락처 저장소를 사용하지 않도록 설정합니다. 개별 사용자의 통합 연락처 저장소를 사용하지 않도록 설정하려면 명령줄에 다음을 입력합니다.
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    예를 들면 다음과 같습니다.
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  명령줄에 다음을 입력하여 지정된 사용자를 롤백합니다.
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    예:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 먼저 Lync Server 사용자를 롤백하여 Exchange 2013 사서함을 이동 해야 합니다. Lync Server 롤백이 완료 될 때까지 Exchange 관리자는 Exchange를 롤백할 수 없도록 차단 됩니다. -Force 옵션을 사용하여 강제로 롤백하는 것은 좋지 않습니다. 이 옵션을 사용할 경우 사용자의 대화 상대가 손실됩니다.

    
    </div>

4.  사용자를 Lync Server로 롤백하 고 나면 exchange 관리자가 exchange 사용자에서 exchange 2013 2010로 exchange를 롤백할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

