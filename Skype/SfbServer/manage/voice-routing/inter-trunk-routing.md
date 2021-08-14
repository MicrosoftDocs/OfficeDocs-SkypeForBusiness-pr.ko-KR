---
title: 트렁크 간 라우팅 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '비즈니스용 Skype 서버 트렁크 라우팅 지원을 통해 기본 세션 관리를 제공합니다. '
ms.openlocfilehash: 2c2d2dfd1062414de0d11b9e77d7f9f1993a77a14266a8d121b43bfbc12335da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351498"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>트렁크 간 라우팅 비즈니스용 Skype 서버

비즈니스용 Skype 서버 트렁크 라우팅 지원을 통해 기본 세션 관리를 제공합니다. 이 기능을 사용하면 비즈니스용 Skype 서버 전화 통신 시스템에 대한 통화 제어 기능을 제공할 수 있습니다. 트렁크 간 라우팅은 IP-PBX를 PSTN(공중 전화망) 게이트웨이에 상호 연결할 수 있으므로 PBX(Private Branch eXchange) 전화의 통화를 PSTN으로 라우팅하고 들어오는 PSTN 통화를 PBX 전화로 라우팅할 수 있습니다. 마찬가지로 비즈니스용 Skype 서버 IP-PBX 시스템에서 PBX 전화 간에 통화를 걸고 수신할 수 있도록 둘 이상의 IP-PBX 시스템을 상호 연결할 수 있습니다. 


다음 그림에서는 PSTN 비즈니스용 Skype 서버 IP-PBX 간의 상호 연결 제공을 보여 줍니다.

![PSTN 게이트웨이와 IP-PBX 간의 상호 연결](../../media/pstn-gateway-ip-pbx.jpg)

다음 그림에서는 두 IP-비즈니스용 Skype 서버 연결하는 방법을 보여 제공합니다.

![비즈니스용 Skype 서버 IP-PGX 시스템 연결](../../media/two-ip-pbx-systems.jpg)

