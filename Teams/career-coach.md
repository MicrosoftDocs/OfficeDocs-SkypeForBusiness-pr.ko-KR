---
title: 구매, 구성 및 커리어 코치 사용 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 구매, 구성 및 커리어 코치 방법을 Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e45732261d7ad9f1298d2aa865f84619bb7bbcd
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646939"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>구매, 구성 및 커리어 코치 사용 Microsoft Teams

커리어 코치 고등 교육 교육용 Microsoft Teams 탐색할 수 있는 개인 설정된 지침을 제공하는 LinkedIn에서 제공하는 다양한 앱입니다. 커리어 코치 교육 기관은 학생들이 자신의 진로를 검색하고, 실제 기술을 성장하고, 네트워크를 한 장소에서 구축할 수 있는 통합된 경력 솔루션을 제공합니다.

## <a name="supported-languages"></a>지원되는 언어

커리어 코치 언어는 다음 언어로 지역화됩니다.

- 중국어(중국 본토 간체)
- 중국어(중국어, 대만)
- 영어(미국)
- 영어(영국)
- 프랑스어(캐나다)
- 프랑스어(프랑스)
- 독일어(독일어)
- 일본어(일본)
- 포르투갈어(브라질)
- 스페인어(스페인)
- 스페인어(멕시코)

