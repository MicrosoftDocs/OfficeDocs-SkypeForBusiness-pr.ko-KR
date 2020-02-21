---
title: 'Lync Server 2013: 발신자 번호 프레젠테이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8feb08297b5588e790917a346557e5e6434930
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a>Lync Server 2013의 발신자 번호 프레젠테이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

Lync Server 2010를 사용 하는 경우 호출 된 당사자의 전화 번호 (전화 번호)는 E. 164 형식에서 트렁크 피어에 필요한 로컬 전화 걸기 형식 (연결 된 게이트웨이, PBX (private branch exchange) 또는 SIP 트렁크)으로 변환 될 수 있습니다. 이 작업을 수행 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 변환 규칙을 하나 이상 정의 해야 합니다.

Lync Server 2013는 전화 건 사람의 전화 번호 (발신자가 통화 하는 전화 번호)를 트렁크 피어에 필요한 로컬 전화 걸기 형식으로 변환 하는 옵션을 소개 합니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.

<div id="sectionSection0" class="section">

**Lync Server 제어판을 사용 하 여 발신자 ID를 구성 하려면**

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭한 다음 **트렁크 구성**을 클릭합니다.

4.  **트렁크 구성** 페이지에서 기존 트렁크 (예: **전역** 트렁크)를 두 번 클릭 하 여 **트렁크 구성 편집** 대화 상자를 표시 합니다.

5.  발신자 번호를 구성 하려면 다음을 수행 합니다.
    
      - Enterprise Voice 배포에서 사용 가능한 모든 변환 규칙 목록에서 하나 이상의 규칙을 선택하려면 **선택**을 클릭합니다. **통화 번호 변환 규칙**에서 트렁크와 연결할 규칙을 클릭 하 고 **확인**을 클릭 합니다.
    
      - 새 변환 규칙을 정의하고 트렁크와 연결하려면 **새로 만들기**를 클릭합니다. 새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.
    
      - 트렁크와 이미 연결된 변환 규칙을 편집하려면 규칙 이름을 클릭한 다음 **자세한 정보 표시**를 클릭합니다. 자세한 내용은 배포 설명서에서 [Lync Server 2013의 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.
    
      - 기존 변환 규칙을 복사하여 새 규칙을 정의하는 시작 시점으로 사용하려면 규칙 이름을 클릭하고 **복사**를 클릭한 다음 **붙여넣기**를 클릭합니다. 자세한 내용은 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md)를 참조 하십시오.
    
      - 트렁크에서 변환 규칙을 제거하려면 규칙 이름을 강조 표시하고 **제거**를 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 연결된 트렁크 피어에서 변환 규칙을 구성한 경우에는 두 규칙이 충돌할 수 있으므로 변환 규칙을 트렁크와 연결하지 마십시오.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

