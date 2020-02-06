---
title: 비즈니스용 Skype 서버의 트렁크 간 라우팅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '비즈니스용 Skype Server는 intertrunk 라우팅 지원을 통해 기본적인 세션 관리를 제공 합니다. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816968"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 트렁크 간 라우팅

비즈니스용 Skype Server는 intertrunk 라우팅 지원을 통해 기본적인 세션 관리를 제공 합니다. 이 접근 권한 값을 사용 하 여 비즈니스용 Skype 서버에서 다운스트림 전화 통신 시스템에 대 한 통화 제어 기능을 제공할 수 있습니다. Intertrunk 라우팅은 IP-PBX (사설 브랜치 교환) 휴대폰의 호출을 PSTN으로 라우팅할 수 있고 들어오는 PSTN 통화를 PBX 전화기로 라우팅할 수 있도록 IP PBX를 PSTN (공개 전환 통신 네트워크) 게이트웨이와 상호 연결할 수 있습니다. 마찬가지로, 비즈니스용 Skype 서버는 두 개 이상의 IP PBX 시스템을 상호 연결 하 여 여러 IP PBX 시스템에서 PBX 전화기 간에 전화를 걸고 받을 수 있습니다. 


다음 그림에서는 PSTN 게이트웨이와 IP PBX 간의 interconnectivity을 제공 하는 비즈니스용 Skype 서버를 보여 줍니다.

![PSTN 게이트웨이와 IP PBX 간의 Interconnectivity](../../media/pstn-gateway-ip-pbx.jpg)

다음 그림은 두 개의 IP PBX 시스템을 연결 하는 비즈니스용 Skype 서버를 보여줍니다.

![두 개의 IP PGX 시스템을 연결 하는 비즈니스용 Skype 서버](../../media/two-ip-pbx-systems.jpg)

