---
title: 직접 라우팅에 대한 통화 알림 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 직접 라우팅 통화 알림
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268433"
---
# <a name="manage-call-notifications"></a>통화 알림 관리

이 문서에서는 직접 라우팅 사용자에 대한 통화 알림을 관리하는 방법을 설명합니다. Teams와 타사 PBX(Private Branch Exchange) 또는 SBC(세션 테두리 컨트롤러)에 대한 통화 엔드포인트를 구성할 수 있습니다. 이 설정은 예를 들어 사용자의 휴대폰 및 책상 전화로 동시에 전화를 보내려는 경우에 유용합니다.   

다음 다이어그램에서 사용자 Irena에는 두 개의 엔드포인트가 있습니다.

- Teams 엔드포인트
- 타사 SBC에 연결된 SIP 전화

통화가 도착하면 SBC는 직접 라우팅과 타사 SBC 간의 호출을 포크합니다.


![포크된 Teams 엔드포인트를 보여 주는 다이어그램](media/direct-routing-call-notification-1.png)

포크 2(타사 SBC)에서 통화가 수락되면 Teams는 "부재 중 전화" 알림을 생성합니다.  

다음과 같이 포크 1에서 취소를 보내도록 SBC를 구성하여 "부재 중 전화" 알림을 방지할 수 있습니다.

이유: SIP; cause=200;text"Call completed elsewhere" 

통화는 Teams 전화 시스템의 통화 세부 정보 레코드에 성공적인 통화로 등록되지 않습니다. 호출은 최종 SIP 코드 "487", 최종 Microsoft 하위 코드 "540200" 및 최종 SIP 코드 구 "통화가 다른 곳에서 완료됨"을 사용하여 "시도"로 등록됩니다.  (통화 세부 정보 레코드를 보려면 Teams 관리 센터 -> **분석 및 보고서** -> **사용 현황 보고서** 로 이동하고 **PSTN 사용량을** 선택합니다.)


아래 다이어그램은 포크 1에 대한 SIP 사다리를 보여 줍니다. 호출 흐름 및 취소 메시지의 예상된 이유를 설명합니다. 

![다이어그램은 포크된 Teams 엔드포인트를 보여 줍니다.](media/direct-routing-call-notification-2.png)
