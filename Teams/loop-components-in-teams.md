---
title: Teams의 루프 구성 요소 개요
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Teams에서 루프 구성 요소를 관리하는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1405464a3eb963d55c357b5fcc165c67a143e5e1
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198550"
---
# <a name="overview-of-loop-components-in-teams"></a>Teams의 루프 구성 요소 개요

Teams 채팅의 루프 구성 요소는 아이디어를 만들고, 만들고, 의사 결정을 내릴 수 있는 새로운 방법을 제공합니다. 테이블, 작업 목록 또는 단락과 같은 구성 요소를 보내 채팅의 모든 사용자가 인라인으로 편집하고 변경 내용을 볼 수 있습니다. 

> [!Note]
> 루프 구성 요소는 Teams에서 사용할 수 있는 [Microsoft Loop 앱](https://www.microsoft.com/en-us/microsoft-loop)의 첫 번째 기능입니다. 

**작업을 더 빠르게 함께 수행합니다.** 의제를 크라우드 소싱하거나, 그룹의 작업 항목을 추적하거나, 공동으로 메모를 작성합니다. 루프 구성 요소를 사용하여 더 쉽게 만들 수 있는 몇 가지 시나리오에 불과합니다.

**구성 요소를 공유합니다.** 이 릴리스에서는 루프 구성 요소를 다른 Teams 채팅에 공유할 수 있습니다. 받는 사람은 어디에서든 편집할 수 있으며 변경 내용에 관계없이 즉시 업데이트를 볼 수 있습니다.

**채팅에서 시작하여 여기에서 빌드합니다.** Teams 채팅에서 만드는 모든 구성 요소는 OneDrive의 파일에 자동으로 저장됩니다. 따라서 채팅에서 공동 작업을 시작한 다음 나중에 Office.com 파일로 이동하여 편집할 수 있는 더 큰 시각적 공간을 확보하고 원하는 만큼 구성 요소를 추가할 수 있습니다.

Teams의 루프 구성 요소에 대한 관리자 설정에 대한 자세한 내용은 [SharePoint에서 루프 구성 요소 관리를 참조하세요](/sharepoint/manage-loop-components).

## <a name="clients-and-platforms"></a>클라이언트 및 플랫폼

Windows, Mac, Linux, iOS 및 Android의 Teams 앱에서 사용할 수 있습니다.

## <a name="loop-components-and-fluid-files"></a>루프 구성 요소 및 .fluid 파일

Teams에서 만든 루프 구성 요소는 작성자의 OneDrive에 저장된 .fluid(가까운 장래에 .loop로 변경될 예정) 파일을 통해 지원됩니다. OneDrive에서 파일이 된다는 것은 사용자가 모든 Office 문서처럼 루프 구성 요소(.fluid 파일)를 쉽게 만들고, 검색하고, 관리할 수 있음을 의미합니다. 

## <a name="how-are-fluid-files-stored"></a>.fluid 파일은 어떻게 저장되는가?

.fluid 파일은 최근 및 권장 영역과 같이 Office.com 및 OneDrive에 표시됩니다. 사용자는 Office.com 및 OneDrive에서 .fluid 파일의 콘텐츠를 검색할 수 있습니다. .fluid 파일은 OneDrive에서 이전 버전으로 복원할 수 있습니다. 루프 구성 요소를 만들려면 채팅 참가자에게 OneDrive 계정이 있어야 합니다. 유효한 OneDrive 계정이 없으면 채팅 참가자는 유효한 OneDrive 계정을 가지고 있지만 직접 만들 수 없는 다른 사용자가 만든 구성 요소에서 공동 작업할 수 있습니다. 

.fluid 파일을 OneDrive에서 SharePoint 사이트로 이동하면 라이브 구성 요소가 Teams 채팅에서 로드되지 않습니다.

## <a name="what-happens-if-the-owner-of-the-file-leaves-the-company"></a>파일 소유자가 회사를 떠나면 어떻게 되나요?

OneDrive 보존 정책은 사용자가 만든 다른 콘텐츠와 마찬가지로 .fluid 파일에 적용됩니다.

## <a name="how-are-fluid-files-shared"></a>.fluid 파일은 어떻게 공유합니까?

루프 구성 요소는 Teams 채팅에 삽입하거나 한 채팅에서 다른 채팅으로 복사할 수 있습니다. (루프 구성 요소는 아직 채널에서 지원되지 않습니다.) 기본적으로 조직의 기존 권한으로 설정되지만 사용자는 보내기 전에 권한을 변경하여 모든 사용자가 액세스할 수 있도록 할 수 있습니다.

Office.com Teams 채팅에서 구성 요소를 열면 다른 Office 문서에 제공되는 공유 옵션과 유사하게 창 맨 위에 공유 기능이 제공됩니다.

## <a name="what-if-a-fluid-file-becomes-corrupted-or-damaged"></a>.fluid 파일이 손상되거나 손상되면 어떻게 해야 할까요?

버전 기록을 사용하면 이전 버전의 파일에서 검토, 복원 또는 복사할 수 있습니다.

## <a name="what-apps-can-open-and-edit-fluid-files"></a>.fluid 파일을 열고 편집할 수 있는 앱은 무엇인가요?

.fluid 파일은 브라우저에서 링크(예: Office.com) 및 Teams 채팅의 루프 구성 요소로만 열 수 있습니다. 다운로드한 경우 먼저 OneDrive 또는 SharePoint에 다시 업로드하지 않고는 다시 열 수 없습니다.

## <a name="does-fluid-files-support-ediscovery"></a>.fluid 파일은 eDiscovery를 지원하나요?

.fluid 파일은 검색할 수 있지만 eDiscovery 워크플로 지원이 제한되어 있습니다. 현재 .fluid 파일은 작성자의 OneDrive에 저장되며 eDiscovery(표준) 및 eDiscovery(프리미엄) 모두에서 검색 및 컬렉션에 사용할 수 있습니다. 그러나 미리 보기로 렌더링되지 않으며 검토를 위한 내보내기 형식은 기존 도구에서 사용할 수 없습니다. 내보낸 콘텐츠를 보려면 OneDrive에 업로드합니다. 원하는 경우 [설정 관리](/sharepoint/manage-loop-components#settings-management) 섹션에 설명된 대로 이러한 환경을 일시적으로 사용하지 않도록 설정할 수 있습니다.

## <a name="if-loop-is-disabled-from-the-admin-switch-what-will-the-user-experience-be"></a>관리 스위치에서 루프를 사용하지 않도록 설정한 경우 사용자 환경은 어떻게 되나요?

[설정 관리](/sharepoint/manage-loop-components#settings-management) 섹션에 설명된 대로 이러한 환경을 사용하지 않도록 설정하면 다음 환경 변경 내용이 적용됩니다.

- Teams 메시징 내의 만들기/삽입 진입점이 숨겨집니다. 사용자는 새 .fluid 파일을 만들 수 없습니다.
- 이전에 대화형 루프 구성 요소로 렌더링되었던 기존 메시지는 대신 하이퍼링크 "루프 구성 요소"로 렌더링됩니다. Teams 내에는 대화형 콘텐츠가 표시되지 않습니다.
- 최종 사용자가 "루프 구성 요소" 하이퍼링크를 클릭하거나 비즈니스용 OneDrive .fluid 파일을 찾아서 열면 별도의 브라우저 탭에서 파일이 열립니다. 최종 사용자는 여전히 파일을 편집할 수 있습니다.

## <a name="known-issues"></a>알려진 문제

- 테넌트 기본 파일 사용 권한을 *특정 사용자* (사용자가 지정한 사람만)로 설정하면 루프 구성 요소에 대한 링크를 복사하고 다른 채팅에 붙여넣기 위해서는 보낸 사람이 권한 대화 상자를 사용하고 특정 사용자 옵션에 받는 사람을 추가하여 액세스 권한을 올바르게 부여해야 합니다.
- 테넌트 기본 파일 사용 권한을 *특정 사용자* (사용자가 지정하는 사람만)로 설정하면 20명 이상의 구성원이 있는 그룹 채팅에서 라이브 구성 요소를 만들려면 보낸 사람이 구성 요소에 대한 사용 권한 옵션을 수동으로 선택해야 합니다.
- Teams 검색에서 루프 구성 요소를 검색하면 채팅 메시지 자체가 아니라 office.com 구성 요소에 대한 링크가 반환됩니다.
- 루프 구성 요소는 페더레이션된 채팅에서 비활성화됩니다.
- 게스트는 회사 공유 링크를 통해 공유되는 라이브 구성 요소에서 공동 작업할 수 없습니다. **이 채팅에서 현재 사람** 권한을 설정하여 게스트와 구성 요소를 공유합니다.
- 루프 구성 요소는 Teams 채널에서 지원되지 않습니다.
- 채팅의 루프 구성 요소는 파일이 다른 라이브러리로 이동된 경우에만 로드되지 않습니다. 파일이 다른 폴더로 이동되면 채팅에서 계속 로드됩니다.
