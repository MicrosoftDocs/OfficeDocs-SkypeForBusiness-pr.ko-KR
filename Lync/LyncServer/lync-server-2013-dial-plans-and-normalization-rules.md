---
title: 'Lync Server 2013: 다이얼 플랜 및 정규화 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4f1cc8221281502487a8f58e1562674432ea29d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Lync Server 2013의 다이얼 플랜 및 정규화 규칙

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

다이얼 플랜은 전화 인증 및 통화 라우팅과 같은 목적으로 명명 된 위치, 개인 사용자 또는 연락처 개체의 전화 번호를 단일 표준 (E) 형식으로 변환 하는 정규화 규칙의 명명 된 집합입니다.

정규화 규칙은 다양 한 형식으로 표시 되는 전화 번호가 지정 된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅되는 방법을 정의 합니다. 전화 거는 위치와 전화를 걸고 있는 사람 또는 연락처 개체에 따라 같은 다이얼 문자열을 다르게 해석 하 고 번역할 수 있습니다.

<div>

## <a name="dial-plan-scope"></a>다이얼 플랜 범위

다이얼 플랜의 *범위* 는 다이얼 플랜을 적용할 수 있는 계층 수준을 결정 합니다. Lync Server에서는 사용자에 게 특정 사용자 단위 다이얼 플랜을 할당할 수 있습니다. 사용자 다이얼 플랜을 할당 하지 않으면 등록자 그룹 다이얼 플랜이 적용 됩니다. 등록자 풀 다이얼 플랜이 없으면 사이트 다이얼 플랜이 적용 됩니다. 마지막으로, 사용자에 게 적용 가능한 다른 다이얼 플랜이 없으면 전역 다이얼 플랜이 적용 됩니다.

클라이언트는 사용자가 Lync Server에 로그온 할 때 제공 되는 대역내 프로비저닝 설정을 통해 다이얼 플랜 범위 수준을 가져옵니다. 관리자는 Lync Server 제어판을 사용 하 여 다이얼 플랜 범위 수준을 관리 하 고 할당할 수 있습니다.

<div>


> [!NOTE]  
> 서비스 수준 PSTN (공개 교환 전화 네트워크) 게이트웨이 다이얼 플랜은 특정 게이트웨이에서 들어오는 전화에 적용 됩니다.



</div>

다이얼 플랜 범위 수준은 다음과 같이 정의 됩니다.

  - **사용자 다이얼 플랜:** 개인 사용자, 그룹 또는 연락처 개체에 할당할 수 있습니다. 음성 응용 프로그램은 전화-컨텍스트를 사용자-기본으로 설정한 상태에서 통화를 받을 때 사용자 단위 다이얼 플랜을 조회할 수 있습니다. 다이얼 플랜을 지정 하기 위해 연락처 개체는 개별 사용자로 처리 됩니다.

  - **풀 다이얼 플랜:** 토폴로지에서 PSTN 게이트웨이 또는 등록자에 대 한 서비스 수준에서 만들 수 있습니다. 풀 다이얼 플랜을 정의 하려면 다이얼 플랜을 적용할 특정 서비스 (PSTN 게이트웨이 또는 등록자 풀)를 지정 해야 합니다.

  - **사이트 다이얼 플랜:** 풀 다이얼 플랜 또는 사용자 다이얼 플랜에 할당 된 사용자, 그룹 또는 연락처 개체를 제외한 전체 사이트에 대해 만들 수 있습니다. 사이트 다이얼 플랜을 정의 하려면 다이얼 플랜을 적용할 사이트를 지정 해야 합니다.

  - **글로벌 다이얼 플랜:** 제품과 함께 설치 된 기본 다이얼 플랜입니다. 전역 다이얼 플랜은 편집할 수 있지만 삭제할 수는 없습니다. 이 다이얼 플랜은 보다 구체적인 범위를 사용 하 여 다이얼 플랜을 구성 하 고 지정 하지 않는 한 배포의 모든 Enterprise Voice 사용자, 그룹 및 연락처 개체에 적용 됩니다.

</div>

<div>

## <a name="planning-for-dial-plans"></a>다이얼 플랜 계획

