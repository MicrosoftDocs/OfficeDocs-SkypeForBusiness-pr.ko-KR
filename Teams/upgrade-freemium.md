---
title: 구독으로 Microsoft Teams 무료 업그레이드
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: 사용자에 대한 Microsoft 365 또는 Office 365 구독 요금제를 구입하여 무료 버전의 Microsoft Teams에서 정식 버전으로 쉽게 업그레이드하는 방법을 알아보습니다.
localization_priority: Normal
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
ms.openlocfilehash: 7c4b95081be4c7a0e900099dd4c81a1807a30bfb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122162"
---
# <a name="upgrade-microsoft-teams-free-to-subscription-version"></a>구독 버전으로 Microsoft Teams 무료 업그레이드

조직에서 무료 버전의 Microsoft Teams를 사용하는 경우 사용자에 대한 Microsoft 365 또는 Office 365 구독 요금제를 구입하여 정식 버전으로 쉽게 업그레이드할 수 있습니다. 정식 버전은 무료 버전이 제공하지 않는 추가 Teams 기능(즉, 계획, 오디오 회의, 향상된 관리 및 보안 기능)을 제공합니다. Microsoft 365 및 Office 365는 익숙한 데스크톱 Microsoft Office Microsoft의 차세대 통신 및 공동 작업 서비스(Exchange Online, SharePoint Online 및 Office)의 클라우드 기반 버전과 결합하여 사용자가 인터넷을 통해 거의 모든 곳에서 생산성을 향상할 수 있도록 합니다. Teams를 업그레이드하면 기존 Teams 데이터가 손실되지 않습니다. 모든 팀, 채널, 채팅, 파일 및 사용 권한이 함께 제공됩니다. 

> [!NOTE]
> Microsoft 365 또는 Office 365 구독이 이미 있는 경우 무료 버전이 아닌 평가판 버전의 Teams(회사 ID가 있는)를 사용할 수 있습니다. Teams 평가판은 제한된 시간 동안 전체 버전의 Teams를 제공 합니다. 자세한 내용은 [Microsoft Teams 상용 클라우드 평가판 제품 관리를 참조하세요.](./teams-exploratory.md)

## <a name="how-does-teams-free-compare-to-the-full-version-of-teams"></a>Teams 무료는 전체 버전의 Teams와 어떻게 비교하나요?

Teams 무료는 중소기업을 위해 디자인되었습니다. 다음과 같은 기능이 있습니다.

- 최대 사용자 500,000명
- 무제한 채팅 메시지 및 검색
- 게스트 액세스
- Word, Excel, PowerPoint 및 OneNote의 온라인 버전을 포함하여 앱 및 서비스와 통합
- 사용자당 저장소 2GB 및 공유 저장소 10GB
- 1:1 및 그룹 온라인 오디오 및 비디오 통화
- 채널 모임
- 화면 공유

Microsoft 365 또는 Office 365 구독에 포함된 전체 버전의 Teams는 Teams에서 무료로 제공하는 기능 외에도 다음과 같은 기능을 제공합니다.

- 사용자 제한 없음(엔터프라이즈 라이선스 사용)
- Exchange 전자 메일 호스팅 및 사용자 지정 전자 메일 도메인
- OneDrive, SharePoint, Planner, Yammer 및 더 많은 Microsoft 365 및 Office 365 서비스
- 사용자당 1 TB의 저장소
- 예약된 모임
- 오디오 회의
- 다단계 인증, Single Sign-On 및 고급 감사 및 보고를 비롯한 향상된 보안 및 규정 준수 기능
- 24 x 7 전화 및 웹 지원, 사용자 및 앱 관리를 위한 관리 도구, Microsoft 365 또는 Office 365 서비스 사용 현황 보고, 서비스 수준 계약 및 구성 가능한 사용자 설정 및 정책을 비롯한 관리 제어 및 지원 기능

Teams 무료 및 Teams 기능에 대한 자세한 비교는 Teams 계획 비교 [를 참조합니다.](https://products.office.com/microsoft-teams/free)

## <a name="upgrade-requirements"></a>업그레이드 요구 사항

다음 요구 사항을 충족하는 경우 전체 버전의 Teams로 업그레이드할 수 있습니다.

- 기존 Teams 무료 구독에 등록한 사용자입니다.
- 사용자 자신의 도메인을 가져오는 경우 Azure Active Directory와 아직 연결되어 있지 않습니다(평가판을 통해 또는 Microsoft 365 또는 Office 365 구독을 통해 구입).

> [!NOTE]
> 데이터를 업그레이드하고 전송하려면 Teams 애플리케이션의 업그레이드 프로세스를 통해 구독을 구입해야 합니다. 업그레이드 프로세스를 거치지 않고 Teams에서 Microsoft 365 또는 Office 365를 구입한 경우 이미 별도의 테넌트가 있기 때문에 데이터를 전송할 수 없습니다.

## <a name="limitations"></a>제한 사항

다음 제한 사항을 염두에 두어야 합니다.

- 업그레이드한 후 Teams 무료로 다시 전환할 수 없습니다.
- 여러 Teams 무료 테넌트는 단일 유료 테넌트에 병합할 수 없습니다.
- 모든 사용자는 동일한 도메인에 있어야 합니다. (모든 사용자는 사용자 이름 형식에 *로그인합니다.* @ *domain.com*.)
- 모든 사용자를 업그레이드해야 합니다. 동일한 테넌트의 Teams 무료 및 유료 구독 사용자 조합은 지원되지 않습니다.

## <a name="how-do-i-upgrade-my-organization"></a>조직을 업그레이드하려면 어떻게 해야 하나요?

전체 버전의 Teams로 업그레이드하려면 **Teams에서 업그레이드를** 선택합니다.

![업그레이드 단추를 보여주는 스크린샷](media/teams-freemium-upgrade-image1.png)

Teams에 로그인하는 데 사용하는 전자 메일 주소를 입력한 다음 Microsoft 365 비즈니스 표준 요금제를 구입합니다. Microsoft 365 Business Basic 또는 Office 365 엔터프라이즈 에디션을 구입하고자 하는 경우 지원 에 [문의합니다.](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade)

## <a name="whats-next"></a>다음은 어떻게 하나요?

업그레이드가 완료되면 첫 번째 단계에 대해 [Microsoft Teams](get-started-with-teams-quick-start.md) 시작을 참조하고 조직 전체에서 Teams 채택에 대한 단계적 접근 방식에 대해 [Microsoft Teams](adopt-microsoft-teams-landing-page.md) 채택을 참조하세요.

## <a name="more-information"></a>추가 정보

- Teams 버전 및 해당 기능에 대한 자세한 내용은 Teams 계획 비교 [를 참조합니다.](https://products.office.com/microsoft-teams/free)
- 전체 버전의 Teams로 업그레이드하는 데 대한 자세한 내용은 [Teams에서 Teams로 무료 업그레이드를 참조하세요.](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)
- 사용자 라이선스 추가, 사용자 이름 변경, 임시 암호 할당 등 사용자 업그레이드와 관련된 추가 관리 작업은 Teams에서 유료 구독으로 무료 업그레이드하는 관리자를 [참조하세요.](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)
- 조직의 팀 무료 관리에 대한 자세한 내용은 Microsoft Teams의 무료 버전 [관리를 참조하세요.](manage-freemium.md)