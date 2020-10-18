---
title: 팀 관리 센터에서 칭찬 앱 관리
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Microsoft 팀 관리 센터에서 칭찬 앱의 관리 설정에 대 한 자세한 정보
ms.openlocfilehash: 27206f48de9c219996f8dcfd631e6640e175fb18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580454"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터에서 칭찬 앱 관리

> [!NOTE]
> 관리자는이 기능에 액세스할 수 있는 팀 라이선스를 보유 하 고 있어야 합니다. 팀 라이선스 없이이 기능에 액세스 하려고 하면 오류 메시지가 표시 됩니다.

Microsoft 팀의 칭찬 앱은 사용자에 게 조직이 나 강의실 구성원에 게 감사를 표시 하는 데 도움이 됩니다. 선택할 수 있는 배지 설정 및 사용자 지정 옵션을 사용 하 여 칭찬에서 사용자가 수행 하는 다양 한 작업을 교육 하는 데 도움이 되도록 디자인 되었습니다.

관리자는 팀 관리 센터에서 조직에 사용할 수 있는 배지를 제어할 수 있습니다. 왼쪽 탐색 창에서 **팀 앱 > 앱 관리**를 선택 합니다. [테 넌 트 앱 카탈로그](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog)에서 칭찬를 열고 **설정**으로 이동 합니다.

> [!NOTE]
> 미국 정부 클라우드에서는 칭찬 앱 기능을 사용할 수 없습니다.

## <a name="use-built-in-badge-sets"></a>기본 제공 배지 집합 사용

기본 제공 집합은 칭찬 앱에 대해 Microsoft에서 디자인 하는 배지 모음입니다. 이러한 집합은 관리자가 편집할 수 없습니다. 칭찬 앱에서 기본 배지 집합을 이미 사용 하도록 설정 하 고 사용할 수 있습니다. 기본 집합 또는 배지 집합의 사용 가능 여부를 변경 하려면 해당 하는 설정/해제로 전환 합니다. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>기본 배지

기본 배지 집합은 팀 사용자가 동료 들에 게 자신의 작업을 수행 하는 것을 도울 수 있도록 고안 되었습니다.

