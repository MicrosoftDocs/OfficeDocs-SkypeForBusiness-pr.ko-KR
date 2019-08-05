---
title: 프런트 엔드 서버 Collocations 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Enterprise Edition 배포의 경우 A/V 회의 서비스는 프런트 엔드 풀에 collocated 됩니다. 또한 프런트 엔드 풀에서 중재 서버를 collocate 독립 실행형 서버로 배포할 수 있습니다. 회의를 사용 하는 경우 A/V 회의 서비스는 항상 collocated.
ms.openlocfilehash: e01605df3dd0082105a05576b3df821688814d1c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196934"
---
# <a name="add-front-end-server-collocations"></a>프런트 엔드 서버 Collocations 추가

Enterprise Edition 배포의 경우 A/V 회의 서비스는 프런트 엔드 풀에 collocated 됩니다. 또한 프런트 엔드 풀에서 중재 서버를 collocate 독립 실행형 서버로 배포할 수 있습니다. 회의를 사용 하는 경우 A/V 회의 서비스는 항상 collocated.

> [!NOTE]
> **기능 선택** 페이지에서 **회의** 를 선택한 경우 A/V 회의 서비스가 필요 합니다. Enterprise Edition 프런트 엔드 풀은 collocated A/V 회의 서비스를 사용 합니다. 회의를 선택 하지 않은 경우 Collocate A/V 회의 서비스를 사용할 수 없게 됩니다.

Standard Edition 프런트 엔드 서버 또는 Enterprise Edition 프런트 엔드 풀에서 중재 서버 역할을 collocate 수 있습니다. 직접 SIP 연결을 미디어 우회 및 DNS (Domain Name System) 부하 분산을 지 원하는 적격 PSTN (공개 교환 전화 네트워크) 게이트웨이에 배포 하는 경우 독립 실행형 중재 서버 풀이 필요 하지 않습니다. 자격 있는 게이트웨이는 중재 서버 풀에 DNS 부하 분산을 사용할 수 있고 풀의 모든 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다. 또한 다음 조건 중 하나가 충족 되는 경우 IP Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 SBC (세션 경계 컨트롤러)에 연결 된 경우에는 프런트 엔드 풀에 중재 서버를 collocate 하는 것이 좋습니다.

- IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.

- IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.

계획 도구를 사용 하 여 중재 서버를 collocate 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 환경이 이러한 요구 사항을 충족 하지 못하는 경우에는 독립 실행형 중재 서버 풀을 배포 해야 합니다.

일반적으로 조직에 고가용성 및 확장성 요구 사항이 있는 경우 중재 서버의 위치를 조정 하는 것은 권장 되지 않습니다. Enterprise Edition 배포의 프런트 엔드 풀에서 이러한 서버 역할을 collocating 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [프런트 엔드 풀 정의 및 구성을](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) 참조 하세요. A/V 회의 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서의 [회의 계획](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) 을 참조 하세요. 중재 서버를 비롯 한 Enterprise Voice 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서의 비즈니스용 [Skype 서버에서 Enterprise Voice 계획](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 을 참조 하세요.


