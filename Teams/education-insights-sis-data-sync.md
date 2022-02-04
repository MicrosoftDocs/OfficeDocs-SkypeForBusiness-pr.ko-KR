---
title: SIS(학생 정보 시스템) 데이터와 Education Insights 동기화
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: SIS(학생 정보 시스템) 데이터를 Microsoft Teams의 Education Insights 동기화
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b22b66800e71f1cea90c31b7091eb98a99466e9f
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363024"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>SIS(학생 정보 시스템) 데이터와 Education Insights 동기화
더 많은 데이터가 [Education Insights](class-insights.md)에 제공될수록 교육자는 학생을 더 잘 지원할 수 있으며 교육 리더는 교육자를 더 잘 지원할 수 있습니다.

조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조가 올바르게 매핑되도록 [SDS(학교 데이터 동기화)](/SchoolDataSync)를 사용하여 SIS(학생 정보 시스템)에 연결해야 합니다. 

Teams의 수업 구조와 권한을 사용하기 때문에 이 동기화에 대해 수업 교육자로서 수업 수준 Insights를 볼 필요가 *없습니다*.

## <a name="plan-your-school-data-sync-integration"></a>학교 데이터 동기화 통합 계획
Microsoft School 데이터 동기화(SDS라고도 함)는 학교 정보 시스템(즉, SIS) 데이터를 제공하며 교육 시스템의 계층 구조이며, 학생 및 조직 계층 구조에 대한 추가 데이터를 제공하며, 할당된 사용자를 매핑합니다.

Insights는 [SDS V2.1 파일 형식](/schooldatasync/sds-v2.1-csv-file-format)을 사용할 때 가장 잘 작동하지만 [SDS V2 파일 형식](/schooldatasync/sds-v2-csv-file-format) 및 [SDS V1 파일 형식에서](/schooldatasync/school-data-sync-format-csv-files-for-sds) *제한적으로 작동합니다*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>SDS V1과 V2 파일 형식의 차이점

| 데이터 형식 | V1 | V2 및 V2.1 |
|:--- |:--- |:--- |
| **사용자** |교육 리더에 대한 조직 수준 권한을 수동으로 설정해야 하므로 ‘강사‘ 역할만 지원됩니다.|역할 기반 권한을 설정할 수 있도록 다중 역할을 지원합니다.|
| **조직** | '학교' 집계 수준만 지원합니다.<br><br>따라서 다중 집계 수준을 제공하지 않으며 다른 유형의 학교(예: 초등학교와 중/고등학교, 과학중/고등학교와 예술중/고등학교)를 비교하기 위해 제한된 기능을 제공합니다.|구역/기관, 대학(4년제), 대학(전문대), 교수진, 캠퍼스, 지역 프로그램 등 다중 계층 구조형을 지원합니다.<br><br>다중 계층 수준을 허용하고 각 수준의 조직 수준 단위를 간편하게 비교하고 특정 수준에 권한을 할당하고 조직 수준별로 목표를 설정하는 등의 작업을 수행할 수 있습니다.|
| **추가 선택적 정보** |없음|**V2.1 파일 형식만**<br><br>*교육 세션* - 세션 기간(학기, 학년도 등)<br><br>인구 통계 및 학생 플래그* - 인종, 성별과 같은 데이터뿐만 아니라 특별 프로그램(IEP, 504)|

> [!NOTE]
> 고객은 2021년 7월 15일부터 파일 형식 v2를 온보딩할 수 없으며 대신 v2.1 형식을 사용해야 합니다. 향후 모든 업그레이드 및 새 기능은 v2.1 형식으로 수행되며 파일 형식 v1과 완전히 호환됩니다.

### <a name="best-practices"></a>모범 사례

계층 구조의 정확한 매핑과 계층 구조 내에서 모든 사람이 속한 위치를 통해 Insights는 다양한 교육 리더 유형에 대해 정확한 데이터와 더 정확하고 관련있는 정보를 제공할 수 있습니다.

더 자세한 정보를 제공할수록 보고서와 스포트라이트가 더 좋아지고 관련성이 더 높아집니다.

