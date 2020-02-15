---
title: 'Lync Server 2013: 다이얼 플랜 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63e34146bd5f0d69576a21f8cc0bf5651632bec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a>Lync Server 2013에서 다이얼 플랜 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-24_

새 다이얼 플랜을 만들려면 다음 절차의 단계를 수행 합니다. 다이얼 플랜을 편집 하려면 [Lync Server 2013에서 다이얼 플랜 수정을](lync-server-2013-modify-a-dial-plan.md)참조 하세요.

<div>

## <a name="to-create-a-dial-plan"></a>다이얼 플랜을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭한 다음 **다이얼 플랜**을 클릭합니다.

4.  **다이얼 플랜** 페이지에서 **새로 만들기** 를 클릭 하 고 다이얼 플랜에 대 한 범위를 선택 합니다.
    
      - **사이트 다이얼 플랜** 은 사용자 또는 그룹을 제외한 전체 사이트에 적용 됩니다. 다이얼 플랜의 범위에 대해 **사이트** 를 선택 하는 경우 **사이트 선택** 대화 상자에서 사이트를 선택 해야 합니다. 사이트에 대 한 다이얼 플랜을 이미 만든 경우 사이트 **선택** 대화 상자에 해당 사이트가 나타나지 않습니다.
    
      - **풀 다이얼 플랜** 은 PSTN (공중 전화망) 게이트웨이 또는 등록자에 게 적용할 수 있습니다. 다이얼 플랜의 범위에 대해 **풀** 을 선택 하는 경우 **서비스 선택** 대화 상자에서 PSTN 게이트웨이 또는 등록자를 선택 합니다. 서비스에 대 한 다이얼 플랜을 이미 만든 경우 (PSTN 게이트웨이 또는 등록자) 해당 서비스가 목록에 표시 되지 않습니다.
    
      - **사용자 다이얼 플랜** 은 지정 된 사용자나 그룹에 적용할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 다이얼 플랜 범위는 선택한 후에 변경할 수 없습니다.

    
    </div>

5.  사용자 다이얼 플랜을 만드는 경우 **새 다이얼 플랜** 대화 상자의 **이름** 필드에 설명 하는 이름을 입력 합니다. 이 이름이 저장 된 후에는 변경할 수 없습니다.
    
    <div>
    

    > [!NOTE]  
    > 사이트 다이얼 플랜의 경우 <STRONG>이름</STRONG> 필드에 사이트 이름이 미리 채워져 있어 변경할 수 없습니다.<BR>풀 다이얼 플랜의 경우 <STRONG>이름</STRONG> 필드에 PSTN 게이트웨이나 등록자 이름이 미리 채워져 있어 변경할 수 없습니다.

    
    </div>

6.  **단순한 이름** 필드는 **이름** 필드에 나타나는 같은 이름으로 미리 채워집니다. 필요한 경우이 필드를 편집 하 여 다이얼 플랜을 적용할 사이트, 서비스 또는 사용자를 나타내는 보다 설명적인 이름을 지정할 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>단순 이름은</STRONG> Lync Server 배포 내의 모든 다이얼 플랜에서 고유 해야 합니다. 256 유니코드 문자를 초과할 수 없으며 각각은 영문자 또는 숫자, 하이픈 (-), 마침표 (.) 또는 밑줄 (_)이 될 수 있습니다.<BR><STRONG>지원 되지 않는</STRONG> 문자에는 RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt). <STRONG>단순 이름</STRONG> 에서 <STRONG>지원 되지</STRONG> 않는 예약 된 문자에는 다음이 포함 됩니다.<BR>";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  반드시 **설명** 필드에 다이얼 플랜에 대 한 추가 정보를 입력할 수 있습니다.

8.  (선택 사항) 이 다이얼 플랜을 전화 접속 액세스 번호의 지역으로 사용하려면 **전화 접속 회의 지역**을 지정합니다. 전화 접속 액세스 번호에 이 다이얼 플랜을 사용하지 않으려면 이 필드를 비워 둡니다.
    
    <div>
    

    > [!NOTE]  
    > 전화 접속 회의 액세스 번호를 하나 이상의 다이얼 플랜과 연결하려면 전화 접속 회의 지역이 필요합니다.

    
    </div>

