---
title: 'Lync Server 2013: 네트워크 지역 경로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-08_

CAC (호출 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스 하는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하 고 실제 링크를 표시 하는 경우 경로에 따라 연결이 한 영역에서 다른 지역으로 이동 하는 연결 경로가 결정 됩니다. Lync Server 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다. Lync Server 제어판에서 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 사용 하 여 네트워크 지역 경로를 만들거나 수정 합니다. 기존 네트워크 지역 경로를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기존 네트워크 지역 경로 삭제](lync-server-2013-deleting-existing-network-region-routes.md)를 참조 하세요.

<div>

## <a name="to-create-a-network-region-route"></a>네트워크 지역 경로를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 경로**를 클릭 합니다.

4.  **지역 경로** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 영역 경로**에서 **이름** 필드에 값을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 값은 Microsoft Lync Server 2013 배포 내에서 고유 해야 합니다.

    
    </div>

6.  **네트워크 지역 \#1** 드롭다운 목록에서이 경로로 연결할 두 지역 중 하나를 선택 합니다.

7.  **네트워크 지역 \#2** 드롭다운 목록에서이 경로의 다른 지역을 선택 합니다. 이 지역은 네트워크 지역 \#1에 대해 선택한 지역과 달라 야 합니다.

8.  **네트워크 영역 링크** 목록 상자를 사용 하 여 경로에 지역 링크를 추가 합니다. **추가** 단추를 클릭 하 여 **지역 링크** 페이지를 표시 합니다. 이 경로에 추가할 지역 링크를 클릭 한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>추가</STRONG> 단추를 계속 클릭 하 여 다른 링크를 추가 하거나 링크를 선택 하 고 <STRONG>제거</STRONG> 를 클릭 하 여 링크를 제거 합니다.

    
    </div>

9.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>네트워크 지역 경로를 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 경로**를 클릭 합니다.

4.  **지역 경로** 페이지에서 수정 하려는 지역 경로를 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **지역 경로 편집**에서이 경로 또는 경로와 연결 된 지역 링크를 통해 연결 된 영역을 수정할 수 있습니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 기존 네트워크 지역 경로 삭제](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

