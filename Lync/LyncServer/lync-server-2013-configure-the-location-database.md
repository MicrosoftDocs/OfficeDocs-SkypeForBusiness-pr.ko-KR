---
title: 'Lync Server 2013: 위치 데이터베이스 구성'
description: 'Lync Server 2013: 위치 데이터베이스를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 877c83976ca0db9abc3a9e57d4a1cf5adaa1291a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544934"
---
# <a name="configure-the-location-database-in-lync-server-2013"></a>Lync Server 2013에서 위치 데이터베이스 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

클라이언트가 네트워크 내에서 자신의 위치를 자동으로 감지하도록 하려면 먼저 위치 데이터베이스를 구성해야 합니다. 위치 데이터베이스를 구성하지 않은 상태에서 위치 정책의 **위치 필요**가 **예** 또는 **고지 사항**으로 설정되어 있으면 수동으로 위치를 입력하라는 메시지가 표시됩니다.

위치 데이터베이스를 구성하려면 다음 작업을 수행합니다.

1.  데이터베이스를 위치에 대한 네트워크 요소 매핑으로 채웁니다. ELIN (비상 위치 식별 번호) 게이트웨이를 사용 하는 경우 필드에 ELIN을 포함 해야 합니다 \<CompanyName\> .

2.  E9-1-1 서비스 공급자가 유지 관리하는 MSAG(마스터 주소 가이드)에 대해 주소를 확인합니다.

3.  업데이트된 데이터베이스를 게시합니다.

<div>


> [!NOTE]  
> 또는 위치 데이터베이스 대신 사용할 수 있는 보조 위치 원본 데이터베이스를 정의할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013에서 보조 위치 정보 서비스 구성을</A>참조 하십시오.



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

