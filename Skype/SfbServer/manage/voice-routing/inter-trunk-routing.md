---
title: 비즈니스용 Skype 서버의 트렁크 간 라우팅
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
description: '비즈니스용 Skype 서버는 트렁크 간 라우팅을 통해 기본 세션 관리를 제공합니다. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814128"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 트렁크 간 라우팅

비즈니스용 Skype 서버는 트렁크 간 라우팅을 통해 기본 세션 관리를 제공합니다. 이 기능을 사용하면 비즈니스용 Skype 서버가 다운스트림 전화 통신 시스템에 통화 제어 기능을 제공할 수 있습니다. 트렁크 간 라우팅은 IP-PBX를 PSTN(공중 전화망) 게이트웨이에 상호 연결할 수 있으므로 PBX(Private Branch eXchange) 전화의 통화를 PSTN으로 라우팅하고 들어오는 PSTN 통화를 PBX 전화로 라우팅할 수 있습니다. 마찬가지로 비즈니스용 Skype 서버는 서로 다른 IP-PBX 시스템에서 PBX 전화 간에 통화를 걸고 수신할 수 있도록 둘 이상의 IP-PBX 시스템을 상호 연결할 수 있습니다. 


다음 그림에서는 PSTN 게이트웨이와 IP-PBX 간의 상호 연결 정보를 제공하는 비즈니스용 Skype 서버를 보여 줍니다.

![PSTN 게이트웨이와 IP-PBX 간의 상호 연결](../../media/pstn-gateway-ip-pbx.jpg)

다음 그림에서는 두 IP-PBX 시스템을 연결하는 비즈니스용 Skype 서버를 보여 제공합니다.

![두 IP-PGX 시스템 연결 비즈니스용 Skype 서버](../../media/two-ip-pbx-systems.jpg)

