---
title: 정부용 팀 정책 패키지
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
description: 정부 조직의 팀 정책 패키지를 사용 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804038"
---
# <a name="teams-policy-packages-for-government"></a>정부용 팀 정책 패키지

> [!NOTE]
> 현재 Microsoft 365 정부 GCC High 또는 DoD 배포에서는 정책 패키지를 사용할 수 없습니다.

## <a name="overview"></a>개요

Microsoft 팀의 [정책 패키지](manage-policy-packages.md) 는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다. 정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다. 사용자의 요구에 맞게 패키지의 정책 설정을 사용자 지정할 수 있습니다. 정책 패키지의 정책 설정을 변경 하면 해당 패키지에 할당 된 모든 사용자가 업데이트 된 설정을 받습니다. Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 관리할 수 있습니다.

정책 패키지는 패키지에 따라 다음에 대 한 정책을 미리 정의 합니다.

- 메시징
- 모임
- 통화
- 앱 설정
- 라이브 이벤트

현재 팀에는 다음과 같은 정부용 정책 패키지가 포함 되어 있습니다.

|Microsoft 팀 관리 센터의 패키지 이름|최적 용도|설명 |
|---------|---------|---------|
|공개 안전 책임자  |정부 조직의 공개 보안 관리 책임자  |조직의 공개 보안 책임자에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다. |
|Firstline manager  |정부 조직의 firstline 관리자 |조직의 Firstline 관리자에 게 정책 집합을 만들고 해당 설정을 적용 합니다.|
|Firstline worker  |정부 조직의 firstline Worker |정책 집합을 만들고 조직의 Firstline Worker에 해당 설정을 적용 합니다.|

![건강 보험 정책 패키지 스크린샷](media/policy-packages-gov.png)

정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다. 예를 들어 조직의 사용자에 게 공용 보안 책임자 정책 패키지를 할당 하면 패키지의 각 정책에 대 한 PublicSafety_Officer 라는 정책이 만들어집니다.

![의료 임상 작업자 패키지의 정책 스크린샷](media/policy-packages-public-safety-officer.png)

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

![관리 센터에서 정책 패키지를 할당 하는 방법 스크린샷](media/policy-packages-gov-assign.png)

사용자에 게 정책이 할당 된 후 나중에 다른 정책을 할당 하는 경우에는 가장 최근의 할당이 우선적으로 적용 됩니다.

## <a name="related-topics"></a>관련 항목

[Teams에서 정책 패키지 관리](manage-policy-packages.md)

[팀에서 사용자에 게 정책 할당](assign-policies.md) 
