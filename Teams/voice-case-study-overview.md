---
title: Teams 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701226"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 사례 연구: Teams 음성 마이그레이션 개요

이 문서에서는 Contoso가 조직에 대해 Teams 음성 솔루션을 구현한 방법에 대한 사례 연구를 소개합니다.

Contoso는 Microsoft 365 Enterprise를 배포하고 네트워킹, ID, Windows 10 Enterprise, Office 365 ProPlus, 모바일 장치 관리, 정보 보호, 보안, 비즈니스용 Skype에서 Teams로 업그레이드, 전화 시스템 및 오디오 회의에 대한 주요 디자인 결정 및 구현 세부 정보를 해결했습니다.  

이 문서에서는 Contoso가 통합 통신, 공동 작업 및 음성을 위해 해당 사용자를 Teams로 마이그레이션하는 방법을 중점적으로 다루고 있습니다. Contoso가 Microsoft의 클라우드 서비스를 사용하여 디지털 변환을 가속화하는 방법에 대한 배경 정보는 [Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)사례 연구 개요부터 시작하는 모든 핵심 문서를 참조하세요.

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

핵심 문서에서는 다음에 대한 정보를 찾을 수 있습니다.  

- Contoso의 IT 인프라 요구
- 네트워킹
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- 모바일 디바이스 관리
- 정보 보호
- Microsoft 365 Enterprise 보안 요약
- 최고 비밀 프로젝트를 위한 팀
- 기밀이 높은 디지털 자산을 위한 SharePoint Online 사이트

업그레이드 계획에 대한 자세한 내용은 Microsoft Teams 업그레이드 시작을 [시작해야 합니다.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Teams에 대한 Contoso 비즈니스 목표

Contoso는 통합 통신, 공동 작업 및 음성을 위해 해당 사용자를 Teams로 마이그레이션하기 위해 다음 비즈니스 목표를 결정했습니다.

- Teams 사용 설정 

  Contoso의 통합 커뮤니케이션 및 공동 작업 팀은 안전한 내부 및 외부 공동 작업을 관리하고 사용하도록 설정하기 위한 올바른 정책으로 Teams를 활성화했습니다. 

- 비즈니스용 Skype에서 Teams로의 업그레이드 

  비즈니스용 Skype는 Contoso 내에서 널리 배포됩니다. Contoso는 레거시 시스템으로 이전해야 하여 비즈니스용 Skype 사용자를 Teams로 업그레이드하기로 결정했습니다. 자세한 내용은 Contoso 사례 연구: Teams 업그레이드 [계획을 참조하세요.](voice-case-study-migration-plan.md)

- 전화 시스템  

  엔터프라이즈 음성이 있는 비즈니스용 Skype는 Contoso 내에서 널리 배포됩니다. Contoso는 중재 서버의 다음 홉인 레거시 시스템을 이동해야 하여 비즈니스용 Skype 엔터프라이즈 음성 사용자를 Phone System으로 마이그레이션했습니다. Contoso 사이트는 Microsoft 통화 요금제, 전화 시스템 직접 라우팅 또는 둘의 조합을 사용했습니다. 자세한 내용은 [Contoso 사례 연구: 전화 시스템을 참조하세요.](voice-case-study-phone-system.md)

- 위치 기반 라우팅 

  전화 통신 규제 국가에 있는 사무실 위치를 통해 Contoso는 전화 시스템 배포에서 비즈니스용 Skype에 Location-Based 라우팅을 다시 구축해야 합니다. 자세한 내용은 Contoso 사례 연구: Location-Based [참조하세요.](voice-case-study-location-based-routing.md)

- 비상 전화 

  직접 라우팅이 구현된 경우 Contoso는 승인된 제3자에 대한 긴급 통화를 설정했습니다. 자세한 내용은 Contoso 사례 연구: 긴급 [통화를 참조하세요.](voice-case-study-emergency-calling.md)

- 오디오 회의 

  Contoso는 SIP 트렁크에서 호스트된 오디오 회의 서비스 번호를 PSTN 공급자에 설정했습니다. 자세한 내용은 [Contoso 사례 연구: 오디오 회의를 참조하세요.](voice-case-study-audio-conferencing.md) 

- 로컬 미디어 최적화 

  Contoso는 원격 사이트에서 활용된 Microsoft Phone System에 대한 직접 경로 트렁크가 있는 위치에서 로컬 미디어 최적화를 활용했습니다. 자세한 내용은 [로컬](direct-routing-media-optimization.md) 미디어 최적화 계획 및 로컬 미디어 최적화 [구성을 참조하세요.](direct-routing-media-optimization-configure.md)

- 자동 전화 회의 및 통화 큐

  Covid-19의 결과로 Contoso는 직원이 원격으로 작업하는 동안 수신 직원 지원을 제공하기를 원했습니다. Contoso는 자동 전화 회의 및 통화 큐를 사용하여 수신 직원의 전화 번호로 수신 전화를 관리했습니다. 자세한 내용은 Contoso 사례 연구: 자동 전화 회의 및 통화 [큐를 참조하세요.](voice-case-study-call-queues.md)  


