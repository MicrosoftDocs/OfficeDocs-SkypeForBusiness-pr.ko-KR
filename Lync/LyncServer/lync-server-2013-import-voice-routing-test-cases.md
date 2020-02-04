---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 013860ea52773f4109c56bd71d37a9f4b8938225
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

테스트 사례를 통해 조직의 음성 경로를 테스트 하는 데 사용할 수 있는 번호와 사용할 다이얼 플랜 및 음성 정책 등을 정의 하 고 Lync Server 2013에서 제공 된 번호가 succes 수 있는지 확인할 수 있습니다. 라우터를 PSTN 네트워크로 완전히 라우팅할 수 있습니다.

Lync Server 제어판을 사용 하 여 만들 수 있는 테스트 사례는 일반적으로 해당 사례가 처음 만들어지고 실행 된 서버에만 저장 됩니다. 그러나 이러한 테스트 사례를 XML 파일로 내보낸 다음 (vtest 확장명 사용) 다른 서버에서 가져올 수 있습니다. 이렇게 하면 토폴로지의 여러 지점에 있는 여러 컴퓨터에서 동일한 테스트를 실행할 수 있습니다.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>음성 라우팅 테스트 사례를 가져오려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.

4.  **작업** 메뉴에서 **테스트 사례 가져오기를**클릭 합니다.

5.  가져오려는 테스트 사례 파일 (vtest)을 찾은 다음 **열기**를 클릭 합니다.

6.  **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > Vtest 파일을 가져올 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 테스트 사례를 게시 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

