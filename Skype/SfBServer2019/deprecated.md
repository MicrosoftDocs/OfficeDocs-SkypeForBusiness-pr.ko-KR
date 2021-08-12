---
title: 2019년 6월부터 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 이러한 기능은 2019년 비즈니스용 Skype 서버 제거되었습니다.'
ms.openlocfilehash: 43fa8bae64e65fcba1aaf21c75e06d396d3c47eee8df40cec0db0eb1d5d646eb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282471"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>2019년 6월부터 비즈니스용 Skype 서버

2019년 6월에 더 이상 사용이 불가능해진 기능에 대해 비즈니스용 Skype 서버 대해 자세히 알아보습니다. 비즈니스용 Skype 서버 2019의 새로운 기능에 대한 자세한 내용은 [What's in 비즈니스용 Skype 서버 2019을 참조하십시오.](whats-new.md)

강조하지 않은 일부 기능은 이전 제품 비즈니스용 Skype 서버 호환성을 위해 2019에 포함되어 있습니다.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>2019년 6월에 더 이상 비즈니스용 Skype 서버 기능 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>XMPP Gateways for 비즈니스용 Skype 서버

비즈니스용 Skype 서버 2015 및 그 선행 방법을 사용하면 에지 서버에서 XMPP(Extensible Messaging and Presence Protocol) 프록시를 구성하고 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이를 구성할 수 있습니다. 이 기능은 2019년 8월에 더 이상 비즈니스용 Skype 서버 없습니다.

### <a name="persistent-chat-for-skype-for-business-server"></a>영구 채팅 for 비즈니스용 Skype 서버

영구 채팅 서버는 조직의 여러 사용자가 시간이 지날 때 지속되는 대화방 대화에 참가할 수 있도록 하는 선택적 역할입니다. 영구 채팅은 2019년 8월과 함께 비즈니스용 Skype 서버 없습니다. 이 서버 역할은 코드뿐만 아니라 토폴로지 작성기에서 제거됩니다. 

동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL 미러링 비즈니스용 Skype 서버

SQL 미러링은 2019에서 배포할 수 비즈니스용 Skype 서버 없습니다. 고가용성 및 재해 복구를 제공하기 위한 다른 옵션은 여전히 지원됩니다. 이 중에서 선택해야 합니다. 옵션을 [검토할](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 수 있는 내용은 Plan for high availability and disaster recovery in 비즈니스용 Skype 서버 참조하세요.

### <a name="in-place-upgrades"></a>인플레이스 업그레이드 

전체 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 나란히 업그레이드 및 동시 사용이 지원됩니다. 자세한 내용은 [Migration to 비즈니스용 Skype 서버 2019을](migration/migration-to-skype-for-business-server-2019.md) 참조하십시오.

### <a name="mobility-service-mcx"></a>Mobility Service(Mcx)

레거시 모바일 클라이언트에서 사용하는 Mobility Service 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 이는 이전에 2015년 비즈니스용 Skype 서버 발표된 바 있습니다.

현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. Mcx를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.

자세한 내용은 Plan [for Mobility for 비즈니스용 Skype 서버](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for 비즈니스용 Skype.](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)

## <a name="tools"></a>도구

2019년 10월의 초기 릴리스에서는 다음 도구를 사용할 비즈니스용 Skype 서버 없습니다.

- 비즈니스용 Skype 서버 용량 계획 계산기
- 비즈니스용 Skype 서버 디버깅 도구
- 비즈니스용 Skype 서버 리소스 키트 도구(일부 도구는 제거됨)
    - 통화 파기계
    - 사용자 콘솔 룩업
    - 미지정 번호 공지 마이그레이션

다음 도구는 2019에서 지원되지 비즈니스용 Skype 서버 않습니다.

- 통화 품질 방법론(통화 품질 대시보드는 아미라)
- Microsoft 통화 품질 방법론 Scorecard, v1.5
- 비즈니스용 Skype 서버 2015 계획 도구
- 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구

### <a name="see-also"></a>참고 항목

[2019의 새로운 비즈니스용 Skype 서버](whats-new.md)

[XMPP 페더레이션 마이그레이션](migration/migrating-xmpp-federation.md)
