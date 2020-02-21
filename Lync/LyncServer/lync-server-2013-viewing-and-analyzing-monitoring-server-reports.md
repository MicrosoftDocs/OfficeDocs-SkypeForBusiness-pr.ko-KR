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
ms.openlocfilehash: 3fc5f963ab9b0181463e3bf065baa61730c9fd0d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 서버 보고서 보기 및 분석

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-19_

모니터링 서버 보고서에서는 최종 사용자에 게 제공 되는 QoE를 모니터링 하기 위한 음성 품질의 여러 가지 방법을 제공 합니다. 또한 모니터링 서버에는 조직에서 사용 및 미디어 품질 추세를 시청 하 고 발생 하는 미디어 품질 문제를 해결 하는 데 사용할 수 있는 몇 가지 기본 제공 보고서가 포함 되어 있습니다.

매일 및 매주 작업을 수행 하기 위해 모니터링 서버 보고서를 유지 하는 주요 부분은 특히 다음과 같이 미디어 품질 보고서를 보고 분석 하는 것입니다.

  - QoE 요약/추세 보고서

  - QoE 성능 보고서

<div>

## <a name="view-reports-from-the-monitoring-server"></a>모니터링 서버에서 보고서 보기

1.  웹 브라우저에서 SQL reporting services를 호스트 하는 서버를 찾습니다.

2.  브라우저 화면에서 필요한 보고서를 확인 합니다.

3.  반드시 내보내기 옵션 및 필요한 출력 형식을 선택 하 여 보고서를 내보냅니다.

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>CDR (통화 정보 기록) 구성

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 상응 하는 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 되어 있는 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **통화 정보 기록**을 클릭합니다.

4.  **통화 정보 기록** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.

5.  삭제를 설정 하려면 **모니터링 서버에 대 한 삭제 사용**을 선택 합니다.

6.  **최대 기간 (일) 동안 통화 정보 기록 유지** 에서 통화 정보 기록을 보존할 최대 일 수를 선택 합니다.

7.  **최대 기간(일) 동안 오류 보고서 데이터 유지:** 에서 오류 보고서를 보존할 최대 일수를 선택합니다.

8.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="configure-qoe"></a>QoE 구성

1.  RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 Delegate Setup Permissions을 참조하십시오.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **체감 품질 데이터**를 클릭합니다.

4.  **체감 품질 데이터** 페이지의 테이블에서 적합한 사이트를 클릭하고 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.

5.  삭제를 설정 하려면 **모니터링 서버에 대 한 삭제 사용**을 선택 합니다.

6.  **최대 기간 (일) 동안 통화 정보 기록 유지** 에서 QoE 데이터를 보존할 최대 일 수를 선택 합니다.

7.  커밋을 클릭합니다.

</div>

<div>

## <a name="change-the-archiving-policy"></a>보관 정책 변경

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 정책**을 클릭합니다.

4.  정책 목록에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

5.  **보관 정책 편집 - 전역**에서 다음을 수행합니다.

6.  배포에 대해 내부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.

7.  배포에 대해 외부 보관을 사용 하거나 사용 하지 않도록 설정 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.

8.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>사용자에 게 보관 정책 적용

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **보관 정책**아래의 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.

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