에 [대해 커리어 코치.](https://aka.ms/career-coach)

> [!NOTE]
> 이 가이드의 모범 사례 및 유용한 팁을 사용하여 학생, 교직원 및 커리어 코치 기능을 사용할 수 있습니다. 빠른 계획 [가이드 문서를 참조하세요.](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4)

## <a name="review-the-requirements"></a>요구 사항 검토

교육 기관에 커리어 코치 활성화하려면 앱을 설치하고 실행하는 데 필요한 기능을 검토합니다.

**기술 요구 사항**

- Office 365 있는 Azure Active Directory

- Microsoft Teams

- Azure Active Directory

**라이선스**

- 교직원

- 학생

> [!NOTE]
> 커리어 코치 구성을 완료하는 IT 관리자에게 교직원 라이선스를 할당해야 합니다.

**교육 기관의 데이터 및 파일**

- 과정 카탈로그 데이터

- 제공되는 연구 분야

- 교육 기관의 LinkedIn 페이지

- LinkedIn Learning 캠퍼스 구독(기본 설정)

## <a name="purchase-the-career-coach-licenses"></a>라이선스 커리어 코치 구입

커리어 코치 EES(등록용 EES), CSP(클라우드 서비스 공급자) 및 웹 직접(웹 직접)을 통해 자격을 갖춘 고등 교육 기관에 대한 추가 Microsoft 365 관리 센터 사용할 수 있습니다. 추가 Microsoft Teams 라이선스를 구입하려면 Microsoft 365 A3/A5 또는 Office 365 A1/A3/A5가 커리어 코치 있어야 합니다.

### <a name="assign-app-licenses-to-users"></a>사용자에게 앱 라이선스 할당

단계별 지침은 사용자에게 라이선스 [할당을 참조하세요.](/microsoft-365/admin/manage/assign-licenses-to-users)

### <a name="turn-on-linkedin-account-connections"></a>LinkedIn 계정 연결 설정

커리어 코치 교육  기관의 사용자가 해당 Microsoft 365 내에서 쉽게 사용할 수 있는 LinkedIn 계정에 연결할 수 커리어 코치

1. [Azure AD](https://aad.portal.azure.com/) 조직의 전역 관리자 계정으로 Azure AD 관리 센터에 로그인합니다.

2. 사용자를 **선택합니다.**

3. 사용자 **페이지에서** 사용자 **설정을 선택합니다.**

4. **LinkedIn 계정 연결에서** 사용자가 자신의 계정을 연결하여 일부 Microsoft 앱 내에서 LinkedIn 연결에 액세스할 수 있습니다. 사용자가 자신의 계정을 연결하는 데 동의할 때까지는 데이터가 공유됩니다.

   - **예를** 선택하여 교육 기관의 모든 사용자에 대해 서비스를 사용하도록 설정

   - 선택한 **그룹을** 선택하여 교육 기관에서 선택한 사용자 그룹에만 서비스를 사용하도록 설정

   - **아니요를** 선택하여 교육 기관의 모든 사용자의 동의를 철회합니다.

LinkedIn 계정 연결을 통합하는 [방법을 Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="configure-career-coach-in-the-teams-admin-center"></a>커리어 코치 관리 센터에서 Teams 구성

관리 센터의 관리자 Microsoft Teams 사용하여 교육 기관에 대한 커리어 코치 구성하고 사용자를 사용하도록 설정할 수 있습니다.

**고려해야 할 일**

- 브랜드 및 기본 설정, LinkedIn을 커리어 코치 전에 다음 섹션을 완료해야 합니다.
- 코스 카탈로그 및 학습 분야용 CSV에는 필수 형식과 최대 18MB의 크기가 있습니다.

- 앱에 "현재 커리어 코치 설정 중"이 표시되어 있는 경우 커리어 코치 섹션이 완료되지 않은 것입니다.

- 필수 필드가 있는 설정 페이지에서 필드가 완료되지 않은 경우 페이지가 제출되지 않습니다.
  - 사용자에게 경고 메시지가 표시되지 않습니다. 페이지는 단순히 제출하지 않습니다.

## <a name="access-the-career-coach-app-settings"></a>앱 커리어 코치 액세스

앱 [관리](/microsoftteams/manage-apps) 페이지를 사용하여 Teams 앱 카탈로그에서 앱을 볼 수 있습니다.

1. 관리 **센터에 Teams 로그인합니다.**

2. 왼쪽 탐색에서 앱 **관리 Teams**  >  **선택합니다.**  

    > [!NOTE]
    > 페이지에 액세스하려면 전역 관리자 또는 Teams 관리자 되어야 합니다.

3. 를 검색하거나 **커리어 코치.**  

4. 을 **커리어 코치** 를 선택한 다음, **설정.**  

    ![커리어 코치 옵션을 사용하여 선택한 설정 표시됩니다.](media/career-coach-app.png)

### <a name="configure-the-career-coach-app-settings"></a>앱 커리어 코치 구성

커리어 코치 5가지 구성 범주가 있습니다.

- [브랜드 및 기본 설정](#brand-and-preferences)

- [LinkedIn 연결](#linkedin-connection)

- [과정 카탈로그](#course-catalog)

- [연구 분야](#fields-of-study)

- [사용자 지정](#customization)

> [!NOTE]
> 학생, 교직원 및 교직원을 위해 앱을  효과적으로 사용하도록 설정하려면 브랜드 및 기본 설정, LinkedIn 구성, 과정 카탈로그 및 학습 필드가 필요합니다.

#### <a name="brand-and-preferences"></a>브랜드 및 기본 설정

브랜드 및 기본 설정 설정 페이지에서 교육 기관의 이름, 로고 및 기본 언어를 설정합니다.

> [!NOTE]
> 이 섹션은 필수 섹션입니다. 커리어 코치 기본 설정이 제출되지 않으면 사용할 수 없습니다.

![관리 커리어 코치 브랜디드 섹션](media/career-coach-brand.png)

##### <a name="educational-institution-icon"></a>교육 기관 아이콘

교육 기관 아이콘은 커리어 코치 교육 기관 고유의 콘텐츠를 식별하고, 앱 전체의 코스 카탈로그 리소스 및 대시보드의 실제 환경 섹션에서 식별하는 데 사용됩니다. 아이콘은 다음으로 서식이 가장 잘 지정됩니다.

- 투명한 PNG
- 1:1의 화면 비율
- 최대 크기는 64 px x 64 px입니다.

##### <a name="educational-institution-thumbnail"></a>교육 기관 축소판 그림

교육 기관 아이콘은 특정 이미지를 코스에 사용할 수 없는 경우 앱 전체의 코스 카탈로그 리소스에 사용됩니다. 아이콘은 다음으로 서식이 가장 잘 지정됩니다.

- A PNG
- 16:9의 화면 비율
- 최대 크기는 360 px x 200 px입니다.

#### <a name="linkedin-connection"></a>LinkedIn 연결

LinkedIn 구성은 LinkedIn의 공용 커리어 코치 데이터와 연결합니다.

> [!NOTE]
> 이 섹션은 필수 섹션입니다. 커리어 코치 연결 확인 없이는 사용할 수 없습니다.

##### <a name="add-and-confirm-the-linkedin-page"></a>LinkedIn 페이지 추가 및 확인

교육 기관의 LinkedIn 페이지를 선택합니다. LinkedIn에서 검색하거나 경력 서비스 직원과 연결하여 사용할 올바른 페이지를 확인하여 LinkedIn 페이지를 찾을 수 있습니다.  
  
1. 관리 **센터에 Teams 로그인합니다.**

1. 연결된 **Teams** 앱 관리  >    >  **커리어 코치**  >  **앱을 선택합니다.**

2. LinkedIn에서 검색하고 학교 필터를 선택하여 LinkedIn 페이지를 찾을 수 있습니다. 또는 커리어 서비스 교직원과 연결하여 사용할 올바른 LinkedIn 학교 페이지를 확인합니다. [LinkedIn 페이지를 식별하는 방법](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)

    ![학교에 대한 linkedin 검색](media/career-coach-school-search.png)

3. LinkedIn 학교 페이지 URL을 추가합니다. URL은 회사 페이지가 아닌 학교 페이지 되어야 합니다. 일반적으로 으로 서식이 `https://www.linkedin.com/school/willow-university/` 지정됩니다.

   ![linkedin 학교 페이지 예제](media/career-coach-linkedin-page-url.png)

4. 제출을 **선택합니다.**

5. 성공적으로 제출하면 페이지가 업데이트되어 확인 링크  및 확인 **링크 만료가 표시됩니다.** 확인 링크는 30일 후에 만료됩니다.

   ![경력 코치 앱에 대한 linkedin 연결](media/career-coach-linked-in.png)  

6. 확인 링크를 복사하여 교육 기관의 LinkedIn 페이지 슈퍼 관리자와 공유합니다. LinkedIn 페이지 관리자 설명서에서 LinkedIn 페이지 슈퍼 관리자 역할에 대해 [자세히 알아보십시오.](https://www.linkedin.com/help/linkedin/answer/102672)

7. LinkedIn 페이지 슈퍼 관리자는 고유한 확인 링크를 사용하여 학교의 커리어 코치 연결합니다. [LinkedIn 페이지](https://www.linkedin.com/help/linkedin/answer/102672)확인에 대한 추가 설명서.

> [!NOTE]
> LinkedIn 페이지 슈퍼 관리자에 의해 확인을 완료하려면 링크드인 연결을 완료해야 커리어 코치.

   ![linkedin 개발자 포털에서 linkedin 페이지 확인](media/career-coach-linkedin-verification.png)

#### <a name="course-catalog"></a>과정 카탈로그

코스 카탈로그는 교육 기관에서 학생들에게 제공하는 과정 및 수업을 나타내고 있습니다.

> [!NOTE]
> 이 섹션은 필수 섹션입니다. 커리어 코치 카탈로그 없이는 사용할 수 없습니다.

이러한 과정은 다음 두 영역에서 앱 내에서 사용됩니다.

- 교육 과정은 학습 리소스의 일부로 반환됩니다.  

- 설명과 같은 코스 및 코스 메타 데이터는 학생들이 성적 증명서를 업로드할 때 자신의 기술을 식별하는 데 사용됩니다.  

과정 카탈로그를 만들하려면 교육 기관에서 학습한 모든 과정 목록을 함께 작성하고 CSV 파일로 업로드합니다. 앱은 코스 카탈로그에서 학생의 기술을 자신의 성적표에서 식별하고 수강할 강좌를 제안합니다.

##### <a name="course-catalog-documents-formatting-and-schema"></a>코스 카탈로그 문서 서식 및 스위마

문서는 최대 크기가 18MB인 CSV 형식으로 작성해야 합니다. 문서에는 필수 필드 코스 **제목,** 코스 **ID** 및 **과정 URL이 포함되어 있어야 합니다.** 권장 필드를 포함하면 더 나은 검색 결과 및 기술 식별을 반환하여 학생들의 환경을 개선할 수 있습니다.

> [!NOTE]
> 시작을 [위해 샘플]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) 과정 카탈로그 문서로 시작합니다.

다음 표에서는 코스 카탈로그에 포함할 항목을 보여 주었다.

| 이름             | 상태      | 유형   | 설명                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | 필수    | string | 일반적으로 코스 ID(일반적으로 성적 스크립트에서 생성된 것)에 매핑됩니다. |
| 타이틀            | 필수    | string | 일반적으로 코스 제목입니다.                                                      |
| sourceLink       | 필수    | URL    | 코스 페이지에 대한 웹 사이트 링크입니다.                                               |
| 설명      | 권장 | string | 과정에 대한 소개 텍스트입니다.                                              |
| language         | 권장 | string | 과정의 언어입니다. 표준 언어 코드를 사용 합니다.                           |
| 형식           | 권장 | string | 교육 모드(온라인, 비디오, 개인)입니다.                              |
| 축소판 그림링크    | 권장 | URL    | 과정 이미지에 대한 축소판 그림 링크입니다.                                            |
| 축소판 그림AltText | 권장 | string | 이미지에 대한 접근성 alt 텍스트                                           |
| educationLevel   | 권장 | string | 학습 수준, 예. 학부/졸업생.                                       |
| 토픽           | 권장 | string | 강의가 가르치는 기술과 관련된 토픽 또는 태그입니다.          |

##### <a name="add-the-course-catalog"></a>과정 카탈로그 추가

1. 관리 **센터에 Teams 로그인합니다.**

1. 앱 **Teams 앱** 관리 커리어 코치 설정 &gt;  &gt;  &gt;  &gt; **선택합니다.**  

2. 업로드, 제목, sourceLink와 같은 필수 열이 있는 CSV 형식의 과정입니다. 각 행에는 필요한 각 열에 대한 데이터가 포함되어야 합니다.

권장 필드를 포함하면 더 나은 검색 결과 및 기술 식별을 반환하여 학생들의 환경을 개선할 수 있습니다.

4. 제출을 **선택합니다.**

   ![경력 코치 앱의 과정 카탈로그 섹션](media/course-catalog.png)

#### <a name="fields-of-study"></a>연구 분야

연구 분야는 주요 관심 분야, 학업 전공 및 학위와 동의어입니다. 이러한 타이틀은 앱을 사용하여 개인 설정된 프로필을 설정하기 시작할 때 학생들이 참조합니다.

> [!NOTE]
> 이 섹션은 필수 섹션입니다. 커리어 코치 목록 없이는 사용할 수 없습니다.

공학, 영어, 비즈니스 등 학생들에게 사용할 수 있는 모든 학습 필드를 추가합니다. 필드 목록을 통해 학생들이 관심 있는 학습 영역을 검색하고 자신의 프로필에 포커스 영역을 추가할 수 있습니다.

> [!NOTE]
> 스터디 [문서의 샘플 필드로 시작합니다.](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy)

다음 표에서는 연구 필드에 포함할 항목을 보여 주었다.

| 이름          | 상태   | 유형   | 설명                    |
|---------------|----------|--------|--------------------------------|
| fieldsOfStudy | 필수 | string | 연구 필드의 이름 |

##### <a name="add-the-fields-of-study"></a>연구 필드 추가

1. 관리 **센터에 Teams 로그인합니다.**
1. Teams **앱 관리** 앱을 커리어 코치 설정 &gt;  &gt;  &gt;  &gt; **필드를 선택합니다.**  

2. 업로드 형식의 학습 필드입니다.

3. 제출을 **선택합니다.**

#### <a name="customization"></a>사용자 지정

커리어 코치 교육 기관 고유하도록 사용자 지정할 수 있습니다. 사용자 지정은 대시보드에 환경 추가를 지원합니다. 학생이 실제 경험을 쌓는 데 도움이 되는 작업 보드, 이벤트, 경력 서비스 사무실, 경력 관련 이벤트, 학생 클럽 및 기타 리소스에 대한 링크를 추가하는 것이 좋습니다.

##### <a name="add-customized-experiences"></a>사용자 지정 환경 추가

1. 관리 **센터에 Teams 로그인합니다.**

1. 사용자 **Teams 앱** 관리 커리어 코치 설정 &gt;  &gt;   >   &gt; **선택합니다.**

2. 각 URL, 제목 및 간략한 설명을 추가합니다.  
  
3. 제출을 **선택합니다.**

## <a name="making-career-coach-available-to-your-organization"></a>조직에서 커리어 코치 사용할 수 있도록 설정

이제 커리어 코치 구성했습니다. 다음 단계를 수행하여 커리어 코치 조직에서 사용할 수 Microsoft Teams.

### <a name="enable-the-app"></a>앱 사용

구성을 완료한 후 학생 및 라이선스가 부여된 사용자에 대해 앱을 사용하도록 설정하여 사용자가 사용자에 대한 액세스 권한을 커리어 코치.  
  
> [!NOTE]
> 전역 또는 관리자 Teams 권한이 있어야 합니다.

1. 관리 **센터에 Teams 로그인합니다.**

1. 앱 **Teams 관리** &gt; **앱을** &gt; **커리어 코치.**

2. 상태 토글을 허용 **으로 이동합니다.**  

  > [!NOTE]
  > 허용되는 것은 교육 기관의 사용자가 앱을 사용할 수 있습니다. 차단된 것은 학생이 앱을 사용할 수 없습니다.

### <a name="add-career-coach-as-an-installed-app"></a>설치된 커리어 코치 앱으로 추가

> [!NOTE]
> 이 단계에서는 1) 커리어 코치 조직에 대해 올바르게 구성되었는지 확인 2) 학생이 커리어 코치.

1. 관리 **센터에 Teams 로그인합니다.**

2. 앱 **Teams 정책** 설정 &gt; **정책을** &gt; *선택합니다.*

3. 설치된 앱 아래에서 앱 추가를 선택합니다.

4. 설치된 앱 추가 창에서 사용자가 앱을 시작할 때 자동으로 설치하려는 앱을 Teams. 앱 사용 권한 정책에 따라 앱을 필터링할 수 있습니다. 앱 목록을 선택한 경우 추가를 선택합니다.

### <a name="pin-the-app"></a>앱 고정

커리어 코치 고정하면 학생들이 앱을 더 쉽게 접근하고 볼 수 있습니다.

1. 관리 **센터에 Teams 로그인합니다.**

2. 앱 **Teams 정책** 설정 &gt; **정책을** &gt; *선택합니다.*

3. 고정된 **앱 아래에서** 앱 **추가를 선택하세요.**

4. 를 **커리어 코치** 을 검색한 다음 **추가를 선택합니다.**

5. 앱이 나타날 순서를 선택하고 저장을 **선택합니다.**

> [!NOTE]
> 학생은 고정된 Microsoft Teams 커리어 코치 알림을 하게 될 것입니다.

자세한 [내용은 Microsoft의](/microsoftteams/teams-app-setup-policies) 앱 설정 정책 관리에 대한 참조입니다.

## <a name="resources"></a>리소스

다음 리소스는 앱을 계획하는 데 커리어 코치 있습니다.

- [Microsoft Teams에 오신 것을 환영합니다.](Teams-overview.md)

- [Teams를 배포하는 방법](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Microsoft Teams의 Teams 및 채널 개요](teams-channels-overview.md)

- [관리 센터에서 앱 Microsoft Teams 관리](manage-apps.md)

- [온라인 가상 방향 키트](https://www.microsoft.com/education/remote-learning/virtual-orientation)

- [채널의 제한 및 Teams 사양](limits-specifications-teams.md)

- [관리자 교육을 시작하기 Microsoft Teams](ITAdmin-readiness.md)

- [Teams 문제 해결](/microsoftteams/troubleshoot/teams-welcome)

- [Microsoft Teams에서 앱 사용 권한 정책 관리](teams-app-permission-policies.md)
