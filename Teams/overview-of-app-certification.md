---
title: Microsoft의 앱 인증 개요
ms.reviewer: ''
description: Teams 앱에 대한 앱 증명 및 인증 프로그램을 이해합니다.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
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
ms.openlocfilehash: 5a8edd0afc2adde7a6867242dd0bdc0b406ca682
ms.sourcegitcommit: 745d707ec63685ce7f973785e7056628472b9c45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2022
ms.locfileid: "64910914"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>타사 앱의 보안, 규정 준수 및 개인 정보 보호를 위한 Microsoft 365 앱 준수 프로그램

Microsoft 규정 준수 프로그램은 주요 업계 표준 프레임워크에서 파생된 제어에 대해 앱을 검사 및 감사합니다. 이 프로그램은 고객 데이터를 보호하기 위해 강력한 보안 및 규정 준수 관행이 마련되어 있음을 보여줍니다. 프로그램에는 다음과 같은 단계가 있습니다.

* 게시자 확인.
* 게시자 증명.
* Microsoft 365 인증.

## <a name="publisher-verification"></a>게시자 확인

앱 개발자가 Microsoft에 앱을 제출하려면 인증을 받아야 합니다. 게시자는 MPN(Microsoft 파트너 네트워크) 계정을 사용해 ID를 확인하고 해당 MPN 계정을 앱 등록에 연결합니다. 게시자 확인은 관리자 및 최종 사용자가 앱 개발자의 신뢰성을 파악하는 데 도움이 됩니다. 게시자 인증은 다음과 같은 장점이 있습니다.

* 고객 측면에서 투명성이 증가하고 위험이 감소 - 이 기능은 고객이 자신의 조직에서 사용 중인 앱들을 자신이 신뢰하는 개발자에 의해 게시되었다는 점을 이해할 수 있게 합니다.
* 향상된 브랜딩 - Azure Active Directory 동의 프롬프트, Enterprise Apps 페이지 및 기타 최종 사용자와 관리자가 사용하는 사용자 인터페이스에 `verified` 배지가 표시됩니다.
* 더욱 매끄러운 엔터프라이즈 채택 - 관리자가 게시자 확인 상태를 기본 정책 조건으로 지정한 상태로 사용자 동의 정책을 구성할 수 있습니다.

## <a name="publisher-attestation"></a>게시자 증명

게시자 증명은 앱 규정 준수 프로그램의 다음 계층입니다. 게시자 증명 앱은 앱의 보안 및 규정 준수 조치에 대해 관리자에게 확신을 더해 줍니다. 또한 앱에 대해 이러한 정보를 검토하는 시간을 줄이는 데도 도움이 됩니다. 증명에는 [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security)에서 식별한 80개 이상의 위험 요소에 대한 앱의 보안, 데이터 처리 및 규정 준수 관행이 반영됩니다. 게시자 증명 프로세스는 게시자 확인이 완료되기 전에 시작할 수 있습니다.

앱 개발자는 앱의 보안 및 규정 준수를 평가하기 위해 고객과 IT 관리자가 자주 묻는 질문이 포함된 자체 평가를 완료해야 합니다. 그런 다음 Microsoft는 보다 쉽고 시기 적절한 평가를 위해 이 정보를 게시합니다. 자세한 내용은 [증명 가이드](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)를 참조하세요.

관리자는 게시된 인증 앱을 세 가지 방법으로 빠르게 확인할 수 있습니다.

* 앱에 대한 추가 정보를 수집할 때 [Microsoft Teams 앱 보안 및 규정 준수](/microsoft-365-app-certification/teams/teams-apps) 링크에서 특정 앱의 세부 정보를 확인하세요. 아니면 Teams 관리 센터에서 게시자 증명 링크를 선택합니다.

  :::image type="content" source="media/attested-app-tac3.png" alt-text="Teams 관리 센터에서 게시자 증명 링크를 클릭하여 앱 증명 세부 정보 보기":::

* Teams 관리 센터의 **앱 관리** 페이지에서 앱 세부 정보를 확인할 때 앱 세부 정보 페이지의 배너에 있는 게시자 인증 아이콘을 확인하세요.

  :::image type="content" source="media/attested-app-tac1.png" alt-text="Teams 관리 센터에서 게시자 인증 아이콘은 인증된 모든 앱에 표시됩니다.":::

* Teams 관리 센터에서 앱에 권한을 부여할 때 앱 이름 앞의 파란색 체크 표시는 해당 앱이 게시자 증명 앱 또는 Microsoft 365 인증 앱임을 나타냅니다.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Teams 관리 센터의 권한 부여 대화 상자에서 파란색 체크 표시는 해당 앱이 게시자 증명 앱임을 나타냅니다.":::

