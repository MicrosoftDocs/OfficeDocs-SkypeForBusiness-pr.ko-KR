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
ms.openlocfilehash: 3e9f42d2467a77e35eb9f5a158967357534e86da
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Lync Server 2013의 다이얼 플랜 및 정규화 규칙

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

다이얼 플랜은 전화 인증 및 통화 라우팅을 위해 명명된 위치, 개별 사용자 또는 연락처 개체의 전화 번호를 하나의 표준(E.164) 형식으로 변환하는 명명된 정규화 규칙 집합입니다.

정규화 규칙은 다양한 형식으로 표현된 전화 번호를 지정된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅하는 방법을 정의합니다. 전화를 거는 위치와 통화를 수행 하는 사람 또는 대화 상대 개체에 따라 같은 다이얼 문자열이 다르게 해석 되 고 변환 될 수 있습니다.

<div>

## <a name="dial-plan-scope"></a>다이얼 플랜 범위

다이얼 플랜의 *범위*는 다이얼 플랜을 적용할 수 있는 계층 수준을 결정합니다. Lync Server에서는 사용자에 게 특정 사용자별 다이얼 플랜을 할당할 수 있습니다. 사용자 다이얼 플랜이 할당되지 않으면 등록자 풀 다이얼 플랜이 적용됩니다. 등록자 풀 다이얼 플랜이 없는 경우 사이트 다이얼 플랜이 적용됩니다. 마지막으로 사용자에게 적용되는 다른 다이얼 플랜이 없는 경우 전역 다이얼 플랜이 적용됩니다.

클라이언트는 사용자가 Lync Server에 로그온 할 때 제공 되는 대역내 프로 비전 설정을 통해 다이얼 플랜 범위 수준을 가져옵니다. 관리자는 Lync Server 제어판을 사용 하 여 다이얼 플랜 범위 수준을 관리 하 고 할당할 수 있습니다.

<div>


> [!NOTE]  
> 서비스 수준 PSTN (공중 전화망) 게이트웨이 다이얼 플랜은 특정 게이트웨이에서 들어오는 호출에 적용 됩니다.



</div>

다이얼 플랜 범위 수준은 다음과 같이 정의할 수 있습니다.

  - **사용자 다이얼 플랜:** 개별 사용자, 그룹 또는 연락처 개체에 할당할 수 있습니다. 음성 응용 프로그램은 전화 컨텍스트를 사용자 기본값으로 설정 하 여 통화가 수신 되는 경우 사용자별 다이얼 플랜을 조회할 수 있습니다. 다이얼 플랜을 지정 하기 위해 연락처 개체가 개별 사용자로 처리 됩니다.

  - **풀 다이얼 플랜:** 토폴로지의 모든 PSTN 게이트웨이 또는 등록자에 대 한 서비스 수준에서 만들 수 있습니다. 풀 다이얼 플랜을 정의하려면 다이얼 플랜을 적용할 특정 서비스(PSTN 게이트웨이 또는 등록자 풀)를 지정해야 합니다.

  - **사이트 다이얼 플랜:** 풀 다이얼 플랜 또는 사용자 다이얼 플랜이 할당 된 모든 사용자, 그룹 또는 연락처 개체를 제외 하 고 전체 사이트에 대해 만들 수 있습니다. 사이트 다이얼 플랜을 정의하려면 다이얼 플랜을 적용할 사이트를 지정해야 합니다.

  - **전역 다이얼 플랜:** 제품과 함께 설치 되는 기본 다이얼 플랜입니다. 전역 다이얼 플랜을 편집할 수 있지만 삭제할 수는 없습니다. 이 다이얼 플랜은 더 구체적인 범위를 사용 하 여 다이얼 플랜을 구성 및 할당 하지 않는 한 배포의 모든 Enterprise Voice 사용자, 그룹 및 연락처 개체에 적용 됩니다.

</div>

<div>

## <a name="planning-for-dial-plans"></a>다이얼 플랜 계획

