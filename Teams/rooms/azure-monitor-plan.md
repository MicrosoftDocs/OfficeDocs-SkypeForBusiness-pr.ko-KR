---
title: Azure monitor를 Microsoft Teams 룸 모니터링 계획
ms.author: czawideh
author: cazawideh
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
description: 이 문서에서는 Azure Monitor를 사용하여 사용자 Microsoft Teams 룸 구현의 Microsoft Teams 룸 모니터링하기 위한 비즈니스용 Skype Teams 설명합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 510f249ea4aef78b898294db0a2c3fbeef8fc283
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504125"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>Azure monitor를 Microsoft Teams 룸 모니터링 계획
 
 이 문서에서는 Azure Monitor를 사용하여 사용자 Microsoft Teams 룸 디바이스를 관리하기 위한 계획 Microsoft Teams 비즈니스용 Skype 설명합니다.

> [!NOTE]
> 관리 센터[를 사용하여](../alerts/device-health-status.md) Teams 룸 상태 모니터링을 Teams 수 있습니다.

[Azure Monitor](/azure/azure-monitor/overview) 는 시작부터 클라우드에서 디자인된 모니터링 서비스의 컬렉션입니다. Azure Monitor 구성 요소는 전적으로 Azure에서 호스팅됩니다. 구성은 최소화되어 있으며 몇 분 만에 실행될 수 있습니다. 일부 사용자 지정 작업을 통해 개별 Microsoft Teams 룸 시스템 상태 또는 오류 알림을 제공하여 모니터링에 도움이 될 수 있으며 수천 개의 시스템 관리로 확장할 수 Microsoft Teams 룸.
  
이 문서에서는 Azure Monitor 기반 모니터링을 구현하는 데 필요한 요구 사항, 디자인/아키텍처 및 구현 모범 사례에 Microsoft Teams 룸. 또한 Azure Monitor for Microsoft Teams 룸 회의실의 지속적인 모니터링을 위한 중요한 참조 정보를 구현하는 Microsoft Teams 룸 링크가 제공됩니다.
  
## <a name="functional-overview"></a>기능 개요

![Azure monitor를 Microsoft Teams 룸 관리 다이어그램을 참조하세요.](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Microsoft Teams 룸 앱은 이벤트 로그에 Windows 기록합니다. Microsoft Monitoring 에이전트가 설치되면 Azure Monitor 서비스에 정보를 전달합니다.
  
제대로 구성되면 Log Analytics는 이벤트 설명에 포함된 JSON 페이로드를 구문 분석하여 Microsoft Teams 룸 작동 방식 및 감지된 오류에 대해 설명합니다.
  
Azure Monitor를 사용하는 관리자는 오프라인 상태이거나 Microsoft Teams 룸, 연결 또는 하드웨어 오류가 발생하는 경우 알림을 받을 수 있을 뿐만 아니라 시스템을 다시 시작해야 하는지 알 수 있습니다. 각 시스템 상태가 자주 업데이트되어 이러한 알림은 실시간 업데이트에 가깝습니다.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor 요구 사항

Log Analytics 기능을 사용하려면 Azure Monitor에 대한 유효한 Azure 구독이 있어야 합니다. Log [Analytics](/azure/azure-monitor/learn/quick-create-workspace) 작업 영역 시작을 참조하여 조직의 구독을 만들 수 있습니다.
  
Log Analytics 뷰 디자이너를 사용하는 방법에 대해 익숙해 야 합니다. 자세한 [내용은 Log Analytics](/azure/azure-monitor/platform/view-designer) 의 보기를 참조하세요.
  
### <a name="related-tasks"></a>관련 작업

1. Azure Monitor Log Analytics를 구독한 후 사용자 지정 필드(지도 사용자 지정 필드[](azure-monitor-deploy.md#Custom_fields)에 설명된 바와 같이)를 만들어 사용자 지정 필드에서 전송되는 정보를 구문 분석하는 데 Microsoft Teams 룸. 여기에는 로그 항목 이해에 설명된 JSON의척도 [이해가 포함됩니다](azure-monitor-manage.md#understand-the-log-entries).
    
2. Log Analytics에서 Microsoft Teams 룸 관리 보기를 개발합니다. 수동으로 [대시보드를 Microsoft Teams 룸 수 있습니다](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>개별 Microsoft Teams 룸 요구 사항

Microsoft Teams 룸 키오스크 모드에서 계산 장치에서 실행되는 앱입니다. 모든 Windows 앱과 마찬가지로 Microsoft Teams 룸 이벤트 로그에 시작 및 하드웨어 오류와 같은 이벤트를 Windows 작성합니다. Microsoft Monitor 에이전트를 Microsoft Teams 룸 이러한 이벤트를 수집할 수 있습니다. (자세한 [커넥트 Windows Azure의 Log Analytics 서비스에](/azure/azure-monitor/platform/agent-windows) 컴퓨터 연결 확인을 참조하세요.)
  
## <a name="ongoing-management"></a>진행 중 관리

Azure Monitor를 사용하여 사용자 Microsoft Teams 룸 Azure Monitor에서 사용하는 이벤트 로그에 포함된 정보를 이해해야 합니다. 이러한 [상태 메시지에](azure-monitor-manage.md#understand-the-log-entries) 대한 자세한 내용은 로그 항목 이해를 참조합니다.
  
### <a name="related-tasks"></a>관련 작업

- 경고가 생성한 경고를 Microsoft Teams 룸 해결 방법 이해(로그 항목 이해 섹션 [참조](azure-monitor-manage.md#understand-the-log-entries))
    
## <a name="see-also"></a>참고 항목

[Azure monitor를 Microsoft Teams 룸 관리 배포](azure-monitor-deploy.md)
  
[Azure monitor를 Microsoft Teams 룸 디바이스 관리](azure-monitor-manage.md)
