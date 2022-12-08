---
title: 무료 Microsoft Teams(클래식) 구독으로 업그레이드
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: 사용자에 대한 Microsoft 365 또는 Office 365 구독 플랜을 구입하여 무료 Microsoft Teams(클래식) 전체 버전으로 쉽게 업그레이드하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8fadec9c28eae01f28be2e8c61f865b9d2004480
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307633"
---
# <a name="upgrade-microsoft-teams-free-classic-to-subscription-version"></a>구독 버전으로 무료 Microsoft Teams(클래식) 업그레이드

조직에서 무료 Microsoft Teams(클래식) 사용하는 경우 사용자에 대한 Microsoft 365 또는 Office 365 구독 플랜을 구입하여 쉽게 전체 버전으로 업그레이드할 수 있습니다. 전체 버전은 무료 버전이 제공하지 않는 오디오 회의, 향상된 관리 및 보안 기능과 같은 다른 Teams 기능을 제공합니다. Microsoft 365 및 Office 365 친숙한 Microsoft Office 데스크톱 제품군과 클라우드 기반 버전의 Microsoft 차세대 통신 및 협업 서비스(Exchange Online, SharePoint Online 및 Office 포함)를 결합하여 사용자가 어디서나 생산성을 높일 수 있도록 지원합니다. 인터넷. Teams를 업그레이드하면 기존 Teams 데이터가 손실되지 않습니다. 모든 팀, 채널, 채팅, 파일 및 사용 권한이 제공됩니다.

> [!NOTE]
> 이미 Microsoft 365 또는 Office 365 구독이 있는 경우 무료 버전이 아닌 Teams 평가판 버전(회사 ID 포함)을 받을 수 있습니다. Teams 평가판은 제한된 시간 동안 전체 버전의 Teams를 제공합니다. 자세한 내용은 [Microsoft Teams 상업용 클라우드 평가판 제품 관리를 참조하세요](./teams-exploratory.md).

## <a name="how-does-teams-free-classic-compare-to-the-full-version-of-teams"></a>Teams 무료(클래식)는 전체 버전의 Teams와 어떻게 비교하나요?

Teams Free(클래식)는 중소기업을 위해 설계되었으며 다음과 같은 기능이 있습니다.

- 최대 사용자 500,000명
- 무제한 채팅 메시지 및 검색
- 게스트 액세스
- Word, Excel, PowerPoint 및 OneNote의 온라인 버전을 비롯한 앱 및 서비스와 통합
- 사용자당 2GB의 스토리지 및 10GB의 공유 스토리지
- 1:1 및 온라인 오디오 및 화상 통화 그룹화
- 채널 모임
- 화면 공유.

Microsoft 365 또는 Office 365 구독에 포함된 Teams의 전체 버전은 무료 Microsoft Teams(클래식) 제공하는 기능 외에도 다음과 같은 기능을 제공합니다.

- 사용자 제한 없음(엔터프라이즈 라이선스 포함)
- Exchange 전자 메일 호스팅 및 사용자 지정 전자 메일 도메인
- OneDrive, SharePoint, Planner, Yammer 등 Microsoft 365 및 Office 365 서비스
- 사용자당 1TB의 스토리지
- 예약된 모임
- 오디오 회의
- 다단계 인증, Single Sign-On, 감사(프리미엄) 및 보고를 비롯한 향상된 보안 및 규정 준수 기능
- 24 x 7 전화 및 웹 지원, 사용자 및 앱을 관리하기 위한 관리 도구, Microsoft 365 또는 Office 365 서비스에 대한 사용 현황 보고, 서비스 수준 계약 및 구성 가능한 사용자 설정 및 정책을 포함한 관리 제어 및 지원 기능

Teams 무료(클래식) 및 Teams 기능에 대한 자세한 비교는 [Teams 계획 비교를 참조하세요](https://products.office.com/microsoft-teams/free).

## <a name="upgrade-requirements"></a>업그레이드 요구 사항

다음 요구 사항을 충족하는 경우 Teams의 전체 버전으로 업그레이드할 수 있습니다.

- 기존 무료 Microsoft Teams(클래식) 구독에 등록한 사용자입니다.
- 자체 도메인을 가져오는 경우 평가판 또는 구매한 Microsoft 365 또는 Office 365 구독을 통해 Azure Active Directory와 아직 연결되지 않았습니다.

> [!NOTE]
> 데이터를 업그레이드하고 전송하려면 Teams 애플리케이션의 업그레이드 프로세스를 통해 구독을 구입해야 합니다. 업그레이드 프로세스를 거치지 않고 teams에서 Microsoft 365 또는 Office 365 구매한 경우 이미 별도의 테넌트가 있으므로 데이터를 전송할 수 없습니다.

## <a name="limitations"></a>제한 사항

다음 제한 사항에 유의하세요.

- 업그레이드한 후에는 Teams 무료(클래식)로 다시 전환할 수 없습니다.
- 여러 Teams 무료(클래식) 테넌트는 단일 유료 테넌트로 병합할 수 없습니다.
- 모든 사용자는 동일한 도메인에 있어야 합니다. (모든 사용자는 *사용자 이름*@ 형식으로 로그인합니다. *domain.com*.)
- 모든 사용자를 업그레이드해야 합니다. 동일한 테넌트의 Teams 무료(클래식) 및 유료 구독 사용자의 혼합은 지원되지 않습니다.

## <a name="how-do-i-upgrade-my-organization"></a>조직을 업그레이드하려면 어떻게 해야 하나요?

Teams의 전체 버전으로 업그레이드하려면 Teams에서 **업그레이드** 를 선택합니다.

![업그레이드 단추를 보여 주는 스크린샷](media/teams-freemium-upgrade-image1.png)

Teams에 로그인하는 데 사용하는 전자 메일 주소를 입력한 다음, Microsoft 365 Business Standard 플랜을 구입합니다. Microsoft 365 Business Basic 또는 Enterprise 버전의 Office 365 구입하려면 [지원에 문의하세요](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade).

## <a name="whats-next"></a>다음 단계는 무엇인가요?

업그레이드가 완료되면 첫 번째 단계는 [Microsoft Teams 시작을](get-started-with-teams-quick-start.md) 참조하고 조직 전체에서 Teams 채택에 대한 단계별 접근 방식은 [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)을 참조하세요.

## <a name="more-information"></a>추가 정보

- Teams 버전 및 해당 기능에 대한 자세한 내용은 [Teams 계획 비교를 참조하세요](https://products.office.com/microsoft-teams/free).
- 전체 버전의 Teams로 업그레이드하는 방법에 대한 자세한 내용은 [Teams 무료(클래식)에서 Teams로 업그레이드를 참조하세요](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39).
- 사용자 라이선스 추가, 사용자 이름 변경, 임시 암호 할당 등 사용자 업그레이드와 관련된 다른 관리 작업에 대한 자세한 내용은 [Teams 무료(클래식)에서 유료 구독으로 업그레이드하는 관리자의 경우를](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52) 참조하세요.
- 조직에서 무료로 Teams를 관리하는 방법에 대한 자세한 내용은 [Microsoft Teams 무료 관리(클래식)](manage-freemium.md)를 참조하세요.