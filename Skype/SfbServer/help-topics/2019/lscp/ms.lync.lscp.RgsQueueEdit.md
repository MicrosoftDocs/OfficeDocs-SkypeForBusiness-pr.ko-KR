---
title: 응답 그룹 큐 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 응답 그룹 큐는 상담원이 전화에 대답할 때까지 응답 그룹에 대 한 통화를 보류 합니다.
ms.openlocfilehash: 20a2066cbbece953e8f050919d8531f887f676ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196261"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>응답 그룹 큐: 새로 만들기 또는 기존 항목 편집

응답 그룹 큐는 상담원이 전화에 대답할 때까지 응답 그룹에 대 한 통화를 보류 합니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 각 대기열에는 이름이 있어야 합니다. 큐에 대 한 설명이 포함 된 이름을 입력 합니다.

- **설명** 이 필드는 선택 사항입니다. 이 기능을 사용 하 여 대기열에 대 한 추가 정보를 제공 합니다.

- **Groups** 큐에 할당 하려는 에이전트 그룹을 선택 합니다. **선택을** 클릭 하 여 목록에 에이전트 그룹을 추가 합니다. 목록에서 선택한 에이전트 그룹을 삭제 하려면 **제거** 를 클릭 합니다.

    위쪽 및 아래쪽 화살표를 사용하여 목록에서 선택한 에이전트 그룹을 위쪽 및 아래쪽으로 이동합니다. 에이전트 그룹의 순서는 비즈니스용 Skype 서버에서 사용 가능한 에이전트를 검색 하는 순서에 영향을 줍니다. 즉, 목록의 첫 번째 그룹에서 사용 가능한 에이전트를 먼저 검색한 다음 두 번째 그룹 및 그 이후 그룹 순서대로 검색합니다.

- **큐 시간 초과 사용** 에이전트가 통화에 응답 하기 전에 호출자가 대기를 대기할 최대 기간을 지정 하려면이 확인란을 선택 합니다. 이 옵션을 선택 하는 경우 다음도 지정 해야 합니다.

  - **시간 제한 기간 (초)** 호출자가 전화에 응답 하기 전에 대기할 수 있는 최대 시간 (초)을 선택 하거나 입력 합니다.

  - **통화 동작** 통화 시간 초과 시 발생 하는 작업을 선택 합니다. 선택 사항은 다음과 같습니다.

  - **연결 끊기**

  - **음성 메일로 착신 전환** 이 옵션을 선택 하는 경우 sip **주소**에 음성 메일 주소를 sip 형식으로 입력 합니다 (<username> @ <domainname> 예: sip:bob@contoso.com).

  - **전화 번호로 착신 전환** 이 옵션을 선택 하는 경우 **sip 주소** 에서 전화 번호를 sip 형식으로 입력 합니다<number> @ <domainname> (예: sip:+14255550121@contoso.com).

  - **SIP 주소로 착신 전환** 다른 사용자에 게 통화를 착신 전환 하려면이 옵션을 선택 합니다. **Sip 주소**에서 sip<username>@<domainname>형식으로 사용자의 URI를 입력 합니다.

  - **다른 큐로 착신 전환** 이 옵션을 선택 하는 경우에는 통화 시간이 초과 될 때 전화를 받을 대기열을 찾습니다.

- **큐 오버플로 사용** 큐에서 보유할 수 있는 최대 통화 수를 지정 하려면이 확인란을 선택 합니다. 이 옵션을 선택 하는 경우 다음도 지정 해야 합니다.

  - **최대 통화 수** 대기열이 저장할 수 있는 최대 통화 수를 선택 하거나 입력 합니다.

  - **통화 착신 전환** 큐 오버플로 임계값이 충족 될 때 조치를 취해야 하는 통화를 선택 합니다.

  - **통화 동작** 큐 오버플로 임계값에 도달 했을 때 발생 하는 작업을 선택 합니다. 선택 사항은 다음과 같습니다.

  - **연결 끊기**

  - **음성 메일로 착신 전환** 이 옵션을 선택 하는 경우 sip **주소**에 음성 메일 주소를 sip 형식으로 입력 합니다 (<username> @ <domainname> 예: sip:bob@contoso.com).

  - **전화 번호로 착신 전환** 이 옵션을 선택 하는 경우 **sip 주소** 에서 전화 번호를 sip 형식으로 입력 합니다<number> @ <domainname> (예: sip:+14255550121@contoso.com).

  - **SIP 주소로 착신 전환** 다른 사용자에 게 통화를 착신 전환 하려면이 옵션을 선택 합니다. **Sip 주소**에서 sip<username>@<domainname>형식으로 사용자의 URI를 입력 합니다.

  - **다른 큐로 착신 전환** 이 옵션을 선택 하는 경우 큐 오버플로 임계값이 충족 될 때 전화를 받을 큐를 찾습니다.

응답 그룹 기능 및 기능에 대 한 자세한 내용은 계획 설명서의 [비즈니스용 Skype 서버에서 응답 그룹 응용 프로그램 계획](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 을 참조 하세요. 큐 사용에 대한 자세한 내용은 작업 설명서의 [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)를 참조하세요.


