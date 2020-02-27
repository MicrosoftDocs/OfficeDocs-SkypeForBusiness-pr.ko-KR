---
title: Microsoft 팀의 보안 및 준수에 대 한 개요
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: 감사 및 보고, 준수 콘텐츠 검색, eDiscovery 등의 Microsoft 팀의 보안 및 규정 준수 기능에 대해 간략하게 설명 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27c46949391ec37178985ab3ed4a08aebc7e5747
ms.sourcegitcommit: 29034bda30a8460eb18600785f785528d0944041
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42285740"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft 팀의 보안 및 규정 준수

> [!IMPORTANT]
> Office 365의 고객은 데이터를 소유 하 고 제어 합니다. Microsoft는 귀하가 구독 한 서비스를 제공 하는 것 외에는 데이터를 사용 하지 않습니다. 서비스 제공 업체는 전자 메일, 문서 또는 팀이 광고 또는 서비스와 관련이 없는 목적을 검사 하지 않습니다. Microsoft는 업로드 된 콘텐츠에 액세스할 수 없습니다. 비즈니스용 OneDrive 및 SharePoint Online과 마찬가지로 고객 데이터는 테 넌 트 내에 남아 있습니다. [Microsoft 보안 센터](https://microsoft.com/trustcenter)에서 신뢰 및 보안 관련 정보에 대 한 자세한 내용을 확인할 수 있습니다. 팀은 Microsoft 보안 센터와 동일한 지침 및 원칙을 따릅니다.

Microsoft 팀은 고객이 기대 하는 고급 보안 및 규정 준수 기능을 제공 하는 Office 365 하이퍼 규모의 엔터프라이즈 등급 클라우드를 기반으로 합니다. O365의 보안 계획에 대 한 자세한 내용은 해당 O365 콘텐츠를 검토 하세요. [O365 보안 로드맵](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) 을 시작 하는 것이 좋습니다. O365의 준수 계획에 대 한 자세한 내용은 [보안 및 준수 계획](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) 문서를 사용 하 여 시작할 수 있습니다.

이 문서에서는 팀 관련 보안 및 준수에 대 한 자세한 정보를 제공 합니다. 보안 및 규정 준수에 대 한 다음 Microsoft 기술 비디오를 검토 해야 합니다.

- [Microsoft 팀의 주요 기능: 보안 및 준수](https://youtu.be/91lHNKVVvQ4) (12:42 분)
- [Microsoft 팀의 보안 및 규정 준수 제어](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 분)

## <a name="security"></a>보안

팀은 팀 전체 및 조직 차원의 두 요소 인증, Active Directory를 통한 single sign-on, 전송 및 남은 데이터의 암호화를 적용 합니다. 파일은 SharePoint에 저장 되며 SharePoint 암호화를 통해 지원 됩니다. 노트는 OneNote에 저장 되며 OneNote 암호화를 통해 지원 됩니다. OneNote 데이터는 팀 SharePoint 사이트에 저장 됩니다. 위 키 탭을 사용 하 여 노트를 작성 하 고 해당 콘텐츠도 팀 SharePoint 사이트 내에 저장할 수도 있습니다.

인증 및 팀에 대 한 자세한 내용을 확인 하기 위해 [id 모델 및 인증](identify-models-authentication.md) 을 읽고, [최신 인증 작동 방식](sign-in-teams.md) 에서는 최신 인증을 사용 하는 것이 특히 도움이 됩니다.

팀은 SharePoint, OneNote, Exchange 등과의 협력 관계를 사용 하기 때문에 O365의 모든 보안을 관리 하는 것이 좋습니다. Office 365 보안에 대 한 자세한 내용은 [보안 강화를 위해 office 365 테 넌 트 구성을](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)읽어 보세요.

> [!NOTE]
> 현재 [개인 채널](private-channels.md) 은 제한 된 보안 및 규정 준수 기능을 지원 합니다. 개인 채널의 모든 보안 및 규정 준수 기능에 대 한 지원은 곧 제공 될 예정입니다.

### <a name="advance-threat-protection-atp"></a>ATP (고급 위협 보호)

Microsoft 팀은 SharePoint 및 비즈니스용 OneDrive, 콘텐츠 관리용 팀과 통합 되는 응용 프로그램 등의 ATP (사전 위협 방지)를 사용할 수 있습니다. ATP를 사용 하 여 이러한 응용 프로그램의 콘텐츠가 악의적인 지 여부를 확인 하 고 사용자 액세스에서이 콘텐츠를 차단할 수 있습니다.

검색 후에는 O365에서 선택한 설정에 영향을 받는 콘텐츠를 관리 하는 방법에 대해 설명 합니다. 모든 응용 프로그램에서 ATP를 구성 하는 것이 좋으며, 추가 정보를 얻기 위해 [SharePoint, OneDrive 및 Microsoft 팀 문서에 대 한 Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) 에는 시작 방법에 대 한 자세한 정보가 포함 됩니다.

### <a name="safe-links"></a>안전한 링크

이번에는 Microsoft 팀에서 ATP 안전한 링크를 사용할 수 없으므로 나중에 사용할 수 있어야 하며,이 경우이 내용이 업데이트 되어 사용자에 게 알려 드립니다. 그 동안 O365 안전한 링크에 대 한 자세한 내용은 [Office 365 ATP 안전 링크](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)를 검토 하세요.

### <a name="how-conditional-access-policies-work-for-teams"></a>팀에 조건부 액세스 정책이 작동 하는 방식

Microsoft 팀은 모임, 일정, interop 채팅, 파일 공유 등의 핵심 생산성 시나리오를 위해 Exchange Online, SharePoint Online, 비즈니스용 Skype Online에 크게 의존 합니다. 이러한 클라우드 앱에 대해 설정 된 조건부 액세스 정책은 사용자가 모든 클라이언트에서 Microsoft 팀에 직접 로그인 할 때 Microsoft 팀에 적용 됩니다.

Microsoft 팀은 Azure Active Directory 조건부 액세스 정책의 클라우드 앱으로 별도로 지원 됩니다. Microsoft 팀 클라우드 앱에 대해 설정 된 조건부 액세스 정책은 사용자가 로그인 할 때 Microsoft 팀에 적용 됩니다. 그러나 Exchange Online 및 SharePoint Online과 같은 다른 앱에 대 한 올바른 정책이 없는 경우에도 사용자는 해당 리소스에 직접 액세스할 수 있습니다. Azure 포털에서 조건부 액세스 정책을 설정 하는 방법에 대 한 자세한 내용은 [Azure Active Directory 빠른](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)시작을 참조 하세요.

Windows 및 Mac 용 Microsoft 팀 데스크톱 클라이언트는 최신 인증을 지원 합니다. 최신 인증은 office 용 ADAL (Active Directory 인증 라이브러리)을 플랫폼 전체의 Microsoft Office 클라이언트 응용 프로그램에 따라 로그인 합니다.

Microsoft 팀 데스크톱 응용 프로그램에서 AppLocker를 지원 합니다.  AppLocker 전제 조건에 대 한 자세한 내용은 [applocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)를 사용 하기 위한 요구 사항을 참조 하세요.

## <a name="compliance"></a>충족

팀에는 보존 정책, DLP (데이터 손실 방지), 채널에 대 한 eDiscovery 및 법률 보존, 채팅 및 파일, 감사 로그 검색, Microsoft와의 모바일 응용 프로그램 관리를 포함 하 여 규정 준수 영역에 도움이 되는 다양 한 정보가 있습니다. Intune. 위의 모든 항목에 대 한 정보를 제공 하 고 Office 365 보안 & 준수 센터로 이동 하 여 이러한 설정을 관리할 수 있습니다.

### <a name="retention-policies"></a>보존 정책

Microsoft 팀의 보존 정책을 사용 하면 조직에서 중요 한 데이터를 유지 하 고, 규정, 법률, 비즈니스 또는 기타 이유를 유지 하 고, 유지 하는 것과 관련이 없는 콘텐츠 및 통신을 제거할 수도 있습니다. 보존 정책을 사용 하 여 일정 기간 동안 데이터를 보관 한 다음 삭제할 수도 있습니다. 자세한 내용은 [Microsoft 팀 문서의 보존 정책](retention-policies.md) 항목을 참조 하세요.

### <a name="data-loss-prevention-dlp"></a>DLP (데이터 손실 방지)

Microsoft 팀의 DLP (데이터 손실 방지)는 o365의 대규모 DLP 스토리로, o365에서 중요 한 문서 및 데이터를 보호 하는 데 사용할 때 비즈니스 준비가 진행 됨을 중심으로 등장 합니다. 메시지 또는 문서의 중요 한 정보에 대해 염려 하는 경우 DLP 정책은 사용자가 중요 한 데이터를 잘못 된 사용자와 공유 하지 못하도록 할 수 있습니다.

팀에서 데이터 손실 방지에 대 한 자세한 내용은 [Microsoft 팀에 대 한 DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)를 검토 하세요. O36 DLP 관심사에 대 한 유용한 문서 [https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)입니다.

### <a name="ediscovery"></a>eDiscovery

전자적 검색 또는 eDiscovery는 법 슈트 또는 조사에서 생산 요청에 대 한 응답으로 ESI (전자적으로 저장 된 정보)를 식별, 수집 및 생성 하는 전자적 측면입니다. 접근 권한 값에는 사례 관리, 유지, 검색, 분석, 팀 데이터 내보내기 등이 포함 됩니다. 여기에는 채팅, 메시지 및 파일, 모임 및 통화 요약도 포함 됩니다. 팀 모임 및 통화의 경우, 모임 및 통화에 발생 한 이벤트에 대 한 요약이 만들어져서 eDiscovery에서 사용할 수 있게 됩니다.

보안 & 준수 센터에서 O365 eDiscovery 기능을 수행 하 고 팀 콘텐츠에 대 한 규정 준수 콘텐츠 검색을 실행 하는 방법에 대 한 자세한 내용은 아래 링크로 이동 하세요.

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[콘텐츠 검색](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

자세한 내용은 팀 관련 문서, [게스트 대 게스트 채팅의 eDiscovery](eDiscovery-investigation.md)를 참조 하세요.

고객은 [필요](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery)에 따라 현재 위치 eDiscovery 또는 [고급 eDiscovery]을 활용할 수 있습니다. 다음 표에서는 두 가지 사이의 차이점에 대해 간략하게 설명 합니다.

| |원본 위치 eDiscovery  |고급 eDiscovery  |
|---------|---------|---------|
|사례 관리     |축        |축         |
|액세스 제어  |축         |축         |
|콘텐츠 검색     |축         | 축        |
|보류 (s)   |축         | 축        |
|내보내기     |축         |축         |
|중복 검색     |-         |축         |
|기계 학습으로 관련성 검색    |-         |축         |
|비구조적 데이터 분석      |-         |축         |

### <a name="legal-hold"></a>법률 보류

소송 중에는 사용자에 연결 된 모든 데이터 (custodian) 또는 팀을 변경 되지 않은 상태로 유지 하 여 대/소문자에 대 한 증거로 사용할 수 있어야 할 수 있습니다. 이 작업은 사용자 (사용자 사서함) 또는 법률에 따라 팀 구성원을 배치 하 여 수행할 수 있습니다. 팀 법률을 유지 하기 위해 팀의 사서함을 다음 보류에 추가할 수 있습니다.

- 원본 위치 유지 (대상 쿼리 또는 필터링 된 콘텐츠를 통한 사서함 또는 사이트 모음의 하위 집합은 보류 중) 또는
- 소송 보존 (전체 사서함 또는 사이트 모음이 보류 상태에 배치 됨)

두 경우 모두 보류를 설정한 후 최종 사용자가 그룹 사서함에 있는 채널 메시지를 삭제 하거나 편집 하더라도 해당 콘텐츠의 변경 되지 않은 복사본이 eDiscovery 검색을 통해 유지 관리 되 고 사용할 수 있도록 보장 합니다. 법률 보존은 일반적으로 eDiscovery 사례의 컨텍스트 내에서 적용 됩니다.

Office 365 보안 & 준수 센터에서 보존 및 유지에 대 한 자세한 내용을 이해 하기 위해 [유지 정책 문서의 개요](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 를 참조 하세요. 법적 고 지에 대 한 팀 관련 정보에 대 한 자세한 내용은 [Microsoft 팀 사용자 또는 팀에](legal-hold.md) 게 자세한 내용에 대 한 법률 유지 문서를 준비 합니다.

### <a name="compliance-content-search"></a>콘텐츠 검색 준수

콘텐츠 검색을 사용 하 여 풍부한 필터링 기능을 통해 모든 팀 데이터를 검색할 수 있습니다. 결과 데이터를 규정 준수 및 소송 지원을 위해 특정 컨테이너에 내보낼 수 있습니다. 이 작업은 eDiscovery 사례와 관계 없이 수행할 수 있습니다. 이렇게 하면 규정 준수 관리자가 모든 사용자에 게 팀 데이터를 수집 하 고 추가 처리를 위해 검토 하 고 내보낼 수 있습니다. Office 365 보안 & 준수 센터에서 Microsoft 팀 및 기타 O365 콘텐츠에 대 한 준수 콘텐츠 검색을 수행 하는 방법에 대해 자세히 알아보려면 [O365 문서에서이 콘텐츠 검색](https://docs.microsoft.com/microsoft-365/compliance/content-search) 을 참조 하세요.

> [!TIP]
> 콘텐츠 검색을 사용 하면 필요한 경우 채팅 및 채널 메시지, 모임, 통화와 같은 Microsoft 팀의 콘텐츠만 필터링 할 수 있습니다.

콘텐츠 검색 구성에 대 한 추가 팀 관련 정보를 보려면 [Microsoft 팀의 콘텐츠 검색](content-search.md) 문서를 검토 하세요.

### <a name="auditing-and-reporting"></a>감사 및 보고

감사 로그 검색은 Office 365 보안 & 준수 센터에 있으며, 작업 부하를 설정 하 고 감사 이벤트를 보고할 수 있으며 무제한 감사 시간 표시 막대에서 관리를 사용 하 고 확인을 수행 하는 데 필요한 특정 또는 제네릭 이벤트 집합을 내보낼 수 있습니다. Office 365 보안 & 준수 센터 내의 모든 감사 로그 데이터에 대 한 알림을 설정 하 고 추가 분석을 위해이 데이터를 필터링 하 고 내보낼 수 있습니다. O365에 대 한 감사 로그를 수행 하는 방법에 대해 자세히 알아보려면 [감사 로그 검색](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 문서를 참조 하세요. Office 365 보안 & 준수 센터에서 Microsoft 팀 이벤트를 검색 하는 방법에 대해 자세히 알아보려면 [팀에서 감사를 사용 하도록 설정](audit-log-events.md) 하 여 검토할 수도 있습니다.

## <a name="information-protection-architecture"></a>정보 보호 아키텍처

다음 그림은 팀 파일 및 메시지에 대 한 Exchange 및 SharePoint 둘 다에 팀 데이터를 수집 하는 흐름을 나타냅니다.

![Exchange 및 SharePoint에 대 한 팀 데이터 워크플로 다이어그램](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

다음 그림은 Exchange로의 팀 모임 및 통화 데이터 수집 흐름을 나타냅니다.

![팀 모임 워크플로 및 Exchange로 데이터 호출에 대 한 다이어그램](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 팀 콘텐츠를 검색 하는 데 최대 24 시간이 걸릴 수 있습니다.

## <a name="licensing"></a>라이선싱

정보 보호 기능을 사용 하는 경우 Office 365 구독 및 관련 독립 실행형 라이선스에 따라 사용할 수 있는 기능 집합이 결정 됩니다.

보안 및 규정 준수에 대 한 기능을 구현 하는 데 필요한 라이선스를 확인 하는 방법에 대 한 자세한 내용은 [Office 365 라이선스](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 를 참조 하세요.

> [!NOTE]
> 보안 & 준수 센터에서 콘텐츠 검색 및 eDiscovery 기능을 사용 하도록 설정할 필요는 없습니다.

## <a name="location-of-data-in-teams"></a>Teams의 데이터 위치

팀의 데이터는 Office 365 테 넌 트와 연결 된 지리적 영역에 위치 합니다. 현재 지원 되는 영역을 확인 하려면 [Microsoft 팀에서 데이터의 위치](location-of-data-in-teams.md) 를 검토 하세요.

테 넌 트에 대 한 데이터가 들어 있는 영역을 확인 해야 하는 경우 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home) > **설정** > **조직 프로필로**이동 합니다. 아래로 스크롤하여 **데이터 위치로**이동 합니다.

![관리 센터의 팀을 비롯 한 데이터 위치 표 스크린샷](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>준수 표준

팀은 계층 D 규격입니다. 여기에는 ISO 27001, ISO 27018, SSAE16 SOC 1, SOC 2, HIPAA 및 EU 모델 절 (EUMC)이 포함 됩니다. Microsoft 규정 준수 프레임 워크 내에서 Microsoft는 Office 365 응용 프로그램 및 서비스를 네 가지 범주로 분류 합니다. 각 범주는 해당 범주에 나열 되는 Office 365 서비스 또는 관련 Microsoft 서비스에 대해 충족 해야 하는 특정 준수 약정에 의해 정의 됩니다.

규정 준수 범주에서 업계 선두적인 규정 준수 약정을 갖는 서비스는 기본적으로 사용 하도록 설정 되어 있습니다. 범주 A 및 B의 서비스는 전체 조직에 대해 이러한 서비스를 설정 하거나 해제 하는 컨트롤과 함께 사용 됩니다. 자세한 내용은 [업계 표준 및 규정 준수 프레임 워크](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf)에 나와 있습니다. 또한 팀은 클라우드 보안 동맹 준수를 지원 합니다.

## <a name="related-topics"></a>관련 주제

[M365 보안](https://docs.microsoft.com/microsoft-365/security/)
[M365 준수](https://docs.microsoft.com/microsoft-365/compliance/)
