---
title: 'Lync Server 2013: 위치 데이터베이스 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15a9456cc79e02735fe94c24748674944722b49c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>Lync Server 2013에서 위치 데이터베이스 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-17_

클라이언트가 네트워크 내에서 해당 위치를 자동으로 검색할 수 있도록 하려면 먼저 위치 데이터베이스를 구성 해야 합니다. 위치 데이터베이스를 구성 하지 않고 위치 정책에 **필요한 위치가** **예** 또는 **부인**로 설정 된 경우 사용자에 게 위치를 수동으로 입력 하 라는 메시지가 표시 됩니다.

위치 데이터베이스를 구성 하려면 다음 작업을 수행 합니다.

1.  네트워크 요소를 위치에 매핑하는 방법으로 데이터베이스를 채웁니다. 비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 \<CompanyName\> 필드에 elin을 포함 해야 합니다.

2.  E9-1 서비스 공급자가 유지 관리 하는 MSAG (마스터 거리 주소 가이드)에 대해 주소의 유효성을 검사 합니다.

3.  업데이트 된 데이터베이스를 게시 합니다.

<div>


> [!NOTE]  
> 또는 위치 데이터베이스에 배치할 때 사용할 수 있는 보조 위치 원본 데이터베이스를 정의할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013에서 보조 위치 정보 서비스 구성을</A>참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 위치 데이터베이스 채우기](lync-server-2013-populate-the-location-database.md)

  - [Lync Server 2013에서 주소 유효성 검사](lync-server-2013-validate-addresses.md)

  - [Lync Server 2013에서 위치 데이터베이스 게시](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

