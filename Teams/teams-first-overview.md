---
title: 먼저 Microsoft Teams 출시
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: 이 지침을 사용하여 Microsoft Teams를 첫 번째 Microsoft 365 또는 Office 365 워크로드로 롤아웃합니다.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909482"
---
# <a name="roll-out-microsoft-teams-first"></a>먼저 Microsoft Teams 출시

Microsoft Teams는 직원들이 서로 연결되고 공동 작업할 수 있도록 지원할 수 있습니다. 특히 원격 업무가 전 세계 직원의 현실인 현재 전례 없는 시간에서 공동 작업할 수 있습니다. Teams 내에서 채팅하고, 비디오 모임을 진행하고, Office 문서에 대해 공동 작업할 수 있게 하여 회사 생산성을 유지하세요. 중소기업, 비영리 또는 대규모 조직이든, 다른 Office 앱 또는 서비스를 배포하기 전에 Microsoft 365 또는 Office 365 제품군 내에서 첫 번째 워크로드로 Teams를 시작할 수 있습니다.

이 문서에서는 "Teams First" 접근 방식을 통해 해야 하는 고려 사항을 자세히 설명하고 있습니다.

> [!IMPORTANT]
> Teams는 조직의 첫 번째 클라우드 배포 워크로드가 될 수 있는 반면 Teams 배포는 전체 클라우드 배포 전략의 일부가 됐습니다.

다른 Microsoft 365 또는 Office 365 서비스를 이미 롤아웃한 경우 Teams가 첫 번째 대신 롤아웃할 다음 워크로드인 경우 Teams를 롤아웃하는 방법을 [시작하세요.](How-to-roll-out-teams.md)

## <a name="start-here"></a>여기에서 시작

Teams First 배포를 시작하려면 최소한 몇 가지 요구 사항을 충족해야 합니다. Teams를 사용하도록 설정하기 전에 조직에 대해 설정해야 하는 항목은 다음 목록에 표시됩니다.

1.  도메인 이름으로 구성된 Microsoft 365 또는 Office 365 조직

2.  테넌트와 동기화된 모든 필수 특성이 있는 AAD 연결(AAD 연결) 또는 유사한 클라우드 ID 동기화 솔루션  
    AAD 동기화와 동기화된 특성을 이해하기 위해 [Azure AD Connect 동기화: Azure Active Directory에](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) 동기화된 특성 읽기

