---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c706064cbe7319d3cb485b0bb1ecf6d34902edde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a>Lync Server 2013에서 음성 라우팅 테스트 사례 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-07_

<div>

## <a name="to-create-a-test-case"></a>테스트 사례를 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.

4.  **음성 라우팅 테스트** 페이지에서 **새로** 만들기를 클릭 하 여 새 테스트 사례를 만듭니다.

5.  **이름**에 테스트 사례에 대 한 고유한 이름을 입력 합니다.
    
    이름은 엔터프라이즈 음성 배포의 모든 음성 라우팅 테스트 사례에서 고유 해야 합니다. 길이는 최대 32 자로 지정할 수 있으며, 백슬래시 (\\), 마침표 (.), 밑줄 (\_) 외에도 영숫자 문자를 포함할 수도 있습니다.

6.  **전화를 걸 번호**에서이 테스트 사례에 대해 지정 하는 라우팅 구성을 테스트 하는 데 사용할 전화 번호를 입력 합니다. 다이얼 플랜, 경로 및 음성 정책에 따라이 번호는 표준화 되어 출력으로 표시 됩니다.

7.  **다이얼 플랜** 목록에서 테스트를 실행할 때 사용할 다이얼 플랜을 선택 합니다. 전역 다이얼 플랜을 기본값으로 합니다.

8.  **음성 정책** 목록에서 테스트를 실행할 때 사용할 음성 정책을 선택 합니다. 기본값은 전역 음성 정책입니다.

9.  **번역 후 예상한**형식으로 전화 번호를 입력 하세요. 선택한 다이얼 플랜에서 일치 하는 첫 번째 정규화 규칙으로 번역 된 후 테스트 하는 전화 번호의 값입니다. 테스트 사례를 실행할 때 테스트 하는 숫자가 **예상한 번역**값을 반환 하지 않으면 테스트에 실패 합니다.

10. ) **필요한 pstn 사용** 목록에서 지정 된 다이얼 플랜 및 음성 정책을 기반으로 테스트 사례를 실행할 때 사용 될 것으로 예상 되는 pstn (공용 전환 전화 네트워크) 사용 레코드를 선택할 수 있습니다. 다른 PSTN 사용 레코드가 사용 되는 경우 테스트에 실패 합니다.

11. ) 예상 되는 **경로** 목록에서 지정 된 다이얼 플랜 및 음성 정책을 기반으로 테스트 사례를 실행할 때 사용할 예상 되는 음성 경로를 선택할 수 있습니다. 다른 음성 경로를 사용 하는 경우 테스트에 실패 합니다.

12. ) **실행** 을 클릭 하 여 테스트 사례를 실행 합니다. 결과는 페이지의 오른쪽 창에 표시 됩니다.

13. **확인**을 클릭합니다.

14. **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 음성 라우팅 테스트 사례를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.

    
    </div>
    
    테스트에 사용 되는 다이얼 플랜에서 더하기 기호 (예: + 12065551219)로 시작 하는 전화 번호를 정규화 하면 해당 요금제로 인해 음성 라우팅 테스트가 실패할 수 있습니다. (다이얼 플랜 및 음성 경로는 작동 하는 반면, 실제로 테스트-CsDialPlan 플랜은 성공 합니다. 그러나 음성 라우팅 테스트에 실패할 가능성이 있습니다. 이는 음성 경로 테스트 시 염두에 두어야 할 사항입니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기](lync-server-2013-export-voice-routing-test-cases.md)  
[Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기](lync-server-2013-import-voice-routing-test-cases.md)  


[Lync Server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md)  
[Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

