---
title: Microsoft Teams 룸 참조
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 참조 자료
f1keywords: ''
ms.openlocfilehash: e75742cb209018030ca9d6600c518e210b396386
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268413"
---
# <a name="managing-room-software-stack"></a>회의실 소프트웨어 스택 관리  
모든 방에서 소프트웨어 스택의 여러 부분이 함께 작동하여 환경을 제공합니다. 대략적으로 다음과 같이 요약할 수 있습니다. 

![소프트웨어 스택 요약 스크린샷](../media/update-management-006.jpg)

모든 회의실에서 매일 긍정적인 모임 환경을 보장하려면 각 회의실에서 실행되는 **모든 소프트웨어를 표준화** 하고 구성에 따라 회의실에서 수정 사항을 롤아웃하는 것이 중요합니다. 또한 고객이 발생할 수 있는 문제를 실제로 해결하는지 확인하거나 기능을 미리 보고 조직이 변경에 대비할 수 있도록 보류 중인 수정에 대한 신뢰를 얻기 위해 자체 유효성 검사 프로세스를 설정하는 것이 일반적입니다.  

Microsoft Teams 룸 관리형 서비스는 업데이트 또는 업데이트 문제 해결에 대해 걱정할 필요가 없도록 위의 모든 작업을 처리합니다. 이 섹션에서는 관리되는 소프트웨어 업데이트의 작동 방식을 설명합니다.  

## <a name="managing-to-a-good-state"></a>양수 상태로 관리 
주요 목표는 조직에서 회의실을 계속 실행하고 사용할 수 있도록 하는 것입니다. Managed Services 전문가는 프로덕션 룸에 업데이트를 큐레이팅, 유효성 검사 및 배포하기 위해 지속적으로 사용자 대신 작업하고 있습니다. 경우에 따라 새 기능 및 릴리스가 출시되기 전에 유효성을 검사할 때 객실 상태보다 우선 순위를 지정한다는 의미일 수 있습니다.

가장 중요한 것은 이러한 업데이트의 세부 정보를 알아보고 직접 유효성을 검사하기 위해 시간을 투자하는 것에 대해 걱정할 필요가 없다는 것을 의미합니다. 특정 업데이트 및 특정 회의실에 문제가 있는 경우 문제를 해결하고 해결하기 위해 귀하와 협력할 것입니다.  

따라서 업데이트를 롤아웃하는 프로세스는 다음으로 세분화될 수 있습니다.

- Managed Services 팀은 업데이트를 사전에 식별하고, 유효성을 검사한 다음, 릴리스를 위해 사용자 환경으로 승격합니다.
- 회의실에 배달되는 업데이트 충돌 및 상호 작용을 방지하기 위해 주문된 다음, 정기적인 운영 시간을 방지하기 위해 예약됩니다.
- 링 시스템은 레그워크를 수행하지 않고도 방에 적용되는 업데이트를 계속 인식할 수 있는 기능을 제공합니다.
- Managed Services는 업데이트를 모니터링하고 해당 회의실 운영 센터에 문제를 후속 조치하고 문제를 해결하기 위해 귀하와 협력하도록 자동으로 경고합니다.
