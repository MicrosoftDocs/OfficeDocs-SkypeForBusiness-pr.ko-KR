---
title: 트렁크 구성 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Enterprise Voice 배포의 일부로 중재 서버와 하나 이상의 피어 간에 트렁크를 구성하여 조직의 Enterprise Voice 클라이언트 및 장치에 대한 PSTN(Public Switched Telephone Network) 연결을 제공할 수 있습니다.
ms.openlocfilehash: 080678192326af1933996ef36ad953c3eff90f50
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391090"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>트렁크 구성 비즈니스용 Skype 서버

Enterprise Voice 배포의 일부로 중재 서버와 다음 피어 중 하나 이상 간에 트렁크를 구성하여 조직의 Enterprise Voice 클라이언트 및 장치에 대해 PSTN(Public Switched Telephone Network) 연결을 제공할 수 있습니다.

- ITSP(인터넷 전화 통신 서비스 공급자)에 대한 SIP 트렁크 연결
- PSTN 게이트웨이
- PBX(Private Branch Exchange)

자세한 내용은 [Plan for PSTN connectivity in 비즈니스용 Skype 서버](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> 트렁크 구성을 시작하기 전에 토폴로지가 작성되었으며 중재 서버 및 해당 피어가 구성되어 서로 연결되었는지 확인합니다. 자세한 내용은 [Define a gateway in Topology Builder in 비즈니스용 Skype 서버](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> 트렁크 구성의 일부로 미디어가 중재 서버를 비즈니스용 Skype 서버 수 있도록 하는 미디어 우회 기능을 사용하도록 설정할 수 있습니다. 트렁크는 미디어 바이패스를 사용하거나 사용하지 않도록 설정한 상태로 구성할 수 있지만, 사용하도록 설정하는 것이 좋습니다. 자세한 내용은 [Plan for media bypass in 비즈니스용 Skype](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
