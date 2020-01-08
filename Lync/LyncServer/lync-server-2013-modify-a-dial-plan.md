---
title: 'Lync Server 2013: 다이얼 플랜 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd6cc46d6e3317ca678b20e86c546db7dcc94fcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>Lync Server 2013에서 다이얼 플랜 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

기존 다이얼 플랜을 수정 하려면 다음 절차의 단계를 수행 합니다. 새 다이얼 플랜을 만들려는 경우 [Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)를 참조 하세요.

<div>

## <a name="to-modify-a-dial-plan"></a>다이얼 플랜을 수정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **다이얼 플랜**을 클릭 합니다.

4.  **다이얼 플랜** 페이지에서 다이얼 플랜 이름을 두 번 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 다이얼 플랜을 만들 때 다이얼 플랜 범위와 이름을 설정 했습니다. 변경할 수 없습니다.

    
    </div>

5.  ) **다이얼 플랜 편집**에서 **이름** 필드에 표시 되는 동일한 이름을 사용 하 여 미리 채워져 있는 **간단한 이름** 필드를 편집 하 여 다이얼 플랜이 적용 되는 사이트, 서비스 또는 사용자를 반영 하는 더 설명적인 이름을 지정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>단순한 이름은</STRONG> Lync Server 2013 배포 내의 모든 다이얼 플랜에서 고유 해야 합니다. 영문자 또는 숫자, 하이픈 (-), 마침표 (.), 더하기 기호 (+) 또는 밑줄 (_) 일 수 있는 256 유니코드 문자는 초과할 수 없습니다.<BR><STRONG>간단한 이름</STRONG> 필드에는 공백을 사용할 수 없습니다.

    
    </div>

6.  ) **설명** 필드에 다이얼 플랜에 대 한 설명 정보를 입력 합니다.

7.  ) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용 하려는 경우 **전화 접속 회의 영역**을 지정 합니다. 전화 접속 액세스 번호에이 다이얼 플랜을 사용 하지 않으려면이 필드를 비워 둡니다.
    
    <div>
    

    > [!NOTE]  
    > 전화 접속 회의 액세스 번호는 하나 이상의 다이얼 플랜에 연결 하는 데 필요 합니다.

    
    </div>

8.  ) 외부 회선 (예: 9)을 가져오기 위해 사용자가 하나 이상의 추가 행간 번호를 사용 해야 하는 경우에만 **external access 접두사** 필드에 값을 지정 합니다. 접두사 값은 최대 4 자 ( \# \*즉,, 0-9)에 입력할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 외부 액세스 접두사를 지정 하는 경우 접두사를 수용할 수 있는 새 정규화 규칙을 만들 필요가 없습니다.

    
    </div>

9.  다이얼 플랜에 대 한 정규화 규칙을 연결 하 고 구성 합니다.
    
      - 엔터프라이즈 음성 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다. **정규화 규칙 선택** 대화 상자에서 다이얼 플랜에 연결 하려는 규칙을 강조 표시 한 다음 **확인**을 클릭 합니다.
    
      - 새 정규화 규칙을 정의 하 고 다이얼 플랜에 연결 하려면 **새로 만들기**를 클릭 합니다. 새 규칙을 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하세요.
    
      - 다이얼 플랜에 이미 연결 된 정규화 규칙을 편집 하려면 규칙 이름을 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다. 규칙 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하세요.
    
      - 기존 정규화 규칙을 복사 하 여 새 규칙을 정의 하는 출발점으로 사용할 수 있도록 규칙 이름을 강조 표시 하 고 **복사**를 클릭 한 다음 **붙여넣기**를 클릭 합니다. 복사본 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하세요.
    
      - 다이얼 플랜에서 정규화 규칙을 제거 하려면 규칙 이름을 강조 표시 하 고 **제거**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 각 다이얼 플랜에는 하나 이상의 관련 정규화 규칙이 있어야 합니다. 다이얼 플랜에 필요한 모든 정규화 규칙을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013에서 다이얼 플랜 및 정규화 규칙</A> 을 참조 하세요.

    
    </div>

10. 다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬 되어 있는지 확인 합니다. 목록에서 규칙의 위치를 변경 하려면 규칙 이름을 강조 표시 한 다음 위쪽 또는 아래쪽 화살표를 클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server는 위에서 아래로 표준화 규칙 목록을 트래버스 하 고, 전화 번호와 일치 하는 첫 번째 규칙을 사용 합니다. 전화 거는 번호가 둘 이상의 정규화 규칙을 충족 하도록 다이얼 플랜을 구성한 경우 더 제한적인 규칙이 덜 제한적인 규칙 보다 먼저 정렬 되어 있는지 확인 합니다.<BR>기본 <STRONG>모든 정규화 유지</STRONG> 규칙 <STRONG>^ (\d{11}) $</STRONG> 는 11 자리 숫자와 일치 합니다. 예를 들어 1425으로 시작 하는 11 자리 숫자와 일치 하는 정규화 규칙을 추가 하는 경우에는 <STRONG>모두 유지</STRONG> 가 보다 제한적인 <STRONG>^ ({7}1425) $</STRONG> rule 아래에 정렬 되어 있는지 확인 합니다.

    
    </div>

11. ) 번호를 입력 하 여 다이얼 플랜을 테스트 하 고 **이동을**클릭 합니다. 테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.
    
    <div>
    

    > [!NOTE]  
    > 아직 테스트를 통과 하지 않은 다이얼 플랜을 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.

    
    </div>

12. **확인**을 클릭합니다.

13. **다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 다이얼 플랜을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

