---
title: 비즈니스 및 Teams 클라우드 비즈니스용 Skype
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 문서에서는 UC 워크로드를 UC 작업으로 이동하기 위해 이동하는 비즈니스용 Skype(또는 Lync)의 온-프레미스 배포가 있는 조직을 위해 이러한 통합을 달성하는 Teams.
ms.openlocfilehash: 268f9a7a35e53a514dda63c304c7a58e252004d3edf74d1342f4934ec4185aab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277463"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Teams과 비즈니스용 Skype를 위한 클라우드 통합

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


많은 대기업에는 온-프레미스 AD 포리스트가 여러 개 있고, 경우에 따라 고객은 둘 이상의 Exchange 및/또는 비즈니스용 Skype 서버(또는 Lync Server) 배포가 있을 수 있습니다. 또한 온-프레미스 포리스트 하나만 있는 조직에서도 비즈니스 합병 또는 인수를 통해 유사한 상황에 처할 수 있습니다. 이러한 고객은 클라우드로 전환할 때 주어진 사내 워크로드의 여러 인스턴스를 단일 클라우드 조직으로 Microsoft 365 합니다. 이 문서에서는 조직을 전체적으로 비즈니스용 Skype(또는 Lync)의 여러 온-프레미스 배포가 있는 조직(모든 Microsoft Teams 전용)을 Teams 방법을 설명합니다.

지금까지는 이러한 상황에 처한 고객은 온-프레미스 배포를 먼저 통합한 다음 클라우드로 이동해야 했습니다. 이 문서에서는 여전히 옵션인 동시에 여러 비즈니스용 Skype 배포를 사용하는 조직이 한 번의 배포를 한 Microsoft 365 조직으로 마이그레이션할 수 있도록 하는 솔루션에 대해 설명합니다. 단일 Microsoft Teams 조직에서 하이브리드 모드에서 여러 비즈니스용 Skype Lync Server 포리스트를 지원하지 Microsoft 365 않습니다. 

