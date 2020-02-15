---
title: 'Lync Server 2013: 수동으로 정규화 규칙 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 305369719631361e0e8f8d9e9d12101fbdbfb1e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-22_

정규화 규칙을 수동으로 만들거나 수정하려면 다음 단계를 수행합니다. Lync Server 제어판에서 정규화 규칙 작성을 사용 하 여 정규화 규칙을 만들거나 수정 하려면 [Lync server 2013에서 작성 a 정규화 규칙을 사용 하 여 정규화 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)참조 하십시오.

<div>

## <a name="to-define-a-normalization-rule-manually"></a>정규화 규칙을 수동으로 정의하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  반드시 [Lync server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 의 단계를 수행 하거나 [lync server 2013에서 다이얼 플랜을 수정](lync-server-2013-modify-a-dial-plan.md)합니다.

4.  **새 정규화 규칙** 또는 **정규화 규칙 편집**의 **이름**에 정규화 중인 숫자 패턴을 설명하는 이름을 입력합니다(예: 정규화 규칙의 이름을 **5DigitExtension**으로 지정).

5.  (선택 사항) **설명** 필드에 정규화 규칙에 대한 설명을 입력합니다(예: "Translates 5-digit extensions").

6.  **정규화 규칙 작성**에서 **편집**을 클릭합니다.

7.  **정규식 입력**에 다음을 입력합니다.
    
      - **다음 패턴과 일치시킴**에서 전화 건 전화 번호와 일치시키는 데 사용할 패턴을 지정합니다.
    
      - **변환 규칙**에서 변환된 E.164 전화 번호 형식에 대한 패턴을 지정합니다.
    
    예를 들어 **변환 규칙**에서 **이 패턴과 일치** 하는 **^ (\\d{7}) $** 및 **+ 1425 $1** 을 입력 하면 규칙은 5550100에서 + 14255550100로 정규화 됩니다.

8.  (선택 사항) 정규화 규칙의 결과가 조직 내부의 전화 번호가 되는 경우 **내부 확장**을 선택합니다.

9.  (선택 사항) 정규화 규칙을 테스트할 번호를 입력한 다음 **이동**을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.
    
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


[Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
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

