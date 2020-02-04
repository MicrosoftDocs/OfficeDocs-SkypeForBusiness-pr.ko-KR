---
title: A/V Edge 서버 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4b45b34b5c52d0eb138fbc16c37e5aaee7262b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 A/V Edge 서버 구성 설정 모음 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

A/V Edge 서비스는 내부 사용자 (조직의 네트워크에 로그온 한 사용자)가 외부 사용자 (조직의 네트워크에 로그인 하지 않은 사용자)와 오디오 및 비디오를 공유 하는 방법을 제공 합니다. A/V Edge 서비스는 사이트 범위 또는 서비스 범위 (개별 A/V Edge 서버에 대해 구성할 수 있음)에서 구성할 수 있는 설정인 A/V Edge 구성 설정을 사용 하 여 관리 됩니다.

Lync Server를 설치할 때 A/V Edge 구성 설정의 전역 컬렉션이 만들어집니다. 이 외에도 Windows PowerShell 및 CsAVEdgeConfiguration cmdlet을 사용 하 여 사이트 범위 또는 서비스 범위 (즉, 개별 A/V Edge 서버의 경우)에 대 한 새 설정을 만들 수 있습니다. 새 설정을 만드는 경우 다음 사항에 유의 하세요.

  - 서비스 범위 (즉, 개별 서버)에 구성 된 설정은 모두에 게 우선 합니다.

  - 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다. 그러나 서비스 범위 설정 에서도 사이트 범위 설정이 대체 됩니다.

  - 전역 범위의 설정은 개별 서버에 구성 된 서비스 설정이 없고 해당 서버가 있는 사이트에 대 한 사이트 설정이 없는 경우에만 사용 됩니다.

그런 다음 CsAVEdgeConfiguration cmdlet을 사용 하 여 모든 설정을 수정할 수 있습니다. 자세한 내용은 [새 CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) 및 [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>사이트 범위에서 새 A/V Edge 구성 설정을 만들려면

  - 다음 명령은 Redmond 사이트에 대 한 A/V Edge 구성 설정의 새 컬렉션을 만듭니다.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>사이트 범위에서 사용자 지정 A/V Edge 구성 설정을 만들려면

  - 추가 매개 변수가 포함 되지 않았으므로 이러한 새 설정에서는 A/V Edge 서비스에 대 한 기본값을 사용 합니다. 또는 매개 변수 및 매개 변수 값을 더 추가 하 여 사용자 지정 컬렉션을 만들 수 있습니다. 예를 들어이 명령은 MaxTokenLifetime 속성을 4 시간 (04 시간: 00 분: 00 초)으로 설정 합니다.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>서비스 범위에서 사용자 지정 A/V Edge 구성 설정을 만들려면

  - 이 명령은 A/V Edge 서버 atl-edge-001.litwareinc.com에 적용 된 유사한 컬렉션을 만듭니다.
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>기존 A/V Edge 구성 설정을 수정 하려면

  - 이 예제에서는 집합-CsAVEdgeConfiguration cmdlet을 사용 하 여 Redmond 사이트의 최대 토큰 수명을 12 시간으로 변경 합니다.
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 A/V Edge 서버 구성 정보 반환](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013에서 A/V Edge 서버 구성 설정의 기존 컬렉션 삭제](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013의 오디오/비디오 (A/V) Edge 서버](lync-server-2013-audio-video-a-v-edge-servers.md)  
[새로운 CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

