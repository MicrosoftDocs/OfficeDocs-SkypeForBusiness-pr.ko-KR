---
title: 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02bbebae55504fcc27550bae3b90d7fca662a487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

Lync Server 제어판에서 정규화 규칙을 만들거나 수정 하려면 다음 단계를 완료 합니다. 또는 정규화 규칙을 수동으로 만들거나 수정 하려면 [Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)참조 하십시오.

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>정규화 규칙 작성을 사용 하 여 규칙을 정의 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  반드시 [Lync server 2013에서 11 단계까지 만든 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 의 단계를 수행 하거나 [lync server 2013에서 10 단계까지 다이얼 플랜을 수정](lync-server-2013-modify-a-dial-plan.md) 합니다 .를 참조 하세요.

4.  **새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 으로 정규화 되는 번호 패턴을 설명 하는 이름 (예: **: 5digitextension**)을 입력 합니다.

5.  반드시 **설명**에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 내선 번호 변환").

6.  **정규화 규칙 작성**의 다음 필드에 값을 입력 합니다.
    
      - **시작 숫자**   (선택 사항) 패턴을 일치 시킬 전화 건 번호의 선행 숫자를 지정 합니다. 예를 들어 425로 시작 하는 전화 번호를 패턴으로 일치 시키려면 **425** 을 입력 합니다.
    
      - **길이**   일치 하는 패턴의 자릿수를 지정 하 고 패턴을이 길이와 정확히 일치 시킬 것인지, 아니면 적어도이 길이에 해당 하는 전화 건 번호를 지정할지, 전화 건 번호와 일치 하는 것을 선택 합니다.
    
      - **제거할 숫자 (**   선택 사항) 패턴을 일치 시킬 전화 건 번호에서 제거할 시작 자릿수를 지정 합니다.
    
      - **추가할 숫자 (**   선택 사항) 패턴을 일치 시킬 전화 건 번호에 추가할 숫자를 지정 합니다.
    
    이러한 필드에 입력 하는 값은 일치 및 **변환 규칙** **에 대 한 패턴** 에 반영 됩니다. 예를 들어 **시작 자리** 를 비워 두면 **길이** 필드에 **7** 을 입력 하 고, **정확히**선택 하 고, **제거할 숫자**에 **0** 을 지정 하 여 **일치 시킬 패턴** 의 정규식을 찾습니다.
    
    **^ (\\d{7}) $**

7.  **변환 규칙**에서 다음과 같이 변환 된 E. 164 전화 번호 형식에 대 한 패턴을 지정 합니다.
    
      - 일치 패턴에 지정 된 자릿수를 나타내는 값입니다. 예를 들어 일치 하는 패턴이 **^ (\\d{7}) $** 이 고 변환 규칙에서 **$1** 은 7 자리 전화 걸기 번호를 나타냅니다.
    
      - 반드시 숫자를 **추가할** 숫자 필드에 값을 입력 하 여 변환 된 번호 앞에 추가할 자릿수를 지정 합니다 (예: **+ 1425**).
    
    예를 들어 **일치 시킬 패턴이** **\\^ (d{7}) $** 를 포함 하는 경우 전화 건 번호의 패턴으로 **+ 1425 $1** 이 E. 164 전화 번호의 패턴으로 포함 된 경우 규칙은 5550100에서 + 14255550100로 정규화 됩니다. ****

8.  (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장**을 선택합니다.

9.  반드시 숫자를 입력 하 여 정규화 규칙을 테스트 한 다음 **이동을**클릭 합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.
    
    <div>
    

    > [!NOTE]
    > 아직 테스트를 통과하지 않는 정규화 규칙을 저장한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.

    
    </div>

10. 정규화 규칙을 저장하려면 **확인**을 클릭합니다.

11. 다이얼 플랜을 저장하려면 **확인**을 클릭합니다.

12. **다이얼 플랜** 페이지에서 **커밋**을 클릭한 다음 **모두 커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]
    > 정규화 규칙을 만들거나 변경할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[Lync Server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md)  
[Lync Server 2013에서 다이얼 플랜 수정](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

