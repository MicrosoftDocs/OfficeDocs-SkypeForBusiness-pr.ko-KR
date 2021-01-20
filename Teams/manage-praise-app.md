---
title: Teams 관리 센터에서 칭찬 앱 관리
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Microsoft Teams 관리 센터의 칭찬 앱의 관리자 설정에 대해 자세히 알아보기
ms.openlocfilehash: 122e7f0ffad914e62ede56ebd1811d1504f3fcd7
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909192"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터에서 칭찬 앱 관리

> [!NOTE]
> 관리자는 이 기능에 액세스하려면 Teams 라이선스가 있어야 합니다. Teams 라이선스 없이 이 기능에 액세스하려고 시도하면 오류 메시지가 표시됩니다.

Microsoft Teams의 칭찬 앱은 사용자가 조직 또는 교실 구성원에게 감사를 표시하는 데 도움이 됩니다. 선택할 수 있는 배지 집합과 나만의 배지를 만들 수 있는 옵션을 사용하여 칭찬은 Teams 사용자가 강사부터 일선 작업자까지 다양한 작업 범위로 들어가는 노력을 인식할 수 있도록 디자인됩니다. 자세한 내용은 다른 사용자에 대한 [칭찬 보내기를 체크 아웃합니다.](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

관리자는 Microsoft Teams 관리 센터에서 조직에서 사용할 수 있는 배지를 제어할 수 있습니다. 왼쪽 탐색 모음에서 Teams 앱으로 이동하여 **> 관리합니다.** 앱 목록에서 칭찬을 클릭한 다음 설정을 **선택합니다.**   여기에서 기본 및 기본 제공 배지 집합을 사용하도록 설정하고 사용자 지정 배지를 만들 수 있습니다.

![칭찬 앱의 설정 탭 스크린샷](media/manage-praise-app-settings.png)

> [!NOTE]
> 칭찬 앱 기능은 미국 정부 클라우드에서 사용할 수 없습니다.

## <a name="use-built-in-badge-sets"></a>기본 제공 배지 집합 사용

기본 제공 집합은 칭찬 앱을 위해 Microsoft에서 디자인한 배지 모음입니다. 이러한 집합은 관리자가 편집할 수 없습니다. 기본 배지 집합은 이미 사용하도록 설정되어 있으며 칭찬 앱에서 사용할 수 있습니다. 기본 집합 또는 배지 집합의 가용성을 변경하기 위해 해당 토글을 켜기 또는 끄기로 전환합니다. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>기본 배지

기본 배지 집합은 Teams 사용자가 동료가 업무를 진행하는 동안 동료를 인식할 수 있도록 디자인되어 있습니다.

![기본 배지 집합 미리 보기](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>교육용 소셜 및 정서적 학습 배지

강사는 이러한 개념을 설명하는 배지를 사용하여 개별 학생에게 SEL(소셜 및 감정 학습) 도전 과제 및 동작을 인식할 수 있습니다.

![교육용 소셜 및 감정 학습 배지 미리 보기](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>나만의 배지 만들기

사용자 **지정 배지 만들기를 선택합니다.** 여기에서 사이드 패널에서 사용자 지정 배지를 디자인할 수 있습니다. 최대 25개 사용자 지정 배지를 만들 수 있습니다. 

![사용자 지정 배지 만들기 창의 스크린샷](media/manage-praise-app-create-custom-badge.png)

1. 배지 이름을 입력합니다. 사용자가 칭찬을 보낼 때 배지에 나타나는 이름입니다.

2. 배지 색을 설정합니다. 배지의 텍스트 및 배경색을 설정하려면 색을 16진수(16진수) 값으로 입력해야 합니다.

   > [!TIP]
   > 16진수 값을 사용하는 방법을 소개하는 [](#hex-colors-intro) 빠른 소개가 포함되어 있습니다.

3. 배지 이미지를 업로드합니다. 허용되는 파일 형식은 . PNG. 이미지 파일은 최대 크기가 216 X 216픽셀인 40 KB보다 작아야 합니다.
![배경, 텍스트 및 이미지 필드에 레이블이 지정되어 있는 배지](media/praise-app-badge-fields.png)

4. 배지 이름 지역화: 지역화된 배지 **이름 아래에서** 추가를 **선택합니다.** 드롭다운 목록에서 원하는 로일을 선택합니다. 그런 다음 지정된 언어로 배지 이름을 입력합니다.

5. 특정 로지에서 배지 제외: **이러한** 로지에서 배지 제외 아래에서 추가를 **선택합니다.** 드롭다운 목록에서 제외할 로일을 선택합니다.

6. 적용을 **선택합니다.** 이제 새 배지가 사용자 지정 배지 테이블에 표시됩니다.

> [!NOTE]
> 4단계와 5단계를 건너뛴 경우 배지는 모든 로지의 기본 언어가 됩니다.
>
> 배지 선택을 변경한 후 제출을 선택해야 **합니다.** 조직에서 이러한 변경 내용을 사용할 수 있는 데 최대 몇 시간이 걸릴 수 있습니다.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>16진수 값을 사용하여 색 지정

16진수 색 값은 666진수의 문자열로, 00에서 FF까지의 특정 색으로 RR(RR), 녹색(GG) 및 파란색(BB)의 강도를 나타냅니다. 세 가지 색의 값을 모두 합치면 16진수 값이 #RRGGBB

예를 들어 빨간색의 16진수 값은 #FF0000 가장 높은 값, FF 및 녹색 및 파란색으로 설정되어 있기 때문에 빨간색의 16진수 값은 각각 가장 낮은 값인 00으로 설정됩니다.

다양한 색과 해당 16진수 값을 탐색하기 위해 [Bing 색 선택을 체크 아웃합니다.](https://www.bing.com/search?q=color+picker)

다음은 시작하는 데 필요한 예제 색 목록입니다.

|색  |16진수 값|
|-------|---------|
|![16진수 #FF6666](media/hexColor1.png)|  #FF6666   |
|![16진수 #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![16진수 #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![16진수 #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![16진수 #800080](media/hexColor5.png)|  #800080   |
|![16진수 #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>사용자 지정 배지를 만들기 위한 모범 사례

**모든 배지를 한에 제출합니다.** 새 배지를 처리하는 데 시간이 걸리기 때문에 모든 사용자 지정 배지를 표에 추가한 후 제출하는 것이 가장 좋은 것입니다.

**색을 선택할 때 접근성에 유의해야 합니다.** 일부 색은 다른 색보다 잘 어우러질 수 있습니다.  배지 이름을 쉽게 읽을 수 있도록 텍스트와 배경색 사이에 대비를 만들 수 있습니다. 예를 들어 어두운 배경색을 선택한 경우 밝은 텍스트 색을 선택해야 합니다.

**이미지를 선택할 때 배지 차원에 유의해야 합니다.** 최상의 품질을 위해 216x216픽셀(최대 크기)인 이미지 파일을 업로드하는 것이 좋습니다. 이러한 크기에 맞게 이미지를 늘이거나 왜곡하지 않도록 합니다.

**배지 이미지가 사각형이 아닌 경우 이미지를 투명하게 만듭니다.** 이미지 파일을 칭찬하기 전에 이 작업을 해야 합니다.

![왼쪽: 투명하지 않은 이미지가 있는 배지, 오른쪽: 투명한 이미지가 있는 배지](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>배지 집합 자산

기본 제공 배지 집합은 수정할 수 없습니다. 따라서 기본 제공 집합을 사용하도록 설정하면 집합의 모든 배지가 칭찬 앱에 추가됩니다. 기본 제공 집합에서 특정 배지를 추가하고 다른 배지를 남겨두고 싶은 경우 사용자 지정 배지로 사용할 배지를 다시 만드면 됩니다. 배지 이미지를 다운로드하고 아래 표의 기본 제공 집합에서 배지의 텍스트와 배경색을 찾을 수 있습니다.

### <a name="default-badges-assets"></a>기본 배지 자산

</br>

|배지 이름     |이미지 파일  |텍스트 색 | 배경색 |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|굉장한        |[멋진 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|코치          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Courage        |[Courage PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|창의성       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|포괄      |[포괄 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|리더십     |[리더십 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|낙관적       |[낙관적 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|문제 해결사 |[문제 해결사 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|팀 플레이어    |[팀 플레이어 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|감사합니다      |[PNG 감사합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>교육 자산에 대한 소셜 및 정서적 학습 배지

</br>

|배지 이름        |이미지 파일  |텍스트 색 | 배경색 |
|------------------|------------|---------- |--------|
|통신     |[통신 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|비판적 사고 |[비판적 사고 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|호기심         |[호기심 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empathy           |[Empathy PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|목표 달성      |[목표 달성 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|동기        |[동기 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|지속성       |[지속성 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|존중           |[PNG 존중](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|책임    |[책임 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|자아 인식    |[자체 인식 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|자체 관리   |[자체 관리 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|신의성    |[신의성 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
