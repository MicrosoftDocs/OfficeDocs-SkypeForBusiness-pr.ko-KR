---
title: Lync 회의실 시스템 장치를 Microsoft Teams 회의실로 마이그레이션
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Microsoft Teams Room 소프트웨어를 사용하기 위해 Lync 회의실 시스템 장치를 마이그레이션하는 방법을 알아보는 이 항목을 참조하세요.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662623"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>LRS(Lync 회의실 시스템) 장치를 Microsoft Teams 회의실로 마이그레이션

Skype 채팅방 시스템 버전 1(SRS v1) 소프트웨어가 있는 LRS(Lync 채팅방 시스템) 장치는 [2018년 10월 9일](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)지원이 종료되었습니다. 즉, Skype 룸 시스템 v1 소프트웨어는 더 이상 제품 업데이트나 수정을 지원받지 않습니다. Skype 룸 시스템 v1 소프트웨어를 갖춘 Lync 룸 시스템 장치를 사용하는 고객은 해당 장치를 Microsoft Teams 룸으로 업그레이드할 것을 권장합니다.

Microsoft Teams Rooms 소프트웨어는 비즈니스용 Skype 서버 및 온라인 서비스 외에도 Microsoft Teams 회의실 지원 장치에서 모임 및 통화를 할 수 있습니다.

Skype Room  System v1 소프트웨어 지원이 종료된 후에도 기존 장치가 계속 작동할 수 있습니다. 그러나 이 소프트웨어가 Microsoft에서 픽스를 릴리스해야 하는 소프트웨어 버그에 해당하면 지원되지 않습니다. SRS v1은 향후 Microsoft에서 사용되지 않는 TLS 1.0/1.1을 사용하게 됩니다. [TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)사용되지 않는 경우 준비하는 방법을 자세히 배울 수 있습니다. 

## <a name="which-devices-are-affected"></a>어떤 디바이스가 영향을 받나요?

이 변경의 영향을 받는 디바이스 목록은 다음과 같습니다.

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [SMART Room 시스템](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>업그레이드 옵션

Lync 회의실 시스템을 차세대 Microsoft Teams 회의실로 업그레이드하는 여러 옵션이 있습니다.

### <a name="crestron-hardware-trade-in-program"></a>Crestron 하드웨어 거래 프로그램

Crestron은 [Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) 시스템 또는 모든 비 Crestron Lync Room System 고객(예: Smart 또는 Polycom LRS)에 해당하는 업그레이드를 제공합니다. 이 프로그램의 세부 정보는 여기를 [참조하거나](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[전자 메일](mailto:lrsupgrade@crestron.com) Crestron LRS 지원.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2를 Microsoft Teams 회의실로 업그레이드

기존 Crestron RL2(Crestron RL200이라고도 하는) 고객은 디바이스당 최소 비용으로 현재 RL2를 RL3으로 업그레이드하는 업그레이드 키트를 획득할 수 있습니다. 여기에서 이 프로그램의 세부 정보를 [참조하세요.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>SMART Room Systems 업그레이드

SMART LRS 고객의 경우 Crestron 하드웨어 거래 프로그램 외에도 SMART는 Microsoft Teams 회의실로 업그레이드할 수 있는 솔루션을 제공하기 위해 작업 중입니다. 이 업그레이드는 SMART Technologies Inc.에서 제품 지원에 따라 고객에게 제공됩니다. 자세한 내용은 여기를 [참조하세요.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>어떻게 해야 하나요?

위에서 언급한 업그레이드 옵션을 사용하여 TLS 1.0/1.1 사용되지 않는 경우 Lync 회의실 시스템 장치를 Microsoft Teams 회의실로 업데이트하는 것이 좋습니다. 또한 기존 장치를 Microsoft Teams 회의실에 대해 인증된 새 장치로 바꾸는 방을 고려할 수도 있습니다. 자세한 [내용은 회의실](https://aka.ms/roomdevices) 장치를 참조하고 Microsoft Teams 회의실 요구 사항을 [살펴보아야 합니다.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Microsoft Teams Rooms 소프트웨어는 2018년 12월 14일 현재 앱 버전 4.0.64.0을 사용하여 TLS 1.2 프로토콜을 지원하고 있습니다. Microsoft Teams 회의실용 TLS 1.2를 통해 통신할 수 있도록 하려면 비즈니스용 Skype Server 2015 CU9(누적 업데이트 9) 또는 비즈니스용 Skype Server 2019 CU1(누적 업데이트 1)이 필요합니다. 클라이언트 변경 내용이 전달 및 후행 준수로 변경될 경우 비즈니스용 Skype Online 고객에게 영향을 주지 않습니다.
