---
title: 새 트렁크 정의
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 다음 정보를 제공하여 새 SIP(Session Initiation Protocol) 트렁크를 정의합니다.
ms.openlocfilehash: 963a622ed2a7f3c39dca0be5199126ffaf201314
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416701"
---
# <a name="define-a-new-trunk"></a>새 트렁크 정의

다음 정보를 제공하여 새 SIP(Session Initiation Protocol) 트렁크를 정의합니다.

- **트렁크 이름**: 이 트렁크를 식별하는 토폴로지의 고유 이름

- **연결된 PSTN 게이트웨이**: 목록에서 배포의 배포 및 구성된 PSTN 게이트웨이 선택

- **IP/PSTN** 게이트웨이용 수신 포트: IP-PBX 또는 PSTN 게이트웨이가 수신하는 포트입니다. 배포에 구성된 다른 모든 트렁크 수신 포트에서 고유해야 합니다.

- **SIP 전송 프로토콜**: 목록에서 TCP 또는 TLS 선택

- **연결된 중재 서버**: 목록에서 배포에 배포 및 구성된 중재 서버를 선택합니다.

- **연결된 중재 서버 포트**: 이 SIP 트렁크에서 사용할 중재 서버의 TCP 또는 TLS 포트 값으로 포트 값을 설정

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 M:N 트렁크](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[SIP 트렁크를 구현하는 방법](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)