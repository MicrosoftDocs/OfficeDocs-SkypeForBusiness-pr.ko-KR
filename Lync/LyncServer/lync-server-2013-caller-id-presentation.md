---
title: 'Lync Server 2013: 발신자 ID 프레젠테이션'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016913ad68865f7d93512cc7383f2cfb47497ebe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a>Lync Server 2013의 발신자 ID 프레젠테이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

Lync Server 2010을 사용 하면 호출 된 파티의 전화 번호 (전화 번호)를 트렁크 피어에 필요한 로컬 전화 걸기 형식 (연결 된 게이트웨이, 개인 분기 교환 (PBX) 또는 SIP 트렁크)으로 변환할 수 있습니다. 이렇게 하려면 요청 URI를 트렁크 피어로 라우팅하기 전에 변환 하는 하나 이상의 번역 규칙을 정의 해야 합니다.

Lync Server 2013는 전화 상대방의 전화 번호 (즉, 발신자가 전화를 거는 전화 번호)를 트렁크 피어에 필요한 지역 전화 걸기 형식으로 변환 하는 옵션도 소개 합니다. 예를 들어 다이얼 문자열의 시작 부분에서 + 44을 제거 하 고 0144으로 바꾸는 번역 규칙을 작성할 수 있습니다.

<div id="sectionSection0" class="section">

**Lync Server 제어판을 사용 하 여 발신자 ID를 구성 하려면**

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.

4.  **트렁크 구성** 페이지에서 기존 트렁크 (예: **전역** 트렁크)를 두 번 클릭 하 여 **트렁크 구성 편집** 대화 상자를 표시 합니다.

5.  발신자 ID 프레젠테이션을 구성 하려면 다음을 수행 합니다.
    
      - 엔터프라이즈 음성 배포에서 사용할 수 있는 모든 번역 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다. **전화 번호 번역 규칙**에서 트렁크와 연결할 규칙을 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 새 번역 규칙을 정의 하 고 트렁크에 연결 하려면 **새로 만들기**를 클릭 합니다. 새 규칙을 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 번역 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하세요.
    
      - 트렁크에 이미 연결 된 번역 규칙을 편집 하려면 규칙 이름을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 번역 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하세요.
    
      - 기존 번역 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용 하려면 규칙 이름을 클릭 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다. 자세한 내용은 [Lync Server 2013에서 번역 규칙 정의](lync-server-2013-defining-translation-rules.md)를 참조 하세요.
    
      - 트렁크에서 번역 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.
    
    <div>
    

    > [!WARNING]  
    > 두 규칙이 충돌할 수 있으므로 연결 된 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙과 트렁크를 연결 하지 마세요.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

