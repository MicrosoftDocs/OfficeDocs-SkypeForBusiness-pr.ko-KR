---
title: Teams 환경의 Microsoft 365 환경
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 이 문서에서는 다중 지역 지원 환경에서 Teams Microsoft 365 방법을 알아보고 있습니다.
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760541"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams 사용 테넌트에서 Microsoft 365 환경 제공

Microsoft Teams 그룹 채팅 소프트웨어, 팀워크 및 Microsoft 365 허브 Office 365. 이 서비스는 Microsoft 365 Online과 함께 SharePoint 그룹 서비스를 통해 비즈니스용 OneDrive 환경을 제공합니다. 테넌트가 북아메리카, 유럽 및 오스트레일리아와 같은 여러 지리적 위치로 확장되는 비즈니스용 OneDrive SharePoint Online Multi-Geo/Teams 테넌트에서 파일 공동 작업 환경도 다중 지역 인식입니다. 이 기능은 네이티브 파일 환경의 여러 Teams 호스트되는 파일을 표면에 저장하기 위한 핵심 첨단 기능입니다. 여기에는 OneNote 및 위키 파일이 포함됩니다.

예를 들어 유럽과의 Contoso 테넌트에서 유럽을 중앙 지역으로, 북아메리카를 중앙 지오로  지정하면 유럽 위성 사용자가 왼쪽 OneDrive 파일 탭 아래에 해당 파일 파일을 볼 수 있습니다. 이 파일은 유럽 데이터 위치에 호스트되어 있으며 미국은 테넌트의 중앙 위치입니다. 또한 사용자는 최근 보기 블레이드에서 가장 최근에 사용한 파일에 **액세스할 수** 있습니다. 최근 파일에는 다른 지리적 위치에 있는 사용자로부터 공유된 파일이 있을 수 있습니다. 

주어진 팀의 SharePoint 사이트도 다중 지역 인식입니다. 즉, 유럽 위성 사용자가 팀을 만드는 경우 해당 SharePoint 사이트가 유럽 위치에 생성됩니다. 해당 팀과 연결된 파일은 해당 위치에 저장됩니다. 새 파일을 업로드하거나 파일을 편집하는 등의 후속 환경은 해당 유럽 위치에 저장되어 해당 파일에 대한 데이터 잔재를 약속합니다.

다중 지역 테넌트는 단일 글로벌 테넌트이기 때문에 위성 사용자가 어디에 있든 전 세계에서 동료를 볼 수 있습니다.

채팅, 채널 메시지, 모임 IM 노트/채팅 Teams 환경 내의 대화는 다중 지역 인식이 아니며 모두 테넌트의 중앙 위치 내에만 보관됩니다. 일반적으로 채팅 대화는 데이터 레지스전시 요구에 적용되지 않습니다. 자세한 내용은 의 데이터 위치를 [Microsoft Teams.](location-of-data-in-teams.md)

다중 지역 지원은 Teams [로드맵에](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)Microsoft 365 있습니다.

Multi-Geo에 대한 자세한 내용은 [Microsoft Multi-Geo 기능 페이지를 참조하세요.](https://aka.ms/multi-geo)
