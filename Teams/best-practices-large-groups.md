---
title: 대규모 팀 관리 Microsoft Teams 모범 사례
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 조직의 요구 사항을 충족하기 위해 Microsoft Teams 대규모 팀을 관리하는 모범 사례에 대해 자세히 알아보습니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d856a47fb4d7888dcaa990cde9a3dd151dac79ea
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619674"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>대규모 팀 관리 Microsoft Teams - 모범 사례

Microsoft Teams 멤버가 수십 명인 소규모 그룹과 수천 명의 구성원이 있는 대규모 그룹 간의 통신을 촉진하는 것이 똑같이 효과적입니다. 팀 [크기에](limits-specifications-teams.md) 대한 업데이트에 대한 Teams 제한 및 사양을 검토합니다. 팀 규모가 증가하면 고유한 관리 및 운영 과제가 있습니다. 이 문서에서는 수천 명의 구성원으로 구성된 대규모 팀을 만들고 관리하는 모범 사례를 설명합니다.

## <a name="value-of-large-teams"></a>대규모 팀의 값

대규모 팀은 다음 공동 작업 시나리오를 사용하도록 설정하는 데 매우 유용합니다.

- **부서 전체 공동** 작업 : 조직에 재무, 운영, R&D와 같은 여러 부서가 있는 경우 특정 부서의 모든 구성원을 포함하는 단일 팀을 만들 수 있습니다. 이제 부서와 관련된 모든 통신을 이 팀에서 공유할 수 있습니다. 이는 구성원의 즉각적인 도달 및 참여를 용이하게 합니다.

- **직원 리소스 그룹의** 공동 작업: 조직에는 서로 관심 있는 많은 사람들이 서로 다른 부서 또는 회사 그룹에 속하는 경우가 있습니다. 예를 들어 개인 금융 및 투자에 대한 열정을 공유하는 그룹이 있을 수 있습니다. 대규모 조직에서 연결하기가 어려운 경우가 종종 있습니다. 이러한 그룹에 대한 커뮤니티를 개발하기 위해 테넌트 관리자는 누구나 참가하고 활용할 수 있는 공용 회사 전체 리소스 그룹 역할을 하는 대규모 팀을 만들 수 있습니다. 결국 이러한 커뮤니티는 새 구성원과 기존 멤버가 모두 즐길 수 있는 정보를 수집합니다.

- **내부 및** 외부 구성원 간의 공동 작업 : 인기 있는 제품은 종종 새로운 제품 릴리스를 시도하고 피드백을 제공하기를 열의를 품고 있는 초기 채택자 커뮤니티를 개발합니다. 초기 채택자는 제품을 형성하는 데 도움이 되는 제품 그룹과의 관계를 개발합니다. 이러한 시나리오에서 테넌트 관리자는 풍부한 제품 개발 프로세스를 용이하게 하기 위해 내부 제품 그룹과 외부 제품 평가자가 모두 포함된 대규모 팀을 설정할 수 있습니다. 이러한 팀은 선택된 고객 집합에 고객 지원을 제공할 수 있습니다.

## <a name="create-teams-from-existing-groups"></a>기존 그룹에서 팀 만들기

연락처 그룹, 보안 그룹 또는 Office 사용하여 팀을 시작합니다. 그룹을 가져와 팀을 만들거나 팀 그룹에서 팀을 Office 있습니다.

**팀을** 만들 그룹 가져오기 : 최대 3,500명 이상의 구성원이 있는 그룹을 Teams Teams 그룹의 총 구성원 수를 자동으로 계산합니다. 이는 일회성 가져오기만 수행되며 그룹의 향후 변경 내용은 해당 그룹에서 자동으로 업데이트되지 Teams.

**대규모 그룹에서** 팀 만들기 : Microsoft 365 그룹에서 팀을 만들면 Microsoft 365 그룹과 팀에 자동으로 Microsoft 365 멤버가 됩니다.  향후 팀 구성원이 팀 그룹에 Microsoft 365 팀에서 자동으로 추가되거나 제거됩니다.

## <a name="bulk-importexportremove-members-in-a-team"></a>팀의 멤버 대량 가져오기/내보내기/제거

Azure Portal을 사용하면 사용자가 그룹에서 멤버를 일괄 가져오기/내보내기/Microsoft 365 수 있습니다. 자세한 내용은 그룹 [멤버를 대량 가져오기 를 참조하세요.](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)

