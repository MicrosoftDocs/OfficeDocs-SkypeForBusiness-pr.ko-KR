---
title: 'Lync Server 2013: 모니터링 서버 보고서 보기 및 분석'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 서버 보고서 보기 및 분석

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-19_

모니터링 서버 보고서는 최종 사용자에 게 제공 되는 체감 품질 모니터링 하는 다양 한 음성 품질 측정값을 제공 합니다. 또한 모니터링 서버에는 조직에서 사용 및 미디어 품질 추세를 시청 하 고 발생 하는 미디어 품질 문제를 해결할 수 있는 몇 가지 기본 제공 보고서가 포함 되어 있습니다.

매일 및 매주 작동 하는 모니터링 서버 보고서를 유지 하는 주요 부분은 특히 다음과 같이 미디어 품질 보고서를 보고 분석 하는 것입니다.

  - 체감 품질 요약/추세 보고서

  - 체감 품질 성과 보고서

<div>

## <a name="view-reports-from-the-monitoring-server"></a>모니터링 서버에서 보고서 보기

1.  웹 브라우저에서 SQL reporting services를 호스트 하는 서버를 찾습니다.

2.  브라우저 화면에서 필요한 보고서를 봅니다.

3.  ) 내보내기 옵션과 필요한 출력 형식을 선택 하 여 보고서를 내보냅니다.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>CDR (통화 정보 기록) 구성

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 동등한 권한이 있거나 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 Lync Server 2013을 배포한 네트워크의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **통화 정보 기록을**클릭 합니다.

4.  **통화 정보 기록** 페이지에서 표의 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  제거를 설정 하려면 **서버 모니터링을 위해 제거 사용**을 선택 합니다.

6.  **최대 기간 (일) 동안 통화 정보 기록 유지:** 통화 정보 기록을 보존 해야 하는 최대 일 수를 선택 합니다.

7.  **최대 기간 (일)에 대 한 오류 보고 데이터 유지:** 오류 보고서를 유지 해야 하는 최대 일 수를 선택 합니다.

8.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="configure-qoe"></a>체감 품질 구성

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 대리인 설정 사용을 참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **경력 데이터 품질**을 클릭 합니다.

4.  **경력 데이터** 페이지의 테이블에서 해당 사이트를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  제거를 설정 하려면 **서버 모니터링을 위해 제거 사용**을 선택 합니다.

6.  **최대 기간 (일) 동안 통화 정보 기록 유지:** 체감 품질 데이터를 유지할 최대 일 수를 선택 합니다.

7.  커밋을 클릭합니다.

</div>

<div>

## <a name="change-the-archiving-policy"></a>보관 정책 변경

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.

4.  정책 목록에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **보관 정책 편집-전역**에서 다음을 수행 합니다.

6.  배포에 대 한 내부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.

7.  배포에 대해 외부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.

8.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>사용자에 게 보관 정책 적용

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

5.  **보관 정책**에서 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 모니터링 보고서 사용](lync-server-2013-using-monitoring-reports.md)  
[Lync Server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md)  
[Lync Server 2013의 미디어 품질 비교 보고서](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

