---
title: Microsoft 365 다중 지역 사용 환경의 Teams 환경
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
description: 이 문서에서는 Microsoft 365 다중 지역 지원 환경에서 Teams를 사용하는 방법을 배워보게 됩니다.
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122248"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Microsoft 365 다중 지역 지원 테넌트의 Teams 환경

Microsoft Teams는 Microsoft 365 및 Office 365의 팀워크 허브인 그룹 채팅 소프트웨어입니다. 파일 환경을 위해 SharePoint Online 및 비즈니스용 OneDrive와 함께 Microsoft 365 그룹 서비스를 제공합니다. 테넌트가 북아메리카, 유럽 및 오스트레일리아와 같은 여러 지리적 위치로 확장되는 비즈니스용 OneDrive/SharePoint Online 다중 지역 테넌트에서, 파일 공동 작업의 Teams 환경은 다중 지역 인식입니다. 이 기능은 Teams에서 네이티브 파일 환경의 여러 지리적 위치로 호스트되는 파일을 표면화할 수 있는 핵심 첨단 기능입니다. 여기에는 OneNote 및 Wiki 파일도 포함됩니다.

예를 들어 유럽을 위성 지역으로, 북아메리카를 중앙 지역으로 하는 Contoso 테넌트에서 유럽  위성 사용자는 파일이 유럽 데이터 위치에서 호스트되는 경우 미국은 테넌트의 중앙 위치인 경우 왼쪽 창의 파일 탭 아래에 OneDrive 파일을 볼 수 있습니다. 또한 사용자는 최근 보기 블레이드에서 가장 최근에 사용한 파일에 **액세스할** 수 있습니다. 최근 파일에는 다른 지리적 위치에 있는 사용자로부터 공유된 파일이 포함되어 있을 수 있습니다. 

주어진 팀의 SharePoint 사이트도 다중 지역 인식입니다. 즉, 유럽 위성 사용자가 팀을 만드는 경우 해당 SharePoint 사이트가 유럽 위치에 만들어집니다. 해당 팀과 연결된 파일은 해당 위치에 저장됩니다. 새 파일을 업로드하거나 파일을 편집하는 등의 후속 환경은 해당 유럽 위치에 저장되어 해당 파일에 대한 데이터 주체의 약속을 유지하게 됩니다.

다중 지역 테넌트는 단일 글로벌 테넌트이기 때문에 @ 언급 중에 위성 사용자는 어디에 있든 전 세계 동료를 볼 수 있습니다.

Teams 환경 내의 채팅, 채널 메시지 및 모임 IM 메모/채팅의 대화는 다중 지역 인식이 아니며 모두 테넌트의 중앙 위치 내에만 보관됩니다. 일반적으로 채팅 대화는 데이터 레지전시 요구에 적용되지 않습니다. 자세한 내용은 [Microsoft Teams의 데이터 위치를 참조하세요.](location-of-data-in-teams.md)

다중 지역에 대한 자세한 내용은 Microsoft 다중 지역 기능 페이지를 [참조하세요.](https://aka.ms/multi-geo)
