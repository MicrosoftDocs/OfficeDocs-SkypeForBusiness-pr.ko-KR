---
title: 에 대한 민감도 Microsoft Teams
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 민감도 레이블을 사용하여 팀을 보호하는 방법을 Microsoft Teams.
ms.openlocfilehash: 135049e80d6a8c0e008886ca924cca64b5943695
ms.sourcegitcommit: 9fd9cfe3683503f3c35ad5591324396e2532caef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59496695"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>에 대한 민감도 Microsoft Teams

[민감도](/microsoft-365/compliance/sensitivity-labels) 레이블을 사용하면 Teams 관리자가 팀 내에서 공동 작업하는 동안 생성된 중요한 조직 콘텐츠에 대한 액세스를 보호하고 규제할 수 있습니다. [Microsoft](/microsoft-365/compliance/go-to-the-securitycompliance-center)규정 준수 센터에서 관련 정책으로 민감도 레이블을 구성한 후 이러한 레이블을 조직의 팀에 적용할 수 있습니다.

민감도 레이블은 현재 교육 SKUS를 사용하는 고객을 위한 수업 팀에서 지원되지 Teams 없습니다. 라이선스에 대한 자세한 내용은 서비스 [Microsoft Teams 참조하세요.](/office365/servicedescriptions/teams-service-description)

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>민감도 레이블과 분류 분류의 차이점은 Teams 무엇입니까?

민감도 레이블은 Azure AD 그룹 Teams 분류와 다릅니다. 분류는 그룹과 연결될 수 Microsoft 365 실제 정책이 없는 텍스트 문자열입니다. 분류를 메타데이터로 사용한 다음 내부 도구 및 스크립트와 같은 다른 메서드를 사용하여 정책을 적용해야 합니다.

민감도 레이블을 사용하는 이점은 해당 정책이 Microsoft 365 그룹 플랫폼, 규정 준수 센터 및 Teams 결합하여 종단 Teams 것입니다. 민감도 레이블은 조직의 중요한 데이터를 보호하고 내부 정책 또는 규정을 준수하도록 보장하기 위한 강력한 인프라 지원을 제공합니다.

현재 Teams 분류를 사용하는 경우 이러한 값을 민감도 레이블로 변환하는 방법에 대한 자세한 내용은 다음 설명서를 [참조하세요.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>민감도 레이블에 대한 예제 시나리오

조직에서 민감도 레이블을 사용하여 민감도 레이블을 사용하는 Teams 예제 시나리오:

- [팀에 대한 개인 정보 수준 설정(공용 또는 비공개)](#set-the-privacy-level-for-teams)
- [팀에 대한 게스트 액세스 제어](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>팀에 대한 개인 정보 수준 설정

팀을 만드는 동안 적용할 때 사용자가 특정 개인 정보(공개 또는 비공개) 설정을 사용하여 팀을 만들 수 있도록 하는 민감도 레이블을 만들고 구성할 수 있습니다.

예를 들어 개인으로 구성된 레이블 개인 정보 옵션이 있는 "기밀"이라는 민감도 레이블을 만들고 **게시합니다.** 결과적으로 이 레이블로 만든 모든 팀은 개인 팀이 되어야 합니다. 

사용자가 새 팀을 만들고 기밀  레이블을 선택하면 사용자가 사용할 수 있는 유일한 개인 정보 옵션은 **비공개입니다.** 공용 및 조직 전체와 같은 다른 개인 정보 보호 옵션은 사용자가 다음을 선택할 수 없습니다.

![기밀 민감도 레이블 스크린샷.](media/sensitivity-labels-confidential-example.png)

마찬가지로 레이블 개인 정보 보호 옵션이 공용으로 구성된 "일반"이라는 민감도 레이블을 만들고 **게시합니다.** 사용자가 새 팀을 만들 때 이 레이블을 선택할 때만 공개 또는 전체 팀을 만들 수 있습니다.

![일반 민감도 레이블 스크린샷.](media/sensitivity-labels-general-example.png)

팀을 만들면 팀의 채널 오른쪽 위 모서리에 있는 사용자에게 민감도 레이블이 표시됩니다. 

![팀 채널의 민감도 레이블 스크린샷.](media/sensitivity-labels-channel.png)

팀 소유자는 팀으로 이동하여 팀의 민감도 레이블 및 개인 정보 설정을 변경한 다음 팀 편집 을 **클릭합니다.**

![팀 속성의 민감도 레이블 스크린샷.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>팀에 대한 게스트 액세스 제어

민감도 레이블을 사용하여 팀에 대한 게스트 액세스를 제어할 수 있습니다. Teams 액세스를 허용하지 않는 레이블로 만든 사용자는 조직의 사용자만 사용할 수 있습니다. 조직 외부의 사람들은 팀에 추가할 수 없습니다.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터

관리 센터에서 팀을 만들거나 편집할 때 민감도 레이블을 적용할 Microsoft Teams 있습니다. 

민감도 레이블은 팀 속성 및 관리  센터의 팀  관리 페이지의 분류 Microsoft Teams 표시됩니다.

## <a name="limitations"></a>제한 사항

민감도 레이블을 사용하기 전에 Teams 제한 사항을 알고 있어야 합니다.

- **민감도 레이블은 API, PowerShell cmdlet 및 Teams Graph 지원되지 않습니다.**
    
    사용자는 기본 API, PowerShell cmd Teams let 및 Teams Graph 통해 직접 팀을 만드는 동안 민감도 레이블을 지정할 Teams 수 없습니다. 그러나 최신 그룹 Graph API 및 PowerShell cmdlet을 사용하면 레이블이 있는 그룹을 만들 수 있습니다. 따라서 사용자는 먼저 그룹 api 또는 PowerShell cmdlet을 사용하여 그룹 Graph 그룹을 만든 다음 이러한 그룹을 그룹으로 변환하여 Teams.

- **개인 채널에 대한 지원**
    
    팀에서 만든 개인 채널은 팀에 적용된 민감도 레이블을 상속합니다. 동일한 레이블은 개인 채널에 대한 SharePoint 사이트 모음에 자동으로 적용됩니다.
    
    그러나 사용자가 개인 채널에 대한 SharePoint 사이트에서 민감도 레이블을 직접 변경하는 경우 해당 레이블 변경은 해당 Teams 반영되지 않습니다. 이 시나리오에서 사용자는 개인 채널 헤더에서 팀에 적용된 원래 민감도 레이블을 계속 볼 수 있습니다.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>사용자에 대한 민감도 레이블을 만들고 구성하는 Teams

다음에 대한 민감도 레이블을 만들고 Microsoft 365 설명서의 지침을 Teams. 

- [민감도 레이블을](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)사용하여 Microsoft Teams, 그룹 및 Microsoft 365 사이트의 콘텐츠를 SharePoint.
