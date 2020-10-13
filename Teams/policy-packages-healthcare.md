---
title: 의료에 대 한 팀 정책 패키지
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 의료 조직의 팀 정책 패키지를 사용 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e55102e07f7ffc77dc67c5d6697cb754c398cc40
ms.sourcegitcommit: a043bde507a9f6747fdd2063dd085edb3c1d6c3c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48427173"
---
# <a name="teams-policy-packages-for-healthcare"></a>의료에 대 한 팀 정책 패키지

## <a name="overview"></a>개요

Microsoft 팀의 [정책 패키지](manage-policy-packages.md) 는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다. 정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다. 사용자의 요구에 맞게 패키지의 정책 설정을 사용자 지정할 수 있습니다. 정책 패키지의 정책 설정을 변경 하면 해당 패키지에 할당 된 모든 사용자가 업데이트 된 설정을 받습니다. Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 관리할 수 있습니다.

정책 패키지는 패키지에 따라 다음에 대 한 정책을 미리 정의 합니다.

- 메시징
- 모임
- 통화
- 앱 설정
- 라이브 이벤트

현재 팀에는 다음과 같은 건강 보험 정책 패키지가 포함 되어 있습니다.

|Microsoft 팀 관리 센터의 패키지 이름|최적 용도|설명 |
|---------|---------|---------|
|의료 임상 근로자  |건강 관리 조직의 임상 근로자  |등록 된 nurses, 청구 nurses, 의사, 소셜 작업자에 게 채팅, 통화, 교대 관리, 모임에 대 한 전체 액세스 등의 임상 근로자를 제공 하는 정책 및 정책 설정 집합을 만듭니다. |
|의료 정보 근로자  |건강 관리 조직의 정보 근로자 |IT 직원, informatics 스태프, 재무 담당자, 규정 준수 관리자, 채팅, 통화, 모임에 대 한 모든 액세스 권한을 제공 하는 정책 및 정책 설정 집합을 만듭니다.|
|의료 환자 실  |환자 실 장치|건강 관리 조직의 환자 방에 해당 하는 정책 및 정책 설정 집합을 만듭니다.|

![건강 보험 정책 패키지 스크린샷](media/policy-packages-healthcare.png)

정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다. 예를 들어 조직의 clinicians에 의료 임상 작업자 정책 패키지를 할당 하면 패키지의 각 정책에 대 한 Healthcare_ClinicalWorker 라는 정책이 만들어집니다.

![의료 임상 작업자 패키지의 정책 스크린샷](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a>정책 패키지 시작

의료 정책 패키지를 시작 하려면 Microsoft 관리 센터 온 보 hub 허브에서 **건강 관리 기본 사항을**선택한 다음 **역할별로 정책 설정 할당**을 선택 합니다. 시작할 준비가 되 면 조직의 사용자를 지정할 정책 패키지를 결정 합니다.

패키지의 특정 정책 및 해당 설정에 대해 자세히 알아보려면 **정책 세부 정보 보기** 를 선택 합니다. 팀 관리 센터에서 과제를 할당 한 후에 [사용자 지정할 수 있습니다](manage-policy-packages.md#customize-policies-in-a-policy-package) .

할당할 패키지를 하나 이상 선택 하 고 **다음**을 클릭 합니다. 역할에 가장 적합 한 정책 패키지를 검색 하 고 사용자를 추가할 수 있습니다. 한 번에 둘 이상의 정책 패키지에 개별적으로 배정할 수 없습니다.

사용자를 올바른 정책 패키지에 추가한 후에는 **완료** 가 선택 항목을 종결 합니다. Microsoft 팀 관리 센터에서 계속 해 서 정책 패키지를 사용자 지정 하 고 관리할 수 있습니다.

## <a name="manage-policy-packages"></a>정책 패키지 관리

### <a name="view"></a>보기

패키지를 할당 하기 전에 정책 패키지의 각 정책에 대 한 설정을 확인 합니다. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지**를 선택 하 고 패키지 이름을 선택한 다음 정책 이름을 선택 합니다.

미리 정의 된 값이 조직에 적합 한지 아니면 조직의 요구 사항에 따라 더 엄격 하 게 또는 lenient 사용자 지정 해야 하는지 여부를 결정 합니다.

### <a name="customize"></a>사용자 지정

필요에 따라 정책 패키지의 정책 설정을 조직의 필요에 맞게 사용자 지정 합니다. 정책 설정에 대 한 변경 내용은 패키지를 할당 한 사용자에 게 자동으로 적용 됩니다. 정책 패키지의 정책 설정을 편집 하려면 Microsoft 팀 관리 센터에서 정책 패키지를 선택 하 고 편집 하려는 정책의 이름을 선택한 다음 **편집**을 선택 합니다.

정책 패키지를 할당 한 후에는 패키지의 정책 설정을 변경할 수도 있습니다. 자세히 알아보려면 [정책 패키지의 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조 하세요. 

### <a name="assign"></a>배정할

사용자에 게 정책 패키지를 할당 합니다. 한 명 또는 여러 명의 사용자에 게 정책 패키지를 할당 하려면 **사용자 관리**를 클릭 합니다. [PowerShell을 사용](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) 하 여 대규모 사용자 일괄 처리에 정책 패키지를 할당할 수도 있습니다. 

Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 할당 하는 방법에 대 한 단계는 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조 하세요.

![관리 센터에서 정책 패키지를 할당 하는 방법 스크린샷](media/policy-packages-healthcare-assign.png)

사용자에 게 정책이 할당 된 후 나중에 다른 정책을 할당 하는 경우에는 가장 최근의 할당이 우선적으로 적용 됩니다.

## <a name="related-topics"></a>관련 항목

[Teams에서 정책 패키지 관리](manage-policy-packages.md)

[팀에서 사용자에 게 정책 할당](assign-policies.md)
