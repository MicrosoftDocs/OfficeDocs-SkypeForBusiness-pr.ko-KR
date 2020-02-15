---
title: A/V에 지 서버 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901562812e7847a6c205f042922dca6383ad6254
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 A/V에 지 서버 구성 설정의 기존 컬렉션 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

A/V 에지 서비스는 내부 사용자(조직 단위 네트워크에 로그온된 사용자)가 외부 사용자(조직 단위 네트워크에 로그온되지 않은 사용자)와 오디오 및 비디오를 공유할 수 있는 방법을 제공합니다. A/V 에지 서비스는 주로 사이트 범위 또는 서비스 범위에서 구성할 수 있는(즉, 개별 A/V 에지 서버에 대해 구성할 수 있는) 설정인 A/V 에지 구성 설정을 사용해서 관리됩니다.

Lync Server를 설치 하면 A/V에 지 구성 설정의 전역 컬렉션이 만들어집니다. 이 전역 컬렉션은 삭제할 수 없습니다. 그러나 Windows PowerShell 및 Get-csavedgeconfiguration cmdlet을 사용 하 여 전역 컬렉션을 "다시 설정" 할 수 있습니다. 이는 전역 컬렉션의 모든 속성 값이 기본값으로 다시 설정 된다는 것을 의미 합니다. 예를 들어 MaxTokenLifetime 속성을 16 시간으로 설정한 경우 해당 속성은 기본값으로 8 시간으로 다시 설정 됩니다.

하지만 사이트 범위 또는 서비스 범위에서 만든 사용자 지정 설정 컬렉션은 Remove-CsAVEdgeConfiguration cmdlet을 사용하여 삭제할 수 있습니다. 사이트 설정을 삭제하면 해당 사이트의 A/V 에지 서버가 전역 설정에 의해 관리됩니다. 장치 범위 설정을 삭제할 경우 해당 서버가 사이트 설정(있는 경우)으로 관리되거나, 사이트 설정을 사용할 수 없으면 전역 설정으로 관리됩니다.

자세한 내용은 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

<div>

## <a name="to-reset-the-global-collection"></a>전역 컬렉션을 다시 설정 하려면

  - 다음 명령은 A/V 에지 구성 설정의 전역 컬렉션을 다시 설정합니다.
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>사이트 범위에서 컬렉션을 제거 하려면

  - 이 명령은 Redmond 사이트에 적용된 A/V 에지 구성 설정을 제거합니다.
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>서비스 범위에서 컬렉션을 제거 하려면

  - 이 명령은 A/V 에지 서버 atl-edge-001.litwareinc.com에 적용된 설정을 제거합니다.
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 A/V에 지 서버 구성 정보 반환](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013에서 A/V에 지 서버 구성 설정 모음 만들기 또는 수정](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013의 A/V (오디오/비디오)에 지 서버](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Get-csavedgeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

