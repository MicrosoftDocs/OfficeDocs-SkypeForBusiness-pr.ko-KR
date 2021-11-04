---
title: Branch Office Appliance 일반 설정 확장기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 다음 섹션에서 기존 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 설정을 편집할 수 있습니다.
ms.openlocfilehash: 97bd7ad5c0df11d26507824a28aee54ed3841038
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768846"
---
# <a name="branch-office-appliance-general-settings-expander"></a>Branch Office Appliance 일반 설정 확장기

다음 섹션에서 기존 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 설정을 편집할 수 있습니다.

- 일반 설정

- 복구 설정

- 중재 서버 설정



SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 다음 항목이 표시됩니다.

## <a name="general-settings"></a>일반 설정

SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 FQDN(정규화된 도메인 이름). 값을 변경하려면 서버의 FQDN을 편집합니다. 새 값과 일치하는 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.

**구성된 모든 IP 주소 사용** 또는 **선택한 IP 주소로 서비스 사용 제한** 을 선택할 수 있습니다. **서비스를 정의된 IP 주소로 제한** 하도록 선택하면 사용자는 서버에서 공중 전화망(PSTN) 게이트웨이를 제외한 모든 통신에 사용할 기본 IP 주소를 정의합니다. PSTN에 사용할 별도의 IP 주소를 정의할 수 있습니다.

**연결** 에서는 다음을 편집하거나 지정할 수 있습니다.

- 보관 서버를 연결하면 보관 서버를 Survivable Branch Appliance 또는 Survivable Branch Server와 연결하기로 선택할 수 있습니다. 드롭다운 목록에서 이미 정의된 보관 서버에서 서버를 선택하거나 새로 고치를 클릭하여  새 보관 서버를 지정할 수 있습니다.

    > [!IMPORTANT]
    > 새로 정의된 토폴로지를 게시하려면 지정하는 서버가 존재하고 도메인에 가입되어 있어야 합니다.

- 모니터링 서버 연결에서는 모니터링 서버를 Survivable Branch Appliance 또는 Survivable Branch Server와 연결하기로 선택할 수 있습니다. 드롭다운 목록에서 이미 정의된 모니터링 서버에서 서버를 선택하거나 새로 추가를  클릭하여 새 모니터링 서버를 지정할 수 있습니다.

- 에지 풀을 연결하면 에지 서버 또는 풀을 Survivable Branch Appliance 또는 Survivable Branch Server와 연결하기로 선택할 수 있습니다. 드롭다운 목록에 있는 이미 정의된 에지 서버 또는 풀에서 서버를 선택하거나 **새로 만들기** 를 클릭하여 새 에지 서버 또는 풀을 지정할 수 있습니다.

## <a name="resiliency"></a>탄력성

탄성은 등록자 풀에 대해 고가용성을 제공합니다. 백업 등록자를 제공하는 경우 기본 등록자에 오류가 발생하면 백업 등록자가 실패한 등록자 대신 작업을 수행하므로 사용자가 로그온 및 통신할 수 있습니다. 기본 등록자와 함께 오류가 발생한 시스템에 따라서는 사용자의 기능이 축소될 수 있습니다.

드롭다운 목록에서 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 분기 서버의 백업 등록자 역할을 할 프런트 엔드 서버를 선택합니다. 장애 조치 및 대체 시간 간격을 설정하도록 선택할 수도 있습니다. 장애 조치 및 대체 시간 간격(초)을 설정하면 실패한 등록자를 자동으로 감지하고 대체 시간 동안 기본 등록자가 백업되는지 자동으로 확인하므로 등록자 프로세스를 계속 수행할 수 있습니다.

> [!IMPORTANT]
> 실패 검색 및 대체 간격을 정의할 경우, 등록자가 잠깐 동안 응답하지 않을 때 장애 조치(failover) 및 대체가 수행되지 않도록 충분한 간격을 입력해야 합니다. 풀이나 서버를 로드하는 시간에 따라 기본 등록자가 잠깐 동안 응답하지 않을 수도 있습니다. 사이트의 Survivable Branch Appliance 또는 Survivable Branch Server에서 풀 또는 Standard Edition 프런트 엔드 서버로의 기본값은 장애 조치(failover)의 경우 120초, 폴백의 경우 240초입니다.

## <a name="mediation-server"></a>중재 서버

**중재 서버** 에 대해 다음을 지정할 수 있습니다.

중재 서버가 배치되어 있기 때문에 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버에서 **배치된 중재 서버 사용됨** 확인란은 사용할 수 없습니다.

풀 서버에서 TLS(전송 계층 보안)에 대한 수신 대기 포트를 정의합니다. 기본적으로 이 포트는 5067입니다. **TCP 포트 사용** 을 선택하면 배치된 중재 서버의 TCP 포트를 정의해야 합니다. 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 PSTN 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.

배치된 중재 서버와 연결된 PSTN 게이트웨이를 정의합니다. 이미 게이트웨이를 정의한 경우 해당 게이트웨이를 중재 서버와 연결할 수 있습니다. 게이트웨이를 정의하지 않았지만 정의할 수 있는 경우 **새로 만들기** 를 선택할 수 있습니다. 또한 이 중재 서버에 대해 이미 구성되어 있는 게이트웨이를 제거할 수 있습니다. 게이트웨이를 선택한 다음 **제거** 를 클릭합니다.

중재 서버와 연결된 게이트웨이가 둘 이상인 경우 연결된 첫 번째 게이트웨이가 기본 게이트웨이가 됩니다. 기본 게이트웨이로 다른 게이트웨이를 선택해야 하는 경우 기본값으로 설정할 게이트웨이를 선택하고 **기본값으로 설정** 을 클릭합니다.

## <a name="see-also"></a>참고 항목

SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [분기 사이트 복구 솔루션](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-solutions)을 참조하십시오.