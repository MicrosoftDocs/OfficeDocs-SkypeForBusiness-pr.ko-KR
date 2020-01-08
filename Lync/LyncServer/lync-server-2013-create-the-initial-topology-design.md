---
title: 'Lync Server 2013: 초기 토폴로지 디자인 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656e9605695fe7dab160469ffa9e9c5075ac807b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Lync Server 2013의 초기 토폴로지 디자인 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

Lync Server 2013, 계획 도구 설치를 완료 한 후에는 계획 도구를 시작 하 고 제안 된 Lync Server 2013 인프라 디자인을 시작할 준비가 되었습니다.

<div>


> [!NOTE]  
> 계획 도구는 사이트 및 토폴로지 디자인의 의사 결정 프로세스에 대해 자세히 설명 하는 마법사 기반 도구입니다. 이 항목은 철저 한 지침이 아니며, 디자인 세션에서 계획 도구를 사용 하 여 시작 하는 데 도움이 됩니다.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>계획 도구를 사용 하 여 시작 하 고 초기 디자인 만들기

1.  Lync Server 2013, 계획 도구: **시작**, **모든 프로그램**, **Microsoft Lync Server 2013**, **계획 도구**를 차례로 클릭 합니다.

2.  계획 도구가 시작 되 면 **Microsoft Lync Server에 대 한 계획 도구 2013** 페이지가 나타납니다. 다음 옵션 중 하나를 선택 하 여 디자인을 시작 합니다.
    
      - **옵션 1:**    **시작을 클릭 하면** 조건을 정의 하는 관련 선택이 있는 특정 일련의 인터뷰 질문이 제공 됩니다. 초기 **시작** 인터뷰 섹션을 완료 한 후에는 사이트 아키텍처를 정의 하는 **디자인 사이트로** 이동 합니다. 이 옵션을 완료 하려면 3 단계로 진행 합니다.
    
      - **옵션 2:**   시작 페이지에서 **디자인 사이트** 를 클릭 하는 디자인 사이트는 **시작** 섹션에 제시 된 인터뷰 질문을 무시 합니다. **시작** 하기 섹션의 면접 질문에 응답 하 여 수집 된 정보는이 옵션을 사용 하 여 기본값으로 설정 됩니다. **사이트 디자인**을 클릭 하면 숙련 된 디자이너가 초기 인터뷰를 우회 하 고 필요한 경우 **중앙 사이트** 시작 페이지에서 기본값을 변경할 수 있습니다. 이 옵션을 완료 하려면 3-5 단계를 건너뛰고 6 단계부터 시작 합니다.
    
      - **옵션 3: 저장 된 토폴로지**   표시 이전에 계획 도구를 사용 하 여 토폴로지를 완료 하 고 저장 한 경우에는 이러한 단계를 대부분 건너뛰고 토폴로지를 열고 표시 하 여 시작할 수 있습니다. 또한 토폴로지를 변경 하 고 업데이트 한 후 다시 저장 한 다음 Microsoft Excel 또는 Microsoft Visio로 내보낼 수 있습니다. 이 옵션을 완료 하려면 3-12 단계를 건너뛰고 13 단계부터 시작 합니다.

3.  **시작** 하기를 클릭 하 여 Lync Server 2013 토폴로지 디자인을 시작 합니다.

4.  디자인에 적합 한 조건을 선택 하 여 각 섹션에 응답 한 후 **다음** 을 클릭 하 여 다음 마법사 페이지로 이동 합니다. 이전 페이지를 변경 하려면 **뒤로** 를 클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 각 페이지에는 선택 조건에 대 한 설명과 선호 하는 방법 및 용량 계획에 따른 권장 사항이 있습니다. 추가 정보가 필요한 <STRONG>경우 자세히를 클릭 하</STRONG> 여 Lync Server 2013 계획 문서에서 Microsoft TechNet 웹 사이트의 자세한 정보를 읽으십시오. Microsoft TechNet 웹 사이트에 액세스 하려면 인터넷에 연결 되어 있어야 합니다.

    
    </div>

5.  디자인에 적합 한 옵션을 선택 합니다. 초기 조건을 정의한 후 페이지에서 기능 개요가 완전 한지 확인 합니다.

6.  **사이트 디자인** 을 클릭 하 여 중앙 사이트를 정의 합니다.
    
    <div>
    

    > [!NOTE]  
    > 각 Lync Server 2013 토폴로지에는 하나 이상의 중앙 사이트가 있습니다. 디자인에는 단일 중앙 사이트, 여러 지점 사이트, 여러 중앙 사이트, 각 중앙 사이트와 연결 된 분기 사이트가 있는 중앙 사이트 수가 포함 되어 있을 수 있습니다.

    
    </div>

7.  **사이트 이름**에이 중앙 사이트를 식별 하는 이름을 입력 합니다.

8.  **사이트 홈 사용자**에이 중앙 사이트에서 사용자가 원하는 온-프레미스 동시 사용자 수를 입력 합니다.

9.  **클라우드 홈 사용자**의 경우이 중앙 사이트에서 사용자가 원하는 예상 온라인 동시 사용자 수를 입력 합니다.

10. 필요에 따라 온라인 공동 작업, 사용자, 음성, 추가 배포 옵션 또는 서버 응용 프로그램에 대 한 선택 항목을 수정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 디자인의이 시점에서는 배포에 대 한 옵션만 선택 하거나 선택을 취소할 수 있습니다. 그러나 계획 도구의 이후 단계에서 더 많은 옵션을 구성할 수 있습니다. 사용할 수 없고 지울 수 없는 옵션도 있습니다. 또한 다른 옵션을 지우려면 하나를 지워야 할 수 있습니다. 예를 들어 Voice에서 <STRONG>Enterprise voice</STRONG> 옵션을 지우면 서버 응용 프로그램의 <STRONG>응답 그룹</STRONG>, <STRONG>공지 사항</STRONG>및 <STRONG>통화 공원</STRONG> 옵션 (Enterprise voice의 기능)도 모두 지워집니다.

    
    </div>

11. 사이트 이름과 사용자 수를 정의한 후 **다음**을 클릭 합니다.

12. 다음 페이지에서는 SIP 도메인, 회의 설정, 음성 설정 및 인프라, Exchange UM, 외부 사용자 액세스, 영구 채팅 설정, 클라이언트 설정, collocation 옵션, 분기 사이트에 대 한 정보를 요청 합니다. 이러한 질문에 적절 하 게 대답 합니다.

13. 마지막 질문은 다른 중앙 사이트를 만들 것인지 묻습니다. **예**를 선택 하면 계획 도구가 중앙 사이트 페이지로 돌아갑니다. **아니요**를 선택 하는 경우 **다음**을 클릭 한 다음 **그리기** 를 클릭 하 여 상위 수준의 전역 토폴로지 보기를 표시 합니다.

14. 기존 토폴로지를 보려면 **표시**를 클릭 합니다.

15. 이전에 저장 한 토폴로지를 나타내는 .xml 파일을 클릭 한 다음 **열기**를 클릭 합니다.

16. 계획 도구에 전역 토폴로지 페이지가 표시 됩니다. 이제 계획 도구에서 제공 되는 도구를 사용 하 여 토폴로지 편집, 업데이트 또는 변경을 시작할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 디자인 편집](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

