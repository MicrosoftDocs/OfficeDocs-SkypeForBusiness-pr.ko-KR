---
title: 'Lync Server 2013: 네트워크 서브넷 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 서브넷 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

다음 절차를 사용 하 여 서브넷을 삭제할 수 있습니다. Lync Server 제어판에서 네트워크 서브넷을 만들거나 수정 하거나 삭제할 수 있습니다. 네트워크 서브넷을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정을](lync-server-2013-create-or-modify-network-subnets.md)참조 하세요.

Microsoft Lync Server 2013에서 호출 허용 제어 (CAC)가 구현 되는 대부분의 배포에서는 일반적으로 많은 수의 서브넷이 있습니다. 이 때문에 Lync Server 관리 셸에서 서브넷을 구성 하는 것이 가장 좋습니다. 여기서는 Windows PowerShell cmdlet **가져오기-CSV**와 함께 **새 csnetworksubnet** 을 호출할 수 있습니다. 이러한 cmdlet을 함께 사용 하 여 쉼표로 구분 된 값 (.csv) 파일의 서브넷 설정을 읽고 동시에 여러 개의 서브넷을 만들 수 있습니다. .Csv 파일에서 서브넷을 만드는 방법에 대 한 예는 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.

<div>

## <a name="to-delete-a-network-subnet"></a>네트워크 서브넷을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **서브넷**을 클릭 합니다.

4.  **서브넷** 페이지에서 삭제 하려는 서브넷을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 둘 이상의 서브넷을 삭제할 수 있습니다. 이 작업을 수행 하려면 ctrl 키를 누른 채 여러 서브넷을 선택 합니다. 또는 모든 서브넷을 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 서브넷 만들기 또는 수정](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

