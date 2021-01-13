---
title: 비즈니스용 Skype 서버에서 트렁크 구성
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
description: Enterprise Voice 배포의 일부로, 중재 서버와 하나 이상의 피어 간에 트렁크를 구성하여 조직의 Enterprise Voice 클라이언트 및 장치에 대한 PSTN(공용 전화망) 연결을 제공할 수 있습니다.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800118"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 트렁크 구성

Enterprise Voice 배포의 일부로 중재 서버와 다음 피어 중 하나 이상 간에 트렁크를 구성하여 조직의 Enterprise Voice 클라이언트 및 장치에 대해 PSTN(공용 전화망) 연결을 제공할 수 있습니다.

- ITSP(인터넷 전화 통신 서비스 공급자)에 대한 SIP 트렁크 연결
- PSTN 게이트웨이
- PBX(Private Branch Exchange)

자세한 내용은 비즈니스용 Skype 서버의 [PSTN 연결 계획(Plan for PSTN connectivity)을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)

> [!IMPORTANT]
> 트렁크 구성을 시작하기 전에 토폴로지가 작성되었으며 중재 서버 및 해당 피어가 구성되어 서로 연결되었는지 확인합니다. 자세한 내용은 비즈니스용 Skype 서버에서 토폴로지 [작성기에서 게이트웨이 정의를 참조하세요.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> 트렁크 구성의 일부로, 미디어가 중재 서버를 우회할 수 있도록 하는 비즈니스용 Skype 서버 미디어 우회 기능을 사용하도록 설정할 수 있습니다. 트렁크는 미디어 바이패스를 사용하거나 사용하지 않도록 설정한 상태로 구성할 수 있지만, 사용하도록 설정하는 것이 좋습니다. 자세한 내용은 비즈니스용 [Skype의 미디어 우회 계획(Plan for media bypass)을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
