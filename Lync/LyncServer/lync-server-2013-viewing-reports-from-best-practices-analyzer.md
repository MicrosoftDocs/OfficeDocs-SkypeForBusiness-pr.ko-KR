---
title: 'Lync Server 2013: 모범 사례 분석기에서 보고서 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013의 모범 사례 분석기에서 보고서 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

모범 사례 분석기를 사용 하 여 환경을 검색 하는 경우 검색의 이름을 지정 합니다. 모범 사례 분석기는 검사를 완료 한 후 검사 결과를 보고서에 저장 하 고 검색 이름 아래에 저장 합니다. 검사가 완료 되 면 검색 **완료** 페이지에서 직접 **이 모범 사례 스캔** 에 대 한 보고서 보기를 클릭 하 여 해당 스캔에 대해 생성 된 보고서를 볼 수 있습니다. 나중에 해당 스캔 또는 이전 검사에서 보고서를 볼 수도 있습니다. 스캔을 실행 한 로컬 컴퓨터에서 보고서를 보거나, 다른 컴퓨터에서 검사 결과를 가져오거나, 검색 결과를 내보내어 모범 사례 분석기가 설치 된 다른 컴퓨터의 보고서를 볼 수 있습니다.

검사 결과는 다음 보고서 형식으로 표시 됩니다.

  - 목록 보고서

  - 트리 보고서

  - 다른 보고서

이러한 보고서에는 오류, 경고 및 기타 정보가 포함 됩니다. 이러한 각 보고서 및 문제 유형에 대 한 자세한 내용은 [Lync Server 2013에서 모범 사례 분석기에서 만든 보고서 이해](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md)를 참조 하세요.

이전에 모범 사례 분석기에서 생성 된 검사 결과를 보려면 다음 절차를 사용 합니다.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>이전 검사에서 보고서를 보려면

1.  로컬 사용자 계정의 구성원 인 계정을 사용 하 여 모범 사례 분석기가 설치 된 컴퓨터에 로그온 합니다.
    
    > [!NOTE]  
    > 로컬 관리자 그룹의 구성원 인 계정을 사용 하 여 검사 결과를 볼 수 있지만 적절 한 사용자 권한 및 사용 권한이 없으면 검사를 실행할 수 없습니다. 자세한 내용은 <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Lync Server 2013의 모범 사례 분석기에 대 한 그룹 멤버 자격 및 사용자 권한 요구 사항을</A>참조 하세요.

2.  **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync Server 2013**을 차례로 가리킨 다음 모범 **사례 분석기**를 클릭 합니다.

3.  **시작** 화면에서 **보려는 검사 결과 선택을**클릭 합니다.

4.  **볼 모범 사례 스캔 선택** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 로컬에 저장 된 검사 결과 목록에서 보고서를 보려면 스캔 이름을 클릭 한 다음 **이 스캔 보고서 보기**를 클릭 합니다.
        
        > [!NOTE]  
        > 모범 &lt;사례 분석기는 폴더&gt;\\로 사용 된 문서 및 설정\\&lt;사용자&gt;\Application Data\Microsoft\RtcBPA.에서 로컬 파일 목록을 만듭니다.
    
      - 다른 위치에 저장 된 검사 결과에 대 한 보고서를 보려면 **검색 가져오기를**클릭 하 고 검사 결과를 포함 하는 파일을 찾은 다음 **열기**를 클릭 합니다.
        
        > [!NOTE]  
        > 이 컴퓨터의 모범 사례 분석기 버전이 가져온 파일의 데이터를 수집 하는 데 사용 된 버전과 일치 하지 않는 경우 컴퓨터의 도구에서 파일을 가져온 후 다시 분석할 수 있습니다.

5.  **모범 사례 보고서 보기** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 서버 구성 요소로 구성 된 목록에서 보고서를 보려면 **목록 보고서**를 클릭 한 다음 **모든 문제점** 탭 또는 **정보 항목** 탭을 클릭 합니다.
    
      - 결과 종류별로 구성 된 계층적 목록으로 보고서를 보려면 **트리 보고서**를 클릭 한 다음 **자세히 보기** 탭 또는 **요약 보기** 탭을 클릭 합니다.
    
      - 다른 보고서를 보려면 **기타 보고서**를 클릭 합니다.
    
    > [!NOTE]  
    > 모범 사례 분석기 보고서 및 이들이 식별 하는 문제에 대 한 자세한 내용은 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013에서 모범 사례 분석기에서 만든 보고서 보기 및 작업</A> 및 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync server 2013의 모범 사례 분석기에서 식별 된 문제 분석 및 해결</A>을 참조 하세요.

</div>

</div>

</div>

</div>

</div>

