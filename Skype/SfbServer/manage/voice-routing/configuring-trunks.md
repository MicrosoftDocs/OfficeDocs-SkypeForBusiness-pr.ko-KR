---
title: 비즈니스용 Skype 서버에서 trunks 구성
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
description: 엔터프라이즈 음성 배포의 일부로 중재 서버와 하나 이상의 피어 들 사이에 트렁크를 구성 하 여 조직의 엔터프라이즈 음성 클라이언트 및 장치에 대 한 PSTN (공개 통신 네트워크) 연결을 제공할 수 있습니다.
ms.openlocfilehash: 41e92f994606ea2153359546d408335d13a21f88
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817018"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 trunks 구성

엔터프라이즈 음성 배포의 일부로, 중재 서버와 다음 피어 중 하나 이상을 구성할 수 있으므로 조직의 엔터프라이즈 음성 클라이언트 및 장치에 대 한 PSTN (공개 통신 네트워크) 연결을 제공 합니다.

- 인터넷 전화 통신 서비스 공급자 (ITSP)에 대 한 SIP 트렁크 연결
- PSTN 게이트웨이
- PBX (사설 분기 교환)

자세한 내용은 [비즈니스용 Skype 서버의 PSTN 연결 계획](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)을 참조 하세요.

> [!IMPORTANT]
> 트렁크 구성을 시작 하기 전에 토폴로지가 만들어졌는지, 중재 서버와 해당 피어가 서로 구성 되어 연결 되었는지 확인 합니다. 자세한 내용은 [비즈니스용 Skype 서버의 토폴로지 작성기에서 게이트웨이 정의](../../deploy/deploy-enterprise-voice/define-a-gateway.md)를 참조 하세요.

> [!NOTE]
> 트렁크 구성의 일부로, 비즈니스용 Skype Server media bypass 기능을 사용 하도록 설정 하 여 미디어에서 중재 서버를 우회할 수 있습니다. 미디어 바이패스를 사용 하도록 설정 하거나 포함 하지 않고 Trunks를 구성할 수 있지만, 사용 하도록 설정 하는 것이 좋습니다. 자세한 내용은 [비즈니스용 Skype의 미디어 바이패스 계획](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)을 참조 하세요.
