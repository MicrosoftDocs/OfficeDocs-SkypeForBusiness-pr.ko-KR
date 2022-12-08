---
title: 리소스 계정 라이선스 Microsoft Teams 전화
author: DaniEASmith
ms.author: danismith
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
- admindeeplinkMAC
description: 조직의 자동 전화 교환 및 통화 큐에 대한 리소스 계정에 Microsoft Teams 전화 리소스 계정 라이선스를 할당하는 방법을 알아봅니다.
ms.openlocfilehash: d3eacab8569981550520385c4aee297ae6835a59
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307763"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>리소스 계정 라이선스 Microsoft Teams 전화

Microsoft Teams에서는 모든 자동 전화 교환 및 통화 큐에 연결된 리소스 계정이 필요합니다. 각 리소스 계정에 **Microsoft Teams 전화 리소스 계정** 라이선스가 할당되어 리소스 *계정에 전화 번호가 할당되는지 여부에 관계없이* 시스템에서 올바르게 식별되고 제대로 작동하도록 해야 합니다. Teams Phone을 포함하는 구독이 있는 조직은 추가 비용 없이 특정 양의 **Teams 전화 리소스 계정** 라이선스를 자동으로 할당합니다.  Microsoft 통화 플랜은 해당 리소스 계정을 사용하여 전화를 걸 수 있기를 원하지 않는 한 필요하지 않습니다. 자세한 내용은 [Teams 자동 전화 교환 계획 및 통화 큐를 참조하세요](../plan-auto-attendant-call-queue.md#prerequisites).

> [!NOTE]
> 이전에는 리소스 계정에 전화 번호를 할당할 때만 **Teams 전화 리소스 계정** 라이선스(한때 **가상 사용자** 라이선스라고 함)가 필요했습니다. 이제 전화 번호가 할당되는지 여부에 관계없이 모든 **리소스 계정에 Teams 전화 리소스 계정** 라이선스가 할당되어야 합니다. 또한 리소스 계정에 **Teams 전화 표준 요금제** 라이선스를 할당하지 마세요. 현재 **Teams 전화 표준 요금제** 라이선스로 구성된 리소스 계정이 있는 경우 아래 설명된 대로 **Teams 전화 리소스 계정** 라이선스로 전환해야 합니다.
 

## <a name="resource-account-license-allocation"></a>리소스 계정 라이선스 할당

조직은 전체 크기에 따라 **Teams 전화 리소스 계정** 라이선스를 할당합니다. **통화 플랜** 라이선스가 있는 **Teams 전화 표준 요금제** 및 Teams Phone과 같은 전화 시스템 기능이 있는 구독이 있는 조직에는 비용 없이 사용할 수 있는 25 **개의 Teams 전화 리소스 계정** 라이선스가 할당됩니다. 

조직에서 **통화 플랜** 을 사용하는 **Teams 전화 표준 요금제** 또는 Teams Phone의 사용자 라이선스 10개마다 **Teams 전화 리소스 계정** 라이선스를 하나 더 사용할 수 있습니다.  대부분의 조직에는 이 크기 조정 계획에 따라 충분한 **Teams 전화 리소스 계정** 라이선스가 있습니다. **더 많은 Teams 전화 리소스 계정** 라이선스가 필요한 경우 EA, EAS, EES, CSP, Web Direct, NCE – 고객 주도 및 NCE – 파트너 주도 또는 Microsoft 계정 담당자를 통해 표준 할당 이외의 더 많은 **Teams 전화 리소스** 계정 라이선스를 구매할 수 있습니다.

### <a name="license-allocation-example"></a>라이선스 할당 예제

Contoso, Inc.는 전화 시스템(직원마다 하나씩)을 포함하는 600개의 라이선스를 구매했습니다. Contoso는 초기 25개와 **Teams 전화 리소스 계정** 라이선스 60개, 총 85개 라이선스를 할당합니다. 조직에는 90개의 통화 큐와 자동 전화 교환이 있습니다. 모든 **Teams 전화 리소스 계정** 라이선스를 할당하고 5개의 추가 **Teams 전화 리소스 계정** 라이선스를 구매해야 합니다. 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 전화 리소스 계정 라이선스를 가져오는 방법

1. [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339) 로그인합니다.
2. **청구** > [**구매 서비스**](https://go.microsoft.com/fwlink/p/?linkid=868433)**추가 기능** > 으로 이동합니다.
3. 스크롤하여 **Microsoft Teams 전화 리소스 계정** 라이선스를 찾습니다. **지금 구매** 를 선택합니다.

   > [!NOTE]
   > 할당 내에 있더라도 비용이 0인 경우에도 라이선스를 **구입** 해야 합니다.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Microsoft Teams 전화 리소스 계정 라이선스를 사용하도록 기존 리소스 계정 변경

**Teams 전화 표준 요금제** 라이선스를 사용하는 기존 리소스 계정이 있는 경우 **Teams 전화 리소스 계정** 라이선스로 를 사용하도록 전환해야 합니다.

1. 새 **Teams 전화 리소스 계정** 라이선스를 가져옵니다.
2. Microsoft 365 관리 센터 연결된 단계에 따라 [사용자를 다른 구독으로 이동합니다](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> 항상 **Teams 전화 표준 요금제** 라이선스를 제거하고 동일한 라이선스 활동에서 **Teams 전화 리소스 계정** 라이선스를 할당합니다. 이전 라이선스를 제거하고, 계정 변경 내용을 저장하고, 새 라이선스를 추가하고, 계정 설정을 다시 저장하면 리소스 계정이 더 이상 조직의 자동 전화 교환 및 통화 큐가 더 이상 작동하지 않는 것처럼 예상대로 작동하지 않을 수 있습니다.
>
> 이 경우 Teams 전화 리소스 계정 라이선스를 사용하여 새 **리소스 계정을** 만들고 손상된 리소스 계정을 제거하는 것이 좋습니다.

## <a name="related-information"></a>관련 정보

[자동 전화 교환 및 통화 큐 서비스 업데이트](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams에서 리소스 계정 관리](../manage-resource-accounts.md)
