---
title: Teams 모임에 대한 사용자 지정 모임 배경
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: 배경과 같은 승인된 회사 자산을 사용하여 조직 내 Teams 모임에 대한 사용자 지정 배경을 만듭니다.
ms.openlocfilehash: f274165a24db2988cb95ad5900220168d0d60fdc
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800218"
---
# <a name="custom-meeting-backgrounds-for-teams-meetings"></a>Teams 모임에 대한 사용자 지정 모임 배경

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

## <a name="overview"></a>개요

Teams 모임에서 사용자 지정을 사용하면 조직에서 모임 환경에서 시각적 ID를 확장할 수 있습니다. 사용자 지정 모임 배경을 사용하면 내부 및 외부 모임 참가자를 통해 내부 기업 문화 구축을 촉진하고 전반적인 브랜드 인지도를 높이는 데 도움이 됩니다. 조직의 브랜드 관리 및 회사 커뮤니케이션 팀의 도움을 받아 관리자는 단일 테넌트 내에서 다양한 사업부 및 부서에 대한 사용자 지정 모임 배경을 쉽게 설정하고 만들 수 있습니다.

기본적으로 관리자이거나 모임 사용자 지정 정책이 할당된 Teams 프리미엄 라이선스 사용자는 사용자 지정 모임 배경을 특징으로 하는 모임을 만들 수 있습니다. 이러한 사용자 지정 배경은 사용할 Teams Premium 라이선스가 있는 조직 내 최종 사용자만 사용할 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

Teams 모임에 대한 사용자 지정 모임 배경을 설정하기 전에 다음 항목이 있는지 확인합니다.

- Teams Premium SKU에 대한 액세스
- Teams 관리 센터에 액세스할 수 있는 관리자이거나 사용자 지정 정책이 할당되었습니다.
- [사용자 지정 백그라운드 정책을](#enabling-the-custom-background-policy) 사용하도록 설정했습니다.
- 배경 이미지는 [필요한 사양을 충족합니다.](#adding-custom-background-images)

## <a name="setting-up-custom-meeting-backgrounds"></a>사용자 지정 모임 배경 설정

관리자는 Teams 관리 센터에서 Teams 모임에 대한 사용자 지정 모임 배경을 업로드하고 관리할 수 있습니다.

### <a name="enabling-the-custom-background-policy"></a>사용자 지정 백그라운드 정책 사용

관리자는 사용자 지정 배경을 만들려면 새 모임 사용자 지정 정책을 만들거나 조직의 전역 기본 정책을 수정해야 합니다.
사용자 지정 백그라운드 정책을 사용하도록 설정하기 위해 관리자는 다음 단계를 수행합니다.

1. Teams 관리 센터 열기
2. 탐색 창에서 **모임** 선택
3. 모임에서 사용자 지정 배경 정책에 액세스하는 두 가지 방법이 있습니다. **사용자 지정 정책을** 선택하여 기존 정책을 선택하거나 새 정책을 만들 수 있습니다. 또는 **모임 정책을** 선택한 다음 오른쪽 위에 있는 **사용자 지정 모임 이미지** 단추를 선택할 수 있습니다.
4. 선택한 정책 내에서 **사용자 지정 모임 배경 섹션으로 이동합니다.**
5. 설정을 사용하도록 설정하려면 **사용자 지정 배경** 설정을 해제에서 켜기로 전환합니다.
6. 저장을 선택합니다 **.**

### <a name="adding-custom-background-images"></a>사용자 지정 배경 이미지 추가

이제 사용자 지정 배경 정책을 사용하도록 설정했으므로 사용자 지정 배경 이미지를 업로드할 수 있습니다. 이러한 이미지는 업로드 시간별로 정렬된 최종 사용자의 인터페이스에 표시됩니다.

업로드는 다음 매개 변수를 준수해야 합니다. 관리자는 다음을 업로드할 수 있습니다.

- 해당 이미지에 대한 PNG 및 JPEG 이미지 형식
- 최소 크기가 360px X 360px인 이미지
- 최소 크기가 3840px X 2160px인 이미지
- 최대 50개 사용자 지정 배경 이미지

이미지를 업로드하려면 **모임** > **사용자 지정 정책** 으로 이동하여 이전 단계에서 정책을 선택합니다. **사용자 지정 모임 배경** 섹션까지 아래로 스크롤하고 사용자 지정 배경의 토글이 있는 테이블 아래에서 **+추가** 를 선택합니다. +추가를 선택하면 **배경 관리** 라는 창이 열리고 이미지를 추가할 수 있습니다.

> [!NOTE]
> Teams Premium 라이선스가 있는 최종 사용자만 배경 설정 패널에 이러한 이미지를 볼 수 있습니다.

### <a name="saving-custom-background-images"></a>사용자 지정 배경 이미지 저장

**사용자 지정 모임 배경** 섹션 아래의 새 테이블에서 업로드된 이미지의 미리 보기를 찾을 수 있습니다. 이 표에는 이미지의 이름과 해상도도 표시됩니다. 업로드된 이미지 선택을 확인하면 미리 보기 테이블 아래의 **저장** 단추를 선택합니다. 이제 저장을 선택했으므로 업로드된 배경이 Teams Premium 라이선스를 사용하여 최종 사용자에게 표시됩니다.

## <a name="where-are-custom-backgrounds-visible"></a>사용자 지정 배경이 표시되는 위치

다음 목록에는 사용자 지정 배경이 표시되는 지원되는 클라이언트가 표시됩니다.

- 웹 클라이언트
- 데스크톱 클라이언트
- Android
- iOS

### <a name="who-can-select-and-apply-custom-meeting-backgrounds"></a>사용자 지정 모임 배경을 선택하고 적용할 수 있는 사용자

사용이 허가된 Teams Premium 사용자만 배경 설정 패널에서 모임 배경을 사용할 수 있습니다.

> [!NOTE]
> 외부 또는 익명 사용자는 사용자 지정 모임 배경을 사용할 수 없습니다.

### <a name="who-can-view-custom-meeting-backgrounds"></a>사용자 지정 모임 배경을 볼 수 있는 사용자

라이선스가 부여된 최종 사용자만 업로드된 배경을 선택할 수 있지만 누구나 모임에 적용된 배경을 볼 수 있습니다. 이러한 사용자는 다음과 같습니다.

- 테넌트 내, Teams Premium 사용이 허가된 사용자
- 테넌트 내, 라이선스가 없는 사용자
- 외부 사용자
- 익명 사용자
