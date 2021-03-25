---
title: Microsoft Teams First 롤아웃
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
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119357"
---
# <a name="roll-out-microsoft-teams-first"></a>Microsoft Teams First 롤아웃

Microsoft Teams는 직원들이 서로 연결되고 공동 작업할 수 있도록 지원할 수 있습니다. 특히 전 세계의 직원들이 원격 작업의 현실이 되는 전례 없는 현재의 경우. Teams 내의 Office 문서에서 채팅하고, 비디오 모임을 진행하고 공동 작업할 수 있게 하여 기업이 생산성을 유지하게 할 수 있습니다. 중소기업이든 비영리 조직이든 대규모 조직이든 다른 Office 앱 또는 서비스를 배포하기 전에 Microsoft 365 또는 Office 365 제품군 내의 첫 번째 워크로드로 Teams를 시작할 수 있습니다.

이 문서에서는 "Teams First" 접근 방식을 통해 고려해야 하는 고려 사항을 자세히 설명합니다.

> [!IMPORTANT]
> Teams는 조직의 첫 번째 클라우드 배포 워크로드일 수 있는 반면, Teams 배포는 전체 클라우드 배포 전략의 일부가 됐습니다.

다른 Microsoft 365 또는 Office 365 서비스를 이미 롤아웃한 경우 Teams가 첫 번째 작업 대신 롤아웃할 다음 워크로드인 경우 Teams를 롤아웃하는 [방법부터 시작하세요.](./deploy-overview.md)

## <a name="start-here"></a>여기에서 시작

Teams First 배포를 시작하려면 최소한 몇 가지 전제 요건을 충족해야 합니다. 다음 목록은 Teams를 사용하도록 설정하기 전에 조직에 필요한 기능을 보여 집니다.

1.  도메인 이름으로 구성된 Microsoft 365 또는 Office 365 조직

2.  모든 필수 특성이 테넌트와 동기화된 AAD 연결(AAD 연결) 또는 유사한 클라우드 ID 동기화 솔루션  
    AAD 동기화와 동기화된 특성을 이해하기 위해 [Azure AD Connect 동기화: Azure Active Directory에](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) 동기화된 특성

3.  Teams에 할당된 적절한 사용자 라이선스  
    Teams 라이선스를 이해하기 위해 [Microsoft Teams 서비스 설명 을 참조하세요.](/office365/servicedescriptions/teams-service-description)

4.  Teams에 대해 준비된 조직의 네트워크  
    네트워크 준비를 이해하기 위해 Teams에 대한 조직의 네트워크 준비 [를 읽어보아야 합니다.](prepare-network.md)

5.  Microsoft 365 또는 Office 365 URL 및 IP 주소 범위의 Exchange, Sharepoint 및 비즈니스용 OneDrive에 대한 네트워크 액세스를 [허용합니다.](/office365/enterprise/urls-and-ip-address-ranges)

> [!NOTE]
> 2019년 9월 1일 이후에 만든 테넌트는 Teams Only 모드에서 프로비전됩니다.
> 
> [!IMPORTANT]
> 비즈니스용 Skype 서버가 배포되어 있으며 2019년 9월 1일 이후에 테넌트가 프로비전된 경우 Teams에 대한 공존 기능을 사용하도록 지원팀에 문의하세요. 사용자에게 Teams 라이선스를 할당하기 전에 '조직 전체 업그레이드 정책'을 '아일랜드 <span class="underline">모드'로</span> 설정해야 합니다.

## <a name="migration-starting-points"></a>마이그레이션 시작 지점

Microsoft 365 또는 Office 365로의 여정 및 시작 지점 및 온-프레미스 비즈니스용 Skype 또는 Lync 서버의 존재에 따라 Teams에서 사용할 수 있는 기능입니다. 다음 섹션에서는 위의 전제 사항 외에도 기본 기능 및 구성 옵션을 자세히 설명합니다. 시작 지점 시나리오를 다음 항목으로 세분화했습니다.

