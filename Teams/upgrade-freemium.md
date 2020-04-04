---
title: Microsoft 팀에서 Office 365 구독으로 무료 업그레이드
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/20/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
search.appverid: MET150
description: 무료 버전의 Microsoft 팀을 업그레이드 하는 방법 알아보기
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6019491c7e72e91c9f3cfbcaec8a4c60ae297c14
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139647"
---
# <a name="upgrade-microsoft-teams-free-to-office-365-subscription-version"></a>Microsoft 팀의 무료 Office 365 구독 버전 업그레이드
======================================================

조직에서 무료 버전의 Microsoft 팀을 사용 하는 경우 사용자를 위해 Office 365 구독 계획을 구매 하 여 정식 버전으로 쉽게 업그레이드할 수 있습니다. 정식 버전은 예약, 오디오 회의, 향상 된 관리, 보안 기능 등 무료 버전이 제공 하지 않는 추가 팀 기능을 제공 합니다. Office 365는 친숙 한 Microsoft Office 데스크톱 제품군과 Exchange Online, SharePoint Online, Office를 포함 하 여 클라우드 기반 Microsoft의 차세대 통신 및 공동 작업 서비스를 결합 하 여 사용자가 인터넷을 통해 사실상 생산성을 높일 수 있도록 지원 합니다. 팀을 업그레이드할 때 기존 팀 데이터가 손실 되지 않습니다. 모든 팀, 채널, 채팅, 파일, 사용 권한을 함께 얻을 수 있습니다. 

> [!NOTE]
> 이미 Office 365 구독이 있는 경우 무료 버전이 아닌 회사 id를 사용 하 여 팀 평가판을 사용할 수 있습니다. 팀 평가판은 제한 된 시간 동안 팀의 전체 버전을 제공 합니다. 자세한 내용은 [Microsoft 팀 상업용 클라우드 평가판 제공 관리](iw-trial-teams.md)를 참조 하세요.

## <a name="how-does-teams-free-compare-to-the-full-version-of-teams"></a>팀에서 정식 버전의 팀을 자유롭게 비교 하는 방법

무료 팀은 중소 기업에 맞게 설계 되었으며 다음과 같은 기능을 제공 합니다.

- 300 최대 사용자 수
- 무제한 채팅 메시지 및 검색
- 게스트 액세스
- Word, Excel, PowerPoint, OneNote의 온라인 버전을 포함 하 여 앱 및 서비스 통합
- 2 GB의 사용자 당 저장소 및 공유 저장소 10gb
- 1:1 및 그룹 온라인 오디오 및 영상 통화
- 채널 모임
- 화면 공유

Office 365 구독에 포함 된 팀의 전체 버전은 팀에서 무료으로 제공 하는 기능 외에 다음과 같은 기능을 제공 합니다.

- 사용자 제한 없음 (엔터프라이즈 라이선스 사용)
- Exchange 전자 메일 호스팅 및 사용자 지정 전자 메일 도메인
- OneDrive, SharePoint, Planner, Yammer 등의 Office 365 서비스
- 사용자 당 1TB 저장소
- 예약 된 모임
- 오디오 회의
- 다단계 인증, single sign-on, 고급 감사 및 보고를 비롯 한 향상 된 보안 및 준수 기능
- 24 x 7 휴대폰 및 웹 지원, 사용자 및 앱 관리용 관리 도구, Office 365 서비스 사용 현황 보고, 서비스 수준 계약, 구성 가능한 사용자 설정 및 정책 등의 관리 제어 및 지원 기능

팀의 무료 및 팀 기능에 대 한 자세한 비교는 [팀 계획 비교](https://products.office.com/microsoft-teams/free)를 참조 하세요.

## <a name="upgrade-requirements"></a>업그레이드 요구 사항

다음 요구 사항을 충족 하는 경우 정식 버전의 팀으로 업그레이드할 수 있습니다.

- 기존 팀 무료 구독에 등록 한 사람입니다.
- 자신의 도메인을 가져오는 경우 Azure Active Directory와 연결 되어 있지 않습니다 (평가판 또는 구매한 O365 구독 사용).

> [!NOTE]
> 데이터를 업그레이드 하 고 전송 하려면 팀 응용 프로그램의 업그레이드 프로세스를 통해 구독을 구입 해야 합니다. 업그레이드 프로세스를 거치지 않고 Office 365을 구입한 경우에는 별도의 테 넌 트가 이미 있으므로 데이터를 전송할 수 없습니다.

## <a name="limitations"></a>따릅니다

다음과 같은 제한 사항을 염두에 두어야 합니다.

- 업그레이드 한 후에는 팀으로 다시 전환할 수 없습니다.
- 여러 팀 무료 테 넌 트를 단일 유료 테 넌 트로 병합할 수 없습니다.
- 모든 사용자가 같은 도메인에 있어야 합니다. (모든 사용자는 사용자 *이름*@*domain.com*형식으로 로그인을 받습니다.)
- 모든 사용자를 업그레이드 해야 함: 같은 테 넌 트에서 팀의 무료 및 유료 구독 사용자가 혼합 되어 지원 되지 않습니다.

## <a name="how-do-i-upgrade-my-organization"></a>조직을 업그레이드 하려면 어떻게 하나요?

정식 버전의 팀으로 업그레이드 하려면 팀에서 **업그레이드** 를 선택 합니다.

![업그레이드 단추를 보여 주는 스크린샷](media/teams-freemium-upgrade-image1.png)

팀에 로그인 하는 데 사용 하는 전자 메일 주소를 입력 한 다음 Office 365 Business Premium 계획을 구입 합니다. Office 365 비즈니스 Essentials 또는 엔터프라이즈 버전의 Office 365을 구입 하려면 [고객 지원에 문의 하세요](https://portal.office.com/support/altusupport.aspx?app=teamsfreeupgrade).

## <a name="whats-next"></a>다음에는 어떤 것이 있나요?

업그레이드가 완료 된 후에는 [Microsoft 팀](get-started-with-teams-quick-start.md) 의 첫 번째 단계를 시작 하 고 조직 내에서 팀 채택을 단계적으로 사용 하도록 [Microsoft 팀을 채택](adopt-microsoft-teams-landing-page.md) 하세요.

## <a name="more-information"></a>추가 정보

- 팀 버전 및 해당 기능에 대 한 자세한 내용은 [팀 계획 비교](https://products.office.com/microsoft-teams/free)를 참고 하세요.
- 팀의 정식 버전으로 업그레이드 하는 방법에 대 한 자세한 내용은 팀 [에서 무료 팀으로 업그레이드](https://support.office.com/article/Upgrade-from-Teams-free-to-Teams-29475bbd-a34f-4175-9b33-d44430f8ad39)를 참조 하세요.
- 사용자 라이선스 추가, 사용자 이름 변경, 임시 암호 지정을 포함 하 여 사용자 업그레이드와 관련 된 추가 관리자 작업의 경우 [팀에서 무료 구독으로의 관리자 업그레이드](https://support.office.com/article/for-admins-upgrading-from-teams-free-to-a-paid-subscription-75a95e7f-001e-42d0-a787-ae8b992d5a52)를 참조 하세요.
- 조직에서 팀을 무료로 관리 하는 방법에 대 한 자세한 내용은 [무료 버전의 Microsoft 팀 관리](manage-freemium.md)를 참조 하세요.

