---
title: 신뢰 된 서버 인증을 사용 하도록 감시자 노드 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6634fa55424190d2e0a05aece38d88977d2f6bca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a>신뢰할 수 있는 서버 인증을 사용 하도록 Lync Server 2013에서 감시자 노드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

감시자 노드 컴퓨터가 경계 네트워크 내에 있는 경우 신뢰할 수 있는 서버 인증을 사용 하면 수많은 사용자 계정 암호 보다는 단일 인증서를 유지 관리 하기 위해 관리자 세금이 대폭 감소 됩니다.

신뢰 된 서버 인증을 구성 하는 첫 번째 단계는 신뢰할 수 있는 응용 프로그램 풀을 만들어 감시자 노드 컴퓨터를 호스트 하는 것입니다. 신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 해당 감시자 노드에서 가상 트랜잭션을 구성 하 여 신뢰할 수 있는 응용 프로그램으로 실행 해야 합니다.

<div>


> [!NOTE]
> 신뢰할 수 있는 응용 프로그램은 Lync Server 2013의 일부로 실행할 신뢰할 수 있는 상태를 지정 하는 응용 프로그램 이지만 제품의 기본 제공 부분이 아닙니다. 신뢰할 수 있는 상태는 응용 프로그램이 실행 될 때마다 인증에 대해 challenge 되지 않는다는 것을 의미 합니다.



</div>

신뢰할 수 있는 응용 프로그램 풀을 만들려면 Lync Server 2013 관리 셸을 열고 다음과 같은 명령을 실행 합니다.

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> 앞의 명령에 사용 되는 매개 변수에 대 한 자세한 내용은 Lync Server Management Shell 프롬프트에서 다음을 입력 합니다.<BR>Get-help 신규-CsTrustedApplicationPool-Full | 자세한



</div>

신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 신뢰할 수 있는 응용 프로그램으로 가상 트랜잭션을 실행 하도록 감시자 노드 컴퓨터를 구성 합니다. 이 작업은 **CsTrustedApplication** cmdlet 및 다음과 유사한 명령을 사용 하 여 수행 됩니다.

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

앞의 명령이 완료 되 고 신뢰할 수 있는 응용 프로그램이 만들어졌으면 Enable-CsTopology를 실행 하 여 변경 내용이 적용 되었는지 확인 합니다.

    Enable-CsTopology

Enable-CsTopology을 실행 한 후 컴퓨터를 다시 시작 하는 것이 좋습니다.

신뢰할 수 있는 새 응용 프로그램이 만들어졌는지 확인 하려면 Lync Server 관리 셸 프롬프트에서 다음을 입력 합니다.

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a>감시자 노드에 대 한 기본 인증서 구성

각 감시자 노드에는 Lync Server 배포 마법사를 사용 하 여 할당 된 기본 인증서가 있어야 합니다.

**기본 인증서를 할당 하려면**

1.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **lync Server**를 클릭 하 고 **lync 서버 배포 마법사**를 클릭 합니다.

2.  Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트** 를 클릭 한 다음 제목 **요청, 설치 또는 인증서 지정**에서 **실행** 을 클릭 합니다.
    
    <div>
    

    > [!NOTE]
    > <STRONG>실행</STRONG> 단추를 사용할 수 없는 경우 먼저 <STRONG>로컬 구성 저장소 설치</STRONG>에서 <STRONG>실행</STRONG> 을 클릭 해야 할 수 있습니다.

    
    </div>

3.  다음 중 하나를 수행 합니다.
    
      - 기본 인증서로 사용할 수 있는 인증서가 이미 있는 경우 인증서 마법사에서 **기본값** 을 클릭 한 다음 **할당**을 클릭 합니다. 인증서 할당 마법사의 단계에 따라 해당 인증서를 할당 합니다.
    
      - 기본 인증서를 사용 하기 위해 인증서를 요청 해야 하는 경우 **요청** 을 클릭 한 다음 인증서 요청 마법사의 단계에 따라 해당 인증서를 요청 합니다. 웹 서버 인증서에 대 한 기본값을 사용 하는 경우에는 기본 인증서로 할당할 수 있는 인증서를 받습니다.

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a>감시자 노드 설치 및 구성

감시자 노드 컴퓨터를 다시 시작 하 고 인증서를 구성한 후에는 Watchernode 파일을 실행 해야 합니다. (Operations Manager 에이전트 파일과 Lync Server 2013 core 구성 요소가 설치 되어 있는 컴퓨터에서 Watchernode을 실행 해야 합니다.)

**감시자 노드를 설치 하 고 구성 하려면**

1.  **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 lync **Server**를 클릭 하 고 **lync Server Management Shell**을 클릭 하 여 lync server management shell을 엽니다.

2.  Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다 (Watchernode 복사본의 실제 경로 지정).
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > 명령 창에서 Watchernode를 실행할 수도 있습니다. 명령 창을 열려면 <STRONG>시작</STRONG>을 클릭 하 고 <STRONG>명령 프롬프트</STRONG>를 마우스 오른쪽 단추로 클릭 한 다음 <STRONG>관리자 권한으로 실행</STRONG>을 클릭 합니다. 명령 창이 열리면 앞의 동일한 명령을 입력 합니다.

    
    </div>

앞의 명령 인증 =로 서버에서 이름/값 쌍은 대/소문자를 구분 합니다. 표시 된 대로 정확 하 게 입력 해야 합니다. 다음 명령은 올바른 문자 대/소문자를 사용 하지 않기 때문에 실패 합니다.

C:\\도구\\Watchernode 인증 = (대상 서버)

외곽 네트워크 내에 있는 컴퓨터에만이 지 있는 서버 모드를 사용할 수 있습니다. 감시자 노드가 (가)로 서버 모드에서 실행 되는 경우 관리자는 컴퓨터에서 테스트 사용자 암호를 유지할 필요가 없습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

