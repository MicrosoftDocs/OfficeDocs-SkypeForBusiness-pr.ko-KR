---
title: 모범 사례 분석기를 사용 하 여 배포를 검사 하 여 잠재적인 문제 해결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a>모범 사례 분석기를 사용 하 여 Lync Server 2013 배포를 검사 하 여 잠재적인 문제 해결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-21_

모범 사례 분석기 검사를 실행 하려면 다음을 지정 해야 합니다.

  - **자격 증명**   검사를 실행 하려면 로컬 관리자 그룹의 구성원 인 계정을 사용 하 여 모범 사례 분석기가 설치 된 컴퓨터에 로그온 해야 합니다. 또한 적절 한 검사를 실행 하는 데 필요한 사용자 권한 및 사용 권한이 있는 사용자 계정을 사용 하 여 로그온 해야 하며 모범 사례 분석기를 실행할 때 적절 한 사용자 권한 및 사용 권한을 가진 자격 증명을 지정 해야 합니다. 자세한 내용은 [Lync Server 2013의 모범 사례 분석기에 대 한 그룹 멤버 자격 및 사용자 권한 요구 사항을](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md)참조 하세요.

  - **스캔 범위 검사**   범위를 지정 하려면 스캔 하려는 범주와 서버를 선택 합니다. Lync Server 환경의 특정 범주 내에 있는 모든 범주, 하나 이상의 범주 또는 하나 이상의 서버를 선택할 수 있습니다.

  - **검사 유형 현재**   상태 검사 검사는 사용 가능한 유일한 스캔 유형으로, 기본적으로 선택 되어 있습니다. 상태 검사 검사는 범위에 지정 된 모든 서버에 대 한 오류, 경고 및 기타 정보를 포함 하는 보고서를 생성 합니다.

  - **네트워크 속도**   네트워크 속도 옵션에는 고속 LAN (100 mbps 이상), LAN (10mbps), 초고속 wan (1.5 mbps) 또는 wan (64 kbps)이 포함 됩니다. 검사를 완료 하는 데 예상 되는 시간은이 설정을 기반으로 합니다. 이 설정은 시간 초과 기간을 설정 하는 데도 사용 됩니다. 검색 하는 동안 모범 사례 분석기는 지정 된 시간 동안 서버 로부터 응답을 기다립니다. 지정 된 시간 초과 기간 내에 응답을 받지 못하는 경우에는 검사의 다음 서버로 이동 합니다. 느린 네트워크에서는 네트워크 대기 시간이 길어질 때이 지정 된 시간 초과 기간이 더 길어집니다. 이 매개 변수에 대 한 토폴로지에서 가장 느린 링크를 선택 하 여 도구가 시간을 너무 빨리 초과 하지 않도록 하는 것이 좋습니다.

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a>Lync Server 2013 배포를 검사 하려면

1.  로컬 관리자 그룹의 구성원 인 계정을 사용 하 여 모범 사례 분석기가 설치 된 컴퓨터에 로그온 하 고 다른 필수 사용자 권한이 있는 경우 사용 권한을 부여 합니다.

2.  **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync Server 2013**을 차례로 가리킨 다음 모범 **사례 분석기**를 클릭 합니다.

3.  **시작** 화면에서 **새 스캔에 대 한 옵션 선택을**클릭 합니다.

4.  **Active directory에 연결** 페이지에서 **active directory 서버**에 지정 된 이름을 확인 하 고 다음 중 하나를 수행 합니다.
    
      - 컴퓨터에 로그온 하는 데 사용한 자격 증명을 사용 하 여 검사를 실행 하려면 **Active Directory 서버에 연결**을 클릭 합니다.
    
      - Active Directory 도메인 서비스, Edge Server 또는 Exchange Server에 사용할 다른 자격 증명을 지정 하려면 **고급 로그온 옵션 표시**를 클릭 하 고 별도의 자격 증명이 필요한 각 확인란을 선택 하 고 선택한 각 확인란에 대 한 자격 증명을 지정한 다음 **Active Directory 서버에 연결**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]
    > 검색을 시작 하기 전에 모범 사례 분석기는 지정 된 계정 자격 증명이 유효 하며 모범 사례 분석기에서 Active Directory 도메인 서비스에 연결할 수 있는지 확인 하는 네트워크 및 사용 권한을 확인 합니다. 도구를 작업 그룹 서버에서 실행 하는 경우 도구는 주변 네트워크의 Edge 서버 (즉, 스캔에 포함 된 경우)에 연결할 수 있는지도 확인 합니다.

    
    </div>

5.  새 모범 **사례 스캔 시작** 페이지에서 스캔에 포함할 옵션을 선택 하 고 네트워크 속도를 지정한 다음 **스캔 시작**을 클릭 합니다.

6.  **검색 완료** 페이지에서 모범 **사례 검사 보고서 보기**를 클릭 합니다.

7.  **모범 사례 보고서 보기** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 서버 구성 요소로 구성 된 목록에서 보고서를 보려면 **목록 보고서**를 클릭 한 다음 **모든 문제점** 탭 또는 **정보 항목** 탭을 클릭 합니다.
    
      - 결과 종류별로 구성 된 계층적 목록으로 보고서를 보려면 **트리 보고서**를 클릭 한 다음 **자세히 보기** 탭 또는 **요약 보기** 탭을 클릭 합니다.
    
      - 다른 보고서를 보려면 **기타 보고서**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]
    > 모범 사례 분석기 보고서 및 이들이 식별 하는 문제점에 대 한 자세한 내용은 <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Lync server 2013에서 모범 사례 분석기를 사용 하 여 만든 보고서 보기 및 작업</A> 및 <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">lync server 2013의 모범 사례 분석기에서 식별 된 문제 분석 및 해결</A>을 참조 하세요.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

