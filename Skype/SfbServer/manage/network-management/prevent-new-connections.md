---
title: 새 연결 방지
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: 2ac97c784f2286a2231a5f20f54aa00daf646384
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600013"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>서버 유지 관리에 비즈니스용 Skype 서버 새 연결 방지


비즈니스용 Skype 서버 사용하면 사용자에게 서비스가 손실되지 않고도 서버를 오프라인으로 전환할 수 있습니다(예: 소프트웨어 또는 하드웨어 업그레이드 적용).

풀의 서버에 대한 새 연결 또는 통화를 방지하기 위한 옵션을 지정하면 이 옵션을 구현하는 즉시 새 연결 및 호출 수행이 중지됩니다. 이러한 새 연결 및 통화는 풀의 다른 서버를 통해 라우팅됩니다. 새 연결을 방지하는 서버는 기존 연결의 세션을 자연적으로 종료될 때까지 둡니다. 모든 기존 세션이 종료되면 서버를 오프라인으로 설정할 수 있습니다.

프런트 엔드 서버에 대한 새 연결을 방지하는 경우 일부 비즈니스용 Skype 서버 및 서비스는 DNS 부하 분산을 사용하여 제대로 작동하도록 합니다. 풀에서 DNS 부하 분산을 사용하지 않는 경우, 이러한 서비스를 통한 연결이 서버가 새 연결을 방지하는 기간 동안 다른 서버로 다시 라우팅되지 않아 서버가 오프라인으로 설정될 때 일부 세션 및 통화가 중단될 수 있습니다. 이 옵션이 적절하게 작동하도록 하기 위해 DNS 부하 분산을 사용하는 기능은 다음과 같습니다.

  - 도우미

  - 회의 알림 응용 프로그램

  - 응답 그룹 응용 프로그램

  - Announcement application(알림 응용 프로그램)

  - 통화 파크 응용 프로그램

DNS 부하 분산에 대한 자세한 내용은 부하 분산 요구 [사항을 참조하세요.](../../plan-your-deployment/network-requirements/load-balancing.md)

서버가 실행되는 서버의 모든 서비스에 대해 새 연결을 비즈니스용 Skype 서버 개별 서비스에서 새 연결을 비즈니스용 Skype 서버 있습니다. 예를 들어 이 방법은 전체 서버를 종료할 필요가 없는 비즈니스용 Skype 서버 업데이트를 적용해야 하는 상황에서 유용합니다. 특정 서비스에 대한 연결을 방지할 때는 Windows 서비스 목록에서 그룹화되어 표시되는 서비스를 선택해야 합니다. 예를 들어 비즈니스용 Skype 서버 Front-End 서비스 및 모니터링용 데이터 수집 에이전트는 별도의 비즈니스용 Skype 서버 서비스이지만 Windows 서비스 목록에 통합되어 비즈니스용 Skype 서버 프런트 엔드 서비스로 표시됩니다. 비즈니스용 Skype 서버 프런트 엔드 서비스에 대한 새 연결을 방지할 수는 있지만 이러한 두 개의 개별 비즈니스용 Skype 서버 개별적으로 연결하지 못하게 할 수는 없습니다.

> [!IMPORTANT]
> 새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>새 연결을 차단하는 비즈니스용 Skype 서버

1.  Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온합니다.

2.  서비스 스냅인 콘솔을 열고 **시작을** 클릭하고 모든 **프로그램,** 관리 도구를 클릭한 다음 서비스를 **클릭합니다.**

3.  목록에서 새 연결을 방지할 비즈니스용 Skype 서버 Windows 서비스를 두 번 클릭합니다.

4.  속성 대화 상자의 서비스 **상태: 시작함 에서** 일시 중지를 **클릭합니다.**

5.  선택적으로 시작 유형 옆에 **있는** 수동 을 **클릭합니다.**
    
    > [!IMPORTANT]
    > 새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.
