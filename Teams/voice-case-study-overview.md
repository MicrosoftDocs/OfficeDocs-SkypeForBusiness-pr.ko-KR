---
title: 팀 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786086"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a>Contoso 사례 연구: 팀 음성 마이그레이션 개요

이 문서에서는 조직에 대 한 팀 음성 솔루션을 구현 하는 가상의 여러 국립 기업, Contoso에 대 한 사례 연구를 소개 합니다.

Contoso는 네트워킹, id, Windows 10 Enterprise, Office 365 ProPlus, 모바일 장치 관리, 정보 보호, 보안, 비즈니스용 Skype에서 팀, 전화 시스템, 오디오 회의에 대 한 주요 디자인 결정과 구현 세부 사항을 해결 365 했습니다.  

이 문서에서는 Contoso가 통합 커뮤니케이션, 공동 작업 및 음성에 대 한 팀에 온-프레미스 사용자를 마이그레이션한 방법에 대해 설명 합니다. Contoso에서 Microsoft 클라우드 서비스를 사용 하 여 디지털 변환을 가속화 하는 방법에 대 한 자세한 내용은 [contoso 사례 연구 개요](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)부터 시작 하 여 모든 핵심 문서를 참조 하세요.

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

핵심 문서에서 다음에 대 한 정보를 찾을 수 있습니다.  

- Contoso의 IT 인프라 요구 사항
- Lan
- Identity
- Windows 10 Enterprise
- Office 365 Pro Plus
- 모바일 장치 관리
- 정보 보호
- Microsoft 365 엔터프라이즈 보안 요약
- 상위 보안 프로젝트의 팀
- 매우 기밀 디지털 자산에 대 한 SharePoint Online 사이트

업그레이드를 계획 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 업그레이드 시작](upgrade-start-here.md)을 사용 하 여 시작 하는 것이 좋습니다.

## <a name="contoso-business-goals-for-teams"></a>Contoso 비즈니스 목표 팀

통합 커뮤니케이션, 공동 작업 및 목소리를 위해 온-프레미스 사용자를 팀으로 마이그레이션하기 위해 Contoso는 다음 비즈니스 목표를 결정 했습니다.

- 팀의 협력 

  Contoso의 통합 커뮤니케이션 및 공동 작업 팀은 안전한 내부 및 외부 공동 작업을 제어 하 고 사용 하도록 올바른 정책으로 팀을 설정 했습니다. 

- 비즈니스용 Skype에서 Teams로의 업그레이드 

  비즈니스용 Skype는 Contoso 내에 광범위 하 게 배포 되었습니다. Contoso는 레거시 시스템을 이동 해야 하므로 Skype for Business 사용자를 팀으로 업그레이드 하기로 결정 했습니다. 자세한 내용은 [Contoso 사례 연구: 팀 업그레이드 계획](voice-case-study-migration-plan.md)을 참조 하세요.

- 전화 시스템  

  Enterprise voice를 사용 하는 비즈니스용 Skype는 Contoso 내에 광범위 하 게 배포 되었습니다. 중재 서버에 대 한 다음 홉 인 레거시 시스템을 이동 해야 하는 경우 Contoso는 비즈니스용 Skype enterprise voice 사용자를 전화 시스템으로 마이그레이션 했습니다. Contoso 사이트는 Microsoft 통화 요금제, 전화 시스템 다이렉트 라우팅 또는 두 가지 조합을 사용 했습니다. 자세한 내용은 [Contoso 사례 연구: 전화 시스템](voice-case-study-phone-system.md)을 참조 하세요.

- 위치 기반 라우팅 

  전화 통신 규제 국가에서 office 위치를 사용 하는 경우 Contoso는 휴대폰 시스템 배포의 비즈니스용 Skype에 있는 위치 기반 라우팅을 다시 만들어야 했습니다. 자세한 내용은 [Contoso 사례 연구: 위치 기반 회람](voice-case-study-location-based-routing.md)을 참조 하세요.

- 비상 전화 

  다이렉트 라우팅이 구현 되는 경우 Contoso는 승인 된 제 3 자에 게 긴급 통화를 설정 합니다. 자세한 내용은 [Contoso 사례 연구: 비상 전화](voice-case-study-emergency-calling.md)를 참조 하세요.

- 오디오 회의 

  Contoso는 자신의 SIP 트렁크에 호스트 된 오디오 회의 서비스 번호를 PSTN 공급자에 게 설정 합니다. 자세한 내용은 [Contoso 사례 연구: 오디오 회의](voice-case-study-audio-conferencing.md)를 참조 하세요. 

- 로컬 미디어 최적화 

  Contoso는 원격 사이트에서 사용한 Microsoft 전화 시스템에 한 개의 직접 경로 트렁크이 있는 위치에서 로컬 미디어 최적화를 활용 했습니다. 자세한 내용은 [로컬 미디어 최적화 계획](direct-routing-media-optimization.md) 및 [로컬 미디어 최적화 구성을](direct-routing-media-optimization-configure.md)참조 하세요.

- 자동 전화 교환 및 통화 대기열

  Covid-19의 결과로 Contoso는 직원이 원격으로 작업 하는 동안 receptionist 지원을 제공 하려고 했습니다. Contoso는 자동 전화 교환 및 통화 대기열을 사용 하 여 receptionist의 전화 번호로 걸려오는 전화를 관리 합니다. 자세한 내용은 [Contoso 케이스 스터디: 자동 전화 교환 및 통화 대기열](voice-case-study-call-queues.md)을 참조 하세요.  


