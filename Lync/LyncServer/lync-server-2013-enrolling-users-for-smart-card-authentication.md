---
title: 'Lync Server 2013: 스마트 카드 인증을 위한 사용자 등록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e74f35119a083aacd8440aec53594b8091b8e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a>Lync Server 2013에서 스마트 카드 인증을 위한 사용자 등록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-03_

스마트 카드 인증을 위해 사용자를 등록 하는 방법에는 일반적으로 두 가지가 있습니다. 더 간단한 방법은 사용자가 웹 등록을 사용 하 여 스마트 카드 인증을 직접 등록 하도록 하는 반면 복잡 한 방법은 등록 에이전트를 사용 하는 것입니다. 이 항목에서는 스마트 카드 인증서의 자체 등록에 대해 중점적으로 설명 합니다.

등록 에이전트로 사용자를 등록 하는 방법에 대 한 자세한 내용은의 다른 사용자 대신 인증서 등록을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a>스마트 카드 인증을 위해 사용자를 등록 하려면

1.  Lync를 사용 하는 사용자의 자격 증명을 사용 하 여 Windows 8 workstation에 로그인 합니다.

2.  Internet Explorer를 실행합니다.

3.  **인증 기관 웹 등록** 페이지 (예:)로 이동 https://MyCA.contoso.com/certsrv)합니다.
    
    <div>
    

    > [!NOTE]  
    > Internet Explorer 10을 사용 하는 경우 호환 모드에서이 웹 사이트를 확인 해야 할 수 있습니다.

    
    </div>

4.  **시작** 페이지에서 **인증서 요청**을 선택 합니다.

5.  그런 다음 **고급 요청**을 선택 합니다.

6.  **이 CA에 대 한 요청 만들기 및 제출을**선택 합니다.

7.  **인증서 템플릿** 섹션에서 **스마트 카드 사용자** 를 선택 하 고 다음 값을 사용 하 여 고급 인증서 요청을 완료 합니다.
    
      - **키 옵션** 다음 설정을 확인 합니다.
        
          - **새 키 집합 만들기** 라디오 단추를 선택 합니다.
        
          - **CSP**의 경우 **Microsoft 기본 스마트 카드 암호화 공급자** 선택
        
          - **키 사용**에 대해 **Exchange** 를 선택 합니다 (사용 가능한 유일한 옵션).
        
          - **키 크기**에는 **2048** 을 입력 합니다.
        
          - **자동 키 컨테이너 이름이** 선택 되었는지 확인
        
          - 다른 확인란은 선택 하지 않은 상태로 둡니다.
    
      - **추가 옵션** 에서 다음 값을 확인 합니다.
        
          - **요청 형식의** 경우 **CMC**를 선택 합니다.
        
          - **해시 알고리즘** 의 경우 **sha1**을 선택 합니다.
        
          - **대화명** 으로 **Smardcard Certificate**를 입력 합니다.

8.  실제 스마트 카드 판독기를 사용 하는 경우 장치에 스마트 카드를 삽입 합니다.

9.  **제출을** 클릭 하 여 인증서 요청을 제출 합니다.

10. 메시지가 표시 되 면 가상 스마트 카드를 만드는 데 사용 된 PIN을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 기본 가상 스마트 카드 PIN 값은 ' 12345678 '입니다.

    
    </div>

11. 인증서가 발급 되 면 **이 인증서 설치** 를 클릭 하 여 등록 프로세스를 완료 합니다.
    
    <div>
    

    > [!NOTE]  
    > "이 웹 브라우저가 인증서 요청 생성을 지원 하지 않습니다" 오류가 발생 하 여 인증서 요청이 실패 하면 문제를 해결할 수 있는 세 가지 방법이 있습니다. 
    > <OL>
    > <LI>
    > <P>Internet Explorer에서 호환성 보기 사용</P>
    > <LI>
    > <P>Internet Explorer에서 인트라넷 설정 켜기 옵션 사용</P>
    > <LI>
    > <P>Internet Explorer 옵션 메뉴의 보안 탭에 있는 모든 영역을 기본 수준으로 다시 설정 설정을 선택 합니다.</P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

