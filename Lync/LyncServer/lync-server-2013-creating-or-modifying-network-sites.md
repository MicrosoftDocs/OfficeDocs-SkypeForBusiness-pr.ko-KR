---
title: 'Lync Server 2013: 네트워크 사이트 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 사이트 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-08_

네트워크 사이트는 CAC (통화 허용 제어) 또는 향상 된 9-1-1 배포의 각 영역 내에서 구성 된 사무실 또는 위치입니다. Microsoft Lync Server 2013 제어판을 사용 하 여 사이트를 구성 하 고 지역에 연결할 수 있습니다. 예를 들어 북미, 레드먼드, Vancouver와 같은 네트워크 사이트에 북아메리카 네트워크 지역이 연결 되어 있을 수 있습니다. 사이트에 대 한 모든 사이트에 대해 CAC 네트워크 사이트를 만들어야 하는 경우에도 해당 사이트가 대역폭 제한 없이 구성 되어야 합니다. Lync Server 제어판에서 네트워크 사이트를 만들고, 수정 하 고, 삭제할 수 있습니다. 네트워크 사이트를 만들거나 수정 하려면 다음 절차를 사용 합니다. 기존 네트워크 사이트를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 사이트 삭제](lync-server-2013-deleting-an-existing-network-site.md)를 참조 하세요.

<div>

## <a name="to-create-a-network-site"></a>네트워크 사이트를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 사이트**의 **name (이름** ) 필드에이 사이트의 이름을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사이트 이름은 Lync Server 2013 배포 내에서 고유 해야 합니다.

    
    </div>

6.  **지역** 드롭다운 목록에서이 사이트와 연결할 네트워크 지역을 선택 합니다.

7.  ) 이 사이트에 대 한 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 대역폭 **정책** 드롭다운 목록에서 적절 한 설정을 사용 하 여 대역폭 정책 프로필을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>네트워크 구성</STRONG> 그룹의 <STRONG>정책 프로필</STRONG> 페이지에서 사용 가능한 대역폭 정책 프로필의 세부 정보를 보거나 새 대역폭 정책 프로필을 만들 수 있습니다. 자세한 내용은 <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정을</A>참조 하세요.

    
    </div>

8.  ) 이 사이트에 대 한 위치 설정을 제공 하려면 **위치 정책** 드롭다운 목록에서 위치 정책을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 위치 정책은 사이트에 특정 향상 된 9-1-1 (E9-1-1) 및 클라이언트 위치 설정을 할당 합니다. <STRONG>네트워크 구성</STRONG> 그룹의 <STRONG>위치 정책</STRONG> 페이지에서 사용 가능한 위치 정책의 세부 정보를 보거나 새 위치 정책을 만들 수 있습니다. 자세한 내용은 <A href="lync-server-2013-viewing-location-policy-information.md">Lync Server 2013의 위치 정책 정보 보기</A>를 참조 하세요.

    
    </div>

9.  ) 이름 만으로 표현할 수 없는이 사이트에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

10. **커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 새 네트워크 사이트를 만들 때 <STRONG>연결 된 서브넷</STRONG> 테이블을 사용 하지 않습니다. 서브넷을 만들거나 수정할 때 서브넷을 사이트와 연결 합니다. 자세한 내용은 <A href="lync-server-2013-create-or-modify-network-subnets.md">Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정을</A>참조 하세요.

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>네트워크 사이트를 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 수정 하려는 사이트를 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **사이트 편집** 페이지에서 설명, 지역, 대역폭 정책 프로필, 사이트와 연결 된 위치 정책을 수정할 수 있습니다. 자세한 내용은이 항목의 앞부분에 있는 "네트워크 사이트 만들기" 섹션을 참조 하세요.

7.  **커밋**을 클릭합니다.

이 페이지에서는 **연결 된 서브넷** 테이블을 수정할 수 없습니다. 사이트 설정을 수정할 때 어떤 서브넷에 영향을 미치는지 알 수 있도록 관련 서브넷 목록이 참조용으로 제공 됩니다.

</div>

<div>

## <a name="to-delete-a-network-site"></a>네트워크 사이트를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **사이트**를 클릭 합니다.

4.  **사이트** 페이지에서 삭제 하려는 사이트를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 여러 사이트를 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 사이트를 선택 합니다. 또는 모든 사이트를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 네트워크 서브넷과 연결 된 네트워크 사이트는 제거할 수 없습니다. 서브넷과 연결 된 사이트를 제거 하려고 하면 오류 메시지가 표시 됩니다. 사이트가 서브넷과 연결 되어 있는지 확인 하려면 사이트를 클릭 한 다음 <STRONG>편집</STRONG> 메뉴에서 <STRONG>자세한 정보 표시</STRONG> 를 클릭 합니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 기존 네트워크 사이트 삭제](lync-server-2013-deleting-an-existing-network-site.md)  


[새-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[집합-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[CsNetworkSite 사이트 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

