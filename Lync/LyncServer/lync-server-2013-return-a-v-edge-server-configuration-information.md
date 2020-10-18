---
title: 'Lync Server 2013: A/V에 지 서버 구성 정보 반환'
description: 'Lync Server 2013: A/V에 지 서버 구성 정보를 반환 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575444"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Lync Server 2013에서 A/V에 지 서버 구성 정보 반환

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

A/V 에지 서비스는 내부 사용자(조직 단위 네트워크에 로그온된 사용자)가 외부 사용자(조직 단위 네트워크에 로그온되지 않은 사용자)와 오디오 및 비디오를 공유할 수 있는 방법을 제공합니다. A/V 에지 서비스는 주로 사이트 범위 또는 서비스 범위에서 구성할 수 있는(즉, 개별 A/V 에지 서버에 대해 구성할 수 있는) 설정인 A/V 에지 구성 설정을 사용해서 관리됩니다.

조직에서 사용 중인 A/V에 지 구성 설정에 대 한 정보를 반환 하려면 Windows PowerShell 및 Get-CsAVEdgeConfiguration cmdlet을 사용 해야 합니다. 자세한 내용은 [get-csavedgeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

Get-CsAVEdgeConfiguration cmdlet에서 반환 되는 정보는 다음과 같습니다.

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>모든 A/V에 지 구성 설정에 대 한 정보를 반환 하려면

  - 다음 명령은 조직에서 현재 사용 중인 모든 A/V에 지 구성 설정에 대 한 정보를 반환 합니다.
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>사이트 범위가 지정 된 A/V에 지 구성 설정에 대 한 정보를 반환 하려면

  - A/V에 지 구성 설정의 특정 컬렉션에 대 한 정보를 반환 하려면 Get-CsAVEdgeConfiguration cmdlet을 실행할 때 해당 컬렉션의 Id를 지정 합니다. 예를 들어이 명령은 Redmond 사이트에 적용 된 설정에 대 한 정보만 반환 합니다.
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>서비스 범위가 지정 된 A/V에 지 구성 설정에 대 한 정보를 반환 하려면

  - 그리고이 명령은 특정 A/V에 지 서버를 적용 한 설정에 대 한 정보만 반환 합니다.
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 A/V에 지 서버 구성 설정 모음 만들기 또는 수정](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Lync Server 2013에서 A/V에 지 서버 구성 설정의 기존 컬렉션 삭제](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Lync Server 2013의 A/V (오디오/비디오)에 지 서버](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

