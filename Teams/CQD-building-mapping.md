---
title: CQD(통화 품질 대시보드)에 대한 건물 맵 만들기
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: CQD(통화 품질 대시보드)에서 테넌트 업로드 및 데이터 작성에 사용할 수 있는 건물 맵을 만드는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: a119324090d05b593eb1ed66f41efbb7a5bd7a0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634102"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)에 대한 건물 맵 만들기

온라인 Microsoft Teams 비즈니스용 Skype 모든 클라이언트는 외부입니다. 결과적으로 클라이언트가 내부 회사 네트워크에 연결되어 있는지 여부에 관계없이 기본적으로 모든 클라이언트가 CQD(통화 품질 대시보드)에서 외부로 보고됩니다.

CQD를 사용할 때 엔드포인트의 위치와 관리할 수 있는 네트워크에 연결되어 있는지 또는 관리할 수 없는 네트워크에 연결되어 있는지 여부를 알아야 합니다. 관리할 수 있는 네트워크만 개선할 수 있는 것으로 가정합니다. 서브넷을 업로드하고 CQD에 정보를 구축하면 CQD를 사용하여 엔드포인트가 내부(관리되는) 네트워크에 연결되어 있는지 또는 외부(관리되지 않는) 네트워크에 연결되어 있는지 여부를 확인할 수 있습니다. 조직에 대한 건물 맵을 만들고 [CQD에](CQD-upload-tenant-building-data.md)업로드하는 것이 중요합니다.

## <a name="building-mapping-tools"></a>매핑 도구 구축

조직의 서브넷을 매핑하는 방법은 여러 가지가 있습니다. 도움이 필요한 경우 이 블로그 게시물에 설명된 CQDTools PowerShell [모듈을 사용할 수 있습니다.](https://aka.ms/cqdtools) 이러한 도구는 PowerShell을 기반으로 하여 AD(Active Directory) 사이트 및 서비스 및 Microsoft DHCP 서비스를 사용하여 건물 파일을 미리 채우는 데 도움이 됩니다. 이러한 도구는 다음 작업에 도움이 됩니다.

1. AD 사이트 및 서비스를 쿼리하고 내부에 포함된 정보를 기반으로 건물 파일을 생성합니다.
1. Microsoft DHCP 서버 또는 서버를 쿼리하여 서브넷 정보를 끌어오고 자동으로 건물 파일을 생성합니다.
1. 기존 건물 파일의 유효성을 검사하여 중복 및 겹치는지 검사합니다.
1. CQD에서 매핑되지 않은 서브넷을 찾을 수 있습니다.

## <a name="related-topics"></a>관련 주제

[업로드 CQD에서 테넌트 및 건물 데이터 저장](CQD-upload-tenant-building-data.md)