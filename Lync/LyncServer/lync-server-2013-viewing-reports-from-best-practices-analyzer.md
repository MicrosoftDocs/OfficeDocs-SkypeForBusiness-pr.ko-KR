---
title: 'Lync Server 2013: 모범 사례 분석기에서 보고서 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ffa6108760955de643b7ffa4afe841464ae140f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535595"
---
# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013에서 모범 사례 분석기의 보고서 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

모범 사례 분석기를 사용해서 환경을 검색할 때는 검색 이름을 지정합니다. 모범 사례 분석기가 검색을 완료하면 검색 결과가 검색 이름 아래에 보고서로 저장됩니다. 검색이 완료되면 **검색 완료** 페이지에서 직접 **이 Best Practices 검색 보고서 보기**를 클릭하여 검색으로 생성된 보고서를 볼 수 있습니다. 또한 해당 검색 또는 이전 검색의 보고서를 나중에 볼 수도 있습니다. 검색이 실행된 로컬 컴퓨터에서 보고서를 보거나, 다른 컴퓨터에서 검색 결과를 가져오거나, 모범 사례 분석기가 설치된 다른 컴퓨터에서 보고서를 볼 수 있도록 검색 결과를 내보낼 수 있습니다.

검색 결과는 다음과 같은 보고서 유형으로 표시됩니다.

  - 목록 보고서

  - 트리 보고서

  - 기타 보고서

이러한 보고서에는 오류, 경고 및 기타 정보가 포함됩니다. 이러한 각 유형의 보고서와 문제에 대 한 자세한 내용은 [Lync Server 2013에서 모범 사례 분석기에서 만든 보고서 이해](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)(영문)를 참조 하십시오.

다음 절차에 따라 이전에 모범 사례 분석기로 생성된 검색 결과를 볼 수 있습니다.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>이전 검색의 보고서를 보려면

1.  로컬 User 계정의 구성원인 계정을 사용하여 모범 사례 분석기가 설치된 컴퓨터에 로그온합니다.
    
    > [!NOTE]  
    > 로컬 Administrators 그룹의 구성원인 계정을 사용하여 검색 결과를 볼 수도 있지만 적합한 사용자 권한이 없으면 검색을 실행할 수 없습니다. 자세한 내용은 <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013의 모범 사례 분석기에 대 한 그룹 구성원 자격 및 사용자 권한 요구 사항</A>를 참조 하세요.

2.  **시작**을 클릭 하 고 **모든 프로그램**을 가리킨 다음 **Microsoft Lync Server 2013**, **모범 사례 분석기**를 차례로 클릭 합니다.

3.  **시작** 화면에서 **확인할 검색 결과 선택**을 클릭합니다.

4.  **확인할 모범 사례 검색 선택** 페이지에서 다음 중 하나를 수행합니다.
    
      - 로컬로 저장된 검색 결과 목록에서 보고서를 보려면 검색 이름을 클릭한 후 **이 검색 보고서 보기**를 클릭합니다.
        
        > [!NOTE]  
        > 모범 사례 분석기는 폴더 드라이브 드라이브 &lt; &gt; \\ 문서 및 설정 \\ &lt; 사용자 &gt; \Application data\microsoft\rtcbpa에서 로컬 파일의 목록을 만듭니다.
    
      - 다른 위치에 저장된 검색 결과에 대한 보고서를 보려면 **검색 가져오기**를 클릭하고 검색 결과가 포함된 파일을 찾은 후 **열기**를 클릭합니다.
        
        > [!NOTE]  
        > 이 컴퓨터의 모범 사례 분석기 버전이 가져온 파일의 데이터를 수집하는 데 사용된 버전과 일치하지 않으면 해당 컴퓨터의 도구가 파일을 가져온 후 다시 분석할 수 있습니다.

5.  **Best Practices 보고서 보기** 페이지에서 다음 중 하나를 수행합니다.
    
      - 서버 구성 요소로 구성된 목록에서 보고서를 보려면 **목록 보고서**를 클릭한 후 **모든 문제** 탭 또는 **정보 항목** 탭을 클릭합니다.
    
      - 결과 유형별로 구성된 계층적 목록으로 보고서를 보려면 **트리 보고서**를 클릭한 후 **자세히 보기** 탭 또는 **요약 보기** 탭을 클릭합니다.
    
      - 다른 보고서를 보려면 **기타 보고서**를 클릭합니다.
    
    > [!NOTE]  
    > 모범 사례 분석기 보고서 및 이들이 식별 하는 문제에 대 한 자세한 내용은 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013에서 모범 사례 분석기에서 만든 보고서 보기 및 작업</A> 및 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync Server 2013의 모범 사례 분석기에서 식별 한 문제 분석 및 해결</A>을 참조 하세요.

</div>

</div>

</div>

</div>

</div>

