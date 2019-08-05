---
title: 팀 및 비즈니스용 Skype에 대 한 클라우드 통합
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 문서에서는 UC 작업을 팀 및/또는 비즈니스용 Skype Online으로 이동 하기 위해 이동 하려는 비즈니스용 Skype (또는 Lync)를 사용 하는 조직에 대해 이러한 통합을 구현 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: 46e84f9a65ec7626c5285196af83d63baa46c15e
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2019
ms.locfileid: "36185559"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>팀 및 비즈니스용 Skype에 대 한 클라우드 통합

많은 대규모 엔터프라이즈에는 온-프레미스 광고 포리스트가 두 개 이상 있으며, 경우에 따라 고객에 게 둘 이상의 Exchange 및/또는 비즈니스용 Skype 서버 (또는 Lync Server) 배포가 있습니다. 또한 한 온-프레미스 포리스트만 사용 하는 조직 에서도 비즈니스 합병 또는 획득을 통해 유사한 상황에서 자신을 찾을 수 있습니다. 이러한 고객은 클라우드로 이동할 때 주어진 온-프레미스 작업의 여러 인스턴스를 클라우드로 단일 Office 365 테 넌 트로 통합 하려고 합니다. 이 문서에서는 UC 작업을 Microsoft 클라우드 (예: Microsoft 팀 및/또는 비즈니스용 Skype Online)로 이동 하려는 비즈니스용 Skype (또는 Lync)의 여러 온-프레미스 배포를 사용 하는 조직에 대해 이러한 통합을 구현 하는 방법에 대해 설명 합니다.

이에 대 한 지침은 지금부터 온-프레미스에 배포를 통합 하 고 클라우드로 이동 하는 고객을 위한 것입니다. 이 문서는 계속 옵션 이지만, 여러 비즈니스용 Skype 배포를 사용 하는 조직이 한 번에 하나의 배포를 단일 Office 365 테 넌 트로 마이그레이션할 수 있도록 하는 새로운 기능을 기반으로 하는 솔루션에 대해 설명 합니다 (온-프레미스 필요 없음). 통합과. 이 새로운 기능을 사용 하는 경우에도 비즈니스용 Skype Online 및 Microsoft 팀은 단일 Office 365 테 넌 트를 사용 하 여 하이브리드 모드에서 비즈니스용 Skype/Lync 포리스트를 여러 개 지원 하지 않습니다. 

