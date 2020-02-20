---
title: 'Lync Server 2013: Exchange 저장소와의 통합 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a3c51b944032fd871ab6f5372f7f3f8c42fad4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>Exchange 저장소와 함께 Lync Server 2013의 통합 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

Lync Server 2013 제어판에서는 보관 구성을 사용 하 여 Exchange 저장소와의 통합을 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다. 여기에는 다음 보관 구성이 포함됩니다.

  - Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.

  - 보관이 특정 사이트 또는 풀에 구현되는 방식을 지정하는 데 사용하도록 만들 수 있는 사이트 수준 및 풀 수준 구성(선택 사항)

지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>Microsoft Exchange 저장소와의 통합을 사용 하거나 사용 하지 않도록 설정 하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.

4.  보관 구성 목록에서 적합한 전역, 사이트 또는 풀 구성 이름을 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭한 후 다음을 수행합니다.
    
      - Exchange 2013 저장소와의 통합을 사용 하도록 설정 하려면 **Microsoft Exchange 통합** 확인란을 선택 합니다.
    
      - Exchange 2013 저장소와의 통합을 사용 하지 않도록 설정 하려면 **Microsoft Exchange 통합** 확인란의 선택을 취소 합니다.

5.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 보관이 작동 하는 방식](lync-server-2013-how-archiving-works.md)  


[조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

