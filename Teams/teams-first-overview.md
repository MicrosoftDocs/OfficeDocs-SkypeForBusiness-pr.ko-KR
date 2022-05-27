---
title: Microsoft Teams 먼저 롤아웃
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: 이 지침을 사용하여 Microsoft Teams 첫 번째 Microsoft 365 또는 Office 365 워크로드로 롤아웃합니다.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2621ea94e2a35e7de9eed3dac2994f9b1932b0bb
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681729"
---
# <a name="roll-out-microsoft-teams-first"></a>Microsoft Teams 먼저 롤아웃

Microsoft Teams 특히 원격 작업이 전 세계 직원의 현실인 현재 전례 없는 시기에 직원들이 서로 연결되고 공동 작업하는 데 도움이 될 수 있습니다. Teams 내에서 채팅하고, 비디오 모임을 수행하고, Office 문서에 대해 공동 작업할 수 있는 것은 기업의 생산성을 유지하는 데 도움이 될 수 있습니다. 중소기업, 비영리 단체 또는 대규모 조직에서 다른 Office 앱 또는 서비스를 배포하기 전에 Microsoft 365 또는 Office 365 제품군 내에서 첫 번째 워크로드로 Teams 시작할 수 있습니다.

이 문서에서는 "Teams First" 접근 방식을 사용하여 고려해야 하는 사항을 자세히 설명합니다.

> [!IMPORTANT]
> Teams 조직의 첫 번째 클라우드 배포 워크로드일 수 있지만 Teams 배포하는 것은 전체 클라우드 배포 전략의 일부여야 합니다.

다른 Microsoft 365 또는 Office 365 서비스를 이미 롤아웃했으며 Teams 다음 워크로드인 경우(첫 번째가 아닌) Teams [롤아웃하는 방법](./deploy-overview.md)부터 시작합니다.

## <a name="start-here"></a>여기에서 시작

Teams First 배포를 시작하려면 최소한 몇 가지 필수 조건을 충족해야 합니다. 다음 목록에서는 Teams 사용하도록 설정하기 전에 조직에 대해 준비해야 하는 사항을 보여 줍니다.

1.  도메인 이름으로 구성된 Microsoft 365 또는 Office 365 조직