**테넌트 Teams 구성**: 테넌트 및 사용자 모드는 받는 사람의 동작을 제어하는 데 사용됩니다. 이러한 설정은 테넌트 수준 또는 조직의 사용자 수준에 할당할 수 있습니다. 자세한 내용은 [비즈니스용 Skype와의 공존을 읽어보아야 합니다.](coexistence-chat-calls-presence.md)

**Teams의 채팅/외부 통신**: 채팅 서비스는 피어 투 피어 투 피어 또는 그룹 채팅 대화를 조직 내 또는 외부로 참조합니다. 외부 통신을 비즈니스용 Skype의 페더전이라고도 합니다.

**Teams에서** 모임 만들기 및 보기: 사용자는 항상 Outlook Teams 추가 기능을 통해 온라인 모임을 만들 수 있으며, 사용자가 라이선스가 부여된 후 모든 시나리오에서 PSTN 전화 접속을 사용할 수 있습니다. Teams 및 Skype for Business 스토어 일정 정보는 사용자의 Exchange 사서함에 저장됩니다. Teams 클라이언트가 사용자의 사서함과 상호 작용할 수 있도록 Exchange Server 2016 CU3 이상에서 Exchange 서버가 있어야 합니다. Exchange 사서함이 Teams의 일정 아이콘에 액세스하지 않으면 사용자가 Teams 클라이언트에서 모임을 보고 만들거나 수정할 수 없습니다.

**Teams의 VoIP/PSTN** 호출 기능 : 통화는 IP(VoIP) 또는 PSTN(공용 전환 전화 네트워크)을 통해 음성을 통해 할 수 있습니다. VoIP 연결은 Teams 클라이언트 간에 기본적으로 발생하고, 사용자가 외부 전화 번호에 전화를 걸 때 PSTN 연결이 발생합니다.  

팀은 두 가지 유형의 PSTN 연결을 지원합니다. Microsoft 통화 계획은 Microsoft가 사용자의 전화 번호 또는 직접 라우팅 구성을 포함한 전화 통신 인프라를 제공하는 경우 고객이 Teams 사용자에 대한 세션 경계 컨트롤러(SBC)를 통해 전화 통신 연결을 제공합니다.  
자세한 내용은 어떤 통화 계획이 [적합한가요?](calling-plan-landing-page.md) 및 전화 시스템 직접 라우팅 을 [읽어보세요.](direct-routing-landing-page.md)

**Teams의 팀** 및 채널 공동 작업 : Teams에서 팀은 작업, 프로젝트 또는 공통 관심사에 대해 함께 모이는 사용자 그룹입니다. 팀은 채널로 만들어 졌다. 각 채널은 "팀 이벤트", 부서 이름 또는 재미를 위해 토픽을 중심으로 구축됩니다. 채널은 모임을 개최하고, 대화를 나누고, 파일을 함께 작업하는 위치입니다. 공동 작업 중

**Teams의 비즈니스용 OneDrive(P2P** 파일 공유) : Teams 및 채널 외부에서 Teams 사용자는 Citrix Files, DropBox, Box 및 Google 드라이브와 같은 비즈니스용 OneDrive 또는 기타 P2P 공유 파일 프로그램을 사용하여 파일 피어 투 피어를 공유할 수 있습니다. 비즈니스용 OneDrive의 경우 사용자에게 SharePoint Online 라이선스가 할당되어 있어야 합니다.

**애플리케이션 플랫폼:** 앱은 조직이 Teams를 더 많이 활용하기 위해 사용할 수 있는 도구를 제공합니다. 이러한 앱은 타사 또는 조직의 개발자가 Microsoft에서 제공하는 탭, 메시징 확장, 커넥터 및 봇의 기능을 결합합니다.

**보안 및 규정 준수 기능:** Teams에는 보존 정책, DLP(데이터 손실 보호), eDiscovery 및 채널, 채팅 및 파일, 감사 로그 검색을 위한 법적 보존을 포함하여 규정 준수 영역을 지원하기 위한 다양한 정보가 있습니다. 자세한 내용은 [Microsoft Teams에서 보안 및 규정 준수를 읽어보아야 합니다.](security-compliance-overview.md)  