모든 팀이 Microsoft 365 지원하기 때문에 Azure Portal을 사용하여 팀에 해당하는 그룹에서 이러한 작업을 수행할 수 있습니다. 멤버 작업은 24시간 이내에 팀에 반영됩니다.

## <a name="create-channels-to-focus-discussions"></a>토론에 집중할 채널 만들기

포커스 채널을 만들어 그룹 토론을 좁힐 수 있습니다. 팀 [구성에 대한 모범 사례를 참조합니다.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>채널 만들기 제한

팀 구성원이 채널을 만들 수 있도록 허용되는 경우 해당 팀에는 채널 스프래플을 사용할 수 있습니다. 팀 소유자는 구성원 권한의 구성원에 대한 채널 **만들기, 업데이트, 삭제 및 설정 > 해제해야 합니다.** 팀 [및 채널 개요를 참조하세요.](teams-channels-overview.md)

![관리 콘솔의 멤버 권한 섹션을 표시하는 화면 설정 탭입니다.](media/no-channel-creation.png "관리자 콘솔의 구성원 사용 권한 섹션이 탭에 있는 설정 이미지입니다. 구성원이 채널을 만들거나 삭제할 수 있도록 허용 옵션이 선택되지 않습니다.")

## <a name="add-favorite-channels"></a>즐겨찾기 채널 추가

새 사용자 참여 및 콘텐츠 검색 속도를 향상하기 위해 기본적으로 사용자가 사용할 수 있는 즐겨찾기 채널을 선택할 수 있습니다. 관리 센터의 **채널** 창에서 구성원 표시 열 아래 **채널을 검사합니다.**

![관리 콘솔의 채널 창을 보여주는 화면 이미지입니다.](media/favorite-channels.png "관리자 콘솔의 채널 창을 보여주는 화면 이미지입니다. 일부 채널은 멤버에 대한 표시를 검사합니다.")

 자세한 내용은 첫 [번째 팀](get-started-with-teams-create-your-first-teams-and-channels.md) 및 채널 만들기를 참조하세요.

## <a name="regulate-applications-and-bots-in-large-teams"></a>대규모 팀에서 애플리케이션 및 봇 규제

방해되는 애플리케이션 또는 봇의 추가를 방지하기 위해 팀 소유자는 팀 구성원에 대한 앱 및 커넥터를 사용하지 않도록 설정, 추가, 제거 및 업로드할 수 있습니다. 구성원 권한 아래 설정 > 관리 센터에서 구성원이 앱 **또는** 커넥터를 추가할 수 있도록 허용하는 세 가지 옵션을 선택하지 않습니다.

![창의 멤버 권한 섹션을 설정 이미지입니다.](media/disable-bots-connectors.png "창의 멤버 권한 섹션을 설정 이미지입니다. 구성원이 앱 또는 커넥터를 추가할 수 있도록 허용하는 옵션이 선택되지 않습니다.")

앱, [봇, & 참조하세요.](deploy-apps-microsoft-teams-landing-page.md)

## <a name="regulate-team-and-channel-mentions"></a>팀 및 채널 언급 규제

팀 및 채널 언급을 사용하여 특정 채널 게시물에 전체 팀의 관심을 끌 수 있습니다. 게시물에 언급이 사용된 후 수천 명의 팀 구성원에게 알림이 전송됩니다. 알림이 너무 자주 발생하는 경우 팀 구성원이 오버로드될 수 있으며 팀 소유자에게 불평할 수 있습니다. 팀 또는 채널 언급을 방지하기 위해 팀 창의 상자를 선택 해제하여 구성원에 대한 팀 및 채널  언급을 설정 > @mentions.

![창의 언급 섹션을 설정 이미지입니다.](media/no-at-mentions.png "창의 언급 섹션을 설정 이미지입니다. 표시 및 언론에 대한 구성원에게 액세스 권한을 부여하는 옵션은 선택되지 않습니다.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>채널에서 중재 설정 고려하기

팀 소유자는 채널에 대한 중재를 설정하여 해당 채널에서 새 게시물을 시작하고 채널의 게시물에 회신할 수 있는 사용자를 제어할 수 있습니다. 중재를 설정할 때 한 명 이상의 팀 구성원을 선택하여 중재자로 지정할 수 있습니다. 팀 소유자는 기본적으로 중재자입니다. 자세한 내용은 채널 중재 설정 [및 관리를 참조하세요.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>관련 주제

- [조직을 구성하기 위한 모범 Teams](best-practices-organizing.md)
- [오그 전체 팀 만들기](create-an-org-wide-team.md)