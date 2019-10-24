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
description: 다이렉트 라우팅 통화 알림
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 07efe11d304107a5a8606a07f5d1c2a7a130bc0b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37639636"
---
# <a name="manage-call-notifications"></a>통화 알림 관리

이 문서에서는 사용자에 대 한 통화 알림을 관리 하는 방법을 설명 합니다. 통화 끝점을 팀과 타사의 PBX (개인 분기 교환) 또는 SBC (세션 경계 컨트롤러) 모두로 구성할 수 있습니다.  이 방법은 사용자의 휴대폰 및 일반 전화기로 전화를 걸 때와 같이 동시에 통화를 보내는 경우에 유용 합니다.   

다음 다이어그램에서 사용자 Irena는 두 개의 끝점을 사용 합니다.

- 팀 끝점
- 타사 SBC에 연결 된 SIP 전화

통화가 도착 하면 SBC는 전화 시스템 다이렉트 라우팅과 타사 SBC 간의 통화를 포크 합니다.


![분기 팀 끝점을 보여 주는 다이어그램](media/direct-routing-call-notification-1.png)

타사 SBC의 포크 2에서 통화를 허용 하는 경우 팀에서 "부재 중 통화" 알림을 생성 합니다.  

다음과 같이 포크 1에 취소를 보내도록 SBC를 구성 하 여 "부재 중 전화" 알림을 방지할 수 있습니다.

이유: SIP 원인 = 200; 텍스트 "통화가 다른 곳에 완료 됨" 

통화는 전화를 걸어 Microsoft 전화 시스템의 통화 정보 레코드에 등록 되지 않습니다. 통화는 최종 SIP 코드 "487", 최종 Microsoft 하위 코드 "540200" 및 최종 SIP 코드 구 "통화를 다른 곳에서 완료 됨"으로 "시도" 하 여 등록 됩니다.   (통화 정보 레코드를 보려면 팀 관리 포털, 분석 및 보고서, 사용 현황 보고서, 그리고 PSNT 사용을 선택 하세요.)


아래 다이어그램은 포크 1에 대 한 SIP 사다리와 통화 흐름에 대 한 설명과 취소 메시지의 예상 되는 이유를 보여줍니다. 

![분기 팀 끝점을 보여 주는 다이어그램](media/direct-routing-call-notification-2.png)
