---
title: 보안 및 규정 준수 개요
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: 개인 정보 Microsoft Teams 암호화, 감사 및 보고 등을 포함한 보안 및 규정 준수 기능에 대한 개요입니다.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61a6cba9ff05e6ee088c96231e8eb947e5d56fed
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733167"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>보안 및 Microsoft Teams

> [!IMPORTANT]
> **COVID-19** 발발 중에 모든 사용자가 집에서 작업하는 동안 보안을 가장 잘 보장하는 방법에 대해 알아보시고 다음 문서를 읽어보아야 합니다.
>  - [보안 팀이 재택 근무를 지원하는 상위 12가지 작업](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [VPN 분할 터널링을 사용하여 원격 사용자를 위해 Microsoft 365 혹은 Office 365 연결 최적화](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 2020년 [4월](teams-security-guide.md) 2일 업데이트: Teams 가이드


Microsoft Teams 고급 보안 및 규정 준수 기능을 Microsoft 365 Office 365 엔터프라이즈급 클라우드를 통해 구축됩니다. 보안 로드맵을 Microsoft 365 Office 365 계획에 대한 자세한 내용은 [](/microsoft-365/security/office-365-security/security-roadmap) 보안 로드맵을 시작하는 것이 좋습니다. 규정 준수 또는 규정 준수에 대한 Microsoft 365 Office 365 자세한 내용은 보안 규정 준수 계획 [을 & 있습니다.](/microsoft-365/compliance/plan-for-security-and-compliance)


이 문서에서는 특정 보안 및 규정 Teams 대한 추가 정보를 제공합니다. 보안 및 규정 준수에 대한 Microsoft Mechanics 비디오를 놓치지 마세요.

- [Microsoft Teams 필수 요소: 보안](https://youtu.be/91lHNKVVvQ4) 및 규정 준수(12:42분)
- [Microsoft Teams 준수를](https://www.youtube.com/watch?v=Km4T4hMM__k) 위한 제어(10:54분)

> [!IMPORTANT]
> 고객이 데이터를 Microsoft 365 Office 365 소유하고 제어합니다. Microsoft는 구독한 서비스를 제공하는 것 이외에는 데이터를 사용하지 않습니다. 서비스 공급자는 광고 또는 서비스 관련이 없는 목적으로 전자 메일, 문서 또는 팀을 검색하지 않습니다. Microsoft는 업로드된 콘텐츠에 액세스할 수 없습니다. 고객 OneDrive SharePoint Microsoft 365 테넌트 내에 고객 데이터가 유지됩니다. Microsoft Trust Center에서 신뢰 및 보안 관련 정보에 대한 자세한 [정보를 확인할 수 있습니다.](https://microsoft.com/trustcenter) Teams Microsoft Trust Center와 동일한 지침 및 원칙을 따르고 있습니다.

## <a name="security"></a>보안

Teams 팀 전체 및 조직 전체의 2단계 인증, Active Directory를 통한 Single Sign-On, 전송 중 및 미사용 데이터 암호화를 적용합니다. 파일은 암호화에 SharePoint 암호화를 통해 SharePoint 있습니다. 노트는 OneNote 암호화를 통해 OneNote 있습니다. OneNote 데이터는 팀 및 사이트 SharePoint 저장됩니다. 위키 탭은 메모를 찍는 데도 사용할 수 있으며 해당 콘텐츠는 팀 사이트 내에서도 SharePoint 있습니다.

인증 [및](identify-models-authentication.md) 인증에 대한 자세한 인사이트를 Teams [](sign-in-teams.md) ID 모델 및 인증을 읽고 최신 인증이 작동하는 방식은 특히 최신 인증에 도움이 됩니다.

Teams, SharePoint, OneNote, Exchange 등과 함께 작동하기 때문에 모든 Microsoft 365 Office 365 관리해야 합니다. 자세한 내용은 보안 강화를 위해 조직 또는 Microsoft 365 Office 365 [방법을 읽어보아야 합니다.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> 현재 개인 [채널은](private-channels.md) 제한된 보안 및 규정 준수 기능을 지원하고 있습니다. 개인 채널의 전체 보안 및 규정 준수 기능에 대한 지원은 곧 제공될 예정입니다.

### <a name="advanced-threat-protection-atp"></a>ATP(고급 위협 보호)

ATP(Advanced Threat Protection)는 콘텐츠 관리를 위한 Microsoft Teams 및 SharePoint OneDrive 애플리케이션과 Teams 사용할 수 있습니다. ATP를 사용하면 이러한 애플리케이션의 콘텐츠가 본질적으로 악의적인지 판단하고 사용자 액세스에서 이 콘텐츠를 차단할 수 있습니다.

영향을 받는 콘텐츠가 검색 후 관리되는 방식은 선택한 설정에 Microsoft 365 Office 365. [ATP를](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) 구성할 때 모든 애플리케이션을 고려하는 것이 좋습니다. 추가 읽기를 위해 atP for SharePoint, OneDrive 및 Microsoft Teams 시작하는 방법에 대한 자세한 정보가 있습니다.

### <a name="safe-links"></a>금고 링크

현재 ATP(고급 위협 보호 Microsoft Teams) 안전 링크는 현재는 탭(TAP)을 [](/microsoft-365/security/office-365-security/atp-safe-links-for-teams) 통해 공개 미리 보기로 제공되어 있으며, 일반 공급에 대한 릴리스 날짜가 설정되지 않은 경우 해당 시간이 도착하면 이 문서가 업데이트됩니다. 한편 링크 또는 링크에 대한 Microsoft 365 Office 365 금고 자세한 내용은 ATP 금고 [를 참조하세요.](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) ATP 금고 링크는 [ATP 계획 1 및 ATP 계획 2에서 모두 사용할 수 있습니다.](/microsoft-365/security/office-365-security/office-365-atp)

### <a name="safe-attachments"></a>금고 첨부 파일

금고 첨부 파일은 악의적인 첨부 파일을 확인하고 검색하여 사용자 보안을 강화하도록 설계된 기능입니다. 전역 또는 보안 관리자는 [](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies) 이러한 의심되는 악의적인 첨부 파일을 처리하기 위한 정책을 만들어 사용자에게 보내고, 클릭하고, 실행하지 못하게 합니다. 금고 첨부 파일 보호는 SharePoint, OneDrive 및 Microsoft Teams 및 고급 위협 Microsoft 365 Office 365 보호 계획 1 및 [2에서](/microsoft-365/security/office-365-security/office-365-atp) 이 기능을 사용할 수 있습니다. 첨부 파일 금고 및 [Microsoft Defender의](/microsoft-365/security/office-365-security/atp-safe-attachments)첨부 파일에서 조직을 보호하는 금고 방법에 대해 자세히 Office 365.

### <a name="secure-score"></a>보안 점수

Microsoft Secure Score는 조직의 보안 자세를 측정하는 측정값으로, 더 높은 숫자는 더 많은 개선 작업을 나타내는 것입니다. 보안 센터 에서 Microsoft 365 [있습니다.](https://security.microsoft.com/securescore) 보안 점수 권장 사항을 따라 조직을 위협으로부터 보호할 수 있습니다. 조직은 보안 센터의 중앙 집중식 대시보드에서 Microsoft 365 ID, 앱 및 디바이스의 보안 Microsoft 365 모니터링하고 작업할 수 있습니다. Microsoft Teams 보안 점수에 대한 권장 사항이 있으며 관리자는 플랫폼에서 보안 입장을 모니터링하는 것이 권장됩니다.

보안 점수는 조직에 도움이 됩니다.
- 조직의 보안 상태의 현재 상태를 보고합니다.
- 검색 가능성, 가시성, 지침 및 제어를 제공하여 보안 자세를 개선합니다.
- 벤치마크와 비교하고 KPIS(주요 성능 지표)를 설정합니다.


### <a name="how-conditional-access-policies-work-for-teams"></a>조건부 액세스 정책이 사용자에 대한 Teams

Microsoft Teams 모임, 일정Exchange Online 채팅, 파일 공유와 같은 핵심 생산성 시나리오에 Exchange Online SharePoint 및 비즈니스용 Skype Online에 크게 의존합니다. 이러한 클라우드 앱에 대해 설정된 조건부 액세스 정책은 사용자가 모든 Microsoft Teams 로그인할 때 Microsoft Teams 적용됩니다.

Microsoft Teams 조건부 액세스 정책에서 클라우드 앱으로 Azure Active Directory 지원됩니다. 사용자가 로그인할 때 Microsoft Teams 클라우드 앱에 Microsoft Teams 조건부 액세스 정책이 적용됩니다. 그러나 다른 앱에 대한 올바른 정책이 없는 Exchange Online SharePoint 사용자는 해당 리소스에 직접 액세스할 수 있습니다. Azure Portal에서 조건부 액세스 정책 설정에 대한 자세한 내용은 빠른 시작 Azure Active Directory [참조하세요.](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams 및 Mac용 데스크톱 Windows 최신 인증을 지원합니다. 최신 인증은 플랫폼에서 클라이언트 애플리케이션을 Azure Active Directory ADAL(인증 라이브러리)Microsoft Office 로그인합니다.

Microsoft Teams 데스크톱 애플리케이션은 AppLocker를 지원합니다.  AppLocker 전제 조건에 대한 자세한 내용은 AppLocker를 사용하는 요구 [사항 을 참조하세요.](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>규정 준수

Teams, 채팅 및 첨부 파일에 대한 통신 준수, 보존 정책, DLP(데이터 손실 보호), eDiscovery 및 채널, 채팅 및 파일, 감사 로그 검색, 모바일 애플리케이션 관리 등 규정 준수 영역을 지원하기 위한 광범위한 Microsoft Intune. 아래 모든 항목에 대한 몇 가지 정보를 제공했습니다. 이러한 [](https://compliance.microsoft.com) 설정을 관리하기 위해 Microsoft 365 규정 준수 센터 있습니다.

### <a name="information-barriers"></a>정보 장벽

정보 장벽은 관리자들이 Teams(비즈니스가 필요하지 않은 경우 또는 이를 차단하는 규제 이유가 없는 경우)와 같은 작업을 수행하기 위해 관리자들이 직접 설정한 정책입니다. 또한 보기 및 eDiscovery와 관련된 정책을 설정할 수 있습니다(아래 설명). 이러한 정책은 1:1 채팅, 그룹 채팅 또는 팀 수준에서 사용자에게 영향을 줄 수 있습니다. 정보 장벽 기능은 공용 클라우드에서 사용할 수 있으며 2021년 1월부터 클라우드에 GCC 있습니다.

이 항목에 대한 자세한 내용은 의 정보 [장벽으로 Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>커뮤니케이션 규정 준수

Microsoft 365 통신 규정 준수를 사용하면 공격적인 언어, 중요한 정보 및 내부 및 규정 표준과 관련된 Microsoft Teams 통신을 검사하도록 구성할 수 있는 범위 내 정책에 사용자를 추가할 수 있습니다. 공용 및 개인 Teams 채널, 개별 채팅 및 첨부 파일 모두에서 채팅 통신 및 관련 첨부 파일을 검색하여 조직의 통신 위험을 최소화할 수 있습니다. 부적절한 통신을 감지, 캡처 및 조치를 취할 수 있도록 정책을 구성하는 방법에 대한 자세한 내용은 Teams 에서 통신 [규정 준수를 Microsoft 365.](/microsoft-365/compliance/communication-compliance)

### <a name="retention-policies"></a>보존 정책

이 Microsoft Teams 보존 정책을 사용하면 조직에서 규정, 법률, 비즈니스 또는 기타 이유로 유지해야 하는 중요한 데이터를 보존하고 보존과 관련이 없는 콘텐츠 및 통신을 제거할 수 있습니다. 보존 정책을 사용하여 데이터를 한 기간 동안 보관한 다음 삭제할 수도 있습니다. 자세한 내용은 의 보존 [정책을 Microsoft Teams.](retention-policies.md)

## <a name="sensitivity-labels"></a>민감도 레이블

민감도 [레이블을](/microsoft-365/compliance/sensitivity-labels) 적용하여 팀 내에서 공동 작업하는 동안 생성된 중요한 조직 콘텐츠에 대한 액세스를 보호하고 규제합니다. 예를 들어 팀의 개인 정보(공개 또는 비공개)를 구성하고 게스트 액세스 및 외부 공유를 제어하고, 관리되지 않는 장치에서 액세스를 관리하는 레이블을 적용합니다. 자세한 내용은 의 [민감도 레이블을 Microsoft Teams.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>DLP(데이터 손실 방지)

DLP(데이터 손실 방지)는 Microsoft Teams 데이터 보호와 관련한 비즈니스 Microsoft 365 Office 365 더 큰 DLP 스토리뿐만 아니라 중요한 문서 및 데이터 보호에 대한 비즈니스 준비를 중심으로 합니다. 메시지 또는 문서의 중요한 정보에 대한 우려가 있는지 여부에 따라 DLP 정책은 사용자가 이 중요한 데이터를 잘못된 사용자와 공유하지 않도록 할 수 있습니다.

데이터 손실 방지에 대한 자세한 Teams 에 대한 [DLP를](/microsoft-365/compliance/dlp-microsoft-teams)Microsoft Teams. O365 DLP 문제의 좋은 문서는 데이터 손실 방지 [개요입니다.](/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

전자 검색 또는 eDiscovery는 법 소송 또는 조사에서 생산 요청에 대응하여 ESI(전자적으로 저장된 정보)를 식별, 수집 및 생산하는 전자적 측면입니다. 기능에는 사례 관리, 보존, 검색, 분석 및 데이터 내보내기 Teams 있습니다. 여기에는 채팅, 메시징 및 파일, 모임 및 통화 요약이 포함됩니다. Teams 및 통화의 경우 모임 및 통화에서 발생한 이벤트의 요약이 eDiscovery에서 만들어지며 사용할 수 있습니다.

보안 센터 및 규정 준수 Microsoft 365 Office 365 eDiscovery를 실행하고, 규정 준수 콘텐츠 검색을 Teams 방법에 대한 자세한 내용은 아래 링크로 이동하세요.

 - [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

 - [콘텐츠 검색](/microsoft-365/compliance/search-for-content)

자세한 내용은 Teams 게스트 [채팅의 eDiscovery에](eDiscovery-investigation.md)대한 특정 문서가 있습니다.

고객은 요구 사항에 따라 eDiscovery 또는 Advanced eDiscovery [사용할](/microsoft-365/compliance/office-365-advanced-ediscovery) 수 있습니다. 다음 표에서는 두 가지 차이점을 간략하게 간략하게 설명합니다.

|&nbsp; |eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|사례 관리     |X        |X         |
|액세스 제어  |X         |X         |
|콘텐츠 검색     |X         | X        |
|Hold(s)   |X         | X        |
|내보내기     |X         |X         |
|중복 검색     |-         |X         |
|검색과의 Machine Learning    |-         |X         |
|구조화되지 않은 데이터 분석      |-         |X         |

### <a name="legal-hold"></a>법적 보류

소송 중에는 사용자(custodian) 또는 팀과 연결된 모든 데이터를 변경 불가능으로 보존해야 할 수 있으므로 사건에 대한 증거로 사용할 수 있습니다. 사용자(사용자 사서함) 또는 팀을 법적 보류에 배치하여 이 작업을 할 수 있습니다. 팀 법적 보류의 경우 팀의 사서함을 다음 보류에 넣을 수 있습니다.

- In-Place 보류(대상 쿼리 또는 필터링된 콘텐츠를 통해 사서함 또는 사이트 모음의 하위 집합이 보류 중) 또는
- 소송 보류(전체 사서함 또는 사이트 모음이 보류 중)

두 경우 모두 보류가 설정되면 최종 사용자가 그룹 사서함에 있는 채널 메시지를 삭제하거나 편집하는 경우에도 해당 콘텐츠의 변경 불가능한 복사본이 유지 관리되고 eDiscovery 검색을 통해 사용할 수 있도록 합니다. 법적 보류는 일반적으로 eDiscovery 사례의 컨텍스트 내에서 적용됩니다.

보존 [및](/microsoft-365/compliance/retention-policies) 보존에 대한 자세한 내용은 보존 정책 개요를 Microsoft 365 규정 준수 센터. 법적 보류에 대한 Teams 자세한 내용은 사용자가 [](legal-hold.md) 자세히 Microsoft Teams 사용자 또는 팀을 법적 보류에 두는 것이 있습니다.

### <a name="compliance-content-search"></a>규정 준수 콘텐츠 검색

콘텐츠 검색은 다양한 필터링 기능을 통해 모든 Teams 검색하는 데 사용할 수 있습니다. 결과 데이터는 규정 준수 및 소송 지원을 위해 특정 컨테이너로 내보낼 수 있습니다. 이 경우 eDiscovery 사례를 사용하거나 없이 수행될 수 있습니다. 이를 통해 규정 준수 관리자는 모든 Teams 데이터를 수집하고, 추가 처리를 위해 데이터를 검토하고 내보낼 수 있습니다. 콘텐츠 검색을 참조하여 웹 사이트 및 기타 Microsoft Teams 규정 준수 콘텐츠 검색을 Microsoft 365 Office 365 자세히 Microsoft 365 규정 준수 센터. [](/microsoft-365/compliance/content-search)

> [!TIP]
> 콘텐츠 검색을 사용하여 필요한 Microsoft Teams 채팅 및 채널 메시지, 모임 및 통화와 같은 콘텐츠만 필터링할 수 있습니다.

콘텐츠 검색 구성에 대한 자세한 Teams 의 콘텐츠 검색을 [Microsoft Teams.](content-search.md)

### <a name="auditing-and-reporting"></a>감사 및 보고

감사 로그 검색은 Microsoft 365 규정 준수 센터 관리자를 위해 워크로드 특정 또는 일반 이벤트 집합을 내보내고 무제한 감사 타임라인에서 조사할 수 있도록 하여 감사 이벤트에 대한 보고뿐만 아니라 경고를 설정할 수 있는 기능을 제공합니다. 이 데이터 내의 모든 감사 로그 데이터에 대한 경고를 Microsoft 365 규정 준수 센터 추가 분석을 위해 이 데이터를 필터링하고 내보낼 수 있습니다. 감사 [로그](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 검색을 수행하는 방법에 대한 자세한 내용은 감사 로그 검색을 Microsoft 365 Office 365. 이 이벤트의 Microsoft Teams 검색에 Microsoft 365 규정 준수 센터 자세한 내용은 검토할 Teams 설정되어 있습니다. [](audit-log-events.md)

## <a name="customer-key"></a>고객 키

Microsoft 365 콘텐츠에 대한 서비스 암호화 위에 추가 암호화 계층을 제공합니다. 제공한 키를 사용하여 고객 Microsoft Teams 키는 여러 가지 유형의 데이터를 암호화합니다. 애플리케이션 수준에서 고객 키를 사용하여 고객 키는 Teams 온라인에 SharePoint 암호화합니다. 자세한 내용은 고객 키 [를 사용하여 서비스 암호화를 참조하세요.](/microsoft-365/compliance/customer-key-overview) 

테넌트 수준에서 고객 키를 사용하여 고객 키는 다음을 암호화합니다.
- Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)
- Teams 메시지(이미지, 코드, 비디오 및 위키 이미지)
- Teams 저장소에 저장된 통화 및 모임 Teams 저장
- Teams 채팅 알림
- Teams 채팅 제안을 Cortana
- Teams 상태 메시지에 대한 자세한 내용은 [](/microsoft-365/compliance/customer-key-tenant-level) 테넌트 수준에서 Microsoft 365 고객 키 개요를 참조하고 공개 미리 보기에서 Microsoft Teams 고객 키 지원을 다 Microsoft Teams 블로그를 [참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) 테넌트 Microsoft Information Protection 고객 키가 포함된 릴리스에 대한 자세한 내용은 중요한 데이터를 알고 보호할 Microsoft Information Protection 새 기능 발표를 [참조하십시오.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>개인 정보

Microsoft에서는 데이터를 보호하는 것이 최우선 순위입니다. 개인 정보 취급 방침에 대해 알아보고자 하는 경우 다음을 읽어보아야 합니다.  

- [Microsoft의 개인 정보 보호](https://www.microsoft.com/trust-center/privacy)
- [개인 정보 보호 및 보안에 대한 Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [IT 전문가의 경우: 개인 정보 보호 및 보안 Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>정보 보호 아키텍처

다음 그림은 파일 및 메시지에 대한 Teams 데이터 Exchange SharePoint Teams 나타냅니다.

> [!div class="mx-imgBorder"]
> ![데이터를 Teams 워크플로 다이어그램을 Exchange SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

다음 그림은 모임 및 Teams 데이터 수집 흐름을 Exchange.

> [!div class="mx-imgBorder"]
> ![모임 및 Teams 호출하는 워크플로의 다이어그램을 Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 콘텐츠를 검색하는 데 최대 24시간이 Teams 수 있습니다.

## <a name="licensing"></a>라이선싱

정보 보호 기능에 관해서는 Microsoft 365 구독, Office 365 및 연결된 독립 실행형 라이선스가 사용 가능한 기능 집합을 결정하게 됩니다.

보안 및 규정 준수를 위한 기능을 구현해야 하는 라이선스를 결정하는 데 대한 자세한 내용은 보안 및 규정 준수 기능에 대한 라이선스 요구 사항을 검토하세요. [](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

> [!NOTE]
> 콘텐츠 검색 및 eDiscovery는 보안 준수 센터에서 작동하도록 & 필요가 없습니다.

## <a name="location-of-data-in-teams"></a>Teams의 데이터 위치

Teams의 데이터는 Microsoft 365 또는 Office 365 조직과 연결된 지리적 영역에 위치합니다. 현재 지원되는 지역을 보시고 에서 데이터 [위치를](location-of-data-in-teams.md)Microsoft Teams.

테넌트에 대한 데이터를 저장하는 지역을 확인해야 [](https://portal.office.com/adminportal/home)하는 경우 조직 Microsoft 365 관리 센터 설정  >    >  **로 이동하세요.** **데이터 위치** 로 스크롤 합니다.

> [!div class="mx-imgBorder"]
> ![관리 센터의 Teams 데이터 위치 테이블의 스크린샷입니다.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>규정 준수 표준

Teams 표준은 [ISO 27001,](/microsoft-365/compliance/offering-iso-27001)ISO [27018,](/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 및 SOC 2,](/microsoft-365/compliance/offering-soc) [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)및 EU 모델 [절(EUMC)](/microsoft-365/compliance/offering-eu-model-clauses)을 사용 합니다. Microsoft 규정 준수 프레임워크 내에서 Microsoft는 애플리케이션 및 Microsoft 365 Office 365 범주로 분류합니다. 각 범주는 해당 범주에 나열되어야 하는 특정 Microsoft 365 Office 365 서비스 또는 관련 Microsoft 서비스에 대해 충족해야 하는 특정 규정 준수 약정에 의해 정의됩니다.

자세한 내용은 데이터 보호 리소스 [에서 찾을 수 있습니다.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams 클라우드 보안 얼라이언스 규정 준수도 지원합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 보안](/microsoft-365/security/)

[Microsoft 365 규정 준수](/microsoft-365/compliance/)

[Microsoft 규정 준수 제품](/microsoft-365/compliance/offering-home)
