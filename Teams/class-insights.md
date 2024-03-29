---
title: Microsoft Teams의 교육 인사이트에 대한 IT 관리자 가이드
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 교육용 Microsoft Teams의 인사이트를 관리하는 데 도움이 되는 IT 관리자 가이드입니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: f93359c04dba3f926983214d9fa8b856f58915c6
ms.sourcegitcommit: 78fbfcf4a1aafce5d39eea79c9461a9fc1bb3d38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2023
ms.locfileid: "69707820"
---
# <a name="it-admin-guide-to-education-insights-in-microsoft-teams"></a>Microsoft Teams의 교육 인사이트에 대한 IT 관리자 가이드

이 문서에서는 Microsoft Teams의 교육 인사이트를 설정 및 실행하고 교육자 및 교육 리더가 플랫폼을 채택하고 앱을 성공적으로 사용할 수 있도록 도와주는 데 필요한 단계를 제공합니다.

## <a name="overview"></a>개요

**각 학생은 고유의 경험, 기술 및 음성을 가지고 있습니다.**<br/>
**Insights를 통해 학생들을 이해하고 요구에 응답할 수 있습니다.**

Insights는 학급 내 학업 진행 및 활동에 대한 실시간 분석을 제공합니다. 쉽게 시각화하여 학교 커뮤니티가 학생 환경을 적극적이고 손쉽게 추적할 수 있습니다. 교육자 및 교육 리더는 의미 있고 안정적인 데이터를 사용하여 학급 팀과 관련된 정보력있는 의사 결정을 내릴 수 있습니다. 이 데이터를 통해 교육자는 학생들의 감정, 소셜 및 학업 욕구를 충족시켜 주는 데 필요한 정보를 얻습니다.

학교 커뮤니티는 교육자가 학생에게 어떤 전략이 적합한지 알고 있을 때 더 많은 노력을 기울이고 더 큰 영향력을 끼칠 수 있습니다. Insights를 통해 제공되는 시기적절한 데이터를 통해 교육자와 교육 리더는 학습 환경을 개선하고, 학생의 성공을 주도하고, 학생들이 발전하도록 돕기 위한 행동에 시간 및 에너지에 집중합니다.

## <a name="who-uses-insights"></a>누가 Insights를 사용하나요?

### <a name="educators"></a>교육자

교육자는 학급 팀을 소유한 모든 사람입니다. 교육자는 교사, 강사 및 교수를 포함할 수 있습니다.

교육자는 수업 수준에서 Insights에 액세스합니다. 수업에 할당된 학생의 활동을 볼 수 있지만 다른 수업의 데이터에 액세스할 수는 없습니다. Insights를 통해 교육자는 학생을 이해하고 지원할 수 있습니다.

Insights 사용을 위한 사전 요건은 없으며, 교육자는 Insights를 왼쪽 앱 표시줄 또는 Teams에서 각 수업의 탭으로 추가하면 됩니다.

Educators are identified by faculty licenses. Educators must have a faculty license and be a class team owner to see the data in Insights.

### <a name="education-leaders"></a>교육 리더

교육 리더는 학생 참여, 학업 진행, 생활 등을 이해하기 위해 조직적인 시각이 필요한 기관의 모든 역할입니다. 교육자도 본인의 수업 팀을 소유하고 과목 부서의 장과 같이 본인의 수업 이상을 조회할 수 있어야 하는 경우 교육 리더가 될 수 있습니다.

교육 리더에는 최고 교육 책임자, 부서장, 학군 리더, 교장, 교사 부장, 상담 교사, 과목 책임자, 프로그램 디렉터, 사회복지사, 심리학자가 포함될 수 있습니다.

교육 리더는 IT 관리자가 할당한 사용 권한에 따라 조직 전체의 뷰를 갖게 됩니다. 예를 들어 학군 관리자는 액세스하는 모든 학교를 볼 수 있습니다. 이와 달리 학교 교장 또는 감독자는 해당 학교의 성적 수준과 수업만 볼 수 있습니다.

