---
title: Branch Office Appliance 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
ROBOTS: NOINDEX, NOFOLLOW
description: 기존 Survivable Branch 기기 또는 Survivable Branch 서버에 대 한 설정을 편집 하려면 다음 섹션이 표시 됩니다.
ms.openlocfilehash: bcd1022c964a252ca08d4a8c000b224f61c42763
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196475"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Branch Office Appliance 일반 설정 확장기

기존 Survivable Branch 기기 또는 Survivable Branch 서버에 대 한 설정을 편집 하려면 다음 섹션이 표시 됩니다.

- 일반 설정

- 탄성 설정

- 중재 서버 설정


Survivable Branch 기기 또는 Survivable Branch 서버의 경우 다음과 같은 항목이 표시 됩니다.

### <a name="general-settings"></a>일반 설정

Survivable Branch 기기 또는 Survivable Branch 서버의 FQDN (정규화 된 도메인 이름)입니다. 값을 변경하려면 서버의 FQDN을 편집합니다. 새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.

**구성된 모든 IP 주소 사용** 또는 **선택한 IP 주소로 서비스 사용 제한**을 선택할 수 있습니다. **서비스를 정의된 IP 주소로 제한**하도록 선택하면 사용자는 서버에서 공중 전화망(PSTN) 게이트웨이를 제외한 모든 통신에 사용할 기본 IP 주소를 정의합니다. PSTN에 사용할 별도의 IP 주소를 정의할 수 있습니다.

**연결**에서는 다음을 편집하거나 지정할 수 있습니다.

- 보관 서버 연결을 선택 하 여 보관 서버를 Survivable Branch 기기 또는 Survivable Branch 서버와 연결할 수 있습니다. 드롭다운 목록에서 서버를 선택 하 여 이미 정의 된 보관 서버에서 선택 하거나 **새로 만들기** 를 클릭 하 여 새 보관 서버를 지정할 수 있습니다.

    > [!IMPORTANT]
    > 새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.

- 모니터링 서버 연결을 선택 하 여 모니터링 서버를 Survivable Branch 기기 또는 Survivable Branch 서버와 연결할 수 있습니다. 드롭다운 목록에서 서버를 선택 하 여 이미 정의 된 모니터링 서버에서 선택 하거나 **새로 만들기** 를 클릭 하 여 새 모니터링 서버를 지정할 수 있습니다.

- Edge 풀 연결을 선택 하 여 Edge 서버 또는 풀을 Survivable Branch 기기 또는 Survivable Branch 서버와 연결할 수 있습니다. 드롭다운 목록에 있는 이미 정의된 에지 서버 또는 풀에서 서버를 선택하거나 **새로 만들기**를 클릭하여 새 에지 서버 또는 풀을 지정할 수 있습니다.

### <a name="resiliency"></a>탄성

탄성은 등록자 풀에 대해 고가용성을 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 오류가 발생한 시스템에 따라서는 사용자의 기능이 축소될 수 있습니다.

드롭다운 목록에서 Survivable Branch 기기 또는 Survivable Branch 서버의 백업 등록 기관 역할을 하는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 선택 합니다. 장애 조치(failover) 및 대체 시간 간격을 설정하도록 선택할 수도 있습니다. 장애 조치 및 대체 시간 간격(초)을 설정하면 실패한 등록자를 자동으로 감지하고 대체 시간 동안 기본 등록자가 백업되는지 자동으로 확인하므로 등록자 프로세스를 계속 수행할 수 있습니다.

> [!IMPORTANT]
> 실패 검색 및 대체 간격을 정의할 경우, 등록자가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 수행되지 않도록 충분한 간격을 입력해야 합니다. 풀이나 서버를 로드하는 시간에 따라 기본 등록자가 잠깐 동안 응답하지 않을 수도 있습니다. Survivable Branch 기기 또는 사이트의 Survivable Branch 서버에 대 한 기본값 (프런트 엔드 서버)은 장애 조치 및 대체에 240 초와 120 초입니다.

### <a name="mediation-server"></a>중재 서버

**중재 서버**에 대해 다음을 지정할 수 있습니다.

**Collocated 중재 서버를 사용 하도록 설정** 하는 확인란은 Survivable branch 기기 또는 Survivable branch 서버에서 사용할 수 없습니다. 중재 서버는 Collocated입니다.

풀 서버에서 TLS(전송 계층 보안)에 대한 수신 대기 포트를 정의합니다. 기본적으로 이 포트는 5067입니다. **TCP 포트 사용**을 선택하면 배치된 중재 서버의 TCP 포트를 정의해야 합니다. 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 PSTN 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.

Collocated 중재 서버와 연결 된 PSTN 게이트웨이를 정의 합니다. 이미 게이트웨이를 정의한 경우 중재 서버와 연결 하는 데 사용할 수 있습니다. 게이트웨이를 정의하지 않았지만 정의할 수 있는 경우 **새로 만들기**를 선택할 수 있습니다. 이 중재 서버에 대해 이미 구성 된 게이트웨이를 제거할 수도 있습니다. 게이트웨이를 선택한 다음 **제거**를 클릭합니다.

중재 서버와 연결 된 게이트웨이가 두 개 이상 있는 경우 연결 된 첫 번째 게이트웨이가 기본 게이트웨이가 됩니다. 기본 게이트웨이로 다른 게이트웨이를 선택해야 하는 경우 기본값으로 설정할 게이트웨이를 선택하고 **기본값으로 설정**을 클릭합니다.


Survivable Branch 기기 또는 Survivable Branch 서버에 대 한 설정을 정의 하 고 구성 하는 방법에 대 한 자세한 내용은 [지점 사이트 복구 솔루션](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)을 참조 하세요.


