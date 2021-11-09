---
title: 통화 대기
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 통화가 일시적인 번호로 전송됩니다. 이 번호는 누군가가 통화를 재개하거나 통화가 시간 외일 때까지 통화가 보전됩니다. 파킹된 통화를 위해 보존할 내선 번호 범위로 테이블을 구성해야 합니다. 이 내선 번호는 가상 내선 번호여야 합니다(즉 이 번호에 할당된 사용자나 전화가 없어야 함). 통화 파크 응용 프로그램을 실행하는 각 풀에는 하나 이상의 내선 범위가 있습니다. 이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.
ms.openlocfilehash: 14c5ddbf3bd7f2d862cfd3f3e89310932964b8b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841570"
---
# <a name="call-park"></a>Call Park

통화가 일시적인 번호로 전송됩니다. 이 번호는 누군가가 통화를 재개하거나 통화가 시간 외일 때까지 통화가 보전됩니다. 파킹된 통화를 위해 보존할 내선 번호 범위로 테이블을 구성해야 합니다. 이 내선 번호는 가상 내선 번호여야 합니다(즉 이 번호에 할당된 사용자나 전화가 없어야 함). 통화 파크 응용 프로그램을 실행하는 각 풀에는 하나 이상의 내선 범위가 있습니다. 이러한 범위는 배포 전체에서 전역적으로 고유해야 합니다.

통화 **파크 페이지에는** 조직에 대해 정의된 모든 통화 파크 번호 범위의 목록이 표시됩니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**통화 대기** 페이지에서는 다음 작업을 수행할 수 있습니다.

- 새 번호 범위 만들기

- 기존 번호 범위 변경

- 번호 범위 삭제

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 명령에 대해 설명합니다.

- **새로 추가** 새 통화 파크 번호 범위를 시작합니다.

- **편집** 편집할 선택한 번호 범위를 열거나 목록의 모든 번호 범위를 선택하거나 선택한 번호 범위를 삭제합니다.

- **새로 고침** 번호 범위 목록을 새로 고침합니다.

다음 목록에서는 페이지의 필드에 대해 설명합니다.

- **이름** 번호 범위를 식별하는 고유 이름입니다.

- **시작 범위** 범위의 시작 번호입니다.

- **끝 범위** 범위의 끝 번호입니다.

- **대상** 번호 범위에 대한 통화 파크 응용 프로그램을 호스팅하는 응용 프로그램 서비스의 FQDN(정식 도메인 이름) 또는 서비스 ID입니다.

통화 파크 기능에 대한 자세한 내용은 [Plan for Call Park in 비즈니스용 Skype 2015을 참조합니다.](../../plan-your-deployment/enterprise-voice-solution/call-park.md) 통화 파킹 번호 범위를 사용할 수 있는 자세한 내용은 [Configure 전화 Number Extensions for Parking Calls을 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)