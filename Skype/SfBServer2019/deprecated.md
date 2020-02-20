---
title: 비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않는 기능
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 이러한 기능은 비즈니스용 Skype 서버 2019에서 제거 되었습니다.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125221"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않는 기능

비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않는 기능에 대해 알아봅니다. 비즈니스용 Skype 서버 2019의 새로운 기능에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2019의 내용을](whats-new.md)참조 하세요.

이전 제품 버전과의 호환성을 위해 비즈니스용 Skype 서버 2019에는 몇 가지 강조 표시 된 기능이 포함 되어 있습니다.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019에서 더 이상 사용 되지 않는 기능 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 XMPP 게이트웨이

비즈니스용 Skype 서버 2015 및 해당 선행 작업을 통해 Edge 서버 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서 XMPP (Extensible Messaging and 현재 상태 프로토콜) 프록시를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019에서는이 기능을 더 이상 사용할 수 없습니다.

### <a name="persistent-chat-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 영구 채팅

영구 채팅 서버는 조직의 여러 사용자가 시간이 지남에 따라 지속 되는 대화방 대화에 참가할 수 있도록 하는 선택적 역할입니다. 영구 채팅은 비즈니스용 Skype 서버 2019와 함께 배포할 수 없습니다. 이 서버 역할은 코드 뿐 아니라 토폴로지 작성기 에서도 제거 됩니다. 

팀 에서도 동일한 기능을 사용할 수 있습니다. 자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참조 하세요.

### <a name="sql-mirroring-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 SQL 미러링

SQL 미러링은 비즈니스용 Skype 서버 2019와 함께 배포할 수 없습니다. 고가용성 및 재해 복구를 제공 하는 다른 옵션은 여전히 지원 되며, 이들 중에서 하나를 선택 해야 합니다. 옵션을 검토 하려면 [비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 을 참조 하세요.

### <a name="in-place-upgrades"></a>인플레이스 업그레이드 

현재 위치 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있었지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다. Side-by-side 업그레이드 및 coexistance 지원 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2019로 마이그레이션을](migration/migration-to-skype-for-business-server-2019.md) 참조 하세요.

### <a name="mobility-service-mcx"></a>모바일 서비스 (Mcx)

레거시 모바일 클라이언트에서 사용 되는 모바일 서비스 지원을 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 이는 이전에 비즈니스용 Skype 서버 2015에서 발표 되었습니다.

현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다. Mcx를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.

자세한 내용은 비즈니스용 Skype에 대 한 [비즈니스용 Skype 서버](../SfbServer/plan-your-deployment/mobility.md) 및 [모바일 클라이언트 기능 비교](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)계획을 참조 하세요.

## <a name="tools"></a>도구

다음 도구는 비즈니스용 Skype 서버 2019의 초기 릴리스에서는 사용할 수 없습니다.

- 비즈니스용 Skype 서버 용량 계획 계산기
- 비즈니스용 Skype 서버 디버깅 도구
- 비즈니스용 Skype 서버 리소스 키트 도구 (일부 도구는 제거 됨)
    - 통화 Parkometer
    - 조회 사용자 콘솔
    - 할당 되지 않은 번호 알림 마이그레이션

다음 도구는 비즈니스용 Skype 서버 2019에서 지원 되지 않습니다.

- 통화 품질 방법론 (통화 품질 대시보드 아님)
- Microsoft 통화 품질 방법론 성과 기록표, v 1.5
- 비즈니스용 Skype 서버 2015 계획 도구
- 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구

### <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2019의 새로운 기능](whats-new.md)

[XMPP 페더레이션 마이그레이션](migration/migrating-xmpp-federation.md)
