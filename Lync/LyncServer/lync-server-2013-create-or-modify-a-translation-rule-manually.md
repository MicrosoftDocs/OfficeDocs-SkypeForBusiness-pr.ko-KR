---
title: 'Lync Server 2013: 수동으로 번역 규칙 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Lync Server 2013에서 수동으로 번역 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-06_

일치 패턴 및 번역 규칙에 대 한 정규식을 작성 하 여 번역 규칙을 정의 하려면 다음 단계를 따르세요. 또는 **번역 규칙 작성** 도구에서 값 집합을 입력 하 고 Lync Server 제어판을 사용 하 여 일치 하는 해당 패턴 및 번역 규칙을 생성할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)참조 하세요.

<div>

## <a name="to-define-a-translation-rule-manually"></a>수동으로 번역 규칙 정의

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  번역 규칙 정의를 시작 하려면 lync [server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md) 의 단계를 수행 하 고 lync server 2013에서 9 단계까지 [미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 합니다.

4.  **새 번역 규칙** 또는 **번역 규칙 편집** 페이지의 **이름** 필드에 번역할 번호 패턴을 설명 하는 이름을 입력 합니다.

5.  ) **설명**에 번역 규칙에 대 한 설명 (예: **US 국제 장거리 전화 걸기**)을 입력 합니다.

6.  **번역 규칙 작성** 섹션의 아래쪽에서 **편집** 을 클릭 합니다.

7.  **정규식 입력**에 다음을 입력 합니다.
    
      - **이 패턴과 일치**하는 경우 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다.
    
      - **번역 규칙**에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다.
    
    예를 들어 **이 패턴과 일치** 하는 ** ^ \\+{9}\\\\(d d +) $** 를 입력 하 고 **번역 규칙**에 **011 $1** 이 있으면 규칙에서 + 441235551010를 011441235551010로 변환 합니다.

8.  **확인** 을 클릭 하 여 번역 규칙을 저장 합니다.

9.  **확인** 을 클릭 하 여 트렁크 구성을 저장 합니다.

10. **트렁크 구성** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 번역 규칙을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 번역 규칙 작성 도구를 사용 하 여 번역 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
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