> [!NOTE]
> 사전 eDiscovery 기능에는 E5 라이선스가 요구됩니다.

[라이선스 옵션을 비교합니다.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

Exchange [및 Microsoft Teams가](exchange-teams-interact.md) 상호 작용하여 시나리오에서 사용할 수 있는 규정 준수 기능을 알아보는 방법을 읽습니다.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>**<span class="underline">비즈니스용</span>** Skype 또는 Lync Server가 없는 조직

이 시작점은 조직에서 현재 비즈니스용 Skype 또는 Lync Server를 활용하지 않는 것으로 가정하고 Teams는 Microsoft 365 또는 Office 365에서 첫 번째 애플리케이션이 될 것으로 가정합니다. 다음 표에서는 핵심 서비스에 대한 Teams에 대한 고급 구성 및 최종 사용자 기능을 자세히 설명합니다.

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
<td>Teams Only 모드, 모든 채팅 및 통화 기능은 Teams에만 있습니다.</td>
</tr>
<tr class="even">
<td>Teams의 채팅/외부 통신</td>
<td><p>Teams에서 내부(Microsoft 365 또는 Office 365 조직 내) 및 외부 채팅 통신을 사용할 수 있습니다.</p>
<p><em>참고: 외부 액세스에 대해 DNS 항목을 구성해야 합니다. 비즈니스용 Skype DNS 레코드는 비즈니스용 Skype 온-프레미스 또는 Microsoft 365 또는 Office 365에 없는 경우에도 Lync 및 비즈니스용 Skype 환경과의 페더전을 허용합니다.<br />
<a href="/office365/enterprise/external-domain-name-system-records">외부 도메인 이름 시스템 레코드</a></em></p></td>
</tr>
<tr class="odd">
<td>Teams에서 모임 만들기 및 보기</td>
<td><p>Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</p>
<p>PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스에서 사용할 수 있습니다.</p>
<p>Teams 일정 액세스에는 Exchange 하이브리드로 배포된 Exchange 2016 CU3+ On-프레미스가 <a href="/exchange/hybrid-deployment/deploy-hybrid">필요합니다. 하이브리드</a> 구성 마법사를 사용하여 하이브리드 배포 만들기. </p>
<p>Exchange 하이브리드 구성 외에도 Exchange OAuth 인증: Exchange 및 Exchange Online 조직 간에 <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 인증 구성"을 수립합니다.</p>

</p></td>
</tr>
<tr class="even">
<td>호출 기능<br />
Teams의 VoIP/PSTN</td>
<td><p>테넌트에 대한 내부 및 외부 VoIP를 사용할 수 있습니다.</p>
<p>PSTN 서비스는 Microsoft Phone System을 통해 구성할 수 있을 뿐만아니라 Microsoft 통화 계획 또는 직접 라우팅을 추가할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td>Teams의 팀 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 포함한 전체 환경의 경우 SharePoint Online 라이선스를 사용자에게 할당해야 합니다.</p>
<p>기존 On-Premises SharePoint 사이트의 마이그레이션은 필요하지 않습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive(P2P 파일 공유)</td>
<td>비즈니스용 OneDrive를 사용하려면 사용자가 SharePoint Online 라이선스를 할당해야 합니다. 이 라이선스가 없는 경우 피어 투 피어 파일 공유는 불가능합니다.</td>
</tr>
<tr class="odd">
<td>애플리케이션 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.<br />
자세한 정보: <a href="/microsoftteams/admin-settings">Teams의 앱에 대한 관리자 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지에 대한 준수에 대한 eDiscovery 및 법적 보류가 지원됩니다.</p></li>
<li><p>DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online에서 사용할 수 있는 전체 기능 집합; Exchange On-Premises는 이러한 대부분의 기능을 지원합니다. 전체 목록은 Exchange 및 Teams가 상호 <a href="/MicrosoftTeams/exchange-teams-interact">작용하는 방법을 참조하세요.</a></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync Server가 없는 조직에 대한 사용 단계

1.  위의 시작 섹션에서 자세히 설명한 전제 요건 충족

2.  테넌트가 Teams 전용 모드로 전환(기존 테넌트에만 [해당):](setting-your-coexistence-and-upgrade-settings.md)공존 및 업그레이드 설정 설정 .

3.  회사의 비즈니스/회사 정책에 따라 테넌트 구성: [조직의 Microsoft Teams 설정](enable-features-office-365.md)관리.

4.  Teams 클라이언트를 사용자에게 배포: [Teams용 클라이언트를 얻습니다.](get-clients.md)

5.  채택 프로그램 드라이브  
    [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 워크로드를 Microsoft 365 또는 Office 365로 이동 계획 시작

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>**<span class="underline">비즈니스용</span>** Skype 또는 Lync 서버가 있는 조직

이 시작점은 조직에서 비즈니스용 Skype 2019 또는 2015+ 또는 Lync 2013+ 온-프레미스 서버를 활용하는 것으로 가정합니다. 이미 프레미스 서버에서 Teams로 마이그레이션하는 조직에 대한 광범위한 지침이 있으며 이러한 시나리오에 따라야 합니다. 이 지침은 Teams가 Microsoft 365 또는 Office 365에서 가장 먼저 활용하는 애플리케이션인 시나리오와 관련이 있습니다. 다음 표에서는 핵심 서비스에 대한 Teams에 대한 고급 구성 및 최종 사용자 기능을 자세히 설명합니다.

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
<td>섬 모드입니다.</td>
</tr>
<tr class="even">
<td>Teams의 채팅/외부 통신</td>
<td>자체 테넌트 내에서만 내부적으로 외부 통신(페더전)은 비즈니스용 Skype 또는 Lync 서버 배포를 통해 진행됩니다.</td>
</tr>
<tr class="odd">
<td>Teams에서 모임 만들기 및 보기</td>
<td><p>Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</p>
<p>PSTN 전화 접속 및 전화 접속 기능은 오디오 회의 라이선스에서 사용할 수 있습니다.</p>
<p>Teams 일정 액세스에는 Exchange 하이브리드가 설정되어 있는 Exchange 2016 CU3+ On-프레미스가 필요합니다.<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용하여 하이브리드 배포를 만들 수 있습니다.</a></p>
<p>관리자는 Teams 모임 정책의 PreferredMeetingProviderForIslandsMode 특성인<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy를</a>통해 비즈니스용 Skype Outlook 추가 기능을 제어할 수 있습니다.</p> 
</td>
</tr>
<tr class="even">
<td>호출 기능<br />
Teams의 VoIP/PSTN</td>
<td><p>테넌트에 내부적으로 VoIP를 사용할 수 있습니다.</p>
<p>사용자가 Teams Only 환경으로 이동될 때까지 PSTN 또는 통화 계획 서비스를 사용할 수 없습니다.</p></td>
</tr>
<tr class="odd">
<td>Teams의 팀 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 포함한 전체 환경의 경우 SharePoint Online 라이선스를 사용자에게 할당해야 합니다.</p>
<p>기존 On-Premises SharePoint 사이트의 마이그레이션은 필요하지 않습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive(P2P 파일 공유)</td>
<td>비즈니스용 OneDrive를 사용하려면 사용자가 SharePoint Online 라이선스를 할당해야 합니다. 이 라이선스가 없는 경우 피어 파일 공유는 불가능합니다.</td>
</tr>
<tr class="odd">
<td>애플리케이션 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.<br />
자세한 정보: <a href="/microsoftteams/admin-settings">Teams의 앱에 대한 관리자 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지에 대한 준수에 대한 eDiscovery 및 법적 보류가 지원됩니다.</p></li>
<li><p>DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online에서 사용할 수 있는 전체 기능 집합; Exchange On-Premises는 이러한 대부분의 기능을 지원합니다. 전체 목록은 Exchange 및 Teams가 상호 <a href="/MicrosoftTeams/exchange-teams-interact">작용하는 방법을 참조하세요.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>비즈니스용 Skype 서버가 있는 조직에 대한 사용 설정 단계  

1.  위의 시작 섹션에 자세히 설명된 전제 요건을 충족합니다.

2.  테넌트 전환(2019년 9월 1일 이후 프로비전된 테넌트의 경우 지원에 문의하여 변경)  
    [공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

3.  회사의 비즈니스/회사 정책에 따라 테넌트 구성  
    [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)

4.  Teams 클라이언트 배포  
    [Teams용 클라이언트 가져오기](get-clients.md)

5.   채택 프로그램 드라이브  
    [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 워크로드를 Microsoft 365 또는 Office 365로 이동 계획 시작

7.  비즈니스용 Skype 하이브리드를 설정하고 비즈니스용 Skype 및 Lync 서버의 권장 업그레이드 경로를 따르기  
    [비즈니스용 Skype에서 프레미스에서 Teams로 업그레이드](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>닫기 문

Microsoft Teams는 조직에서 모든 직원, 정보 근로자 및 프런트라인 작업자를 단일 플랫폼에서 함께 사용할 수 있도록 지원할 수 있습니다. 오늘 [시작할 수](https://products.office.com/microsoft-teams/group-chat-software) 있습니다. 여기에서 모든 최신 공지 및 월별 제품 업데이트를 계속 연락할 수 [있습니다.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)

또한 전 세계 기업이 현재 COVID-19 상황을 관리하고 있는 동안 조직의 최대 영향력을 위해 Teams를 활용하는 데 도움이 되는 일련의 콘텐츠를 만들 수 있습니다.

  - [COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/) 기간 동안 고객에 대한 약속

  - [2주: 원격 작업에서 배운 사항](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [온라인 모임 및 이벤트 배달](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [중소 기업이 Teams와 원격으로 작업할 수 있도록 지원](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [라이브 이벤트의 디지털 변환: 최전선에서 Bob Bejan의 관찰](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT가 직원들의 원격 작업을 가능하게하는 9가지 방법](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [원격으로 작업하고 보안을 유지하며 CISOS에 대한 팁](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [교사와 학생들이 원격 학습으로 전환할 수 있도록 지원](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Microsoft Teams와 원격으로 작업하는 동안 생산성 유지](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>지원 서비스 참조

팀은 Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 365 그룹을 의존하여 사용자에게 완전히 통합된 Microsoft 365 또는 Office 365 환경을 제공합니다. 위에서 설명한 대로 Teams는 제한된 기능을 통해 이러한 서비스를 전체 배포하지 않고도 작동하게 됩니다. Teams 및 해당 전제요소에 대한 자세한 내용은 Teams에 오신 것을 [환영합니다.](teams-overview.md)

위에 나열된 각 서비스에 대한 자세한 설명은 아래 링크를 따르세요.

  - Exchange Online은 Teams에서 피어 투 피어 메시지를 일정화하고 피어 투 피어 메시지를 저장하는 데 사용됩니다. 자세한 내용은 Exchange 및 Teams 상호 작용 [방식을 읽어보아야 합니다.](exchange-teams-interact.md)

> [!IMPORTANT]
> Teams가 Exchange온-프레미스와 상호 연결되는 경우 Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성에 설명된 바와 같이 새 [Exchange OAuth 인증](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)프로토콜을 구성해야 합니다.

  - SharePoint는 채널에서 파일 공유에 사용됩니다. 비즈니스용 /OneDrive는 1:1 또는 그룹 채팅에서 파일 공유에 사용됩니다. 자세한 내용은 SharePoint Online 및 [비즈니스용 OneDrive가 Microsoft Teams와](sharepoint-onedrive-interact.md)상호 작용하는 방법을 읽어보아야 합니다.

  - [Microsoft 365 그룹은](office-365-groups.md) 팀 및 채널 만들기/관리에 사용됩니다.


## <a name="related-topics"></a>관련 항목

[Microsoft Teams IT 아키텍처 및 전화 통신 솔루션 포스터](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Teams를 사용하여 원격 작업자 지원](support-remote-work-with-teams.md)

[Microsoft 365에서 원격으로 작업](https://aka.ms/remote-work)