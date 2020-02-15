---
title: 'Lync Server 2013: 가상 트랜잭션 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 448e96c03b554970b1ee92166908965ee2a6629c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013에서 가상 트랜잭션 실행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-08-18_

가상 트랜잭션은 일반적으로 두 가지 방식으로 수행 됩니다. Get-cshealthmonitoringconfiguration cmdlet을 사용 하 여 각 등록자 풀에 대해 테스트 사용자를 설정할 수 있습니다. 이러한 테스트 사용자는 가상 트랜잭션과 함께 사용 하도록 미리 구성 된 사용자 쌍입니다. 일반적으로 테스트 계정이 며 실제 사용자에 게 속하는 계정이 아닙니다. 풀에 대해 구성 된 테스트 사용자를 사용 하 여 테스트에 포함 된 사용자 계정에 대 한 id를 지정 하지 않고도 해당 풀에 대해 가상 트랜잭션을 실행할 수 있습니다.

또는 실제 사용자 계정을 사용 하 여 가상 트랜잭션을 실행할 수 있습니다. 예를 들어 두 명의 사용자가 인스턴트 메시지를 교환할 수 없는 경우 테스트 계정 쌍 대신 이러한 두 사용자 계정을 사용 하 여 가상 트랜잭션을 실행 한 다음 문제를 진단 하 고 해결 해 볼 수 있습니다. 실제 사용자 계정을 사용 하 여 가상 트랜잭션을 수행 하기로 결정 한 경우 각 사용자에 대 한 로그온 이름과 암호를 제공 해야 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 감시자 노드 테스트 사용자 및 구성 설정 구성](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Lync Server 2013의 가상 트랜잭션에 대 한 특별 설치 지침](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

