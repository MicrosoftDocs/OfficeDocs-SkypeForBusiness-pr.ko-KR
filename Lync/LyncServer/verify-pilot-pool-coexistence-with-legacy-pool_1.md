---
title: 레거시 풀로 파일럿 풀 동시 사용 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73f8d25237d7d056282cc7c88685802eb50f16
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>레거시 풀로 파일럿 풀 동시 사용 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Office Communications Server 2007 R2 관리 도구의 풀 확인

1.  Office Communications Server 2007 R2 관리 도구를 엽니다.

2.  **포리스트** 노드를 확장하고 **Standard Edition 서버** 또는 **엔터프라이즈 풀** 노드를 확장한 후 풀 또는 서버 이름을 확장합니다.

3.  풀에서 Office Communications Server 2007 R2 서비스가 실행 되 고 있는지 확인 합니다.
    
    ![Office Communications Server 2007 R2 관리 콘솔](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 관리 콘솔")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Lync Server 2013 제어판에서 파일럿 풀 확인

1.  CsAdministrator 역할의 구성원 인 사용자 계정에서 Lync Server 2013 프런트 엔드 서버에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  **토폴로지**를 클릭합니다.

4.  배포한 서버가 파일럿 풀에 있는지 확인합니다.
    
    ![Lync Server 제어판 토폴로지 페이지](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server 제어판 토폴로지 페이지")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Lync Server 2013 서비스가 시작 되었는지 확인

1.  Lync Server 2013 프런트 엔드 서버의 **관리 도구** 그룹에서 **서비스** 애플릿을 엽니다.

2.  나열된 서비스가 다음 그림의 목록과 일치하는지 확인합니다.
    
    ![Lync services가 시작 된 서비스 페이지](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Lync services가 시작 된 서비스 페이지")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

