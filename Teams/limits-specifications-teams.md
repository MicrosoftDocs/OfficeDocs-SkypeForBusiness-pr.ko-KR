---
title: Microsoft 팀의 제한 사항 및 사양
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/10/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: karuanag
description: Microsoft 팀에 적용 되는 제한, 사양 및 기타 요구 사항에 대해 알아봅니다.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40c334a1a0159614b77de11f8eb3e5a0e3dcc1b5
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184127"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a>Microsoft 팀의 제한 사항 및 사양

이 문서에서는 팀에 적용 되는 몇 가지 제한 사항, 사양 및 기타 요구 사항을 설명 합니다.

## <a name="teams-and-channels"></a>팀 및 채널 

|요소    | 최대 한도 |
|-----------|---------------|
|사용자가 만들 수 있는 팀 수 | 250 개체&제한에 따라 sup1.         |
|팀의 구성원 수 | 5000       |
|테 넌 트에서 허용 되는 조직 차원의 팀 수 | 5mb     |
|[조직 차원의 팀](create-an-org-wide-team.md) 구성원 수 | 5000       |
|전역 관리자가 만들 수 있는 팀 수        |  50만   |
|Office 365 테 넌 트가 가질 수 있는 팀 수    | 50만&sup2     |
|팀 당 채널 수    | 200 (삭제 된 채널 포함) &sup3         |

