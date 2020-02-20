---
title: 'Lync Server 2013: 네트워크 서브넷 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fa570d54a4c65c5f69782a57b4074043a26306
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

네트워크 서브넷은 해당 서브넷에 속한 호스트의 지리적 위치를 확인할 수 있도록 네트워크 사이트에 연결되어야 합니다. Lync Server 제어판을 사용 하 여 서브넷을 구성할 수 있습니다. Lync Server 제어판에서는 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다. 네트워크 서브넷을 삭제 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 서브넷 삭제](lync-server-2013-deleting-network-subnets.md)를 참조 하십시오.

Microsoft Lync Server 2013의 대부분의 배포에서 CAC (통화 허용 제어)가 구현 되는 경우 일반적으로 서브넷 수가 많습니다. 따라서 Lync Server 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다. 여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다. 두 cmdlet을 함께 사용하면 CSV(쉼표로 구분된 값) 파일에서 서브넷 설정을 읽어와서 여러 개의 서브넷을 동시에 만들 수 있습니다. .csv 파일에서 서브넷을 만드는 방법의 예는 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조하십시오.

<div>

## <a name="to-create-a-network-subnet"></a>네트워크 서브넷을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **서브넷**을 클릭합니다.

4.  **서브넷** 페이지에서 **다음**을 클릭합니다.

5.  **새 서브넷**의 **서브넷 ID** 필드에 값을 입력합니다. 이 ID는 IP 주소(예: 174.11.12.0)여야 하며 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.

6.  **마스크** 필드에 1에서 32 사이의 숫자 값을 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 값은 작성 중인 서브넷에 적용할 비트 마스크입니다.

    
    </div>

7.  **네트워크 사이트 ID**에서 이 서브넷이 속하는 사이트를 선택합니다.

8.  (선택 사항) 이름만으로는 표현할 수 없는 이 서브넷에 대한 자세한 정보를 제공하려면 **설명** 필드에 값을 입력합니다.

9.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-modify-a-network-subnet"></a>네트워크 서브넷을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **서브넷**을 클릭합니다.

4.  **서브넷** 페이지에서 수정할 서브넷을 클릭합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.

6.  **서브넷 편집** 페이지에서 비트 마스크, 연결된 네트워크 사이트 또는 설명을 수정할 수 있습니다. 비트 마스크를 수정하는 경우에도 서브넷 ID는 서브넷으로 정의된 IP 주소 범위의 첫 번째 주소여야 합니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 서브넷 삭제](lync-server-2013-deleting-network-subnets.md)  


[Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[새-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[설정-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[제거-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