9.  반드시 외부 회선을 사용 하 여 사용자가 하나 이상의 추가 선행 번호 (예: 9)를 눌러야 하는 경우에만 **해당 필드에** 값을 지정 합니다. 접두사 값에 최대 4 자 (\#, \*, 0-9)를 입력할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 외부 액세스 접두사를 지정하면 접두사를 수용하기 위해 새 정규화 규칙을 만들 필요가 없습니다.

    
    </div>

10. 다음과 같이 다이얼 플랜에 대 한 정규화 규칙을 연결 하 고 구성 합니다.
    
      - Enterprise Voice 배포에서 사용할 수 있는 모든 정규화 규칙 목록에서 하나 이상의 규칙을 선택 하려면 **선택을**클릭 합니다. **정규화 규칙 선택**에서 다이얼 플랜과 연결할 규칙을 강조 표시 하 고 **확인**을 클릭 합니다.
    
      - 새 정규화 규칙을 정의하고 다이얼 플랜과 연결하려면 **새로 만들기**를 클릭합니다. 새 규칙을 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하십시오.
    
      - 다이얼 플랜과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름을 강조하고 **자세한 정보 표시**를 클릭합니다. 규칙 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하십시오.
    
      - 기존의 정규화 규칙을 복사한 후 이를 기반으로 새 규칙을 정의하려면 규칙 이름을 강조하고 **복사**를 클릭한 다음 **붙여넣기**를 클릭합니다. 복사본 편집에 대 한 자세한 내용은 [Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)를 참조 하십시오.
    
      - 정규화 규칙을 다이얼 플랜에서 제거하려면 규칙 이름을 강조하고 **제거**를 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 각각의 다이얼 플랜마다 적어도 하나의 정규화 규칙이 연결되어 있어야 합니다. 다이얼 플랜에 필요한 모든 정규화 규칙을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013에서 다이얼 플랜 및 정규화 규칙</A> 을 참조 하십시오.

    
    </div>

11. 다이얼 플랜의 정규화 규칙이 올바른 순서로 정렬되어 있는지 확인합니다. 목록에서 규칙의 위치를 변경하려면 규칙 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server는 정규화 규칙 목록을 위에서 아래로 이동 하 고 전화 건 번호와 일치 하는 첫 번째 규칙을 사용 합니다. 전화를 건 번호가 둘 이상의 정규화 규칙과 일치하도록 다이얼 플랜을 구성하는 경우 더 제한적인 규칙을 덜 제한적인 규칙보다 위에 정렬되게 하십시오.<BR>기본 <STRONG>모든 정규화 유지</STRONG> 규칙 <STRONG>^ (\d{11}) $</STRONG> 는 11 자리 숫자와 일치 합니다. 예를 들어 1425으로 시작 하는 11 자리 번호와 일치 하는 정규화 규칙을 추가 하는 경우에는 <STRONG>모두 유지</STRONG> 를 보다 제한적인 <STRONG>^ ({7}1425) $</STRONG> rule 아래에 정렬 해야 합니다.

    
    </div>

12. (선택 사항) 다이얼 플랜을 테스트할 번호를 입력한 다음 **이동**을 클릭합니다. 테스트 결과가 **테스트할 번호 입력** 아래에 표시됩니다.
    
    <div>
    

    > [!NOTE]  
    > 아직 테스트를 통과하지 않은 다이얼 플랜을 저장한 다음 나중에 다시 구성할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.

    
    </div>

13. **확인**을 클릭합니다.

14. **다이얼 플랜** 페이지에서 **커밋**을 클릭한 다음 **모두 커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 다이얼 플랜을 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다. 자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 다이얼 플랜 수정](lync-server-2013-modify-a-dial-plan.md)  
[Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Lync Server 2013에서 정규화 규칙 정의](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

