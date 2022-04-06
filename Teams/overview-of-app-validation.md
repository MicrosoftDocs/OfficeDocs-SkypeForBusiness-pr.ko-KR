---
title: Microsoft의 앱 유효성 검사 및 앱 테스트 개요
ms.reviewer: ''
description: Teams 앱에 대한 품질 검사, 앱 유효성 검사 및 인증 프로그램을 이해합니다.
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
ms.openlocfilehash: 384a57abb724ee29feb5f93fa171d0bc5ec96f3d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686495"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Teams 앱에서 Microsoft가 수행한 검사 및 유효성 검사

Microsoft는 최종 사용을 위해 스토어에 나열되기 전에 모든 앱이 필수 유효성 검사를 통과하도록 요구합니다. Teams 앱 스토어에 게시된 모든 앱(사용자 지정 앱 제외)에 적용됩니다. 또한 Microsoft는 앱 개발자가 향상된 규정 준수, 보안 및 개인 정보 제어를 나타내는 앱의 선택적 인증에 참여하도록 강력히 권장합니다.

모든 앱은 Microsoft 앱 인증 정책을 준수해야 합니다. Teams 스토어 팀은 400개 이상의 테스트를 수행하여 앱이 사용 가능하고 높은 수준의 개인 정보 보호 및 보안을 준수하는지 확인합니다.

앱 개발자가 준수하는 자세한 유효성 검사 지침을 알아보려면 [개발자를 위한 유효성 검사 지침을 참조하세요](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). 이 지침은 [Teams 앱에 대한 인증 정책을](/legal/marketplace/certification-policies#1140-teams) 기반으로 합니다.

> [!NOTE]
> Microsoft의 유효성 검사 및 검사는 조직 내에서 개발되고 조직의 구성원만 사용할 수 있으므로 사용자 지정 앱에 사용할 수 없습니다.

## <a name="app-validation-and-testing"></a>앱 유효성 검사 및 테스트

Teams 스토어에서 사용할 수 있게 되기 전에 모든 앱에 대해 400개 이상의 테스트 사례를 실행합니다. 테스트는 적절한 기능, 사용자 환경 및 보안을 보장하고 모든 앱이 공개적으로 나열된 CMO 정책을 준수하는지 확인합니다. 다음은 Microsoft 앱 유효성 검사 팀이 게시하기 전에 모든 앱에 대해 수행한 테스트 중 일부입니다.

* 앱에서 요청한 Graph 권한이 실제로 앱 기능에 필요한 권한이며 추가 권한이 아닌지 확인합니다. 기존 앱에 대한 Graph 권한은 앱에 필요한 추가 권한이 없는지 확인하기 위해 정기적으로 확인됩니다.
* 사용자가 로그인/로그인해야 하는 앱에는 로그/로그아웃 옵션이 있어야 합니다.
* 모든 앱 게시자는 Microsoft 파트너 센터에서 자세한 확인 프로세스를 거칩니다. 확인에는 전자 메일 확인, 비즈니스 확인 등이 포함됩니다. 앱 게시에 대한 자세한 내용은 [개발자가 파트너 센터 계정을 만드는 방법](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [개발자를 위한 제출 가이드 및 개발자](/office/dev/store/add-in-submission-guide)가 [앱을 게시하는 방법을](https://aka.ms/PublishToTeamsStore) 참조하세요.
* 확인된 게시자의 앱만 최종 사용자의 Graph 권한을 검색할 수 있습니다.
* 어떤 앱도 실행 파일을 다운로드할 수 없습니다.
* 앱은 다른 앱에 대한 광고, 프로모션을 포함하지 않도록 테스트됩니다.
* 앱은 공격적인 언어, 사이버 공격 봇, 스팸 또는 사기 콘텐츠 없이 적절하게 작동하도록 테스트됩니다.
* 앱의 모든 링크는 작동하며 앱 제품과만 관련이 있습니다.
* 앱 스토어 상태 검사의 일환으로 게시된 모든 Teams 앱을 정기적으로 테스트하고 평가합니다.
* ISV에서 Teams 앱을 게시하는 개인 정보 취급 방침 및 사용 약관
* ISV의 연락처 세부 정보는 매장 목록 및 해당 [Publisher 증명 페이지에서](/microsoft-365-app-certification/teams/teams-apps) 사용할 수 있습니다.

## <a name="publisher-verification"></a>Publisher 확인

Publisher 확인은 관리자와 최종 사용자가 Microsoft ID 플랫폼 통합하는 애플리케이션 개발자의 신뢰성을 이해하는 데 도움이 됩니다. 확인된 게시자가 있으면 게시자가 MPN(Microsoft 파트너 네트워크) 계정을 사용하여 ID를 확인하고 이 MPN 계정을 앱 등록과 연결했음을 의미합니다.

Publisher 확인은 다음과 같은 이점을 제공합니다.

* 고객에 대한 투명성 및 위험 감소 증가 - 이 기능을 통해 고객은 신뢰할 수 있는 개발자가 조직에서 어떤 앱을 게시하는지 이해할 수 있습니다.
* 향상된 브랜딩 - `verified` Azure Active Directory 동의 프롬프트, Enterprise 앱 페이지 및 최종 사용자 및 관리자가 사용하는 기타 사용자 인터페이스에 배지가 표시됩니다.
* 원활한 엔터프라이즈 채택 - 관리자는 게시자 확인 상태를 기본 정책 조건으로 사용하여 사용자 동의 정책을 구성할 수 있습니다.

또한 Microsoft는 앱 개발자가 엄격한 2계층 접근 방식인 규정 준수 프로그램에 참여하여 앱 품질, 보안 및 규정 준수를 보장하도록 권장합니다. Teams 스토어에는 이미 상세한 유효성 검사 지침을 충족하고 이러한 프로그램을 준수하는 수백 개의 앱이 있습니다.

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365 앱 규정 준수 프로그램

Microsoft 규정 준수 프로그램은 앱이 업계 최고의 표준 프레임워크에서 파생된 컨트롤에 대해 심사를 받고 고객 데이터를 보호하기 위한 강력한 보안 및 규정 준수 사례가 마련되어 있음을 보여 줍니다. 프로그램에는 다음 두 단계가 있습니다.

* Publisher 증명입니다.
* Microsoft 365 인증.

### <a name="publisher-attestation"></a>Publisher 증명

앱 개발자는 앱의 보안 및 규정 준수를 평가할 때 고객 또는 IT 관리자가 자주 묻는 질문을 포함하는 자체 평가를 완료해야 합니다. 그런 다음 Microsoft는 더 쉽고 시기 적절한 평가를 위해 이 정보를 게시합니다. 이 정보에는 조직에서 앱이 활성화될 때 데이터 처리, 보안, 규정 준수 및 개인 정보 보호에 대한 세부 정보가 포함됩니다.

자세한 내용은 [게시 증명 가이드](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)를 참조하세요.

### <a name="microsoft-365-certification"></a>Microsoft 365 인증

앱 인증은 앱의 보안 및 규정 준수 프레임워크, 프로세스 및 절차를 중심으로 하는 포괄적인 평가에 대한 적격 분석가의 검토 및 승인을 통해 달성됩니다. 이 앱은 업계 최고의 표준 프레임워크에서 파생된 일련의 보안 제어에 대해 심사됩니다. 이 인증서는 조직에서 앱이 활성화될 때 고객 데이터를 보호하기 위한 강력한 보안 및 규정 준수 사례가 마련되어 있음을 보여 줍니다.

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
