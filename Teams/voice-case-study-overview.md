---
title: Teams Contoso 사례 연구 개요
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
description: 'Teams 기업에 대한 음성 사례 연구: 음성 마이그레이션 개요'
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae8a09ab48215b1915c06e46b3d6a3a693958621
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587177"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 사례 연구: Teams 음성 마이그레이션 개요

이 문서에서는 다국적 기업인 Contoso가 조직에 대한 음성 솔루션을 구현하는 Teams 사례 연구를 소개합니다.

Contoso는 Microsoft 365 Enterprise, ID, Windows 10 Enterprise, Office 365 ProPlus, 모바일 디바이스 관리, 정보 보호, 보안, 업그레이드, 비즈니스용 Skype, Teams, 오디오 회의 및 오디오 회의에 전화 시스템 주요 디자인 결정 및 구현 세부 정보를 배포하고 해결했습니다.  

이 문서에서는 Contoso가 통합된 통신, 공동 작업 및 음성을 위해 해당 Teams 사용자를 마이그레이션하는 방법에 대해 중점적으로 다를 수 있습니다. Microsoft의 클라우드 서비스를 사용하여 Contoso가 디지털 변환을 가속화하는 방법에 대한 배경 정보는 [Contoso](/microsoft-365/enterprise/contoso-case-study)사례 연구 개요부터 시작하는 모든 핵심 문서를 참조하세요.

[https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

핵심 문서에서는 다음에 대한 정보를 찾을 수 있습니다.  

- Contoso의 IT 인프라 요구
- 네트워킹
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- 모바일 디바이스 관리
- 정보 보호
- 보안 Microsoft 365 Enterprise 요약
- 비밀 프로젝트 팀
- SharePoint 기밀이 높은 디지털 자산을 위한 온라인 사이트

업그레이드 계획에 대한 자세한 내용은 업그레이드 시작 을 Microsoft Teams [합니다.](upgrade-start-here.md)

## <a name="contoso-business-goals-for-teams"></a>Contoso 비즈니스 목표에 Teams

Contoso는 통합된 통신, 공동 작업 및 음성을 Teams 사용자로 마이그레이션하기 위해 다음 비즈니스 목표를 결정했습니다.

- Teams 활성화 

  Contoso의 통합 통신 및 공동 작업 팀을 통해 Teams 및 외부 공동 작업을 안전하게 관리하고 사용하도록 설정하는 올바른 정책을 사용할 수 있습니다. 

- 비즈니스용 Skype에서 Teams로의 업그레이드 

  비즈니스용 Skype 배포가 Contoso 내에서 널리 배포됩니다. 레거시 시스템을 벗어날 필요가 있는 Contoso는 사용자 비즈니스용 Skype 업그레이드하기로 Teams. 자세한 내용은 [Contoso 사례 연구: Teams 계획 을 참조하세요.](voice-case-study-migration-plan.md)

- 전화 시스템  

  비즈니스용 Skype 음성을 통해 Contoso 내에서 널리 배포됩니다. Contoso는 미디에이션 서버의 다음 홉이던 레거시 시스템을 벗어날 필요가 비즈니스용 Skype 엔터프라이즈 음성 사용자를 전화 시스템. Contoso 사이트는 Microsoft 통화 계획, 전화 시스템 라우팅 또는 둘 다의 조합을 사용했습니다. 자세한 내용은 [Contoso 사례 연구:](voice-case-study-phone-system.md)전화 시스템.

- 위치 기반 라우팅 

  전화 통신 규제 국가에 있는 사무실 위치를 사용하려면 Contoso는 배포에 Location-Based 있는 비즈니스용 Skype 라우팅을 전화 시스템 필요했습니다. 자세한 내용은 Contoso 사례 연구: Location-Based [참조하세요.](voice-case-study-location-based-routing.md)

- 비상 전화 

  직접 라우팅이 구현된 경우 Contoso는 승인된 타사를 통해 긴급 호출을 설정했습니다. 자세한 내용은 [Contoso 사례 연구: 긴급 호출 을 참조하세요.](voice-case-study-emergency-calling.md)

- 오디오 회의 

  Contoso는 해당 SIP 트렁크에서 호스트된 오디오 회의 서비스 번호를 해당 PSTN 공급자에 설정했습니다. 자세한 내용은 [Contoso 사례 연구: 오디오 회의 를 참조하세요.](voice-case-study-audio-conferencing.md) 

- 로컬 미디어 최적화 

  Contoso는 원격 사이트에서 활용된 시스템으로의 직접 경로 트렁크가 Microsoft 전화 위치에서 로컬 미디어 최적화를 활용했습니다. 자세한 내용은 [로컬](direct-routing-media-optimization.md) 미디어 최적화 계획 및 로컬 미디어 최적화 구성 [을 참조하세요.](direct-routing-media-optimization-configure.md)

- 자동 참석자 및 통화 큐

  Covid-19의 결과로 Contoso는 직원들이 원격으로 작업하는 동안 수신 직원 지원을 제공하기를 원했습니다. Contoso는 자동 참석자 및 통화 큐를 사용하여 수신 관리자의 전화 번호로 들어오는 통화를 관리했습니다. 자세한 내용은 [Contoso 사례 연구: 자동 참석자 및 통화 큐 를 참조하세요.](voice-case-study-call-queues.md)
