---
title: 'Lync Server 2013: 장치 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Lync Server 2013의 장치 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-12_

디바이스 보고서가 마이크와 스피커 보고서 라는 제목의 더 좋을 수 있습니다. 이는 장치 보고서가 통화에 사용 되는 마이크와 스피커로 그룹화 된 통화 관련 메트릭 (불량 통화 백분율, 에코, 음성 전환 시간 등)을 검색 하기 때문입니다. IP 전화 ("장치" 라고도 함)에 관심이 있는 경우에는 [Lync Server 2013에서 Ip 전화 인벤토리 보고서](lync-server-2013-ip-phone-inventory-report.md) 를 대신 사용 합니다.

장치 보고서는 특정 유형의 장치가 다른 장치 보다 낮은 품질의 통화를 많이 겪고 있는지 확인 하는 데 매우 유용 합니다. 이렇게 하면 새 장치를 구입 하거나 기존 장치를 교체할 때 수행 해야 하는 모든 의사 결정에 영향을 줄 수 있습니다.

기본적으로 장치 보고서에 표시 되는 정보는 마이크 (캡처 디바이스) 및 통화에 사용 된 스피커/헤드셋 (렌더링 장치)에도 기반 합니다. 예를 들어 다음과 같은 캡처 장치를 사용 하는 여러 사용자와 다음 렌더링 장치를 가정 합니다. 기본적으로 장치 보고서에 표시 되는 정보는 마이크 (캡처 디바이스) 및 통화에 사용 된 스피커/헤드셋 (렌더링 장치)에도 기반 합니다. 예를 들어 다음과 같은 캡처 장치 및 렌더링 장치를 사용 하는 여러 사용자가 있다고 가정 합니다.

  - 장치 캡처--마이크 (SoundMAX 통합 디지털 HD 오디오)

  - 장치 렌더링--헤드셋의 휴대 전화 (Microsoft LifeChat LX-3000)