증명되거나 인증된 앱의 증명 세부 정보 페이지에는 다음 세부 정보가 나열됩니다.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="증명 앱에 대해 제공되는 세부 정보입니다.":::

## <a name="microsoft-365-certification"></a>Microsoft 365 인증

앱 인증은 다음을 통해 달성됩니다.

* 자격을 갖춘 분석가의 검토.
* 앱의 보안 및 규정 준수 프레임워크, 프로세스 및 절차를 중심으로 한 종합 평가에 대한 승인.

Microsoft는 주요 업계 표준 프레임워크에서 파생된 일련의 보안 제어에 대해 앱을 확인합니다.

이 인증서는 앱이 조직에서 활성화될 때 고객 데이터를 보호하기 위해 강력한 보안 및 규정 준수 관행이 마련되어 있음을 보여줍니다. Microsoft 365 인증이 관리자 및 최종 사용자에게 어떻게 유용한지에 대한 자세한 정보는 [Microsoft 365 앱 규정 준수 프로그램](/microsoft-365-app-certification/docs/enterprise-app-certification-guide) 개요를 참조하세요.

관리자는 다음과 같은 방법으로 Microsoft 365 인증된 앱을 빠르게 확인할 수 있습니다.

* 웹에서 앱에 대한 자세한 정보를 수집하는 경우 앱에 대한 Microsoft 설명서의 방패 아이콘을 확인하세요.

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="앱의 보안 및 규정 준수에 관련된 자세한 도움말 문서에서 Microsoft 365 인증 정보를 확인합니다.":::

* Teams 관리 센터에서 응용 프로그램을 확인할 때 인증 열을 사용하여 앱 목록을 정렬합니다. 아이콘을 확인하고 필요에 따라 링크를 선택하여 위에서 언급한 앱별 페이지에 액세스합니다.

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Teams 관리 센터에서 앱의 Microsoft 365 인증 상태를 확인합니다." lightbox="media/m365cert-apps-list2.png":::

* 앱에 대한 세부 정보를 볼 때 해당 앱의 배너에서 Microsoft 365 인증 아이콘을 확인하세요.

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Teams 관리 센터에서 특정 앱을 관리할 때 해당 앱의 배너에서 Microsoft 365 인증 정보 보기":::

* Teams 관리 센터에서 앱에 권한을 부여할 때 앱 이름 앞의 파란색 체크 표시는 해당 앱이 게시자 증명 앱 또는 Microsoft 365 인증 앱임을 나타냅니다.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Teams 관리 센터의 권한 부여 대화 상자에서 관리자는 파란색 체크 표시를 선택하여 앱이 Microsoft 365 인증을 받았음을 확인할 수 있습니다.":::

## <a name="view-security-compliance-and-privacy-information-in-microsoft-documentation"></a>Microsoft 설명서에서 보안, 규정 준수 및 개인 정보 보호 관련 정보 보기

증명 또는 인증된 앱은 각각의 보안, 개인 정보 보호, 규정 준수 등과 관련된 세부 정보가 [Microsoft Teams 앱 보안 및 규정 준수](/microsoft-365-app-certification/teams/teams-apps)에 링크된 각자의 도움말 문서에 표시됩니다.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Microsoft 규정 준수 프로그램을 거치는 앱에 대해 제공되는 세부 정보입니다.":::

<!--- TBD: Move to the permissions article 

## View the granted Graph permissions in Azure Portal

Admins can grant permission to an app on behalf of all organization users. It helps avoid each user to individually request the permissions. Permissions granted of an admin are called delegated permissions in [Azure Portal](https://aad.portal.azure.com/).

Before you grant any permission to an app, review a list of requested permissions in the [Manage Apps](https://admin.teams.microsoft.com/policies/manage-apps) section of Teams admin center.

:::image type="content" source="media/attested-app-tac2.png" alt-text="In Teams admin center, on the dialog to grant permissions, admins can check the permissions requested by an app.":::

After admins grant the org-wide permissions to an app, they can review the Graph permissions in Azure Portal.

:::image type="content" source="media/tac-perms-in-aad-after-granting1.png" alt-text="Admins can see all the app permissions granted by users and admins in the Azure Portal." lightbox="media/tac-perms-in-aad-after-granting2.png":::
--->

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>앱의 개인 정보 취급 방침 및 사용 약관 보기

Teams 관리 센터의 각 앱 페이지는 해당 앱의 개인정보처리방침 및 사용 약관으로 연결됩니다.

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="Teams 관리 센터에서 관리자는 모든 앱의 개인 정보 취급 방침 및 사용 약관에 대한 링크에 액세스할 수 있습니다." lightbox="media/tac-app-tou-privacy-info2.png":::

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

- How to view the support information for an app in TAC?

- We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->

## <a name="see-also"></a>참고 항목

* [앱 사용 권한 보기 및 관리자 동의 부여](app-permissions-admin-center.md)
