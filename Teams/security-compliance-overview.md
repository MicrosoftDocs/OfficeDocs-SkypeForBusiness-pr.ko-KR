---
title: 보안 및 규정 준수 개요
author: MSFTTracyP
ms.author: tracyp
manager: laurawi
ms.date: 04/12/2022
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: 개인 정보 및 암호화, 감사 및 보고 등을 포함한 Microsoft Teams 보안 및 규정 준수 기능에 대한 개요입니다.
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
ms.openlocfilehash: c4e31e59992d24aeac190c4f1ffb40d8c3dfef78
ms.sourcegitcommit: 2871c05e00458a0cc76d919ff822b0b354bd1f72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66810070"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams의 보안 및 규정 준수

> [!IMPORTANT]
> **COVID-19 발생 시 모든 사람이 집에서 작업하는 동안 보안을** 가장 잘 보장하는 방법을 알아보려면 다음 문서를 읽어보세요.
>  - [보안 팀이 재택 근무를 지원하는 상위 12가지 작업](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [VPN 분할 터널링을 사용하여 원격 사용자를 위해 Microsoft 365 혹은 Office 365 연결 최적화](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 업데이트된 2020년 4월 2일: [Teams 보안 가이드](teams-security-guide.md)


Microsoft Teams는 Microsoft 365 및 Office 365 대규모 엔터프라이즈급 클라우드를 기반으로 구축되어 고객이 기대하는 고급 보안 및 규정 준수 기능을 제공합니다. Microsoft 365 또는 Office 365 보안 계획에 대한 자세한 내용은 [보안 로드맵](/microsoft-365/security/office-365-security/security-roadmap)을 시작하는 것이 좋습니다. Microsoft 365 또는 Office 365 규정 준수 계획에 대한 자세한 내용은 [보안 & 규정 준수 계획](/microsoft-365/compliance/plan-for-security-and-compliance)부터 시작할 수 있습니다.


이 문서에서는 Teams 관련 보안 및 규정 준수에 대한 추가 정보를 제공합니다. 보안 및 규정 준수에 대한 Microsoft Mechanics 비디오를 놓치지 마세요.

- [IT용 Microsoft Teams Essentials: 보안 및 규정 준수](https://youtu.be/91lHNKVVvQ4)(12:42분)
- [보안 및 규정 준수를 위한 Microsoft Teams 컨트롤](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54분)

> [!IMPORTANT]
> Microsoft 365 또는 Office 365 고객은 데이터를 소유하고 제어합니다. Microsoft는 사용자가 구독한 서비스를 제공하는 것 외에는 데이터를 사용하지 않습니다. 서비스 공급자는 메일, 문서 또는 팀을 검색하여 광고하거나 서비스와 관련이 없는 용도로 검색하지 않습니다. Microsoft는 업로드된 콘텐츠에 액세스할 수 없습니다. Microsoft 365의 OneDrive 및 SharePoint와 마찬가지로 고객 데이터는 테넌트 내에 유지됩니다. [Microsoft 보안 센터에서](https://microsoft.com/trustcenter) 신뢰 및 보안 관련 정보에 대해 자세히 확인할 수 있습니다. Teams는 Microsoft 보안 센터와 동일한 지침 및 원칙을 따릅니다.

## <a name="security"></a>보안

Teams는 팀 전체 및 조직 전체의 2단계 인증, Active Directory를 통한 Single Sign-On 및 전송 중 및 미사용 데이터 암호화를 적용합니다. 파일은 SharePoint에 저장되며 SharePoint 암호화를 통해 지원됩니다. 노트는 OneNote에 저장되며 OneNote 암호화를 통해 지원됩니다. OneNote 데이터는 팀 SharePoint 사이트에 저장됩니다. Wiki 탭은 메모 작성에도 사용할 수 있으며 해당 콘텐츠는 팀 SharePoint 사이트 내에도 저장됩니다.

인증 및 Teams에 대한 자세한 인사이트를 보려면 [ID 모델 및 인증](identify-models-authentication.md) 을 읽고, [최신 인증이 작동하는 방식은](sign-in-teams.md) 특히 최신 인증에 도움이 됩니다.

Teams는 SharePoint, OneNote, Exchange 등과 협력하여 작동하므로 Microsoft 365 또는 Office 365 전체에서 보안을 편리하게 관리할 수 있어야 합니다. 자세한 내용은 [보안 강화를 위해 Microsoft 365 또는 Office 365 조직을 구성하는 방법을](/office365/securitycompliance/tenant-wide-setup-for-increased-security) 읽어보세요.

> [!NOTE]
> 현재 [개인 채널은](private-channels.md) 제한된 보안 및 규정 준수 기능을 지원합니다. 프라이빗 채널의 전체 보안 및 규정 준수 기능에 대한 지원이 곧 제공될 예정입니다.

### <a name="microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender

Office 365용 Microsoft Defender 콘텐츠 관리를 위해 Teams와 통합되는 애플리케이션인 SharePoint 및 OneDrive와 함께 Microsoft Teams에서 사용할 수 있습니다. Office 365용 Defender 사용하면 이러한 애플리케이션의 콘텐츠가 본질적으로 악의적인지 확인하고 이 콘텐츠를 사용자 액세스에서 차단할 수 있습니다.

검색 후 영향을 받는 콘텐츠를 관리하는 방법은 Microsoft 365 또는 Office 365 선택한 설정에 달려 있습니다. Office 365용 Defender 구성과 관련하여 모든 애플리케이션을 고려하는 것이 좋으며, 추가 읽기를 위해 [안전한 링크의 작동 방식에 대한 개요와 이를 설정하는 단계가 여기에 있습니다](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide).

### <a name="safe-links-in-microsoft-teams"></a>Microsoft Teams의 안전한 링크

Office 365용 Defender 안전한 링크는 Microsoft Teams에서 사용할 수 있습니다. 안전한 링크의 내용과 이 기능으로 수행할 작업에 대한 자세한 내용을 보려면 [Teams에 대한 안전한 링크 설정을](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) 읽어보세요. 안전 링크는 [Office 365용 Defender 플랜 1과 플랜 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide) 모두에서 사용할 수 있습니다.

### <a name="safe-attachments"></a>안전한 첨부 파일

안전한 첨부 파일은 악성 첨부 파일을 확인하고 검색하여 사용자 보안을 강화하도록 설계된 기능입니다. 전역 또는 보안 관리자는 [이 기능을 켜](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams?view=o365-worldwide) 고 이러한 의심스러운 악성 첨부 파일을 처리하여 사용자에게 전송, 클릭 및 조치를 취하지 못하도록 [하는 정책을 만듭니](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) 다.

안전한 첨부 파일 보호는 SharePoint, OneDrive 및 Microsoft Teams, Microsoft 365 또는 [Office 365용 Microsoft Defender 플랜 1 및 플랜 2의 Office 365](/microsoft-365/security/office-365-security/overview?view=o365-worldwide) 사용할 수 있습니다. 안전한 첨부 파일에 대해 자세히 알아보고 [이 문서에서](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) 조직을 보호하는 방법을 알아보세요.

### <a name="secure-score"></a>보안 점수

Microsoft Secure Score는 조직의 보안 상태를 측정하는 것으로, 더 많은 개선 작업이 수행되었음을 나타내는 숫자가 더 높습니다. [Microsoft 365 보안 센터](https://security.microsoft.com/securescore) 찾을 수 있습니다. 보안 점수 권장 사항에 따라 위협으로부터 조직을 보호할 수 있습니다. Microsoft 365 보안 센터 중앙 집중식 대시보드에서 조직은 Microsoft 365 ID, 앱 및 디바이스의 보안을 모니터링하고 작업할 수 있습니다. 이제 Microsoft Teams에는 보안 점수에 대한 권장 사항이 있으며 관리자는 플랫폼에서 보안 상태를 모니터링하는 것이 좋습니다.

보안 점수는 조직에 도움이 됩니다.
- 조직의 보안 상태의 현재 상태를 보고합니다.
- 검색 가능성, 가시성, 지침 및 제어를 제공하여 보안 태세를 개선합니다.
- 벤치마크와 비교하고 KPI(핵심 성과 지표)를 설정합니다.

### <a name="how-conditional-access-policies-work-for-teams"></a>Teams에서 조건부 액세스 정책이 작동하는 방식

Microsoft Teams는 모임, 일정, interop 채팅 및 파일 공유와 같은 핵심 생산성 시나리오를 위해 Exchange Online, SharePoint 및 비즈니스용 Skype Online에 크게 의존합니다. 이러한 클라우드 앱에 대해 설정된 조건부 액세스 정책은 사용자가 모든 클라이언트에서 Microsoft Teams에 직접 로그인할 때 Microsoft Teams에 적용됩니다.

Microsoft Teams는 Azure Active Directory 조건부 액세스 정책에서 클라우드 앱으로 별도로 지원됩니다. Microsoft Teams 클라우드 앱에 대해 설정된 조건부 액세스 정책은 사용자가 로그인할 때 Microsoft Teams에 적용됩니다. 그러나 Exchange Online 및 SharePoint와 같은 다른 앱에 대한 올바른 정책이 없으면 사용자는 해당 리소스에 직접 액세스할 수 있습니다. Azure Portal 조건부 액세스 정책을 설정하는 방법에 대한 자세한 내용은 [Azure Active Directory 빠른 시작을 참조하세요](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Windows 및 Mac용 Microsoft Teams 데스크톱 클라이언트는 최신 인증을 지원합니다. 최신 인증은 ADAL(Azure Active Directory 인증 라이브러리)을 기반으로 하는 로그인을 플랫폼 간 Microsoft Office 클라이언트 애플리케이션에 제공합니다.

Microsoft Teams 데스크톱 애플리케이션은 AppLocker를 지원합니다.  AppLocker 필수 구성 요소에 대한 자세한 내용은 다음을 참조하세요. [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)를 사용하기 위한 요구 사항입니다.

## <a name="compliance"></a>규정 준수

Teams에는 채널, 채팅 및 첨부 파일에 대한 커뮤니케이션 규정 준수, 보존 정책, DLP(데이터 손실 방지), eDiscovery 및 채널, 채팅 및 파일, 감사 로그 검색, Microsoft Intune 모바일 애플리케이션 관리를 비롯한 규정 준수 영역에 도움이 되는 다양한 정보가 있습니다. 아래의 모든 항목에 대한 몇 가지 정보를 제공했으며 [Microsoft Purview 규정 준수 포털](https://compliance.microsoft.com) 이동하여 이러한 설정을 관리할 수 있습니다.

### <a name="information-barriers"></a>정보 장벽

Microsoft Purview 정보 장벽은 팀 관리자가 사용자 또는 그룹이 서로 통신하지 못하도록 하는 것과 같은 작업을 수행하기 위해 마련된 정책입니다(비즈니스에서 통신할 필요가 없거나 이를 차단하는 규제 이유가 없는 경우) 조회 및 eDiscovery와 관련된 정책을 설정할 수도 있습니다(아래 설명). 이러한 정책은 1:1 채팅, 그룹 채팅 또는 팀 수준에서 사용자에게 영향을 미칠 수 있습니다. Information Barrier 기능은 퍼블릭 클라우드에서 사용할 수 있으며 2021년 1월부터 GCC 클라우드에 출시되었습니다.

이 항목에 대한 자세한 내용은 [Microsoft Teams의 정보 장벽으로](information-barriers-in-teams.md) 이동하세요.

### <a name="communication-compliance"></a>커뮤니케이션 규정 준수

Microsoft Purview 커뮤니케이션 규정 준수 사용하여 Microsoft Teams 통신에서 공격적인 언어, 중요한 정보 및 내부 및 규정 표준과 관련된 정보를 검사하도록 구성할 수 있는 범위 내 정책에 사용자를 추가할 수 있습니다. 공용 및 개인 Teams 채널, 개별 채팅 및 첨부 파일 모두에서 채팅 통신 및 관련 첨부 파일을 검사하여 조직의 통신 위험을 최소화할 수 있습니다. 부적절한 Teams 통신을 감지, 캡처 및 조치를 취하는 데 도움이 되는 정책을 구성하는 방법에 대한 자세한 내용은 [커뮤니케이션 규정 준수에 대한 자세한 내용을 참조하세요](/microsoft-365/compliance/communication-compliance).

### <a name="sensitivity-labels"></a>민감도 레이블

[민감도 레이블을](/microsoft-365/compliance/sensitivity-labels) 적용하여 팀 내에서 공동 작업 중에 만든 중요한 조직 콘텐츠에 대한 액세스를 보호하고 규제합니다. 예를 들어 팀의 개인 정보(공개 또는 비공개)를 구성하고, 게스트 액세스 및 외부 공유를 제어하고, 관리되지 않는 디바이스에서 액세스를 관리하는 레이블을 적용합니다. 자세한 내용은 [Microsoft Teams의 민감도 레이블을 검토하세요](sensitivity-labels.md).

### <a name="microsoft-purview-data-loss-prevention-dlp"></a>Microsoft Purview 데이터 손실 방지(DLP)

Microsoft Teams의 DLP(데이터 손실 방지)와 Microsoft Purview에 대한 더 큰 DLP 스토리는 중요한 문서 및 데이터를 보호하는 데 있어 비즈니스 준비 상태를 중심으로 진행됩니다. 메시지 또는 문서의 중요한 정보에 대한 우려가 있는지 여부에 관계없이 DLP 정책은 사용자가 이 중요한 데이터를 잘못된 사용자와 공유하지 않도록 할 수 있습니다.

Teams의 데이터 손실 방지에 대한 자세한 내용은 [Microsoft Teams용 DLP를](/microsoft-365/compliance/dlp-microsoft-teams) 검토하세요. DLP 문제에 대한 좋은 문서는 [데이터 손실 방지에 대해 알아보기](/microsoft-365/compliance/dlp-learn-about-dlp)입니다.

### <a name="customer-key"></a>고객 키

Microsoft 365는 콘텐츠에 대한 서비스 암호화를 기반으로 추가 암호화 계층을 제공합니다. 사용자가 제공하는 키를 사용하여 고객 키는 Microsoft Teams에서 여러 유형의 데이터를 암호화합니다. 고객 키는 애플리케이션 수준에서 고객 키를 사용하여 SharePoint Online에 저장된 Teams 파일을 암호화합니다. 자세한 내용은 [Microsoft Purview 고객 키를 사용한 서비스 암호화](/microsoft-365/compliance/customer-key-overview)를 참조하세요.

테넌트 수준에서 고객 키를 사용하여 고객 키는 다음을 암호화합니다.
- Teams 채팅 메시지(1:1 채팅, 그룹 채팅, 모임 채팅 및 채널 대화)
- Teams 미디어 메시지(이미지, 코드 조각, 비디오 및 위키 이미지)
- Teams 스토리지에 저장된 Teams 통화 및 모임 녹음/녹화
- Teams 채팅 알림
- Cortana의 Teams 채팅 제안
- Teams 상태 메시지

자세한 내용은 [테넌트 수준의 고객 키 개요를](/microsoft-365/compliance/customer-key-tenant-level) 참조하고 [현재 공개 미리 보기에서 Microsoft Teams에 대한 고객 키 지원을 다루는 Microsoft Teams 블로그를](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) 참조하세요. 테넌트 수준에서 고객 키가 포함된 Microsoft Purview Information Protection 릴리스에 대한 자세한 내용은 [중요한 데이터를 알고 보호할 수 있는 새로운 Microsoft Purview Information Protection 기능 발표를 참조하세요](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692).

### <a name="retention-policies"></a>보존 정책

Microsoft Teams의 보존 정책을 사용하면 조직에서 규정, 법률, 비즈니스 또는 기타 이유로 유지하는 데 중요한 데이터를 보존하고 보존과 관련이 없는 콘텐츠 및 통신을 제거할 수 있습니다. 보존 정책을 사용하여 일정 기간 동안 데이터를 보관한 다음 삭제할 수도 있습니다. 자세한 내용은 [Microsoft Teams의 보존 정책을 검토하세요](retention-policies.md).

### <a name="ediscovery"></a>eDiscovery

전자 검색 또는 eDiscovery는 법률 소송 또는 조사에서 생산 요청에 대한 응답으로 ESI(전자 저장 정보)를 식별, 수집 및 생성하는 전자적 측면입니다. 기능에는 Teams 데이터의 사례 관리, 보존, 검색, 분석 및 내보내기가 포함됩니다. 여기에는 채팅, 메시징 및 파일, 모임 및 통화 요약이 포함됩니다. Teams 모임 및 통화의 경우 모임 및 통화에서 발생한 이벤트에 대한 요약이 만들어지고 eDiscovery에서 사용할 수 있습니다.

Microsoft Purview 규정 준수 포털 eDiscovery 도구를 사용하여 Teams 콘텐츠를 검색하는 방법에 대한 자세한 내용은 아래 링크로 이동하세요.

- [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

- [콘텐츠 검색](/microsoft-365/compliance/search-for-content)

Microsoft Teams의 콘텐츠에 대한 [eDiscovery 조사를 수행하는](eDiscovery-investigation.md) 방법에 대한 자세한 내용은 Teams 관련 문서를 제공합니다.

고객은 요구 사항에 따라 [eDiscovery 또는 eDiscovery(프리미엄)](/microsoft-365/compliance/office-365-advanced-ediscovery) 를 활용할 수 있습니다. 다음 표에서는 두 가지 차이점을 간략하게 설명합니다.

|&nbsp; |eDiscovery  |eDiscovery(프리미엄)  |
|---------|---------|---------|
|사례 관리     |X        |X         |
|Access Control  |X         |X         |
|콘텐츠 검색     |X         | X        |
|Hold(들)   |X         | X        |
|내보내기     |X         |X         |
|중복 검색     |-         |X         |
|Machine Learning을 사용하여 관련성 검색    |-         |X         |
|구조화되지 않은 데이터 분석      |-         |X         |

### <a name="legal-hold"></a>법적 보존

소송 중에는 사용자(보유자) 또는 팀과 연결된 모든 데이터를 변경할 수 없는 상태로 보존하여 사례에 대한 증거로 사용할 수 있어야 할 수 있습니다. 사용자(사용자 사서함) 또는 팀을 법적 보류 상태로 설정하여 이 작업을 수행할 수 있습니다. 팀 법적 보존의 경우 팀의 사서함을 다음 보류에 배치할 수 있습니다.

- In-Place 보류(대상 쿼리 또는 필터링된 콘텐츠를 통한 사서함 또는 사이트 모음의 하위 집합이 보류됨) 또는
- 소송 보존(전체 사서함 또는 사이트 모음이 보류됨).

두 경우 모두 보류가 설정되면 최종 사용자가 그룹 사서함에 있는 채널 메시지를 삭제하거나 편집하더라도 해당 콘텐츠의 변경할 수 없는 복사본이 유지 관리되고 eDiscovery 검색을 통해 사용할 수 있습니다. 법적 보존은 일반적으로 eDiscovery 사례의 컨텍스트 내에서 적용됩니다.

[보존 정책 개요를](/microsoft-365/compliance/retention-policies) 참조하여 Microsoft Purview 규정 준수 포털 보존 및 보존에 대한 자세한 내용을 이해하세요. 법적 보존에 대한 자세한 Teams 관련 정보를 보려면 [Microsoft Teams 사용자 또는 팀을 법적 보류 상태로 설정](legal-hold.md) 하여 자세한 내용을 확인할 수 있습니다.

### <a name="content-search"></a>콘텐츠 검색

콘텐츠 검색을 사용하여 풍부한 필터링 기능을 통해 모든 Teams 데이터를 검색할 수 있습니다. 결과 데이터는 규정 준수 및 소송 지원을 위해 특정 컨테이너로 내보낼 수 있습니다. 이 작업은 eDiscovery 케이스를 사용하거나 사용하지 않고 수행할 수 있습니다. 이렇게 하면 규정 준수 관리자가 모든 사용자에 걸쳐 Teams 데이터를 수집하고 검토하여 내보내 추가 처리를 수행할 수 있습니다. Microsoft Teams 및 기타 Microsoft 365 또는 Office 365 콘텐츠에 대한 규정 준수 콘텐츠 검색을 수행하는 방법에 대한 자세한 내용은 [콘텐츠 검색](/microsoft-365/compliance/content-search) Microsoft Purview 규정 준수 포털을 참조하세요.

> [!TIP]
> 콘텐츠 검색을 사용하면 필요한 경우 채팅 및 채널 메시지, 모임 및 통화와 같은 콘텐츠만 Microsoft Teams로 필터링할 수 있습니다.

콘텐츠 검색 구성에 대한 Teams 관련 추가 정보를 원하는 경우 [Microsoft Teams에서 콘텐츠 검색을 검토합니다](content-search.md).

### <a name="auditing"></a>감사

감사 로그 검색은 Microsoft Purview 규정 준수 포털 바로 연결되며, 무제한 감사 타임라인에서 관리자 사용 및 조사를 위한 워크로드별 또는 일반 이벤트 집합의 내보내기를 허용하여 경고 및 감사 이벤트에 대한 보고서를 설정할 수 있는 기능을 제공합니다. Microsoft Purview 규정 준수 포털 내의 모든 감사 로그 데이터에 대한 경고를 설정하고 추가 분석을 위해 이 데이터를 필터링하고 내보낼 수 있습니다. Microsoft Purview 규정 준수 포털 Microsoft Teams 이벤트를 검색하는 방법에 대한 자세한 내용은 [Microsoft Teams의 이벤트에 대한 감사 로그 검색을 참조하세요](audit-log-events.md).

## <a name="privacy"></a>개인 정보

Microsoft에서 데이터 보호가 가장 높은 우선 순위입니다. 개인 정보 취급 방침에 대해 알아보려면 다음을 읽어보세요.  

- [Microsoft의 개인 정보 보호](https://www.microsoft.com/trust-center/privacy)
- [Microsoft Teams의 개인 정보 보호 및 보안에 대한 당사의 약속](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [IT 전문가용: Microsoft Teams의 개인 정보 보호 및 보안](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Information Protection 아키텍처

다음 그림은 Teams 파일 및 메시지에 대한 Exchange 및 SharePoint로의 Teams 데이터 수집 흐름을 나타냅니다.

> [!div class="mx-imgBorder"]
> ![Exchange 및 SharePoint에 대한 Teams 데이터의 워크플로 다이어그램.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

다음 그림은 Teams 모임의 수집 흐름과 Exchange에 대한 데이터 호출을 나타냅니다.

> [!div class="mx-imgBorder"]
> ![Teams 모임 및 Exchange로 데이터를 호출하는 워크플로의 다이어그램.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Teams 콘텐츠를 검색하는 데 최대 24시간 지연이 있을 수 있습니다.

## <a name="licensing"></a>라이선싱

정보 보호 기능과 관련하여 Microsoft 365 구독, Office 365 구독 및 연결된 독립 실행형 라이선스에 따라 사용 가능한 기능 집합이 결정됩니다.

보안 및 규정 준수를 위한 기능을 구현해야 하는 라이선스 요구 사항을 결정하는 방법에 대한 자세한 내용은 보안 및 규정 준수 기능에 대한 [라이선스 요구 사항을](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 검토하세요.

> [!NOTE]
> 콘텐츠 검색, eDiscovery(표준) 및 eDiscovery(프리미엄)는 Microsoft Purview 규정 준수 포털 작동하도록 설정할 필요가 없습니다. 자세한 내용은 [Microsoft 365 eDiscovery 솔루션을 참조하세요](/microsoft-365/compliance/ediscovery).

## <a name="location-of-data-in-teams"></a>Teams의 데이터 위치

Teams의 데이터는 Microsoft 365 또는 Office 365 조직과 연결된 지리적 영역에 위치합니다. 현재 지원되는 지역을 확인하려면 [Microsoft Teams의 데이터 위치를](location-of-data-in-teams.md) 검토하세요.

테넌트에 대한 데이터를 보관하는 지역을 확인해야 하는 경우 [Microsoft 365 관리 센터](https://portal.office.com/adminportal/home) > **Settings** > **조직 프로필** 로 이동합니다. **데이터 위치** 로 스크롤 합니다.

> [!div class="mx-imgBorder"]
> ![관리 센터의 Teams를 포함한 데이터 위치 테이블의 스크린샷.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>규정 준수 표준

Teams는 [ISO 27001](/microsoft-365/compliance/offering-iso-27001), [ISO 27018](/microsoft-365/compliance/offering-iso-27018), [SSAE18 SOC 1 및 SOC 2](/microsoft-365/compliance/offering-soc), [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech) 및 [EUMC(EU Model Clauses)](/microsoft-365/compliance/offering-eu-model-clauses)와 같은 표준을 사용합니다. Microsoft 규정 준수 프레임워크 내에서 Microsoft는 Microsoft 365 및 Office 365 애플리케이션 및 서비스를 네 가지 범주로 분류합니다. 각 범주는 해당 범주에 나열될 Microsoft 365 또는 Office 365 서비스 또는 관련 Microsoft 서비스에 대해 충족해야 하는 특정 규정 준수 약정에 의해 정의됩니다.

자세한 내용은 [데이터 보호 리소스](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)에서 찾을 수 있습니다. Teams는 Cloud Security Alliance 규정 준수도 지원합니다.

## <a name="related-topics"></a>관련 주제

[Microsoft 365 보안](/microsoft-365/security/)

[Microsoft 365 규정 준수](/microsoft-365/compliance/)

[Microsoft 규정 준수 제품](/microsoft-365/compliance/offering-home)
