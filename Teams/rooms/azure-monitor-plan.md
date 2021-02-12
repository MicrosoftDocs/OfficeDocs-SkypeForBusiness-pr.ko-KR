---
title: Azure Monitor를 사용하여 Microsoft Teams 회의실 관리 계획
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 이 문서에서는 Azure Monitor를 사용하여 비즈니스용 Skype 또는 Teams 구현에서 Microsoft Teams 회의실 장치를 관리하기 위한 계획 고려 사항을 설명합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 16a962d7414407cf5f2f5734b7a2f39a56f7d281
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137608"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Azure Monitor를 사용하여 Microsoft Teams 회의실 관리 계획
 
 이 문서에서는 Azure Monitor를 사용하여 Microsoft Teams 또는 비즈니스용 Skype 구현에서 Microsoft Teams 회의실 디바이스를 관리하기 위한 계획 고려 사항을 설명합니다.
  
[Azure Monitor는](https://docs.microsoft.com/azure/azure-monitor/overview) 시작부터 클라우드에서 디자인된 관리 서비스의 컬렉션입니다. Azure Monitor 구성 요소는 전적으로 Azure에서 호스팅되는 대신, 모든 리소스를 배포하고 관리하는 대신에 Azure에서 호스트됩니다. 구성은 최소한으로, 몇 분 만에 문자 그대로 실행될 수 있습니다. 일부 사용자 지정 작업을 통해 개별 회의실 시스템에 대한 시스템 상태 또는 오류에 대한 실시간 알림을 제공하여 Microsoft Teams 회의실 회의 시스템을 관리하는 데 도움이 될 수 있으며, 잠재적으로 수천 개의 Microsoft Teams 회의실 회의실을 관리하기 위해 확장할 수 있습니다.
  
이 문서에서는 Microsoft Teams 회의실 회의 디바이스의 Azure Monitor 기반 관리를 구현하는 데 필요한 요구 사항, 디자인/아키텍처 및 구현 모범 사례를 설명하고 Microsoft Teams 회의실용 Azure Monitor 구현에 대한 자세한 문서와 Microsoft Teams 회의실의 지속적인 모니터링을 위한 중요한 참조 정보에 대한 링크를 제공합니다. 
  
## <a name="functional-overview"></a>기능 개요

![Azure Monitor를 사용한 Microsoft Teams 회의실 관리 다이어그램](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
콘솔 장치의 Microsoft Teams 회의실 앱은 Windows 이벤트 로그에 이벤트를 기록합니다. Microsoft Monitoring Agent가 설치되면 Azure Monitor 서비스에 정보를 전달합니다. 
  
제대로 구성되면 Log Analytics는 이벤트 설명에 포함된 JSON 페이로드를 구문 분석하여 각 Microsoft Teams 회의실 시스템이 어떻게 작동하고 어떤 오류가 감지되었는지를 기술합니다. 
  
Azure Monitor를 사용하는 관리자는 오프라인 상태이거나 앱, 연결 또는 하드웨어 오류가 발생하는 Microsoft Teams 회의실 시스템에 대한 알림을 받을 수 있을 뿐만 아니라 시스템을 다시 시작해야 하는지 알 수 있습니다. 각 시스템 상태는 자주 업데이트됩니다. 따라서 이러한 알림은 실시간 업데이트에 가깝습니다.
  
## <a name="azure-monitor-requirements"></a>Azure Monitor 요구 사항

Log Analytics 기능을 사용하려면 Azure Monitor에 대한 유효한 Azure 구독이 있어야 합니다. Log [Analytics 작업](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 영역 시작을 참조하여 조직에 대한 구독을 만드십시오.
  
Log Analytics 뷰 디자이너를 사용하는 방법에 대해 필요한 경우 익숙해지세요. 자세한 [내용은 Log Analytics의](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) 보기를 참조하세요.
  
### <a name="related-tasks"></a>관련 작업

1. Azure Monitor Log Analytics를 구독한 후 Microsoft [](azure-monitor-deploy.md#Custom_fields)Teams 회의실 콘솔에서 보낼 정보를 구문 분석하는 데 필요한 사용자 지정 필드(맵 사용자 지정 필드에 설명)를 생성합니다. 여기에는 로그 항목 이해에 설명된 JSON [스마마 이해가 포함됩니다.](azure-monitor-manage.md#understand-the-log-entries)
    
2. Log Analytics에서 Microsoft Teams 회의실 관리 보기를 개발합니다. 가져오기 방법을 사용하여 [Microsoft Teams 회의실](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) 대시보드를 만들거나 Microsoft Teams 회의실 대시보드를 수동으로 만들 수 [있습니다.](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>개별 Microsoft Teams 회의실 콘솔 요구 사항

각 Microsoft Teams 회의실 콘솔은 키오스크 모드의 Surface Pro 장치에서 실행되는 앱입니다(일반적으로 장치에서 실행할 수 있는 유일한 앱으로 구성). Windows 앱과 마찬가지로 Microsoft Teams Rooms 앱은 Windows 이벤트 로그에 시작 및 하드웨어 오류와 같은 이벤트를 작성합니다. Microsoft Teams 회의실 장치에 Microsoft Monitor 에이전트를 추가하면 이러한 이벤트를 수집할 수 있습니다. (자세한 [내용은 Azure의 Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) 서비스에 Windows 컴퓨터 연결 참조)
  
## <a name="ongoing-management"></a>지속적인 관리

Azure Monitor를 사용하여 Microsoft Teams Rooms 디바이스를 관리하는 동안 Azure Monitor에서 사용하는 이벤트 로그에 포함된 정보를 이해해야 합니다. 이러한 [상태 메시지에 대한](azure-monitor-manage.md#understand-the-log-entries) 자세한 내용은 로그 항목 이해를 참조합니다.
  
### <a name="related-tasks"></a>관련 작업

- Microsoft Teams 회의실에서 생성된 경고 및 이를 해결하는 방법을 이해합니다(로그 항목 이해 섹션 [참조).](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>참고 항목

[Azure Monitor를 사용하여 Microsoft Teams 회의실 관리 배포](azure-monitor-deploy.md)
  
[Azure Monitor를 사용하여 Microsoft Teams 회의실 디바이스 관리](azure-monitor-manage.md)