---
title: Office 365 OneDrive 및 SharePoint Online의 팀 환경에 대 한 복수 지역-지리적으로 지 활성화 된 테 넌 트
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
description: Office 365 OneDrive 및 SharePoint Online 다중 지역에서 팀을 사용 하는 방법에 대해 자세히 알아보세요.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e90e4a3c1ae2886a01802a805da3464cea3d8b50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180678"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Office 365 OneDrive 및 SharePoint Online의 팀 환경에 대 한 복수 지역-지리적으로 지 활성화 된 테 넌 트
===========================================

Microsoft 팀은 Office 365의 팀워크에 대 한 허브 인 그룹 채팅 소프트웨어입니다. Office 365 그룹 서비스는 SharePoint Online 및 비즈니스용 OneDrive와 함께 해당 파일 환경에 따라 구동 됩니다. 테 넌 트가 북미, 유럽, 호주 등의 여러 지리적 위치로 확장 되는 비즈니스용 OneDrive/SharePoint Online의 다중 지역에서 기본 파일 환경이 다중 지역 인식 이므로 파일을 사용 하 여 팀을 경험할 수 있습니다. 공동 작업도 다중 지역에서 인식 됩니다. 이는 원시 파일 환경에서 여러 Geos에 의해 호스팅되는 파일을 팀에 게 제공 하는 주요 최고의 기능입니다.

예를 들어 유럽 지역, 영국을 중앙 Geo로 사용 하는 Contoso의 테 넌 트에서 유럽 위성 사용자는 파일 탭의 왼쪽 창에 있는 OneDrive 파일을 볼 수 있지만,이는 유럽 데이터 위치 및 미국 Stat에서 호스트 됩니다. es는 테 넌 트의 중앙 위치입니다. 또한 사용자는 최근 보기 블레이드에서 최근에 사용한 파일에 액세스할 수 있습니다. 최근 파일에는 다른 Geos의 사용자가 사용자와 공유 하는 파일이 포함 되어 있을 수 있으며, 테 넌 트가 확장 된 다른 지리적 위치에서 마스터 될 수 있습니다. 

지정 된 팀의 그룹 사이트도 다중 지역에서 인식 됩니다. 즉, 유럽 위성 사용자가 팀을 만드는 경우 해당 그룹 사이트가 유럽 위치에 만들어지고 해당 팀 그룹과 연결 된 파일이 해당 위치에 그대로 유지 됩니다. 새 파일을 업로드 하거나 파일을 편집 하는 등의 모든 후속 환경은 해당 파일에 대 한 데이터 영주권의 약속을 유지 하면서 해당 유럽 위치를 대상으로 지정 됩니다. 이는 기본 foundation Office 365 그룹이 다중 지리적으로 인식 되는 것으로 모두 가능 합니다.

다중 지역 거주자는 단일 전역 테 넌 트 이므로, @ 멘 션은 위성 사용자가 거주 하는 위치에 관계 없이 전세계의 동료를 볼 수 있게 됩니다. 

팀 경험 내에 있는 채팅 및 모임 메신저 대화 노트의 대화는 다중 지역 인식 되지 않으며, 테 넌 트의 중앙 위치 내 에서만 유지 된다는 점에 유의 하세요. 일반적으로 채팅 대화는 데이터 영주권 요구 사항에는 적용 되지 않습니다.

Office 365 다중 지역에 대 한 자세한 내용은 [Microsoft 다중 지역 기능 페이지](https://aka.ms/multi-geo)를 참조 하세요.