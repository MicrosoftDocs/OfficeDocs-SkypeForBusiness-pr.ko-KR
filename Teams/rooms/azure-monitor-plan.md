---
title: Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 계획
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 이 문서에서는 비즈니스용 Skype 또는 팀 구현에서 Azure Monitor를 사용 하 여 Microsoft 팀 회의실 장치를 관리 하기 위한 계획 고려 사항에 대해 설명 합니다.
ms.openlocfilehash: 1e5c41866b02a74bee06b472623919f955691dd9
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269132"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 계획
 
 이 문서에서는 Azure Monitor를 사용 하 여 Microsoft 팀 또는 비즈니스용 Skype 구현에서 Microsoft 팀 회의실 장치를 관리 하기 위한 계획 고려 사항을 설명 합니다.
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) 는 시작부터 클라우드에서 설계 된 관리 서비스의 모음입니다. Azure는 온-프레미스 리소스를 배포 및 관리 하는 대신 Azure에서 완전히 호스트 됩니다. 구성은 미미 하 고, 몇 분 내에 문자 그대로 실행할 수 있습니다. 일부 사용자 지정 작업을 사용 하면 개별 룸 시스템에 대 한 시스템 상태 또는 오류에 대 한 실시간 알림을 제공 하 여 Microsoft 팀 회의실 회의 시스템을 관리 하는 데 도움이 될 수 있으며, 수천 개의 Microsoft 팀을 관리 하는 일이 발생할 수 있습니다. 회의실 회의실.
  
이 문서에서는 microsoft 팀 회의실 회의 디바이스의 Azure Monitor 기반 관리를 구현 하는 데 필요한 요구 사항, 디자인/아키텍처 및 구현 모범 사례에 대해 설명 하 고 microsoft 팀 대화방에 대 한 Azure 모니터 구현에 대 한 자세한 문서 링크를 제공 하 고 팀 대화방의 지속적인 모니터링을 위한 중요 참조 정보에 대해 설명 합니다. 
  
## <a name="functional-overview"></a>기능 개요

![Azure 모니터를 사용 하는 Microsoft 팀 회의실 관리 다이어그램](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
콘솔 장치의 Microsoft 팀 대화방 앱은 Windows 이벤트 로그에 이벤트를 기록 합니다. Microsoft Monitoring agent가 설치 된 후에는 해당 정보를 Azure 모니터 서비스에 전달 합니다. 
  
올바르게 구성 되 면 로그 분석은 이벤트 설명에 포함 된 JSON 페이로드를 구문 분석 하 여 각 Microsoft 팀 대화방 시스템이 작동 하는 방식과 감지 되는 결함을 설명 합니다. 
  
Azure 모니터를 사용 하는 관리자는 오프 라인 상태 이거나 앱, 연결 또는 하드웨어 오류와 시스템을 다시 시작 해야 하는지 여부를 알고 있는 Microsoft 팀 대화방 시스템에 대 한 알림을 받을 수 있습니다. 각 시스템 상태는 자주 업데이트 되므로 이러한 알림은 실시간 업데이트와 유사 합니다.
  
## <a name="azure-monitor-requirements"></a>Azure 모니터 요구 사항

Log Analytics 기능을 사용 하려면 Azure Monitor에 대 한 유효한 Azure 구독이 있어야 합니다. 조직에 대 한 구독을 만들려면 [Log Analytics 작업 영역 시작](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) 을 참조 하세요.
  
로그 분석 보기 디자이너를 사용 하는 방법에 대해서는 필요에 따라 숙지 해야 합니다. [로그 분석에서](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) 해당 세부 정보에 대 한 보기를 참조 하세요.
  
### <a name="related-tasks"></a>관련 작업

1. Azure 모니터 로그 분석을 구독 한 후에는 Microsoft 팀 대화방 콘솔에서 전송 되는 정보를 구문 분석 하는 데 필요한 사용자 지정 필드 ( [Map 사용자 지정 필드](azure-monitor-deploy.md#Custom_fields)에 설명 된 대로)를 만듭니다. 여기에는 [로그 항목을 이해](azure-monitor-manage.md#understand-the-log-entries)하는 데 문서화 된 JSON 스키마에 대 한 이해가 포함 됩니다.
    
2. 로그 분석에서 Microsoft 팀 회의실 관리 보기를 개발 합니다. [Import 메서드를 사용 하 여 Microsoft 팀 회의실 대시보드를 만들거나](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) [수동으로 microsoft 팀 대화방 대시보드를 만들](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)수 있습니다.
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>개별 Microsoft 팀 공간 콘솔 요구 사항

각 Microsoft 팀 대화방 콘솔은 키오스크 모드의 Surface Pro 장치에서 실행 되는 앱으로, 일반적으로 장치에서 실행할 수 있는 유일한 앱으로 구성 됩니다. 모든 Windows 앱에서와 마찬가지로 Microsoft 팀 대화방 앱은 시작 및 하드웨어 폴트와 같은 이벤트를 Windows 이벤트 로그에 기록 합니다. Microsoft 팀 대화방 장치에 Microsoft 모니터 에이전트를 추가 하면 이러한 이벤트를 수집할 수 있습니다. (자세한 내용은 [Azure의 Log Analytics 서비스에 Windows 컴퓨터 연결을](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) 참조 하세요.)
  
## <a name="ongoing-management"></a>지속적인 관리

Azure Monitor를 사용 하 여 Microsoft 팀 공간 장치를 관리 하는 동안 Azure Monitor에서 사용 되는 이벤트 로그에 포함 된 정보를 이해 해야 합니다. 이러한 상태 메시지에 대 한 자세한 내용은 [로그 항목 이해](azure-monitor-manage.md#understand-the-log-entries) 를 참조 하세요.
  
### <a name="related-tasks"></a>관련 작업

- Microsoft 팀 대화방에서 생성 된 알림과이를 해결 하는 방법 이해 ( [로그 항목 이해](azure-monitor-manage.md#understand-the-log-entries)섹션 참조)
    
## <a name="see-also"></a>참고 항목

[Azure Monitor를 사용 하 여 Microsoft 팀 공간 관리 배포](azure-monitor-deploy.md)
  
[Azure Monitor를 사용 하 여 Microsoft 팀 회의실 장치 관리](azure-monitor-manage.md)