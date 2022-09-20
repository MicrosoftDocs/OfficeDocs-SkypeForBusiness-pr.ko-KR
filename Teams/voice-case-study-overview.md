---
title: Teams 음성 Contoso 사례 연구 개요
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
description: '다국적 기업을 위한 Teams 음성 사례 연구: 음성 마이그레이션 개요'
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae0d123841e57987346fae304e34bde28e4ffe84
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808629"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 사례 연구: Teams 음성 마이그레이션 개요

이 문서에서는 가상의 다국적 기업인 Contoso가 조직을 위한 Teams 음성 솔루션을 구현하는 방법에 대한 사례 연구를 소개합니다.

Contoso는 Microsoft 365 Enterprise 배포하고 네트워킹, ID, Windows 10 Enterprise, Office 365 ProPlus, 모바일 디바이스 관리, 정보 보호, 보안, 업그레이드에 대한 주요 디자인 결정 및 구현 세부 정보를 해결했습니다. Teams, 전화 시스템 및 오디오 회의에 비즈니스용 Skype.  

이 문서에서는 Contoso가 통합 커뮤니케이션, 공동 작업 및 음성을 위해 온-프레미스 사용자를 Teams로 마이그레이션하는 방법에 중점을 둡니다. Contoso가 Microsoft의 클라우드 서비스를 사용하여 디지털 변환을 가속화하는 방법에 대한 배경 정보는 [Contoso 사례 연구 개요](/microsoft-365/enterprise/contoso-case-study)부터 시작하는 모든 핵심 문서를 참조하세요.

[https://learn.microsoft.com/microsoft-365/enterprise/contoso-case-study](/microsoft-365/enterprise/contoso-case-study) 

핵심 문서에서는 다음에 대한 정보를 찾을 수 있습니다.  

- Contoso의 IT 인프라 요구 사항
- 네트워킹
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- 모바일 디바이스 관리
- 정보 보호
- Microsoft 365 Enterprise 보안 요약
- 일급 비밀 프로젝트 팀
- 기밀 디지털 자산에 대한 SharePoint Online 사이트

업그레이드 계획에 대한 자세한 내용은 [Microsoft Teams 업그레이드 시작부터 시작하는 것이](upgrade-start-here.md) 좋습니다.

## <a name="contoso-business-goals-for-teams"></a>Teams용 Contoso 비즈니스 목표

Contoso는 통합 커뮤니케이션, 공동 작업 및 음성을 위해 온-프레미스 사용자를 Teams로 마이그레이션하기 위해 다음 비즈니스 목표를 결정했습니다.

- Teams 사용 

  Contoso의 통합 커뮤니케이션 및 공동 작업 팀은 올바른 정책을 통해 Teams가 안전한 내부 및 외부 공동 작업을 제어하고 사용하도록 설정할 수 있도록 했습니다. 

- 비즈니스용 Skype에서 Teams로의 업그레이드 

  비즈니스용 Skype Contoso 내에 널리 배포되었습니다. Contoso는 레거시 시스템을 전환해야 하므로 비즈니스용 Skype 사용자를 Teams로 업그레이드하기로 결정했습니다. 자세한 내용은 [Contoso 사례 연구: Teams 업그레이드 계획을](voice-case-study-migration-plan.md) 참조하세요.

- 전화 시스템  

  엔터프라이즈 음성을 사용한 비즈니스용 Skype Contoso 내에 널리 배포되었습니다. Contoso는 조정 서버의 다음 홉이었던 레거시 시스템을 전환해야 했기 때문에 비즈니스용 Skype 엔터프라이즈 음성 사용자를 Phone System으로 마이그레이션했습니다. Contoso 사이트에서는 Microsoft 통화 플랜, 전화 시스템 직접 라우팅 또는 둘 다의 조합을 사용했습니다. 자세한 내용은 [Contoso 사례 연구: 전화 시스템을 참조하세요](voice-case-study-phone-system.md).

- 위치 기반 라우팅 

  전화 통신 규제 국가에서 사무실 위치를 사용하여 Contoso는 전화 시스템 배포에서 비즈니스용 Skype 있는 Location-Based 라우팅을 다시 만들어야 했습니다. 자세한 내용은 [Contoso 사례 연구: Location-Based 라우팅을 참조하세요](voice-case-study-location-based-routing.md).

- 비상 전화 

  직접 라우팅이 구현된 경우 Contoso는 승인된 제3자와 긴급 통화를 설정합니다. 자세한 내용은 [Contoso 사례 연구: 긴급 통화(Emergency Calling](voice-case-study-emergency-calling.md))를 참조하세요.

- 오디오 회의 

  Contoso는 SIP 트렁크에 호스트된 오디오 회의 서비스 번호를 PSTN 공급자에 설정했습니다. 자세한 내용은 [Contoso 사례 연구: 오디오 회의를 참조하세요](voice-case-study-audio-conferencing.md). 

- 로컬 미디어 최적화 

  Contoso는 원격 사이트에서 활용한 Microsoft Phone 시스템에 대한 직접 경로 트렁크가 하나 있는 위치에서 로컬 미디어 최적화를 활용했습니다. 자세한 내용은 [로컬 미디어 최적화 계획](direct-routing-media-optimization.md) 및 [로컬 미디어 최적화 구성](direct-routing-media-optimization-configure.md)을 참조하세요.

- 자동 전화 교환 및 통화 큐

  Covid-19의 결과로 Contoso는 직원이 원격으로 작업하는 동안 접수원 지원을 제공하고자 했습니다. Contoso는 자동 전화 교환 및 통화 큐를 사용하여 접수원의 전화 번호로 들어오는 통화를 관리했습니다. 자세한 내용은 [Contoso 사례 연구인 자동 전화 교환 및 통화 큐를 참조하세요](voice-case-study-call-queues.md).
