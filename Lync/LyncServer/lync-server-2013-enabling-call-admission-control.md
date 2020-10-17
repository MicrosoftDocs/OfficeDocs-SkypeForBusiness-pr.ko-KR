---
title: 'Lync Server 2013: 통화 허용 제어를 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfe6ae76fd1f6b89178d101337f24ba0089dd35b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500985"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Lync Server 2013에서 통화 허용 제어 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

CAC(통화 허용 제어)는 사용 가능한 대역폭을 기반으로 오디오 및 비디오 전송에 제한을 둘 수 있는 지역, 사이트 및 서브넷의 네트워크입니다. CAC 네트워크를 구성한 후에는 대역폭 제한을 적용할 수 있도록 CAC를 설정해야 합니다. Lync Server 제어판을 사용 하 여이 작업을 수행할 수 있습니다.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Lync Server 제어판에서 CAC를 사용 하도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **전역**을 클릭합니다.

4.  **전역** 페이지에서 **전역** 구성을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 모든 Microsoft Lync Server 2013 배포에 대해 네트워크를 하나만 구성할 수 있으므로 목록에는 둘 이상의 네트워크 구성이 허용 되지 않습니다. 전역 구성은 이름을 바꿀 수 없습니다.

    
    </div>

5.  **편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.

6.  **전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택하고 **커밋**을 클릭합니다.

**커밋**을 클릭하면 구성 테스트가 실행됩니다. **전역 설정 편집** 대화 상자가 닫히고 **전역** 페이지로 돌아갑니다. 네트워크 구성에서 오류나 불일치 사항이 검색되어 구성이 제대로 작동하지 않는 경우(예: 모든 지역이 지역 간 경로를 통해 다른 모든 지역에 연결되어 있지 않은 경우)에는 경고가 표시됩니다.

네트워크 구성을 변경하는 경우 전역 구성을 열고 **커밋**을 클릭하여 유효성 검사를 실행할 수 있습니다. 먼저 CAC를 사용하지 않도록 설정할 필요는 없으며, 확인란을 선택한 대로 두고 **커밋**을 클릭하면 됩니다. 구성을 변경하지 않아도 언제든지 이 검사를 수행할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 허용 제어 개요](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server 2013의 통화 허용 제어 계획](lync-server-2013-planning-for-call-admission-control.md)  
[Lync Server 2013에서 통화 허용 제어 구성](lync-server-2013-configure-call-admission-control.md)  
[Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Get-csnetworkconfiguration을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

