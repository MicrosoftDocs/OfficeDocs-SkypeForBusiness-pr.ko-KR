---
title: 토폴로지 정보 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69add03365fa55ba3b08ac4c6b7a1dd60a6294f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>토폴로지 정보 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-26_

병합이 완료 되었는지 확인 하는 첫 번째 단계는 Lync Server 2013와 병합 한 Office Communications Server 2007 R2 토폴로지 정보를 확인 하는 것입니다. 토폴로지 작성기에서 **BackCompatSite** 노드는 병합 한 각 Office Communications Server 2007 R2 풀 및 서버의 FQDN (정규화 된 도메인 이름)을 표시 합니다.

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>토폴로지 작성기에서 BackCompatSite를 보려면

1.  Office Communications Server 2007 R2 환경에서 Office Communications Server 2007 R2 관리 도구를 열고 레거시 풀 및 서버의 Fqdn을 기록해 둡니다.

2.  Lync Server 2013 환경에서 토폴로지 작성기를 열고 **BackCompatSite** 노드를 확장 합니다.

3.  병합하는 풀 및 서버의 FQDN이 표시되는지 확인합니다.
    
    <div>
    

    > [!NOTE]  
    > 프런트 엔드 서버 또는 Standard Edition 서버에 배치 된 된 서버 역할에 대 한 정보는 <STRONG>BackCompatSite</STRONG> 에 표시 되지 않습니다. Office Communications Server 2007 R2와 Lync Server 2013 간의 상호 운용성에 필요한 서버 역할만 표시 됩니다.

    
    </div>

![토폴로지 작성기 BackCompatSite 대화 상자](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "토폴로지 작성기 BackCompatSite 대화 상자")

또한 Lync Server 2013 제어판을 사용 하 여 병합 된 토폴로지를 볼 수 있습니다. Lync Server 2013 제어판에서는 병합 된 토폴로지의 각 서버 FQDN, 풀 FQDN 및 사이트 이름을 볼 수 있습니다. 병합된 서버는 **BackCompatSite**라는 **사이트**를 포함합니다.

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>Lync Server 2013 제어판에서 병합 된 토폴로지를 보려면

1.  Lync Server 2013 제어판을 엽니다.

2.  **토폴로지**를 클릭합니다.

3.  **상태** 탭의 **사이트** 열에서 **BackCompatSite**를 찾아서 병합한 서버 및 풀이 표시되는지 확인합니다.

![병합 된 토폴로지를 보여 주는 Lync Server 제어판](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "병합 된 토폴로지를 보여 주는 Lync Server 제어판")

병합된 풀에 대한 자세한 내용을 보려면 **Get-CsPool** cmdlet을 사용합니다. 이 cmdlet은 토폴로지 작성기 및 Lync Server 2013 제어판에서 사용할 수 있는 정보 외에도 Lync Server 2013 풀에서 실행 되는 서비스를 표시 합니다.

<div>


> [!NOTE]  
> 토폴로지 작성기에서 병합 마법사를 실행 한 후에 토폴로지를 게시 하면 전화 회의 디렉터리가 Lync Server 2013에 병합 됩니다. <STRONG>Get-csconferencedirectory</STRONG> cmdlet을 실행 하 여 전화 회의 디렉터리를 확인할 수 있습니다.



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>병합된 풀에서 서비스를 보려면

1.  Lync Server 2013 관리 셸을 엽니다.

2.  명령줄에 다음을 입력합니다.
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    예:
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>병합된 회의 디렉터리를 보려면

1.  Lync Server 2013 관리 셸을 엽니다.

2.  명령줄에 다음을 입력합니다.
    
        Get-CsConferenceDirectory

3.  병합 하는 풀 또는 서버의 모든 전화 회의 디렉터리가 현재 Lync Server 2013에 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

