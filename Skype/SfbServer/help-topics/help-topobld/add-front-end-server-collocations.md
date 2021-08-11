---
title: 프론트 엔드 서버 병설 추가
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Enterprise Edition 배포의 경우 A/V 회의 서비스가 프런트 엔드 풀에 배치됩니다. 또한 중재 서버를 프런트 엔드 풀에 배치하거나 독립 실행형 서버로 배포할 수 있습니다. 회의를 사용하도록 설정하면 A/V 회의 서비스가 항상 함께 함께 사용됩니다.
ms.openlocfilehash: 496264b412e9caabb99cc8249d6933be72bcd10364eaed752b9e1921140d2868
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321730"
---
# <a name="add-front-end-server-collocations"></a>프론트 엔드 서버 병설 추가

Enterprise Edition 배포의 경우 A/V 회의 서비스가 프런트 엔드 풀에 배치됩니다. 또한 중재 서버를 프런트 엔드 풀에 배치하거나 독립 실행형 서버로 배포할 수 있습니다. 회의를 사용하도록 설정하면 A/V 회의 서비스가 항상 함께 함께 사용됩니다.

> [!NOTE]
> **기능 선택** 페이지에서 **회의** 가 선택되어 있으면 A/V 회의 서비스는 필수입니다. Enterprise Edition 프런트 엔드 풀은 함께 있는 A/V 회의 서비스를 사용하게 됩니다. 회의가 선택되어 있지 않으면 A/V 회의 서비스 배치를 사용할 수 없습니다.

Standard Edition 프런트 엔드 서버 또는 Enterprise Edition 프런트 엔드 풀에 중재 서버 역할을 배치할 수 있습니다. 미디어 우회 및 DNS(Domain Name System) 부하 분산을 지원하는 적격한 PSTN(Public Switched Telephone Network) 게이트웨이에 직접 SIP 연결을 배포하는 경우 독립 실행형 중재 서버 풀이 필요하지 않습니다. 적격 게이트웨이가 중재 서버 풀로 DNS 부하 분산을 할 수 있으며 풀의 모든 중재 서버에서 트래픽을 수신할 수 있기 때문에 독립 실행형 중재 서버 풀은 필요하지 않습니다. 또한 다음 조건이 충족되는 한 IP-PBXs 배포하거나 인터넷 전화 통신 서버 공급자의 SBC(Session Border Controller)에 연결할 때도 중재 서버를 프런트 엔드 풀에 배치하는 것이 좋습니다.

- IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.

- IP-PBX 또는 SBC가 풀의 중재 서버에서 트래픽을 수신하도록 구성되었고 풀의 모든 중재 서버에 트래픽을 단일 방식으로 라우팅할 수 있습니다.

Microsoft Lync Server 2013 계획 도구를 사용하여 중재 서버를 함께 배포하려는 프런트 엔드 풀이 부하를 처리할 수 있는지 여부를 평가할 수 있습니다. 사용자 환경에서 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.

일반적으로 조직에 고가용성 및 확장성 요구 사항이 있는 경우 중재 서버를 함께 두지 않는 것이 좋습니다. Enterprise Edition 배포에서 프런트 엔드 풀에 이러한 서버 역할을 배치하는 방법에 대한 자세한 내용은 배포 설명서의 [프런트 엔드 풀 정의 및 구성](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)을 참조하십시오. A/V 회의 기능 및 구성 요소에 대한 자세한 내용은 계획 설명서의 [회의 계획](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)을 참조하십시오. 중재 서버를 Enterprise Voice 구성 요소에 대한 자세한 내용은 계획 설명서에서 [Plan for Enterprise Voice in 비즈니스용 Skype 서버 2015을](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) 참조하십시오.