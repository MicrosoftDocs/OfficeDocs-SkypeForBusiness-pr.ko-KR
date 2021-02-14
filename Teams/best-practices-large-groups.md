---
title: Microsoft Teams에서 대규모 팀 관리 - 모범 사례
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 조직의 요구를 충족하기 위해 Microsoft Teams에서 대규모 팀을 관리하기 위한 모범 사례에 대해 자세히 배워야 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 90345578ceb6bbf8d8752b561511d8df85023bf1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582665"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Microsoft Teams에서 대규모 팀 관리 - 모범 사례
======================================================

Microsoft Teams는 수십 명의 구성원이 있는 소규모 그룹과 수천 명의 구성원이 있는 대규모 그룹 간의 통신을 촉진하는 데도 똑같이 효과적입니다. 팀 [크기에 대한](limits-specifications-teams.md) 업데이트는 Teams에 대한 제한 및 사양을 검토하세요. 팀 규모를 늘리면 고유한 관리 및 운영 과제가 있습니다. 이 문서에서는 수천 명의 구성원으로 구성된 대규모 팀을 만들고 관리하기 위한 모범 사례를 제공합니다.

## <a name="value-of-large-teams"></a>대규모 팀의 가치

대규모 팀은 다음과 같은 공동 작업 시나리오를 사용하도록 설정하는 데 매우 유용합니다.

- **부서** 전체 공동 작업: 조직에 재무, 운영, R&D 등의 여러 부서가 있는 경우 특정 부서의 모든 구성원을 포함하는 단일 팀을 만들 수 있습니다. 이제 부서와 관련된 모든 커뮤니케이션을 이 팀에서 공유할 수 있으며, 이를 통해 구성원의 즉각적인 연락과 참여를 용이하게 할 수 있습니다.

- **직원 리소스 그룹의 공동 작업:** 조직에는 종종 다른 부서 또는 작업 그룹에 속한 상호 관심 있는 대규모 사용자 그룹이 있습니다. 예를 들어 개인 재무와 투자에 대한 열정을 공유하는 사용자 그룹이 있을 수 있습니다. 대규모 조직에서는 연결하기가 어려운 경우가 종종 있습니다. 테넌트 관리자는 이러한 그룹에 대한 커뮤니티를 개발하기 위해 누구나 참가하고 활용할 수 있는 공용 회사 전체 리소스 그룹 역할을 하는 대규모 팀을 만들 수 있습니다. 결국 이러한 커뮤니티는 신규 및 기존 구성원이 즐길 수 있는 정보를 수집합니다.

- **내부 및** 외부 구성원 간의 공동 작업: 인기 있는 제품은 종종 새 제품 릴리스를 시도하고 피드백을 제공하려는 초기 채택자 커뮤니티를 개발합니다. Early Adopters는 제품 그룹과 관계를 맺고 제품을 형성하는 데 도움을 줄 수 있습니다. 이러한 시나리오에서 테넌트 관리자는 풍부한 제품 개발 프로세스를 용이하게 하기 위해 내부 제품 그룹과 외부 제품 평가자가 모두 포함된 대규모 팀을 설정할 수 있습니다. 이러한 팀은 선택한 고객 집합에 고객 지원을 제공할 수 있습니다.

## <a name="create-teams-from-existing-groups"></a>기존 그룹에서 팀 만들기

연락처 그룹, 보안 그룹 또는 Office 그룹을 사용하여 팀을 바로 시작할 수 있습니다. 그룹을 가져와 팀을 만들거나 Office 그룹에서 팀을 만들 수 있습니다.

**팀을 만들** 그룹 가져오기: 최대 3,500명이 있는 그룹을 Teams로 가져오면 Teams에서 자동으로 그룹의 총 구성원 수를 계산합니다. 일회성 가져오기 전용으로, 그룹의 향후 변경 내용은 Teams에서 자동으로 업데이트되지 않습니다.

**대규모 Microsoft 365** 그룹에서 팀 만들기: 대규모 Microsoft 365 그룹에서 팀을 만들면 구성원은 자동으로  Microsoft 365 그룹 및 팀의 일부가 됩니다. 향후에는 팀 구성원이 Microsoft 365 그룹에 가입하거나 떠날 때 팀에서 자동으로 추가되거나 제거됩니다.

## <a name="create-channels-to-focus-discussions"></a>토론에 집중할 채널 만들기