감독자도 강의한다고 가정하면 교육자 및 교육 리더로 간주되며 Insights의 두 가지 보기(교육자 및 교육 리더용)에 모두 액세스할 수 있습니다. 여기, Insights는 교육 리더가 교육자들과 학생들을 지원하도록 돕습니다.
조직 수준에서 IT 관리자는 학생 정보 시스템을 연결하고 관련 학교 또는 부서에 액세스하도록 각 역할에 사용 권한을 부여해야 합니다.

교육 리더는 교직원용 라이선스로 식별되지만, 조직의 Insights 보고서를 보려면 IT 전역 관리자로부터 *명백한 권한* 을 받아야 합니다.

> [!NOTE]
> **학생 관련:**
>
> Insights는 Teams에서 학생 활동에 대한 데이터를 수집합니다.
>
> 학생은 Teams 내의 수업 팀의 구성원입니다. 학생은 라이선스로 식별되며 Insights 앱 또는 탭에 **액세스할 수 없습니다**(팀 소유자인 경우에도).

## <a name="where-do-users-find-insights"></a>사용자가 Insights를 찾을 수 있는 위치

교육자 및 교육 리더는 Insights에 액세스하는 방법이 다릅니다.

### <a name="educators"></a>교육자

교육자는 다음과 같은 두 가지 방법을 사용할 수 있습니다.

