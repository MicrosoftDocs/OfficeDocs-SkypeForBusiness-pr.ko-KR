---
title: 프론트 엔드 서버 병설 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Enterprise Edition 배포의 경우 A/V 회의 서비스가 프런트 엔드 풀에 배치 된 됩니다. 또한 프런트 엔드 풀에서 중재 서버를 함께 배치할 하거나 독립 실행형 서버로 배포할 수 있습니다. 회의를 사용 하도록 설정 하는 경우 A/V 회의 서비스는 항상 배치 된입니다.
ms.openlocfilehash: 015570d42482b0e4f34e6679bab27aa2c40f2f88
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216509"
---
# <a name="add-front-end-server-collocations"></a>프론트 엔드 서버 병설 추가

Enterprise Edition 배포의 경우 A/V 회의 서비스가 프런트 엔드 풀에 배치 된 됩니다. 또한 프런트 엔드 풀에서 중재 서버를 함께 배치할 하거나 독립 실행형 서버로 배포할 수 있습니다. 회의를 사용 하도록 설정 하는 경우 A/V 회의 서비스는 항상 배치 된입니다.

> [!NOTE]
> **기능 선택** 페이지에서 **회의**가 선택되어 있으면 A/V 회의 서비스는 필수입니다. Enterprise Edition 프런트 엔드 풀은 배치 된 A/V 회의 서비스를 사용 합니다. 회의가 선택되어 있지 않으면 A/V 회의 서비스 배치를 사용할 수 없습니다.

Standard Edition 프런트 엔드 서버 또는 Enterprise Edition 프런트 엔드 풀에 중재 서버 역할을 배치할 수 있습니다. 미디어 바이패스 및 DNS (Domain Name System) 부하 분산을 지 원하는 정규 PSTN (공중 전화망) 게이트웨이에 직접 SIP 연결을 배포 하는 경우 독립 실행형 중재 서버 풀을 사용할 필요가 없습니다. 정규 게이트웨이는 중재 서버 풀에 대 한 DNS 부하 분산을 가능 하 게 하 고 풀의 중재 서버에서 트래픽을 수신할 수 있으므로 독립 실행형 중재 서버 풀은 필요 하지 않습니다. 또한 다음 조건 중 하나라도 충족 되 면 IP-Pbx를 배포 하거나 인터넷 전화 통신 서버 공급자의 세션 경계 컨트롤러 (SBC)에 연결 하는 경우에도 프런트 엔드 풀에 중재 서버를 함께 배치할 것을 권장 합니다.

- IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.

- IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.

Microsoft Lync Server 2013, 계획 도구를 사용 하 여 중재 서버를 함께 배치할 프런트 엔드 풀에서 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.

일반적으로 조직에 고가용성 및 확장성 요구 사항이 있는 경우에는 중재 서버의 배치를 사용 하지 않는 것이 좋습니다. Enterprise Edition 배포에서 프런트 엔드 풀에 이러한 서버 역할을 배치하는 방법에 대한 자세한 내용은 배포 설명서의 [프런트 엔드 풀 정의 및 구성](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)을 참조하십시오. A/V 회의 기능 및 구성 요소에 대한 자세한 내용은 계획 설명서의 [회의 계획](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx)을 참조하십시오. 중재 서버를 포함 하 여 Enterprise Voice 기능 및 구성 요소에 대 한 자세한 내용은 계획 설명서에서 [비즈니스용 Skype 서버 2015의 Enterprise Voice 계획](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 을 참조 하십시오.