다이얼 플랜을 계획 하려면 다음 단계를 수행 합니다.

  - 조직에 office가 있는 모든 로캘을 나열 합니다.
    
    목록이 최신 상태이 고 완료 되어야 합니다. 또한 회사 조직이 발전함에 따라 목록도 수정되어야 합니다. 규모가 작은 다국적 대기업에서는 시간이 많이 소요 되는 작업이 될 수 있습니다.

  - 각 사이트의 유효한 번호 패턴을 확인 합니다.
    
    다이얼 플랜 계획 중 가장 시간이 오래 걸리는 부분은 각 사이트에 유효한 숫자 패턴을 식별하는 것입니다. 경우에 따라, 특히 해당 사이트가 같은 국가/지역 또는 대륙 내에 있는 경우 한 다이얼 플랜에 대해 작성한 정규화 규칙을 다른 다이얼 플랜에 복사할 수 있습니다. 한 다이얼 플랜에서 번호를 조금만 변경해서 다른 다이얼 플랜에 사용할 수도 있습니다.

  - 다이얼 플랜을 명명 하기 위한 조직 차원의 구성표를 개발 합니다.
    
    표준 명명 체계를 도입하면 조직 전체에서 일관성을 보장하고 유지 관리 및 업데이트를 더 수월하게 할 수 있습니다.

  - 단일 위치에 여러 다이얼 플랜이 필요한 지 여부를 결정 합니다.
    
    조직에서 여러 위치에 대해 단일 다이얼 플랜을 유지 관리 하는 경우에도 PBX (private branch exchange)에서 마이그레이션하는 Enterprise Voice 사용자에 대해 별도의 다이얼 플랜을 만들고 기존 내선 번호를 보존 해야 할 수 있습니다.

  - 사용자 단위 다이얼 플랜이 필요한 지 여부를 결정 합니다. 예를 들어 중앙 사이트에 등록 된 분기 사이트에 사용자가 있거나 Sba (survivable Branch 기기에 등록 된 사용자가 있는 경우 이러한 사용자에 대 한 특수 전화 걸기 시나리오를 사용 하 여 사용자별 다이얼 플랜 및 정규화 규칙을 고려할 수 있습니다. . 자세한 내용은 [Lync Server 2013에 대 한 분기 사이트 복구 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.

  - 다이얼 플랜 범위 결정 (이 항목의 앞 부분에 설명 된 대로)

다이얼 플랜을 만들려면 필요에 따라 Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 다음 필드에 값을 지정 합니다.

<div>

## <a name="name-and-simple-name"></a>이름 및 단순한 이름

사용자 다이얼 플랜의 경우 다이얼 플랜이 할당 되는 사용자, 그룹 또는 연락처 개체를 식별 하는 설명이 포함 된 이름을 지정 해야 합니다. 사이트 다이얼 플랜의 경우 이름 필드에 사이트 이름이 미리 채워지며 이는 변경할 수 없습니다. 풀 다이얼 플랜의 경우 이름 필드에 PSTN 게이트웨이 또는 프런트 엔드 풀 FQDN (정규화 된 도메인 이름)이 미리 채워져 있어 변경할 수 없습니다.

다이얼 플랜 *단순한 이름*에는 다이얼 플랜 이름에서 파생된 문자열이 미리 채워집니다. 간단한 이름 필드는 편집 가능 하며,이를 통해 다이얼 플랜에 대 한 보다 설명적인 명명 규칙을 만들 수 있습니다. *단순한 이름* 값은 비워 둘 수 없으며 고유해야 합니다. 전체 조직에 대 한 명명 규칙을 개발한 다음 모든 사이트 및 사용자에 대해 일관 되 게이 규칙을 사용 하는 것이 좋습니다.

</div>

<div>

## <a name="description"></a>설명

해당 다이얼 플랜이 적용되는 지역 위치에 대한 일반적이고 쉽게 알아볼 수 있는 이름을 입력하는 것이 좋습니다. 예를 들어 다이얼 플랜 이름이 London.Contoso.com이면 권장되는 설명은 런던입니다.

</div>

<div>

## <a name="dial-in-conferencing-region"></a>전화 접속 회의 지역

전화 접속 회의를 배포하는 경우 다이얼 플랜과 전화 접속 회의 액세스 번호를 연결할 전화 접속 회의 지역을 지정해야 합니다.

</div>

<div>

## <a name="external-access-prefix"></a>외부 액세스 접두사

사용자가 하나 이상의 추가 선행 번호 (예: 9)를\#사용 \*하 여 외부 회선을 사용 해야 하는 경우 최대 4 자 (,, 0-9)의 외부 액세스 접두사를 지정할 수 있습니다.

<div>


> [!NOTE]  
> 외부 액세스 접두사를 지정하면 접두사를 수용하기 위해 추가 정규화 규칙을 만들 필요가 없습니다.



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>정규화 규칙

정규화 규칙은 다양한 형식으로 표현된 전화 번호를 명명된 위치에 대해 라우팅하는 방법을 정의합니다. 같은 숫자 문자열은 전화를 거는 로캘에 따라 다르게 해석 되 고 변환 될 수 있습니다. 사용자가 대화 상대 목록에 전화 번호를 입력할 때 여러 형식을 사용할 수 있고 또 사용하기 때문에 정규화 규칙은 통화 라우팅에 필요합니다.

사용자가 제공한 전화 번호 정규화는 다음과 같은 작업을 용이 하 게 하는 일관 된 형식을 제공 합니다.

  - 전화 건 번호를 의도 한 받는 사람의 SIP URI와 일치 시킵니다.

  - 통화 당사자에 게 전화 걸기 권한 부여 규칙을 적용 합니다.

정규화 규칙에서 고려해야 하는 숫자 필드는 다음과 같습니다.

  - 다이얼 플랜

  - 국가 번호

  - 지역 번호

  - 내선 번호 길이

  - 사이트 접두사

<div>

## <a name="creating-normalization-rules"></a>정규화 규칙 만들기

정규화 규칙은 .NET Framework 정규식을 사용하여 서버가 역방향 번호 조회를 수행하기 위해 전화 걸기 문자열을 E.164 형식으로 변환하는 데 사용하는 숫자 일치 패턴을 지정합니다. 수동으로 식을 입력 하거나, 일치 시킬 전화 걸기 문자열의 길이를 입력 하 여 Lync Server 제어판에서 정규화 규칙을 만들거나, Lync Server 제어판에서 해당 사용자를 위한 정규식입니다. 두 경우 모두 완료되면 테스트 번호를 입력하여 정규화 규칙이 예상대로 작동하는지 확인할 수 있습니다.

.NET Framework 정규식 사용에 대 한 자세한 내용은의 ".NET Framework 정규식"을 참조 [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)하십시오.

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>샘플 정규화 규칙

다음 표는 .NET Framework 정규식으로 작성된 샘플 정규화 규칙을 보여 줍니다. 샘플은 예로만 제공되며 정규화 규칙을 만드는 방법에 대한 규정은 아닙니다.

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>표 1. .NET Framework 정규식을 사용한 정규화 규칙

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
<th>발신 제한</th>
<th>Translation</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>4자리 내선 번호 변환</p></td>
<td><p>^ (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>0100이 +14255550100으로 변환됨</p></td>
</tr>
<tr class="even">
<td><p>: 5Digitextension</p></td>
<td><p>5자리 내선 번호 변환</p></td>
<td><p>^ 5 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>50100이 +14255550100으로 변환됨</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>7자리 번호를 레드몬드 지역 번호로 변환</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1425 $1</p></td>
<td><p>5550100이 +14255550100으로 변환됨</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>7자리 번호를 달라스 지역 번호로 변환</p></td>
<td><p>^ (\d{7}) $</p></td>
<td><p>+ 1972 $1</p></td>
<td><p>5550100이 +19725550100으로 변환됨</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>미국 10자리 번호 변환</p></td>
<td><p>^ (\d{10}) $</p></td>
<td><p>+ 1 $1</p></td>
<td><p>2065550100이 +12065550100으로 변환됨</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>미국 시외 접두사 포함 번호 변환</p></td>
<td><p>^ 1 (\d{10}) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100이 +2145550100으로 변환됨</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>미국 국가별 접두사 포함 번호 변환</p></td>
<td><p>^ 011 (\d *) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100이 +91445550100으로 변환됨</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>0을 레드몬드 교환으로 변환</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0이 +14255550100으로 변환됨</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>온넷 접두사(6) 및 레드몬드 사이트 코드(222) 포함 번호 변환</p></td>
<td><p>^ 6222 (\d{4}) $</p></td>
<td><p>+ 1425555 $1</p></td>
<td><p>62220100이 +14255550100으로 변환됨</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>온넷 접두사(6) 및 뉴욕 사이트 코드(333) 포함 번호 변환</p></td>
<td><p>^ 6333 (\d{4}) $</p></td>
<td><p>+ 1202555 $1</p></td>
<td><p>63330100이 +12025550100으로 변환됨</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>온넷 접두사(6) 및 달라스 사이트 코드(444) 포함 번호 변환</p></td>
<td><p>^ 6444 (\d{4}) $</p></td>
<td><p>+ 1972555 $1</p></td>
<td><p>64440100이 +19725550100으로 변환됨</p></td>
</tr>
</tbody>
</table>


다음 표는 앞의 표에 나열된 정규화 규칙을 기반으로 미국 워싱턴주 레드몬드에 대한 샘플 다이얼 플랜을 보여 줍니다.

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>표 2. 표 1에 표시된 정규화 규칙에 기초한 레드몬드 다이얼 플랜

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>ForestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>: 5Digitextension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
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
> 앞의 표에 나열된 정규화 규칙에는 공백이 포함되어 있지 않지만 이는 선택의 문제입니다. 예를 들어 표의 첫 번째 이름을 "5 digit extension" 또는 "5-digit Extension"으로 작성해도 유효합니다.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

