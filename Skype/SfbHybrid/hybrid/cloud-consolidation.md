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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 문서에서는 UC 작업을 팀 및/또는 비즈니스용 Skype Online으로 이동 하기 위해 이동 하려는 비즈니스용 Skype (또는 Lync)에 대 한 온-프레미스 배포를 수행 하는 조직에 대해이 통합을 구현 하는 방법을 설명 합니다.
ms.openlocfilehash: f09359f126a051f72397b10724c6ab51d6ca0c1a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033667"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Teams과 비즈니스용 Skype를 위한 클라우드 통합

많은 대기업에는 온-프레미스 AD 포리스트가 여러 개 있고, 경우에 따라 고객은 둘 이상의 Exchange 및/또는 비즈니스용 Skype 서버(또는 Lync Server) 배포가 있을 수 있습니다. 또한 온-프레미스 포리스트 하나만 있는 조직에서도 비즈니스 합병 또는 인수를 통해 유사한 상황에 처할 수 있습니다. 이러한 고객이 클라우드로 이동함에 따라 주어진 온-프레미스 워크로드의 여러 인스턴스를 단일 Office 365 테넌트에 클라우드로 통합하려고 합니다. 이 문서에서는 UC 작업을 Microsoft 클라우드 (예: Microsoft 팀 및/또는 비즈니스용 Skype Online)로 이동 하려는 비즈니스용 Skype (또는 Lync)가 여러 온-프레미스 배포를 사용 하는 조직에 대 한 통합을 구현 하는 방법에 대해 설명 합니다.

지금까지는 이러한 상황에 처한 고객은 온-프레미스 배포를 먼저 통합한 다음 클라우드로 이동해야 했습니다. 이 문서는 계속 사용할 수 있는 기능 이지만, 여러 Skype를 사용 하는 조직에서 온-프레미스를 수행 하지 않고도 단일 Office 365 테 넌 트로 한 번에 하나의 배포를 마이그레이션하는 데 사용 되는 새 기능의 솔루션에 대해 설명 합니다. 사용한. 이 새로운 기능을 사용 하는 경우에도 비즈니스용 Skype Online 및 Microsoft 팀은 단일 Office 365 테 넌 트와 함께 하이브리드 모드에서 비즈니스용 Skype/Lync 포리스트를 여러 개 지원 하지 않습니다. 

