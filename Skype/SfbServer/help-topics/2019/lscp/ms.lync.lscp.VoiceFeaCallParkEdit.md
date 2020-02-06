---
title: 통화 공원 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
ROBOTS: NOINDEX, NOFOLLOW
description: 통화 공원 번호 범위는 사용자가 검색 하거나 시간 초과 될 때까지 파킹 된 통화가 대기 하는 임시 번호를 정의 합니다.
ms.openlocfilehash: 252d0ab604eb733ddbe3ea79fc27e29f8e3c8035
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797825"
---
# <a name="call-park-create-new-or-edit-existing"></a>통화 대기: 새로 만들기 또는 기존 항목 편집

통화 공원 번호 범위는 사용자가 검색 하거나 시간 초과 될 때까지 파킹 된 통화가 대기 하는 임시 번호를 정의 합니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 숫자 범위를 식별 하는 설명적인 이름을 입력 합니다. 번호 범위를 저장 한 후에는이 이름을 변경할 수 없습니다.

- **숫자 범위** 첫 번째 필드에 숫자 범위의 시작 번호를 입력 합니다. 두 번째 필드에 숫자 범위의 끝 번호를 입력 합니다.

  - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

  - 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

  - 번호 범위는 고유해야 합니다. 범위가 다른 범위와 겹쳐서는 안 됩니다.

  - 숫자 범위가 문자로 \* 시작 하는 경우 범위는 100 보다 커야 합니다.

  - 유효한 값: 정규식 문자열과 일치 해야 합니다 ([\\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}). 즉, value는 문자 \* 또는 숫자 1부터 9까지 (첫 문자는 0이 될 수 없음)로 시작 하는 문자열 이어야 합니다. 첫 번째 문자가 \* or # 이면 다음 문자는 1부터 9 까지의 숫자 (0이 될 수 없음) 여야 합니다. 이후 문자는 0 ~ 9 개 까지의 추가 문자 (예: "#6000", "\*92000", "\*95551212", "915551212") 일 수 있습니다. 첫 문자 \* 를 입력 하는 경우 첫 번째 문자는 1 ~ 9 (0이 될 수 없음) 다음에 최대 8 자 (예: 915551212; 41212; 300) 여야 합니다.

  - 풀당 번호는 5만 개까지 포함할 수 있습니다. 각 번호 범위에는 일반적으로 100개 이하의 번호가 포함되지만, 그보다 훨씬 커질 수도 있습니다(1만 개 이하의 번호 포함). 예를 들어 시작 번호를 "7000000"으로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"으로, 끝 번호를 "7000100"으로 지정할 수 있습니다.

- **대상 서버의 FQDN** 통화 공원 응용 프로그램을 호스트 하는 응용 프로그램 서비스의 FQDN (정규화 된 도메인 이름) 또는 서비스 ID를 선택 합니다. 숫자 범위의 시작 번호와 끝 번호로 지정 된 범위 내에 있는 모든 통화는이 서버 또는 풀로 라우팅됩니다.

통화 공원 기능 및 기능에 대 한 자세한 내용은 [비즈니스용 Skype의 통화 공원 계획](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)을 참조 하세요. 통화 공원 번호 범위 작업에 대 한 자세한 내용은 [파킹 통화에 대 한 전화 번호 확장 구성을](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)참조 하세요.


