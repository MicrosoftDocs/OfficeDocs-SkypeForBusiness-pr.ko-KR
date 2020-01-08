---
title: 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 527510ac9b683df191414f5dffe456353d9cf277
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Lync Server 제어판에서 정규화 규칙을 만들거나 수정 하려면 다음 단계를 완료 합니다. 또는 정규화 규칙을 수동으로 만들거나 수정 하려는 경우에는 [Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)참조 하세요.

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>정규화 규칙 빌드를 사용 하 여 규칙을 정의 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  ) [Lync server 2013에서](lync-server-2013-create-a-dial-plan.md) 11 단계 또는 [lync server 2013에서 10 단계까지 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md) 통해 다이얼 플랜 만들기의 단계를 따릅니다.

4.  **새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 에 정규화 되는 번호 패턴을 설명 하는 이름 (예: **5DigitExtension**)을 입력 합니다.

5.  ) **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 확장명 변환").

6.  **정규화 규칙 작성**에서 다음 필드에 값을 입력 합니다.
    
      - **시작**   번호 (선택 사항) 패턴을 일치 시킬 전화 거는 번호의 선행 자릿수를 지정 합니다. 예를 들어 패턴에서 425로 시작 하는 전화 번호를 일치 시키려면 **425** 을 입력 합니다.
    
      - **Length**   일치 하는 패턴의 자릿수를 지정 하 고 해당 패턴을이 길이에 정확 하 게 일치 시킬 것인지 아니면 최소이 길이의 전화 접속 번호와 일치 하는 항목을 선택 하거나 길이에 상관 없이 전화를 걸 수 있습니다.
    
      - **제거할 자릿수 (**   선택 사항) 패턴을 일치 시킬 전화 번호에서 제거할 시작 자릿수를 지정 합니다.
    
      - **더할 자릿수 (**   선택 사항) 패턴을 일치 시킬 전화 번호에 추가할 숫자를 지정 합니다.
    
    이러한 필드에 입력 하는 값은 일치 및 **번역 규칙** **에 따라 패턴** 에 반영 됩니다. 예를 들어 **시작 자릿수** 를 비워 두면 **길이** 필드에 **7** **을 입력 하 고,** **제거할 숫자**에 **0** 을 지정 하 고, **일치 시킬 패턴** 의 정규식은 다음과 같습니다.
    
    **^ (\\d{7}) $**

7.  **번역 규칙**에서 다음과 같이 변환 된 전자 164 전화번호의 형식에 대 한 패턴을 지정 합니다.
    
      - 일치 패턴에 지정 된 자릿수를 나타내는 값입니다. 예를 들어 일치 하는 패턴이 **^ (\\d{7}) $** 이 고 번역 규칙의 **$1** 에서 7 자리 전화 걸기 번호를 나타냅니다.
    
      - ) 숫자를 **추가할** 숫자 필드에 값을 입력 하 여 앞으로 변환할 숫자를 지정 합니다 (예: **+ 1425**).
    
    예를 들어 **일치 하는 패턴** 에 **^ (\\d{7}) $** 가 있는 경우, 전화를 걸고 **있는 번호** 의 패턴으로 **+ 1425 $1** 이 포함 된 경우이 규칙은 5550100에서 + 14255550100로 정규화 됩니다.

8.  ) 정규화 규칙이 조직 내부의 전화 번호를 반환 하는 경우 **내부 확장**을 선택 합니다.

9.  ) 번호를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다. 테스트 결과가 **테스트에 대 한 숫자 입력**아래에 표시 됩니다.
    
    <div>
    

    > [!NOTE]
    > 아직 테스트를 통과 하지 않은 정규화 규칙을 저장 한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.

    
    </div>

10. **확인** 을 클릭 하 여 정규화 규칙을 저장 합니다.

11. **확인** 을 클릭 하 여 다이얼 플랜을 저장 합니다.

12. **다이얼 플랜** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]
    > 정규화 규칙을 만들거나 변경할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013에서 다이얼 플랜 수정](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

