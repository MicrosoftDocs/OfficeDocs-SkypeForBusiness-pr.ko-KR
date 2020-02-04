---
title: 새 트렁크 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 다음 정보를 제공 하 여 새 SIP (세션 초기화 프로토콜) 트렁크를 정의 합니다.
ms.openlocfilehash: 9de4808bc7a53aae79c2373116e74be98c7ae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684841"
---
# <a name="define-a-new-trunk"></a>새 트렁크 정의

다음 정보를 제공 하 여 새 SIP (세션 초기화 프로토콜) 트렁크를 정의 합니다.

- **트렁크 이름**:이 트렁크를 식별 하는 토폴로지의 고유 이름입니다.

- **연결 된 Pstn 게이트웨이**: 목록에서 배포에 배포 및 구성한 pstn 게이트웨이를 선택 합니다.

- IP/PSTN 게이트웨이: IP PBX 또는 PSTN 게이트웨이가 수신 대기 하는 포트 **에 대 한 수신 대기 포트**입니다. 배포에 구성 된 다른 모든 트렁크 수신 대기 포트에서 고유 해야 합니다.

- **SIP 전송 프로토콜**: 목록에서 TCP 또는 TLS 중 하나를 선택 합니다.

- **연결 된 중재 서버**: 배포에 배포 되 고 구성 되는 중재 서버를 목록에서 선택 합니다.

- **연결 된 중재 서버 포트**:이 SIP 트렁크에서 사용할 중재 서버의 TCP 또는 TLS 포트 값과 동일한 포트 값을 설정 합니다.

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015의 M:N 트렁크](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP 트렁크를 구현하는 방법](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
