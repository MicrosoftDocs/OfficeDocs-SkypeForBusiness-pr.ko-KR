---
title: Microsoft 팀의 민감도 레이블
author: lanachin
ms.author: v-lanac
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
description: Microsoft 팀에서 우편물 종류 레이블을 정의 하 고 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 446bd222ce29ed627eb3229b244228665bbff6c0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838118"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft 팀의 민감도 레이블

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[우편물 종류 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 사용 하면 팀 관리자가 팀 내에서 공동 작업을 수행 하는 중요 한 조직 콘텐츠에 액세스할 수 있습니다. [보안 & 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)에서 민감도 레이블 및 관련 정책을 정의할 수 있습니다. 이러한 레이블과 정책은 조직의 팀에 자동으로 적용 됩니다.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>민감도 레이블과 팀 분류 레이블의 차이점은 무엇 인가요?

민감도 레이블은 PowerShell을 사용 하 여 만들어야 할 분류 레이블과 다릅니다. 분류 레이블은 그룹과 연결 될 수 있지만 관련 된 실제 정책이 없는 텍스트 문자열입니다. 분류 레이블을 메타 데이터로 사용 하 여 내부 도구 및 스크립트를 통해 정책을 수동으로 적용할 수 있습니다.

다른 한편, 민감도 레이블과 해당 정책은 그룹 플랫폼, 보안 & 준수 센터, 팀 서비스를 조합 하 여 자동으로 종단 간 적용 됩니다. 민감도 레이블은 조직의 민감한 데이터를 보호 하기 위한 강력한 인프라 지원을 제공 합니다.  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>팀에 대 한 민감도 레이블 만들기, 관리 및 게시

팀의 민감도 레이블을 사용, 만들기, 게시 하는 방법에 대 한 자세한 내용은 [Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블 사용](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)을 참조 하세요.

>[!IMPORTANT]
>민감도 레이블을 만들고 업데이트 하 고 삭제 하는 경우에는 레이블을 사용자에 게 게시할 때 주의 해야 합니다. 시퀀스의 모든 편차를 통해 모든 사용자에 대해 영구 팀 만들기 오류가 발생할 수 있습니다. 따라서 <a href="#createpublishlabels">레이블을 만들고 게시</a>하 고, <a href="#modifydeletelabels">게시 된 레이블을 수정 및 삭제</a>하 고, <a href="#manageerrors">팀 만들기 오류를 관리</a>하는 경우에는 다음과 같은 작업을 수행 하는 것이 중요 합니다.

<a name="createpublishlabels"></a> **레이블 만들기 및 게시**

보안 & 준수 센터에서 레이블을 만들고 게시 하면 팀 만들기 인터페이스에서 레이블이 표시 되는 데 최대 24 시간이 걸릴 수 있습니다. 다음 단계를 사용 하 여 테 넌 트의 모든 사용자에 대 한 레이블을 게시 합니다.
1. 테 넌 트의 몇 가지 선택 사용자 계정에 대해 레이블을 만들고 게시 합니다.
2. 레이블이 게시 되 면 24 시간 동안 기다립니다.
3. 24 시간 후에는 레이블에 액세스할 수 있는 사용자 계정 중 하나를 사용 하 여 레이블이 포함 된 팀을 만들어 보세요.
4. 팀이 3 단계에서 성공적으로 만들어졌으면 나머지 사용자에 대 한 레이블을 테 넌 트에 게시 합니다.

게시 된 <a name="modifydeletelabels"></a> **레이블 수정 및 삭제**

우편물 종류 정책에 연결 된 상태에서 레이블을 삭제 하거나 수정 하면 테 넌 트에서 팀 만들기 오류가 발생할 수 있습니다. 따라서 레이블을 삭제 하거나 수정 하기 전에 먼저 연결 된 정책에서 레이블의 연관을 해제 해야 합니다. 다음 단계 사용  
레이블을 삭제 하거나 수정 하려면 다음을 실행 합니다.
1. 레이블을 사용 하는 모든 정책에서 레이블을 제거 합니다. 또는 정책 자체를 삭제할 수도 있습니다.
2. 정책에서 레이블을 제거 하거나 정책 자체를 삭제 하면 48 시간이 지난 후에 계속 진행 합니다.
3. 48 시간이 지난 후 팀 만들기 인터페이스를 시작 하 고 테 넌 트에서 사용자에 게 해당 레이블이 더 이상 표시 되지 않도록 합니다.
4. 이제 레이블을 안전 하 게 삭제 하거나 수정할 수 있습니다.

**팀 만들기 오류 관리** <a name="manageerrors"></a>

공용 미리 보기 중에 팀 만들기가 특정 시점에 실패 하기 시작 하면 다음 두 가지 옵션이 있습니다.
 - 팀을 만드는 동안 우편물 종류 레이블이 사용자에 게 필수적이 지 않은지 확인 합니다.
 - [이 미리 보기 사용](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)에서 스크립트를 사용 하 여 민감도 레이블을 해제 합니다.

EnableMIPLabels 설정은 다음과 같이 false로 설정 되어야 합니다.

```
$setting["EnableMIPLabels"] = "False"
 ```

## <a name="using-sensitivity-labels-with-teams"></a>팀과 우편물 종류 레이블 사용

조직의 팀에서 민감도 레이블을 사용 하는 방법에 대 한 몇 가지 예는 다음과 같습니다.

### <a name="privacy-setting-of-teams"></a>팀의 개인 정보 설정

팀을 만드는 동안 적용 하면 사용자가 특정 개인 정보 (공개 또는 비공개) 설정을 사용 하 여 팀을 만들 수 있는 민감도 레이블을 만들 수 있습니다.

예를 들어 보안 & 준수 센터에 "기밀" 이라는 레이블을 만들고이 레이블을 사용 하 여 만든 모든 팀이 개인 팀 이어야 하도록 팀을 구성 합니다. 사용자가 새 팀을 만들고 **기밀** 레이블을 선택 하는 경우 사용자가 사용할 수 있는 개인 정보 옵션은 **비공개**입니다. 공개 및 조직 전체와 같은 기타 개인 정보 옵션을 사용자에 게 사용할 수 없습니다.

![비밀 민감도 레이블의 스크린샷](media/sensitivity-labels-confidential-example.png)

마찬가지로 사용자가 새 팀을 만들 때 **일반** 을 선택 하는 경우에는 공용 또는 조직 차원의 팀만 만들 수 있습니다.

![일반 민감도 레이블의 스크린샷](media/sensitivity-labels-general-example.png)

팀을 만들 때 우편물 종류 레이블은 팀의 채널 오른쪽 위 모서리에 표시 됩니다.

![팀 채널의 우편물 종류 레이블 스크린샷](media/sensitivity-labels-channel.png)

팀 소유자는 팀으로 이동한 다음 **팀 편집**을 클릭 하 여 언제 든 지 팀의 민감도 레이블과 개인 정보 설정을 변경할 수 있습니다.

![팀 채널의 우편물 종류 레이블 스크린샷](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>팀에 대 한 게스트 액세스

특정 레이블을 사용 하 여 만든 팀에서 게스트 액세스를 허용 하는지 여부를 지정할 수 있습니다. 게스트 액세스를 허용 하지 않는 레이블을 사용 하 여 만든 팀은 조직의 사용자만 사용할 수 있습니다. 조직 외부의 사용자를 팀에 추가할 수 없습니다.

## <a name="known-issues"></a>알려진 문제

**Microsoft 팀 관리 센터의 민감도 레이블 지원**

현재 Microsoft 팀 관리 센터에서는 우편물 종류 레이블이 지원 되지 않습니다. 우편물 종류 레이블을 사용 하는 경우 팀을 만들거나 편집할 때 우편물 종류 레이블을 설정할 수 없습니다. 민감도 레이블은 팀 속성에도 표시 되지 않으며 Microsoft 팀 관리 센터의 **분류** 열에 표시 되지 않습니다.

**팀 그래프 Api, Powershell cmdlet 및 템플릿에 대 한 민감도 레이블 지원**

현재 사용자는 Graph Api, Powershell cmdlet, 템플릿을 통해 직접 만든 팀에 민감도 레이블을 적용할 수 없습니다.

**개인 채널의 SharePoint 사이트 모음에서 우편물 종류 레이블을 직접 편집**

팀에서 만든 개인 채널은 팀에 적용 된 민감도 레이블을 상속 합니다. 또한 개인 채널의 SharePoint 사이트 모음에도 동일한 레이블이 자동으로 적용 됩니다.

사용자가 개인 채널의 SharePoint 사이트 모음에서 우편물 종류 레이블을 직접 업데이트 하는 경우 팀 클라이언트에서 해당 레이블이 업데이트 되지 않습니다. 이 시나리오에서는 사용자가 개인 채널 헤더에서 팀에 적용 된 우편물 종류 레이블을 계속 볼 수 있습니다.

**팀 앱 외부의 민감도 레이블에 적용 된 변경 내용에 대 한 전파 시간**

팀 앱 외부의 민감도 레이블에 대 한 변경 사항은 팀 앱에서 적용 하는 데 최대 24 시간까지 걸릴 수 있습니다. 이는 테 넌 트의 레이블을 사용 하거나 사용 하지 않도록 변경한 내용, 레이블 이름, 설정, 정책의 변경에 적용 됩니다.

또한 팀을 지 원하는 그룹 또는 SharePoint 사이트 모음에 직접 변경한 내용은 팀 앱에 전파 하는 데 최대 24 시간이 걸릴 수 있습니다.