> [!Important]
> 구성에이 가이드를 사용 하기 전에 [제한 사항을](#limitations)검토 하 고 이해 해야 조직에 영향을 줄 수 있습니다.

## <a name="overview-of-cloud-consolidation"></a>클라우드 통합 개요

다음 핵심 요구 사항이 충족되는 경우 여러 비즈니스용 Skype 배포를 사용하는 모든 조직에 대해 단일 Office 365 테넌트에서 온-프레미스의 모든 사용자를 클라우드로 통합 할 수 있습니다.

- 관련 Office 365 테넌트가 최대 하나가 있어야 합니다. Office 365 테넌트가 두 개 이상 있는 시나리오의 통합 기능은 지원되지 않습니다.
- 언제든지 하나의 온-프레미스 비즈니스용 Skype 포리스트만 하이브리드 모드(공유 SIP 주소 공간)에 있을 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 온-프레미스로 유지되어야(아마도 서로 연결되어) 합니다. [새로운 기능을 사용 하 여 온라인 SIP 도메인](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps) 을 12 월 2018 일 때 사용할 수 없도록 설정 하는 경우 이러한 다른 온-프레미스 조직은 AAD와 동기화 *할 수 있습니다* .

여러 포리스트에 비즈니스용 Skype를 배포하는 고객은 공유 SIP 주소 공간 기능을 사용하여 단일 하이브리드 비즈니스용 Skype 포리스트의 모든 사용자를 개별적으로 Office 365 테넌트로 완전히 마이그레이션해야 합니다. 그런 다음, 다음 온-프레미스 비즈니스용 Skype 배포를 마이그레이션하기 전에 해당 온-프레미스 배포와 하이브리드를 비활성화합니다. 클라우드로 마이그레이션하기 전에 온-프레미스 사용자는 동일한 사용자의 온-프레미스 디렉터리에 표시되지 않는 사용자와 페더레이션 상태로 유지됩니다.  

## <a name="canonical-example-of-cloud-consolidation"></a>클라우드 통합의 정식 예

Microsoft 팀 또는 비즈니스용 Skype Online에 온라인으로 통합 하려는 비즈니스용 Skype를 별도의 페더레이션 온-프레미스 배포를 사용 하는 조직을 가정해 봅니다.


|원래 상태 정보 |원하는 상태 세부 정보 |
|---------|---------|
|<ul><li>별도의 AD 포리스트에서 두 개의 독립 비즈니스용 Skype 온-프레미스 배포<li>최대 1 개 포리스트는 비즈니스용 Skype 온라인과의 하이브리드입니다. <li> Orgs는 서로 연결 되어 있습니다. <li>사용자가 이러한 포리스트 간에 동기화 되지 않음<li> 조직에 Office 365 테 넌 트가 있을 수 있으며 Azure AD로 디렉터리를 동기화 할 수 있습니다.</ul>|<ul> <li>Office 365 테 넌 트 1 개<li>더 이상 온-프레미스 배포를 지원 하지 않으므로 하이브리드가 남아 있지 않음<li>온-프레미스의 모든 사용자는 비즈니스용 Skype Online에 있고 선택적으로 팀 전용 사용자 일 수 있습니다. <li>외부 비즈니스용 Skype에 대 한 온-프레미스 공간 없음 <li>사용자가 계속 온-프레미스 인증을 보유 하 고 있습니다.</ul> |

![두 개의 별도 페더레이션 온-프레미스 배포 통합](../media/cloudconsolidationfig1.png)  

원래 상태에서 원하는 최종 상태로 이동 하는 기본 단계는 다음과 같습니다.  일부 조직은 이러한 단계의 중간 부분에 시작 지점이 있을 수 있습니다. 이 문서 뒷부분의 [다른 시작 지점을](#other-starting-points)참조 하십시오. 마지막으로, 일부 경우에는 필요에 따라 순서를 조정할 수 있습니다. [주요 제약 조건 및 제한 사항](#limitations) 에 대해서는 뒷부분에서 설명 합니다.

1.  아직 없는 경우 Office 365 테 넌 트를 가져옵니다.
2.  온-프레미스 배포에서 모든 관련 SIP 도메인이 확인 된 Office 365 도메인 인지 확인 합니다.
3.  Office 365을 사용 하 여 하이브리드로 사용할 비즈니스용 Skype 배포를 선택 합니다. 이 예에서는 OriginalCompany를 사용 합니다. <span>com
4.  처음에 하이브리드 (OriginalCompany)이 될 [포리스트에 대해 AAD 연결을 사용 하도록 설정](configure-azure-ad-connect.md) 합니다.<span> com). 
5.  조직에 팀이 도입 되는 경우 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy) 에 대 한 테 넌 트 전체 정책을 SfBWithTeamsCollab 또는 기타 SfB 모드 (SfBOnly 또는 SfBWithTeamsCollabAndMeetings) 중 하나로 설정 합니다. 이는 온-프레미스에 있는 사용자 에게만 팀으로 이동 하는 사용자에 대 한 통화 및 채팅의 라우팅을 보장 하기 위해 중요 합니다.
6.  이 지점에서 다른 포리스트 (AcquiredCompany) [에 대해 AAD 연결을 사용 하도록 설정](cloud-consolidation-aad-connect.md) 하는 것이 좋습니다 (아직 11 단계까지<span> 필요 함). com). 두 포리스트에서 AAD 연결이 사용 되도록 설정 된 경우 org가 **[그림 A](#figure-a)** 와 같이 표시 되며,이는 일부 orgs에 대 한 공통 시작 지점이 될 수 있습니다. 
7.  다른 온-프레미스 배포에서 호스트 되는 모든 SIP 도메인 (이 경우에는 AcquiredCompany<span> . com)에서 PowerShell을 사용 하 여 `Disable-CsOnlineSipDomain` [비즈니스용 Skype ONLINE에서 이러한 SIP 도메인을 사용 하지 않도록 설정](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 합니다. (이 기능은 12 월 2018의 새로운 기능입니다.)
8.  OriginalCompany에 대해 [비즈니스용 Skype 하이브리드를 구성](configure-federation-with-skype-for-business-online.md) 합니다. <span>com (온라인 SIP 도메인을 사용 하도록 설정 된 한 개의 배포)
9.  하이브리드 배포 (OriginalCompany<span> ) com)에서 비즈니스용 [Skype Online의 사용자 이동을 클라우드로 이동](move-users-between-on-premises-and-cloud.md) 하기 시작 합니다 (팀 전용 여부에 관계 없이). 이제 **[그림 B](#figure-b)** 와 같은 조직이 표시 됩니다. 그림 A의 주요 변경 사항은 다음과 같습니다.
    - 온-프레미스 디렉터리의 사용자는 이제 AAD에 있습니다.
    - AcquiredCompany. <span>com은 사용 하지 않도록 설정 된 온라인 SIP 도메인입니다.
    - 일부 사용자는 온라인으로 비즈니스용 Skype Online 또는 팀으로 이동 되었습니다. (자주색 사용자 A 참고)
10. 모든 사용자가 클라우드로 이동 되 면 OriginalCompany 용 [비즈니스용 Skype 온-프레미스 배포와의 하이브리드를 사용 하지 않도록 설정](cloud-consolidation-disabling-hybrid.md) 합니다. <span>Office 365의 com:  
    - Office 365 테넌트에서 분할 도메인을 사용하지 않도록 설정합니다.
    - OriginalCompany에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다. <span>com 온-프레미스
    - OriginalCompany에 대 한 DNS 레코드를 업데이트 합니다. <span>Office 365를 가리키도록 com을 지정 합니다.
11. 아직 수행 하지 않은 경우 다음에 하이브리드가 이동 될 [포리스트에 대해 AAD 연결을 사용 하도록 설정](cloud-consolidation-aad-connect.md) 합니다 (AcquiredCompany).<span> com). 이 시점에서 조직은 **[그림 C](#figure-c)** 와 같습니다. 이는 일부 조직에서 시작 되는 다른 일반적인 출발점 일 수 있습니다. 
12. PowerShell에서 하이브리드, AcquiredCompany로 이동 하는 [다음 온-프레미스 배포에 대해 SIP 도메인을 사용 하도록 설정](https://docs.microsoft.com/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps) 합니다. <span>com 이 작업은 12 `Enable-CsOnlineSipDomain`월 2018까지 사용할 수 있는 새로운 기능을 사용 하 여 수행 합니다.
13. 닫힌 페더레이션을 사용 하는 경우 **동일한** Office 365에서 순수 온라인 테 넌 트의 모든 SIP 도메인 (microsoftonline.com 제외)을 허용 도메인으로 추가 해야 합니다. 변경 내용이 적용 될 때까지 시간이 걸릴 수 있으며이 작업을 일찍 수행 하는 데는 문제가 없기 때문에 14 단계로 이동 하기 전에이 작업을 수행 하는 것이 좋습니다.
14. 온라인 테 넌 트에서 SIP 도메인을 수락 하도록 온-프레미스 환경을 업데이트 하 여 일치 시킵니다.
    - [모든에 지 인증서의 SAN](cloud-consolidation-edge-certificates.md) 을 이전와 동일한 값으로 업데이트 하 고,이 경우에는 microsoftonline.com를 제외한 모든 기존 온라인 SIP 도메인의 값을이 경우에는. <span>com
    - OriginalCompany를 확인 합니다. <span>com은 온-프레미스 배포의 AcquiredCompany에 허용 되는 [도메인](https://docs.microsoft.com/powershell/module/skype/new-csalloweddomain) 입니다. 허용 도메인을 추가 합니다.
15. 온-프레미스 AcquiredCompany 간에 [비즈니스용 Skype hybrid을 사용 하도록 설정](configure-federation-with-skype-for-business-online.md) 합니다. <span>com 및 클라우드
16. 필요에 따라 온 [-프레미스에서 클라우드로 사용자를 마이그레이션합니다](move-users-between-on-premises-and-cloud.md). 사용자를 [Teamsonly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability) 모드로 직접 마이그레이션하거나 마이그레이션할 수도 있고, 먼저 비즈니스용 Skype Online으로 마이그레이션할 수도 있습니다. 이 상태에서 조직은 **[그림 D](#figure-d)** 와 같습니다.
17. 모든 사용자가 마이그레이션된 후 [에는 온-프레미스 환경에서 하이브리드를 사용 하지 않도록 설정](cloud-consolidation-disabling-hybrid.md) 하 여 *조직 순수 클라우드로 만듭니다*.

아래 다이어그램에서는이 프로세스 중 다양 한 주요 지점에 대 한 구성을 보여 줍니다.

##### <a name="figure-a"></a>그림 A:

- 두 조직이 AAD Connect를 통해 동기화 되므로 AAD에서는 온-프레미스 배포의 모든 사용자를 갖게 됩니다.
- 모든 사용자가 온-프레미스에 속해 있습니다.  
- 비즈니스용 Skype 하이브리드가 아직 구성 *되지* 않았습니다.
- 두 배포 중 하나의 사용자가 팀을 사용 하는 경우에는 서로 또는 모든 조직과 페더레이션 할 수 없으며 비즈니스용 Skype 사용자와의 상호 운용성이 없습니다. 이 단계에서는 채널에만 팀을 사용 하는 것이 좋습니다.<br><br>
    ![그림 A 다이어그램](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>그림 B:

- AcquiredCompany. <span>com은 [사용 하지 않도록 설정](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 된 온라인 SIP 도메인입니다. 모든 사용자가 온-프레미스입니다. 팀을 사용 하는 경우 페더레이션 또는 상호 운용성이 없습니다. 이 단계에서는 채널에만 팀을 사용 하는 것이 좋습니다.
- 비즈니스용 Skype 하이브리드가 온-프레미스 조직 중 하나에 대해 사용 하도록 설정 되었습니다.
- 하이브리드 조직의 일부 사용자는 클라우드 (자주색 음영으로 표시 된 사용자 A)로 옮겨졌습니다. 이러한 사용자는 비즈니스용 Skype Online 사용자 또는 팀이 전체 상호 운용성 및 페더레이션 지원을 가진 사용자 일 수 있습니다.<br><br>
    ![그림 B 다이어그램](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>그림 C:

- OriginalCompany의 모든 사용자입니다. <span>com은 이제 클라우드 (비즈니스용 Skype Online)에 있습니다. 또한 팀만이 될 것을 권장 합니다.
- OriginalCompany를 사용한 비즈니스용 Skype 하이브리드 구성 <span>com 배포가 사용 하지 않도록 설정 되었습니다. 온-프레미스 배포가 사라졌습니다.
- AcquiredCompany 인 경우 <span>com은 이전에 AAD로 동기화 되지 않았으므로 지금 계속 동기화 해야 합니다. 그러나 아직 하이브리드 (공유 SIP 주소 공간)이 아니며 조직이 하이브리드로 이동할 준비가 될 때까지, 순수 온-프레미스 조직 (AcquiredCompany.com)에 대 한 온라인 SIP 도메인은 사용 하지 않도록 설정 되어 있어 온라인 팀 사용자가 통신할 수 있습니다. 온-프레미스 사용자<br><br>
    ![그림 C 다이어그램](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>그림 D:

- AcquiredCompany. <span>이제 com은 온라인 SIP 도메인으로 사용 하도록 설정 됩니다.
- OriginalCompany를 허용 하도록 온-프레미스가 업데이트 되었습니다. <span>com (허용 되는 도메인 및에 지 인증서가 모두 업데이트 됨)
- AcquiredCompany 간에 공유 SIP 주소 공간이 사용 되도록 설정 됩니다. <span>Com 및 Office 365 테 넌 트
- 하이브리드 조직의 일부 사용자는 클라우드로 이동 되었을 수 있습니다 (예: 자주색 음영으로 표시).<br><br>
    ![그림 D 다이어그램](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>기타 시작 지점

위의 정식 예에 나오는 단계는 조직이 Office 365 현재 없이 두 개의 페더레이션 온-프레미스 배포로 시작 된다고 가정 합니다. 그러나 일부 조직에는 기존 Office 365의 공간이 있을 수 있으며 위의 순서에 따라 각 진입점이 다를 수 있습니다. 일반적으로 다음과 같은 네 가지 구성이 있습니다.

- Office 365 테 넌 트가 없는 여러 페더레이션 온-프레미스 조직 이 경우 1 단계에서 시작 합니다.
- 여러 비즈니스용 Skype 포리스트가 이미 단일 Azure AD 테 넌 트로 동기화 되는 여러 페더레이션 온-프레미스 조직 이러한 조직은 그림 A의 가상 조직과 유사 하지만, 1-6 단계가 완료 되며 7 단계에서 시작 해야 합니다.
- 하나 이상의 다른 순수한 온-프레미스 조직이 포함 된에서 콘텐츠 하이브리드 조직이 며 AAD에는 어떤 동기화도 하지 않습니다. 이러한 조직은 아래와 같이 **그림 E**의 가상 조직과 비슷합니다.
    - 이 조직은 다음을 제외 하 고는 1-9 단계를 완료 한 그림 B와 비슷합니다.
        - 이 비 하이브리드 비즈니스용 Skype 배포는 아직 Azure AD와 동기화 *되지 않습니다* .
        -  온라인 SIP 도메인은 아직 사용 하지 않도록 설정 되어 있지 않습니다. 
    - 이러한 조직은 다음 중 하나를 수행 해야 합니다.
        - 기존 하이브리드 조직의 마이그레이션을 완료 하 고 10 단계에서 위의 시퀀스를 입력 합니다.  사용자나
        - 하이브리드 조직의 마이그레이션을 완료 하기 전에 다른 비즈니스용 Skype 포리스트를 AAD로 동기화 하려면 조직에서 7 단계 (모든 온라인 SIP 도메인을 사용 하지 않도록 설정)을 수행 해야 합니다. AAD에 동기화) 한 다음 AAD 연결을 사용 하도록 설정한 다음 10 단계 (원본 하이브리드 배포 해제)를 계속 진행 합니다.       
                **그림 E**<br>
                ![그림 E 다이어그램](../media/cloudconsolidationfige.png)
- 별도의 온-프레미스 비즈니스용 Skype 조직을에서 콘텐츠 하는 비즈니스용 Skype Online 조직 (팀을 사용 하 고 있을 수 있음)입니다. 이 조직에서는 온-프레미스 조직에 대 한 온라인 SIP 도메인을 사용 하지 않도록 설정 하 고 온-프레미스 비즈니스용 Skype 조직에 대해 AAD 연결을 사용 하도록 설정 하면 **[그림 C](#figure-c)** 에 나와 있는 가상 조직과 유사한 것으로, 1-11 단계가 완료 되었습니다.

## <a name="limitations"></a>제한

- 관련 Office 365 테넌트가 최대 하나가 있어야 합니다. Office 365 테넌트가 두 개 이상 있는 시나리오의 통합 기능은 지원되지 않습니다.
- 한 번에 하나의 온-프레미스 비즈니스용 Skype 포리스트로 하이브리드 모드 (공유 SIP 주소 공간)가 될 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 항상 온-프레미스에 유지 되어야 하며 서로 페더레이션 하 고 Office 365 테 넌 트와 연결 해야 합니다.
- 온라인에 있는 모든 사용자가 온-프레미스로 표시 되지는 않으므로 클라우드로 마이그레이션 되기 전에는이 배포 사용자에 게 비대칭 환경이 제공 됩니다.
    - 환경은 다음과 같이 합계 될 수 있습니다.
        - 사용자가 하이브리드 인 경우 하이브리드 환경의 온-프레미스 사용자와 상호 작용 합니다.
        - 하이브리드 배포의 온-프레미스 사용자는 온-프레미스 디렉터리에 하이브리드 인 것 처럼 표시 되는 온라인 사용자와 상호 작용 합니다. 
        - 하이브리드 배포의 온-프레미스 사용자는 온-프레미스 AD에 페더레이션 된 것으로 표시 되지 않는 온라인 사용자와 상호 작용 합니다.
    - 위의 **[그림 D](#figure-d)** 에서는 사용자 E가 AcquiredCompany에서 온-프레미스입니다. <span>com  사용자 E는 표준 하이브리드 환경을 사용 하 여 사용자 D (홈 online)와 상호 작용 하지만 사용자 E는 온-프레미스 디렉터리에 표시 되지 않으므로 사용자 A, B 및 C에 연합 된 환경이 있습니다. 그러나 사용자 A, B 및 C는 사용자가 하이브리드 인 것 처럼 사용자 E와 상호 작용 합니다.
    - 하이브리드와 페더레이션 간의 상호 작용의 의미
        - 사용자가 연락처로 표시 되지 않으면 페더레이션 사용자에 대해 현재 상태가 자동으로 구독 되지 않습니다.
        - 페더레이션 도메인 간에는 착신 전환이 작동 하지 않습니다.
        - 통화 전송 시나리오가 더 제한 됩니다.
        - 제한 사항이 페더레이션 트래픽에 적용 될 수 있습니다.
- 이러한 비대칭 환경이 제공 되는 경우 온-프레미스 사용자와 온-프레미스 디렉터리에 없는 클라우드 사용자 간의 크로스-프레미스 시나리오에서의 통화 기능에 대 한 공식적인 지원은 피어 간 전용으로 제한 됩니다. 
    - 이러한 사용자 간의 착신 전환, 전송, 통화 큐 등은 지원 되지 않습니다.
    - 지원 되지 않는 이러한 통화 시나리오는 계속 사용 하도록 설정 되지만 대부분의 경우 예기치 않은 방식으로 오류가 발생 합니다. 
    - 위의 **[그림 D](#figure-d)** 에서는 사용자 E가 온-프레미스이 고 사용자 A, B 또는 C를 사용한 통화는 피어 투 피어로만 지원 됩니다. 사용자 D와의 통화에는 지원 제한이 없습니다.  그러나 온-프레미스 사용자 E가 클라우드로 이동 된 후에는이 제한이 더 이상 적용 되지 않습니다.
- 사용자 환경에 비즈니스용 Skype 서버 2019의 배포를 두 개 이상 사용 하는 경우 해당 기능에 비즈니스용 Skype 서버 하이브리드 구성이 필요 하기 때문에 해당 배포 중 하나를 조직 자동 전화 교환에서 구성할 수 있습니다. 
- 이전 단계의 일부 순서를 조정할 수 있습니다. 이러한 사항이 모두 참인 경우에는 다음과 같은 주요 요구 사항을 충족 해야 합니다.
    - 단일 AAD 테 넌 트에 동기화 하는 온-프레미스 비즈니스용 Skype 포리스트가 두 개 이상 있습니다.
    - 단일 온-프레미스 포리스트를 사용 하 여 분할 도메인 사용
    - 하이브리드 조직에 있는 사용자 한 명 이상이 클라우드로 마이그레이션 되었습니다.<br>   그런 다음 다른 모든 온라인 SIP 도메인을 다른 온-프레미스 비즈니스용 Skype 포리스트에서 사용 하지 않도록 설정 *해야 합니다* . 그렇지 않으면 하이브리드 조직의 온라인 사용자와 다른 조직의 온-프레미스 사용자 간의 페더레이션이 한 방향으로 중단 됩니다.

## <a name="implications"></a>상당한

- 위에서 설명한 고급 통화 기능에 대 한 지원에는 제한이 있으므로, **조직은 마이그레이션의 일부로 이러한 비대칭 상태를 일시적으로 처리 해야 하며, 안정적인 상태로 전환 하지는 않습니다**.  
- 여러 온-프레미스 비즈니스용 Skype 배포를 사용 하는 조직은 일반적으로 클라우드로 완전히 마이그레이션될 수 있는 배포로 시작 해야 통합을 계속할 수 있습니다. 어떤 경우에는 아직 팀으로 이동할 수 없는 특정 사용자 그룹이 holdouts 것을 이해 하 고 있습니다. 여러 비즈니스용 Skype 포리스트가 포함 된 시나리오에서 고려해 야 할 사항은 가능한 경우 이러한 제한이 없는 다른 포리스트로 마이그레이션을 시작 합니다.
- 온-프레미스에서 클라우드로 이동 하는 경우 대리인에 게 위임 관계가 있거나 일반적으로 통화 전달에 관여 하는 사용자는 하나의 단위로 함께 이동 해야 합니다.

## <a name="considerations-for-moving-to-teamsonly-mode"></a>TeamsOnly 모드로 전환할 때의 고려 사항

하이브리드 환경에서 사용자를 온-프레미스에서 클라우드로 이동 하는 경우 비즈니스용 Skype 전용 또는 TeamsOnly 모드로 이동할 수 있습니다. *사용자를 TeamsOnly 모드로 이동 하려는 경우 먼저이 섹션을 읽어야 합니다.*

- TeamsOnly 모드를 사용자에 게 할당 하면 다른 사용자의 모든 채팅 및 통화가 해당 사용자의 팀 클라이언트에 배치 됩니다. 
- 비즈니스용 Skype 온-프레미스 사용자가 주로 비즈니스용 skype 클라이언트를 사용 하 고 팀이 아닌 경우에는 해당 온-프레미스 사용자에 대 한 라우팅이 팀 대신 비즈니스용 Skype에 연결 되도록 TeamsUpgradePolicy를 설정 하는 것이 좋습니다. TeamsOnly와 아직 비즈니스용 Skype를 사용 하는 사용자 간의 채팅 및 통화에 대 한 적절 한 라우팅이 가능 하도록 하려면 온-프레미스 사용자에 게는 TeamsUpgradePolicy가 아닌 SfB 모드 중 하나를 사용 하 여 유효한 값을 입력 해야 합니다 ( 기본값) 
    - 이 작업을 수행 하려면 *먼저 TeamsUpgradePolicy의 테 넌 트의 전역 인스턴스를 다음 값 중 하나로 설정 해야 합니다*.
        - SfBWithTeamsCollab (권장)
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 다음 명령을 사용 하 여 테 넌 트 전체 정책을 부여할 수 있습니다.<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 참고: 온라인 디렉터리에서 SIP 주소가 없는 개별 사용자에 게 정책을 할당할 수 없기 때문에 테 넌 트 차원 수준에서이 작업을 수행 해야 합니다. 순수한 온-프레미스 배포에 대해 온라인 SIP 도메인을 사용 하지 않도록 설정한 경우 해당 도메인의 사용자는 디자인을 통해 온라인 디렉터리에 SIP 주소를 갖고 있지 않습니다. 따라서 이러한 온-프레미스 사용자에 게 정책을 적용 하는 유일한 방법은 테 넌 트 수준에서 할당 하는 것입니다. 반면, 하이브리드 배포 사용자는 온라인 디렉터리에 SIP 주소를 할당 하 여 테 넌 트 전역 정책과는 다른 값을 갖도록 하려는 경우에는 정책을 명시적으로 할당할 수 있습니다.
- 팀 클라이언트 UX는 아직 TeamsUpgradePolicy의 SfB 모드를 준수 하지 않습니다. 예를 들어 이러한 모드에서는 나중에이 경우에도 발생할 수 있지만 현재 팀에서 통화 및 채팅을 시작할 수 있습니다. 이로 인해 회신이 때때로 팀 이나 가끔씩 비즈니스용 Skype에 있을 수도 있으므로 상황에 따라 혼란을 야기할 수 있습니다. 아직 온-프레미스 상태인 사용자의 경우에는 TeamsMessagingPolicy 및 Teamsmessagingpolicy를 통해 통화 및 채팅을 개별적으로 사용 하지 않도록 설정 하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목

[에 지 인증서 업데이트](cloud-consolidation-edge-certificates.md)

[두 개 이상의 포리스트를 포함 하도록 AAD 연결 업데이트](cloud-consolidation-aad-connect.md)

[클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화](cloud-consolidation-disabling-hybrid.md)
