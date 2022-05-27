---
title: 운영자 연결 회의 계획
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
description: 요구 사항 및 배포 계획과 같은 운영자 연결 회의 대해 자세히 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881df7d9bd2d2d2bcbf6775654a97066a2927250
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676020"
---
# <a name="plan-for-operator-connect-conferencing"></a>운영자 연결 회의 계획

Microsoft 오디오 회의 전화 회의에 전화를 걸고 PSTN(공중 전화망) 전화 번호를 사용하여 회의에서 전화를 걸 수 있는 기능을 제공합니다.  참가자는 오디오 전용 회의 브리지를 사용하여 Microsoft Teams 모임에 참가합니다.

운영자 연결 회의 기능을 사용하면 조직에서 타사 운영자의 전화 번호를 사용하여 Microsoft Teams 모임에 참가할 수 있습니다. 현재 운영자가 Microsoft 운영자 연결 프로그램의 일부인 경우 운영자의 전화 번호를 오디오 회의 브리지에 추가하고 이를 사용하여 모임에 참가할 수 있습니다.

운영자 연결 회의 기능이 없으면 조직은 Microsoft에서 제공하는 전화 번호만 오디오 회의 브리지에 사용할 수 있습니다.

>[!NOTE]
>Microsoft 운영자 연결 프로그램의 일부인 전화 번호 공급자는 이 문서에서 "운영자"로 참조됩니다.
>
>운영자가 Microsoft 운영자 연결 프로그램에 참여하는지 확인하려면 [Microsoft 365 운영자 연결 디렉터리를 참조하세요](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory).

이 문서에서는 운영자 연결 회의 설명합니다.

- [이점](#benefits)
- [라이선스 요구 사항 및 청구](#licensing-requirements-and-billing)
- [Microsoft 오디오 회의 대한 추가 정보](#additional-information-on-microsoft-audio-conferencing)

운영자 연결 회의 구성하는 방법에 대한 자세한 내용은 [운영자 연결 회의 구성](operator-connect-conferencing-configure.md)을 참조하세요.

조직의 일부 사용자가 PSTN 전화 번호에 외부 전화를 걸어야 하는 경우에도 통화 플랜이 필요합니다. 외부 PSTN 연결에 타사 연산자를 사용하는 방법에 대한 자세한 내용은 [운영자 연결 계획을](operator-connect-plan.md) 참조하세요.

## <a name="benefits"></a>이점

운영자 연결 회의 다음과 같은 이점을 제공합니다.

- **운영자와 Microsoft 간에 전화 번호를 유연하게 할당합니다.** Microsoft와 운영자의 전화 번호(Microsoft 오디오 회의 Standard 구독만 사용)를 사용하거나 운영자의 전화 번호만 사용합니다(운영자 연결 회의 라이선스만 있음).

- **운영자 관리형 인프라.** 운영자는 SCC(세션 테두리 컨트롤러) 및 Microsoft와의 상호 연결을 관리하여 추가 하드웨어 구매 및 관리에서 사용자를 절약합니다.

- **더 빠르고 쉽게 배포할 수 있습니다.** 운영자에게 신속하게 연결하고 Teams 관리 센터에서 오디오 회의 브리지에 전화 번호를 할당합니다.

- **향상된 지원 및 안정성.** 운영자는 서비스 지원을 개선하기 위한 기술 지원 및 공유 서비스 수준 계약을 제공하며, Azure에서 제공하는 직접 피어링으로 안정성 향상을 위해 일대일 네트워크 연결을 만듭니다.

다음과 같은 경우 운영자 연결 회의 조직에 적합한 솔루션일 수 있습니다.

- 기존 전화 번호 공급자 **와 계약을 유지** 하려고 합니다.

- 기존 Microsoft 오디오 회의 브리지의 **전역 범위를 확장** 하려고 합니다.

- 새 **전화 번호 공급자의 오디오 회의 전화 번호를 입력** 하려고 합니다.

- **지리적 위치에서 Microsoft 오디오 회의 사용할 수 없음**

- 유료 번호를 사용하고 Teams 모임에서 구독에 포함되지 않은 국가의 전화 번호로 아웃바운드 전화를 걸 때와 같이 **분당 유료 모델로 오디오 회의 서비스에 운영자를 활용** 하려고 합니다.

## <a name="licensing-requirements-and-billing"></a>라이선스 요구 사항 및 청구

모임에 참가하기 위해 운영자 연결 회의 번호가 필요한 사용자에게는 Microsoft 오디오 회의 Standard 구독 또는 Microsoft 운영자 연결 회의 라이선스가 할당되어 있어야 합니다.

### <a name="audio-conferencing-standard-subscription"></a>오디오 회의 Standard 구독

Microsoft 오디오 회의 Standard 구독은 Microsoft Teams 라이선스에 대한 추가 기능으로 구매할 수 있으며 Microsoft 365 E5 및 Office 365 E5 구독에도 포함됩니다.

오디오 회의 Standard 구독을 사용하면 구독자가 Microsoft의 전화 번호를 사용하고 운영자의 번호로 오디오 회의 브리지를 확장할 수 있습니다. 구독자는 Microsoft를 통해 라우팅할 Teams 모임의 아웃바운드 호출과 운영자를 통해 라우팅할 호출을 결정할 수도 있습니다.

자세한 내용은 [**운영자 연결 회의 구성**](operator-connect-conferencing-configure.md)을 참조하세요.

### <a name="operator-connect-conferencing-license"></a>운영자 연결 회의 라이선스

Microsoft 운영자 연결 회의 라이선스는 Microsoft Teams 라이선스에 대한 추가 기능으로 획득할 수 있습니다.

운영자 연결 회의 라이선스를 사용하면 구독자가 운영자의 전화 번호를 사용할 수 있지만 Microsoft의 전화 번호는 포함되지 않습니다. Teams 모임의 모든 아웃바운드 호출은 운영자를 통해 라우팅되어야 합니다.

자세한 내용은 [**운영자 연결 회의 구성**](operator-connect-conferencing-configure.md)을 참조하세요.

>[!Note]
>모임 참가자는 운영자 연결 회의 기능이 있는 사용자가 구성한 모임에 참가하기 위해 오디오 회의 표준 구독 라이선스 또는 운영자 연결 회의 라이선스가 필요하지 않습니다.

운영자 연결 회의 통해 Microsoft는 조직에서 사용하는 오디오 회의 라이선스 유형, Microsoft 오디오 회의 또는 운영자 연결 회의 및 Microsoft에서 제공하는 전화 번호 사용에 따라 조직에 요금을 청구합니다.

운영자는 조직에 제공하는 운영자 연결 회의 번호를 사용하도록 청구합니다.

## <a name="additional-information-on-microsoft-audio-conferencing"></a>Microsoft 오디오 회의 대한 추가 정보

Microsoft 오디오 회의 사용하면 참가자가 PSTN 전화 번호로 전화를 걸거나 PSTN 전화 번호로 전화를 걸어 Microsoft Teams 모임에 참가할 수 있습니다. 조직에서 사용할 수 있는 Microsoft 오디오 회의 기능에 대한 자세한 내용은 [Microsoft 365 오디오 회의](audio-conferencing-in-office-365.md) 참조하세요.
