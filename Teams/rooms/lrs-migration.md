---
title: Lync Room System 디바이스를 Microsoft Teams 룸
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 이 항목을 읽고 Lync Room System 디바이스를 마이그레이션하여 Lync Room System 디바이스를 Microsoft Teams 룸 방법을 참조하세요.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: aae146767f66327e5678956a14dfe72d957a8164
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503515"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>LRS(Lync Room System) 디바이스를 Microsoft Teams 룸

SRS(룸 시스템 버전 1) Skype Lync Room System(LRS) 디바이스는 [2018년 10월 9](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)일 지원이 종료되었습니다. 즉, Skype 룸 시스템 v1 소프트웨어는 더 이상 제품 업데이트나 수정을 지원받지 않습니다. Skype 룸 시스템 v1 소프트웨어를 갖춘 Lync 룸 시스템 장치를 사용하는 고객은 해당 장치를 Microsoft Teams 룸으로 업그레이드할 것을 권장합니다.

Microsoft Teams 룸 소프트웨어는 Microsoft Teams 지원되는 모든 디바이스에서 비즈니스용 Skype 서버 및 온라인 서비스 외에도 Microsoft Teams 룸 작동합니다.

Room System v1 소프트웨어 지원이 종료된 후에도 기존 Skype 계속 작동할 수 있습니다. 그러나 이 소프트웨어가 Microsoft에서 수정 사항을 릴리스해야 하는 소프트웨어 버그에 해당하면 지원되지 않습니다. SRS v1은 향후 Microsoft에서 사용되지 않는 TLS 1.0/ 1.1을 사용하게 됩니다. [TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 사용되지 않는 준비에 대해 자세히 알아보실 수 있습니다. 

## <a name="which-devices-are-affected"></a>영향을 받는 디바이스는 무엇입니까?

이 변경의 영향을 받는 디바이스 목록은 다음과 같습니다.

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [SMART Room 시스템](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>업그레이드 옵션

Lync Room Systems를 차세대 시스템으로 업그레이드하기 위한 여러 옵션이 Microsoft Teams 룸.

### <a name="crestron-hardware-trade-in-program"></a>Crestron 하드웨어 Trade-in 프로그램

Crestron은 [Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) 시스템 또는 모든 비 크레스트론 Lync Room System 고객(예: Smart 또는 Polycom LRS)에 해당하는 업그레이드를 제공합니다. 이 프로그램의 자세한 내용은 여기를 참조[하거나](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[메일 주소](mailto:lrsupgrade@crestron.com) Crestron LRS가 지원됩니다.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 업그레이드를 Microsoft Teams 룸

기존 Crestron RL2(Crestron RL200이라고도 하는) 고객은 디바이스당 최소 비용으로 현재 RL2를 RL3으로 업그레이드하는 업그레이드 키트를 획득할 수 있습니다. 이 프로그램의 자세한 내용은 여기를 [참조하세요](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>SMART Room Systems 업그레이드

SMART LRS 고객의 경우 Crestron 하드웨어 거래 프로그램 외에도 SMART는 업그레이드할 솔루션을 제공하기 위해 Microsoft Teams 룸. 이 업그레이드는 SMART Technologies Inc.에서 제품 지원에 따라 고객에게 제공됩니다. 자세한 내용은 여기를 참조 [하세요](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>어떻게 해야 하나요?

위에서 언급한 업그레이드 옵션을 사용하여 TLS 1.0/1.1 사용이 Microsoft Teams 룸 전에 Lync Room System 디바이스를 업데이트하는 것이 좋습니다. 또한 기존 디바이스를 인증된 새 디바이스로 교체하는 것이 Microsoft Teams 룸. 자세한 [내용은 Room 디바이스](https://aka.ms/roomdevices)를 참조하고 요구 사항을 Microsoft Teams 룸 [살펴보기 바랍니다](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  


> [!NOTE]
> Microsoft Teams 룸 소프트웨어는 앱 버전 4.0.64.0을 사용하여 2018년 12월 14일 현재 TLS 1.2 프로토콜을 지원합니다. 프레미스 고객에 대해 TLS 1.2를 통해 통신을 Microsoft Teams 룸 2015 누적 업데이트 9(CU9) 비즈니스용 Skype 서버 2019 누적 업데이트 1(CU1)을 비즈니스용 Skype 서버 필요합니다. 클라이언트 변경 내용이 전달 및 비즈니스용 Skype 변경이 온라인 고객에게 영향을 주지 않습니다.