> [!Important]
> 이 가이드를 구성하기 전에 제한 사항을 [](#limitations)검토하고 이해해야 합니다. 제한 사항이 조직에 영향을 줄 수 있습니다.

## <a name="overview-of-cloud-consolidation"></a>클라우드 통합 개요

다음 주요 요구 사항이 충족되는 경우 여러 비즈니스용 Skype 배포를 사용하는 모든 조직에 대해 단일 Microsoft 365 조직의 모든 사용자를 클라우드로 통합할 수 있습니다.

- 조직에 관련된 조직은 Microsoft 365 있어야 합니다. 조직이 두 개 이상인 시나리오에서는 통합이 지원되지 않습니다.
- 언제든지 하나의 온-프레미스 비즈니스용 Skype 포리스트만 하이브리드 모드(공유 SIP 주소 공간)에 있을 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 온-프레미스로 유지되어야(아마도 서로 연결되어) 합니다. 이러한 다른 사내 *조직은* 온라인 SIP 도메인을 사용하지 않도록 설정하는 경우 원하는 경우 Azure AD에 [동기화할 수 있습니다.](/powershell/module/skype/disable-csonlinesipdomain)

여러 포리스트에 비즈니스용 Skype 배포하는 고객은 공유 SIP 주소 공간 기능을 사용하여 단일 하이브리드 비즈니스용 Skype 포리스트의 모든 사용자를 개별적으로 Microsoft 365 조직으로 완전히 마이그레이션한 다음, 다음 온-프레미스 비즈니스용 Skype 배포를 마이그레이션하기 전에 해당 온-프레미스 배포와 하이브리드를 사용하지 않도록 설정해야 합니다. 클라우드로 마이그레이션하기 전에 온-프레미스 사용자는 동일한 사용자의 온-프레미스 디렉터리에 표시되지 않는 사용자와 페더레이션 상태로 유지됩니다.  

## <a name="canonical-example-of-cloud-consolidation"></a>클라우드 통합의 정형 예

조직에서 온라인에서 통합하려는 두 개의 별도 비즈니스용 Skype 배포가 있는 Microsoft Teams.


|원래 상태 세부 정보 |원하는 상태 세부 정보 |
|---------|---------|
|<ul><li>2개의 비즈니스용 Skype AD 포리스트에 있는 독립적인 프레미스 배포<li>포리스트가 1개까지 하이브리드에 Teams <li> Orgs가 서로 페더더러 <li>사용자가 이러한 포리스트에서 동기화되지 않습니다.<li> 조직에 조직이 Microsoft 365 Azure AD에 디렉터리를 동기화할 수 있습니다.</ul>|<ul> <li>조직 Microsoft 365 1개<li>더 이상 사내 배포가 아니기 때문에 하이브리드가 남지 않습니다.<li>모든 사용자가 프레미스에서 Teams 모드로 이동했습니다. <li>어디에서도 사용할 수 있는 비즈니스용 Skype 서버 공간 없음 <li>사용자가 여전히 사내 인증을 사용 중입니다.</ul> |

![두 개의 개별 페더링된 사내 배포 통합](../media/cloudconsolidationfig1.png)  

원래 상태부터 원하는 종료 상태로의 기본 단계는 아래와 같습니다.  일부 조직에서는 시작 지점이 이러한 단계의 중간에 있을 수 있습니다. 이 [문서 의](#other-starting-points)나중에 다른 시작 지점을 참조하세요. 마지막으로 필요한 경우 순서를 조정할 수 있는 경우도 있습니다. [주요 제약 조건 및 제한에 대한](#limitations) 설명은 나중에 설명되어 있습니다.

1.  아직 Microsoft 365 없는 조직을 얻습니다.
2.  두 배포의 모든 관련 SIP 도메인이 도메인에 대해 확인된 Microsoft 365 합니다.
3.  하이브리드 비즈니스용 Skype 배포를 선택할 수 Microsoft 365. 이 예제에서는 OriginalCompany를 사용하게 될 것입니다. <span> com.
4.  [먼저 커넥트 포리스트에 대해 AAD](configure-azure-ad-connect.md) 설정을 사용하도록 설정(OriginalCompany). <span> com) 
5.  [TeamsUpgradePolicy에](/powershell/module/skype/grant-csteamsupgradepolicy) 대한 테넌트 전체 정책을 SfBWithTeamsCollab 또는 다른 SfB 모드 중 하나(SfBOnly 또는 SfBWithTeamsCollabAndMeetings)로 설정 이는 프레미스에 남아 있는 사용자에게만 통화 및 채팅을 Teams 중요합니다.
6.  이 시점에서 다른 포리스트(AcquiredCompany)에 대해 [AAD](cloud-consolidation-aad-connect.md) 커넥트 사용하도록 설정하는 것이 좋습니다(11단계까지는 필요하지 않음). <span> com) AAD 커넥트 두 포리스트에서 사용하도록 설정되어 있는 경우, 이러한 설정은 그림 **[A와](#figure-a)** 같이 표시됩니다. 이 점은 일부조지의 일반적인 시작 지점일 수 있습니다. 
7.  다른 사내 배포에서 호스팅하는 모든 SIP 도메인의 경우(이 경우 AcquiredCompany). <span> com) Microsoft 365 PowerShell 모듈에서 이러한 온라인 [SIP](/powershell/module/skype/disable-csonlinesipdomain) 도메인을 Teams `Disable-CsOnlineSipDomain` 비활성화합니다. 
8.  [OriginalCompany에 비즈니스용 Skype 하이브리드를](configure-federation-with-skype-for-business-online.md) 구성합니다. <span> com(온라인 SIP 도메인을 사용하도록 설정한 하나의 배포).
9.  하이브리드 배포(OriginalCompany) <span> com), [사용자가](move-users-between-on-premises-and-cloud.md) 비즈니스용 Skype 수 있도록 비즈니스용 Skype 클라우드로 사용자를 이동하기 시작(Teams 전용인지 여부는 Teams). 이제 조직은 그림 **[B처럼 보입니다.](#figure-b)** 그림 A에서 변경된 주요 사항은 다음입니다.
    - 이제 두 가지 모두에 있는 사용자가 AAD에 있습니다.
    - AcquiredCompany. <span> com은 사용하지 않도록 설정된 온라인 SIP 도메인입니다.
    - 일부 사용자는 온라인에서 사용자만 Teams 이동했습니다. 자주색 사용자 A를 참조합니다.
10. 모든 사용자를 클라우드로 이동한 [](cloud-consolidation-disabling-hybrid.md) 후 OriginalCompany에 대한 비즈니스용 Skype 하이브리드를 사용하지 않도록 설정하십시오. <span> com from Microsoft 365:  
    - 조직에서 분할 도메인을 Microsoft 365 않습니다.
    - OriginalCompany에서 사용자와 통신하는 Microsoft 365 비활성화합니다. <span> com on-premises.
    - OriginalCompany에 대한 DNS 레코드를 업데이트합니다. <span> com을 Microsoft 365.
11. 아직 수행하지 않은 경우 하이브리드로 전환할 커넥트 [포리스트에 대해 AAD](cloud-consolidation-aad-connect.md) 응용 커넥트(AcquiredCompany)를 사용하도록 설정합니다. <span> com) 이때 조직은 그림 **[C와 같이 됩니다.](#figure-c)** 이는 일부 조직에서 일반적인 시작 지점이 될 수 있습니다. 
12. PowerShell을 Teams 하이브리드가 될 다음 사내 배포인 AcquiredCompany에 [대해 SIP](/powershell/module/skype/enable-csonlinesipdomain) 도메인을 사용하도록 설정하십시오. <span> com. 이는 2018년 12월부터 사용할 수 있는 새로운 `Enable-CsOnlineSipDomain` 기능인 을 사용하여 수행됩니다.
13. 닫힌 페더링을 사용하는 경우 순수 온라인 테넌트의 모든 SIP 도메인(.microsoftonline.com 제외)을 동일한 도메인에 허용된 \* 도메인으로 추가해야  Microsoft 365. 변경이 적용되기까지 다소 시간이 걸릴 수 있으며 초기에 이 작업을 수행하면 손상되지 않습니다. 따라서 14단계로 이동하기 전에 이 작업을 잘 수행해보는 것이 좋습니다.
14. 온라인 테넌트의 모든 SIP 도메인을 수락하여 일치하게 하여 사내 환경을 업데이트합니다.
    - 모든 에지 인증서의 [SAN을](cloud-consolidation-edge-certificates.md) 이전과 동일한 값과 기존 온라인 SIP 도메인(*.microsoftonline.com 제외)에 대한 값(이 경우 Sip.OriginalCompany)으로 업데이트합니다. <span> com.
    - OriginalCompany를 선택해야 합니다. <span> com은 [사내](/powershell/module/skype/new-csalloweddomain) 배포의 허용 도메인인 AcquiredCompany입니다. 허용 도메인을 추가합니다.
15. [하이브리드 비즈니스용 Skype 하이브리드를](configure-federation-with-skype-for-business-online.md) 사용하도록 설정하려면 AcquiredCompany를 사용하도록 설정해야 합니다. <span> com 및 클라우드.
16. 원하는 경우 [사용자를](move-users-between-on-premises-and-cloud.md) 클라우드로 마이그레이션하여 TeamsOnly 사용자로 [마이그레이션합니다.](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) 이 상태의 경우 조직은 그림 **[D와 같이 됩니다.](#figure-d)**
17. 모든 사용자가 마이그레이션된 후 [조직을](cloud-consolidation-disabling-hybrid.md) 순수 클라우드로 만들기 위해 하이브리드를 사내 환경과 *함께 사용하지 않도록 설정하세요!*

아래 다이어그램은 이 프로세스 중 다양한 주요 지점에서 구성을 보여 주며,

##### <a name="figure-a"></a>그림 A:

- 두 조직은 AAD 커넥트 동기화하기 때문에 이제 AAD에는 두 가지 모두의 모든 사용자가 있습니다.
- 사내에 있는 모든 사용자입니다.  
- 비즈니스 하이브리드용 Skype *구성되지* 않았습니다.
- 두 배포의 사용자가 Teams 사용하는 경우 서로(또는 어떤 조직과도) 페더러티할 수 없으며 모든 사용자와의 상호 비즈니스용 Skype 없습니다. 이 단계에서는 채널에만 Teams 사용하는 것이 좋습니다.<br><br>
    ![그림 다이어그램](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>그림 B:

- AcquiredCompany. <span> com은 [사용하지 않도록 설정된](/powershell/module/skype/disable-csonlinesipdomain) 온라인 SIP 도메인입니다. 모든 사용자가 사내에 있습니다. 이러한 사용자가 Teams 또는 상호운용성이 없습니다. 이 단계에서는 채널에만 Teams 사용하는 것이 좋습니다.
- 비즈니스 하이브리드용 Skype 조직 중 하나에 대해 사용하도록 설정되어 있습니다.
- 하이브리드 조직의 일부 사용자는 클라우드로 이동되어 Teams(보라색 음영으로 표시된 사용자 A)입니다. 이러한 Teams 사용자만 다른 모든 사용자와의 모든 상호 비즈니스용 Skype 지원할 수 있습니다.<br><br>
    ![그림 B 다이어그램](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>그림 C:

- OriginalCompany의 모든 사용자입니다. <span> com은 이제 Teams 전용 모드로 설정됩니다. 
- 비즈니스용 Skype 하이브리드 구성을 구성할 수 있습니다. <span> com 배포가 사용하지 않도록 설정되어 있습니다. 사내 배포가 사라졌습니다.
- AcquiredCompany인 경우 <span> com이 이전에 AAD와 동기화되지 않은 경우 여기에서 계속 동기화해야 합니다. 그러나 아직 하이브리드(공유 SIP 주소 공간)가 아니며 조직이 하이브리드로 이동할 준비가 될 때까지는 온라인 사용자와 통신할 수 있도록 순수 AcquiredCompany.com(AcquiredCompany.com)에 대한 온라인 SIP 도메인을 사용하지 않도록 설정해야 Teams 수 있습니다.<br><br>
    ![그림 C 다이어그램](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>그림 D:

- AcquiredCompany. <span> 이제 com이 온라인 SIP 도메인으로 사용하도록 설정됩니다.
- On-premises is updated to accept OriginalCompany. <span> com. 허용 도메인과 에지 인증서가 모두 업데이트됩니다.
- AcquiredCompany 간에 공유 SIP 주소 공간을 사용할 수 있습니다. <span> com 및 Microsoft 365.
- 하이브리드 조직의 일부 사용자는 아래 사용자 D(보라색 음영으로 표시)처럼 클라우드로 이동된 것일 수 있습니다.<br><br>
    ![그림 D 다이어그램](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>기타 시작점

위 정식 예제의 단계에서는 조직이 현재 상태와는 별개인 두 개의 페더임-프레미스 배포로 Microsoft 365 가정합니다. 그러나 일부 조직에는 기존 설치 Microsoft 365 수 있으며 위의 순서에 서로 다른 진입점이 있을 수 있습니다. 일반적인 구성은 네 가지입니다.

- 조직에 조직이 없는 여러 개의 페더 Microsoft 365. 이 경우 1단계에서 시작합니다.
- 여러 개의 비즈니스용 Skype 포리스트를 단일 Azure AD 테넌트에 이미 동기화하고 있는 여러 페더링된 사내 조직 이러한 조직은 그림 A의 가상 조직과 같이 1~6단계를 완료하고 7단계에서 시작해야 합니다.
- AAD와 동기화되지는 않습니다. 이러한 조직은 아래 표시된 **그림 E의** 가상 조직과 같습니다.
    - 이 조직은 다음을 제외하고 1~9단계를 완료한 그림 B와 비슷합니다.
        - 하이브리드가 아닌 비즈니스용 Skype *배포는* 아직 Azure AD와 동기화되지 않습니다.
        -  온라인 SIP 도메인은 아직 사용하지 않도록 설정되지 않았습니다. 
    - 이러한 조직은 다음 중 하나를 해야 합니다.
        - 기존 하이브리드 조직의 마이그레이션을 완료하고 10단계에서 위의 순서를 입력합니다.  OR,
        - 하이브리드 조직의 마이그레이션을 완료하기 전에 다른 비즈니스용 Skype 포리스트를 AAD에 동기화하려는 경우 조직은 7단계를 수행(AAD와 동기화할 다른 모든 비즈니스용 Skype 배포의 모든 온라인 SIP 도메인을 사용하지 않도록 설정)한 다음 AAD 커넥트 10단계(원래 하이브리드 배포 해제)를 계속해야 합니다.       
                **그림 E**<br>
                ![그림 E 다이어그램](../media/cloudconsolidationfige.png)
- 순수 Teams 별도의 Teams 조직과 페더더인 조직만 비즈니스용 Skype. 이 조직이온-프레미스 조직에 대해 온라인 SIP 도메인을 사용하지 않도록 설정하고 커넥트 비즈니스용 Skype 조직에 대해 AAD 도메인을 활성화하면 1-11단계를 완료한 그림 **[C에](#figure-c)** 표시된 가상의 조직과 같이 표시됩니다.

## <a name="limitations"></a>제한 사항

- 조직에 관련된 조직은 Microsoft 365 있어야 합니다. 조직이 두 개 이상인 시나리오에서는 통합이 지원되지 않습니다.
- 포리스트가 한 비즈니스용 Skype 모드(공유 SIP 주소 공간)에 있을 수 있습니다. 다른 모든 비즈니스용 Skype 포리스트는 전적으로 사내에 유지되어야 하며 서로 및 조직과 페더 Microsoft 365 합니다.
- 클라우드로 마이그레이션하기 전에는 이 배포의 사용자에 대한 비대칭 환경이 있습니다. 온라인의 모든 사용자가 사내에 표현되지는 않습니다.
    - 환경은 다음과 같이 요약될 수 있습니다.
        - 온라인에 있는 모든 사용자는 사용자가 하이브리드인 경우처럼 하이브리드 환경의 모든 사용자와 상호 작용합니다.
        - 하이브리드 배포의 On-premises users will interact with online users who are represented in their on-premises directory as if they were hybrid. 
        - 하이브리드 배포의 On-premises users will interact with online users who are not represented in on-premises AD as federated.
    - 위의 **[그림 D에서](#figure-d)** 사용자 E는 AcquiredCompany의 On-premises입니다. <span> com.  사용자 E는 표준 하이브리드 환경을 사용하여 사용자 D(온라인에 있는)와 상호 작용하지만, 사용자 E는 사용자 A, B 및 C와의 페더전된 환경을 경험하게 됩니다. 이는 사용자가온-프레미스 디렉터리에 나타내지 않습니다. 그러나 사용자 A, B 및 C는 사용자가 하이브리드에 있는 경우처럼 사용자 E와 상호 작용합니다.
    - 상호 작용이 하이브리드와 페더에 대한 의미를 비교합니다.
        - 사용자가 연락처로 표시되어 있지 않은 경우 페더니언트 사용자에 대해 현재 상태는 자동으로 구독되지 않습니다.
        - 페더링된 도메인 간에는 전달이 작동하지 않습니다.
        - 통화 전송 시나리오가 더 제한됩니다.
        - 페더링 트래픽에 스로틀을 적용할 수 있습니다.
- 이러한 비대칭 환경이 제공될 경우, 사내 사용자와 사내 디렉터리에 없는 클라우드 사용자 간의 크로스-프레미스 시나리오의 통화 기능에 대한 공식적인 지원은 피어 투 피어 전용으로 제한됩니다. 
    - 이러한 사용자 간의 통화 전달, 전송, 통화 큐 등은 지원되지 않습니다.
    - 이러한 지원되지 않는 호출 시나리오는 여전히 사용하도록 설정되어 있지만 대부분의 경우 예측할 수 없는 방식으로 실패합니다. 
    - 위의 **[그림 D에서는](#figure-d)** 사용자 E가 사내에 있으며, 사용자 A, B 또는 C와의 통화는 피어 투 피어로만 지원됩니다. 사용자 D가 있는 통화에는 지원 제한이 없습니다.  그러나 사내 사용자 E가 클라우드로 이동된 후 이 제한은 더 이상 적용되지 않습니다.
- 환경에 비즈니스용 Skype 서버 2019를 두 개 이상 배포하는 경우 조직 구성을 사용하도록 이러한 배포 중 1개만 구성할 수 자동 전화 교환 해당 기능에는 하이브리드 구성이 비즈니스용 Skype 서버 있습니다. 
- 이전 단계 중 일부의 순서를 조정할 수 있습니다. 충족해야 하는 주요 요구 사항은 이러한 모든 요구 사항이 충족될 경우 다음을 충족하는 것입니다.
    - Azure AD의 단일 비즈니스용 Skype 테넌트와 동기화하는 포리스트에 Microsoft 365 포리스트가 두 개 이상 있습니다.
    - 하나의 사내 포리스트에서 분할 도메인을 사용하도록 설정
    - 하이브리드 조직의 사용자 한 명 이상이 클라우드로 마이그레이션된 경우<br>   그런 다음 다른 *모든* 온라인 SIP 도메인의 다른 모든 온라인 SIP 도메인을 포리스트의 다른 모든 비즈니스용 Skype 합니다. 그렇지 않으면 하이브리드 조직의 온라인 사용자와 다른 조직의 온라인 사용자 간의 페더임이 한 방향으로 중단됩니다.

## <a name="implications"></a>의미

- 위에서 설명한 대로 고급 통화 기능에 대한 지원에는 제한이 있기 때문에 조직에서는 이러한 비대칭 상태를 마이그레이션의 일부로 처리하고 이를 꾸준한 상태로 진행하지 **말아야 합니다.**  
- 여러 온-프레미스 비즈니스용 Skype 조직은 통합을 계속할 수 있도록 클라우드로 완전히 마이그레이션할 수 있는 배포로 시작해야 합니다. 경우에 따라 특정 사용자 그룹으로 이동하기가 아직 가능하지 않은 특정 사용자 그룹의 보류가 Teams. 여러 비즈니스용 Skype 포리스트가 관련된 시나리오에서 이 고려 사항이 고려되는 경우 가능한 경우 이러한 제한이 없는 다른 포리스트로 마이그레이션을 시작하십시오.
- 사내에서 클라우드로 이동할 때 위임 관계가 있으며/또는 일반적으로 통화 전달 시나리오에 관련된 사용자는 한 단위로 함께 이동해야 합니다.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>TeamsOnly 모드로 이동하기 위한 고려 사항

하이브리드 환경에서 사용자를 사내에서 클라우드로 이동하면 이러한 사용자는 사용자만 Teams 됩니다.

- 사용자에게 TeamsOnly 모드를 할당하면 다른 사용자의 모든 채팅 및 통화가 해당 사용자의 Teams 클라이언트에 연결됩니다. 
- 비즈니스용 Skype 사용자가 주로 비즈니스용 Skype 클라이언트가 아닌 Teams 클라이언트를 사용하는 경우, 해당 프레미스 사용자에 대한 라우팅이 항상 비즈니스용 Skype 대신 Teams. TeamsOnly인 사용자와 여전히 비즈니스용 Skype 프레미스를 사용하는 사용자 간에 채팅 및 통화의 적절한 라우팅을 보장하려면, 사내 사용자는 아일랜드(기본값)가 아니라 SfB 모드 중 하나를 사용하여 TeamsUpgradePolicy의 유효 값을 가중치로 설정해야 합니다. 
    - 이렇게하려면 먼저 *테넌트의 TeamsUpgradePolicy* 전역 인스턴스를 다음 값 중 하나로 설정해야 합니다.
        - SfBWithTeamsCollab(권장)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 다음 명령을 사용하여 테넌트 전체 정책을 부여할 수 있습니다.<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 참고: 온라인 디렉터리에 SIP 주소가 없는 개별 사용자에게 정책을 할당할 수 없는 경우 테넌트 전체 수준에서 이 작업을 해야 합니다. 순수온-프레미스 배포에 대해 온라인 SIP 도메인을 사용하지 않도록 설정한 경우 해당 도메인의 사용자에게는 온라인 디렉터리의 SIP 주소가 디자인에 따라 사용되지 않습니다. 따라서 이러한 사내 사용자에게 정책을 적용하는 유일한 방법은 테넌트 수준에서 할당하는 것입니다. 반면, 하이브리드 배포 사용자는 온라인 디렉터리에 SIP 주소가 있으므로 테넌트 글로벌 정책과 다른 값을 원하는 경우 정책을 명시적으로 할당할 수 있습니다.

## <a name="see-also"></a>참고 항목

[에지 인증서 업데이트](cloud-consolidation-edge-certificates.md)

[여러 포리스트를 포함하도록 AAD Connect를 업데이트](cloud-consolidation-aad-connect.md)

[클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화](cloud-consolidation-disabling-hybrid.md)
