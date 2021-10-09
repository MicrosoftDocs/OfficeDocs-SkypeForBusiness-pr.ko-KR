---
title: 연산자 커넥트
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 요구 사항 및 배포 계획과 커넥트 운영자에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf1e158eb491f0b4b4f2df19c4aa7ebe46f08950
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249670"
---
# <a name="plan-for-operator-connect"></a>연산자에 대한 커넥트

운영자 커넥트 는 PSTN(공용 전환 전화 네트워크)에 연결 및 연결과 연결 Teams 전화 시스템. 음성 솔루션 및 PSTN Teams 옵션에 대한 자세한 [](cloud-voice-landing-page.md) 내용은 음성 솔루션 및 PSTN Teams 계획 [을 참조하세요.](pstn-connectivity.md)

이 문서에서는 이점 및 요구 사항을 설명하고 Microsoft Operator 커넥트 링크를 제공합니다.  운영자 커넥트 조직에 적합한 솔루션으로 결정한 경우 이 문서를 [읽은](operator-connect-configure.md)후 연산자 커넥트.  

## <a name="benefits"></a>이점

연산자 커넥트 경우 기존 연산자가 Microsoft 연산자 커넥트 프로그램에 참여하는 경우 PSTN 호출을 호출하는 서비스를 관리할 수 Teams. 연산자 커넥트 프로그램은 다음과 같은 이점을 제공합니다.

- **기존 계약을 활용하거나 새 연산자를 찾습니다.** 원하는 운영자 및 계약을 유지하거나, 비즈니스 요구 사항을 충족하기 위해 참여 연산자의 선택에서 새 연산자를 선택합니다.

- **운영자 관리 인프라입니다.** 운영자는 PSTN 호출 서비스 및 SBC(세션 테두리 컨트롤러)를 관리하므로 하드웨어 구매 및 관리를 저장할 수 있습니다.

- **더 빠르고 쉽게 배포할 수 있습니다.** 운영자에 빠르게 연결하고 사용자에게 전화 번호를 할당할 수 있습니다. 모든 Teams 있습니다.

- **향상된 지원 및 안정성.** 운영자는 지원 서비스를 개선하기 위해 기술 지원 및 공유 서비스 수준 계약을 제공하고, Azure에서 제공하는 직접 피어링은 향상된 안정성을 위해 일대일 네트워크 연결을 만듭니다.

## <a name="requirements"></a>요구 사항

 운영자는 커넥트 경우 조직에 적합한 솔루션일 수 있습니다.

- Microsoft 통화 요금제는 지리적 위치에서 사용할 수 없습니다.
- 기본 설정 연산자는 Microsoft Operator 커넥트 참여자입니다.
- 새 연산자를 찾아 통화에서 Teams.

연산자에서 전화 번호 할당을 사용하도록 설정하려면 커넥트 다음을 수행해야 합니다.

- Teams 전화 라이선스가 부여됩니다. 자세한 내용은 사용자에 대한 추가 [전화 시스템?](what-is-phone-system-in-office-365.md) 및 Teams 추가 기능 라이선스 할당 을 [참조하세요.](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- TeamsOnly 모드에서. 사용자가 TeamsOnly 모드로 전환해야 하지만 전체 조직은 그렇지 않습니다. 자세한 내용은 공존 및 상호 Microsoft Teams 비즈니스용 Skype 이해를 [참조합니다.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

Microsoft Operator 커넥트 프로그램에 참여하는 운영자 목록과 해당 서비스를 사용할 수 있는 국가 또는 지역은 Microsoft 365 운영자 커넥트 [디렉터리를 참조하세요.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)
