---
title: Teams 및 비즈니스용 Skype를 위한 클라우드 통합
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
description: 이 문서에서는 UC 워크로드를 Teams 및/또는 비즈니스용 Skype Online으로 이동하기 위해 이동하고자 하는 비즈니스용 Skype(또는 Lync)의 온-프레미스 배포가 있는 조직을 위해 통합하는 방법을 설명합니다.
ms.openlocfilehash: d2733ffacf8b56a5cfe4217553f533950eb82e36
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221492"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Teams과 비즈니스용 Skype를 위한 클라우드 통합

많은 대기업에는 온-프레미스 AD 포리스트가 여러 개 있고, 경우에 따라 고객은 둘 이상의 Exchange 및/또는 비즈니스용 Skype 서버(또는 Lync Server) 배포가 있을 수 있습니다. 또한 온-프레미스 포리스트 하나만 있는 조직에서도 비즈니스 합병 또는 인수를 통해 유사한 상황에 처할 수 있습니다. 이러한 고객은 클라우드로 이동하는 경우, 주어진 On-premises 워크로드의 여러 인스턴스를 단일 Microsoft 365 또는 Office 365 조직으로 클라우드에 통합하기를 원합니다. 이 문서에서는 UC 워크로드를 Microsoft 클라우드(예: Microsoft Teams 및/또는 비즈니스용 Skype Online)로 이동하려는 비즈니스용 Skype(또는 Lync)의 여러 온-프레미스 배포가 있는 조직을 위해 통합하는 방법을 설명합니다.

지금까지는 이러한 상황에 처한 고객은 온-프레미스 배포를 먼저 통합한 다음 클라우드로 이동해야 했습니다. 이 문서에서는 여전히 옵션이지만, 이 문서에서는 여러 비즈니스용 Skype 배포를 사용하는 조직이 한 시기에 하나의 배포를 단일 Microsoft 365 또는 Office 365 조직으로 마이그레이션할 수 있도록 하는 새로운 기능을 기반으로 하는 솔루션에 대해 설명합니다. 이 새로운 기능을 사용하는 경우에도 비즈니스용 Skype Online 및 Microsoft Teams는 단일 Microsoft 365 또는 Office 365 조직을 사용하는 하이브리드 모드에서 여러 비즈니스용 Skype/Lync 포리스트를 지원하지 않습니다. 

