---
title: 'Lync Server 2013: 통화 허용 제어 사용'
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
ms.openlocfilehash: 1776cc173d7ddec50aae34e8316844d14f67b009
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a>Lync Server 2013에서 통화 허용 제어 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

통화 허용 제어 배포에 대 한 네트워크 설정을 구성한 후에는 CAC를 사용 하도록 설정 하 여 대역폭 정책을 적용 해야 합니다.

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [Get-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [제거-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>관리 셸을 사용 하 여 통화 허용 제어를 사용 하도록 설정 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  Set-csnetworkconfiguration cmdlet을 실행 하 여 네트워크에서 CAC를 사용 하도록 설정 합니다. 예를 들어 다음을 실행합니다.
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    네트워크에서 CAC를 사용 하지 않도록 설정 하려면 다음을 실행 합니다.
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 통화 허용 제어를 사용 하도록 설정 하려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  **전역** 탐색 단추를 클릭 합니다.

4.  목록에서 **전역** 을 클릭 한 다음 **편집** 메뉴에서 **세부 정보 표시** 를 선택 합니다.

5.  **전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 배포 전체에서 통화 허용 제어를 사용 하지 않도록 설정 하려면이 확인란의 선택을 취소 합니다.

    
    </div>

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

