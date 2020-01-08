---
title: A/V Edge 서버 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af42c338cb7032231ce562ac2227ff4089729ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 A/V Edge 서버 구성 설정의 기존 컬렉션 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

A/V Edge 서비스는 내부 사용자 (조직의 네트워크에 로그온 한 사용자)가 외부 사용자 (조직의 네트워크에 로그인 하지 않은 사용자)와 오디오 및 비디오를 공유 하는 방법을 제공 합니다. A/V Edge 서비스는 사이트 범위 또는 서비스 범위 (개별 A/V Edge 서버에 대해 구성할 수 있음)에서 구성할 수 있는 설정인 A/V Edge 구성 설정을 사용 하 여 관리 됩니다.

Lync Server를 설치할 때 A/V Edge 구성 설정의 전역 컬렉션이 만들어집니다. 이 전역 모음은 삭제할 수 없습니다. 그러나 Windows PowerShell 및 CsAVEdgeConfiguration cmdlet을 사용 하 여 전역 컬렉션을 "다시 설정" 할 수 있습니다. 즉, 전역 컬렉션의 모든 속성 값이 기본값으로 다시 설정 됩니다. 예를 들어 MaxTokenLifetime 속성을 16 시간으로 설정한 경우 해당 속성이 기본값으로 8 시간으로 다시 설정 됩니다.

그러나 사이트 범위 또는 서비스 범위에서 만든 사용자 지정 설정 모음은 Remove-CsAVEdgeConfiguration cmdlet을 사용 하 여 삭제할 수 있습니다. 사이트 설정을 삭제 하면 해당 사이트의 A/V Edge 서버가 전역 설정으로 관리 됩니다. 서비스 범위 설정을 삭제 한 경우 해당 서버는 해당 사이트 설정 (있는 경우) 또는 사이트 설정을 사용할 수 없는 경우 전역 설정에 따라 관리 됩니다.

자세한 내용은 [제거 CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.

<div>

## <a name="to-reset-the-global-collection"></a>전역 컬렉션을 다시 설정 하려면

  - 다음 명령은 A/V Edge 구성 설정의 전역 컬렉션을 다시 설정 합니다.
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>사이트 범위에서 컬렉션을 제거 하려면

  - 이 명령은 Redmond 사이트에 적용 된 A/V Edge 구성 설정을 제거 합니다.
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>서비스 범위에서 컬렉션을 제거 하려면

  - 이 명령은 A/V Edge 서버 atl-edge-001.litwareinc.com에 적용 된 설정을 제거 합니다.
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 A/V Edge 서버 구성 정보 반환](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013에서 A/V Edge 서버 구성 설정 모음 만들기 또는 수정](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013의 오디오/비디오 (A/V) Edge 서버](lync-server-2013-audio-video-a-v-edge-servers.md)  
[제거-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