> [!Important]
> 이 가이드를 구성하기 전에 제한 사항을 [](#limitations)검토하고 이해해야 합니다. 제한 사항이 조직에 영향을 줄 수 있습니다.

## <a name="overview-of-cloud-consolidation"></a>클라우드 통합 개요

다음 주요 요구 사항이 충족될 경우 여러 비즈니스용 Skype 배포를 사용하는 모든 조직에 대해 단일 Microsoft 365 또는 Office 365 조직의 모든 사용자를 클라우드로 통합할 수 있습니다.

- 관련된 Microsoft 365 또는 Office 365 조직이 하나 이상 있어야 합니다. 조직이 두 개 이상인 시나리오에서는 통합이 지원되지 않습니다.
- 언제든지 하나의 온-프레미스 비즈니스용 Skype 포리스트만 하이브리드 모드(공유 SIP 주소 공간)에 있을 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 온-프레미스로 유지되어야(아마도 서로 연결되어) 합니다. 이러한 다른 온라인 프레미스 *조직은* 2018년 12월을 현재 사용할 수 있는 온라인 [SIP](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 도메인을 사용하지 않도록 설정하는 새로운 기능과 함께 원하는 경우 AAD에 동기화할 수 있습니다.

여러 포리스트에 비즈니스용 Skype를 배포하는 고객은 공유 SIP 주소 공간 기능을 사용하여 단일 하이브리드 비즈니스용 Skype 포리스트의 모든 사용자를 개별적으로 Microsoft 365 또는 Office 365 조직으로 완전히 마이그레이션한 다음, 다음 온-프레미스 비즈니스용 Skype 배포를 마이그레이션하기 전에 해당 온-프레미스 배포와 하이브리드를 사용하지 않도록 설정해야 합니다. 클라우드로 마이그레이션하기 전에 온-프레미스 사용자는 동일한 사용자의 온-프레미스 디렉터리에 표시되지 않는 사용자와 페더레이션 상태로 유지됩니다.  

## <a name="canonical-example-of-cloud-consolidation"></a>클라우드 통합의 정형 예

Microsoft Teams 또는 비즈니스용 Skype Online에서 온라인으로 통합하려는 비즈니스용 Skype의 두 개의 별도 페더임이 있는 조직을 고려하세요.


|원래 상태 세부 정보 |원하는 상태 세부 정보 |
|---------|---------|
|<ul><li>별도의 AD 포리스트에 2개의 독립적인 비즈니스용 Skype-프레미스 배포<li>1대의 포리스트가 비즈니스용 Skype Online과 하이브리드에 있습니다. <li> Orgs는 서로 페더러다이트됩니다. <li>사용자가 이러한 포리스트에서 동기화되지 않습니다.<li> 조직에 Microsoft 365 또는 Office 365 조직이 있을 수 있으며 디렉터리를 Azure AD에 동기화할 수 있습니다.</ul>|<ul> <li>1 Microsoft 365 또는 Office 365 조직<li>더 이상 On-premises 배포가 아니기 때문에 하이브리드가 남지 않습니다.<li>모든 프레미스 사용자가 비즈니스용 Skype Online에 있으며 선택적으로 Teams 전용 사용자일 수 있습니다. <li>어디에서도 비즈니스용 Skype의 모든 공간에 대한 모든 프레미스 공간 없음 <li>사용자에게 여전히 프레미스 인증이 있습니다.</ul> |

![두 개의 개별 페더링된프레미스 배포 통합](../media/cloudconsolidationfig1.png)  

원래 상태에서 원하는 종료 상태로의 기본 단계는 아래와 같습니다.  일부 조직에서는 시작 지점이 이러한 단계 중간에 있을 수 있습니다. 이 [문서의](#other-starting-points)부분에 있는 다른 시작 지점을 참조하세요. 마지막으로 경우에 따라 순서를 조정할 수 있습니다. [주요 제약 조건 및 제한은](#limitations) 나중에 설명됩니다.

1.  아직 없는 경우 Microsoft 365 또는 Office 365 조직을 다운로드합니다.
2.  두 배포의 모든 관련 SIP 도메인이 Microsoft 365 또는 Office 365 도메인으로 확인되어 있는지 확인해야 합니다.
3.  Microsoft 365 또는 Office 365와 하이브리드로 사용할 비즈니스용 Skype 배포를 하나 선택하세요. 이 예제에서는 OriginalCompany를 사용하게 될 것입니다. <span> com.
4.  먼저 하이브리드가 될 포리스트에 [대해 AAD Connect를](configure-azure-ad-connect.md) 사용하도록 설정(OriginalCompany). <span> com) 
5.  조직에 Teams를 도입할 경우 [TeamsUpgradePolicy에](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy) 대한 테넌트 전체 정책을 SfBWithTeamsCollab 또는 다른 SfB 모드(SfBOnly 또는 SfBWithTeamsCollabAndMeetings) 중 하나로 설정하십시오. 이는 Teams로 이동하는 사용자의 통화 및 채팅 라우팅을 프레미스에 남아 있는 사용자로만 라우팅하는 데 중요합니다.
6.  이때 다른 포리스트(AcquiredCompany)에 대해 [AAD Connect를](cloud-consolidation-aad-connect.md) 사용하도록 설정하는 것이 좋습니다(11단계까지는 필요하지 않음). <span> com) 두 포리스트에서 AAD Connect가 사용하도록 설정되어 있는 경우 조직은 그림 **[A와](#figure-a)** 같이 보입니다. 이는 일부 조직에 대한 일반적인 시작점이 될 수 있습니다. 
7.  다른 On-premises 배포에서 호스팅하는 모든 SIP 도메인(이 경우 AcquiredCompany) <span> com) PowerShell에서 비즈니스용 [Skype Online에서 이러한 SIP](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 도메인을 사용하지 `Disable-CsOnlineSipDomain` 않도록 설정하세요. 이 기능은 2018년 12월 이후의 새로운 기능입니다.
8.  OriginalCompany에 대한 비즈니스용 [Skype](configure-federation-with-skype-for-business-online.md) 하이브리드를 구성합니다. <span> com(온라인 SIP 도메인을 계속 사용하도록 설정한 배포 하나).
9.  하이브리드 배포(OriginalCompany) <span> com), 해당 [계정이](move-users-between-on-premises-and-cloud.md) 비즈니스용 Skype Online에 있도록 사용자를 비즈니스용 Skype에서 클라우드로 이동(Teams만 여부에 여부에 따라 다름)을 시작하세요. 이제 조직은 그림 **[B와 같이 됩니다.](#figure-b)** 그림 A에서 변경된 주요 사항은 다음입니다.
    - 이제 두 On-premises Director의 사용자가 모두 AAD에 있습니다.
    - AcquiredCompany. <span> com은 사용하지 않도록 설정된 온라인 SIP 도메인입니다.
    - 일부 사용자는 비즈니스용 Skype Online 또는 Teams로 온라인으로 이동했습니다. (자주색 사용자 A를 참조합니다.)
10. 모든 사용자가 클라우드로 이동된 후 OriginalCompany에 대한 비즈니스용 [Skype On-premises](cloud-consolidation-disabling-hybrid.md) 배포를 통해 하이브리드를 사용하지 않도록 설정하세요. <span> office 365에서 com:  
    - Microsoft 365 또는 Office 365 조직에서 분할 도메인을 사용하지 않도록 설정
    - OriginalCompany에서 Microsoft 365 또는 Office 365와 통신하는 기능을 사용하지 않도록 설정 <span> com on-premises.
    - OriginalCompany에 대한 DNS 레코드를 업데이트합니다. <span> com을 통해 Microsoft 365 또는 Office 365를 지점으로 합니다.
11. 아직 수행하지 않은 경우 하이브리드로 전환할 다음 포리스트(AcquiredCompany)에 [대해 AAD](cloud-consolidation-aad-connect.md) Connect를 사용하도록 설정해야 합니다. <span> com) 이때 조직은 그림 **[C와 같이 됩니다.](#figure-c)** 이는 일부 조직에 대한 또 다른 일반적인 시작 지점일 수 있습니다. 
12. PowerShell에서 하이브리드, AcquiredCompany를 진행할 다음 [On-프레미스](https://docs.microsoft.com/powershell/module/skype/enable-csonlinesipdomain) 배포에 대해 SIP 도메인을 사용하도록 설정합니다. <span> com. 이 기능은 `Enable-CsOnlineSipDomain` 2018년 12월에 사용할 수 있는 새로운 기능인 사용하여 수행됩니다.
13. 닫힌 페더링을 사용하는 경우 순수 온라인 테넌트의 SIP \* 도메인(.microsoftonline.com 제외)을 동일한 Microsoft 365 또는 Office 365의 허용 도메인으로 추가해야  합니다. 변경이 적용되기까지 시간이 다소 걸릴 수 있으며 이 초기에는 해가 없습니다. 따라서 14단계로 이동하기 전에 이 작업을 잘 수행해보는 것이 좋습니다.
14. 온라인 테넌트의 모든 SIP 도메인을 수락하여 일치하게 프레미스 환경을 업데이트합니다.
    - 모든 에지 인증서의 [SAN을](cloud-consolidation-edge-certificates.md) 이전과 동일한 값과 기존 온라인 SIP 도메인의 값(*.microsoftonline.com 제외)으로 업데이트합니다(이 경우 Sip.OriginalCompany). <span> com.
    - OriginalCompany를 만들어야 합니다. <span> com은 [On-premises](https://docs.microsoft.com/powershell/module/skype/new-csalloweddomain) 배포에서 허용되는 도메인인 AcquiredCompany입니다. 허용 도메인을 추가합니다.
15. [비즈니스용 Skype](configure-federation-with-skype-for-business-online.md) 하이브리드를 사용할 수 있도록 설정한 후,프레미스 AcquiredCompany를 사용할 수 있습니다. <span> com 및 클라우드.
16. 원하는 경우 사용자를 프레미스에서 클라우드로 [마이그레이션합니다.](move-users-between-on-premises-and-cloud.md) 사용자를 [TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) 모드로 직접 마이그레이션하거나 먼저 비즈니스용 Skype Online으로 마이그레이션할 수 있습니다. 이 상태 동안 조직은 그림 **[D와 같이 됩니다.](#figure-d)**
17. 모든 사용자가 마이그레이션된 후, 조직을 순수 클라우드로 만들기 위해 하이브리드를 [On-프레미스](cloud-consolidation-disabling-hybrid.md) 환경과 *함께 사용하지 않도록 설정하세요.*

아래 다이어그램은 이 프로세스 중에 다양한 주요 지점의 구성을 보여 주며,

##### <a name="figure-a"></a>그림 A:

- 두 조직은 AAD Connect를 통해 동기화하기 때문에 이제 AAD에는 두 가지 모두의 모든 사용자가 있습니다.
- 모든 사용자가 홈으로 사용했습니다.  
- 비즈니스용 Skype 하이브리드가 *아직 구성되지* 않았습니다.
- 두 배포 중 하나에서 사용자가 Teams를 사용하는 경우 서로(또는 조직) 페더러티를 할 수 없으며 비즈니스용 Skype 사용자와 상호 협력할 수도 없습니다. 이 단계에서는 채널에만 Teams를 사용하는 것이 좋습니다.<br><br>
    ![그림 다이어그램](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>그림 B:

- AcquiredCompany. <span> com은 [사용하지 않도록 설정된](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 온라인 SIP 도메인입니다. 모든 사용자가 On-premises입니다. Teams를 사용하는 경우 페더전 또는 상호 협력성이 없습니다. 이 단계에서는 채널에만 Teams를 사용하는 것이 좋습니다.
- 비즈니스용 Skype 하이브리드는 온라인 프레미스 조직 중 하나에 대해 사용하도록 설정되어 있습니다.
- 하이브리드 조직의 일부 사용자는 클라우드로 이동했습니다(보라색 음영으로 표시된 사용자 A). 이러한 사용자는 비즈니스용 Skype Online 사용자 또는 전체 상호 상호 연결 및 페더전 지원을 지원하는 Teams 전용 사용자일 수 있습니다.<br><br>
    ![그림 B 다이어그램](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>그림 C:

- OriginalCompany의 모든 사용자 <span> com은 이제 클라우드(비즈니스용 Skype Online에 있는)에 있습니다. 또한 Teams 전용인 것이 좋습니다.
- OriginalCompany를 <span> 통해 비즈니스용 Skype 하이브리드 구성 com 배포가 사용하지 않도록 설정되어 있습니다. The on-premises deployment is gone.
- If AcquiredCompany. <span> com이 이전에 AAD와 동기화되지 않은 경우 여기에서 계속 동기화해야 합니다. 그러나 아직 하이브리드(공유 SIP 주소 공간)가 아니며 조직이 하이브리드로 이동할 준비가 될 때까지는 온라인 Teams 사용자가 온라인 Teams 사용자와 통신할 수 있도록 순수 AcquiredCompany.com 조직(AcquiredCompany.com)에 대한 온라인 SIP 도메인을 사용하지 않도록 설정해야 합니다.<br><br>
    ![그림 C 다이어그램](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>그림 D:

- AcquiredCompany. <span> com이 이제 온라인 SIP 도메인으로 사용하도록 설정됩니다.
- On-premises is updated to accept OriginalCompany. <span> com. 허용 도메인 및 에지 인증서가 모두 업데이트됩니다.
- AcquiredCompany 간에 공유 SIP 주소 공간을 사용할 수 있습니다. <span> com 및 Microsoft 365 또는 Office 365 조직.
- 하이브리드 조직의 일부 사용자는 아래 사용자 D(보라색 음영으로 표시)처럼 클라우드로 이동된 것일 수 있습니다.<br><br>
    ![그림 D 다이어그램](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>기타 시작점

위 정식 예제의 단계에서는 조직이 Microsoft 또는 Office 365가 없는 두 개의 페더임된온-프레미스 배포로 시작된다고 가정합니다. 그러나 일부 조직에는 기존 Microsoft 365 또는 Office 365 사용 공간도 있을 수 있으며 위의 순서에 서로 다른 진입점이 있을 수 있습니다. 일반적인 구성은 네 가지입니다.

- Microsoft 365 또는 Office 365 조직이 없는 여러 개의 페더임된 On-프레미스 조직 이 경우 1단계에서 시작합니다.
- 여러 비즈니스용 Skype 포리스트를 단일 Azure AD 테넌트에 이미 동기화하고 있는 여러 개의 페더링된 On-premises 조직 이러한 조직은 그림 A의 가상 조직과 1-6단계를 완료하고 7단계에서 시작해야 합니다.
- AAD와 동기화되지는 않습니다. 이러한 조직은 아래 표시된 **그림 E의** 가상 조직과 같습니다.
    - 이 조직은 다음을 제외하고 1-9단계를 완료한 그림 B와 비슷합니다.
        - 하이브리드가 아닌 비즈니스용 Skype *배포는* 아직 Azure AD와 동기화되지 않았습니다.
        -  온라인 SIP 도메인은 아직 사용하지 않도록 설정되지 않았습니다. 
    - 이러한 조직은 다음 중 하나에 해당해야 합니다.
        - 기존 하이브리드 조직의 마이그레이션을 완료하고 10단계에서 위의 순서를 입력합니다.  또는
        - 하이브리드 조직의 마이그레이션을 완료하기 전에 다른 비즈니스용 Skype 포리스트를 AAD에 동기화하려는 경우 조직은 7단계를 수행(AAD와 동기화할 다른 모든 온라인 비즈니스용 Skype 배포에서 모든 온라인 SIP 도메인을 사용하지 않도록 설정)한 다음 AAD Connect를 사용하도록 설정한 다음 10단계(원래 하이브리드 배포 해제)만 계속해야 합니다.       
                **그림 E**<br>
                ![그림 E 다이어그램](../media/cloudconsolidationfige.png)
- 별도의 비즈니스용 Skype 조직과 페더미스되는 순수 비즈니스용 Skype Online 조직(Teams를 사용 중일 수도 또는 사용하지 않을 수 있습니다.) 이 조직이온-프레미스 조직에 대해 온라인 SIP 도메인을 사용하지 않도록 설정하고, 비즈니스용 Skype 조직에 대해 AAD Connect를 사용할 수 있는 경우 1-11단계를 완료한 그림 **[C에](#figure-c)** 표시된 가상 조직과 같은 기능을 수행합니다.

## <a name="limitations"></a>제한 사항

- 관련된 Microsoft 365 또는 Office 365 조직이 하나 이상 있어야 합니다. 조직이 두 개 이상인 시나리오에서는 통합이 지원되지 않습니다.
- 한 프레미스 비즈니스용 Skype 포리스트 하나만 하이브리드 모드(공유 SIP 주소 공간)에 있을 수 있습니다. 다른 모든 비즈니스용 Skype 포리스트는 전적으로 모든 On-premises로 유지되어야 하며, 서로 및 Microsoft 365 또는 Office 365 조직과 페더러되어야 합니다.
- 클라우드로 마이그레이션하기 전에는 온라인의 모든 사용자가 다음을 통해 표현되는 것이 아니기 때문에 이 배포의 사용자에게는 비대칭 환경이 있습니다.
    - 환경은 다음과 같이 요약될 수 있습니다.
        - 온라인에 있는 모든 사용자는 사용자가 하이브리드인 경우처럼 하이브리드 환경의 모든 사용자와 상호 작용합니다.
        - 하이브리드 배포의온-프레미스 사용자는 하이브리드인 경우처럼 자신의 온라인 디렉터리에 있는 온라인 사용자와 상호 작용합니다. 
        - 하이브리드 배포의 On-premises users will interact with online users who are not represented in on-premises AD as federated.
    - 위의 **[그림 D에서](#figure-d)** 사용자 E는 AcquiredCompany의 On-premises입니다. <span> com.  사용자 E는 표준 하이브리드 환경을 사용하여 사용자 D(홈 온라인)와 상호 작용하지만, 사용자 E는 사용자 A, B 및 C와의 페더전된 환경을 경험하게 됩니다. 이러한 환경은온-프레미스 디렉터리에 나타내지 않습니다. 그러나 사용자 A, B 및 C는 사용자가 하이브리드에 있는 경우처럼 사용자 E와 상호 작용합니다.
    - 상호 작용이 하이브리드와 페더에 대한 의미:
        - 사용자가 연락처로 표시되어 있지 않으면 페더니언트 사용자에 대해 현재 상태는 자동으로 구독되지 않습니다.
        - 페더링 도메인 간에는 통화 전달이 작동하지 않습니다.
        - 통화 전송 시나리오가 더 제한됩니다.
        - 페더링 트래픽에 스로틀을 적용할 수 있습니다.
- 이 비대칭 환경이 제공될 경우, 크로스-프레미스 시나리오의 전화 기능에 대한 공식적인 지원은 크로스-프레미스 사용자와, 즉 On-프레미스 디렉터리에 없는 클라우드 사용자 간의 지원은 피어 투 피어 전용으로 제한됩니다. 
    - 이러한 사용자 간의 통화 전달, 전송, 통화 큐 등은 지원되지 않습니다.
    - 이러한 지원되지 않는 호출 시나리오는 여전히 사용하도록 설정되어 있지만 대부분의 경우 예측할 수 없는 방식으로 실패합니다. 
    - 위의 **[그림 D에서는](#figure-d)** 사용자 E가프레미스에 있으며, 사용자 A, B 또는 C와의 통화는 피어 투 피어로만 지원됩니다. 사용자 D가 있는 통화에는 지원 제한이 없습니다.  그러나 클라우드로 이동한 후 이 제한은 더 이상 적용되지 않습니다.
- 환경에 비즈니스용 Skype 서버 2019 배포가 두 개 이상 있는 경우 해당 기능을 사용하려면 비즈니스용 Skype 서버 하이브리드 구성이 필요하기 때문에 이러한 배포 중 1개만 조직 구성 자동 전화 교환 구성할 수 있습니다. 
- 이전 단계 중 일부의 순서를 조정할 수 있습니다. 충족해야 하는 주요 요구 사항은 이러한 모든 요구 사항이 충족될 경우 다음을 충족하는 것입니다.
    - 단일 AAD 테넌트와 동기화하는 두 개 이상의 비즈니스용 Skype 포리스트
    - 하나의 On-premises 포리스트에서 분할 도메인을 사용하도록 설정
    - 하이브리드 조직의 사용자 한 명 이상이 클라우드로 마이그레이션된 경우<br>   그런 다음 *다른 모든* 비즈니스용 Skype 포리스트에서 다른 모든 온라인 SIP 도메인을 사용하지 않도록 설정해야 합니다. 그렇지 않으면 하이브리드 조직의 온라인 사용자와 다른 조직의 온라인 사용자 간의 페더임이 한 방향으로 중단됩니다.

## <a name="implications"></a>의미

- 위에서 설명한 대로 고급 통화 기능에 대한 지원에는 제한이 있기 때문에 조직은 이러한 비대칭 상태를 마이그레이션의 일부로 처리하고 이를 비동기 상태로 진행하지 **말아야 합니다.**  
- 온-프레미스 비즈니스용 Skype 배포가 여러 개 있는 조직은 일반적으로 통합을 계속할 수 있도록 클라우드로 완전히 마이그레이션할 수 있는 배포로 시작해야 합니다. 경우에 따라 Teams로 이동할 수 없는 특정 사용자 그룹의 보류가 있을 수 있습니다. 여러 비즈니스용 Skype 포리스트가 관련된 시나리오에서 이 사항을 고려할 경우 가능한 경우 이러한 제한이 없는 다른 포리스트로 마이그레이션을 시작하십시오.
- 프레미스에서 클라우드로 이동할 때 위임 관계가 있으며 일반적으로 통화 전달 시나리오에 포함되는 사용자는 한 단위로 함께 이동해야 합니다.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>TeamsOnly 모드로 전환할 때의 고려 사항

사용자를 하이브리드 환경의 클라우드로 이동하는 경우 사용자를 비즈니스용 Skype 전용 또는 TeamsOnly 모드로 이동할 수 있습니다. *사용자를 TeamsOnly 모드로 이동하는 경우 먼저 이 섹션을 읽어야 합니다.*

- 사용자에게 TeamsOnly 모드를 할당하면 다른 사용자의 모든 채팅 및 통화가 해당 사용자의 Teams 클라이언트에 연결됩니다. 
- 비즈니스용 Skype를 사용하는 사용자가 주로 Teams가 아닌 비즈니스용 Skype 클라이언트를 사용하는 경우, 해당 비즈니스용 Skype 사용자에 대한 라우팅이 항상 Teams 대신 비즈니스용 Skype에 연결하게 하여 TeamsUpgradePolicy를 설정하는 것이 좋습니다. TeamsOnly인 사용자와 비즈니스용 Skype를 여전히 사용하는 사용자 간의 적절한 채팅 및 통화 라우팅을 보장하려면, 기본적으로 아일랜드가 아닌 SfB 모드 중 하나를 사용하여 TeamsUpgradePolicy의 유효 값이 있어야 합니다. 
    - 이렇게하려면 먼저 테넌트의 *TeamsUpgradePolicy* 전역 인스턴스를 다음 값 중 하나로 설정해야 합니다.
        - SfBWithTeamsCollab(권장)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 다음 명령을 사용하여 테넌트 전체 정책을 부여할 수 있습니다.<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 참고: 온라인 디렉터리에 SIP 주소가 없는 개별 사용자에게는 정책을 할당할 수 없는 테넌트 수준으로 이 작업을 해야 합니다. 순수온-프레미스 배포에 대해 온라인 SIP 도메인을 사용하지 않도록 설정한 경우 해당 도메인의 사용자는 기본적으로 온라인 디렉터리에 SIP 주소를 사용하지 않습니다. 따라서 해당 On-프레미스 사용자에게 정책을 적용하는 유일한 방법은 테넌트 수준에서 할당하는 것입니다. 반면, 하이브리드 배포에서는 사용자가 테넌트 글로벌 정책과 다른 값을 가지길 원하는 경우 정책을 명시적으로 할당할 수 있도록 온라인 디렉터리에 SIP 주소가 있습니다.
- Teams 클라이언트 UX는 아직 TeamsUpgradePolicy의 SfB 모드를 존중하지 않습니다. 예를 들어 이러한 모드에서는 Teams에서 통화 및 채팅 시작이 현재 가능하기는 하지만 앞으로는 이러한 경우를 예로 들 수 없습니다. 이로 인해 사용자들이 혼란을 일으킬 수 있습니다. 경우에 따라 답장은 때때로 Teams에 오고 경우에 따라 비즈니스용 Skype가 될 수 있기 때문에 혼동을 일으킬 수 있습니다. 여전히 프레미스에 있는 사용자에 대해 TeamsMessagingPolicy 및 TeamsCallingPolicy를 통해 통화 및 채팅을 별도로 사용하지 않도록 설정하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

[에지 인증서 업데이트](cloud-consolidation-edge-certificates.md)

[여러 포리스트를 포함하도록 AAD Connect를 업데이트](cloud-consolidation-aad-connect.md)

[클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화](cloud-consolidation-disabling-hybrid.md)
