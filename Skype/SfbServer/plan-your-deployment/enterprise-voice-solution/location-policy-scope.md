---
title: 비즈니스용 Skype 서버에서 위치 정책 범위 지정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 비즈니스용 Skype Server Enterprise Voice에서 E9-1 배포에 대 한 계획 위치 정책
ms.openlocfilehash: 04eb04733649e2967980e0121d17cf71221f5387
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187644"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 위치 정책 범위 지정
 
비즈니스용 Skype Server Enterprise Voice에서 E9-1 배포에 대 한 계획 위치 정책
  
다른 비즈니스용 Skype 서버 정책과 마찬가지로 위치 정책은 전역, 사이트 및 사용자의 여러 범위 수준에서 할당할 수 있습니다. 그러나 사용자 수준 위치 정책의 범위는 다른 비즈니스용 Skype 서버 정책에 비해 약간 다르게 작동 합니다. 끝점 개체 (예: 사용자 및 공용 지역 전화 연락처 개체)에는 사용자 단위 위치 정책을 적용할 수 있을 뿐만 아니라 비즈니스용 Skype 서버 네트워크 사이트에도 적용할 수 있습니다. 네트워크 사이트는 지리적 위치와 관련 된 클라이언트 서브넷의 그룹 이지만, 전체 중앙 사이트 또는 지사 사이트의 모든 서브넷 일 필요는 없습니다. 네트워크 사이트의 서브넷에 연결 된 클라이언트는 해당 네트워크 사이트에 할당 된 위치 정책을 자동으로 선택 합니다. 사용자 수준 위치 정책이 사용자와 네트워크 사이트에 모두 할당 되는 경우 네트워크 사이트 기반 위치 정책은 사용자별 정책 설정 보다 우선 합니다.
  
각 네트워크 사이트에는 위치 정책이 할당 되며 각 정책에는 서로 다른 PSTN 용도, 알림 Uri 및 전화 회의 Uri 값이 지정 됩니다.
  
> [!NOTE]
> 이 특수 정책 범위 지정 동작이 발생 하는 이유는 한 office 사이트의 풀에 속한 사용자가 다른 사이트를 방문할 때 긴급 통화를 해야 할 때 해당 네트워크 사이트에 적합 한 E9-1-1 통화 라우팅 설정이 어떤 풀이나 사이트에 관계 없이 적용 될 수 있기 때문입니다. ser이 할당 되었습니다. 
  

