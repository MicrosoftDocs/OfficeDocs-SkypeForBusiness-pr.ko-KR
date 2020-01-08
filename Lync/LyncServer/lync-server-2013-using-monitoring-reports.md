---
title: 'Lync Server 2013: 모니터링 보고서 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7c1e70a47e3f3043215e1d16e1f01bfec4b677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 보고서 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-21_

Lync Server 2013에는 Microsoft SQL Server Reporting Services에서 게시 하는 표준 보고서 집합이 포함 되어 있습니다. 웹 브라우저를 사용 하 여 액세스할 수 있는 이러한 보고서에는 CDR 및 체감 품질 데이터베이스에 저장 된 CDR (통화 정보 기록) 및 체감 품질 (사용 품질) 레코드를 기준으로 하는 사용량, 호출 진단 정보 및 미디어 품질 정보가 제공 됩니다.

이러한 보고서를 사용 하려면 SQL Server의 인스턴스를 실행 하는 컴퓨터에 모니터링 보고서를 설치 해야 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   의 모니터링 대시보드를 사용 하 여 관리자는 시스템 상태 및 시스템 사용량을 빠르게 간략하게 살펴볼 수가 있습니다.

  - [Lync server 2013](lync-server-2013-system-usage-reports.md)   의 시스템 사용 보고서는 lync server에서 수집한 CDR 데이터를 기반으로 시스템 사용 정보를 제공 합니다.

  - [Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   의 사용자 당 전화 진단 보고서에는 실패 한 피어 투 피어 및 회의 세션에 대 한 사용자 단위 정보가 제공 됩니다.

  - [Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   의 호출 진단 보고서는 실패 한 피어 투 피어 및 회의 세션에 대 한 요약 정보 및 진단 데이터를 제공 합니다.

  - [Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   의 미디어 품질 진단 보고서는 통화 품질 및 실패 한 통화에 대 한 진단 및 문제 해결 정보에 대 한 정보를 제공 합니다.

</div>

<div>

## <a name="locating-records"></a>레코드 찾기

모니터링 보고서에는 한 번에 제한 된 수의 레코드만 화면에 표시 됩니다. 화면에 표시 되는 실제 레코드 수는 보고서에 따라 달라 집니다. 현재 화면에 표시 되지 않은 레코드를 보려면 각 보고서의 도구 모음에 있는 표준 앞으로 및 뒤로 컨트롤을 사용 하 여 데이터를 페이징 하는 데 사용할 수 있습니다. 데이터 집합의 첫 번째 페이지 또는 마지막 페이지로 빠르게 이동할 수도 있습니다.

앞으로 및 뒤로 컨트롤을 사용 하는 것 외에도 **현재 페이지** 상자에 페이지 번호를 입력 하 고 enter 키를 눌러 데이터 집합의 페이지로 이동할 수도 있습니다.

각 보고서에는 데이터를 페이징 하는 기능을 제공 하는 것 외에도 레코드를 찾는 제한 된 기능이 포함 되어 있습니다. 지정 된 값을 기준으로 레코드를 찾으려면 **찾기** 상자에 해당 값을 입력 한 다음 **찾기를**클릭 합니다. 보고서에서 데이터를 검색 하기 시작 하 고 **찾기** 상자에 입력 한 값의 첫 번째 인스턴스에서 멈춥니다. 검색 조건을 충족 하는 다음 레코드를 찾으려면 **다음**을 클릭 합니다.

참고로, 모니터링 보고서는 가장 기본적인 검색 기능만 제공 합니다. 예를 들어 값을 찾을 필드를 지정할 수 없습니다. 검색 메커니즘은 모든 레코드의 모든 필드에서 일치 하는 값을 자동으로 검색 합니다. 검색에 와일드 카드를 사용할 수 없으며 모든 검색에서 부분 값을 찾습니다. 즉, 111을 검색 하면 값 11100 111, 811, 3112, 611A5B, 그리고 해당 필드 내의 아무 곳에 나 값을 포함 하는 다른 모든 필드를 검색 하 여 반환 합니다.

각 보고서는 기본 레코드 집합을 표시 하도록 구성 됩니다. 예를 들어 사용자 등록 보고서에는 기본적으로 지난 주에 대 한 사용자 등록 활동이 표시 됩니다. 어떤 경우에는이로 인해 보고서를 반환 하는 레코드가 표시 되지 않을 수도 있습니다. 이 경우 지난 주에 사용자 등록이 수행 되지 않았음을 의미 합니다. "보고서 필터와 일치 하는 결과가 없습니다" 라는 메시지가 표시 되는 경우 필터 값을 변경 하 고 (예: 기간을 지난 주가 아닌 지난 달로 변경) 쿼리를 다시 실행 합니다. 자세한 내용은이 항목의 뒷부분에 나오는 "데이터 필터링" 섹션을 참조 하세요.

</div>

<div>

## <a name="filtering-data"></a>데이터 필터링

레코드의 하위 집합을 보기만 하는 경우가 있을 수 있습니다. 예를 들어 피어 투 피어 세션 및 회의 세션과는 달리 피어 투 피어 세션만 가능 합니다. 마찬가지로 반환 되는 레코드 수를 줄여야 하는 경우도 있습니다. 기본적으로 보고서에는 데이터 집합의 첫 번째 1000 레코드만 표시할 수 있습니다. 이러한 문제를 해결 하기 위해 대부분의 보고서에는 여러 필터링 옵션이 포함 되어 있습니다. 예를 들어 2 월 1 일에서 2011 년 1 월 15 2011 일 사이의 레코드만 표시 하려면 **보낸 사람** 상자에 2011 1, 15, 01, 시작 **날짜 상자에** 2011을 입력 하면 됩니다. 그런 다음 **보고서 보기**를 클릭 하면 반환 되는 데이터가 2011 년 1 월 1 일에서 2011 년 1 월 15 일 사이에 발생 하는 작업으로 제한 됩니다.

사용할 수 있는 필터는 보고 있는 보고서에 따라 달라 집니다. 특정 보고서에 대 한 자세한 내용은 해당 보고서에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="exporting-data"></a>데이터 내보내기

모니터링 보고서는 두 가지 이상의 방법을 제공 하 여 보고서에 포함 된 데이터를 내보냅니다. 각 보고서의 맨 위에 표시 되는 도구 모음에서 **내보내기** 옵션을 사용할 수 있습니다. 이 옵션을 사용 하려면 **형식 선택** 드롭다운 목록에서 원하는 내보내기 형식을 선택 합니다. 다음과 같은 형식을 사용할 수 있습니다.

  - 보고서 데이터를 포함 하는 XML 파일

  - CSV (쉼표로 분리)

  - Acrobat (PDF) 파일

  - MHTML (웹 보관)

  - 0:excel}

  - TIFF 파일

  - 이면

형식을 선택한 후 **내보내기를**클릭 합니다. **파일 다운로드** 대화 상자가 표시 되 면 **저장**을 클릭 합니다. **다른 이름으로 저장** 대화 상자에서 대상 폴더를 선택 하 고 파일 이름을 입력 한 다음 **저장**을 클릭 합니다.

Microsoft OneNote가 설치 되어 있는 경우 보고서 데이터를 OneNote에 복사할 수도 있습니다. 이렇게 하려면 도구 모음에서 **보고서 보기** 단추를 마우스 오른쪽 단추로 클릭 합니다. **Onenote에서 위치 선택** 대화 상자에서 데이터를 복사 하려는 onenote 섹션을 선택한 다음 **확인**을 클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

