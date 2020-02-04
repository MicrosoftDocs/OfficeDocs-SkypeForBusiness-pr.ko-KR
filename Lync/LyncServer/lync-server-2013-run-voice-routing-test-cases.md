---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Lync Server 2013에서 음성 라우팅 테스트 사례 실행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

음성 라우팅 테스트 사례 도구 모음에서 모든 테스트 사례를 실행 하거나 하나 이상의 선택 된 테스트 사례를 실행할 수 있습니다.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>모든 음성 라우팅 테스트 사례를 실행 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.

4.  **음성 라우팅 테스트** 페이지에서 **작업** 을 클릭 한 다음 **모두 실행**을 클릭 합니다.
    
    각 테스트 사례의 합격 또는 불합격 상태는 **합격/불합격** 열에 표시 됩니다. 테스트 사례가 아직 실행 되지 않은 경우에는 **성공/실패** 열에 N/a가 표시 됩니다.

5.  ) 각 테스트 사례에 대 한 자세한 결과를 보려면 테스트 사례 이름을 두 번 클릭 합니다. **테스트 사례 편집** 페이지의 오른쪽에 있는 회색 영역에 결과가 표시 됩니다.
    
    1.  **테스트 결과:** 테스트 사례 실행의 전체 통과 또는 실패 상태입니다.
    
    2.  **정규화 규칙:** 해당 번호와 일치 하는이 테스트 사례에 대해 선택한 다이얼 플랜의 첫 번째 정규화 규칙 ( **번호를 테스트** 필드에 입력 한 값)입니다.
    
    3.  **정규화 된 번호:** 정규화 규칙으로 번역 한 후의 전화 번호 값입니다.
    
    4.  **첫 번째 PSTN 사용:** 전화를 건 번호와 일치 하는이 테스트 사례에 대해 선택한 음성 정책의 첫 번째 PSTN (공개 전화 네트워크) 사용 레코드입니다.
    
    5.  **첫 번째 경로:** 첫 번째 PSTN 사용 레코드에서 전화 번호와 일치 하는 첫 번째 음성 경로입니다.
        
        <div>
        

        > [!NOTE]  
        > 예상 되는 <STRONG>PSTN 사용 레코드</STRONG> 및 <STRONG>예상 경로</STRONG> 필드는 음성 라우팅 테스트 사례 구성에서 선택 사항입니다. 테스트 사례에서 이러한 값을 지정 하지 않으면 테스트 결과의 해당 필드가 비어 있게 됩니다.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>하나 이상의 선택한 음성 라우팅 테스트 사례를 실행 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **음성 라우팅 테스트**를 클릭 합니다.

4.  **음성 라우팅 테스트** 페이지에서 실행할 테스트 사례의 이름을 클릭 합니다.

5.  **작업** 메뉴에서 **선택 실행**을 클릭 합니다.
    
    각 테스트 사례의 합격 또는 불합격 상태는 **합격/불합격** 열에 표시 됩니다. 테스트 사례가 아직 실행 되지 않은 경우에는 **성공/실패** 열에 N/a가 표시 됩니다.

6.  ) 각 테스트 사례에 대 한 자세한 결과를 보려면 테스트 사례 이름을 두 번 클릭 합니다. **테스트 사례 편집** 페이지의 오른쪽에 있는 회색 영역에 결과가 표시 됩니다.
    
    1.  **테스트 결과:** 테스트 사례 실행의 전체 통과 또는 실패 상태입니다.
    
    2.  **정규화 규칙:** 해당 번호와 일치 하는이 테스트 사례에 대해 선택한 다이얼 플랜의 첫 번째 정규화 규칙 ( **번호를 테스트** 필드에 입력 한 값)입니다.
    
    3.  **정규화 된 번호:** 정규화 규칙으로 번역 한 후의 전화 번호 값입니다.
    
    4.  **첫 번째 PSTN 사용:** 전화를 건 번호와 일치 하는이 테스트 사례에 대해 선택한 음성 정책의 첫 번째 PSTN 사용 레코드입니다.
    
    5.  **첫 번째 경로:** 첫 번째 PSTN 사용 레코드에서 전화 번호와 일치 하는 첫 번째 음성 경로입니다.
        
        <div>
        

        > [!NOTE]  
        > 예상 되는 <STRONG>PSTN 사용 레코드</STRONG> 및 <STRONG>예상 경로</STRONG> 필드는 음성 라우팅 테스트 사례 구성에서 선택 사항입니다. 테스트 사례에서 이러한 값을 지정 하지 않으면 테스트 결과의 해당 필드가 비어 있게 됩니다.

        
        </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)  
[Lync Server 2013에서 음성 라우팅 테스트 실행](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

