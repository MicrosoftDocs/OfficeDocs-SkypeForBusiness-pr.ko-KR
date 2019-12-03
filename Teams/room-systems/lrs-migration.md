---
title: Microsoft 팀 대화방으로 Lync 채팅방 시스템 장치 마이그레이션
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 이 항목에서는 Microsoft 팀 공간 소프트웨어를 사용 하도록 Lync 대화방 시스템 장치를 마이그레이션하는 방법을 알아봅니다.
ms.openlocfilehash: 2a324e426368722cf261554b09298f098644d5ba
ms.sourcegitcommit: 74c06b00ff78dc816a59e6c59e9be87181fc0f3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39669276"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>LRS (Lync 채팅방 System) 장치를 Microsoft 팀 대화방으로 마이그레이션

[2018 년 10 월 9 일에](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)Skype 실 시스템 버전 1 (SRS v1) 소프트웨어가 있는 LRS (Lync 대화방 system) 장치가 지원 종료에 도달 했습니다. 즉, Skype 룸 시스템 v1 소프트웨어는 더 이상 제품 업데이트나 수정을 지원받지 않습니다. Skype 룸 시스템 v1 소프트웨어를 갖춘 Lync 룸 시스템 장치를 사용하는 고객은 해당 장치를 Microsoft Teams 룸으로 업그레이드할 것을 권장합니다.

Microsoft 팀 대화방 소프트웨어는 모든 Microsoft 팀 회의실 지원 장치에서 모임 및 통화를 위한 비즈니스용 Skype 서버 및 온라인 서비스 외에도 Microsoft 팀과 함께 작동 합니다.

Skype 대화방 시스템 v1 소프트웨어 지원이 종료 된 후에도 기존 장치가 계속 작동할 **수 있습니다** . 그러나이 소프트웨어가 수정 프로그램을 릴리스 해야 하는 소프트웨어 버그에 도달 하는 경우에는 지원 되지 않습니다. SRS v1은 향후 Microsoft에서 더 이상 사용 하지 않는 TLS 1.0/1.1를 사용 합니다. [TLS 1.0/1.1의 중단을 준비](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)하는 방법에 대해 자세히 알아볼 수 있습니다. 

## <a name="which-devices-are-affected"></a>어떤 장치가 영향을 받습니까?

이 변경으로 인해 영향을 받는 디바이스 목록은 다음과 같습니다.

- RL의 crestr
- [RL2에서 crestron](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [스마트 실 시스템](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>업그레이드 옵션

Lync 채팅방 시스템을 차세대 Microsoft 팀 대화방으로 업그레이드 하기 위한 여러 옵션이 있습니다.

### <a name="crestron-hardware-trade-in-program"></a>하드웨어 거래 프로그램에서의 crestron

Crestron은 [SR 시스템의 crestron](https://www.crestron.com/products/featured-solutions/crestron-sr) 또는 Lync 채팅방 시스템 고객 (예: 스마트 또는 Polycom LRS)에 대 한 모든 비 crestron를 제공 합니다. 이 [프로그램에](https://support.crestron.com/app/answers/answer_view/a_id/1000220) 대 한 세부 정보 보기 또는 <!-- For details, -->[전자 메일](mailto:lrsupgrade@crestron.com) LRS 지원에 대 한 crestron  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Microsoft 팀 대화방으로 RL2를 업그레이드 하는 crestron

기존 CRESTRON (RL200의 Crestron 함) 고객은 업그레이드 키트를 사용 하 여 RL2를 RL3으로 업그레이드 하는 것이 장치 당 최소 비용으로 인 한 요금으로 업그레이드할 수 있습니다. 이 프로그램에 대 한 세부 정보를 [참조 하세요.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>스마트 실 시스템 업그레이드

스마트 LRS 고객의 경우 하드웨어 거래 관련 프로그램에 대 한 자세한 내용은 Microsoft 팀 대화방으로 업그레이드 하기 위한 솔루션을 제공 하는 방법에도 사용 됩니다. 이 업그레이드는 기술 지원 부서에서 고객에 게 스마트 기술 Inc를 통해 제공 됩니다. 이에 대 한 자세한 내용은 [여기](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)를 참조 하세요.


## <a name="what-should-you-do"></a>무엇을 해야 하나요?

TLS 1.0/1.1에서는 위에 언급 된 업그레이드 옵션을 사용 하 여 Lync 채팅방 시스템 장치를 Microsoft 팀 방에 업데이트 하도록 계획 하는 것이 좋습니다. 또한 기존 장치를 Microsoft 팀 방에 대해 인증 된 새 장치로 바꾸는 것도 고려할 수 있습니다. 자세한 내용은 [방 장치](https://aka.ms/roomdevices) 를 참조 하 고 [Microsoft 팀 방에 대 한 요구 사항을](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)살펴보세요.  


> [!NOTE]
> Microsoft 팀 대화방 소프트웨어는 앱 버전 4.0.64.0를 사용 하 여 2018 년 12 월 14 일의 TLS 1.2 프로토콜을 지원 합니다. 온-프레미스 고객의 경우 TLS 1.2를 통해 Microsoft 팀 방에 대 한 통신을 사용 하도록 설정 하려면 비즈니스용 Skype Server 2015 누적 업데이트 CU9) 또는 비즈니스용 Skype 서버 2019 누적 업데이트 1 (CU1)이 필요 합니다. 클라이언트 변경 내용이 정방향이 고 역방향으로 호환 되는 경우 변경 내용이 비즈니스용 Skype Online 고객에 게 영향을 미치지 않습니다.
