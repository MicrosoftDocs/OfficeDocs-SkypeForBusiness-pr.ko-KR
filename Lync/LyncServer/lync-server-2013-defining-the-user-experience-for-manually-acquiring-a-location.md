---
title: 수동으로 위치를 가져오기 위한 사용자 환경 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5be01e4cf35d51b457cd575ef31254475bfda5bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

클라이언트가 네트워크 외부에 있거나 정의 되지 않은 서브넷에 있는 경우에는 사용자가 수동으로 위치를 입력할 수 있습니다. 그러나 비상 전화 중에는 먼저 국내/지역 E9-1-1-긴급 통화 응답 센터 (ECRC) 발송자에 게 전달 되기 전에 해당 통화가 공공 안전 응답 시점 (PSAP)으로 라우팅되지 않습니다. ECRC는 호출자에 게 위치를 구두로 다음 제공 된 정보를 기반으로 해당 PSAP로 호출을 착신 전환 합니다.

  - **위치 정보 서비스에서 자동으로 제공 되지 않는 위치를 입력 하 라는 메시지가 표시 되 게 하려면**  
    예를 들어 클라이언트가 정의 되지 않은 서브넷, 가정용, 호텔 또는 네트워크 외부의 모든 위치에 있는 경우 사용자가 위치를 입력 해야 할 수 있습니다.
    
    위치 정책의 **위치** 설정을 구성 하 여 클라이언트 동작을 정의할 수 있습니다. 이 값을 No로 설정 하면 사용자에 게 위치를 묻지 않는다는 의미입니다. 이 값을 예/y e s로 설정 하면 사용자에 게 위치를 묻는 메시지가 표시 되지만 메시지가 해제 될 수 있습니다. 이 값을 포기로 설정 하면 사용자에 게 위치를 묻는 메시지가 표시 되 고, 프롬프트를 해제 하려고 할 때의 고 지 사항이 표시 됩니다. 모든 경우에 사용자는 평소 대로 클라이언트를 계속 사용할 수 있습니다.

사용자가 위치를 수동으로 입력 하는 경우 위치는 클라이언트 네트워크의 기본 게이트웨이의 MAC 주소로 매핑되고 클라이언트에 있는 사용자별 테이블에 저장 됩니다. 사용자가 이전에 저장 된 위치로 돌아갈 때 Lync 클라이언트는 자동으로 해당 위치로 설정 됩니다.

<div>


> [!NOTE]
> 클라이언트의 현재 위치만 수정할 수 있지만 로컬 사용자의 테이블에 저장 된 위치를 삭제할 수도 있습니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

