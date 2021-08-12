---
title: 통화 파크 새로 만들기 또는 기존 데이터 편집
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 통화 파크 번호 범위는 누군가가 통화를 재개하거나 시간이 지날 때까지 통화가 보전되는 임시 번호를 정의합니다.
ms.openlocfilehash: 7c4050ebf09d2b0f533aee9fecb4eda3c4f383b9a914886a125f150740cea07f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294735"
---
# <a name="call-park-create-new-or-edit-existing"></a>통화 파킹: 새로 만들기 또는 기존 항목 편집

통화 파크 번호 범위는 누군가가 통화를 재개하거나 시간이 지날 때까지 통화가 보전되는 임시 번호를 정의합니다.

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 번호 범위를 식별하는 설명적인 이름을 입력합니다. 번호 범위를 저장한 후 이 이름은 변경할 수 없습니다.

- **번호 범위** 첫 번째 필드에 번호 범위의 시작 번호를 입력합니다. 두 번째 필드에 번호 범위의 끝 번호를 입력합니다.

  - 범위의 시작 번호는 범위의 마지막 번호보다 작거나 같아야 합니다.

  - 범위의 시작 번호 값 길이는 범위의 마지막 번호 길이와 같아야 합니다.

  - 번호 범위는 고유해야 합니다. 이 범위는 다른 범위와 겹칠 수 없습니다.

  - 숫자 범위가 문자나 #로 시작하는 경우 범위는 \* 100보다 커야 합니다.

  - 유효한 값: 정규식 문자열([ \\ *|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ). 즉, 값은 문자나 #으로 시작되는 문자열 또는 1에서 9까지의 숫자(첫 번째 문자는 \* 0일 수 없습니다.)입니다. 첫 문자가 또는 #이면 다음 문자는 1에서 9까지의 숫자가 되어야 합니다. 0이 될 \* 수 없습니다. 이후 문자는 "#6000", \* "92000", "95551212" 및 "915551212")까지 0에서 9까지의 숫자를 사용할 수 \* 있습니다. 첫 번째 문자가 또는 #이면 첫 번째 문자는 1에서 9까지의 숫자가 되어야 합니다(0일 수 없습니다). 그 다음에 0에서 9까지의 숫자를 입력할 수 있습니다(예: \* 915551212;41212;300).

  - 풀당 숫자는 총 50,000개 이상이면 안 됩니다. 각 번호 범위에는 일반적으로 100개 이하의 숫자가 포함되지만 숫자가 10,000개 미만인 경우 훨씬 클 수 있습니다. 예를 들어 시작 번호를 "7000000"로, 끝 번호를 "8000000"으로 지정하는 대신 시작 번호를 "7000000"로, 끝 번호를 "7000100"으로 지정할 수 있습니다.

- **대상 서버의 FQDN** 통화 파크 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 FQDN(FQDN) 또는 서비스 ID를 선택합니다. 번호 범위의 시작 번호와 끝 번호로 지정된 범위 내의 번호로 예약된 모든 통화는 이 서버 또는 풀로 라우팅됩니다.

통화 파크 기능에 대한 자세한 내용은 [Plan for Call Park in 비즈니스용 Skype.](../../../plan-your-deployment/enterprise-voice-solution/call-park.md) 통화 파킹 번호 범위를 사용할 수 있는 자세한 내용은 [Configure 전화 Number Extensions for Parking Calls을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)