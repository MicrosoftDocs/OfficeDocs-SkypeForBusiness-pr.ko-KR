---
title: 'Lync Server 2013: 네트워크 서브넷 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

네트워크 서브넷이이 서브넷에 속한 호스트의 지리적 위치를 확인 하기 위해 네트워크 사이트와 연결 되어 있어야 합니다. Lync Server 제어판을 사용 하 여 서브넷을 구성할 수 있습니다. Lync Server 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다. 네트워크 서브넷을 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 서브넷 삭제](lync-server-2013-deleting-network-subnets.md)를 참조 하세요.

Microsoft Lync Server 2013에서 호출 허용 제어 (CAC)가 구현 되는 대부분의 배포에서는 일반적으로 많은 수의 서브넷이 있습니다. 이 때문에 Lync Server 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다. 여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다. 이러한 cmdlet을 함께 사용 하 여 쉼표로 구분 된 값 (.csv) 파일의 서브넷 설정을 읽고 동시에 여러 개의 서브넷을 만들 수 있습니다. .Csv 파일에서 서브넷을 만드는 방법에 대 한 예는 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.

<div>

## <a name="to-create-a-network-subnet"></a>네트워크 서브넷을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **서브넷**을 클릭 합니다.

4.  **서브넷** 페이지에서 **새로 만들기**를 클릭 합니다.

5.  **새 서브넷**에서 **서브넷 ID** 필드에 값을 입력 합니다. 이는 IP 주소 (예: 174.11.12.0) 여야 하며 서브넷에 정의 된 IP 주소 범위에서 첫 번째 주소 여야 합니다.

6.  **마스크** 필드에 1부터 32 까지의 숫자 값을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 값은 만들려는 서브넷에 적용 되는 비트 마스크입니다.

    
    </div>

7.  **네트워크 사이트 ID**에서이 서브넷이 속한 사이트를 선택 합니다.

8.  ) 이름 만으로 표현할 수 없는이 서브넷에 대 한 자세한 정보를 제공 하려면 **설명** 필드에 값을 입력 합니다.

9.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>네트워크 서브넷을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **서브넷**을 클릭 합니다.

4.  **서브넷** 페이지에서 수정 하려는 서브넷을 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  **서브넷 편집** 페이지에서 비트 마스크, 관련 네트워크 사이트 또는 설명을 수정할 수 있습니다. 비트 마스크를 수정 하는 경우 서브넷 ID가 서브넷에 정의 된 IP 주소 범위에서 첫 번째 주소 여야 한다는 점에 유의 하세요.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 서브넷 삭제](lync-server-2013-deleting-network-subnets.md)  


[Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[새-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[CsNetworkSubnet 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