해당 사용자가 총 254 통화를 한 경우 보고서에 다음과 같은 항목이 표시 됩니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>캡처 장치</th>
<th>렌더링 장치</th>
<th>통화 볼륨</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>마이크 (SoundMAX 통합 디지털 HD 오디오)</p></td>
<td><p>헤드셋의 휴대 전화 (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


이제 동일한 캡처 장치를 사용 하지만 렌더링 장치가 다른 여러 사용자가 있다고 가정 합니다. 이 경우 캡처 장치 및 렌더 장치의 고유한 조합에 대 한 두 번째 줄 입력이 보고서에 표시 됩니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>캡처 장치</th>
<th>렌더링 장치</th>
<th>통화 볼륨</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>마이크 (SoundMAX 통합 디지털 HD 오디오)</p></td>
<td><p>헤드셋의 휴대 전화 (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>마이크 (SoundMAX 통합 디지털 HD 오디오)</p></td>
<td><p>스피커 (SoundMAX 통합 디지털 HD 오디오)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


지정 된 장치에 대해 총 합계가 표시 되는 경우 (예: 사용 하는 렌더링 장치에 상관 없이 SoundMAX 캡처 장치) 장치 유형 드롭다운 목록에서 적절 한 옵션을 선택 합니다 (캡처 장치 또는 렌더 장치). 이 예제에서 장치 캡처를 선택 하면 다음과 유사한 출력을 제공 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>캡처 장치</th>
<th>통화 볼륨</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>마이크 (SoundMAX 통합 디지털 HD 오디오)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>장치 보고서에 액세스

일반적으로 장치 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다. 그러나 [Lync Server 2013에서 통화 정보 보고서](lync-server-2013-call-detail-report.md) 를 보고 있는 경우 다음 메트릭 중 하나를 클릭 하 여 특정 장치에 대 한 장치 보고서로 드릴 다운할 수 있습니다.

  - 캡처 장치

  - 렌더링 장치

장치 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) 로 드릴 다운할 수 있습니다.

  - 통화 볼륨

  - 통화 불량 백분율

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>장치 보고서를 최대한 활용 하기

장치 이름에 대 한 자세한 내용은 장치 보고서에 자세히 설명 되어 있습니다. 예를 들어 다음과 같은 캡처 장치가 있다고 가정 합니다.

  - Aastra 3002 마이크 (2-Aastra 3002)

  - Aastra 3002 마이크 (3-Aastra 3002)

  - Aastra 3002 마이크 (Aastra 3002)

  - Aastra 6725ip

  - Aastra 6725ip 마이크 (10-Aastra 6725ip)

  - Aastra 6725ip 마이크 (10-Aastra 6725ip)-V0

  - Aastra 6725ip 마이크 (2-Aastra 6725ip)

  - Aastra 6725ip 마이크 (3-Aastra 6725ip)

  - Aastra 6725ip 마이크 (4-Aastra 6725ip)

  - Aastra 6725ip 마이크 (5-Aastra 6725ip)

  - Aastra 6725ip 마이크 (6-Aastra 6725ip)

  - Aastra 6725ip 마이크 (7-Aastra 6725ip)

  - Aastra 6725ip 마이크 (9-Aastra 6725ip)

  - Aastra 6725ip 마이크 (9-Aastra 6725ip)-V0

  - Aastra 6725ip 마이크 (Aastra 6725ip)

  - Aastra 6725ip 마이크 (Aastra 6725ip)-V0

  - Aastra 6725ip 마이크 (USB 오디오 장치)

  - Aastra 6725ip 마이크 (USB 오디오 장치)-V0

<div>


> [!NOTE]  
> Lync Server 2013의 번역 된 버전을 실행 하는 경우 캡처 장치 이름이 동일 하지 않을 수 있다는 점에 유의 하세요. 미국 영어에서 Aastra 6725ip 마이크 (Aastra 6725ip)-V0 이라는 장치는 프랑스어 또는 스페인어의 다른 이름을 가질 수 있습니다.



</div>

해당 수준에 대 한 자세한 정보를 알고 싶은 경우가 있습니다. 그러나 다른 시간에는 모델 번호에 관계 없이 Aastra 마이크를 사용 하는 통화의 수에만 관심이 있을 수 있습니다. 이와 같은 정보를 얻으려면 Microsoft Excel로 장치 보고서 데이터를 내보낸 다음 해당 데이터를 쉼표로 구분 된 값 파일 (예: C:\\data\\Devices\_Report. m a m)에 저장 하는 것입니다. 그런 다음 다음과 비슷한 명령 집합을 사용 하 여를 가져올 수 있습니다. CSV 파일을 Windows PowerShell에 표시 하 고 Aastra 캡처 장치를 사용 하 여 생성 된 총 통화 수를 보고 합니다.

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

그러면 Aastra 캡처 장치를 사용 하 여 만든 총 통화 수를 나타내는 single 값이 반환 됩니다. 예를 들면 다음과 같습니다.

    384

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 장치 보고서를 사용 하 여 통화 유형 (즉, 클라이언트 전화 통화), 컨퍼런스 통화 또는 PSTN (공공 전환 전화 네트워크) 통화 등의 항목을 필터링 할 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우 장치는 시간, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 장치 보고서에 사용할 수 있는 필터가 나열 되어 있습니다.

### <a name="device-report-filters"></a>장치 보고서 필터

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>보낸 사람</strong></p></td>
<td><p>시간 범위의 시작 날짜/시간입니다. 시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</p>
<p>오후 7/7/2012 1:00</p>
<p>시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/7/2012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/3/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>받는 사람</strong></p></td>
<td><p>시간 범위의 종료 날짜/시간입니다. 시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</p>
<p>오후 7/7/2012 1:00</p>
<p>종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/7/2012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/3/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>음성 스위치 원인</strong></p></td>
<td><p>에코를 방지 하기 위해 통화를 반이중 모드로 전환 해야 하는 이유입니다. 반이중 모드에서는 통신을 한 번에 한 방향 으로만 이동할 수 있으며, walkie-talkie와 통신 하는 경우에도 동일 하 게 적용 됩니다. 다음 중 하나를 선택 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>모든</p>
</dd>
<dt><span></span></dt>
<dd><p>없음</p>
</dd>
<dt><span></span></dt>
<dd><p>잘못 된 타임 스탬프</p>
</dd>
<dt><span></span></dt>
<dd><p>O</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (동적 비선형 프로세서)</p>
</dd>
<dt><span></span></dt>
<dd><p>낮은 복잡도</p>
</dd>
<dt><span></span></dt>
<dd><p>잘못 된 장치 상태</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 이후 에코 (음향 반향 제거)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>에코 원인</strong></p></td>
<td><p>통화 중에 허용 된 수준 위의 반향을 감지 하는 이유입니다. (텔레커뮤니케이션에서 echo는 소리를 반사 하는 것으로, 잘 아래쪽으로 yell 때 들릴 수 있는 것과 같은 현상을 말합니다.) 다음 중 하나를 선택 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>모든</p>
</dd>
<dt><span></span></dt>
<dd><p>없음</p>
</dd>
<dt><span></span></dt>
<dd><p>잘못 된 타임 스탬프</p>
</dd>
<dt><span></span></dt>
<dd><p>AEC 이후 에코 (음향 반향 제거)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (적응 비선형 프로세서)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (동적 비선형 프로세서)</p>
</dd>
<dt><span></span></dt>
<dd><p>마이크 클리핑</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>통화 종류</strong></p></td>
<td><p>발생 한 통화 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>모든</p>
</dd>
<dt><span></span></dt>
<dd><p>클라이언트 통화</p>
</dd>
<dt><span></span></dt>
<dd><p>PSTN 통화</p>
</dd>
<dt><span></span></dt>
<dd><p>컨퍼런스 통화</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Access 형식</strong></p></td>
<td><p>전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>모든</p>
</dd>
<dt><span></span></dt>
<dd><p>내부용</p>
</dd>
<dt><span></span></dt>
<dd><p>내부</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>네트워크 유형</strong></p></td>
<td><p>전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>모든</p>
</dd>
<dt><span></span></dt>
<dd><p>유</p>
</dd>
<dt><span></span></dt>
<dd><p>Wireless-n</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>모든</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>비 VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>장치 유형</strong></p></td>
<td><p>장치 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<dl>
<dt><span></span></dt>
<dd><p>캡처 장치</p>
</dd>
<dt><span></span></dt>
<dd><p>렌더링 장치</p>
</dd>
<dt><span></span></dt>
<dd><p>장치 쌍 캡처/렌더링</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>장치 이름</strong></p></td>
<td><p>캡처 또는 렌더링 디바이스의 이름입니다. 전체 장치 이름 또는 장치 이름의 일부를 입력할 수 있습니다. 예를 들어 디바이스 마이크 (Microsoft LifeCam VX-1000)를 찾으려면 다음과 같이 전체 장치 이름을 입력 하면 됩니다.</p>
<p>마이크 (Microsoft LifeCam VX-1000)</p>
<p>또는 이름의 일부만 입력할 수도 있습니다. 예를 들면 다음과 같습니다.</p>
<p>LifeCam</p>
<p>위의 필터는 이름에 LifeCam &quot;&quot; 문자열을 포함 하는 모든 장치를 반환 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 장치 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="device-report-metrics"></a>장치 보고서 메트릭

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>캡처 장치</strong></p></td>
<td><p>예</p></td>
<td><p>오디오를 전송 하는 데 사용 되는 장치 (예: 마이크 또는 웹캠)</p></td>
</tr>
<tr class="even">
<td><p><strong>렌더링 장치</strong></p></td>
<td><p>예</p></td>
<td><p>오디오를 수신 하는 데 사용 되는 장치 (예: 헤드셋 또는 스피커)</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화 볼륨</strong></p></td>
<td><p>예</p></td>
<td><p>총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>통화 불량 백분율</strong></p></td>
<td><p>예</p></td>
<td><p>불량으로 &quot;분류 된 통화의 백분율입니다. &quot; 잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>고유 사용자</strong></p></td>
<td><p>예</p></td>
<td><p>장치를 사용 하는 고유한 사용자입니다. 사용자가 장치를 13 번 사용 하는 경우 한 명의 고유 사용자로 서 한 번만 장치를 사용 하는 사용자와 동일 하 게 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>음성 전환 시간 비율</strong></p></td>
<td><p>예</p></td>
<td><p>에코를 방지 하기 위해 반이중 모드에서 수행 해야 하는 통화의 백분율입니다. 반이중 모드에서는 통신을 한 번에 한 방향 으로만 이동할 수 있으며, walkie-talkie와 통신 하는 경우에도 동일 하 게 적용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>마이크 작동 하지 않는 비율</strong></p></td>
<td><p>예</p></td>
<td><p>캡처 장치가 허용 되는 수준에서 작동 하지 않는 통화의 백분율입니다. 값이 높으면 특히 캡처 장치가 정상적으로 작동 하지 않기 때문에 통화의 품질 문제가 발생 하는 것을 제안 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>스피커 작동 하지 않는 비율</strong></p></td>
<td><p>예</p></td>
<td><p>렌더링 장치가 허용 되는 수준에서 작동 하지 않는 통화의 백분율입니다. 값이 높으면 특히 렌더링 장치가 정상적으로 작동 하지 않기 때문에 통화의 품질 문제가 발생 하는 것을 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>음성 스위치가 있는 통화 (%)</strong></p></td>
<td><p>예</p></td>
<td><p>반이중 모드에 배치 해야 했던 총 통화의 백분율입니다. 반이중 모드에서는 통신을 한 번에 한 방향 으로만 이동할 수 있으며, walkie-talkie와 통신 하는 경우에도 동일 하 게 적용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>(%)에 에코 마이크</strong></p></td>
<td><p>예</p></td>
<td><p>마이크 캡처 스트림에 화면 표시가 감지 된 시간의 백분율입니다. 일반적으로 헤드셋 이나 송수화기의 경우 값은 낮고 스피커 전화 또는 독립 실행형 스피커는 더 높습니다. 화상 음향 반향 제거를 지 원하는 디바이스의 경우 높은 값은 에코 누수를 나타냅니다. 다른 디바이스의 경우이 메트릭은 장치 품질을 평가 하는 데 사용해 서는 안 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>에코 보내기 (%)</strong></p></td>
<td><p>예</p></td>
<td><p>다른 사용자에 게 전송 되는 에코의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>에코 (%)로 전화 걸기</strong></p></td>
<td><p>예</p></td>
<td><p>에코에 허용 되는 수준을 초과한 총 통화의 백분율입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

