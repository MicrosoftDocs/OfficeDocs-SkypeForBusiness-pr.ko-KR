---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 직접 라우팅 통화 알림
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341799"
---
# <a name="manage-call-notifications"></a>통화 알림 관리

이 문서에서는 사용자의 통화 알림을 관리하는 방법을 설명하고 있습니다. Teams와 타사 PBX(Private Branch Exchange) 또는 SBC(세션 테두리 컨트롤러)에 대한 호출 엔드포인트를 구성할 수 있습니다.  예를 들어 사용자의 휴대폰과 데스크 전화로 동시에 통화를 보내고 싶은 경우 유용합니다.   

다음 다이어그램에서 사용자 Irena에는 두 개의 엔드포인트가 있습니다.

- Teams 엔드포인트
- 타사 SBC에 연결된 SIP 휴대폰

호출이 도착하면 SBC는 전화 시스템 직접 라우팅과 타사 SBC 간에 통화를 포크합니다.


![포크된 Teams 엔드포인트를 보여주는 다이어그램](media/direct-routing-call-notification-1.png)

타사 SBC에서 포크 2에서 통화를 수락하면 Teams에서 "부재 중 전화" 알림을 생성합니다.  

다음과 같이 포크 1에서 취소를 보내기 위해 SBC를 구성하여 "부재 중 통화" 알림을 방지할 수 있습니다.

이유: SIP; cause=200;text"Call completed elsewhere" 

통화는 성공한 통화로 Microsoft Phone System의 통화 세부 정보 레코드에 등록되지 않습니다. 호출은 최종 SIP 코드 "487", 최종 Microsoft 하위 코드 "540200" 및 최종 SIP 코드 구 "다른 곳에서 호출 완료"를 사용하여 "시도"로 등록됩니다.  통화 세부 정보 레코드를 확인하려면 Teams 관리 포털, 분석 및 보고서, 사용 현황 보고서로 이동하여 PSTN 사용량을 선택합니다.


아래 다이어그램은 포크 1에 대한 SIP 사다리, 호출 흐름 및 취소 메시지의 예상된 이유를 설명합니다. 

![포크된 Teams 엔드포인트를 보여주는 다이어그램](media/direct-routing-call-notification-2.png)