> [!Important]
> 구성에이 가이드를 사용 하기 전에 [제한 사항을](#limitations)검토 하 고 이해 하는 것이 조직에 영향을 미칠 수 있으므로 확인 해야 합니다.

## <a name="overview-of-cloud-consolidation"></a>클라우드 통합 개요

다음 주요 요구 사항이 충족 되는 경우 여러 비즈니스용 Skype 배포를 사용 하는 모든 조직에 대해 온-프레미스의 모든 사용자를 단일 Office 365 테 넌 트로 통합할 수 있습니다.

- Office 365 테 넌 트가 하나 이상 포함 되어 있어야 합니다. 두 개 이상의 Office 365 테 넌 트가 있는 시나리오의 통합은 지원 되지 않습니다.
- 언제 든 지 하이브리드 모드 (공유 SIP 주소 공간) 인 경우에는 온-프레미스 비즈니스용 Skype forest 하나만 사용할 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 온-프레미스에 유지 되어야 하며 서로 페더레이션 해야 합니다. 이러한 다른 온-프레미스 조직은 새 기능을 사용 하 여 12 월 2018 [온라인 SIP 도메인을 사용 하지 않도록 설정 하](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) 는 경우 AAD와 동기화 *할 수 있습니다* .

여러 포리스트에 비즈니스용 Skype를 배포 하는 고객은 공유 SIP 주소 공간 기능을 사용 하 여 단일 하이브리드 Skype for Business 포리스트의 모든 사용자를 Office 365 테 넌 트로 완전히 마이그레이션한 다음 하이브리드을 사용 하지 않도록 설정 해야 합니다. 온-프레미스 배포로 이동 하기 전에 비즈니스용 Skype 배포에 대해 다음에 시작 합니다. 클라우드로 마이그레이션 이전에는 온-프레미스 사용자는 동일한 사용자의 온-프레미스 디렉터리에 표시 되지 않은 사용자와 함께 페더레이션 상태로 유지 됩니다.  

## <a name="canonical-example-of-cloud-consolidation"></a>클라우드 통합의 정식 예제

Microsoft 팀 또는 비즈니스용 Skype Online에서 온라인으로 통합 하려는 비즈니스용 Skype에 대 한 별도의 페더레이션된 온-프레미스 배포를 사용 하는 조직을 고려해 보세요.


|원래 상태 정보 |원하는 상태 정보 |
|---------|---------|
|<ul><li>별도의 광고 포리스트에 2 개의 독립 비즈니스용 Skype 온-프레미스 배포<li>최대 1 개 포리스트는 비즈니스용 Skype Online을 하이브리드으로 합니다. <li> Orgs는 서로 연결 되어 있습니다. <li>이 포리스트 간에 사용자가 동기화 되지 않음<li> 조직에 Office 365 테 넌 트가 있고 해당 디렉터리를 Azure AD와 동기화 할 수 있습니다.</ul>|<ul> <li>1 개의 Office 365 테 넌 트<li>더 이상 온-프레미스 배포가 없으므로 아직 하이브리드가 남아 있지 않음<li>온-프레미스의 모든 사용자는 비즈니스용 Skype Online에 있으며, 선택적으로 팀 전용 사용자 일 수 있습니다. <li>어디서 나 비즈니스용 Skype에 대 한 온-프레미스 공간 없음 <li>사용자가 계속 온-프레미스 인증을 보유 하 고 있습니다.</ul> |

![두 개의 별도 페더레이션 온-프레미스 배포 통합](../media/cloudconsolidationfig1.png)  

원래 상태에서 원하는 종료 상태로 전환 하는 기본 단계는 다음과 같습니다.  일부 조직에서는 시작 지점이 이러한 단계의 중간에 위치 하 고 있다는 것을 알 수 있습니다. 이 문서의 뒷부분에 나오는 [다른 시작 지점을](#other-starting-points)참조 하세요. 마지막으로, 어떤 경우에는 필요에 따라 주문을 조정할 수 있습니다. [주요 제약 조건 및 제한](#limitations) 사항은 나중에 설명 합니다.

1.  아직 없는 경우 Office 365 테 넌 트를 가져옵니다.
2.  온-프레미스 배포의 모든 관련 SIP 도메인이 확인 된 Office 365 도메인 인지 확인 합니다.
3.  Office 365와 함께 사용할 수 있는 비즈니스용 Skype 배포를 선택 합니다. 이 예제에서는 OriginalCompany를 사용 합니다. <span>com.
4.  먼저 하이브리드 (OriginalCompany)이 될 [포리스트에 대해 AAD Connect를 사용 하도록 설정](configure-azure-ad-connect.md) 합니다.<span> com). 
5.  조직에 팀이 도입 되는 경우 [TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) 에 대 한 테 넌 트 전역 정책을 SfBWithTeamsCollab 또는 기타 SfB 모드 (SfBOnly 또는 SfBWithTeamsCollabAndMeetings) 중 하나로 설정 합니다. 이는 구내에 남아 있는 사용자 에게만 팀으로 이동 하는 사용자의 통화 및 채팅을 라우팅하는 데 매우 중요 합니다.
6.  다른 포리스트 (AcquiredCompany) [에 대 한 AAD 연결을 사용 하도록 설정](cloud-consolidation-aad-connect.md) 하는 것이 좋습니다 (아직 11 단계까지 필요 하지<span> 는 않음). com). 두 포리스트에서 AAD Connect를 사용 하도록 설정 하는 경우 org는 **[그림 A](#figure-a)** 와 같이 표시 되며,이는 일부 orgs에 대 한 일반적인 시작 지점이 될 수 있습니다. 
7.  다른 온-프레미스 배포에서 호스트 되는 모든 SIP 도메인 (이 경우 AcquiredCompany.<span> com) 인 경우 [이 SIP 도메인을 비즈니스용 Skype Online에서](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) PowerShell `Disable-CsOnlineSipDomain` 에서 사용 하지 않도록 설정 합니다. (이는 12 월 2018 새 기능입니다.)
8.  OriginalCompany에 대해 [비즈니스용 Skype 하이브리드을 구성](configure-federation-with-skype-for-business-online.md) 합니다. <span>com (온라인 SIP 도메인을 활성화 한 배포 인 경우)
9.  배포 (OriginalCompany.<span> com)에서 비즈니스용 [Skype Online의 사용자를 클라우드로 이동](move-users-between-on-premises-and-cloud.md) 하기 시작 합니다 (팀 전용 여부에 관계 없이). 이제 조직은 **[그림 B](#figure-b)** 와 같습니다. 그림 A의 주요 변경 사항은 다음과 같습니다.
    - 이제 온-프레미스 디렉터리의 사용자가 AAD에 있습니다.
    - AcquiredCompany. <span>com은 비활성화 된 온라인 SIP 도메인입니다.
    - 일부 사용자는 온라인으로 비즈니스용 Skype Online 또는 팀으로 이동 되었습니다. (자주색 사용자 A 참조)
10. 모든 사용자를 클라우드로 이동한 후에는 OriginalCompany에 대 한 [비즈니스용 Skype 온-프레미스 배포와 하이브리드를 사용 하지 않도록 설정](cloud-consolidation-disabling-hybrid.md) 합니다. <span>Office 365의 com:  
    - Office 365 테 넌 트에서 도메인 분할을 사용 하지 않도록 설정 합니다.
    - OriginalCompany에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다. <span>온-프레미스의 com.
    - OriginalCompany에 대 한 DNS 레코드를 업데이트 합니다. <span>Office 365를 가리키는 com입니다.
11. 아직 수행 하지 않은 경우 하이브리드 (AcquiredCompany)로 이동 하는 [다음 포리스트에 대해 AAD Connect를 사용 하도록 설정](cloud-consolidation-aad-connect.md) 합니다.<span> com). 이 시점에서 조직은 **[그림 C](#figure-c)** 와 같습니다. 이는 일부 조직의 경우에는 일반적으로 시작 되는 다른 출발점 일 수 있습니다. 
12. PowerShell에서 하이브리드, AcquiredCompany로 이동 하는 [다음 온-프레미스 배포에 대해 SIP 도메인을 사용 하도록 설정](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) 합니다. <span>com. 이 작업은 12 `Enable-CsOnlineSipDomain`월 2018으로 제공 되는 새로운 기능을 사용 하 여 수행 됩니다.
13. 폐쇄형 페더레이션을 사용 하는 경우에는 **동일한** Office 365에 허용 된 도메인으로 순수 온라인 테 넌 트의 모든 SIP 도메인 (microsoftonline.com을 제외한 모든)을 추가 해야 합니다. 변경 내용이 적용 되기까지 시간이 걸릴 수 있으며 일찍이 작업을 수행 하는 데는 나쁜 영향을 주지 않으므로 14 단계로 이동 하기 전에이 작업을 수행 하는 것이 좋습니다.
14. 온라인 테 넌 트에서 SIP 도메인을 수락 하도록 온-프레미스 환경을 업데이트 하 여 일치 시킵니다.
    - [모든 edge 인증서의 SAN](cloud-consolidation-edge-certificates.md) 을 이전과 동일한 값으로 업데이트 하 고,이 경우에는 기존 온라인 SIP 도메인의 값 (이 경우 microsoftonline.com)을 추가 합니다. <span>com.
    - OriginalCompany를 확인 합니다. <span>com은 온-프레미스 배포, AcquiredCompany에서 허용 되는 [도메인](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain) 입니다. 허용 된 도메인을 추가 합니다.
15. 온-프레미스 AcquiredCompany에서 비즈니스용 [Skype 하이브리드을 사용 하도록 설정](configure-federation-with-skype-for-business-online.md) 합니다. <span>com 및 클라우드.
16. 필요에 따라 온 [-프레미스에서 클라우드로 사용자를 마이그레이션합니다](move-users-between-on-premises-and-cloud.md). 사용자를 [팀 전용](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) 모드로 직접 마이그레이션하거나 비즈니스용 Skype Online으로 마이그레이션할 수 있습니다. 이 상태에서 조직은 **[그림 D](#figure-d)** 와 같습니다.
17. 모든 사용자가 마이그레이션된 후에는 온 [-프레미스 환경과 하이브리드을 사용 하지 않도록 설정](cloud-consolidation-disabling-hybrid.md) 하 여 *조직 순수 클라우드를 만듭니다*.

아래 다이어그램은이 프로세스 중 다양 한 주요 지점에 대 한 구성을 보여 줍니다.

##### <a name="figure-a"></a>그림 A:

- 두 조직이 AAD Connect를 통해 동기화 되므로 AAD는 온-프레미스 배포의 모든 사용자를 포함 합니다.
- 모든 사용자가 온-프레미스에 접속 했습니다.  
- 비즈니스용 Skype 하이브리드이 아직 구성 *되지* 않았습니다.
- 두 배포 중 하나에 속한 사용자가 팀을 사용 하는 경우에는 서로 페더레이션 (또는 모든 조직) 할 수 없으며, 어떠한 Skype 사용자와도 상호 운영성이 없습니다. 이 단계에서는 채널 전용 팀을 사용 하는 것이 좋습니다.<br><br>
    ![그림 A 다이어그램](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>그림 B:

- AcquiredCompany. <span>com은 [비활성화](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) 된 온라인 SIP 도메인입니다. 모든 사용자가 온-프레미스입니다. 팀을 사용 하는 경우 페더레이션 또는 상호 운영성이 없습니다. 이 단계에서는 채널 전용 팀을 사용 하는 것이 좋습니다.
- 온-프레미스 조직 중 하나에 비즈니스용 Skype 하이브리드을 사용 하도록 설정 했습니다.
- 하이브리드 조직의 일부 사용자가 클라우드 (자주색 음영으로 표시 된 사용자 A)로 옮겨졌습니다. 이러한 사용자는 비즈니스용 Skype Online 사용자 또는 팀에 게 완전 한 상호 운용성 및 페더레이션 지원이 있는 사용자만 있을 수 있습니다.<br><br>
    ![그림 B 다이어그램](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>그림 C:

- OriginalCompany의 모든 사용자. <span>com이 이제 클라우드 (비즈니스용 Skype Online에서 홈)에 있습니다. 팀만 있으면 되는 것이 좋습니다.
- OriginalCompany와의 비즈니스용 Skype 하이브리드 구성입니다. <span>com 배포를 사용 하지 않도록 설정 했습니다. 온-프레미스 배포는 사라졌습니다.
- AcquiredCompany. <span>이전에 COM이 AAD와 동기화 되지 않았으므로 여기서 계속 하려면 지금 동기화 해야 합니다. 그러나 아직 하이브리드 (공유 SIP 주소 공간)이 아니고 조직이 하이브리드로 이동할 준비가 될 때까지, 순수한 온-프레미스 조직의 온라인 SIP 도메인 (AcquiredCompany.com)을 사용 하지 않도록 설정 해야 하므로 온라인 팀에서 사용자와 통신할 수 있습니다. 온-프레미스 사용자.<br><br>
    ![그림 C 다이어그램](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>그림 D:

- AcquiredCompany. <span>이제 com을 온라인 SIP 도메인으로 사용할 수 있습니다.
- 온-프레미스가 OriginalCompany를 수락 하도록 업데이트 됩니다. <span>com. (허용 된 도메인 및 edge 인증서가 모두 업데이트 됩니다.)
- AcquiredCompany 간에 공유 SIP 주소 공간을 사용할 수 있습니다. <span>Com 및 Office 365 테 넌 트.
- 하이브리드 조직의 일부 사용자가 클라우드로 이동 했을 수 있습니다 (예: 자주색 음영으로 표시).<br><br>
    ![그림 D 다이어그램](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>다른 시작 지점

위의 정식 예제에 나와 있는 단계는 조직이 Office 365 현재 없이 두 개의 페더레이션 온 온-프레미스 배포로 시작 된다고 가정 합니다. 그러나 일부 조직에는 기존 Office 365의 공간이 있을 수 있으며 위의 순서로 다양 한 진입점이 있을 수 있습니다. 네 가지 일반적인 구성이 있습니다.

- Office 365 테 넌 트가 없는 여러 페더레이션 온-프레미스 조직 이 경우 1 단계부터 시작 합니다.
- 이미 여러 비즈니스용 Skype 포리스트를 단일 Azure AD 테 넌 트로 동기화 하는 여러 페더레이션 온-프레미스 조직 이러한 조직은 그림 A의 가상 조직과 비슷하지만 1-6 단계를 완료 하 여 7 단계에서 시작 해야 합니다.
- 하나 이상의 다른 순수한 온-프레미스 조직으로 federates 하는 하이브리드 조직이 며 AAD와 동기화 되지 않습니다. 이러한 조직은 아래와 같이 **그림 E**의 가상 조직과 비슷합니다.
    - 이 조직은 다음을 제외 하 고는 1-9 단계를 완료 한 그림 B와 비슷합니다.
        - 이 비 하이브리드 비즈니스용 Skype 배포는 아직 Azure AD와 동기화 *되지 않습니다* .
        -  온라인 SIP 도메인은 아직 사용할 수 없습니다. 
    - 이러한 조직은 다음 중 하나를 수행 해야 합니다.
        - 기존 하이브리드 조직의 마이그레이션을 완료 하 고 10 단계에서 위의 순서를 입력 합니다.  또는
        - 하이브리드 조직의 마이그레이션을 완료 하기 전에 다른 비즈니스용 Skype 포리스트를 AAD에 동기화 하는 것이 바람직 할 경우, 조직은 7 단계 (모든 온라인 SIP 도메인을 사용 하지 않도록 설정)를 수행 해야 합니다. AAD에 동기화 한 다음 AAD Connect를 사용 하도록 설정한 다음 10 단계를 계속 합니다 (원본 하이브리드 배포 역할 해제).       
                **그림 E**<br>
                ![그림 E 다이어그램](../media/cloudconsolidationfige.png)
- 별도의 온-프레미스 비즈니스용 Skype 조직을 federates 하는 비즈니스용 Skype Online 조직 (팀을 사용 하지 않을 수 있음)입니다. 이 조직이 온-프레미스 조직에 대 한 온라인 SIP 도메인을 사용 하지 않도록 설정 하 고 온-프레미스 비즈니스용 Skype 조 직에 대 한 AAD Connect를 사용 하도록 설정 하는 경우 **[그림 C](#figure-c)** 의 단계를 완료 한 가상 조직과 비슷합니다. 1-11.

## <a name="limitations"></a>따릅니다

- Office 365 테 넌 트가 하나 이상 포함 되어 있어야 합니다. 두 개 이상의 Office 365 테 넌 트가 있는 시나리오의 통합은 지원 되지 않습니다.
- 하이브리드 모드 (공유 SIP 주소 공간)에는 한 번에 한 온-프레미스 비즈니스용 Skype 포리스트만 사용할 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트에는 전적으로 온-프레미스 상태로 유지 되어야 하며 서로 페더레이션 하 고 Office 365 테 넌 트에 연결 해야 합니다.
- 클라우드로 마이그레이션 전에, 온라인의 모든 사용자가 온-프레미스로 표시 되지 않으므로이 배포의 사용자에 게 비대칭 환경이 있습니다.
    - 환경은 다음과 같이 합산 될 수 있습니다.
        - 사용자 홈 온라인은 사용자가 혼성 인 것 처럼 하이브리드 환경에서 온-프레미스 사용자와 상호 작용 합니다.
        - 하이브리드 배포의 온-프레미스 사용자는 온-프레미스 디렉터리로 표시 되는 온라인 사용자와 상호 작용 합니다. 
        - 하이브리드 배포의 온-프레미스 사용자는 페더레이션된로 온-프레미스 광고에 표시 되지 않는 온라인 사용자와 상호 작용 합니다.
    - **[그림 D](#figure-d)** 위의 AcquiredCompany에서 user E는 온-프레미스입니다. <span>com.  사용자 E는 표준 하이브리드 환경을 사용 하 여 사용자 D (홈 online)와 상호 작용 하지만 사용자 A는 온-프레미스 디렉터리에 표시 되지 않으므로 사용자 A, B, C에는 페더레이션 환경이 있습니다. 그러나 사용자 A, B, C는 사용자가 하이브리드 인 것 처럼 사용자 E와 상호 작용 합니다.
    - 하이브리드과 페더레이션 비교의 의미:
        - 사용자가 연락처로 표시 되지 않는 한 페더레이션 사용자는 현재 상태가 자동으로 구독 되지 않습니다.
        - 페더레이션 도메인 간에는 착신 전환을 사용할 수 없습니다.
        - 통화 전달 시나리오가 더 제한 됩니다.
        - 페더레이션 트래픽에 제한을 적용할 수 있습니다.
- 이러한 비대칭 경험에서 온-프레미스 사용자와 온-프레미스 디렉터리에 없는 클라우드 사용자 간 상호 프레미스 시나리오의 호출 기능에 대 한 공식적인 지원은 피어 투 피어 전용으로 제한 됩니다. 
    - 이러한 사용자 간의 착신 전환, 전송, 통화 대기열 등은 지원 되지 않습니다.
    - 이와 같이 지원 되지 않는 호출 시나리오는 계속 사용할 수 있지만, 대부분의 경우 예기치 않은 방식으로 오류가 발생 하 게 됩니다. 
    - **[그림 D](#figure-d)** 위의 사용자 E는 온-프레미스이 고 사용자 A, B 또는 C와의 통화는 피어로만 지원 됩니다. (사용자 D와의 통화에는 지원 제한이 없습니다.)  그러나 온-프레미스 사용자 E를 클라우드로 이동한 후에는이 제한이 더 이상 적용 되지 않습니다.
- 환경에 비즈니스용 Skype 서버 2019의 배포를 두 개 이상 사용 하는 경우, 해당 기능에 비즈니스용 Skype Server 하이브리드 구성이 필요 하기 때문에 해당 배포의 유일한 구성은 조직 자동 전화 교환을 사용 하도록 구성 될 수 있습니다. 
- 이전 단계의 일부 순서를 조정할 수 있습니다. 충족 해야 하는 주요 요구 사항은 다음이 모두 참일 경우입니다.
    - 하나 이상의 온-프레미스 비즈니스용 Skype 포리스트가 단일 AAD 테 넌 트로 동기화 됩니다.
    - 한 온-프레미스 포리스트를 사용 하 여 도메인 분할을 사용할 수 있음
    - 하이브리드 조직의 사용자 중 한 명 이상이 클라우드로 마이그레이션 되었습니다.<br>   그런 다음 다른 모든 온라인 SIP 도메인을 비즈니스용 온-프레미스 비즈니스용 Skype 포리스트에서 사용 하지 않도록 설정 *해야 합니다* . 그렇지 않으면 하이브리드 조직의 온라인 사용자와 다른 조직의 온-프레미스 사용자 간 페더레이션이 한 방향으로 중단 됩니다.

## <a name="implications"></a>함축

- 위에서 설명한 대로 고급 통화 기능을 지원 하기 때문에 **조직은 마이그레이션의 일부로 이러한 비대칭 상태를 일시적으로 처리 하 고 일정 한 상태로 전환 하지 않아야 합니다**.  
- 여러 개의 온-프레미스 비즈니스용 Skype 배포를 사용 하는 조직은 일반적으로 클라우드로 완전히 마이그레이션할 수 있는 배포로 시작 해야 통합을 계속할 수 있습니다. 어떤 경우에는 아직 팀으로 이동할 수 없는 특정 사용자 그룹이 holdouts 것을 이해 하 고 있는 것입니다. 이는 비즈니스용 Skype 포리스트가 포함 된 시나리오에서 고려해 야 할 경우 가능 하면 이러한 제한이 없는 다른 포리스트로 마이그레이션을 시작 합니다.
- 온-프레미스에서 클라우드로 이동 하는 경우 위임 관계 및/또는 일반적으로 착신 전환 시나리오와 관련 된 사용자를 하나의 단위로 함께 이동 해야 합니다.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>팀 전용 모드로 전환 하기 위한 고려 사항

하이브리드 환경에서 사용자를 온-프레미스에서 클라우드로 이동 하면이를 비즈니스용 Skype 전용 또는 팀 전용 모드로 이동할 수 있습니다. *사용자를 팀 전용 모드로 이동 하려는 경우 먼저이 섹션을 읽어야 합니다.*

- 팀 전용 모드를 사용자에 게 할당 하면 다른 사용자의 모든 채팅 및 통화가 해당 사용자의 팀 클라이언트에 배치 됩니다. 
- 팀을 위해 Skype를 사용 하는 사용자와 다른 사용자 간의 채팅 및 통화의 원활한 라우팅이 가능 하 고, 온-프레미스 사용자가 아일랜드 대신 SfB 모드 중 하나를 사용 하 여 TeamsUpgradePolicy를 보장 해야 합니다 (기본값). ). 
    - 이렇게 하려면 *먼저 TeamsUpgradePolicy의 테 넌 트의 전역 인스턴스를 다음 값 중 하나로 설정 해야 합니다*.
        - SfBWithTeamsCollab (권장)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 다음 명령을 사용 하 여 테 넌 트 전역 정책을 부여할 수 있습니다.<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 참고: 온라인 디렉터리에 SIP 주소가 없는 개별 사용자에 게는 정책을 할당할 수 없기 때문에 현재이 작업을 테 넌 트 차원의 수준에서 수행 해야 합니다. 순수 온-프레미스 배포에 대해 온라인 SIP 도메인을 사용 하지 않도록 설정한 경우 해당 도메인의 사용자는 온라인 디렉터리에 대 한 SIP 주소를 디자인에 따라 표시 하지 않습니다. 따라서 해당 온-프레미스 사용자에 게 정책을 적용 하는 유일한 방법은 테 넌 트 수준에서 할당 하는 것입니다. 반대로, 하이브리드 배포의 경우 사용자가 테 넌 트 전역 정책과는 다른 값을 원하는 경우 정책을 명시적으로 할당할 수 있도록 온라인 디렉터리에 SIP 주소가 있습니다.
- 팀 클라이언트 UX는 아직 TeamsUpgradePolicy의 SfB 모드를 준수 하지 않습니다. 예를 들어 이러한 모드에서는 향후에도 팀의 통화 및 채팅 시작이 가능 하지만, 나중에는 그렇지 않습니다. 이로 인해, 상황에 따라 회신이 팀 이나 때때로 비즈니스용 Skype에 있을 수 있으므로 사용자 간에 혼란이 발생할 수 있습니다. 아직 구내에 있는 사용자를 위해 팀과 채팅을 별도로 사용 하지 않도록 설정 하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

[Edge 인증서 업데이트](cloud-consolidation-edge-certificates.md)

[둘 이상의 포리스트를 포함 하도록 AAD Connect 업데이트](cloud-consolidation-aad-connect.md)

[클라우드로 마이그레이션을 완료 하기 위해 하이브리드을 사용 하지 않도록 설정](cloud-consolidation-disabling-hybrid.md)
