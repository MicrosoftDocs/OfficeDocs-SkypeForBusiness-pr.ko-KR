---
title: Microsoft Teams의 민감도 레이블
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: abgupta
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 민감도 레이블을 정의하고 사용하는 방법을 배워야 합니다.
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795780"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams의 민감도 레이블

[민감도 레이블을 사용하면](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) Teams 관리자가 팀 내에서 공동 작업하는 동안 생성된 중요한 조직 콘텐츠에 대한 액세스를 규제할 수 있습니다. 준수 센터에서 민감도 레이블 및 관련 정책을 정의할 [수 있습니다.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) 이러한 레이블 및 정책은 조직의 팀에 자동으로 적용됩니다.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>민감도 레이블과 Teams 분류 레이블의 차이점은 무엇입니까?

민감도 레이블은 분류 레이블과 다릅니다. 분류 레이블은 Microsoft 365 그룹과 연결될 수 있지만 연결된 실제 정책이 없는 텍스트 문자열입니다. 분류 레이블을 메타데이터로 사용하여 내부 도구 및 스크립트를 통해 정책을 수동으로 적용합니다.

반면에 민감도 레이블 및 해당 정책은 그룹 플랫폼, Security & 준수 센터 및 Teams 서비스의 조합을 통해 종단 & 자동으로 적용됩니다. 민감도 레이블은 조직의 중요한 데이터를 보호하는 강력한 인프라 지원을 제공합니다.  

기존 그룹을 분류 레이블 사용에서 민감도 레이블 사용으로 마이그레이션하려면 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)그룹에 대한 Azure Active Directory 분류 및 민감도 레이블의 지침을 사용하세요.

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Teams에 대한 민감도 레이블 만들기, 관리 및 게시

Teams에 대한 민감도 레이블을 사용하도록 설정, 만들기 및 게시하는 방법에 대한 자세한 내용은 민감도 레이블을 사용하여 [Microsoft Teams, Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)그룹 및 SharePoint 사이트의 콘텐츠를 보호하세요.

>[!IMPORTANT]
>민감도 레이블을 만들고, 업데이트하고, 삭제하려면 사용자에게 레이블을 게시하는 신중한 시차를 지정해야 합니다. 시퀀스의 모든 오차로 인해 모든 사용자에 대한 영구 팀 만들기 오류가 발생할 수 있습니다. 따라서 레이블을 만들고 <a href="#createpublishlabels">게시하고,</a>게시된 레이블을 수정 및 삭제하고, <a href="#modifydeletelabels"></a>팀 만들기 오류를 관리할 때 다음을 해야 <a href="#manageerrors">합니다.</a>

**레이블 만들기 및 게시** <a name="createpublishlabels"></a>

레이블을 만들어 준수 센터에 게시하면 팀 만들기 인터페이스에 레이블이 표시될 때 최대 10분이 걸릴 수 있습니다. 다음 단계를 사용하여 테넌트의 모든 사용자에 대한 레이블을 게시합니다.
1. 레이블을 만들고 테넌트에서 몇 가지 선택된 사용자 계정에 대해 게시합니다.
2. 레이블이 게시될 때 10분 정도 기다립니다.
3. 10분 후에 레이블에 대한 액세스 권한이 있는 사용자 계정 중 하나를 사용하여 레이블이 있는 팀을 만들어 시도합니다.
4. 팀이 3단계에서 성공적으로 만든 경우 계속 진행하여 테넌트의 나머지 사용자에 대한 레이블을 게시합니다.

**게시된 레이블 수정 및 삭제** <a name="modifydeletelabels"></a>

민감도 정책과 연결된 레이블을 삭제하거나 수정하면 테넌트 전체에서 팀 만들기에 실패할 수 있습니다. 따라서 레이블을 삭제하거나 수정하기 전에 먼저 연결된 정책에서 레이블을 연결 취소해야 합니다. 다음 단계 사용  
레이블을 삭제하거나 수정하려면:
1. 레이블을 사용하는 모든 정책에서 레이블을 제거합니다. 또는 정책 자체를 삭제할 수도 있습니다.
2. 레이블이 정책에서 제거되거나 정책 자체가 삭제되면 10분 동안 기다렸다가 계속 진행합니다.
3. 10분 후에 팀 만들기 인터페이스를 시작하고 테넌트의 모든 사용자에게 레이블이 더 이상 표시되지 않도록 합니다.
4. 이제 레이블을 안전하게 삭제하거나 수정할 수 있습니다.

**팀 만들기 오류 관리** <a name="manageerrors"></a>

