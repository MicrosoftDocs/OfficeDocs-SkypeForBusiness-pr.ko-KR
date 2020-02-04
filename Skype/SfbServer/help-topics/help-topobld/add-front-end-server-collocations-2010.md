---
title: 프론트 엔드 서버 병설 2010 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Enterprise Edition 배포의 경우 프런트 엔드 풀에서 A/V 회의 서비스, 중재 서버 또는 둘 다를 collocate 하거나 독립 실행형 서버로 배포할 수 있습니다. 표준 버전 서버 배포의 경우, 회의를 사용 하도록 설정 하면 A/V 회의 서비스는 항상 collocated.
ms.openlocfilehash: 371643491438b7f1711c2a023f1b8a6d7a39525c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685151"
---
# <a name="add-front-end-server-collocations-2010"></a>프론트 엔드 서버 병설 2010 추가

Enterprise Edition 배포의 경우 프런트 엔드 풀에서 A/V 회의 서비스, 중재 서버 또는 둘 다를 collocate 하거나 독립 실행형 서버로 배포할 수 있습니다. 표준 버전 서버 배포의 경우, 회의를 사용 하도록 설정 하면 A/V 회의 서비스는 항상 collocated.

> [!NOTE]
> **기능 선택** 페이지에서 **회의** 를 선택한 경우 A/V 회의 서비스가 필요 합니다. Enterprise Edition 프런트 엔드 풀은 collocated A/V 회의 서비스 또는 독립 실행형 A/V 회의 풀을 사용할 수 있습니다. 회의를 선택 하지 않은 경우 Collocate A/V 회의 서비스를 사용할 수 없게 됩니다.

Standard Edition 프런트 엔드 서버 또는 Enterprise Edition 프런트 엔드 풀에서 중재 서버 역할을 collocate 수 있습니다. 직접 SIP 연결을 미디어 우회 및 DNS (Domain Name System) 부하 분산을 지 원하는 적격 PSTN (공개 교환 전화 네트워크) 게이트웨이에 배포 하는 경우 독립 실행형 중재 서버 풀이 필요 하지 않습니다. 자격 있는 게이트웨이는 중재 서버 풀에 DNS 부하 분산을 사용할 수 있고 풀의 모든 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다. 또한 다음 조건 중 하나가 충족 되는 경우 IP Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 SBC (세션 경계 컨트롤러)에 연결 된 경우에는 프런트 엔드 풀에 중재 서버를 collocate 하는 것이 좋습니다.

- IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.

- IP-PBX 또는 SBC는 풀의 중재 서버에서 트래픽을 수신 하도록 구성 되며 풀의 모든 중재 서버에 일관 된 트래픽을 라우팅할 수 있습니다.

Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 collocate 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 환경이 이러한 요구 사항을 충족 하지 못하는 경우에는 독립 실행형 중재 서버 풀을 배포 해야 합니다.

일반적으로 A/V 회의 서버 또는 중재 서버의 위치를 사용 하지 않는 것이 좋습니다. 조직에서 엔터프라이즈 버전 배포의 프런트 엔드 풀에 이러한 서버 역할을 collocating 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [프런트 엔드 풀 정의 및 구성](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) requirementsFor을 참조 하세요. A/V 회의 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서의 [회의 계획](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) 을 참조 하세요. 중재 서버를 비롯 한 Enterprise Voice 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서의 비즈니스용 [Skype Server 2015의 Enterprise Voice 계획](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 을 참조 하세요.


