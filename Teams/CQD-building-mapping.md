---
title: CQD(통화 품질 대시보드)에 대한 건물 맵 만들기
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: CQD(통화 품질 대시보드)에서 테넌트 및 빌드 데이터를 업로드하는 데 사용할 수 있는 건물 맵을 만드는 방법을 알아봅니다.
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789823"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)에 대한 건물 맵 만들기

Microsoft Teams 또는 비즈니스용 Skype Online 배포에서는 모든 클라이언트가 외부에 있습니다. 따라서 기본적으로 모든 클라이언트는 내부 회사 네트워크에 연결되어 있는지 여부에 관계없이 CQD(통화 품질 대시보드)에서 외부로 보고됩니다.

CQD로 작업할 때 엔드포인트의 위치와 엔드포인트가 관리할 수 있는 네트워크에 연결되었는지 또는 관리할 수 없는 네트워크에 연결되었는지를 알아야 합니다. 즉, 관리할 수 있는 네트워크만 개선할 수 있다는 가정이 있습니다. 서브넷을 업로드하고 CQD에 정보를 빌드하면 CQD에서 엔드포인트가 내부(관리형) 네트워크 또는 외부(관리되지 않는) 네트워크에 연결되었는지 여부를 확인할 수 있습니다. 따라서 조직에 대한 건물 맵을 만들고 [CQD에 업로드하는 것이](CQD-upload-tenant-building-data.md) 중요합니다.

## <a name="building-mapping-tools"></a>매핑 도구 빌드

조직의 서브넷을 매핑하는 방법에는 여러 가지가 있습니다. 도움이 필요한 경우 이 [블로그 게시물에](https://aka.ms/cqdtools) 설명된 CQDTools PowerShell 모듈을 사용할 수 있습니다. 이러한 도구는 PowerShell을 기반으로 하며 AD(Active Directory) 사이트 및 서비스 및 Microsoft DHCP 서비스를 사용하여 건물 파일을 미리 채우는 데 도움이 됩니다. 이러한 도구는 다음 작업에 도움이 됩니다.

1. AD 사이트 및 서비스를 쿼리하고, 포함된 정보를 기반으로 건물 파일을 만듭니다.
1. Microsoft DHCP 서버 또는 서버를 쿼리하여 서브넷 정보를 가져오고 건물 파일을 자동으로 만듭니다.
1. 중복 및 겹침을 확인하여 기존 건물 파일의 유효성을 검사합니다.
1. CQD에서 매핑되지 않은 서브넷을 찾습니다.

## <a name="related-topics"></a>관련 주제

[CQD에서 테넌트 업로드 및 데이터 빌드](CQD-upload-tenant-building-data.md)