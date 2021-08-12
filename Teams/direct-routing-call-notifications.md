---
title: 'Teams: 통화 알림 관리'
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
description: 직접 라우팅 호출 알림
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b251040f9433d9ac51b388d12fa530b7c982e0773580d6ac69d41825fbba1ae6
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848323"
---
# <a name="manage-call-notifications"></a>통화 알림 관리

이 문서에서는 사용자의 통화 알림을 관리하는 방법을 설명합니다. PBX(개인 분기)Teams(PBX) 또는 세션 경계 컨트롤러(Exchange)에 대해 호출 엔드포인트를 구성할 수 있습니다.  이 설정은 사용자의 모바일 및 책상 전화에 동시에 전화를 보내고자 하는 경우와 같은 유용합니다.   

다음 다이어그램에서 사용자 Irena에는 두 개의 엔드포인트가 있습니다.

- Teams 엔드포인트
- 타사 SBC에 연결된 SIP 전화

호출이 도착하면 SBC는 직접 라우팅과 타사 전화 시스템 간에 호출을 포크합니다.


![포크된 엔드포인트를 Teams 다이어그램](media/direct-routing-call-notification-1.png)

Fork 2에서 호출이 수락된 경우(타사 SBC에서) Teams "부재 중 전화" 알림이 생성됩니다.  

다음과 같이 포크 1에서 취소를 보내기 위해 SBC를 구성하여 "부재 중 전화" 알림을 방지할 수 있습니다.

이유: SIP; cause=200;text"call completed elsewhere" 

호출은 시스템 시스템의 호출 세부 정보 레코드에 Microsoft 전화 성공적인 호출로 등록되지 않습니다. 호출은 최종 SIP 코드 "487", 최종 Microsoft 하위 코드 "540200", 최종 SIP 코드 구 "다른 곳에서 완료된 호출"으로 "시도"로 등록됩니다.  (통화 세부 정보 레코드를 확인하려면 관리 Teams, 분석 및 보고서, 사용 현황 보고서를 이동하고 PSTN 사용량을 선택합니다.)


아래 다이어그램에서는 Fork 1용 SIP 사다리에 대해 설명하고, 호출 흐름 및 취소 메시지에서 예상된 이유를 설명합니다. 

![다이어그램은 포크된 엔드포인트를 Teams 보여줍니다.](media/direct-routing-call-notification-2.png)
