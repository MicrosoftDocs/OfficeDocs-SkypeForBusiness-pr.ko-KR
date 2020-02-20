---
title: A/V에 지 서버 구성 설정 모음 만들기 또는 수정
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
ms.openlocfilehash: faff058e2d4e2ef3a874ad5fcece3ad1422605c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 A/V에 지 서버 구성 설정 모음 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

A/V 에지 서비스는 내부 사용자(조직 단위 네트워크에 로그온된 사용자)가 외부 사용자(조직 단위 네트워크에 로그온되지 않은 사용자)와 오디오 및 비디오를 공유할 수 있는 방법을 제공합니다. A/V 에지 서비스는 주로 사이트 범위 또는 서비스 범위에서 구성할 수 있는(즉, 개별 A/V 에지 서버에 대해 구성할 수 있는) 설정인 A/V 에지 구성 설정을 사용해서 관리됩니다.

Lync Server를 설치 하면 A/V에 지 구성 설정의 전역 컬렉션이 만들어집니다. 또한 Windows PowerShell 및 Get-csavedgeconfiguration cmdlet을 사용 하 여 사이트 범위 또는 서비스 범위 (즉, 개별 A/V에 지 서버에 대 한)에 새 설정을 만들 수 있습니다. 새 설정을 만들 때는 다음을 고려해야 합니다.

  - 서비스 범위로(즉, 개별 서버에서) 구성된 설정은 다른 모든 것들보다 우선 적용됩니다.

  - 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다. 그러나 서비스 범위 설정도 사이트 범위 설정으로 대체 됩니다.

  - 전역 범위의 설정은 개별 서버에 구성된 서비스 설정이 없는 경우 그리고 서버가 배치된 위치에 사이트 설정이 없는 경우에만 사용됩니다.

그런 후 Set-CsAVEdgeConfiguration cmdlet을 사용하여 모든 설정을 수정할 수 있습니다. 자세한 내용은 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) 및 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>사이트 범위에서 새 A/V에 지 구성 설정을 만들려면

  - 다음 명령은 Redmond 사이트에 대해 새로운 A/V 에지 구성 설정의 컬렉션을 만듭니다.
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>사이트 범위에서 사용자 지정 A/V에 지 구성 설정을 만들려면

  - 추가 매개 변수가 포함되지 않았기 때문에 이러한 새 설정에는 A/V 에지 서비스에 대한 기본 값이 사용됩니다. 또는 추가 매개 변수 및 매개 변수 값을 추가하여 사용자 지정 컬렉션을 만들 수 있습니다. 예를 들어 이 명령은 MaxTokenLifetime 속성을 4시간으로 설정합니다(04시간 : 00분 : 00초).
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>서비스 범위에서 사용자 지정 A/V에 지 구성 설정을 만들려면

  - 이 명령은 A/V 에지 서버 atl-edge-001.litwareinc.com에 적용되는 비슷한 컬렉션을 만듭니다.
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>기존 A/V에 지 구성 설정을 수정 하려면

  - 이 예에서 Set-CsAVEdgeConfiguration cmdlet은 Redmond 사이트의 최대 토큰 수명을 12시간으로 변경하는 데 사용됩니다.
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 A/V에 지 서버 구성 정보 반환](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Lync Server 2013에서 A/V에 지 서버 구성 설정의 기존 컬렉션 삭제](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013의 A/V (오디오/비디오)에 지 서버](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

