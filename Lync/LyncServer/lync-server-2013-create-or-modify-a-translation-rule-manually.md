---
title: 'Lync Server 2013: 수동으로 변환 규칙 만들기 또는 수정'
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
ms.openlocfilehash: f8225d5be1582add6a7dfd1a025b53da7c9b403b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a>Lync Server 2013에서 수동으로 변환 규칙 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-06_

일치하는 패턴 및 변환 규칙에 대한 정규식을 작성하여 변환 규칙을 정의하려면 다음 단계를 따르십시오. 또는 **변환 규칙 작성** 도구에서 값 집합을 입력 하 고 Lync Server 제어판을 사용 하도록 설정 하 여 해당 일치 패턴 및 변환 규칙을 생성할 수 있습니다. 자세한 내용은 [Lync Server 2013의 변환 규칙 작성 도구를 사용 하 여 변환 규칙 만들기 또는 수정을](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)참조 하십시오.

<div>

## <a name="to-define-a-translation-rule-manually"></a>변환 규칙을 수동으로 정의하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  변환 규칙 정의를 시작 하려면 [Lync server 2013에서 미디어 바이패스를 사용 하 여 온 트렁크 to media bypass](lync-server-2013-configure-a-trunk-with-media-bypass.md) 에서 10 단계까지 또는 [lync server 2013에서는 미디어 바이패스 없이 트렁크를 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md) 하는 방법을 설명 하는 단계를 수행 합니다.

4.  **새 변환 규칙** 또는 **변환 규칙 편집** 페이지의 **이름** 필드에 변환 대상 숫자 패턴을 설명하는 이름을 입력합니다.

5.  (선택 사항) **설명**에 변환 규칙에 대한 설명을 **미국 국제 시외 전화**와 같이 입력합니다.

6.  **변환 규칙 작성** 섹션 아래쪽의 **편집**을 클릭합니다.

7.  **정규식 입력**에 다음을 입력합니다.
    
      - **다음 패턴과 일치시킴**에 변환할 숫자와 일치시키는 데 사용할 패턴을 지정합니다.
    
      - **변환 규칙**에 변환된 숫자 형식의 패턴을 지정합니다.
    
    예를 들어 **이 패턴과 일치** 하 고 **변환 규칙**에서 **011 $1** 을 입력 ** ^ \\하면 + (\\d{9}\\d +) $** 가 + 441235551010를 011441235551010로 변환 합니다.

8.  **확인**을 클릭하여 변환 규칙을 저장합니다.

9.  **확인**을 클릭하여 트렁크 구성을 저장합니다.

10. **트렁크 구성** 페이지에서 **커밋**을 클릭하고 **모두 커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 변환 규칙을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다. 자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 변환 규칙 작성 도구를 사용 하 여 변환 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[Lync Server 2013의 미디어 바이패스로 트렁크 구성](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013에서 미디어 바이패스 없이 트렁크 구성](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013의 글로벌 미디어 바이패스 옵션](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