공개 미리 보기 중 어느 시점에서든 팀 만들기가 실패하기 시작하는 경우 다음 두 가지 옵션이 있습니다.
 - 팀을 만들 때 민감도 레이블이 사용자에 대해 필수가 아닌지 확인
 - 이 미리 보기 사용에서 스크립트를 사용하여 민감도 [레이블을 해제합니다.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)

EnableMIPLabels 설정은 다음과 같이 false로 설정해야 합니다.

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Teams에서 민감도 레이블 사용

다음은 조직의 Teams에서 민감도 레이블을 사용하는 방법에 대한 몇 가지 예제 시나리오입니다.

### <a name="privacy-setting-of-teams"></a>팀의 개인 정보 설정

팀을 만드는 동안 적용될 때 사용자가 특정 개인 정보(공개 또는 비공개) 설정으로 팀을 만들 수 있도록 하는 민감도 레이블을 만들 수 있습니다.

예를 들어 보안 & 준수 센터에서 "기밀"이라는 레이블을 만들고 이 레이블로 만든 모든 팀이 비공개 팀이 되어야 하도록 Teams를 구성합니다. 사용자가 새 팀을 만들고 기밀  레이블을 선택하면 사용자가 사용할 수 있는 유일한 개인 정보 옵션은 **비공개입니다.** 공개 및 전체와 같은 기타 개인 정보 옵션은 사용자에 대해 사용할 수 없습니다.

![기밀 민감도 레이블 스크린샷](media/sensitivity-labels-confidential-example.png)

마찬가지로 사용자가 새 팀을 만들 때 **일반을** 선택하는 경우 공개 또는 전체 팀만 만들 수 있습니다.

![일반 민감도 레이블 스크린샷](media/sensitivity-labels-general-example.png)

팀을 만들면 민감도 레이블이 팀의 채널 오른쪽 위 모서리에 표시됩니다.

![팀 채널의 민감도 레이블 스크린샷](media/sensitivity-labels-channel.png)

팀 소유자는 팀으로 이동한 다음 편집 팀을 클릭하여 팀의 민감도 레이블 및 개인 정보 설정을 변경할 **수 있습니다.**

![팀 속성의 민감도 레이블 스크린샷](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>팀에 대한 게스트 액세스

특정 레이블을 사용하여 만든 팀이 게스트 액세스를 허용할지 여부를 지정할 수 있습니다. 게스트 액세스를 허용하지 않는 레이블로 만든 팀은 조직의 사용자만 사용할 수 있습니다. 조직 외부의 사람은 팀에 추가할 수 없습니다.

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터의 민감도 레이블

Microsoft Teams 관리 센터에서 팀을 만들거나 편집할 때 민감도 레이블을 설정할 수 있습니다. 민감도 레이블은 팀 속성 및 Microsoft  Teams 관리 센터의 팀 관리 페이지의 분류 열에도 표시됩니다.

## <a name="known-issues"></a>알려진 문제

**Teams Graph API, PowerShell cmdlet 및 템플릿에서 민감도 레이블 지원**

현재 사용자는 Graph API, PowerShell cmdlet 및 템플릿을 통해 직접 만든 팀에 민감도 레이블을 적용할 수 없습니다.

**Teams EDU SKU의 민감도 레이블 지원**

민감도 레이블은 현재 Teams Education SKUS를 사용하는 고객에게 지원되지 않습니다.

**개인 채널의 SharePoint 사이트 모음에서 직접 민감도 레이블 편집**

팀에서 만든 비공개 채널은 팀에 적용된 민감도 레이블을 상속합니다. 또한 동일한 레이블이 개인 채널의 SharePoint 사이트 모음에 자동으로 적용됩니다.

사용자가 개인 채널의 SharePoint 사이트 모음에서 민감도 레이블을 직접 업데이트하는 경우 해당 레이블은 Teams 클라이언트에서 업데이트되지 않습니다. 이 시나리오에서 사용자는 개인 채널 헤더에서 팀에 적용된 민감도 레이블을 계속 볼 수 있습니다.

**Teams 앱 외부의 민감도 레이블에 적용된 변경 내용의 전파 시간**

Teams 앱 외부의 민감도 레이블에 대한 변경 내용은 Teams 앱에 반영하는 데 최대 24시간이 걸릴 수 있습니다. 이는 테넌트에 대한 레이블을 사용 또는 사용하지 않도록 설정하기 위해 변경한 내용, 레이블 이름, 설정 및 정책에 대한 변경 내용에 적용됩니다.

또한 팀을 지원하는 그룹 또는 SharePoint 사이트 모음에 직접 적용된 레이블을 변경하면 Teams 앱에 전파되는 데 최대 24시간이 걸릴 수 있습니다.