3.  Teams에 할당된 적절한 사용자 라이선스  
    Teams 라이선스를 이해하기 위해 Microsoft Teams 서비스 [설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

4.  Teams에 대해 준비된 조직의 네트워크  
    네트워크 준비를 이해하기 위해 [Teams에 대한 조직의 네트워크 준비를 읽어보아야 합니다.](prepare-network.md)

5.  Microsoft 365 또는 Office 365: [Office 365 URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)및 IP 주소 범위에서 Exchange, Sharepoint 및 비즈니스용 OneDrive에 대한 네트워크 액세스를 허용합니다.

> [!NOTE]
> 2019년 9월 1일 이후에 만든 테넌트는 Teams 전용 모드로 프로비전됩니다.
> 
> [!IMPORTANT]
> 비즈니스용 Skype Server를 배포하고 2019년 9월 1일 이후에 테넌트가 프로비전된 경우 지원에 문의하여 Teams의 공존 기능을 사용하도록 설정하세요. 사용자에게 Teams 라이선스를 할당하기 전에 '조직 전체 <span class="underline"></span> 업그레이드 정책'을 '섬 모드'로 설정해야 합니다.

## <a name="migration-starting-points"></a>마이그레이션 시작 지점

시작 지점 및 온-프레미스 비즈니스용 Skype 또는 Lync 서버의 존재 여부에 따라 Microsoft 365 또는 Office 365 및 Teams에서 사용할 수 있는 기능에 대한 여정입니다. 다음 섹션에서는 위의 전제 구성 구성 외에도 기본 기능 및 구성 옵션에 대해 자세히 설명합니다. 시작 지점 시나리오를 다음 항목으로 세분화했습니다.

**테넌트 Teams 구성:** 테넌트 및 사용자 모드는 받는 사람의 동작을 제어하는 데 사용됩니다. 이러한 설정은 테넌트 수준 또는 조직의 사용자 수준에서 할당할 수 있습니다. 자세한 내용은 비즈니스용 [Skype와의 공존을 읽어보아야 합니다.](coexistence-chat-calls-presence.md)

**Teams의 채팅/외부 통신: 채팅** 서비스는 피어 투 피어 또는 그룹 채팅 대화를 조직 내부 및 조직 내부 또는 외부에서 참조합니다. 외부 통신을 비즈니스용 Skype에서 페더러리라고도 합니다.

**Teams에서** 모임 만들기 및 보기: 사용자는 항상 Outlook Teams 추가 기능을 통해 온라인 모임을 만들 수 있으며, 사용자가 라이선스가 부여된 후 모든 시나리오에서 PSTN 전화 접속을 사용할 수 있습니다. Teams 및 비즈니스용 Skype는 사용자의 Exchange 사서함에 일정 정보를 저장합니다. Teams 클라이언트가 사용자의 사서함과 상호 작용할 수 있도록 Exchange Server 2016 CU3 이상을 위한 프레미스 Exchange 서버가 있어야 합니다. Exchange 사서함에 액세스하지 않으면 Teams의 일정 아이콘이 나타나지 않고 사용자가 Teams 클라이언트에서 모임을 보거나 만들거나 수정할 수 없습니다.

**Teams의 VoIP/PSTN** 통화 기능: 통화는 VoIP(Voice over IP) 또는 PSTN(Public Switched Telephone Network)일 수 있습니다. VoIP 연결은 Teams 클라이언트 간에 기본적으로 발생하고, PSTN 연결은 사용자가 외부 전화 번호로 전화를 걸 때 발생합니다.  

Teams는 두 가지 유형의 PSTN 연결을 지원합니다. Microsoft 통화 요금제는 Microsoft에서 사용자의 전화 번호를 포함한 전화 통신 인프라 또는 직접 라우팅 구성을 제공하는 경우 고객이 Teams 사용자의 SBC(세션 테두리 컨트롤러)를 통해 전화 통신 연결을 제공합니다.  
자세한 내용은 어떤 통화 [요금제가 적합한가요?](calling-plan-landing-page.md) 및 전화 시스템 직접 라우팅을 [읽어보세요.](direct-routing-landing-page.md)

**Teams의 팀** 및 채널 공동 작업: Teams에서 팀은 작업, 프로젝트 또는 일반적인 관심사에 대해 함께 모인 사용자 그룹입니다. 팀은 채널로만 이월됩니다. 각 채널은 "팀 이벤트", 부서 이름 또는 재미를 위해 주제를 중심으로 구축됩니다. 채널은 모임을 열고, 대화를 나누고, 파일을 함께 작업하는 위치입니다. 공동 작업 중

**Teams의 비즈니스용 OneDrive(P2P** 파일 공유) : Teams 및 채널 외부에서 Teams 사용자는 비즈니스용 OneDrive 또는 Citrix Files, DropBox, Box 및 Google Drive와 같은 다른 P2P 공유 파일 프로그램을 사용하여 파일 피어 투 피어를 공유할 수 있습니다. 비즈니스용 OneDrive의 경우 사용자에게 SharePoint Online 라이선스가 할당되어 있어야 합니다.

**애플리케이션 플랫폼:** 앱은 조직에서 Teams를 더 많이 활용하는 데 사용할 수 있는 도구를 제공합니다. 이러한 앱은 타사 또는 조직의 개발자가 Microsoft에서 제공하는 탭, 메시징 확장, 커넥터 및 봇의 기능을 결합합니다.

**보안 및 규정 준수 기능:** Teams에는 보존 정책, DLP(데이터 손실 방지), eDiscovery 및 채널, 채팅 및 파일, 감사 로그 검색에 대한 법적 보존을 포함하여 규정 준수 영역을 지원하기 위한 다양한 정보가 있습니다. 자세한 내용은 Microsoft Teams에서 보안 [및 규정 준수를 읽어보아야 합니다.](security-compliance-overview.md)  

> [!NOTE]
> EDiscovery 기능의 경우 E5 라이선스가 필요 합니다.

[라이선스 옵션을 비교합니다.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

[Exchange 및 Microsoft Teams가 상호](exchange-teams-interact.md) 작용하여 시나리오에서 사용할 수 있는 규정 준수 기능을 알아보는 방법을 읽어 읽습니다.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>**<span class="underline">비즈니스용</span>** Skype 또는 Lync Server가 없는 조직

이 시작점에서는 조직에서 현재 비즈니스용 Skype 또는 Lync Server를 활용하지 않는 경우 Teams가 Microsoft 365 또는 Office 365의 첫 번째 응용 프로그램이 될 것으로 가정합니다. 다음 표에서는 핵심 서비스에 대한 Teams에 대한 고급 구성 및 최종 사용자 기능에 대해 자세히 설명하고 있습니다.

<table>
<thead>
<tr class="header">
<th>항목</th>
<th>참고</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>테넌트 Teams 구성</td>
<td>Teams 전용 모드, 모든 채팅 및 통화 기능은 Teams에만 있습니다.</td>
</tr>
<tr class="even">
<td>Teams의 채팅/외부 통신</td>
<td><p>Teams에서 내부(Microsoft 365 또는 Office 365 조직 내부) 및 외부 채팅 통신을 사용할 수 있습니다.</p>
<p><em>참고: 외부 액세스를 위해 DNS 항목을 구성해야 합니다. 비즈니스용 Skype DNS 레코드는 비즈니스용 Skype 온-프레미스 또는 Microsoft 365 또는 Office 365에 없는 경우에도 Lync 및 비즈니스용 Skype 환경과의 페더맹을 허용하는 데 필요합니다.<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">외부 도메인 이름 시스템 레코드</a></em></p></td>
</tr>
<tr class="odd">
<td>Teams에서 모임 만들기 및 보기</td>
<td><p>Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</p>
<p>오디오 회의 라이선스에서 PSTN 다이얼 인 및 전화 걸기 기능을 사용할 수 있습니다.</p>
<p>Teams 일정 액세스에는 Exchange 하이브리드를 사용하여 배포된 Exchange 2016 CU3+ On-프레미스가 <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">필요합니다. 하이브리드</a> 구성 마법사를 사용하여 하이브리드 배포 만들기 </p>
<p>Exchange 하이브리드 구성 외에도 Exchange OAuth 인증을 설정: Exchange와 Exchange Online 조직 간에 <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 인증 구성"을 수립합니다.</p>

</p></td>
</tr>
<tr class="even">
<td>통화 기능<br />
Teams의 VoIP/PSTN</td>
<td><p>테넌트 내부 및 외부에서 VoIP를 사용할 수 있습니다.</p>
<p>Microsoft Phone System을 통해 PSTN 서비스를 구성하고 Microsoft 통화 요금제 또는 직접 라우팅을 추가할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td>Teams의 팀 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 포함한 전체 환경을 위해 사용자에게 SharePoint Online 라이선스를 할당해야 합니다.</p>
<p>기존 On-프레미스 SharePoint 사이트를 마이그레이션할 필요는 없습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive(P2P 파일 공유)</td>
<td>비즈니스용 OneDrive를 사용하려면 사용자가 SharePoint Online 라이선스를 할당해야 합니다. 이 라이선스가 없는 경우 피어 투 피어 파일 공유는 불가능합니다.</td>
</tr>
<tr class="odd">
<td>애플리케이션 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.<br />
자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams의 앱에 대한 관리자 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지에 대한 규정 준수를 위한 eDiscovery 및 법적 보류가 지원됩니다.</p></li>
<li><p>DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online에서 사용할 수 있는 전체 기능 집합 Exchange-프레미스에서는 이러한 기능 대부분을 지원하고 있습니다. 전체 목록은 Exchange 및 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Teams가 상호 작용하는 방법을 참조하세요.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync Server가 없는 조직에 대한 사용 단계

1.  위의 시작 섹션에 자세히 설명된 전제 요건 충족

2.  테넌트가 Teams 전용 모드로 전환(기존 테넌트에만 해당): 공존 및 업그레이드 설정 [설정](setting-your-coexistence-and-upgrade-settings.md)

3.  회사의 비즈니스/회사 정책에 따라 테넌트 구성: [조직의 Microsoft Teams](enable-features-office-365.md)설정 관리

4.  사용자에게 Teams 클라이언트 배포: [Teams용 클라이언트를 얻습니다.](get-clients.md)

5.  채택 프로그램 구동  
    [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 워크로드를 Microsoft 365 또는 Office 365로 이동 계획 시작

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>**<span class="underline">비즈니스용</span>** Skype 또는 Lync 서버가 있는 조직

이 시작점에서는 조직이 온-프레미스에서 비즈니스용 Skype 2019 또는 2015+ 또는 Lync 2013+ 서버를 활용하고 있는 것으로 가정합니다. 이미 프레미스 서버에서 Teams로 마이그레이션하는 조직에 대한 광범위한 지침이 있으며 이러한 시나리오에 따라야 합니다. 이 지침은 Teams가 Microsoft 365 또는 Office 365에서 가장 먼저 활용하는 응용 프로그램인 시나리오와 관련이 있습니다. 다음 표에서는 핵심 서비스에 대한 Teams에 대한 고급 구성 및 최종 사용자 기능에 대해 자세히 설명하고 있습니다.

<table>
<thead>
<tr class="header">
<th>항목</th>
<th>참고</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>테넌트 Teams 구성</td>
<td>제도 모드입니다.</td>
</tr>
<tr class="even">
<td>Teams의 채팅/외부 통신</td>
<td>자체 테넌트 내에서만 내부적으로 외부 통신(페더십)은 비즈니스용 Skype 또는 Lync 서버 배포를 통해 진행됩니다.</td>
</tr>
<tr class="odd">
<td>Teams에서 모임 만들기 및 보기</td>
<td><p>Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</p>
<p>오디오 회의 라이선스에서 PSTN 다이얼 인 및 전화 걸기 기능을 사용할 수 있습니다.</p>
<p>Teams 일정 액세스에는 Exchange 하이브리드를 설정하여 배포된 Exchange 2016 CU3+ On-프레미스가 필요합니다.<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용하여 하이브리드 배포를 만들 수 있습니다.</a></p>
<p>관리자는 Teams 모임 정책의 PreferredMeetingProviderForIslandsMode 특성인<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy를</a>통해 비즈니스용 Skype Outlook 추가 기능을 제어할 수 있습니다.</p> 
</td>
</tr>
<tr class="even">
<td>통화 기능<br />
Teams의 VoIP/PSTN</td>
<td><p>테넌트에 내부적으로 VoIP를 사용할 수 있습니다.</p>
<p>사용자가 Teams 전용 환경으로 이동될 때까지 PSTN 또는 통화 요금제 서비스를 사용할 수 없습니다.</p></td>
</tr>
<tr class="odd">
<td>Teams의 팀 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 포함한 전체 환경을 위해 사용자에게 SharePoint Online 라이선스를 할당해야 합니다.</p>
<p>기존 On-프레미스 SharePoint 사이트를 마이그레이션할 필요는 없습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive(P2P 파일 공유)</td>
<td>비즈니스용 OneDrive를 사용하려면 사용자가 SharePoint Online 라이선스를 할당해야 합니다. 이 라이선스가 없는 경우 피어 파일 공유가 불가능합니다.</td>
</tr>
<tr class="odd">
<td>애플리케이션 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.<br />
자세한 정보: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Teams의 앱에 대한 관리자 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지에 대한 규정 준수를 위한 eDiscovery 및 법적 보류가 지원됩니다.</p></li>
<li><p>DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online에서 사용할 수 있는 전체 기능 집합 Exchange-프레미스에서는 이러한 기능 대부분을 지원하고 있습니다. 전체 목록은 Exchange 및 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Teams가 상호 작용하는 방법을 참조하세요.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>비즈니스용 Skype Server를 사용하여 조직에 대한 사용 단계  

1.  위의 시작 섹션에 자세히 설명된 요구 사항을 충족합니다.

2.  테넌트가 제도 모드로 전환(2019년 9월 1일 이후에 프로비전된 테넌트의 경우 이 변경을 위해 고객 지원에 문의)  
    [공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

3.  회사의 비즈니스/회사 정책에 따라 테넌트 구성  
    [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)

4.  Teams 클라이언트 배포  
    [Teams용 클라이언트 가져오기](get-clients.md)

5.   채택 프로그램 구동  
    [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 워크로드를 Microsoft 365 또는 Office 365로 이동 계획 시작

7.  비즈니스용 Skype 하이브리드를 설정하고 비즈니스용 Skype 및 Lync 서버에 대한 권장 업그레이드 경로를 따르기  
    [비즈니스용 Skype-프레미스에서 Teams로 업그레이드](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>닫기 문

Microsoft Teams는 조직에서 모든 직원, 정보 근로자 및 일선 직원을 단일 플랫폼으로 모을 수 있도록 지원할 수 있습니다. 지금 시작할 [수](https://products.office.com/microsoft-teams/group-chat-software) 있습니다. 여기에서 최신 공지 및 월별 제품 업데이트를 계속 연락할 수 [있습니다.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

또한 전 세계 회사가 현재 COVID-19 상황을 관리하고 있는 동안 Teams를 조직에서 최대의 영향력으로 활용하는 데 도움이 되는 일련의 콘텐츠를 만들 수 있습니다.

  - [COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/) 기간 동안 고객에게 약속

  - [2주: 원격 작업에서 배운 사항](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [온라인 모임 및 이벤트 제공](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [중소 기업이 Teams와 원격으로 작업할 수 있도록 지원](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [라이브 이벤트의 디지털 변환: 최전선에서 Bob Bejan의 관찰](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT가 직원들의 원격 작업을 가능하게하는 9가지 방법](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [원격으로 작업하고 보안을 유지하며 CIS에 대한 팁](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [교사와 학생이 원격 학습으로 전환할 수 있도록 지원](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Microsoft Teams를 사용하여 원격으로 작업하면서 생산성 유지](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>지원 서비스 참조

Teams는 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 365 그룹을 통해 사용자에게 완전히 통합된 Microsoft 365 또는 Office 365 환경을 제공합니다. 위에서 설명한 대로 Teams는 제한된 기능으로 이러한 서비스를 전체 배포하지 않고도 작동할 것입니다. Teams 및 해당 전제에 대한 자세한 내용은 Teams에 오신 것을 [환영합니다.](teams-overview.md)

위에 나열된 각 서비스에 대한 구체적인 설명은 아래 링크를 따르세요.

  - Exchange Online은 Teams에서 일정 기능 및 피어 투 피어 메시지 저장에 사용됩니다. 자세한 내용은 Exchange 및 [Teams가 상호 작용하는 방법을 읽어보아야 합니다.](exchange-teams-interact.md)

> [!IMPORTANT]
> Exchange와 Exchange Online 조직 간의 OAuth 인증 구성에 설명된 새 Exchange [OAuth](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)인증 프로토콜을 구성해야 합니다.

  - SharePoint는 채널에서 파일 공유에 사용되는 반면 비즈니스용 OneDrive는 1:1 또는 그룹 채팅에서 파일 공유에 사용됩니다. 자세한 내용은 SharePoint Online 및 [비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법을 읽어보아야 합니다.](sharepoint-onedrive-interact.md)

  - [Microsoft 365 그룹은](office-365-groups.md) 팀 및 채널 만들기/관리에 사용됩니다.


## <a name="related-topics"></a>관련 항목

[Microsoft Teams IT 아키텍처 및 전화 통신 솔루션 포스터](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Teams를 사용하여 원격 작업자 지원](support-remote-work-with-teams.md)

[Microsoft 365를 사용하여 원격으로 작업](https://aka.ms/remote-work)