#### <a name="file-format-version-to-use-adn-data-to-sync"></a>사용할 파일 형식 버전 및 동기화할 데이터
*   파일 형식 V2.1을 사용하고 [여기](/schooldatasync/sds-for-insights-overview#education-insights-capabilities-matrix-and-sds-v21-csv)에서 설명된 대로 Education Insights에서 사용하는 선택적 데이터를 동기화합니다.

#### <a name="users-and-roles"></a>사용자 및 역할
*   제공하고 동기화 한 파일에 **모든 사용자** 가 나열되어 있는지 확인합니다. 여기에는 자신이 포함된 조직 단위의 데이터를 봐야 하는 모든 학생과 교직원이 포함됩니다.
*   현재 SDS에 교육자만 나열되어 있는 경우 파일을 SDS에 업로드하고 데이터를 동기화하기 전에 모든 다른 사용자를 수동으로 추가합니다. 일부 학생이 누락된 경우 Insights에서 수집한 통계는 등록된 학생들에게서만 온 것이며, 이 경우 데이터와 결론에 오해의 소지가 있습니다.
    
*   플고비저닝에도 SDS를 사용하는 경우, **각 사용자의 성과 이름을 제공해야 합니다**. 그렇지 않으면, 학생이 전자 메일 주소로 참조되므로 최적의 환경이 될 수 없습니다.

*   성적/연도 수준은 이 [매핑 목록](#supported-grade-level-values)을 기반으로 해야 합니다. 

*   **나이/학년 수준을 모든 학생에 대해 추가** 해야 합니다.    

*   **각 사용자를 관련 조직 단위** 에 할당해야 합니다.

    *   학생은 둘 이상의 조직과 연결될 수 있습니다(예: 특수 프로그램 또는 두 개의 학부에 등록된 학생). 학생에게 하나 이상의 조직 구성 단위가 있는 경우 해당 학생에 대한 사용자 파일의 각 줄에 대한 줄을 제공합니다.
    
    *   IT 관리자는 직원의 조직 구성 단위에 따라 권한을 부여할 수 있습니다. **올바른 단위 수준과 연결되어 있는지 확인** 하여 필요한 사용 권한을 받을 수 있도록 합니다. 예를 들어, 4개의 학교에 배정된 상담사는 4개 학교의 모든 성적을 봐야 합니다. 교장은 자신의 학교의 모든 수업을 봐야 합니다. 
    
*   **역할은 중요합니다**. 이 닫힌 목록이지만 [목록](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported)의 역할을 업로드한 각 사용자의 실제 역할과 일치시키세요. 이렇게 하면 그에 따라 역할 기반 권한을 할당할 수 있습니다. 예를 들어 모든 교장이 학교의 수업을 볼 수 있거나 모든 교수가 교직원을 볼 수 있는 권한을 제공합니다. 

#### <a name="organizations"></a>조직

* **조직의 실제 및 완전한 계층 구조가 반영** 되어 있는지 확인합니다. 경우에 따라 이 계층은 SIS에 반영되지 않습니다. 이 경우 CSV 파일 efore 동기화에 수동으로 추가해야 합니다.

* **모든 조직 트리 아래의 모든 조직 단위ㅇ에 학생이나 수업** 이 있는지 확인하세요. 학생은 트리의 최하위 가지에 있는 것이 좋습니다.

> [!NOTE]
> SDS 배포에 대한 자세한 내용은 [SDS 계획](/schooldatasync/planning-school-data-sync)을 참조하세요.

## <a name="integrate-sis-data-using-sds"></a>SDS를 사용하여 SIS 데이터 통합

SDS(학교 데이터 동기화)는 교육용 Office 365와 함께 제공됩니다. SDS는 교육 기관의 SIS(학생 정보 시스템)에서 데이터를 읽고 이를 Teams와 같은 Microsoft 응용 프로그램과 통합하여 온라인 교실과 사용자를 자동으로 만들 수 있도록 합니다.

또한, SIS 데이터를 Insights와 동기화합니다.

IT 관리자는 프로비전 전용, Insights 전용 또는 두 가지 모두에 대해서 SDS를 사용하도록 선택할 수 있습니다.

SIS 정보를 Educations Insights와 동기화하려면 [Insights에 SDS를 배포하는 방법](/schooldatasync/how-to-deploy-sds-for-insights)의 지침을 따릅니다.

### <a name="deploy-sds"></a>SDS 배포
**SDS를 이미 사용하는 경우** [모범 사례](#best-practices)를 따르는 것이 좋습니다. 

**아직 SDS를 사용하지 않는 경우** 지금 [SDS를 배포](/schooldatasync/deploying-school-data-sync)해야 합니다.

배포 프로세스 중에 사용자 및 클래스를 Teams에 프로비전하는 데 SDS를 사용할 것인지 아니면 Insights에 사용자 및 조직 계층을 제공하는 데만 사용할 것인지 결정할 수 있습니다.

> [!NOTE]
> 현재의 한 해의 반이 지났고 이미 수동으로 팀을 만든 경우 SDS를 사용하여 Insights에 사용자 및 조직 계층 데이터를 제공하고 내년에는 Teams에 대한 사용자 및 클래스를 프로비전하는 데 SDS를 사용하는 것을 고려하십시오.

### <a name="verify-the-sync-process"></a>동기화 프로세스 확인
동기화 상태 진행률을 확인하려면 [Insights용 SDS 데이터 상태 및 모니터링](/schooldatasync/sds-for-insights-data-health-and-monitoring)의 지침을 따르세요.

> [!IMPORTANT]
> 문제가 발생하면 [고객 지원](https://aka.ms/edusupport)에서 도움을 드리겠습니다.

## <a name="supported-grade-level-values"></a>지원되는 성적 수준 값

SDS 파일에서 열거된 값으로 정의된 성적/학년 수준인 CSV 파일 내에서 선택된 값 집합만 제공할 수 있습니다. 지정한 값 외의 다른 값은 동기화 처리 중에 오류가 발생합니다.

아래 섹션에서는 사용자 파일의 지원되는 값을 정의합니다.

### <a name="united-states--worldwide-grade-levels"></a>미국/전 세계 성적 수준
|파일 값(성적 열) | Insights의 레이블|
|:---|:---| 
|IT|유아|
|PR|미취학 아동|
|PK|유아|
|TK|유치원 준비 아동|
|KG|유치원생|
|01 또는 1|1학년|
|02 또는 2|2학년|
|03 또는 3|3학년|
|04 또는 4|4학년|
|05 또는 5|5학년|
|06 또는 6|6학년|
|07 또는 7|중학교 1학년|
|08 또는 8|중학교 2학년|
|09 또는 9|중학교 3학년|
|10|고등학교 1학년|
|11|고등학교 2학년|
|12|고등학교 3학년|
|PS|고등학교 졸업 후 교육|
|PS1|고등학교 졸업 후 교육 1학년|
|PS2|고등학교 졸업 후 교육 2학년|
|PS3|고등학교 졸업 후 교육 3학년|
|PS4|고등학교 졸업 후 교육 4학년|
|학부생|학부생|
|졸업|졸업|
|대학원|대학원(연구를 중점으로 공부하는 학부생)|
|동창생|동창생|
|평생 교육|평생 교육|
|UG|성적이 매겨지지 않음|
|기타|기타|

### <a name="united-kingdom-year-groups"></a>영국 연도 그룹
|파일 값(성적 열) | Insights의 레이블|
|:---|:---| 
|IT|보육|
|PR|미취학 아동|
|PK|리셉션|
|01 또는 1|1년|
|02 또는 2|2년|
|03 또는 3|3년|
|04 또는 4|4년|
|05 또는 5|5년|
|06 또는 6|6년|
|07 또는 7|7년|
|08 또는 8|8년|
|09 또는 9|9년|
|10|10년|
|11|11년|
|12|12년|
|13|13년|
|PS|고등학교 졸업 후 교육|
|PS1|고등학교 졸업 후 교육 1년|
|PS2|고등학교 졸업 후 교육 2년|
|PS3|고등학교 졸업 후 교육 3년|
|PS4|고등학교 졸업 후 교육 4년|
|학부생|학부생|
|졸업|졸업|
|대학원|대학원(연구를 중점으로 공부하는 학부생)|
|동창생|동창생|
|평생 교육|평생 교육|
|UG|성적이 매겨지지 않음|
|기타|기타|

