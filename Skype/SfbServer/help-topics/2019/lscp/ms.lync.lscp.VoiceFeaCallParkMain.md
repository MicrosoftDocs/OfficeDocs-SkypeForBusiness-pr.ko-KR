---
title: 통화 대기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 대기 중인 통화는 다른 사용자가 검색 하거나 시간 초과 될 때까지 통화가 보류 되는 임시 번호로 전송 됩니다. 파킹 된 통화를 위해 예약 하는 내선 번호 범위를 사용 하 여 표를 구성 해야 합니다. 이 내선 번호는 가상 내선 번호여야 합니다(즉, 이 번호에 할당된 사용자나 전화가 없어야 함). 통화 공원 응용 프로그램을 실행 하는 각 풀에는 하나 이상의 확장 범위가 있을 수 있습니다. 이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.
ms.openlocfilehash: 6519a678c2370e9763dddd3680c3a64257fe4305
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690323"
---
# <a name="call-park"></a>통화 대기

대기 중인 통화는 다른 사용자가 검색 하거나 시간 초과 될 때까지 통화가 보류 되는 임시 번호로 전송 됩니다. 파킹 된 통화를 위해 예약 하는 내선 번호 범위를 사용 하 여 표를 구성 해야 합니다. 이 내선 번호는 가상 내선 번호여야 합니다(즉, 이 번호에 할당된 사용자나 전화가 없어야 함). 통화 공원 응용 프로그램을 실행 하는 각 풀에는 하나 이상의 확장 범위가 있을 수 있습니다. 이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.

**통화 공원** 페이지에는 조직에 대해 정의 된 모든 통화 공원 번호 범위가 표시 됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**통화 대기** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 새 번호 범위 만들기

- 기존 번호 범위 변경

- 번호 범위 삭제

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 명령에 대해 설명합니다.

- **새로운** 새 통화 공원 번호 범위를 시작 합니다.

- **편집** 선택한 숫자 범위를 편집용으로 열거나 목록에 있는 모든 숫자 범위를 선택 하거나 선택한 숫자 범위를 삭제 합니다.

- **새로 고침** 숫자 범위 목록을 새로 고칩니다.

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 숫자 범위를 식별 하는 고유 이름입니다.

- **시작 범위** 범위의 시작 번호입니다.

- **끝 범위** 범위의 끝 번호입니다.

- **대상** 숫자 범위에 대 한 통화 공원 응용 프로그램을 호스트 하는 응용 프로그램 서비스의 FQDN (정규화 된 도메인 이름) 또는 서비스 ID입니다.

통화 공원 기능 및 기능에 대 한 자세한 내용은 [비즈니스용 Skype의 통화 공원 계획](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)을 참조 하세요. 통화 공원 번호 범위 작업에 대 한 자세한 내용은 [파킹 통화에 대 한 전화 번호 확장 구성을](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)참조 하세요.


