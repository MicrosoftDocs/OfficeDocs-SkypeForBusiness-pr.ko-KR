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
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>Lync Server 2013에서 수동으로 정규화 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-22_

정규화 규칙을 수동으로 만들거나 수정 하려면 다음 단계를 완료 합니다. Lync Server 제어판에서 정규화 규칙 작성을 사용 하 여 정규화 규칙을 만들거나 수정 하려면 [Lync server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)참조 하세요.

<div>

## <a name="to-define-a-normalization-rule-manually"></a>정규화 규칙을 수동으로 정의 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  ) [Lync server 2013에서 다이얼 플랜 만들기](lync-server-2013-create-a-dial-plan.md) 의 단계를 따르고 [lync server 2013에서 다이얼 플랜을 수정](lync-server-2013-modify-a-dial-plan.md)합니다.

4.  **새 정규화 규칙** 또는 **정규화 규칙 편집**에서 **이름** 에 정규화 되는 번호 패턴을 설명 하는 이름 (예: 정규화 규칙 **5DigitExtension**의 이름)을 입력 합니다.

5.  ) **설명** 필드에 정규화 규칙에 대 한 설명을 입력 합니다 (예: "5 자리 확장명 변환").

6.  **정규화 규칙 작성**에서 **편집**을 클릭 합니다.

7.  **정규식 입력**에 다음을 입력 합니다.
    
      - **이 패턴과 일치**하는 경우 전화를 거는 전화 번호와 일치 하는 데 사용할 패턴을 지정 합니다.
    
      - **번역 규칙**에서 번역 된 전자 전화번호의 형식에 대 한 패턴을 지정 합니다.
    
    예를 들어 **이 패턴과 일치** 하는 **^{7}(\\d) $** 를 입력 하 고 **번역 규칙**에 **+ 1425 $1** 이 있으면 규칙이 5550100에서 + 14255550100로 정규화 됩니다.

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


[Lync Server 2013에서 정규화 규칙 작성을 사용 하 여 정규화 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
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

