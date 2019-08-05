---
title: 새 연결 방지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188550"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>비즈니스용 Skype 서버 유지 관리에 대 한 새 연결 방지


비즈니스용 Skype Server를 통해 사용자에 게 서비스를 손실 하지 않고 서버를 오프 라인으로 전환 (예: 소프트웨어 또는 하드웨어 업그레이드 적용) 할 수 있습니다.

풀에서 서버에 대 한 새 연결이 나 호출을 방지 하는 옵션을 지정 하는 경우,이 옵션을 구현 하는 즉시 새 연결 및 통화가 중지 됩니다. 이러한 새 연결 및 통화는 풀의 다른 서버를 통해 라우팅됩니다. 새 연결을 차단 하는 서버는 기존 연결의 세션이 자연스럽 게 끝날 때까지 계속 진행할 수 있습니다. 모든 기존 세션이 종료 되 면 서버를 오프 라인 상태로 전환할 준비가 된 것입니다.

프런트 엔드 서버에 대 한 새 연결을 차단 하는 경우 일부 비즈니스용 Skype 서버 기능 및 서비스가 DNS 로드 균형 조정에 의존 하 여 제대로 작동 하는지 확인 합니다. 풀에서 DNS 부하 분산을 사용 하지 않는 경우 서버에서 새 연결을 차단 하는 기간 동안 이러한 서비스를 통한 연결이 다른 서버로 다시 라우팅되지 않을 수 있으며, 따라서 서버가 오프 라인 상태가 되 면 일부 세션 및 호출이 발생할 수 있습니다. 되었습니다. 이 옵션이 올바르게 작동 하는지 확인 하기 위해 DNS 로드 균형 조정에 의존 하는 기능은 다음과 같습니다.

  - 리소스만

  - 회의 알림 신청

  - 응답 그룹 응용 프로그램

  - 알림 신청

  - 통화 공원 응용 프로그램

DNS 부하 분산에 대 한 자세한 내용은 [부하 분산 요구 사항을](../../plan-your-deployment/network-requirements/load-balancing.md)참조 하세요.

비즈니스용 Skype Server를 실행 하는 서버에 있는 모든 서비스에 대해 새 연결을 방지 하는 것 외에, 개별 비즈니스용 Skype Server 서비스에 대 한 새로운 연결을 막을 수도 있습니다. 예를 들어이 방법은 전체 서버를 종료할 필요가 없는 비즈니스용 Skype 서버 업데이트를 적용 해야 하는 상황에 유용 합니다. 한 서비스에 대 한 연결을 방지 하려면 서비스가 그룹화 되 고 서비스의 Windows 목록에 표시 되는 서비스를 선택 해야 합니다. 예를 들어 비즈니스용 Skype Server 프런트 엔드 서비스 및 모니터링에 대 한 데이터 수집 에이전트는 별도의 비즈니스용 Skype Server services 이지만 Windows 서비스 목록에서 통합 되어 비즈니스용 Skype 서버 프런트 엔드로 표시 됩니다. services. 비즈니스용 Skype Server 프런트 엔드 서비스에 대 한 새 연결을 막을 수는 있지만,이 두 가지 기본 비즈니스용 Skype Server 서비스에 대 한 새 연결을 개별적으로 막을 수는 없습니다.

> [!IMPORTANT]
> 새 연결을 방지 하도록 서버를 설정한 다음 서버를 다시 시작 하면 기본적으로 서버가 시작 된 후 새 연결을 즉시 수락 하 게 됩니다. 이를 방지 하려면 서버를 다시 시작 하기 전에 서버를 일시 중지 했다가 수동으로 다시 시작 하도록 설정 합니다.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 새 연결을 방지 하려면

1.  로컬 컴퓨터에 관리자 그룹의 구성원으로 로그온 합니다.

2.  **시작**을 클릭 하 고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **서비스**를 클릭 하 여 서비스 스냅인 콘솔을 엽니다.

3.  목록에서 새 연결을 방지 하려는 비즈니스용 Skype 서버 Windows 서비스를 두 번 클릭 합니다.

4.  속성 대화 상자의 **서비스 상태: 시작**에서 **일시 중지**를 클릭 합니다.

5.  또는 **시작 유형**옆에 있는 **수동**을 클릭 합니다 (선택 사항).
    
    > [!IMPORTANT]
    > 새 연결을 방지 하도록 서버를 설정한 다음 서버를 다시 시작 하면 기본적으로 서버가 시작 된 후 새 연결을 즉시 수락 하 게 됩니다. 이를 방지 하려면 서버를 다시 시작 하기 전에 서버를 일시 중지 했다가 수동으로 다시 시작 하도록 설정 합니다.
