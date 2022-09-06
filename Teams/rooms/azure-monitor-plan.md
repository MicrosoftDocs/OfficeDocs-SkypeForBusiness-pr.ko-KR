---
title: Azure Monitor를 사용하여 Microsoft Teams 룸 모니터링 계획
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 이 문서에서는 Azure Monitor를 사용하여 비즈니스용 Skype 또는 Teams 구현에서 Microsoft Teams 룸 모니터링하기 위한 계획 고려 사항에 대해 설명합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5640fd63ac413403105be7d5f23e413b2f19ebdf
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606397"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Azure Monitor를 사용하여 Microsoft Teams 룸 모니터링 계획
 
 이 문서에서는 Azure Monitor를 사용하여 Microsoft Teams 또는 비즈니스용 Skype 구현에서 Microsoft Teams 룸 디바이스를 관리하기 위한 계획 고려 사항에 대해 설명합니다.

> [!NOTE]
> Teams 관리 센터를 사용하여 [Teams 룸 상태 모니터링을 설정할](../alerts/device-health-status.md) 수도 있습니다.

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

[Azure Monitor](/azure/azure-monitor/overview) 는 처음부터 클라우드에서 설계된 모니터링 서비스의 컬렉션입니다. Azure Monitor 구성 요소는 온-프레미스 리소스를 배포하고 관리하는 대신 Azure에서 완전히 호스트됩니다. 구성은 최소이며 몇 분 안에 실행될 수 있습니다. 일부 사용자 지정 작업을 사용하면 개별 회의실 시스템에 대한 시스템 상태 또는 오류에 대한 알림을 제공하여 Microsoft Teams 룸 모니터링하는 데 도움이 될 수 있으며 수천 개의 Microsoft Teams 룸 관리하도록 확장할 수 있습니다.
  
이 문서에서는 Microsoft Teams 룸 Azure Monitor 기반 모니터링을 구현하는 데 필요한 요구 사항, 디자인/아키텍처 및 구현 모범 사례에 대해 설명합니다. 또한 Microsoft Teams 룸 대한 Azure Monitor 구현에 대한 자세한 문서와 Microsoft Teams 룸 룸의 지속적인 모니터링을 위한 중요한 참조 정보에 대한 링크를 제공합니다.
  
## <a name="functional-overview"></a>기능 개요

![Azure Monitor를 사용하는 Microsoft Teams 룸 관리 다이어그램](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Microsoft Teams 룸 앱은 Windows 이벤트 로그에 이벤트를 씁니다. Microsoft Monitoring Agent가 설치되면 Azure Monitor 서비스에 정보를 전달합니다.
  
올바르게 구성되면 Log Analytics는 이벤트 설명에 포함된 JSON 페이로드를 구문 분석하여 Microsoft Teams 룸 작동하는 방식과 감지되는 오류를 설명합니다.
  
Azure Monitor를 사용하는 관리자는 오프라인 상태이거나 앱, 연결 또는 하드웨어 오류가 발생하는 Microsoft Teams 룸 대한 알림을 받을 수 있을 뿐만 아니라 시스템을 다시 시작해야 하는지 여부를 알 수 있습니다. 각 시스템 상태는 자주 업데이트되므로 이러한 알림은 실시간 업데이트에 가깝습니다.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor 요구 사항

Log Analytics 기능을 사용하려면 Azure Monitor에 유효한 Azure 구독이 있어야 합니다. 조직의 구독을 만들려면 [Log Analytics 작업 영역 시작을](/azure/azure-monitor/learn/quick-create-workspace) 참조하세요.
  
Log Analytics 뷰 디자이너를 사용하는 방법을 숙지해야 합니다. 자세한 내용은 [Log Analytics의 보기를](/azure/azure-monitor/platform/view-designer) 참조하세요.
  
### <a name="related-tasks"></a>관련 작업

1. Azure Monitor Log Analytics를 구독한 후에는 Microsoft Teams 룸 보낼 정보를 구문 분석하는 데 필요한 [사용자 지정 필드(지도 사용자 지정 필드에](azure-monitor-deploy.md#Custom_fields) 설명됨)를 만듭니다. 여기에는 로그 항목 이해에 설명된 JSON 스키마 [이해가 포함됩니다](azure-monitor-manage.md#understand-the-log-entries).
    
2. Log Analytics에서 Microsoft Teams 룸 관리 뷰를 개발합니다. [Microsoft Teams 룸 대시보드를 수동으로 만들 수 있습니다](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>개별 Microsoft Teams 룸 요구 사항

Microsoft Teams 룸 키오스크 모드의 컴퓨팅 디바이스에서 실행되는 앱입니다. 모든 Windows 앱과 마찬가지로 Microsoft Teams 룸 앱은 시작 및 하드웨어 오류와 같은 이벤트를 Windows 이벤트 로그에 씁니다. Microsoft Teams 룸 Microsoft Monitor 에이전트를 추가하면 이러한 이벤트를 수집할 수 있습니다. 자세한 내용은 [Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결을](/azure/azure-monitor/platform/agent-windows) 참조하세요.
  
## <a name="ongoing-management"></a>지속적인 관리

Azure Monitor를 사용하여 Microsoft Teams 룸 모니터링하는 동안 Azure Monitor에서 사용하는 이벤트 로그에 포함된 정보를 이해해야 합니다. 이러한 상태 메시지에 대한 자세한 내용은 [로그 항목 이해](azure-monitor-manage.md#understand-the-log-entries) 를 참조하세요.
  
### <a name="related-tasks"></a>관련 작업

- Microsoft Teams 룸 생성된 경고 및 해결 방법 이해([로그 항목 이해](azure-monitor-manage.md#understand-the-log-entries) 섹션 참조)
    
## <a name="see-also"></a>참고 항목

[Azure Monitor를 사용하여 Microsoft Teams 룸 관리 배포](azure-monitor-deploy.md)
  
[Azure Monitor를 사용하여 Microsoft Teams 룸 디바이스 관리](azure-monitor-manage.md)
