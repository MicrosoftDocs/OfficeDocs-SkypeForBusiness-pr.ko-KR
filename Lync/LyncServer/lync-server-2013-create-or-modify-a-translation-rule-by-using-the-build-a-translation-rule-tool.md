---
title: 번역 규칙 작성 도구를 사용 하 여 번역 규칙 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06f498af25dfd851bd2950ce08d5c66179b95ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a>Lync Server 2013에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

**번역 규칙 작성** 도구에 값 집합을 입력 하 고 Lync Server 제어판에서 해당 일치 패턴 및 번역 규칙을 생성 하도록 설정 하 여 번역 규칙을 정의 하려면 다음 단계를 따르세요. 또는 정규식을 수동으로 작성 하 여 일치 패턴 및 번역 규칙을 정의할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 수동으로 번역 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-translation-rule-manually.md)참조 하세요.

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>번역 규칙 작성 도구를 사용 하 여 규칙을 정의 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  번역 규칙 정의를 시작 하려면 lync [server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md) 의 단계를 수행 하 고 lync server 2013에서 9 단계까지 [미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 합니다.

4.  **새 번역 규칙** 또는 **번역 규칙 편집** 페이지의 **이름** 아래에서 번역할 번호 패턴을 설명 하는 이름을 입력 합니다.

5.  ) **설명**아래에 번역 규칙에 대 한 설명 (예: **US 국제 장거리 전화 걸기**)을 입력 합니다.

6.  대화 상자의 **번역 규칙 작성** 섹션에서 다음 필드에 값을 입력 합니다.
    
      - **시작 번호**: (선택 사항) 패턴을 일치 시킬 숫자의 선행 자릿수를 지정 합니다. 예를 들어이 **+** 필드에는 * 164 형식의 숫자와 일치 하도록 입력 합니다 (+로 시작).
    
      - **길이**: 일치 하는 패턴의 자릿수를 지정 하 고 해당 패턴이이 길이의 정확한 숫자, 최소 길이 또는 길이 중 어느 것을 일치 시킬 것인지 선택 합니다. 예를 **들어 11을 입력 하** 고 최소 11 자리 숫자로 이루어진 숫자와 일치 하도록 드롭다운 목록에서 **최소한** 을 선택 합니다.
    
      - **제거할 자릿수**: (선택 사항) 제거할 시작 숫자의 수를 지정 합니다. 예를 들어 **1** 을 입력 하 여 숫자 **+** 의 시작 부분에서 제거 합니다.
    
      - **더할 자릿수**: (선택 사항) 번역 된 숫자 앞에 추가할 숫자를 지정 합니다. 예를 들어 규칙을 적용할 때 이진수를 번역 된 번호로 앞에 표시 하려면 **011** 을 입력 합니다.
    
    이러한 필드에 입력 하는 값은 일치 및 **번역 규칙** 필드에 따라 **패턴** 에 반영 됩니다. 예를 들어 앞의 예제 값을 지정 하는 경우 **일치 하는 패턴** 필드의 결과 정규식은 다음과 같습니다.
    
    **^\\+ (\\d{9}\\d +) $**
    
    **번역 규칙** 필드는 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다. 이 패턴은 두 부분으로 구성 됩니다.
    
      - 일치 하는 패턴의 자릿수를 나타내는 값 (예: **$1**)
    
      - ) **추가할 숫자** 필드에 입력 하 여 앞에 입력할 수 있는 값
    
    앞의 예제 값을 사용 하 여 **번역 규칙** 필드에 **011 $1** 이 표시 됩니다.
    
    이 번역 규칙이 적용 되 면 + 441235551010이 011441235551010.

7.  **확인** 을 클릭 하 여 번역 규칙을 저장 합니다.

8.  **확인** 을 클릭 하 여 트렁크 구성을 저장 합니다.

9.  **트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]
    > 번역 규칙을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 수동으로 번역 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013의 글로벌 미디어 우회 옵션](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

