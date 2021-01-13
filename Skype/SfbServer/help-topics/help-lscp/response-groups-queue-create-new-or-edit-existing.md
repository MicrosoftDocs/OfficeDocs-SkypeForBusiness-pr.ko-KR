---
title: 응답 그룹 큐 새로 만들기 또는 기존 데이터 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: 응답 그룹 큐는 에이전트가 통화에 응답할 때까지 응답 그룹에 대한 통화를 보류합니다.
ms.openlocfilehash: cfe2d212f90f8dcdf83b8f827ebf470245ce87fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829318"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>응답 그룹 큐: 새로 만들기 또는 기존 항목 편집

응답 그룹 큐는 에이전트가 통화에 응답할 때까지 응답 그룹에 대한 통화를 보유합니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 각 큐에는 이름이 있어야 합니다. 큐에 대한 설명적인 이름을 입력합니다.

- **설명** 이 필드는 선택 사항입니다. 이 기능을 사용하여 큐에 대한 추가 세부 정보를 제공합니다.

- **그룹** 큐에 할당할 에이전트 그룹을 선택합니다. **선택을** 클릭하여 목록에 에이전트 그룹을 추가합니다. **목록에서** 선택한 에이전트 그룹을 삭제하려면 제거를 클릭합니다.

    위쪽 및 아래쪽 화살표를 사용하여 목록에서 선택한 에이전트 그룹을 위쪽 및 아래쪽으로 이동합니다. 에이전트 그룹의 순서는 비즈니스용 Skype 서버가 사용 가능한 에이전트를 검색하는 순서에 영향을 미치게 됩니다. 즉, 목록의 첫 번째 그룹에서 사용 가능한 에이전트를 먼저 검색한 다음 두 번째 그룹 및 그 이후 그룹 순서대로 검색합니다.

- **큐 시간 아웃 사용** 에이전트가 통화에 응답하기 전에 발신자 대기 시간을 최대로 지정하려면 이 확인란을 선택합니다. 이 옵션을 선택하는 경우 다음도 지정해야 합니다.

  - **시간 아웃 기간(초)** 에이전트가 통화에 응답할 때까지 발신자에서 대기할 수 있는 최대 시간(초)을 선택하거나 입력합니다.

  - **통화 작업** 통화 시간 외의 시간일 때 수행된 작업을 선택합니다. 선택할 수 있는 선택은

  - **연결 끊기**

  - **음성 메일로 전달** 이 옵션을 선택하는 경우 **SIP** 주소에 음성 메일 주소를 sip 형식으로 입력합니다(예: <username> @ <domainname> sip:bob@contoso.com).

  - **전화 번호로 전달** 이 옵션을 선택하는 경우 **SIP** 주소에 전화 번호를 sip 형식으로 입력합니다(예: <number> @ <domainname> sip:+14255550121@contoso.com).

  - **SIP 주소로 전달** 통화를 다른 사용자에게 전달하려면 이 옵션을 선택합니다. **SIP 주소에** 사용자의 URI를 sip: 형식으로 <username> @ <domainname> 입력합니다.

  - **다른 큐로 전달** 이 옵션을 선택하는 경우 통화 시간이 지난 경우 전화를 받을 큐로 이동합니다.

- **큐 오버플로 사용** 큐에 보유할 수 있는 최대 통화 수를 지정하려면 이 확인란을 선택합니다. 이 옵션을 선택하는 경우 다음도 지정해야 합니다.

  - **최대 통화 수** 큐에 보유할 수 있는 최대 통화 수를 선택하거나 입력합니다.

  - **통화 전달** 큐 오버플로 임계값에 도달하면 조치를 취할 호출을 선택합니다.

  - **통화 작업** 큐 오버플로 임계값에 도달할 때 수행되는 작업을 선택합니다. 선택할 수 있는 선택은

  - **연결 끊기**

  - **음성 메일로 전달** 이 옵션을 선택하는 경우 **SIP** 주소에 음성 메일 주소를 sip 형식으로 입력합니다(예: <username> @ <domainname> sip:bob@contoso.com).

  - **전화 번호로 전달** 이 옵션을 선택하는 경우 **SIP** 주소에 전화 번호를 sip 형식으로 입력합니다(예: <number> @ <domainname> sip:+14255550121@contoso.com).

  - **SIP 주소로 전달** 통화를 다른 사용자에게 전달하려면 이 옵션을 선택합니다. **SIP 주소에** 사용자의 URI를 sip: 형식으로 <username> @ <domainname> 입력합니다.

  - **다른 큐로 전달** 이 옵션을 선택하는 경우 큐 오버플로 임계값에 도달하면 통화를 받을 큐로 이동합니다.

응답 그룹 기능에 대한 자세한 내용은 계획 설명서에서 비즈니스용 [Skype 서버 2015의](../../plan-your-deployment/enterprise-voice-solution/response-group.md) 응답 그룹 응용 프로그램 계획을 참조하십시오. 큐를 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)를 참조하십시오.


