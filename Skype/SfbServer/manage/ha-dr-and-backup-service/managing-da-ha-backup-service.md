---
title: 재해 복구, 고가용성 및 백업 서비스 관리
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 재해 복구 작업 절차 및 연결 된 프런트 엔드 풀의 데이터를 동기화 하는 백업 서비스 유지 관리에 대해 알아봅니다.
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197478"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>비즈니스용 Skype 서버 재해 복구, 고가용성 및 백업 서비스 관리

이 섹션에는 장애 복구 작업에 대 한 절차가 포함 되어 있으며, 연결 된 프런트 엔드 풀의 데이터를 동기화 하는 백업 서비스를 유지 관리 하는 방법에 대해 설명 합니다.

재난 복구 절차 (장애 조치와 장애 복구)는 모두 수동입니다. 재해가 발생 하는 경우 관리자가 장애 조치 절차를 수동으로 호출 해야 합니다. 풀이 복구 된 후에도 장애 복구에 적용 됩니다.

이 섹션의 재난 복구 절차에서는 다음을 가정 합니다.

  - 고가용성 [및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)에 설명 된 바와 같이 쌍으로 이루어진 프런트 엔드 풀을 여러 사이트에 배치 하는 배포를 사용할 수 있습니다. 동기화를 유지 하기 위해이 쌍의 풀에서 백업 서비스를 실행 하 고 있습니다.

  - 중앙 관리 저장소가 풀에서 호스트 되는 경우 두 연결 된 풀에 설치 되 고 실행 되며, 활성 마스터를 호스트 하는 풀 중 하나를 사용 하 고 대기를 호스팅하는 다른 풀에 연결 됩니다.

> [!IMPORTANT]
> 다음 절차에서 *poolfqdn* 매개 변수는 영향을 받는 사용자가 리디렉션되는 풀이 아닌 재해의 영향을 받는 풀의 FQDN을 나타냅니다. 동일한 영향을 받는 사용자 집합의 경우 장애 조치 및 장애 복구 cmdlet (즉, 장애 조치 전에 사용자를 먼저 홈으로 설정한 풀)에서 동일한 풀을 참조 합니다.<BR><br>예를 들어 풀 P1에 속한 모든 사용자가 백업 풀 (P2)로 장애 조치 되는 경우를 가정해 보겠습니다. 관리자가 현재 P2에서 서비스를 제공 하는 모든 사용자를 P1에서 처리 하려는 경우 관리자는 다음 단계를 수행 해야 합니다. 
> <OL>
> <LI>
> <P>장애 복구 cmdlet을 사용 하 여 P1에서 원래 홈으로 설정 된 모든 사용자를 P2에서 P1으로 다시 복구 합니다. 이 경우 *Poolfqdn* 은 P1's fqdn입니다.</P>
> <LI>
> <P>P2에 원래 있는 모든 사용자가 장애 조치 cmdlet을 사용 하 여 P1으로 장애 조치 합니다. 이 경우 PoolFQDN은 P2's FQDN입니다.</P>
> <LI>
> <P>나중에 관리자가 p2 사용자를 P2로 다시 장애 복구 하려는 경우 PoolFQDN은 P2's FQDN입니다.</P></LI></OL><br>풀 무결성을 유지 하려면 위의 1 단계를 2 단계 전에 수행 해야 합니다. 1 단계 전에 2 단계를 수행 하면 2 단계 cmdlet이 실패 합니다.


## <a name="see-also"></a>참고 항목

[고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
