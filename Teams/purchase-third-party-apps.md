---
title: 타사 앱 구매 및 구독 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, nsuter
search.appverid: MET150
f1keywords: ''
description: 신용 카드, 직불 카드 또는 청구서 청구를 통해 Teams 스토어에서 유료 앱 라이선스를 구입하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 82364d5659009e067a6884551266c6fabf93dc04
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912427"
---
# <a name="purchase-third-party-teams-apps-and-manage-subscriptions"></a>타사 Teams 앱 구매 및 구독 관리

일부 Teams 앱은 앱의 전체 기능 및 범위를 경험하기 위해 서비스 구독을 구매해야 할 수 있습니다. 이러한 서비스 구독을 SaaS(Software as a Service) 제품이라고 합니다. 라이선스는 [AppSource](https://appsource.microsoft.com/) 및 [Microsoft Teams 관리 센터를](https://admin.teams.microsoft.com) 통해 구매할 수 있습니다.

유료 앱은 다른 앱과 동일한 거버넌스 컨트롤을 사용하여 관리됩니다. Teams 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 모든 Teams 앱을 보고 관리합니다.

앱 관리 페이지에서 조직의 사용자를 위해 타사 앱에서 제공하는 서비스에 대한 라이선스를 구매할 수도 있습니다. 테이블 **의 라이선스** 열은 앱이 구매를 위해 SaaS 구독을 제공하는지 나타냅니다. 최종 사용자는 신용 카드, 직불 카드 또는 청구서 청구를 사용하여 앱을 구입할 수 있습니다.

:::image type="content" source="media/manage-apps-new-page.png" alt-text="Teams 관리 센터의 앱 관리 페이지에 있는 구매 라이선스 옵션을 보여 주는 스크린샷" lightbox="media/manage-apps-new-page-large.png":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>Teams 관리 센터에서 앱 구매

Teams 관리 센터에서 앱을 구매하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 에 액세스합니다. 페이지에 액세스하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

1. 이름으로 원하는 앱을 검색합니다. 앱이 유료 SaaS 구독을 제공하는지 확인하려면 라이선스 열을 참조 **하세요** . 각 앱에는 다음 값 중 하나가 있습니다.
    * **구매**: 앱은 SaaS 구독을 제공하며 구매할 수 있습니다.
    * **구입함**: 앱에서 SaaS 구독을 제공하고 이에 대한 라이선스를 구매했습니다.
    * **- -**: 앱에서 SaaS 구독을 제공하지 않습니다.

1. **구매** 를 선택하여 앱 세부 정보 페이지의 **플랜 및 가격 책정** 탭으로 이동합니다. 관리 센터에서 사용할 수 있는 요금제 및 가격 정보를 검토할 수 있습니다. **자세히 알아보기** 링크를 선택하여 [AppSource](https://appsource.microsoft.com/)에서 앱 페이지로 이동합니다.

1. 앱을 구독하려면 원하는 플랜을 선택하고 **구매** 를 선택합니다. 체크아웃 흐름은 Teams 관리 센터에서 직접 열립니다.

> [!NOTE]
> 조직에서 앱 개발자와 개별적으로 협상 가능한 특별 가격 책정이 포함된 비공개 플랜도 구매할 수 있습니다. 이러한 플랜은 플랜 이름 아래에 **비공개 플랜** 이라는 레이블이 있습니다.

1. 구매하려는 사용자 라이선스 수를 선택합니다.

1. 청구 계정과 판매처 주소가 올바른지 확인하세요. 아직 없는 경우 **추가** 를 선택합니다. 청구 계정에 대한 자세한 내용은 [청구 계정 이해](/microsoft-365/commerce/manage-billing-accounts)를 참조하세요. 전역 관리자만 새 청구 계정을 추가할 수 있습니다.

1. 올바른 청구 프로필이 선택되었는지 확인합니다. 아직 없는 경우 **새 항목 추가** 를 선택합니다. 신용 카드, 직불 카드 또는 [청구서 청구로 결제할 수 있습니다](#invoice-billing). 또한 청구 프로필을 사용하면 구매 주문 번호를 추가하여 나중에 주문을 식별할 수도 있습니다. 청구 프로필에 대한 자세한 내용은 [청구 프로필 이해를 참조하세요](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles).

1. **주문하기** 를 선택합니다.

1. 앱 개발자 웹 사이트에서 구독을 활성화하려면 **설정** 을 선택합니다. 구매 후 구독을 설정하지 않은 경우 나중에 **구독 관리를 선택하여 구독** 을 설정할 수 있습니다.

Teams 앱과 연결된 SaaS 제품을 구매한 후에는 앱 세부 정보 페이지의 **플랜 및 구독** 탭에서 다음 구매 세부 정보를 볼 수 있습니다.

* **라이선스 활성화 날짜**: 라이선스가 활성화된 날짜입니다.
* **라이선스**: 구매한 라이선스 수입니다.

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text="Teams 관리 센터의 앱 세부 정보 페이지에 있는 플랜 및 가격 책정 탭의 스크린샷" lightbox="media/purchase-third-party-apps-details-page.png":::

**구독 관리를** 선택하여 구매한 라이선스를 보고 관리합니다.

전역 관리자는 조직의 모든 사용자가 구매한 구독을 볼 수 있지만 라이선스를 더 추가하고, 라이선스를 제거하고, 청구 계정의 모든 사용자가 구매한 구독을 취소할 수 있습니다. Teams 서비스 관리자는 자체 구매에 대해 동일한 작업을 수행할 수 있습니다.

> [!NOTE]
> 전역 관리자가 다른 전역 관리자가 구매한 구독을 관리하려면 동일한 청구 계정에 있어야 합니다. [Microsoft 365 관리 센터](https://admin.microsoft.com)에서 앱을 선택하여 다른 전역 관리자에게 구매한 구독에 대한 액세스 권한을 부여할 수 있습니다. 관리 센터에서 **청구 프로필 보기** > **청구 계정 선택** > **역할 할당** > **다른 전역 관리자 추가** 에 액세스합니다.

> [!IMPORTANT]
> 앱 구매를 활성화하면 앱 내 구매도 활성화됩니다. 사용자는 앱에 대해 앱 개발자가 제어하는 ​​인앱 구매 제안을 볼 수 있습니다. 사용자가 앱을 구매하지 못하도록 하려면 앱을 차단해야 합니다.

### <a name="invoice-billing"></a>청구서 청구

* 청구서 청구는 일부 거래에 대한 결제 옵션으로 사용할 수 있습니다.
* 청구서 청구를 처음 사용하는 경우 신용 검토가 필요하며 승인에 최대 24~48시간이 소요될 수 있습니다. 신용 확인이 완료될 때까지 청구서 청구를 사용할 수 없습니다. 신용 카드로 주문하거나 신용 검토가 승인된 후 나중에 다시 시도할 수 있습니다.
* 청구서 청구는 전역 관리자 또는 Teams 서비스 관리자 및 청구 관리자 권한이 모두 있는 관리자만 사용할 수 있습니다.
* 30일 무료 평가판이 포함된 플랜을 구매하는 경우 청구서 청구를 사용할 수 없습니다.

## <a name="manage-subscriptions-in-teams-admin-center"></a>Teams 관리 센터에서 구독 관리

Teams 관리 센터에서 구매한 앱 구독 및 라이선스를 관리할 수 있습니다. 앱 구독 목록과 해당 세부 정보를 보고 다음 작업을 수행할 수 있습니다.

* 계획 변경
* 라이선스 구입 또는 제거
* 결제 방법 업데이트
* 구독 취소
* 청구서 보기

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="앱의 구독 세부 정보 스크린샷" lightbox="media/manage-existing-subscriptions-all.png":::

구독을 관리하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > [**앱 관리**](https://admin.teams.microsoft.com/policies/manage-apps) 에 액세스합니다.

1. 구독 탭 **을** 선택하여 구매한 구독을 봅니다.

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="앱 관리 페이지의 앱에 대한 구독 옵션 스크린샷" lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> Teams 관리 센터에서 사용자 또는 동일한 청구 계정의 일부인 다른 관리자가 구매한 앱 구독을 관리할 수 있습니다. 다른 관리자가 동일한 테넌트에서 구매했거나 다른 청구 계정을 사용하여 구매한 모든 앱 구독을 보려면 [Microsoft 365 관리 센터](https://admin.microsoft.com/adminportal/home#/homepage) 방문하세요.

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>Teams 앱에 대한 SaaS 제안 나열 및 판매

개발자는 Teams 앱과 연결된 SaaS 제안을 생성할 수 있습니다. 이러한 제안은 [파트너 센터](https://partner.microsoft.com)를 통해 게시되며 조직에서 [AppSource](https://appsource.microsoft.com/) 및 Microsoft Teams 관리 센터를 통해 구매할 수 있습니다.

타사 앱 개발자에 대한 자세한 내용은 [SaaS 제안 만들기](/azure/marketplace/partner-center-portal/create-new-saas-offer)를 참조하세요.

## <a name="related-articles"></a>관련 기사

* [Microsoft Teams 관리 센터에서 앱 관리](manage-apps.md)
* [SaaS 제품 만들기](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 기본 제공 역할](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 관리자 역할](/microsoft-365/admin/add-users/about-admin-roles)
