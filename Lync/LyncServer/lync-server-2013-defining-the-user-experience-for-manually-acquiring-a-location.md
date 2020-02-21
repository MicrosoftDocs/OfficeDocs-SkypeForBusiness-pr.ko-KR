---
title: 위치를 수동으로 가져오기 위한 사용자 환경 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb1d4a51179326f15999f05f2f80649d7b9dec8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

클라이언트가 네트워크 외부에 있거나 정의 되지 않은 서브넷에 있는 경우 사용자가 위치를 수동으로 입력할 수 있습니다. 그러나 긴급 통화 중에는 통화가 공용 안전 응답 지점 (PSAP)으로 라우팅되도록 하기 전에 먼저 국내/지역별 E9-1-1 긴급 통화 응답 센터 (ECRC) 발송자에 게 라우팅됩니다. ECRC는 이동할에서 위치를 쿼리 한 다음 제공 된 정보에 따라 적절 한 PSAP로 통화를 착신 전환 합니다.

  - **위치 정보 서비스에서 자동으로 제공 되지 않는 위치를 입력 하 라는 메시지가 표시 됩니까?**  
    예를 들어 클라이언트가 정의 되지 않은 서브넷, 집, 호텔 또는 네트워크 외부의 다른 위치에 있는 경우 사용자가 위치를 입력 해야 합니까?
    
    위치 정책에서 클라이언트 동작을 정의 하는 **위치** 설정을 구성할 수 있습니다. 이 값을 No로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되지 않습니다. 이 값을 Yes로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되지만 메시지를 닫을 수 없습니다. 이 값을 고 지 수로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되며 메시지를 다시 표시 하지 않을 경우 고 지 사항이 표시 됩니다. 모든 경우에 사용자는 평소와 같이 클라이언트를 계속 사용할 수 있습니다.

사용자가 위치를 수동으로 입력 하면 위치가 클라이언트 네트워크의 기본 게이트웨이의 MAC 주소에 매핑되고 클라이언트에 있는 사용자별 테이블에 저장 됩니다. 사용자가 이전에 저장 된 위치로 반환 되 면 Lync 클라이언트는 자동으로 해당 위치로 설정 됩니다.

<div>


> [!NOTE]
> 클라이언트의 현재 위치만 수정할 수 있지만 로컬 사용자의 테이블에 저장 된 모든 위치를 삭제할 수도 있습니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