![기본 배지 집합 미리 보기](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>교육용 소셜 및 감정 학습 배지

강사는 이러한 개념을 설명 하는 배지를 사용 하 여 소셜 및 감정 learning (SEL) 성과 및 동작에 대 한 개별 학생을 인식할 수 있습니다.

![교육용 소셜 및 감정 learning 배지 미리 보기](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>나만의 배지 만들기

**사용자 지정 배지** 전환 설정 및 **사용자 지정 배지 만들기**를 선택 합니다. 여기서는 측면 패널에서 사용자 지정 배지를 디자인할 수 있습니다. 최대 25 명의 사용자 지정 배지를 만들 수 있습니다. 

1. 배지 이름을 입력 합니다. 사용자가 칭찬를 보낼 때 배지에 표시 되는 이름입니다.

2. 배지 색을 설정 합니다. 배지의 텍스트 및 배경색을 설정 하려면 16 진수 값으로 색을 입력 해야 합니다.

   > [!TIP]
   > 16 진수 값을 처음 사용 하는 경우이 문서에는 사용법을 보여 주는 [간략](#hex-colors-intro) 한 설명이 포함 되어 있습니다.

3. 배지 이미지를 업로드 합니다. 허용 되는 파일 형식은. N. 이미지 파일은 최대 크기의 216 X 216 픽셀을 사용 하는 40 미만 이어야 합니다.
![배경, 텍스트, 이미지 필드가 표시 된 배지](media/praise-app-badge-fields.png)

4. 배지 이름 지역화: 현지화 된 **배지 이름**아래에서 **추가**를 선택 합니다. 드롭다운 목록에서 원하는 로케일을 선택 합니다. 그런 다음 지정 된 언어로 배지 이름을 입력 합니다.

5. 특정 로캘에서 배지 제외: **다음 로캘의 제외 배지**에서 **추가**를 선택 합니다. 드롭다운 목록에서 제외 하려는 로케일을 선택 합니다.

6. **적용**을 선택 합니다. 이제 사용자 지정 배지 표에 새 배지가 표시 됩니다.

> [!NOTE]
> 4 ~ 5 단계를 건너뛰면 모든 로캘의 기본 언어가 배지에 나타납니다.
>
> 배지 선택 변경 작업을 마쳤으면 **제출을**선택 합니다. 조직에서 이러한 변경을 사용할 수 있으려면 몇 시간이 걸릴 수 있습니다.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>16 진수 값이 있는 색 지정

16 진수 색 값은 00 ~ FF의 특정 색으로 빨강 (RR), 녹색 (GG) 및 파랑 (BB)의 농도를 나타내는 6 개의 16 진수 문자열입니다. 세 가지 색의 값을 모두 함께 입력할 경우 다음과 같이 16 진수 값이 표시 됩니다. #RRGGBB

예를 들어 빨강으로 가장 높은 값, FF, 녹색으로 설정 되 고 파랑은 각각 값이 최소값 00으로 설정 되므로 빨간색의 16 진수 값은 #FF0000 됩니다.

다른 색과 해당 16 진수 값을 탐색 하려면 [Bing 색 선택기](https://www.bing.com/search?q=color+picker)를 확인 합니다.

다음은 시작 하는 데 도움이 되는 예제 색 목록입니다.

|색  |16 진수 값|
|-------|---------|
|![16 진수 색 #FF6666](media/hexColor1.png)|  #FF6666   |
|![16 진수 색 #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![16 진수 색 #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![16 진수 색 #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![16 진수 색 #800080](media/hexColor5.png)|  #800080   |
|![16 진수 색 #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>사용자 지정 배지를 만들기 위한 모범 사례

**모든 배지를 한 번에 제출 합니다.** 새 배지를 처리 하는 데 다소 시간이 걸리기 때문에 사용자 지정 배지를 제출 하기 전에 표에 추가 하는 것이 가장 좋습니다.

**색을 선택할 때 접근성을 염두에 두어야 합니다.** 일부 색이 다른 색상 보다 더 잘 작용 합니다.  텍스트와 배경색 간의 대비를 만들어 배지 이름을 쉽게 읽을 수 있도록 합니다. 예를 들어 어두운 배경색을 선택한 경우 밝은 텍스트 색을 선택 합니다.

**이미지를 선택 하는 경우 배지 크기를 염두에 두십시오.** 최상의 품질을 위해서는 216 x 216 픽셀 (최대 크기) 인 이미지 파일을 업로드 하는 것이 좋습니다. 이러한 치수에 맞게 이미지를 늘이거나 왜곡할 필요가 없습니다.

**배지 이미지가 직사각형이 아닌 경우 이미지를 투명 하 게 만듭니다.** 이미지 파일을 칭찬에 업로드 하기 전에이 작업을 수행 해야 합니다.

![왼쪽: 투명 하지 않은 이미지가 있는 배지, 오른쪽: 투명 한 이미지가 있는 배지](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>배지 설정 자산

기본 제공 배지 집합은 수정할 수 없으므로 기본 제공 집합을 사용 하도록 설정한 경우 집합의 모든 배지를 칭찬 앱에 추가 합니다. 기본 제공 집합에서 특정 배지를 추가 하 고 다른 항목을 종료 하려면 사용자 지정 배지로 사용할 배지를 다시 만듭니다. 배지 이미지를 다운로드 하 고 아래 표에 있는 기본 제공 집합에서 배지의 텍스트 및 배경색을 찾을 수 있습니다.

### <a name="default-badges-assets"></a>기본 배지 자산

</br>

|배지 이름     |이미지 파일  |텍스트 색 | 배경 색 |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|굉장한        |[멋진 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Coach          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Courage        |[Courage PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|창의적인       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|하한값      |[포함 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|종류 하트     |[종류 하트 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|통     |[리더십 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Optimism       |[Optimism PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|문제 해 찾기 |[문제 해 찾기 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|팀 플레이어    |[팀 플레이어 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|감사합니다      |[감사 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>교육 자산에 대 한 소셜 및 감정 학습 배지

</br>

|배지 이름        |이미지 파일  |텍스트 색 | 배경 색 |
|------------------|------------|---------- |--------|
|통신과     |[통신 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|중요 한 생각 |[중요 한 생각 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Curiosity         |[Curiosity PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empathy           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|목표 달성      |[목표를 달성 하는 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|부여        |[동기 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|기반의       |[지 속성 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|기준           |[PNG 관련](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|책임져야    |[업무 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|자체 인식    |[자체 인식 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|자체 관리   |[자체 관리 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Thoughtfulness    |[Thoughtfulness PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
