---
title: 비즈니스용 Skype 서버의 여러 트렁크 지원
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
description: 비즈니스용 Skype 서버 기능은 게이트웨이와 중재 서버 간의 복수 연결을 지원 합니다. 이러한 연결은 중재 서버 풀과 PSTN (공개 교환 통신 네트워크) 게이트웨이, SBC (세션 경계 컨트롤러) 또는 IP-PBX 간의 논리적 연결 인 트렁크를 정의 하 여 이루어집니다. 토폴로지 작성기를 사용 하 여 게이트웨이를 중재 서버와 연결 합니다 (즉, trunks).
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816948"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 여러 트렁크 지원

비즈니스용 Skype 서버 기능은 게이트웨이와 중재 서버 간의 복수 연결을 지원 합니다. 이러한 연결은 중재 서버 풀과 PSTN (공개 교환 통신 네트워크) 게이트웨이, SBC (세션 경계 컨트롤러) 또는 IP-PBX 간의 논리적 연결 인 트렁크를 정의 하 여 이루어집니다. 토폴로지 작성기를 사용 하 여 게이트웨이를 중재 서버와 연결 합니다 (즉, trunks).

- 비즈니스용 Skype 서버에서 트렁크를 할당 또는 제거 하려면 먼저 토폴로지 작성기에서 트렁크를 정의 해야 합니다. 트렁크는 다음 연결로 구성 됩니다. 중재 서버 FQDN (정규화 된 도메인 이름), 중재 서버 수신 포트, 게이트웨이 FQDN 및 게이트웨이 수신 대기 포트.
- 여러 trunks를 구성 하려면 동일한 게이트웨이와 중재 서버 간에 여러 연결을 만들 수 있습니다. 이렇게 하면 PBX (개인 브랜치 교환) interoperational 시나리오에서 특히 유용한 엔터프라이즈 음성 인프라에 대 한 추가 탄력성을 제공 합니다. 

트렁크가 정의 되 면 경로에 연결 되어 있어야 합니다. 트렁크를 경로에 연결 하려면 토폴로지 작성기에서 트렁크에 대 한 간단한 이름을 정의 합니다. 이 간단한 이름은 비즈니스용 Skype Server 제어판에서 트렁크 이름으로 사용 되며, trunks 연결 될 수 있습니다. 간단한 트렁크 이름을 비즈니스용 Skype 서버 관리 셸에서의 게이트웨이 이름으로 사용 합니다.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

관리자는 중재 서버와 연결 된 기본 트렁크를 선택 해야 합니다. 토폴로지 작성기에서 연결 된 중재 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다. 중재 서버의 기본 게이트웨이를 지정 합니다. 

다음 다이어그램에서는 각 중재 서버 및 게이트웨이에 대해 정의 된 여러 trunks를 보여 줍니다. 

![여러 트렁크 과제](../../media/multiple-trunk-assignments.jpg)
