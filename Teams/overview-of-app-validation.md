---
title: Microsoft의 앱 유효성 검사 및 앱 테스트 개요
ms.reviewer: ''
description: Teams 앱에 대해 수행된 품질 검사 및 앱 유효성 검사에 대해 이해합니다.
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
ms.openlocfilehash: fa6a03c5408afcd7cce1d3e48b78b3b1ddb3675a
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2022
ms.locfileid: "64756994"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>모든 Teams 앱에 대해 Microsoft에서 수행한 유효성 검사

Microsoft는 모든 앱이 최종 사용을 위해 스토어에 표시되기 전에 필수 유효성 검사를 통과하도록 요구합니다. 이는 Teams 앱 스토어에 게시된 모든 앱(사용자 지정 앱 제외)에 적용됩니다. 또한 Microsoft는 앱 개발자가 향상된 규정 준수, 보안 및 개인 정보 보호 제어를 나타내는 앱의 선택적 인증에 참여하도록 강력히 권장합니다.

모든 앱은 Microsoft 앱 인증 정책을 준수해야 합니다. Teams 스토어 팀은 앱을 사용할 수 있는지 확인하고 해당 앱이 높은 수준의 개인 정보 보호 및 보안을 준수하도록 하기 위해 400개 이상의 테스트를 수행합니다.

앱 개발자가 준수하는 자세한 유효성 검사 지침을 확인하려면 [개발자를 위한 유효성 검사 지침](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)을 참조하세요. 해당 지침은 [Teams 앱 인증 정책](/legal/marketplace/certification-policies#1140-teams)을 기반으로 합니다.

> [!NOTE]
> 사용자 지정 앱은 조직 내에서 개발되어 조직 구성원들만 이용할 수 있으므로 Microsoft의 유효성 검사와 확인을 사용할 수 없습니다.

## <a name="app-validation-and-testing"></a>앱 유효성 검사 및 테스트

Microsoft에서는 모든 앱을 Teams 스토어에서 사용하도록 하기 전에 400번 이상의 테스트를 실행합니다. 테스트를 통해 적절한 기능, 사용자 환경, 보안을 확인하며 모든 앱이 공개적으로 표시된 CMO 정책을 준수하는지 확인합니다. Microsoft 앱 유효성 검사 팀이 모든 앱을 게시하기 전에 해당 앱에 대해 수행하는 테스트 중 일부는 다음과 같습니다.

* 앱에서 요청한 그래프 권한이 실제로 해당 앱의 기능에 필요하며 추가 권한이 아닌지 확인합니다. 기존 앱의 그래프 권한을 정기적으로 확인해 앱에서 추가 권한을 요청할 필요가 없는지 확인합니다.
* 사용자가 로그인해야 하는 앱에 로그아웃 옵션이 있는지 확인합니다.
* 모든 앱 게시자가 Microsoft 파트너 센터의 자세한 확인 프로세스를 거치는지 확인합니다. 확인에는 전자 메일 확인, 비즈니스 확인 등이 포함됩니다. 앱 게시에 대한 자세한 내용은 [개발자가 파트너 센터 계정을 생성하는 방법](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [개발자용 제출 가이드](/office/dev/store/add-in-submission-guide), [개발자가 앱을 게시하는 방법](https://aka.ms/PublishToTeamsStore)을 참조하세요.
* 확인된 게시자의 앱만 최종 사용자의 그래프 권한을 검색할 수 있습니다.
* 어떤 앱도 실행 파일을 다운로드할 수 없습니다.
* 앱에 다른 앱의 광고나 프로모션이 없는지 검사합니다.
* 앱에 모욕적인 언어, 사이버 공격용 봇, 스팸, 사기 콘텐츠가 없이 적절하게 작동하는지 검사합니다.
* 앱의 모든 링크가 작동하며 앱에서 제공되는 내용만 연결됩니다.
* 게시된 모든 Teams 앱을 앱 스토어 상태 검사의 일부로 검사하고 평가합니다.
* Teams 앱을 취급하는 개인 정보 취급 방침 및 사용 약관이 ISV를 통해 게시됩니다.
* ISV의 연락처 세부 정보는 스토어 목록 및 앱 각각의 [게시자 증명 페이지](/microsoft-365-app-certification/teams/teams-apps)에서 확인할 수 있습니다.

또한 Microsoft에서는 앱 개발자들이 앱 품질, 보안, 규정 준수의 보장을 위해 두 계층으로 나누어 엄격히 접근되는 규정 준수 프로그램에 참여하도록 권장합니다. Teams 스토어에는 이미 세부적인 유효성 검사 지침을 충족하고 이러한 프로그램을 준수하는 수준을 넘는 앱이 수백 개 있습니다.

## <a name="publisher-verification"></a>게시자 확인

앱 개발자가 Microsoft에 앱을 제출하려면 인증을 받아야 합니다. 게시자는 MPN(Microsoft 파트너 네트워크) 계정을 통해 ID를 확인하고 해당 MPN 계정을 앱 등록에 연결합니다. 게시자 확인은 관리자 및 최종 사용자가 Microsoft ID 플랫폼과 통합하는 앱 개발자의 신뢰성을 파악하는 데 도움이 됩니다. 게시자 인증은 다음과 같은 장점이 있습니다.

* 고객 측면에서 투명성이 증가하고 위험이 감소 - 이 기능은 고객이 자신의 조직에서 사용 중인 앱들을 자신이 신뢰하는 개발자에 의해 게시되었다는 점을 이해할 수 있게 합니다.
* 향상된 브랜딩 - Azure Active Directory 동의 프롬프트, Enterprise Apps 페이지 및 기타 최종 사용자와 관리자가 사용하는 사용자 인터페이스에 `verified` 배지가 표시됩니다.
* 더욱 매끄러운 엔터프라이즈 채택 - 관리자가 게시자 확인 상태를 기본 정책 조건으로 지정한 상태로 사용자 동의 정책을 구성할 수 있습니다.

## <a name="see-also"></a>참고 항목

* [Microsoft 365 앱 규정 준수 프로그램 관리자 개요](overview-of-app-certification.md)
