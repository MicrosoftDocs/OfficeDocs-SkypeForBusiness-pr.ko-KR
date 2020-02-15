---
title: 'Lync Server 2013: 비공식 음성 라우팅 테스트 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8edac9a9bd955165a2e20197fd340ea80c2e27a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>Lync Server 2013에서 비공식 음성 라우팅 테스트 실행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-07_

**음성 라우팅 테스트 사례 정보 만들기** 대화 상자를 사용 하 여 실제 테스트 사례를 만들기 전에 비공식 테스트를 실행할 수 있습니다. 테스트 결과가 만족 스 러 우면 공식 테스트 사례로 저장 하는 옵션이 있습니다.

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>비공식 음성 라우팅 테스트를 실행 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **음성 라우팅**을 클릭하고 **음성 라우팅 테스트**를 클릭합니다.

4.  **음성 라우팅 테스트** 페이지에서 **음성 라우팅 테스트 사례 정보 만들기**를 클릭 합니다.

5.  전화 **건 번호** 필드에이 테스트에 사용할 통화 번호를 입력 합니다. 이 값은 정규화 되어 **결과** 창의 정규화 된 **번호** 필드에 표시 됩니다.

6.  **다이얼 플랜** 목록에서 전화 건 번호를 테스트 하는 데 사용할 다이얼 플랜을 선택 합니다. 기본값은 전역 다이얼 플랜입니다.
    
    테스트를 실행 하면이 다이얼 플랜에서 전화 건 번호와 일치 하는 첫 번째 정규화 규칙이 **결과** 창의 **정규화 규칙** 필드에 표시 됩니다.

7.  **음성 정책** 목록에서 전화 건 번호를 테스트 하는 데 사용할 음성 정책을 선택 합니다. 기본값은 전역 음성 정책입니다.
    
    테스트를 실행 하면이 음성 정책에서 일치 하는 첫 번째 PSTN 사용 레코드가 **결과** 창의 **첫 번째 PSTN 사용** 필드에 표시 됩니다. 또한이 PSTN 사용 레코드와 연결 된 첫 번째로 일치 하는 음성 경로는 **첫 번째 경로** 필드에 표시 됩니다.

8.  반드시 특정 사용자에 게 할당 된 음성 정책에 대해 전화 건 번호를 테스트 하려면 **사용자 로부터 채우기** 확인란을 선택 합니다.
    
    1.  **찾아보기를** 클릭 하 여 **Enterprise Voice Users 선택** 대화 상자를 표시 합니다.
    
    2.  **찾기를** 클릭 하 여 Enterprise Voice를 사용 하도록 설정 된 사용자 목록을 표시 합니다.
    
    3.  이 테스트에 대해 할당 된 음성 정책을 사용할 사용자 이름을 두 번 클릭 합니다. 이제 **정책** 필드가 선택한 사용자에 게 할당 된 음성 정책으로 채워집니다.
    
    테스트를 실행 하면이 음성 정책에서 일치 하는 첫 번째 pstn (공중 전화망) 사용 레코드가 **결과** 창의 **첫 번째 PSTN 사용** 필드에 표시 됩니다. 또한이 PSTN 사용 레코드와 연결 된 첫 번째로 일치 하는 음성 경로는 **첫 번째 경로** 필드에 표시 됩니다.

9.  **실행** 을 클릭 하 여 테스트 사례를 실행 합니다. 결과가 대화 상자의 오른쪽 패널에 표시 됩니다.

10. 반드시 이 테스트 구성을 공식 테스트 사례로 저장 하려면 **다른 이름으로 저장** 을 클릭 합니다.
    
    1.  **음성 라우팅 테스트 사례 정보 저장** 대화 상자의 **이름** 필드에 테스트 사례의 고유한 이름을 입력 합니다.
        
        이 이름은 엔터프라이즈 음성 배포의 모든 음성 라우팅 테스트 사례에서 고유 해야 합니다. 이 길이는 최대 32 자까지 사용할 수 있으며 백슬래시 (\\), 마침표 (.) 또는 밑줄 (\_) 외에 영숫자 문자를 포함할 수도 있습니다.
    
    2.  **음성 라우팅 테스트 사례 정보 저장** 대화 상자에서 나머지 필드는 읽기 전용 이며 비공식적인 테스트 구성 *및* 결과에서 미리 채워집니다. 테스트 사례에 대해 저장 하려는 구성 인지 확인 합니다.
        
        <div>
        

        > [!NOTE]  
        > 테스트 결과 값은 다음과 같이 <STRONG>음성 라우팅 테스트 사례 정보 저장</STRONG> 대화 상자에서 필드를 미리 채우는 데 사용 됩니다. 
        > <UL>
        > <LI>
        > <P><STRONG>예상 번역</STRONG> 은 <STRONG>정규화 된 번호</STRONG> 필드의 값으로 미리 채워집니다.</P>
        > <LI>
        > <P><STRONG>예상 경로</STRONG> 는 <STRONG>첫 번째 경로</STRONG> 필드의 값으로 미리 채워집니다.</P>
        > <LI>
        > <P><STRONG>예상 pstn 사용 레코드</STRONG> 는 <STRONG>첫 번째 PSTN 사용</STRONG> 필드의 값으로 미리 채워집니다.</P></LI></UL>테스트 실행 중에 이러한 값과 일치 하는 항목을 찾지 못한 경우에는 <STRONG>음성 라우팅 테스트 사례 정보 저장</STRONG> 대화 상자에서 해당 필드가 비어 있습니다.

        
        </div>
    
    3.  **확인** 을 클릭 하 여 테스트 사례를 저장 하거나, **취소** 를 클릭 하 여 **음성 라우팅 테스트 사례 정보 보기** 대화 상자로 돌아간 후 저장 하기 전에 테스트를 추가로 개발 합니다.

11. **커밋**을 클릭한 후 **모두 커밋**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 음성 라우팅 테스트 사례를 만들 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 테스트 사례를 게시 해야 합니다. 자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 라우팅 테스트 사례 만들기](lync-server-2013-create-a-voice-routing-test-case.md)  
[Lync Server 2013에서 음성 라우팅 테스트 사례 실행](lync-server-2013-run-voice-routing-test-cases.md)  
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

