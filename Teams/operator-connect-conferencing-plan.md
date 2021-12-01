---
title: 운영자 커넥트 계획
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 10/28/2021
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
description: 요구 사항 및 배포 계획과 커넥트 운영자 회의에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d910fd9d464d1c4ff452da70a3bde039e4748123
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257541"
---
# <a name="plan-for-operator-connect-conferencing"></a>운영자 커넥트 계획

Microsoft Audio Conferencing은 PSTN(공용 전환 전화 네트워크) 전화 번호를 사용하여 전화 회의에 전화를 걸고 회의에서 전화를 걸 수 있는 기능을 제공합니다.  참가자는 Microsoft Teams 회의 브리지를 사용하여 모임에 참가합니다.

운영자 커넥트 회의 기능을 사용하여 조직은 타사 운영자의 전화 번호를 사용하여 모임에 참가할 수 Microsoft Teams 있습니다. 현재 운영자가 Microsoft 운영자 커넥트 프로그램의 일부인 경우 운영자의 전화 번호를 오디오 회의 브리지에 추가하고 모임에 참가할 수 있습니다.

운영자 커넥트 회의 기능이 없는 경우 조직은 Microsoft에서 제공하는 전화 번호만 오디오 회의 브리지에 사용할 수 있습니다.

>[!NOTE]
>Microsoft Operator 커넥트 프로그램의 일부인 전화 번호 공급자는 이 문서에서 "연산자"로 참조됩니다.
>
>운영자가 Microsoft Operator 커넥트 프로그램에 참여하는지 확인한 Microsoft 365 운영자 커넥트 [를 참조합니다.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)

이 문서에서는 운영자 회의 커넥트 설명합니다.

- [이점](#benefits)
- [라이선스 요구 사항 및 청구](#licensing-requirements-and-billing)
- [Microsoft 오디오 회의에 대한 추가 정보](#additional-information-on-microsoft-audio-conferencing)

연산자 회의 구성에 대한 자세한 내용은 커넥트 회의 및 커넥트 [구성을 참조하세요.](operator-connect-conferencing-configure.md)

조직의 일부 사용자가 PSTN 전화 번호로 외부 통화를 해야 하는 경우 여전히 통화 계획이 필요합니다. 외부 PSTN 연결에 타사 연산자 사용에 대한 자세한 내용은 운영자에 대한 계획을 [커넥트.](operator-connect-plan.md)

## <a name="benefits"></a>이점

운영자 커넥트 회의는 다음과 같은 이점을 제공합니다.

- **운영자와 Microsoft 간에 전화 번호를 유연하게 할당합니다.** Microsoft와 운영자의 전화 번호(Microsoft 오디오 회의 표준 구독만 사용)를 사용하거나 운영자의 전화 번호만 사용하세요(운영자 회의 라이선스만 커넥트 사용).

- **운영자 관리 인프라입니다.**   운영자는 SBC(Session Border Controllers) 및 Microsoft와의 상호 연결 기능을 관리하여 추가 하드웨어 구매 및 관리에서 절약할 수 있습니다.

- **더 빠르고 쉽게 배포할 수 있습니다.**   운영자에게 빠르게 연결하고 관리 센터에서 오디오 회의 브리지에 전화 Teams 할당합니다.

- **향상된 지원 및 안정성.**   운영자는 서비스 지원을 개선하기 위해 기술 지원 및 공유 서비스 수준 계약을 제공하고, Azure에서 제공하는 직접 피어링은 향상된 안정성을 위해 일대일 네트워크 연결을 만듭니다.

운영자 커넥트 회의는 조직에 적합한 솔루션일 수 있습니다.

- 기존 전화 **번호 공급자와** 계약을 유지하려는 경우

- 기존 Microsoft  오디오 회의 브리지의 전역 범위를 확장하려는 경우

- 새 전화 번호 **공급자에서 오디오** 회의에 대한 전화 번호를 원본으로 사용하려는 경우

- **지리적 위치에서 Microsoft 오디오 회의를 사용할 수 없습니다.**

- 유료 전화 번호 사용 및 구독에 포함되지 않은 국가의 전화 번호로 Teams 아웃바운드 통화와 같은 분당 유료 모델을 사용하여 오디오 회의 서비스에 대한 연산자를 활용하려는 경우

## <a name="licensing-requirements-and-billing"></a>라이선스 요구 사항 및 청구

운영자 회의 커넥트 모임에 참가해야 하는 사용자는 Microsoft 오디오 회의 표준 구독 또는 Microsoft 운영자 회의 커넥트 라이선스가 할당되어 있어야 합니다.

### <a name="audio-conferencing-standard-subscription"></a>오디오 회의 표준 구독

Microsoft Audio Conferencing Standard 구독은 라이선스에 대한 추가 기능으로 Microsoft Teams 수 있으며 구독 및 구독에 Microsoft 365 E5 Office 365 E5 있습니다.

오디오 회의 표준 구독을 사용하면 구독자가 Microsoft의 전화 번호를 사용할 수 있으며 운영자의 번호로 오디오 회의 브리지를 확장할 수 있습니다. 구독자는 Microsoft를 통해 라우팅할 Teams 모임에서 어떤 아웃바운드 호출을 호출하고 운영자를 통해 라우팅할지 결정할 수 있습니다.

자세한 내용은 운영자 커넥트 구성을 [**참조하세요.**](operator-connect-conferencing-configure.md)

### <a name="operator-connect-conferencing-license"></a>운영자 커넥트 회의 라이선스

Microsoft 운영자 커넥트 회의 라이선스를 추가 기능으로 획득할 수 Microsoft Teams 있습니다.

운영자 커넥트 회의 라이선스를 사용하면 구독자가 운영자의 전화 번호를 사용할 수 있지만 Microsoft의 전화 번호는 포함하지 않습니다. 모든 아웃바운드 Teams 연산자를 통해 라우팅해야 합니다.

자세한 내용은 운영자 커넥트 구성을 [**참조하세요.**](operator-connect-conferencing-configure.md)

>[!Note]
>모임 참가자는 사용자가 운영자 회의 기능을 커넥트 모임에 참가하기 위해 오디오 회의 표준 구독 라이선스 또는 운영자 커넥트 필요하지 않습니다.

운영자 커넥트 회의를 통해 Microsoft는 조직에서 사용하는 오디오 회의 라이선스 유형, Microsoft 오디오 회의 또는 운영자 커넥트 회의 및 Microsoft에서 제공하는 모든 전화 번호 사용에 따라 조직에 청구합니다.

운영자는 제공한 연산자 및 회의 커넥트 요금을 조직에 청구합니다.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Microsoft 오디오 회의에 대한 추가 정보

Microsoft 오디오 회의를 통해 참가자는 PSTN Microsoft Teams 전화 접속하거나 PSTN 전화 번호로 전화를 걸고 모임에 참가할 수 있습니다. 조직에서 사용할 수 있는 Microsoft 오디오 회의 기능에 대한 자세한 내용은 에서 오디오 [회의를](audio-conferencing-in-office-365.md)Microsoft 365.