- [개인 앱](https://support.microsoft.com/office/747fd8d9-00b0-43e6-bacc-a1bf030b1867) - 수업 데이터의 드릴 다운 기능을 이용하여 Teams 왼쪽 앱 표시줄에서 모든 활성 수업의 개요를 볼 수 있습니다.
- [탭](https://support.microsoft.com/office/1386d1b4-3641-4a23-9b9c-0c6c774c2b6c) - 각 수업 팀의 상단 탐색 메뉴에 있는 탭에서 소유한 지정 수업의 Insights를 사용할 수 있습니다. 이 탭은 교육자로 하여금 Teams 내 해당 수업에서 수업 컨텍스트의 데이터를 보고자 할 경우 관련 데이터에 직접 액세스할 수 있도록 합니다.

Insights는 수업 팀 내 모든 채널의 활동 데이터를 보여주지만, 공개 채널에 한 탭으로만 추가될 수 있습니다. 해당 탭에는 소유자가 아닌 수업 팀의 모든 사람(수업 팀의 소유자가 아닌 교육자 포함)의 활동이 반영됩니다.

In both views, an educator can access class data. Using the personal app, the educator needs to drill down to the class level, whereas the tab provides direct access to class data.

수업 수준에서 교육자가 수업 팀을 소유하는 경우, IT 관리 부분에서 다른 작업을 수행하지 않고도 Insights을 사용할 수 있습니다.

### <a name="education-leaders"></a>교육 리더

교육 리더는 Insights를 Teams 왼쪽 앱 바에 있는 [개인 앱](https://support.microsoft.com/office/8738d1b1-4e1c-49bd-9e8d-b5292474c347)으로 사용할 수 있습니다.

조직 수준에서 IT 관리자는 학생 정보 시스템을 연결하고 관련 학교 또는 부서에 액세스하도록 각 역할에 사용 권한을 부여해야 합니다.

예를 들어 교장은 본인의 학교 수업만 보고, 부서 책임자는 부서의 수업만을 볼 수 있습니다.
학생 데이터는 수업, 부서, 학교 및 학군 수준에서 집계되고, 각 수준의 인사이트(각 사용자의 사용 권한에 따라)가 제공 됩니다. 교육자 및 교육 리더 모두 개별 학생에 대한 데이터를 자세히 확대하여 볼 수 있습니다.

**Teams에서 Insights 앱 추가하기:**

- 앱 바에서 "**...**"을(를) 선택합니다.
- **Insights** 를 검색하고 선택합니다.
- 설명 화면이 열립니다. **추가** 를 선택합니다.

  :::image type="content" source="media/insights-add-personal-app.png" alt-text="Teams에 Insights를 추가합니다.":::

- Insights 아이콘을 마우스 오른쪽 버튼으로 선택하고 **고정** 을 선택합니다.

  :::image type="content" source="media/insights-pin-app.png" alt-text="Insights 앱을 고정합니다.":::

> [!TIP]
> 다음 링크를 통해 Insights 앱을 찾을 수도 있습니다. [https://aka.ms/addInsights](https://aka.ms/addInsights)

## <a name="when-is-insights-used"></a>Insights는 언제 사용하나요?

Insights supports learning communities throughout **the learning cycle**. With real-time metrics across multiple dimensions, Insights supports a continuous cycle of identification, reflection, discussion, and taking action amongst members of the school community.

- 학생들이 어떻게 그리고 언제 교육자, 교육 과정 자료 및 다른 학생들과 참여할 것인지, 그리고 어떻게 과제를 수행할 것인지 **확인합니다**.
- 자료가 학생들의 성공과 성장 분야를 결정하는데 어떤 지원을 할 수 있는지 그리고 어느 부분에서 지원이 필요한지 **숙고합니다**.
- 학생들과 학교 커뮤니티가 관계 강화, 목표 설정, 자체 검토, 공동 작업 추진 및 결과 개선을 위해 조사한 결과들에 대해 **논의합니다**.
- 중재를 개발하고, 성장 영역에 대한 피드백을 제공하고, 교육 전략을 수정하고, 필요한 추가 지원을 식별하기 위해 **조치를 취하세요**.

:::image type="content" source="media/insights-learning-cycle.png" alt-text="Insights는 학습 주기 동안 학습 커뮤니티를 지원합니다.":::

## <a name="how-insights-works"></a>Insights의 방식

Insights는 교육자가 더 나은 학습 결과를 낼 수 있도록 도와주는 강력한 분석을 제공합니다. Teams 내에서 학생 활동을 분석하고 선택적으로 해당 활동을 컨텍스트화하고 그룹화하는 데 도움이 되도록 제공하는 학생 정보 시스템(SIS) 데이터를 사용하여 이를 수행합니다.

기관에 Insights 배포를 시작하기 전에 Insights의 작동 방식, 데이터 윤리에 대한 Microsoft의 약속 및 필요한 라이선스를 간단히 살펴보세요.

### <a name="data-collection"></a>데이터 수집

Teams의 학생 및 교육자 활동으로부터 인사이트를 얻기 위해 데이터가 수집됩니다.

Insights는 교육자에 대한 데이터를 표시하지 *않습니다*. 데이터를 분석하면 교육과 학습에 도움이 되는 실행 가능한 인사이트가 제공됩니다.

현재 수업 팀의 다음과 같은 영역에서 데이터가 수집됩니다.

|팀 구성 요소|수집된 데이터|
|---|---|
|**과제**|과제 열기, 제출, 채점.|
|**채널 참여**|채널 방문, 게시물 작성, 게시물에 응답 및 좋아요 누르기(채팅 콘텐츠 제외).|
|**파일**|파일 업로드, 다운로드, 액세스, 수정, 댓글 달기 및 공유(파일 콘텐츠 제외)|
|**OneNote 수업용 전자 필기장**|전자 필기장에서 페이지 또는 섹션 편집(페이지 콘텐츠 미포함).|
|**모임**|출석(모임 콘텐츠 제외)|
|**[읽기 진행](https://support.microsoft.com/topic/e71705a2-a79a-4d7e-bcef-a1e0aa336017)**|분당 정확도, 가장 까다로운 단어 및 단어 수입니다.|
|**[반영](reflect.md)**|체크 인(값 포함).|
|**커리어 코치**|기술, 기술 흥미, 커리어 흥미, 학습 흥미, 커리어 관련 활동을 포함하는 커리어 코치 앱의 학생 제공 전공(공부 분야) 및 학년, 학생 활동입니다.|

> [!NOTE]
> Most of the collected data shows up in Insights within a few minutes. Attendance in class meetings (meetings associated with one of the class channels) appears a few hours after the end of the meeting, usually up to 24 hours later.

> [!NOTE]
> Data collected in Education Insights is kept until either the IT Admin turns off the [Education Analytics toggle](#turn-sds-for-insights-on-or-off) or the Office subscription for the tenant ends. Turning off specific features in Teams does not delete historic data.

### <a name="privacy-and-security"></a>개인 정보 및 보안

Education Insights는 Microsoft 365의 일부로서 [GDPR](/compliance/regulatory/gdpr) 및 학생의 교육 기록 개인 정보를 보호하는 [FERPA(가족 교육 권한 및 개인 정보 보호법)](/compliance/regulatory/offering-ferpa)를 포함하여 데이터 수집 및 사용에 대한 국가, 지역 및 산업별 규정을 충족합니다.

데이터는 기관에 속하며, Microsoft는 데이터를 오로지 수집하고 저장합니다. Microsoft 직원은 데이터 복구와 같이 서비스를 유지 관리하기 위해 감사 방식으로 규정 준수가 허용하는 경우를 제외하고 데이터에 액세스하거나 데이터를 볼 수 없습니다.

> [!TIP]
>
> - [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에 방문하여 Microsoft에서 어떻게 데이터를 보호하는지 자세히 알아보세요.
> - [Microsoft 규정 준수 서비스](/compliance/regulatory/offering-home)에서 조직이 규정 준수 표준을 충족하는 데 있어 Microsoft 365가 어떻게 도움을 주는지 알아보세요.

### <a name="performance-and-reliability"></a>성능과 안정성

Insights는 Teams에서 수집되는 대량의 데이터를 최적의 성능과 안정성으로 처리하도록 설계되었습니다. 100% 가용성을 보장할 수는 없지만 해당 목표에 최대한 가깝게 사용할 수 있도록 노력합니다.

데이터 수집 프로세스는 Teams의 Insights 탭 설치와는 관계 없이 별도의 서버에서 이루어집니다. Insights 탭 또는 개인 앱은 나머지 Teams 기능을 사용하는 교육자와 학생의 응용 프로그램 성능이나 네트워크 대역폭에 영향을 주지 않습니다.

> [!TIP]
> 자세한 내용은 [EDU용 Teams의 낮은 대역폭 상황을 위한 지원](edu-remote-low-bandwidth.md)을 참조하세요.

### <a name="data-storage"></a>데이터 저장소

현재 Insights는 유럽과 미국에 배포됩니다. 유럽 기반 사용자에 대한 데이터는 유럽 내 서버에 저장됩니다. 오스트레일리아 기반 및 미국 기반 사용자의 데이터는 미국 내 서버에 저장됩니다. 유럽, 오스트레일리아 또는 미국을 제외한 지역의 사용자에 대한 데이터는 당사의 지리적 지역 중 한 곳에 저장됩니다.

### <a name="using-data-ethically"></a>데이터를 윤리적으로 사용하기

Microsoft는 책임감 있고 윤리적으로 데이터를 사용하기 위해 최선을 다하고 있습니다. Insights는 Microsoft의 책임 있는 데이터 및 AI 원칙을 따릅니다. 즉, 데이터 사용 방법에 대해 투명하게 설명하고 교육자와 학생의 관심사를 우선 적용합니다.  당사는 가장 높은 보안 및 개인 정보 표준을 따르며, 지속적인 안정성과 정확도를 모니터링하고 기관의 지속적인 규정 준수를 보장합니다.

Microsoft는 Insights를 만드는 출발점부터 데이터 보호를 보장합니다. Microsoft는 이 데이터를 사용하는 방법에 대한 잠재적 민감도를 알고 있으며, 사용자의 데이터와 개인 정보 보호에 관심이 있습니다.

#### <a name="data-to-support-learning"></a>학습을 지원하는 데이터

Insights는 학생의 학습 및 디지털 참여를 집중 조명합니다. 해당 데이터는 학습을 지원하고 디지털 학습 플랫폼에서 학생 참여 수준을 보여줍니다. 귀하는 수업 활동에 대한 개별 수준으로 드릴다운 할 수 있는 반면, Microsoft는 이런 작업에 **어떤 긍적적 또는 부정적 가치도 부여하지 않습니다**. 데이터 수집의 목적은 학생들과 교육자들이 최상의 성과를 내도록 지원하는 것입니다.

교육자는 학생들을 가장 잘 알고 이해합니다. Insights에서 제공되는 정보는 디지털 학습 시나리오에서 교육자들이 **학생들을 잘 지원하기 위해** 존재합니다. 직접 경험에서 사용할 수 있는 인사이트를 복제합니다. 예를 들어 학생이 특정 기간 동안 활성화되지 않았거나 지난주에 정시에 모든 과제를 완료하지 않았다고 가정합니다. 교육자에게 데이터를 보여주어 학생에게 올바른 행동을 유도하거나 학생을 체크할 수 있도록 합니다. 학생 또는 학생의 가족이나 보호자와 소통하고, 발견한 활동 또는 비활동의 근본적인 이유를 파악하는 것은 교육자의 책임입니다.

Insights는 디지털 학습 환경 프레임워크에서 학생과 교육자 모두를 지원하도록 설계되었습니다. Insights는 **교육자에 대한 데이터를 직접 표시하지 않습니다**. 개별 학생의 데이터 외에도, 특정 교육자에게 학생의 활동과 결과의 종합을 제공하여 교육 리더가 학생들과 교육자들을 지원할 수 있도록 합니다.

### <a name="licensing"></a>라이선싱

Insights에 액세스하려면 사용자에게 Microsoft 365용 A1, A3 또는 A5 교직원 라이선스가 있어야 합니다.

*교육 Insights Premium* 은 교육 리더에게 교육 Insights 데이터의 조직 수준 보기 및 교육자를 위한 기록 데이터 뷰에 대한 확장된 액세스를 제공하는 유료 업그레이드입니다. 자격을 갖춘 교육 기관은 EES(Enrollment for Education Solutions), CSP(Cloud Service Providers) 및 Microsoft 365 관리 센터(웹 직접)를 통해 *교육 Insights Premium* 추가 기능 라이선스를 구입할 수 있습니다.

교육 Insights Premium 추가 기능은 테넌트에서 모든 디지털 활성 학생 라이선스 구매를 기반으로 하는 조직에서 사용할 수 있습니다.

## <a name="student-information-system-sis-integration"></a>SIS(학생 정보 시스템) 가져오기

데이터가 Insights에 더 많이 제공될수록 교육자는 학생을 더 좋은 방법으로 지원할 수 있으며 교육 리더는 교육자를 더 좋은 방법으로 지원할 수 있습니다.

조직 수준의 Insights를 제공하려면 Insights가 교육 시스템의 계층 구조를 올바르게 매핑하도록 [SDS(학교 데이터 동기화)](/SchoolDataSync)를 사용하여 SIS(학생 정보 시스템)에 연결해야 합니다.

Teams의 수업 구조와 권한을 사용하기 때문에 수업 교육자로서 수업 수준 Insights를 볼 필요가 *없습니다*.

자세한 내용은 [**SIS(학생 정보 시스템) 데이터를 Education Insights와 동기화**](education-insights-sis-data-sync.md)를 읽어보세요.

## <a name="manage-permissions"></a>사용 권한 관리

As an IT admin you can provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists. Educators are *automatically* given permission when they own a class team.

자세한 내용은 [**Education Insights에 대한 사용자 액세스 관리**](education-insights-manage-access.md)를 참조하세요

## <a name="manage-the-setup-policy"></a>설정 정책 관리

IT 관리자로서 앱 설정 정책을 사용하여 Teams를 시작할 때 교육자와 리더용 Insights를 기본으로 설치할 수 있습니다. 이 설정 정책을 사용하면 Teams를 사용자 지정하여 Insights를 강조 표시하고 앱 모음에서 해당 항목을 고정할 수 있습니다.

교육자가 각 수업에 직접 액세스하려는 경우 상단 탐색 메뉴에서 Insights 탭을 수동으로 설치할 수 있습니다. 이 탭은 교육자로 하여금 Teams 내 해당 수업에서 수업 컨텍스트의 데이터를 보고자 할 경우 관련 데이터에 직접 액세스할 수 있도록 합니다.

In both views, an educator can access class data. Using the personal app, the educator needs to drill down to the class level, whereas the tab provides direct access to class data.

> [!TIP]
> 자세한 정보는 [Teams 정책 및 교육용 정책 패키지](./policy-packages-edu.md)를 참조하세요.

## <a name="encourage-the-adoption-of-insights"></a>Insights 사용 권장

Insights 사용에 대해 교육 기관에 알리세요.

다음 자료를 **교육자에게** 마음껏 나눠주세요.

- [Insights 지원 페이지](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)를 확인하여 도움을 받으세요.
- 빠른 시작 및 실행 – [Insights 다운로드 요약 문서 PDF](https://aka.ms/insights/start)
- [완벽한 가이드 PDF 파일](https://aka.ms/insights/guide)을 읽어보세요.
- Insights 사용법에 관한 [단계별 자습 영상](https://aka.ms/insights/resources)을 시청합니다.
- Microsoft 교육자 센터에서 [무료 Insights 과정](https://aka.ms/insights/course)을 이수하세요.
- 마지막으로, Insights에 관한 [이 블로그](https://techcommunity.microsoft.com/t5/education-blog/6-ways-to-be-insight-ful-and-support-student-engagement/ba-p/1903091)를 참조하세요.

**교육 리더** 를 위한 자료:

- [교육 조직을 위한 지원 페이지용 Insights](https://support.microsoft.com/office/8738d1b1-4e1c-49bd-9e8d-b5292474c347).

### <a name="turn-on-and-off-insights"></a>Insights 켜고 끄기

기본적으로 Insights는 켜져 있으므로 Teams 내에서 학생의 활동에 대한 분석을 Insights에서 사용할 수 있습니다. Insights를 선택 해제할 수 있습니다. 이 경우 Insights에 대해 *수집된 모든 데이터를 삭제* 하고 향후 데이터 수집을 중지합니다. Insights를 다시 켜면 다시 활성화된 시점부터 데이터 수집을 시작합니다.

*Education Insights* 를 제어할 수 있는 곳은 두 곳입니다. 두 옵션 모두 동일한 결과를 가집니다. *SDS(기본)* 에서 *프로비전용 SDS* 로 전환한 고객의 경우 Teams 클라이언트 옵션만 사용할 수 있습니다.

#### <a name="turn-on-and-off-insights-from-the-sds-admin-center"></a>SDS 관리 센터에서 Insights 켜고 끄기

1. [SDS 관리 센터](https://sds.microsoft.com/)를 엽니다.
1. **설정** > **교육 Insights 관리** 로 이동합니다.
1. **Insights에 대한 활동 데이터 수집** 토글을 켜기 또는 끄기로 조정합니다.

![인사이트를 끄고 켜는 SDS 관리 센터 토글의 스크린샷.](media/manage-insights-toggles.png)

#### <a name="turn-on-and-off-insights-from-the-teams-client"></a>Teams 클라이언트에서 Insights 켜기 및 끄기

1. *교육 Insights* 개인 앱을 고정하지 않은 경우 [이 안내](class-insights.md#education-leaders)에 따라 추가하세요.
1. Microsoft 365 관리자 계정으로 *교육 Insights* 의 오른쪽 상단에 있는 줄임표 아이콘을 사용하여 **관리자 설정** 페이지를 엽니다.
1. **Insights에 대한 활동 데이터 수집** 토글을 켜기 또는 끄기로 조정합니다.

![Insights를 해제하고 켜기 위해 Teams 클라이언트 토글의 스크린샷](media/admin-settings-main-screen.png)

> [!NOTE]
> Insights를 끈 경우 수집된 데이터가 삭제됩니다. 옵트아웃 시 삭제된 데이터는 Insights가 다시 활성화되더라도 나중에 복원할 수 없습니다.

### <a name="turn-on-and-off-advanced-inferences-in-insights"></a>Insights에서 고급 유추 켜기 및 끄기

교육 Insights에 대한 **고급 유추 허용** 토글이 켜져 있으면 Education Insights에서 학생, 교육자 및 교육 리더에게 학습에 대한 고급 유추(예: 참여 경고)를 제시할 수 있습니다. 이러한 유추를 통해 교육자는 학생에게 보다 맞춤화된 지원을 제공할 수 있습니다. 또한 토글은 모델링에 테넌트 데이터를 사용하여 제어합니다.

이 토글을 켜면 교육 Insights에서 이미 수집한 데이터 이외의 추가 데이터는 수집하지 않습니다.

*고급 추론* 을 제어할 수 있는 두 곳이 있습니다. 두 옵션 모두 동일한 결과를 가집니다. *SDS(기본)* 에서 *프로비전용 SDS* 로 전환한 고객의 경우 Teams 클라이언트 옵션만 사용할 수 있습니다.  

#### <a name="turn-on-and-off-advanced-inferences-from-the-sds-admin-center"></a>SDS 관리 센터에서 고급 추론 켜기 및 끄기

1. [SDS 관리 센터](https://sds.microsoft.com/)를 엽니다.
1. **설정** > **교육 Insights 관리** 로 이동합니다.
1. **고급 추론 허용** 토글을 켜기 또는 끄기로 조정합니다.

#### <a name="turn-on-and-off-advanced-inferences-from-the-teams-client"></a>Teams 클라이언트에서 고급 추론 켜기 및 끄기

1. *교육 Insights* 개인 앱을 고정하지 않은 경우 [이 안내](class-insights.md#education-leaders)에 따라 추가하세요.
1. Microsoft 365 관리자 계정으로 *교육 Insights* 의 오른쪽 상단에 있는 줄임표 아이콘을 사용하여 **관리자 설정** 페이지를 엽니다.
1. **고급 추론 허용** 토글을 켜기 또는 끄기로 조정합니다.

> [!NOTE]
> 이 토글은 **Insights를 위한 활동 데이터 수집** 토글에 따라 다릅니다. **Insights를 위한 활동 데이터 수집** 을 끄면 **고급 유추 허용** 토글도 꺼집니다.

### <a name="turn-sds-for-insights-on-or-off"></a>Insights용 SDS 켜기 또는 끄기

SDS(학교 데이터 동기화)는 Teams 내에서 SIS(학생 정보 시스템) 자동으로 데이터를 가져오고 동기화하도록 돕습니다.

Insights를 사용할 때 SDS를 사용할 필요가 *없습니다*. 그러나 언제든지 Insights에서 선택 해제할 수 있습니다.

- 학교 데이터 동기화의 Insights 사용을 끄려면 [Insights용 SDS활성화](/schooldatasync/how-to-deploy-sds-for-insights#disabling-sds-for-insights)의 지침을 따르세요.

- 다시 켜려면 [Insights용 SDS 배포 방법](/schooldatasync/how-to-deploy-sds-for-insights)의 지침을 따르세요.

### <a name="how-to-delete-user-data-from-education-insights"></a>교육 Insights의 사용자 데이터 삭제 방법

Insights는 교육용 Microsoft Teams에서 수행된 학생 및 강사 활동을 저장합니다.

인사이트에서 수집하는 데이터는 다음 두 가지 유형입니다.

- **통합 데이터** – 수업 학습 활동의 일부로 생성되는 데이터입니다.
- **비혼합(비공개) 데이터** – 수업 학습 활동의 일부가 아닌 교육용 Teams의 학생 활동에 의해 수집된 데이터입니다.

인사이트에서 수집하는 전체 데이터 목록은 [여기](class-insights.md#data-collection)에서 확인하세요.

과거 기간에 대한 데이터의 완전성과 무결성을 교육자 및 교육 기관 리더에게 제공하기 위해 기본적으로 Insights는 학생 또는 교육자 사용자 계정이 닫힐 때 서비스에서 데이터를 자동으로 삭제하지 않습니다. 조직의 IT 관리자는 다음 단계를 수행하여 사용자(강사 또는 학생) 데이터를 수동으로 삭제하도록 요청할 수 있습니다.

- [지원 티켓](https://aka.ms/edusupport)을 엽니다. 지원 티켓은 GDPR 삭제 DSR 작업 요청을 명확하게 명시해야 하며 삭제할 개체 ID를 포함해야 합니다.
삭제의 데이터 집합 또는 기간을 제한할 수 없습니다.
- 요청에서 IT 관리자는 다음 옵션을 사용하여 해당 사용자의 어떤 데이터 유형을 삭제하길 원하는지를 분명히 밝혀야 합니다.
  - 모든 데이터(혼합 및 비공개)
  - 모든 비공개 데이터
  - 커리어 코치 데이터만
- 일단 제출되면 지원 티켓은 규정 준수 최소 보존 정책을 위해 일주일 동안 큐에 추가됩니다. 이 기간에는 작업을 취소할 수 있습니다.
- 1주일 후 교육 Insights 팀에서 해당 사용자 ID와 관련된 위에 설명된 특정 유형의 데이터를 모두 서비스에서 삭제합니다. Microsoft 지원에서 티켓을 모니터링하고 28일 이내에 삭제 프로세스가 완료되면 사용자에게 알립니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="why-doesnt-my-institution-see-any-data-in-insights"></a>왜 우리 기관에는 Insight에서 어떤 데이터도 나타나지 않을까요?

*새로운* 테넌트가 있고 데이터가 Insights에서 *한 번도* 나타나지 않는 경우 테넌트가 **교육 테넌트(Insights)로 검증** 되어 Insights에 액세스하는지 확인합니다. Microsoft 계정 관리자에게 문의하여 테넌트가 올바르게 구성되었는지 확인하도록 요청합니다.

계정 관리자가 없는 경우 티켓을 엽니다. [Microsoft 365 관리 센터](https://admin.microsoft.com/AdminPortal/) > **지원** > **새 서비스 요청** 으로 이동합니다.  티켓 제목에 "교육 검증에 도움이 필요합니다"라고 쓰십시오.

또한 Insight에 대한 데이터 수집이 활성화되어 있는지 확인합니다. 기본적으로 켜져 있는 동안 IT 관리자는 이 기능을 해제하여 Insight에서 보유한 모든 데이터를 삭제했을 수 있습니다.

이를 확인하려면 [SDS 관리 센터](https://sds.microsoft.com)를 열고 **설정** > **Education Insights 관리** 로 이동하세요. 'Insights용 활동 데이터 수집' 상태를 확인하십시오.

If it's turned off, turn it back on.  Insights starts to collect data, but it may take up to 24 hours to see it in the reports.

### <a name="why-dont-educators-see-meeting-data"></a>강사가 모임 데이터를 볼 수 없는 이유는 무엇입니까?

Insights 보고서에서 모임 데이터를 보는 데 최대 24시간이 걸립니다. 충분한 시간이 흘렀는지 확인해보세요.

또한 학생들이 [Teams 계정 없이 수업 모임에 참여](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)하지 않았는지 확인합니다. 이러한 시나리오에서는 학생 활동이 수집되지 않습니다.

> [!TIP]
> For those educators who want to track student attendance, you can recommend sending a message during the meeting asking students to reply. This registers their attendance within a few minutes.

> [!NOTE]
> 질문에 여전히 응답하지 않는 경우 [지원 티켓을 여세요](https://aka.ms/edusupport). 문제와 문제가 발생한 날짜를 나타내는 관련 스크린샷을 포함합니다. 문제를 해결하는 데 도움이 될 수 있는 모든 데이터를 추가하세요.

### <a name="what-licenses-do-i-need-to-activate-education-insights-premium"></a>교육 Insights Premium을 활성화하려면 어떤 라이선스가 필요한가요?

조직에 교육 Insights Premium을 사용하도록 설정하려면 테넌트가 조직의 테넌트에서 디지털 활성 학생 수를 기준으로 라이선스를 구매해야 합니다. 즉, 모임, 커뮤니케이션, 채팅, 과제, 파일 편집, 수업용 전자 필기장 또는 Reflect와 같은 활동을 위해 학교 작업의 일부로 Teams 수업을 사용하는 모든 학생을 위한 것입니다.
