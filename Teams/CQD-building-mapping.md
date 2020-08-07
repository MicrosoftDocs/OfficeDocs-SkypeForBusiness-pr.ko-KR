---
title: CQD (통화 품질 대시보드) 용 건물 지도 만들기
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 테 넌 트를 업로드 하 고 CQD (통화 품질 대시보드에서) 데이터를 작성 하는 데 사용할 수 있는 건물 지도를 만드는 방법에 대해 알아봅니다.
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584037"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>CQD (통화 품질 대시보드) 용 건물 지도 만들기

Microsoft 팀 또는 비즈니스용 Skype Online 배포의 경우 모든 클라이언트가 외부에 있습니다. 따라서 기본적으로 모든 클라이언트는 클라이언트가 내부 회사 네트워크에 연결 되어 있는지 여부에 관계 없이 CQD (통화 품질 대시보드) 외부로 보고 됩니다.

CQD를 사용 하는 경우 끝점의 위치를 알고 있어야 하며 관리할 수 있는 네트워크에 연결 되었는지 또는 관리할 수 없는 네트워크만을 관리 하는 것이 좋습니다. CQD에 서브넷 및 빌드 정보를 업로드 하면 CQD를 사용 하 여 끝점이 내부 (관리) 네트워크 또는 외부 (관리) 네트워크에 연결 되었는지 여부를 확인할 수 있습니다. 이 때문에 조직에 대 한 건물 지도를 만들고 [CQD에 업로드](CQD-upload-tenant-building-data.md)하는 것이 중요 합니다.

## <a name="building-mapping-tools"></a>빌드 매핑 도구

조직의 서브넷을 매핑하는 방법에는 여러 가지가 있습니다. 도움이 필요한 경우이 [블로그 게시물](https://aka.ms/cqdtools)에서 설명 하는 CQDTools PowerShell 모듈을 사용할 수 있습니다. 이러한 도구는 PowerShell을 기반으로 하며 AD (Active Directory) 사이트 및 서비스와 Microsoft DHCP 서비스를 사용 하 여 문서 파일을 미리 채울 수 있도록 지원 합니다. 이러한 도구는 다음 작업을 수행 하는 데 도움이 됩니다.

1. 광고 사이트 및 서비스를 쿼리하고에 포함 된 정보를 기반으로 문서 파일을 만듭니다.
1. Microsoft DHCP 서버를 쿼리하여 서브넷 정보를 가져오고 자동으로 문서 파일을 만듭니다.
1. 기존 문서 파일의 유효성을 검사 하 고 중복 항목이 있는지 확인 합니다.
1. CQD에서 매핑되지 않은 서브넷을 찾습니다.

## <a name="related-topics"></a>관련 항목

[테 넌 트 업로드 및 CQD에 데이터 빌드](CQD-upload-tenant-building-data.md)