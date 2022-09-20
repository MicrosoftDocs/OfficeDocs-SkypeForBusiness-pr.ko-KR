---
title: Microsoft의 앱 인증 개요
description: 타사 앱의 보안, 규정 준수 및 개인 정보 보호를 위한 Microsoft 365 앱 준수 프로그램에 대해 자세히 알아봅니다.
ms.topic: article
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.subservice: teams-apps
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 713f30d148517f080c1799f71461d52e69d855ac
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837658"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>타사 앱의 보안, 규정 준수 및 개인 정보 보호를 위한 Microsoft 365 앱 준수 프로그램

Microsoft 규정 준수 프로그램은 주요 업계 표준 프레임워크에서 파생된 제어에 대해 앱을 검사 및 감사합니다. 이 프로그램은 고객 데이터를 보호하기 위해 강력한 보안 및 규정 준수 관행이 마련되어 있음을 보여줍니다. 프로그램에는 다음과 같은 단계가 있습니다.

* [게시자 확인](#publisher-verification).
* [게시자 증명](#publisher-attestation)입니다.
* [Microsoft 365 인증](#microsoft-365-certification).

## <a name="publisher-verification"></a>게시자 확인

앱 개발자가 Microsoft에 앱을 제출하려면 인증을 받아야 합니다. 개발자는 MPN(Microsoft 파트너 네트워크) 계정을 사용해 ID를 확인하고 해당 MPN 계정을 앱 등록에 연결합니다. 게시자 확인은 관리자 및 최종 사용자가 앱 개발자의 신뢰성을 파악하는 데 도움이 됩니다. 게시자 인증은 다음과 같은 장점이 있습니다.

* 고객 측면에서 투명성이 증가하고 위험이 감소 - 이 기능은 고객이 자신의 조직에서 사용 중인 앱들을 자신이 신뢰하는 개발자에 의해 게시되었다는 점을 이해할 수 있게 합니다.
* 향상된 브랜딩 - Azure Active Directory 동의 프롬프트, Enterprise Apps 페이지 및 기타 최종 사용자와 관리자가 사용하는 사용자 인터페이스에 `verified` 배지가 표시됩니다.
* 더욱 매끄러운 엔터프라이즈 채택 - 관리자가 게시자 확인 상태를 기본 정책 조건으로 지정한 상태로 사용자 동의 정책을 구성할 수 있습니다.

## <a name="publisher-attestation"></a>게시자 증명

게시자 증명은 앱 규정 준수 프로그램의 다음 계층입니다. 게시자 증명 앱은 앱의 보안 및 규정 준수 조치에 대해 관리자에게 확신을 더해 줍니다. 또한 앱에 대해 이러한 정보를 검토하는 시간을 줄이는 데도 도움이 됩니다. 증명에는 [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security)에서 식별한 80개 이상의 위험 요소에 대한 앱의 보안, 데이터 처리 및 규정 준수 관행이 반영됩니다. 게시자 증명 프로세스는 게시자 확인이 완료되기 전에 시작할 수 있습니다.

앱 개발자는 앱의 보안 및 규정 준수를 평가하기 위해 고객과 IT 관리자가 자주 묻는 질문이 포함된 자체 평가를 완료해야 합니다. 그런 다음 Microsoft는 보다 쉽고 시기 적절한 평가를 위해 이 정보를 게시합니다. 자세한 내용은 [증명 가이드](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)를 참조하세요.

관리자는 게시된 인증 앱을 세 가지 방법으로 빠르게 확인할 수 있습니다.

* 앱에 대한 추가 정보를 수집할 때 [Microsoft Teams 앱 보안 및 규정 준수](/microsoft-365-app-certification/teams/teams-apps) 링크에서 특정 앱의 세부 정보를 참조하세요. 또는 [Teams 관리 센터](https://admin.teams.microsoft.com/)에서 `Publisher attestation` 링크를 선택합니다.

  :::image type="content" source="media/attested-app-tac3.png" alt-text="Teams 관리 센터에서 게시자 증명 링크를 선택하여 앱 증명의 세부 정보를 봅니다.":::

* Teams 관리 센터의 **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 페이지에서 앱 세부정보를 확인할 때 앱 세부 정보 페이지의 배너에서 게시자 인증 아이콘을 확인하세요.

  :::image type="content" source="media/attested-app-tac1.png" alt-text="Teams 관리 센터에서 게시자 인증 아이콘은 인증된 모든 앱에 표시됩니다.":::

* Teams 관리 센터에서 [앱에 권한을 부여](app-permissions-admin-center.md)할 때 앱 이름 앞의 파란색 확인 표시는 게시자 인증 앱 또는 Microsoft 365 인증 앱을 나타냅니다.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Teams 관리 센터의 권한 부여 대화 상자에서 파란색 체크 표시는 해당 앱이 게시자 증명 앱임을 나타냅니다.":::

증명되거나 인증된 앱의 증명 세부 정보 페이지에는 다음 세부 정보가 나열됩니다.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="증명 앱에 대해 제공되는 세부 정보입니다.":::

## <a name="microsoft-365-certification"></a>Microsoft 365 인증

앱 인증은 다음을 통해 달성됩니다.

* 자격을 갖춘 분석가의 검토.
* 앱의 보안 및 규정 준수 프레임워크, 프로세스 및 절차를 중심으로 한 종합 평가에 대한 승인.

Microsoft는 주요 업계 표준 프레임워크에서 파생된 일련의 보안 제어에 대해 앱을 확인합니다.

이 인증서는 조직에서 앱을 사용할 때 고객 데이터를 보호하기 위해 마련된 강력한 보안 및 규정 준수 관행을 보여줍니다. 관리자와 최종 사용자가 인증을 통해 얻는 이점에 대한 자세한 내용은 [Microsoft 365 앱 규정 준수 프로그램 개요](/microsoft-365-app-certification/docs/enterprise-app-certification-guide)를 참조하세요.

관리자는 다음과 같은 방법으로 Microsoft 365 인증된 앱을 빠르게 확인할 수 있습니다.

* 웹에서 앱에 대한 추가 정보를 수집하는 경우 [앱에 대한 Microsoft 문서](/microsoft-365-app-certification/teams/teams-apps)에서 방패 아이콘을 참조하세요.

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="앱의 보안 및 규정 준수에 관한 자세한 도움말 문서에서 Microsoft 365 인증 정보를 확인합니다.":::

* [Teams 관리 센터](https://admin.teams.microsoft.com/policies/manage-apps)에서 애플리케이션을 확인할 때 인증 열을 사용하여 앱 목록을 정렬합니다. 아이콘을 확인하고 필요에 따라 링크를 선택하여 위에서 언급한 앱별 페이지에 액세스합니다.

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Teams 관리 센터에서 앱의 Microsoft 365 인증 상태를 확인합니다." lightbox="media/m365cert-apps-list2.png":::

* 앱에 대한 세부 정보를 볼 때 해당 앱의 배너에서 Microsoft 365 인증 아이콘을 확인하세요.

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Teams 관리 센터에서 특정 앱을 관리할 때 해당 앱의 배너에서 Microsoft 365 인증 정보 보기":::

* Teams 관리 센터에서 [앱에 권한을 부여](app-permissions-admin-center.md)할 때 앱 이름 앞의 파란색 확인 표시는 게시자 인증 앱 또는 Microsoft 365 인증 앱을 나타냅니다.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Teams 관리 센터의 권한 부여 대화 상자에서 관리자는 파란색 체크 표시를 확인하여 앱이 Microsoft 365 인증됐는지를 확인할 수 있습니다.":::

## <a name="view-security-compliance-and-privacy-information"></a>보안, 규정 준수, 개인 정보 보호 정보 보기

[Microsoft 설명서](/microsoft-365-app-certification/teams/teams-apps) 및 [Teams 관리 센터](https://admin.teams.microsoft.com/policies/manage-apps)에서 인증 또는 인증된 앱의 보안, 개인 정보 보호, 규정 준수 및 동작에 대한 정보를 찾을 수 있습니다.

### <a name="microsoft-documentation"></a>Microsoft 문서

[Microsoft Teams 앱 보안 및 규정 준수](/microsoft-365-app-certification/teams/teams-apps)의 링크된 앱별 도움말 문서에서 각 앱에 대한 보안, 개인 정보 보호, 규정 준수 등에 관한 세부 정보를 찾을 수 있습니다.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Microsoft 규정 준수 프로그램을 거치는 앱에 대해 제공되는 세부 정보입니다.":::

### <a name="teams-admin-center"></a>Teams 관리 센터

앱을 평가할 때 MCAS(Microsoft Cloud App Security)와 같은 독립적인 CASB(Cloud Access Security Brokers)를 사용하여 앱의 보안 및 동작에 대한 정보를 찾을 수 있습니다. Teams 관리 센터에는 Microsoft 365 인증 앱용 MCAS의 보안 및 규정 준수 정보가 포함되어 있습니다. 앱 세부 정보 페이지에서 이 정보를 확인하여 앱이 보안 요구 사항을 충족하는지 확인하세요.

> [!NOTE]
> 이 기능은 조직에 MCAS를 지원하는 라이선스가 있는지에 관계없이 모든 관리자가 사용할 수 있습니다.

앱의 MCAS 정보에 액세스하려면 다음을 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱 관리 앱** > 에 액세스 **[합니다](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. **인증** 을 선택하여 앱을 정렬하고 모든 Microsoft 365 인증 앱을 테이블 맨 위로 올립니다.

1. Microsoft 365 인증 앱을 선택합니다.

1. **보안 및 규정 준수** 탭을 선택합니다.

   :::image type="content" source="media/mcas.png" alt-text="Teams 관리 센터 보안 및 규정 준수 탭의 스크린샷":::

   앱에 지원되는 기능에 관한 자세한 내용을 보려면 각 범주의 드롭다운 목록을 선택합니다.

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>앱의 개인 정보 취급 방침 및 사용 약관 보기

Teams 관리 센터의 각 앱 페이지는 해당 앱의 개인정보처리방침 및 사용 약관으로 연결됩니다.

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="Teams 관리 센터에서 관리자는 모든 앱의 개인 정보 취급 방침 및 사용 약관에 대한 링크에 액세스할 수 있습니다." lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>관련 기사

* [앱 사용 권한 보기 및 관리자 동의 부여](app-permissions-admin-center.md)
