---
title: 리소스 계정 라이선스 Microsoft Teams 전화
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 조직의 리소스 계정에 무료 Teams 전화 리소스 계정 라이선스 또는 유료 Teams 전화 표준 요금제 사용자 라이선스를 할당하는 방법에 대해 알아봅니다.
ms.openlocfilehash: f8aaf7480fc228fc78879ed5905aaaf7092777ab
ms.sourcegitcommit: 6e677c7d0dfe9e380d70adaca748eea88ca95705
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2022
ms.locfileid: "67298298"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>리소스 계정 라이선스 Microsoft Teams 전화

통화 플랜 라이선스 사용자가 있는 Teams 전화 표준 요금제 또는 Teams Phone이 있는 조직은 무료 *Microsoft Teams 전화 리소스 계정* 라이선스 또는 유료 *Teams 전화 표준 요금제* 사용자 라이선스를 리소스 계정에 할당할 수 있습니다. Microsoft 통화 플랜이 항상 필요한 것은 아닙니다(외부 전화 번호로 통화를 전송할 때 필수 구성 요소에 대한 [Teams 자동 전화 교환 계획 및 통화 큐](../plan-auto-attendant-call-queue.md#prerequisites) 참조).

모든 자동 전화 교환 및 통화 큐에는 연결된 리소스 계정이 필요합니다. 전화 번호가 필요한 리소스 계정에는 무료 *Microsoft Teams 전화 Resource Account* 라이선스 또는 유료 *Teams 전화 표준 요금제* 사용자 라이선스가 있어야만 전화 번호를 리소스 계정에 적용할 수 있습니다.

> [!TIP]
> 중첩된 자동 전화 교환 또는 전화 번호가 할당되지 않은 통화 큐에 사용할 리소스 계정에는 라이선스가 필요하지 않습니다.

## <a name="resource-account-license-allocation"></a>리소스 계정 라이선스 할당

조직은 전체 크기에 따라 *리소스 계정* 라이선스를 Microsoft Teams 전화 할당됩니다. 통화 플랜 라이선스가 있는 Teams 전화 표준 요금제 및 Teams Phone을 포함하여 Teams Phone 시스템 기능이 있는 라이선스가 하나 이상 있는 조직에는 25개의 리소스 계정 라이선스를 비용 없이 사용할 수 있습니다. 조직에서 통화 플랜 사용자 라이선스를 사용하여 10개의 Teams 전화 표준 요금제 또는 Teams Phone을 추가하면 Microsoft Teams 전화 *리소스 계정* 라이선스를 하나 더 사용할 수 있게 됩니다.

> [!NOTE]
> 통화 플랜이 있는 Teams 전화 표준 요금제 및 Teams Phone은 모든 Microsoft 365 구독자가 사용할 수 있는 추가 기능 라이선스입니다. Teams 전화 표준 요금제 라이선스도 Microsoft 365 E5 계획의 일부로 포함됩니다.

조직에서 자동 전화 교환 또는 통화 큐 노드를 만드는 데 무료 *Microsoft Teams 전화 Resource Account* 라이선스를 사용하는 경우에도 리소스 계정에서 유료 *Teams 전화 표준 요금제* 라이선스를 사용할 수 있습니다. 대부분의 조직에는 크기 조정 계획에 따라 충분한 리소스 계정 라이선스가 있습니다.

### <a name="license-allocation-example"></a>라이선스 할당 예제

Contoso, Inc.는 전화 시스템(직원마다 하나씩)을 포함하는 600개의 라이선스를 구입했습니다. Contoso는 초기 25개와 *Microsoft Teams 전화 리소스 계정* 라이선스 60개, 총 85개 라이선스를 할당합니다. 조직에는 전화 번호가 있는 90개의 통화 큐 및 자동 전화 교환이 있습니다. 모든 *Microsoft Teams 전화 Resource Account* 라이선스를 할당하고 5개의 일반 가격 *Teams 전화 표준 요금제* 라이선스를 획득해야 합니다.

Contoso는 자동 전화 교환 및 통화 큐 시스템을 다시 설계하는 것을 고려해야 합니다. 전화 번호가 필요하지 않은 더 적은 전화 번호와 더 많은 중첩 노드를 사용하는 경우 구현을 간소화하고 비용을 절감합니다.

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 전화 리소스 계정 라이선스를 구입하는 방법

1. Microsoft 365 관리 센터에 로그인합니다.
2. **청구** > **구매 서비스 추가 기능** > **으로** 이동합니다.
3. 스크롤하여 **Microsoft Teams 전화 Resource Account** 라이선스를 찾습니다. **지금 구입** 을 선택합니다.

   > [!NOTE]
   > 비용이 0인 경우에도 라이선스를 **구입** 해야 합니다.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Microsoft Teams 전화 리소스 계정 라이선스를 사용하도록 기존 리소스 계정 변경

리소스 계정의 라이선스를 Teams 전화 표준 요금제 라이선스에서 *Microsoft Teams 전화* *Resource Account* 라이선스로 전환하려는 경우:

1. 새 *Microsoft Teams 전화 Resource Account* 라이선스를 가져옵니다.
2. Microsoft 365 관리 센터 연결된 단계에 따라 [사용자를 다른 구독으로 이동합니다](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> 항상 전체 *Teams 전화 표준 요금제* 라이선스를 제거하고 동일한 라이선스 작업에서 *Microsoft Teams 전화 Resource Account* 라이선스를 할당합니다. 이전 라이선스를 제거하고 계정 변경 내용을 저장하고 새 라이선스를 추가한 다음 계정 설정을 다시 저장하면 리소스 계정이 더 이상 예상대로 작동하지 않을 수 있습니다. 이 경우 Microsoft Teams 전화 리소스 계정 라이선스에 대한 새 *리소스 계정을* 만들고 손상된 리소스 계정을 제거하는 것이 좋습니다.

## <a name="related-information"></a>관련 정보

[자동 전화 교환 및 통화 큐 서비스 업데이트](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams에서 리소스 계정 관리](../manage-resource-accounts.md)
