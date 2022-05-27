---
title: 조직에서 전화 시스템 설정
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Microsoft 365 조직에 대한 Teams 전화 시스템 설정하는 방법을 자세히 설명하는 단계별 가이드입니다.
ms.openlocfilehash: 12e202fed6ad63835c364662194be2eabf872b31
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681929"
---
# <a name="set-up-phone-system-in-your-organization"></a>조직에서 전화 시스템 설정

이 문서에서는 Microsoft 365 클라우드에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하는 Microsoft의 기술인 전화 시스템 설정하기 위한 콘텐츠에 대한 로드맵을 제공합니다. 자세한 정보에 대한 링크는 각 단계의 끝에서 사용할 수 있습니다.

이 문서를 읽기 전에 [전화 시스템 내용을](what-is-phone-system-in-office-365.md) 읽었는지 확인하고 [전화 시스템](here-s-what-you-get-with-phone-system.md). 후자의 두 문서에서는 전화 시스템 요구 사항 및 기능에 대해 설명합니다.

이 문서에서는 다음 단계를 설명합니다.

- [1단계: 전화 시스템 라이선스 구입 및 할당](#step-1-buy-and-assign-a-phone-system-license)
- [2단계: PSTN 연결 옵션 선택](#step-2-choose-a-pstn-connectivity-option)
- [3단계: 사용자의 전화 번호 가져오기](#step-3-get-phone-numbers-for-your-users)
- [4단계: 서비스에 대한 전화 번호 가져오기](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [5단계: 통화 큐를 설정하려는 경우](#step-5-if-you-want-to-set-up-a-call-queue)
- [6단계: 자동 전화 교환을 설정하려는 경우](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [7단계: 무료 번호에 대한 통신 크레딧 설정](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>1단계: 전화 시스템 라이선스 구입 및 할당

단일 사용자에게 전화 시스템 라이선스를 할당하기 위해 단계는 Microsoft 365 라이선스를 할당하는 것과 동일합니다. 여러 사용자에게 라이선스를 대량으로 할당할 수도 있습니다. 사용 가능한 전화 시스템 라이선스 및 라이선스 획득 및 할당 방법에 대한 자세한 내용은 [Teams 추가 기능 라이선스](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) 및 [Microsoft Teams 추가 기능 라이선스 할당을 참조하세요](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>2단계. PSTN 연결 옵션 선택

사용자가 외부 전화를 걸고 받을 수 있도록 하려면 전화 시스템 PSTN(공중 전화망)에 연결해야 합니다. Microsoft는 다음을 포함하여 PSTN에 연결하기 위한 여러 옵션을 제공합니다.

- 통화 플랜. Microsoft를 PSTN 이동 통신 사업자로 사용하는 클라우드 전체 솔루션입니다.

- 운영자 연결. 기존 이동 통신 사업자가 Microsoft 운영자 연결 프로그램에 참여하는 경우 PSTN 통화 및 SCC(세션 테두리 컨트롤러)를 관리할 수 있습니다.

- 직접 라우팅. SCC를 연결하여 전화 시스템 자체 PSTN 이동 통신 사업자를 사용합니다.

모든 연결 옵션에 대한 자세한 내용은 [PSTN 연결 옵션을 참조하세요](pstn-connectivity.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>3단계: 사용자의 전화 번호 가져오기

조직에서 전화를 걸고 받을 사용자를 설정하려면 먼저 전화 번호를 받아야 합니다.

사용자의 전화 번호를 관리하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요. 사용자에 대한 숫자를 관리하는 방법은 선택한 PSTN 연결 옵션에 따라 달라집니다.

- [조직의 전화 번호 관리](manage-phone-numbers-landing-page.md) – PSTN 연결 옵션에 따라 번호를 획득하고 관리하기 위한 특정 문서에 대한 링크가 포함된 전화 번호 유형의 개요를 제공합니다.
두 가지 유형의 [사용자 전화 번호를 설명합니다](manage-phone-numbers-landing-page.md#user-telephone-numbers).

- [사용자의 전화 번호 할당, 변경 또는 제거 – 획득한 전화 번호를](assign-change-or-remove-a-phone-number-for-a-user.md) 할당하고 관리하는 방법을 설명합니다.

- [받을 수 있는 전화 번호 수](how-many-phone-numbers-can-you-get.md) – 전화 번호 유형 및 구입 및 할당한 라이선스 유형에 따라 받을 수 있는 전화 번호 수를 설명합니다.

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>4단계: 서비스에 대한 전화 번호 가져오기(통화 큐, 자동 전화 교환)

사용자의 전화 번호를 받는 것 외에도 자동 전화 교환 및 통화 큐와 같은 서비스에 대한 유료 또는 무료 전화 번호를 얻을 수 있습니다. 서비스 번호는 수백 건의 통화를 동시에 처리할 수 있는 반면, 사용자의 전화 번호는 몇 번의 통화만 동시에 처리할 수 있습니다.

라이선스에 포함된 Microsoft에서 서비스 번호를 가져올 수 있습니다. 운영자 연결 또는 직접 라우팅을 통해 PSTN을 연결한 경우 자체 통신 사업자 또는 운영자가 제공하는 서비스 번호를 사용할 수 있습니다.

자세한 내용은 다음을 참조하세요.

- [조직의 전화 번호 관리](manage-phone-numbers-landing-page.md) – PSTN 연결 옵션에 따라 번호를 획득하고 관리하기 위한 특정 문서에 대한 링크가 포함된 전화 번호 유형의 개요를 제공합니다.
라이선스에 포함된 Microsoft에서 사용할 수 있는 [서비스 전화 번호](manage-phone-numbers-landing-page.md#service-telephone-numbers) 에 대해 설명합니다. 운영자 연결 또는 직접 라우팅에서 제공하는 서비스 번호에 대한 자세한 내용은 공급자에게 문의하세요.

- [받을 수 있는 전화 번호 수](how-many-phone-numbers-can-you-get.md) – 전화 번호 유형 및 구입 및 할당한 라이선스 유형에 따라 받을 수 있는 전화 번호 수를 설명합니다.

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>5단계: 통화 큐를 설정하려는 경우

통화 큐에는 누군가가 조직의 전화 번호로 전화를 걸 때 사용되는 인사말, 자동으로 통화를 보류할 수 있는 기능 및 통화를 처리하기 위해 사용 가능한 다음 통화 에이전트를 검색하는 기능이 포함됩니다. 조직에 대한 단일 또는 여러 통화 큐를 만들 수 있습니다.

통화 큐에 대한 자세한 내용은 [통화 큐 만들기를](create-a-phone-system-call-queue.md) 참조하세요.

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>6단계: 자동 전화 교환을 설정하려는 경우

자동 전화 교환을 사용하면 조직에 전화하는 사용자가 메뉴 시스템을 탐색하여 올바른 부서, 통화 큐, 사람 또는 운영자로 이동할 수 있습니다.

자동 전화 교환 설정에 대한 자세한 내용은 [자동 전화 교환 설정을](create-a-phone-system-auto-attendant.md) 참조하세요.

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>7단계: 무료 번호에 대한 통신 크레딧 설정

Microsoft Teams 무료 번호를 사용하려면 Communications Credits를 설정해야 합니다. 무료 통화는 분당 요금이 청구되며 긍정적인 통신 크레딧 잔액이 필요합니다.

통신 크레딧은 다음과 같이 사용할 무료 번호를 추가하는 편리한 방법입니다.

- 음성 앱에 대한 서비스 번호(예: 자동 전화 교환 또는 통화 큐)

- 국내 통화 플랜 구독이 있거나 국내 및 국제 통화 플랜 구독에 포함된 것 이상으로 국제 전화 번호로 전화를 겁니다.

- 매월 분 할당을 모두 소진한 후 전화 걸기 및 분당 지불

자세한 내용은 [커뮤니케이션 크레딧이란?](what-are-communications-credits.md) 을 참조하고 [조직에 대한 통신 크레딧을 설정합니다](set-up-communications-credits-for-your-organization.md).

## <a name="related-topics"></a>관련 항목

- [전화 시스템이란?](what-is-phone-system-in-office-365.md)

- [다음은 전화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)

- [조직의 전화 번호 관리](manage-phone-numbers-landing-page.md)