다이얼 플랜을 계획 하려면 다음 단계를 따르세요.

  - 조직에 office가 있는 모든 로캘을 나열 합니다.
    
    목록은 최신 상태 여야 하며 완료 되어야 합니다. 회사 조직이 변화 함에 따라 수정 해야 합니다. 소규모 지사의 수가 많은 다국적 대기업에서는 시간이 오래 걸리는 작업이 가능 합니다.

  - 각 사이트의 유효한 번호 패턴을 확인 합니다.
    
    다이얼 플랜 계획 중 시간이 오래 걸리는 부분은 각 사이트의 유효한 번호 패턴을 식별 하는 것입니다. 일부 경우에는 해당 사이트가 같은 국가/지역 또는 대륙 내에 있는 경우 특정 다이얼 플랜에 대해 작성 한 정규화 규칙을 다른 다이얼 플랜에 복사할 수 있습니다. 다른 경우에는 특정 다이얼 플랜에서 숫자를 약간만 변경 하면 다른 다이얼 플랜에서이를 사용 하는 것이 충분할 수 있습니다.

  - 다이얼 플랜의 이름을 지정 하기 위한 조직 차원의 스키마를 개발 합니다.
    
    표준 명명 스키마를 채택 하면 조직 전체의 일관성을 보장 하 고 유지 관리 및 업데이트를 쉽게 할 수 있습니다.

  - 단일 위치에 여러 다이얼 플랜이 필요한 지 여부를 결정 합니다.
    
    조직에서 여러 위치에 걸친 단일 다이얼 플랜을 유지 관리 하는 경우에도, PBX (개인 브랜치 교환)에서 마이그레이션하는 Enterprise Voice 사용자를 위한 별도의 다이얼 플랜을 만들어야 하며, 기존 확장을 보존 해야 하는 경우가 있을 수 있습니다.

  - 사용자 단위 다이얼 플랜이 필요한 지 여부를 결정 합니다. 예를 들어 중앙 사이트를 사용 하 여 등록 한 지점 사이트에 사용자가 있거나 Survivable Branch 기기에 등록 된 사용자가 있는 경우, 사용자에 대 한 다이얼 플랜 및 정규화 규칙을 사용 하 여 해당 사용자에 대 한 특별 한 전화 접속 시나리오를 고려할 수 있습니다. . 자세한 내용은 [Lync Server 2013에 대 한 지점 사이트 복원 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.

  - 다이얼 플랜 범위 결정 (이 항목의 이전 설명 참조).

다이얼 플랜을 만들려면 필요에 따라 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 다음 필드에 값을 지정 합니다.

<div>

## <a name="name-and-simple-name"></a>이름 및 단순한 이름

사용자 다이얼 플랜의 경우 다이얼 플랜이 할당 되는 사용자, 그룹 또는 연락처 개체를 식별 하는 설명적인 이름을 지정 해야 합니다. 사이트 다이얼 플랜의 경우 이름 필드는 사이트 이름으로 미리 채워져 있으므로 변경할 수 없습니다. 풀 다이얼 플랜의 경우 이름 필드는 PSTN 게이트웨이 또는 프론트 엔드 풀 정규화 된 도메인 이름 (FQDN)으로 미리 채워 있으므로 변경할 수 없습니다.

다이얼 플랜의 *단순한 이름* 에는 다이얼 플랜 이름에서 파생 된 문자열이 미리 채워져 있습니다. 간단한 이름 필드는 편집 가능 하며,이를 통해 다이얼 플랜에 대 한 보다 설명적인 명명 규칙을 만들 수 있습니다. *간단한 이름* 값은 비워 둘 수 없으며 고유 해야 합니다. 전체 조직의 명명 규칙을 개발한 다음 모든 사이트와 사용자에 게 일관 되 게이 규칙을 사용 하는 것이 가장 좋습니다.

</div>

<div>

## <a name="description"></a>설명

해당 다이얼 플랜이 적용 되는 지리적 위치에 대해 인식할 수 있는 일반적인 이름을 입력 하는 것이 좋습니다. 예를 들어 다이얼 플랜 이름이 London.Contoso.com 경우 권장 설명은 London입니다.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>전화 접속 회의 지역

전화 접속 회의를 배포 하는 경우 다이얼 인 회의 액세스 번호를 다이얼 플랜에 연결 하려면 전화 접속 회의 지역을 지정 해야 합니다.

</div>

<div>

## <a name="external-access-prefix"></a>외부 액세스 접두사

외부 회선을 얻으려면 사용자가 하나 이상의 추가 선행 번호 (예\#: \*9)로 전화를 걸어야 하는 경우 최대 4 자 (,, 0-9)로 외부 액세스 접두사를 지정할 수 있습니다.

<div>


> [!NOTE]  
> 외부 액세스 접두사를 지정 하는 경우 접두사를 수용할 수 있는 추가 정규화 규칙을 만들 필요가 없습니다.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>정규화 규칙

정규화 규칙은 다양 한 형식으로 표시 되는 전화 번호가 명명 된 위치에 대해 라우팅되는 방법을 정의 합니다. 같은 숫자 문자열은이를 거는 로케일에 따라 다르게 해석 하 고 번역할 수 있습니다. 사용자는 연락처 목록에 전화 번호를 입력할 때 다양 한 형식을 사용할 수 있기 때문에 통화 라우팅에 정규화 규칙이 필요 합니다.

사용자 제공 전화 번호 정규화는 다음 작업을 용이 하 게 하는 일관 된 형식을 제공 합니다.

  - 전화를 받는 사람의 SIP URI와 번호를 일치 시킵니다.

  - 전화 건이에 대 한 권한 부여 규칙을 통화 파티에 적용 합니다.

다음 번호 필드는 정규화 규칙에서 고려해 야 할 수 있습니다.

  - 다이얼 플랜

  - 국가 코드

  - 지역 번호

  - 확장 길이

  - 사이트 접두사

<div>

## <a name="creating-normalization-rules"></a>정규화 규칙 만들기

정규화 규칙에서는 검색 문자열을 변환 하는 데 사용 되는 숫자 일치 패턴을 지정 하기 위해 서버에서 역방향 번호 조회를 수행 하기 위한 목적으로이 정규식을 사용 합니다. 수동으로 식을 입력 하거나, 일치 시킬 다이얼 문자열의 시작 숫자와 길이를 입력 하 여 Lync Server 제어판에서 정규화 규칙을 만들 수 있습니다. 사용자에 게 정규식을 표시 합니다. 두 방법 중 하나를 마치면 테스트 번호를 입력 하 여 정규화 규칙이 예상 대로 작동 하는지 확인할 수 있습니다.

.NET Framework 정규식을 사용 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net framework 정규식"을 참조 하세요.

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>예제 정규화 규칙

다음 표에는 .NET Framework 정규식으로 작성 된 예제 정규화 규칙이 나와 있습니다. 샘플은 예일 뿐 이며 고유한 정규화 규칙을 만들기 위한 규범적 참조 일 수 없습니다.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>표 1. .NET Framework 정규식을 사용 하는 정규화 규칙

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>규칙 이름</th>
<th>설명</th>
<th>번호 패턴</th>
<th>변환용</th>
<th>예</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>4 자리 확장을 변환 합니다.</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>0100는 + 14255550100로 변환 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>다섯 자리 확장명 변환</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>50100는 + 14255550100로 변환 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>7 자리 숫자를 Redmond 지역 번호로 변환 합니다.</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1425 $1</p></td>
<td><p>5550100는 + 14255550100로 변환 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>7 자리 숫자를 달라스 지역 번호로 변환</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100는 + 19725550100로 변환 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>미국에서 10 자리 숫자를 변환 합니다.</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+ 1 $1</p></td>
<td><p>2065550100는 + 12065550100로 변환 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>미국에서 시외 접두 번호를 사용 하 여 숫자를 번역 합니다.</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100는 + 2145550100로 변환 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>소개</p></td>
<td><p>미국에서 국제 접두 번호로 번호를 번역 합니다.</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100는 + 91445550100로 변환 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>0에서 레드먼드 연산자로 변환</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0이 + 14255550100로 변환 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>A-net 접두사 (6) 및 Redmond 사이트 코드 (222)를 사용 하 여 숫자를 변환 합니다.</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>62220100는 + 14255550100로 변환 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>순 접두 (6) 및 (333) 전화 번호를 사용 하 여 숫자를 번역 합니다.</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100는 + 12025550100로 변환 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>A-net 접두사 (6) 및 달라스 사이트 코드 (444)를 사용 하 여 숫자를 변환 합니다.</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+ 1972555 $1</p></td>
<td><p>64440100는 + 19725550100로 변환 됩니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 이전 표에 표시 된 표준화 규칙에 따라 Redmond, 인천, 미국에 대 한 예제 다이얼 플랜을 보여 줍니다.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>표 2. 표 1에 표시 된 정규화 규칙을 기반으로 하는 Redmond 다이얼 플랜

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond forestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>소개</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 앞의 표에 나와 있는 정규화 규칙 이름에는 공백이 포함 되지 않지만, 선택 하는 것이 중요 합니다. 예를 들어 표의 이름에는 "5 자리 내선" 또는 "5 자리 내선 번호"가 기록 되 고 여전히 유효 합니다.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

