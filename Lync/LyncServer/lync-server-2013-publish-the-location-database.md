---
title: 'Lync Server 2013: 위치 데이터베이스 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb7fef480a5b9a53706cca9f76408fbd58f28be
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Lync Server 2013에서 위치 데이터베이스 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

위치 데이터베이스에 추가한 새 위치는 게시 될 때까지 클라이언트에서 사용할 수 없게 됩니다.

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - **게시-Export-cslisconfiguration**

ELIN (응급 위치 식별 번호) 게이트웨이를 사용 하는 경우에는 PSTN (공중 전화망) 캐리어의 ALI (자동 위치 식별) 데이터베이스에 Elin를 업로드 해야 합니다. PSTN 통신 회사에서는 레코드의 ELIN 특정 형식을 사용 해야 할 수도 있습니다. 자세한 내용은 PSTN 캐리어에 문의 하세요. 위치 정보 서비스 데이터베이스에서 레코드를 내보내고 필요에 따라 서식을 지정할 수 있습니다.

<div>

## <a name="to-publish-the-location-database"></a>위치 데이터베이스를 게시 하려면

  - **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

  - 다음 cmdlet를 실행 하 여 위치 데이터베이스를 게시 합니다.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

