---
title: 'Lync Server 2013: 네트워크 지역 링크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 링크 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

두 네트워크 지역 간의 링크를 CAC (call 허용 제어)의 일부로 구성할 수 있습니다. 네트워크 내의 영역은 실제 WAN (광역 네트워크) 연결을 통해 연결 됩니다. Lync Server 제어판을 사용 하 여 두 네트워크 지역 간의 링크를 정의 하 고 이러한 지역 간의 오디오 및 비디오 연결에 대 한 대역폭 제한을 설정할 수 있습니다. 기존 네트워크 지역 링크를 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 링크 삭제](lync-server-2013-deleting-network-region-links.md)를 참조 하세요.

<div>

## <a name="to-create-a-network-region-link"></a>네트워크 지역 링크를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 링크**를 클릭 합니다.

4.  **지역 링크** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 영역 링크**의 **이름** 필드에 값을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 값은 Lync Server 2013 배포 내에서 고유 해야 합니다.

    
    </div>

6.  **네트워크 지역 \#1** 드롭다운 목록에서 연결할 두 지역 중 하나를 선택 합니다.

7.  **네트워크 지역 \#2** 드롭다운 목록에서 연결할 다른 영역을 선택 합니다. 이 지역은 네트워크 지역 \#1에 대해 선택한 지역과 달라 야 합니다.

8.  ) 이러한 지역 간의 오디오 또는 비디오 통화에 대 한 대역폭 제한을 설정 하려면 **대역폭 정책** 드롭다운 목록에서 대역폭 정책 프로필을 선택 합니다.

9.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>네트워크 지역 링크를 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 링크**를 클릭 합니다.

4.  **지역 링크** 페이지에서 수정 하려는 지역 링크를 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **지역 편집 링크**에서 연결 된 영역이 나이 링크에 대 한 대역폭 정책 프로필을 수정할 수 있습니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 지역 링크 삭제](lync-server-2013-deleting-network-region-links.md)  


[새-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[-Csnetwork국가 링크 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-Csnetwork국가 링크](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
