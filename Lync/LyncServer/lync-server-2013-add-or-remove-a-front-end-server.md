---
title: 'Lync Server 2013: 프런트 엔드 서버 추가 또는 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Lync Server 2013에서 프런트 엔드 서버 추가 또는 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-01-21_

풀에 프런트 엔드 서버를 추가 하거나 풀에서 프런트 엔드 서버를 제거 하는 경우에는 풀을 다시 시작 해야 합니다. 사용자에 대 한 서비스 중단을 방지 하려면 프런트 엔드 서버를 추가 하거나 제거할 때 다음 절차를 사용 합니다.

<div>


> [!NOTE]  
> 풀에 새 서버를 추가 하는 경우 새 풀 서버를 풀의 기존 서버와 동일한 누적 업데이트 수준으로 업데이트 합니다.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>프런트 엔드 서버를 추가 하거나 제거 하려면

1.  프런트 엔드 서버를 제거 하는 경우 먼저 해당 서버에 대 한 새 연결을 중지 합니다. 이렇게 하려면 다음 cmdlet을 사용 하면 됩니다.
    
        Stop-CsWindowsServices -Graceful

2.  제거할 서버에 현재 세션이 없는 경우에는 Lync Server 서비스를 중지 합니다.

3.  토폴로지 작성기를 열고 필요한 서버를 추가 또는 제거 합니다.

4.  토폴로지를 게시 합니다.

5.  풀의 프런트 엔드 서버를 2 개 이상으로 유지 하거나, 두 개 이상의 서버에서 정확히 2 개에 이르기까지 다음 cmdlet을 입력 해야 합니다.
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    풀에 서버가 세 대 이상 있는 경우이 cmdlet을 입력할 때 세 개 이상의 서버가 실행 중 이어야 합니다.

6.  풀의 모든 프런트 엔드 서버를 한 번에 하나씩 다시 시작 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