&sup1 Azure Active Directory의 모든 디렉터리 개체는이 제한에 대해 계산 됩니다. 전역 관리자는 [응용 프로그램 사용 권한을](https://docs.microsoft.com/graph/permissions-reference)사용 하 여 Microsoft Graph를 호출 하는 앱 처럼이 제한에서 제외 됩니다.

&sup2 이 제한에는 보관 된 팀이 포함 됩니다.

&sup3; 30 일 이내에 삭제 된 채널을 복원할 수 있습니다. 30 일 이내에 삭제 된 채널은 팀 제한에 따라 200 채널에 계속 해 서 계산 됩니다. 30 일이 지난 후 삭제 된 채널과 해당 콘텐츠는 영구적으로 삭제 되며 채널은 더 이상 팀 제한에 따라 200 채널에 대해 카운트 되지 않습니다.

## <a name="meetings-and-calls"></a>모임 및 통화 

|요소     | 최대 한도 |
|------------|---------------|
|모임에 참가 한 사용자 수  | 250    |

## <a name="teams-live-events"></a>팀 라이브 이벤트

|요소     | 최대 한도 |
|------------|---------------|
|청중 크기 | 1만 참석자 |
|이벤트 기간 | 4 시간 |
|Office 365 테 넌 트의 동시 라이브 이벤트 | ~ |

Live 이벤트 및 팀의 live 이벤트를 Skype 모임 브로드캐스트에 비교 하는 방법에 대 한 자세한 내용은 [팀 live 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참고 하세요.

## <a name="storage"></a>용량

Microsoft 팀의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에서 폴더를 가져옵니다. 대화 내에서 공유 된 파일은 문서 라이브러리에 자동으로 추가 되며 SharePoint에 설정 된 사용 권한 및 파일 보안 옵션은 팀 내에 자동으로 반영 됩니다.

테 넌 트에서 SharePoint Online이 활성화 되어 있지 않은 경우 Microsoft 팀 사용자는 팀에서 파일을 공유할 수 없습니다. 비즈니스용 OneDrive (SharePoint 라이선스에 연결 됨)가 해당 기능에 필요 하므로 개인 채팅의 사용자도 파일을 공유할 수 없습니다.

SharePoint Online 문서 라이브러리 및 비즈니스용 OneDrive에 파일을 저장 하면 테 넌 트 수준에서 구성 된 모든 준수 규칙이 따릅니다. 자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive For Microsoft 팀과의 상호 작용](sharepoint-onedrive-interact.md)을 참조 하세요.

팀은 파일 공유를 위해 SharePoint Online 백 엔드에서 실행 되므로 SharePoint 제한은 팀 내의 Files 섹션에 적용 됩니다. SharePoint Online에 적용 가능한 저장소 제한 사항은 다음과 같습니다.

|요소                 |Office 365 비즈니스 주요 기능  |Office 365 Business Premium   |Office 365 Enterprise E1  |Office 365 Enterprise E3  |Office 365 Enterprise E5  |Office 365 Enterprise F1  |
|------------------------|---------|---------|---------|---------|---------|---------|
|용량                 |조직 당 1TB 및 구입한 라이선스 당 10gb  |조직 당 1TB 및 구입한 라이선스 당 10gb  |조직 당 1TB 및 구입한 라이선스 당 10gb   |조직 당 1TB 및 구입한 라이선스 당 10gb |조직 당 1TB 및 구입한 라이선스 당 10gb  |조직 당 1TB           |
|팀 파일 저장소 |사이트 모음 또는 그룹 당 최대 25 TB |사이트 모음 또는 그룹 당 최대 25 TB |사이트 모음 또는 그룹 당 최대 25 TB |사이트 모음 또는 그룹 당 최대 25 TB |사이트 모음 또는 그룹 당 최대 25 TB |사이트 모음 또는 그룹 당 최대 25 TB |
|파일 업로드 제한 (파일당)    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |15 GB    |

채널은 팀에 대해 만든 SharePoint Online 사이트 모음 내의 폴더에 따라 지원 되므로 채널 내의 파일 탭은 자신이 속한 팀의 저장 용량 제한을 공유 합니다.

자세한 내용은 [SharePoint Online 제한을](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)참조 하세요.

## <a name="messaging"></a>메시지

Microsoft 팀에서 채팅 목록의 일부인 대화에 참여 하는 사용자는 관리자를 위해 Exchange Online (클라우드 기반) 사서함이 있어야 채팅 대화를 검색할 수 있습니다. 채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장 되기 때문입니다. 채팅 참가자에 게 Exchange Online 사서함이 없는 경우 관리자는 채팅을 통해 대화를 검색 하거나 보류할 수 없게 됩니다. 예를 들어 Exchange 하이브리드 배포에서 온-프레미스 사서함을 사용 하는 사용자는 Microsoft 팀의 채팅 목록에 속하는 대화에 참여할 수 있습니다. 그러나이 경우 사용자에 게 클라우드 기반 사서함이 없기 때문에 이러한 대화의 콘텐츠를 검색할 수 없으며 보류 되지 않습니다. 자세한 내용은 [Exchange 및 Microsoft 팀의 상호 작용 방식을](exchange-teams-interact.md)참조 하세요.

Microsoft Exchange 백 엔드에서 microsoft 팀 채팅 기능이 작동 하므로 Microsoft 팀 내에서 채팅 기능에 Exchange 메시징 제한을 적용할 수 있습니다. 사용자가 팀의 채널에 전자 메일을 보내려고 하는 경우 채널 전자 메일 주소를 사용 합니다. 전자 메일이 채널의 일부인 경우 누구나 회신 하 여 대화를 시작할 수 있습니다. 다음은 채널에 전자 메일을 보낼 때 적용 되는 몇 가지 제한 사항입니다. 

|요소  | 최대 한도  |
|---------|---------|
|개인 채팅의 사용자 수  | 100    |
|메시지 크기&dagger;  |25kb   |
|첨부 파일 수&Dagger;  |1천만     |
|인라인 이미지 수&Dagger; |50   |

&dagger;메시지가이 제한을 초과 하는 경우 미리 보기 메시지가 생성 되 고 사용자에 게 제공 된 링크에서 원래 전자 메일을 보거나 다운로드 하 라는 메시지가 표시 됩니다.

&Dagger;첨부 파일 또는 이미지 수가이 한도를 초과 하는 경우 메시지가 처리 되지 않으며, NDR 전자 메일을 보낸 사람에 게 다시 보내 오류를 알립니다.

> [!NOTE]
> 메시지 크기, 첨부 파일 및 인라인 이미지 제한은 모든 Office 365 라이선스에서 동일 합니다.

자세한 내용은 [Exchange Online 제한을](https://technet.microsoft.com/library/exchange-online-limits.aspx)참조 하세요.

## <a name="browsers"></a>브라우저인

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a>운영 체제

운영 체제 요구 사항에 대 한 자세한 내용은 [Microsoft 팀 용 클라이언트 가져오기를](get-clients.md)참조 하세요.
