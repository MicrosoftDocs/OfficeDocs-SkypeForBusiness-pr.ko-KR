---
title: 'Lync Server 2013: 기존 네트워크 지역 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3a1c1e697e681eec4886dca9e942d9bc133b0f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525405"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>Lync Server 2013에서 기존 네트워크 지역 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

네트워크 지역은 여러 지역의 많은 네트워크 부분을 교차합니다. 모든 네트워크 지역은 중앙 사이트와 연결되어야 합니다. 중앙 사이트는 CAC(통화 허용 제어) 대역폭 정책 서비스가 실행되는 데이터 센터 사이트입니다. Lync Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다. 네트워크 지역에는 오디오 및 비디오 연결에 대해 인터넷을 통한 대체 경로가 허용되는지 여부를 결정하는 설정이 포함됩니다. Lync Server 제어판에서는 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 참조하여 기존 네트워크 지역을 삭제하십시오. 기존 네트워크 지역을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-regions.md)참조 하십시오.

<div>

## <a name="to-delete-a-network-region"></a>네트워크 지역을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **네트워크 구성**을 클릭한 다음 **지역**을 클릭합니다.

4.  **지역** 페이지에서 삭제하려는 지역을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 둘 이상의 지역을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 지역을 선택합니다. 또는 지역을 모두 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭합니다.

6.  **확인**을 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 네트워크 사이트와 연결된 네트워크 지역은 제거할 수 없습니다. 사이트와 연결된 지역을 제거하려고 시도하면 오류 메시지가 표시됩니다. 지역이 사이트와 연결되어 있는지 확인하려면 지역을 선택하고 <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG>를 클릭합니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 지역 만들기 또는 수정](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