2.  테넌트와 동기화된 모든 필수 특성을 사용하여 AAD 연결(AAD 연결) 또는 유사한 클라우드 ID 동기화 솔루션 Azure Active Directory  
    AAD 동기화와 동기화된 특성을 이해하려면 [Azure AD 커넥트 동기화를 읽습니다. Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  Teams 할당된 적절한 사용자 라이선스  
    Teams 라이선스를 이해하려면 [Microsoft Teams 서비스 설명을](/office365/servicedescriptions/teams-service-description) 읽어보세요.

4.  Teams 위해 준비된 조직의 네트워크  
    네트워크 준비를 이해하려면 [Teams 위해 조직의 네트워크 준비를](prepare-network.md) 읽어 보세요.

5.  Microsoft 365 또는 Office 365 Exchange, SharePoint 및 비즈니스용 OneDrive 대한 네트워크 액세스를 허용[합니다( Office 365 URL 및 IP 주소 범위](/office365/enterprise/urls-and-ip-address-ranges)).

> [!NOTE]
> 2019년 9월 1일 이후에 만든 테넌트는 Teams 전용 모드로 프로비전됩니다.
> 
> [!IMPORTANT]
> 비즈니스용 Skype 서버 배포하고 테넌트가 2019년 9월 1일 이후에 프로비전된 경우 지원에 문의하여 Teams 공존 기능을 사용하도록 설정하세요. 사용자에게 Teams 라이선스를 할당<span class="underline">하기 전에</span> '조직 전체 업그레이드 정책'이 '아일랜드 모드'로 설정되어 있는지 확인합니다.

## <a name="migration-starting-points"></a>마이그레이션 시작 지점

시작점과 온-프레미스 비즈니스용 Skype 또는 Lync 서버의 존재에 따라 Teams 사용할 수 있는 Microsoft 365 또는 Office 365 및 기능으로의 여정. 다음 섹션에서는 위의 필수 구성 요소 외에도 기본 기능 및 구성 옵션을 자세히 설명합니다. 시작 지점 시나리오를 다음 항목으로 세분화했습니다.

**테넌트 Teams 구성**: 테넌트 및 사용자 모드는 받는 사람의 동작을 제어하는 데 사용됩니다. 이러한 설정은 조직의 테넌트 수준 또는 사용자 수준에서 할당할 수 있습니다. 자세한 내용은 [비즈니스용 Skype 공존](coexistence-chat-calls-presence.md)을 참조하세요.

**Teams 채팅/외부 통신**: 채팅 서비스는 조직 내 또는 조직 외부의 피어 투 피어 또는 그룹 채팅 대화를 참조합니다. 외부 통신을 비즈니스용 Skype 페더레이션이라고도 합니다.

**Teams 모임 만들기 및 보기**: 사용자는 항상 Outlook Teams 추가 기능을 통해 온라인 모임을 만들 수 있으며, PSTN 전화 접속은 사용자가 라이선스가 부여되면 모든 시나리오에서 사용할 수 있습니다. Teams 및 비즈니스용 Skype 사용자의 Exchange 사서함에 일정 정보를 저장합니다. 온-프레미스 Exchange 서버는 Teams 클라이언트가 사용자의 사서함과 상호 작용할 수 있도록 2016 CU3 이상을 Exchange Server 합니다. Exchange 사서함 액세스가 없으면 Teams 일정 아이콘이 표시되지 않으며 사용자는 Teams 클라이언트에서 모임을 보거나 만들거나 수정할 수 없습니다.

**Teams 통화 기능 VoIP/PSTN**: 통화는 VoIP(Voice over IP) 또는 PSTN(공중 전화망)일 수 있습니다. VoIP 연결은 기본적으로 Teams 클라이언트 간에 발생하지만 사용자가 외부 전화 번호로 전화를 걸 때 PSTN 연결이 발생합니다.  

Teams 두 가지 유형의 PSTN 연결을 지원합니다. Microsoft 통화 플랜은 Microsoft에서 사용자의 전화 번호 또는 직접 라우팅 구성을 포함한 전화 통신 인프라를 제공하는 경우 고객이 Teams 사용자에 대한 SBC(세션 테두리 컨트롤러)를 통해 전화 통신 연결을 제공합니다.  
자세한 내용은 [적합한 통화 플랜](calling-plan-landing-page.md)을 읽고 [직접 라우팅을 전화 시스템](direct-routing-landing-page.md).

**Teams Teams 및 채널 공동 작업**: Teams 팀은 업무, 프로젝트 또는 공동 관심사를 위해 함께 모이는 그룹입니다. Teams 채널로 구성됩니다. 각 채널은 "팀 이벤트", 부서 이름 또는 재미를 위해 같은 주제를 중심으로 빌드됩니다. 채널은 모임을 개최하고, 대화를 나누고, 파일을 함께 작업하는 곳입니다. 공동 작업 중

**Teams 비즈니스용 OneDrive(P2P 파일 공유):** Teams 및 채널 외부에서 Teams 사용자는 비즈니스용 OneDrive 사용하거나 Citrix 파일, DropBox, Box 및 Google 드라이브 같은 다른 P2P 공유 파일 프로그램을 사용하여 피어 투 피어 파일을 공유할 수 있습니다. 비즈니스용 OneDrive 경우 사용자에게 SharePoint Online 라이선스가 할당되어 있어야 합니다.

**애플리케이션 플랫폼**: 앱은 조직에서 Teams 더 많은 것을 얻을 수 있는 기본 도구를 제공합니다. 이러한 앱은 타사 또는 조직의 개발자가 빌드한 Microsoft에서 제공하는 탭, 메시징 확장, 커넥터 및 봇의 기능을 결합합니다.

**보안 및 규정 준수 기능:** Teams 보존 정책, DLP(데이터 손실 방지), eDiscovery 및 채널, 채팅 및 파일에 대한 법적 보존, 감사 로그 검색 등 규정 준수 영역에 도움이 되는 다양한 정보를 제공합니다. 자세한 내용은 [Microsoft Teams 보안 및 규정 준수를](security-compliance-overview.md) 참조하세요.  

> [!NOTE]
> 고급 eDiscovery 기능을 사용하려면 E5 라이선스가 필요합니다.

[라이선스 옵션을 비교합니다](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

[Exchange 및 Microsoft Teams 상호 작용](exchange-teams-interact.md)하여 시나리오에서 사용할 수 있는 규정 준수 기능을 알아봅니다.

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync Server **<span class="underline">가 없는</span>** 조직

이 시작점에서는 조직에서 현재 비즈니스용 Skype 또는 Lync Server를 활용하지 않으며 Teams Microsoft 365 또는 Office 365 첫 번째 애플리케이션이 될 것이라고 가정합니다. 다음 표에서는 핵심 서비스에 대한 Teams 대한 높은 수준의 구성 및 최종 사용자 기능에 대해 자세히 설명합니다.

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
<td>Teams 모드에서는 모든 채팅 및 통화 기능이 Teams 전용입니다.</td>
</tr>
<tr class="even">
<td>Teams 채팅/외부 통신</td>
<td><p>내부(Microsoft 365 또는 Office 365 조직 내부) 및 Teams 외부 채팅 통신이 가능합니다.</p>
<p><em>참고: 외부 액세스를 위해 DNS 항목을 구성해야 합니다. 비즈니스용 Skype DNS 레코드는 Lync 및 비즈니스용 Skype 환경과의 페더레이션을 허용하기 위해 온-프레미스 또는 Microsoft 365 또는 Office 365 비즈니스용 Skype 없는 경우에도 필요합니다.<br />
<a href="/office365/enterprise/external-domain-name-system-records">외부 도메인 이름 시스템 레코드</a></em></p></td>
</tr>
<tr class="odd">
<td>Teams 모임 만들기 및 보기</td>
<td><p>Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</p>
<p>PSTN Dial in 및 Dial out 기능은 오디오 회의 라이선스에서 사용할 수 있습니다.</p>
<p>Teams 일정 액세스에는 Exchange 하이브리드를 사용하여 배포된 Exchange 2016 CU3+ 온-프레미스: <a href="/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용하여 하이브리드 배포 만들기가 필요합니다.</a> </p>

Exchange 하이브리드 구성 외에도 Exchange OAuth 인증을 설정합니다. [Exchange 조직과 Exchange Online 조직 간에 OAuth 인증을 구성합니다](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help). 

</p></td>
</tr>
<tr class="even">
<td>통화 기능<br />
Teams VoIP/PSTN</td>
<td><p>내부 및 외부적으로 테넌트에 대한 VoIP를 사용할 수 있습니다.</p>
<p>PSTN 서비스는 Microsoft 전화 시스템을 통해 구성할 수 있으며 Microsoft 통화 플랜 또는 직접 라우팅을 추가할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td>Teams Teams 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 포함한 전체 환경을 위해 SharePoint Online 라이선스를 사용자에게 할당해야 합니다.</p>
<p>기존 온-프레미스 SharePoint 사이트의 마이그레이션은 필요하지 않습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive(P2P 파일 공유)</td>
<td>비즈니스용 OneDrive 사용자에게 SharePoint Online 라이선스가 할당되어야 합니다. 이 라이선스가 없으면 피어 투 피어 파일 공유가 불가능합니다.</td>
</tr>
<tr class="odd">
<td>애플리케이션 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.<br />
자세한 내용은 다음을 참조하세요. <a href="/microsoftteams/admin-settings">Teams 앱에 대한 관리 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지의 규정 준수에 대한 eDiscovery 및 법적 보존이 지원됩니다.</p></li>
<li><p>DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online 함께 사용할 수 있는 전체 기능 집합 Exchange 온-프레미스는 이러한 기능 대부분을 지원합니다. 전체 목록은 <a href="/MicrosoftTeams/exchange-teams-interact">Exchange 및 Teams 상호 작용하는 방법을 참조하세요</a>.</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync Server가 없는 조직의 사용 단계

1.  위의 시작 섹션에 자세히 설명된 필수 구성 요소 충족

2.  테넌트 Teams 전용 모드로 전환(기존 테넌트에만 해당): [공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

3.  회사의 비즈니스/회사 정책에 따라 테넌트 구성: [조직의 Microsoft Teams 설정을 관리합니다](enable-features-office-365.md).

4.  사용자에게 Teams 클라이언트 배포: [Teams 클라이언트 가져오기](get-clients.md)

5.  채택 프로그램 추진  
    [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 워크로드를 Microsoft 365 또는 Office 365 이동 계획 시작

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>비즈니스용 Skype 또는 Lync 서버가 **<span class="underline">있는</span>** 조직

이 시작점에서는 조직에서 비즈니스용 Skype 2019 또는 2015+ 또는 Lync 2013+ 서버를 온-프레미스에서 활용한다고 가정합니다. 온-프레미스 서버에서 Teams 마이그레이션하는 조직에 대한 광범위한 지침이 이미 있으며 이러한 시나리오에 따라야 합니다. 이 지침은 Teams Microsoft 365 또는 Office 365 사용하는 첫 번째 애플리케이션인 시나리오에 따라 다릅니다. 다음 표에서는 핵심 서비스에 대한 Teams 대한 높은 수준의 구성 및 최종 사용자 기능에 대해 자세히 설명합니다.

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
<td>아일랜드 모드입니다.</td>
</tr>
<tr class="even">
<td>Teams 채팅/외부 통신</td>
<td>자체 테넌트 내에서만 내부적으로 외부 통신(페더레이션)은 비즈니스용 Skype 또는 Lync 서버 배포를 통해서만 가능합니다.</td>
</tr>
<tr class="odd">
<td>Teams 모임 만들기 및 보기</td>
<td><p>Outlook 추가 기능을 통해 내부 및 외부 모임을 만들 수 있습니다.</p>
<p>PSTN Dial in 및 Dial out 기능은 오디오 회의 라이선스에서 사용할 수 있습니다.</p>
<p>Teams 일정 액세스에는 Exchange 하이브리드가 설정된 Exchange 2016 CU3+ 온-프레미스가 배포되어야 합니다.<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">하이브리드 구성 마법사를 사용하여 하이브리드 배포를 만듭니다.</a></p>
<p>관리자는 Teams 모임 정책의 PreferredMeetingProviderForIslandsMode 특성<a href="/powershell/module/skype/set-csteamsmeetingpolicy">인 set-csteamsmeetingpolicy</a>를 통해 비즈니스용 Skype Outlook 추가 기능을 제어할 수 있습니다.</p> 
</td>
</tr>
<tr class="even">
<td>통화 기능<br />
Teams VoIP/PSTN</td>
<td><p>내부적으로 테넌트에 대한 VoIP를 사용할 수 있습니다.</p>
<p>PSTN 또는 통화 플랜 서비스는 사용자가 Teams 전용 환경으로 이동될 때까지 사용할 수 없습니다.</p></td>
</tr>
<tr class="odd">
<td>Teams Teams 및 채널 공동 작업</td>
<td><p>규정 준수 기능을 포함한 전체 환경을 위해 SharePoint Online 라이선스를 사용자에게 할당해야 합니다.</p>
<p>기존 온-프레미스 SharePoint 사이트의 마이그레이션은 필요하지 않습니다.</p></td>
</tr>
<tr class="even">
<td>비즈니스용 OneDrive(P2P 파일 공유)</td>
<td>비즈니스용 OneDrive 사용자에게 SharePoint Online 라이선스가 할당되어야 합니다. 피어당 이 라이선스가 없으면 파일 공유를 수행할 수 없습니다.</td>
</tr>
<tr class="odd">
<td>애플리케이션 플랫폼</td>
<td>사용자는 회사 정책에 따라 사용할 수 있도록 지정된 앱을 사용할 수 있습니다.<br />
자세한 내용은 다음을 참조하세요. <a href="/microsoftteams/admin-settings">Teams 앱에 대한 관리 설정</a></td>
</tr>
<tr class="even">
<td>보안 및 규정 준수 기능</td>
<td><ul>
<li><p>보존 정책을 사용할 수 있습니다.</p></li>
<li><p>채널 메시지의 규정 준수에 대한 eDiscovery 및 법적 보존이 지원됩니다.</p></li>
<li><p>DLP(데이터 손실 방지 정책)를 사용할 수 있습니다.</p></li>
</ul>
<p>Exchange Online 함께 사용할 수 있는 전체 기능 집합 Exchange 온-프레미스는 이러한 기능 대부분을 지원합니다. 전체 목록은 <a href="/MicrosoftTeams/exchange-teams-interact">Exchange 및 Teams 상호 작용하는 방법을 참조하세요.</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>비즈니스용 Skype 서버 있는 조직을 위한 사용 단계  

1.  위의 시작 섹션에 자세히 설명된 필수 구성 요소를 충족합니다.

2.  테넌트 모드로 전환(2019년 9월 1일 이후에 프로비전된 테넌트에 대해서는 지원에 문의하여 변경하세요.)  
    [공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

3.  회사의 비즈니스/회사 정책에 따라 테넌트 구성  
    [조직에서 Microsoft Teams 설정 관리](enable-features-office-365.md)

4.  Teams 클라이언트 배포  
    [Teams용 클라이언트 가져오기](get-clients.md)

5.   채택 프로그램 추진  
    [Microsoft Teams 채택](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams 채택 빠른 시작 검사 목록](teams-adoption-quick-start-checklist.md)

6.  다른 워크로드를 Microsoft 365 또는 Office 365 이동 계획 시작

7.  비즈니스용 Skype 하이브리드를 설정하고 비즈니스용 Skype 및 Lync 서버에 권장되는 업그레이드 경로를 따릅니다.  
    [비즈니스용 Skype 온-프레미스에서 Teams 업그레이드](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>닫는 문

Microsoft Teams 조직에서 모든 직원, 정보 근로자 및 일선 직원을 단일 플랫폼으로 한데 모을 수 있는 가능하게 만들 수 있습니다. 오늘 [시작할](https://products.office.com/microsoft-teams/group-chat-software) 수 있습니다. 여기에서 모든 최신 공지 사항 및 월별 제품 업데이트에 계속 연락할 수 [있습니다](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).

또한 전 세계 기업이 현재 COVID-19 상황을 관리함에 따라 조직의 최대 영향을 위해 Teams 활용하는 데 도움이 되는 일련의 콘텐츠를 만들었습니다.

  - [COVID-19 기간 동안 고객에 대한 당사의 약속](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2주: 원격 작업에 대해 배운 내용](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [온라인 모임 및 이벤트 제공](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [중소 기업이 Teams와 원격으로 작업할 수 있도록 지원](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [라이브 이벤트의 디지털 변환: 최전방에서 밥 베잔의 관찰](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT가 직원들의 원격 작업을 가능하게하는 9가지 방법](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [원격으로 작업, 보안 유지 - CISO에 대한 팁](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [교사와 학생들이 원격 학습으로 전환할 수 있도록 지원](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [Microsoft Teams 원격으로 작업하는 동안 생산성 유지](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>지원 서비스 참조

Teams Exchange Online, SharePoint Online, 비즈니스용 OneDrive 및 Microsoft 365 그룹 사용하여 사용자에게 완전히 통합된 Microsoft 365 또는 Office 365 환경을 제공합니다. 위에서 설명한 대로 Teams 제한된 기능으로 이러한 서비스를 완전히 배포하지 않고 작동합니다. Teams 및 필수 구성 요소에 대한 자세한 내용은 다음을 참조하세요. [Teams 시작](teams-overview.md)하세요.

위에 나열된 각 서비스에 대한 자세한 내용은 아래 링크를 따르세요.

  - Exchange Online 일정 기능을 사용하고 피어 투 피어 메시지를 Teams 저장하는 데 사용됩니다. 자세한 내용은 [Exchange 및 Teams 상호 작용하는 방법을](exchange-teams-interact.md) 참조하세요.

> [!IMPORTANT]
> Exchange 온-프레미스와의 Teams interop의 경우 Exchange [조직과 Exchange Online 조직 간의 OAuth 인증 구성에 설명된 대로 새 Exchange OAuth 인증](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) 프로토콜을 구성해야 합니다.

  - SharePoint 채널에서 파일 공유에 사용되는 반면 /비즈니스용 OneDrive 1:1 또는 그룹 채팅에서 파일 공유에 사용됩니다. 자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive Microsoft Teams 상호 작용하는 방법을](sharepoint-onedrive-interact.md) 참조하세요.

  - [Microsoft 365 그룹](office-365-groups.md) 팀 및 채널 만들기/관리에 사용됩니다.


## <a name="related-topics"></a>관련 항목

[Microsoft Teams IT 아키텍처 및 전화 통신 솔루션 포스터](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[비즈니스용 Skype 서버와 Office 365 간의 하이브리드 연결 플랜](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[Teams 사용하여 원격 작업자 지원](support-remote-work-with-teams.md)

[Microsoft 365 원격으로 작업](https://aka.ms/remote-work)
