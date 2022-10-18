---
title: 전화 걸기 계획 및 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Microsoft Teams에서 전화 걸기 플랜 및 라우팅
ms.openlocfilehash: f3474dc576671c5d8ef90e68c9bc5b246209cdb1
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585086"
---
# <a name="overview"></a>개요

이 섹션의 문서에서는 Microsoft Teams의 다이얼 플랜 및 통화 라우팅에 대해 설명합니다. 

- [다이얼 플랜이란?](what-are-dial-plans.md)
- [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)
- [할당되지 않은 마비로 호출 라우팅](routing-calls-to-unassigned-numbers.md)

이 섹션의 문서는 PSTN(공중 전화망)에 연결하기 위한 모든 옵션인 통화 플랜, 운영자 연결, Teams Phone Mobile 및 직접 라우팅에 적용됩니다. 모든 PSTN 연결 옵션에 대한 자세한 내용은 [PSTN 연결 옵션을 참조하세요](pstn-connectivity.md).

통화 플랜, 운영자 연결 또는 Teams Phone Mobile을 선택하는 경우 대부분의 통화 라우팅은 Microsoft 또는 공급자가 처리합니다. 그러나 직접 라우팅에는 호출 라우팅을 구성하는 추가 단계가 필요합니다. 

직접 라우팅의 경우 음성 경로를 지정하고 사용자에게 음성 라우팅 정책을 할당하여 통화 라우팅을 구성해야 합니다. SCC(세션 테두리 컨트롤러)와의 상호 운용성을 보장하기 위해 트렁크 수준에서 번호 변환에 대한 다이얼 플랜을 구성할 수 있습니다. 자세한 내용은 [직접 라우팅에 대한 음성 라우팅 구성](direct-routing-voice-routing.md), [음성 라우팅 정책 관리](manage-voice-routing-policies.md) 및 [전화 번호 번역](direct-routing-translate-numbers.md)을 참조하세요.

통화 플랜 및 운영자 연결 사용자에게 직접 라우팅 온라인 음성 라우팅 정책을 할당할 수 있습니다. 예를 들어 사용자가 콜 센터에 직접 전화를 걸 수 있도록 하려면 이 작업을 수행할 수 있습니다. 콜 센터에 직접 라우팅 트렁크를 설정할 수 있습니다.

예를 들어 사용자에게 통화 플랜 라이선스가 있는 경우 해당 사용자의 발신 통화는 Microsoft 통화 플랜 PSTN 인프라를 통해 자동으로 라우팅됩니다. 사용자에게 직접 라우팅 온라인 음성 라우팅 정책을 구성하고 할당하는 경우 전화 걸기 번호가 온라인 음성 라우팅 정책에 정의된 숫자 패턴과 일치하는지 여부를 확인하기 위해 사용자의 발신 통화가 확인됩니다. 일치하는 항목이 있으면 직접 라우팅 트렁크를 통해 호출이 라우팅됩니다. 일치하는 항목이 없으면 호출이 통화 계획 PSTN 인프라를 통해 라우팅됩니다.

자세한 내용은 [직접 라우팅 음성 라우팅 정책 고려 사항을 참조하세요](direct-routing-voice-routing.md#voice-routing-policy-considerations).



