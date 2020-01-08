---
title: 'Lync Server 2013: 네트워크 지역 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3ca5d44fd2278ffee8a3e9dd4494575cc64c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다. 모든 네트워크 지역은 중앙 사이트와 연결 되어 있어야 합니다. 중앙 사이트는 CAC (call 허용 제어) 대역폭 정책 서비스가 실행 되는 데이터 센터 사이트입니다. Lync Server 제어판을 사용 하 여 네트워크 지역을 구성할 수 있습니다. 네트워크 영역에는 오디오 및 비디오 연결에 인터넷을 통한 대체 경로가 허용 되는지 여부를 결정 하는 설정이 포함 됩니다. Lync Server 제어판에서 네트워크 지역을 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 사용 하 여 네트워크 지역을 만들고 수정 합니다. 기존 네트워크 지역을 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 영역 삭제](lync-server-2013-deleting-existing-network-regions.md)를 참조 하세요.

<div>

## <a name="to-create-a-network-region"></a>네트워크 지역을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역을**클릭 합니다.

4.  **지역** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 지역** 페이지의 **이름** 필드에 값을 입력 합니다. 이 값은 Microsoft Lync Server 2013 배포 내에서 고유 해야 합니다.

6.  **중앙 사이트** 드롭다운 목록에서이 네트워크 영역에 대 한 중앙 사이트를 선택 합니다.

7.  **오디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다. 이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 오디오 통화가 대체 경로를 통해 라우팅되는 지를 결정 합니다. 인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다. 인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.

8.  **비디오 대체 경로 사용** 확인란이 기본적으로 선택 되어 있습니다. 이 필드는 기본 경로에 적절 한 대역폭이 없는 경우 영상 통화를 대체 경로를 통해 라우팅할 지 여부를 결정 합니다. 인터넷에 대 한 오프 로드를 해제 해야 하는 경우에만이 확인란의 선택을 취소 합니다. 인터넷에 전화를 거는 경우 대역폭 설정에 관계 없이이 확인란을 선택 해야 합니다.

9.  ) 이름 만으로 표현할 수 없는이 영역에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

10. **커밋**을 클릭합니다.

**연결 된 사이트** 테이블은 네트워크 지역을 만드는 데 사용 되지 않습니다. 사이트를 만들거나 수정할 때 사이트를 영역과 연결 합니다. 자세한 내용은 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-sites.md)참조 하세요.

</div>

<div>

## <a name="to-modify-a-network-region"></a>네트워크 지역 수정

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역을**클릭 합니다.

4.  **지역** 페이지에서 수정 하려는 지역을 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **지역 편집** 페이지에서 오디오 및 비디오 대체 경로를 사용 하거나 사용 하지 않도록 설정 하는 설정을 수정 하 고 설명 (자세한 내용은이 항목의 "네트워크 영역 만들기" 섹션을 참조 하세요.)을 변경할 수 있습니다.

7.  **커밋**을 클릭합니다.

이 페이지에서 **연결 된 사이트** 를 수정할 수 없습니다. 연결 된 사이트 목록은 지역 설정을 수정할 때 영향을 받는 사이트를 알 수 있도록 참조용으로 제공 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 기존 네트워크 영역 삭제](lync-server-2013-deleting-existing-network-regions.md)  
[Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성](lync-server-2013-configure-network-regions-for-cac.md)  


[새-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[CsNetworkRegion 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