포커스가 있는 채널을 만들어 그룹 토론 범위를 좁힐 수 있습니다. 팀 [구성에 대한 모범 사례를 참조합니다.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>채널 만들기 제한

팀 구성원이 채널을 만들 수 있는 경우 해당 팀에는 채널 스프래플이 있습니다. 팀 소유자는 구성원 권한 설정에서 구성원에 대한 채널 **만들기, 업데이트, 삭제 및 복원을 > 합니다.** 팀 [및 채널 개요를 참조하세요.](teams-channels-overview.md)

![관리 콘솔 설정 탭의 구성원 사용 권한 섹션을 보여주는 화면 이미지입니다.](media/no-channel-creation.png "관리 콘솔 설정 탭의 구성원 사용 권한 섹션에 있는 화면 이미지입니다. 구성원이 채널을 만들거나 삭제할 수 있도록 허용 옵션을 선택하지 않습니다.")

## <a name="add-favorite-channels"></a>즐겨찾는 채널 추가

새 사용자 참여 및 콘텐츠 검색 속도를 향상하기 위해 기본적으로 사용자가 사용할 수 있는 즐겨 찾는 채널을 선택할 수 있습니다. 관리 센터의 **채널** 창에서 구성원 표시 열 아래에 **있는 채널을** 검사합니다.

![관리 콘솔의 채널 창을 보여주는 화면 이미지입니다.](media/favorite-channels.png "관리 콘솔의 채널 창을 보여주는 화면 이미지입니다. 일부 채널은 구성원에 대한 표시를 확인했습니다.")

 자세한 [내용은 첫 번째 팀 및 채널](get-started-with-teams-create-your-first-teams-and-channels.md) 만들기를 참조하세요.

## <a name="regulate-applications-and-bots-in-large-teams"></a>대규모 팀에서 애플리케이션 및 봇 규제

애플리케이션 또는 봇의 추가를 방해하지 않도록 팀 소유자는 팀 구성원에 대한 앱 및 커넥터를 비활성화, 추가, 제거 및 업로드할 수 있습니다. 구성원 권한 설정 > 관리 센터에서 구성원이 앱 **또는** 커넥터를 추가할 수 있는 세 가지 옵션을 선택하지 않습니다.

![설정 창의 구성원 사용 권한 섹션을 보여주는 화면 이미지입니다.](media/disable-bots-connectors.png "설정 창의 구성원 사용 권한 섹션을 보여주는 화면 이미지입니다. 멤버가 앱 또는 커넥터를 추가할 수 있도록 허용하는 옵션이 선택되지 않습니다.")

앱, [봇, & 참조하세요.](deploy-apps-microsoft-teams-landing-page.md)

## <a name="regulate-team-and-channel-mentions"></a>팀 및 채널 언급 규제

팀 및 채널 언급을 사용하여 특정 채널 게시물에 전체 팀의 주목을 끌 수 있습니다. 게시물에 언급이 사용된 경우 수천 명의 팀 구성원에게 알림이 전송됩니다. 알림이 너무 자주 발생하는 경우 팀 구성원이 오버로드될 수 있으며 팀 소유자에게 불만을 할 수 있습니다. 팀 또는 채널 언급을 방지하려면 팀 설정 창에서 확인란을 선택 해제하여 구성원에 대한 팀 **및 채널 > @mentions** 해제합니다.

![설정 창의 Mentions 섹션을 보여주는 화면 이미지입니다.](media/no-at-mentions.png "설정 창의 Mentions 섹션을 보여주는 화면 이미지입니다. 구성원에게 언론에 대한 액세스 권한을 표시하고 부여하는 옵션은 선택되지 않습니다.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>채널에서 중재 설정 고려하기

팀 소유자는 채널에 대한 중재를 설정하여 해당 채널에서 새 게시물을 시작하고 채널의 게시물에 회신할 수 있는 사용자를 제어할 수 있습니다. 중재를 설정할 때 한 명 이상의 팀 구성원을 선택하여 중재자로 지정할 수 있습니다. 팀 소유자는 기본적으로 중재자입니다. 자세한 내용은 채널 중재 설정 [및 관리를 참조하세요.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>관련 항목

- [Teams 구성 모범 사례](best-practices-organizing.md)
- [전체 팀 만들기](create-an-org-wide-team.md)
