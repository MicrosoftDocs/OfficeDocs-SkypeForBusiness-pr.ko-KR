---
title: 'Lync Server 2013: 통화 허용 제어 기능 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e181c0fbc4c3794d14b364f6fd2affa4e4358f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a>Lync Server 2013에서 통화 허용 제어 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

통화 허용 제어 배포에 대한 네트워크 설정을 구성한 후 CAC를 사용하도록 설정하여 대역폭 정책을 적용해야 합니다.

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Get-csnetworkconfiguration을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>관리 셸을 사용하여 통화 허용 제어를 사용하도록 설정하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  Set-CsNetworkConfiguration cmdlet을 실행하여 네트워크에서 CAC를 사용하도록 설정합니다. 예를 들어 다음을 실행합니다.
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    네트워크에서 CAC를 사용하지 않도록 설정하려면 다음을 실행합니다.
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용하여 통화 허용 제어를 사용하도록 설정하려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  **전역** 탐색 단추를 클릭합니다.

4.  목록에서 **전역**을 클릭한 다음 **편집** 메뉴에서 **세부 정보 표시**를 선택합니다.

5.  **전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택합니다.
    
    <div>
    

    > [!NOTE]  
    > 배포 전체에서 통화 허용 제어를 사용하지 않도록 설정하려면 이 확인란을 선택 취소합니다.

    
    </div>

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

