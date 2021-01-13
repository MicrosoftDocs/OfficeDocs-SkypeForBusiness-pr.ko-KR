---
title: 감시자 노드 설치 및 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: '요약: 비즈니스용 Skype 서버 가상 트랜잭션에 대한 감시자 노드를 설치하고 구성합니다.'
ms.openlocfilehash: f6d3db973291b8a41647a3c4a4d3c3530c7af019
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812760"
---
# <a name="install-and-configure-watcher-nodes"></a>감시자 노드 설치 및 구성
 
**요약:** 비즈니스용 Skype 서버 가상 트랜잭션에 대한 감시자 노드를 설치하고 구성합니다.
  
감시자 노드는 주기적으로 비즈니스용 Skype 서버 가상 트랜잭션을 실행하는 컴퓨터입니다. 가상 트랜잭션은 Windows PowerShell 인스턴트 메시지를 교환하는 등의 주요 사용자 시나리오가 예상대로 작동하고 있는지 확인하는 cmdlet입니다. 비즈니스용 Skype 서버 2015의 경우 System Center Operations Manager는 다음 표에 나와 있는 가상 트랜잭션을 실행할 수 있습니다. 여기에는 세 가지 가상 트랜잭션 유형이 포함됩니다.
  
- **기본값** 감시자 노드가 기본적으로 실행되는 가상 트랜잭션입니다. 새 감시자 노드를 만들 때 해당 노드가 실행될 가상 트랜잭션을 지정할 수 있습니다. 이 매개 변수는 이 cmdlet에서 사용되는 Tests 매개 New-CsWatcherNodeConfiguration 사용됩니다. 감시자 노드를 만들 때 Tests 매개 변수를 사용하지 않는 경우 모든 기본 가상 트랜잭션이 자동으로 실행되고 기본이 아닌 가상 트랜잭션이 실행되지 않습니다. 예를 들어 감시자 노드가 Test-CsAddressBookService 실행하도록 구성되지만 감시자 노드는 Test-CsExumConnectivity 실행하도록 구성되지 않습니다.
    
- **기본값이 아닌 경우** 감시자 노드가 기본적으로 실행되지 않는 테스트입니다. 자세한 내용은 기본 형식에 대한 설명을 참조하세요. 그러나 감시자 노드를 사용하도록 설정하여 기본이 아닌 가상 트랜잭션을 실행할 수 있습니다. 감시자 노드를 만들 때(New-CsWatcherNodeConfiguration cmdlet을 사용하여) 감시자 노드를 만들 때 또는 감시자 노드가 만들어진 후 이 작업을 할 수 있습니다. 대부분의 비기기 가상 트랜잭션에는 추가 설정 단계가 필요합니다. 이러한 단계에 대한 자세한 내용은 가상 트랜잭션에 대한 특수 [설치 지침을 참조하세요.](test-users-and-settings.md#special_synthetictrans)
    
- **확장** 기본이 아닌 가상 트랜잭션의 특별한 유형입니다. 다른 가상 트랜잭션과 달리 확장 테스트는 한 번의 테스트 과정 중에 여러 번 실행할 수 있습니다. 이 기능은 풀의 여러 PSTN(Public Switched Telephone Network) 음성 경로와 같은 동작을 확인할 때 유용합니다. 감시자 노드에 확장 테스트의 여러 인스턴스를 추가하여 이 작업을 구성할 수 있습니다.
    
감시자 노드에 다른 가상 트랜잭션을 추가하는 프로세스에 대한 자세한 내용은 가상 트랜잭션을 실행하도록 감시자 [노드 구성을 참조합니다.](watcher-nodes.md#enable_synthetic_trans) 비즈니스용 Skype 서버 관리 셸을 사용하여 감시자 노드에서 가상 트랜잭션을 제거할 수 있습니다.
  
감시자 노드에서 사용할 수 있는 가상 트랜잭션에는 다음 항목이 포함됩니다.
  
|**Cmdlet 이름(테스트 이름)**|**설명**|
|:-----|:-----|
|Test-CsAddressBookService(ABS)  <br/> |사용자가 자신의 연락처 목록에 없는 사용자를 확인할 수 있도록 합니다.  <br/> |
|Test-CsAddressBookWebQuery(ABWQ)  <br/> |사용자가 HTTP를 통해 연락처 목록에 없는 사용자를 확인할 수 있도록 합니다.  <br/> |
|Test-CsAVConference(AvConference)  <br/> |사용자가 오디오/비디오 회의를 만들고 참가할 수 있는지 확인합니다.  <br/> |
|Test-CsGroupIM(IM 회의)  <br/> |사용자가 회의 중 인스턴트 메시지를 보내고 3명 이상의 사용자가 포함된 인스턴트 메시지 대화에 참가할 수 있는지 확인합니다.  <br/> |
|Test-CsIM(P2P IM)  <br/> |사용자가 피어 투 피어 인스턴트 메시지를 보낼 수 있는지 확인합니다.  <br/> |
|Test-CsP2PAV(P2PAV)  <br/> |사용자가 피어 투 피어 음성 통화를 걸 수 있는지 확인합니다(신호만).  <br/> |
|Test-CsPresence(Presence)  <br/> |사용자가 다른 사용자의 현재 상태 정보를 볼 수 있도록 합니다.  <br/> |
|Test-CsRegistration(Registration)  <br/> |사용자가 비즈니스용 Skype에 로그인할 수 있도록 합니다.  <br/> |
|Test-CsPstnPeerToPeerCall(PSTN)  <br/> |사용자가 기업 외부에 있는 사용자와 통화를 걸거나 받을 수 있는지 확인합니다(PSTN 번호).  <br/> |
|Test-CsASConference(ASConference)  <br/> |사용자가 응용 프로그램 공유 회의를 만들고 참가할 수 있도록 합니다.  <br/> |
|Test-CsAVEdgeConnectivity(AVEdgeConnectivity)  <br/> |오디오 비디오 에지 서버가 피어 투 피어 통화 및 전화 회의 통화에 대한 연결을 허용할 수 있도록 합니다.  <br/> |
|Test-CsDataConference(DataConference)  <br/> |사용자가 데이터 공동 작업 회의(화이트보드 및 설문 조사와 같은 활동을 포함하는 온라인 모임)에 참가할 수 있도록 합니다.  <br/> |
|Test-CsDialinConferencing(DialinConferencing)  <br/> |사용자가 전화 번호로 전화 회의에 참가할 수 있도록 합니다.  <br/> |
|Test-CsDialinConferencing(DialinConferencing)  <br/> |사용자가 전화 번호로 전화 회의에 참가할 수 있도록 합니다.  <br/> |
|Test-CsExumConnectivity(ExumConnectivity)  <br/> |사용자가 Exchange UM(통합 메시징)에 연결할 수 있도록 합니다.  <br/> |
|Test-CsGroupIM -TestJoinLauncher(JoinLauncher)  <br/> |사용자가 웹 주소 링크를 통해 예약된 모임을 만들고 참가할 수 있도록 합니다.  <br/> |
|Test-CsMCXP2PIM(MCXP2PIM)  <br/> |모바일 장치 사용자가 등록하고 인스턴트 메시지를 보낼 수 있는지 확인합니다.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV(P2PVideoInteropServerSipTrunkAV)  <br/> |비디오 SIP 트렁크를 통해 비디오 Interop 서버가 설치 및 들어오는 연결을 처리할 수 있는지 확인합니다.  <br/> **참고:** 레거시 모바일 클라이언트에 대한 MCX 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. |
|Test-CsPersistentChatMessage(PersistentChatMessage)  <br/> |사용자가 영구 채팅 서비스를 사용하여 메시지를 교환할 수 있도록 합니다.  <br/> |
|Test-CsUcwaConference(UcwaConference)  <br/> |사용자가 웹을 통해 전화 회의에 참가할 수 있도록 합니다.  <br/> |
|Test-CsUnifiedContactStore(UnifiedContactStore)  <br/> |통합 연락처 저장소를 사용해서 사용자의 연락처에 액세스할 수 있는지 확인합니다. 사용자는 통합 연락처 저장소를 통해 비즈니스용 Skype 서버 2015, Outlook 메시징 및 공동 작업 클라이언트 및/또는 Outlook Web Access를 사용하여 액세스할 수 있는 단일 연락처 집합을 유지 관리하는 방법을 제공합니다.  <br/> |
|Test-CsXmppIM(XmppIM)  <br/> |XMPP(Extensible Messaging and Presence Protocol) 게이트웨이를 통해 인스턴트 메시지를 보낼 수 있도록 합니다.  <br/> XMPP 게이트웨이 및 XMPP 게이트웨이는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.  |

System Center Operations Manager를 사용하기 위해 감시자 노드를 설치할 필요가 없습니다. 이러한 노드를 설치하지 않은 경우 문제가 발생할 때마다 비즈니스용 Skype 서버 2015 구성 요소에서 실시간 알림을 받을 수 있습니다. 구성 요소 및 사용자 관리 팩은 감시자 노드를 사용하지 않습니다. 그러나 활성 모니터링 관리 팩을 사용하여 종단 내 시나리오를 모니터링하려면 감시자 노드가 필요합니다.
  
> [!NOTE]
> 관리자는 Operations Manager를 사용하지 않고 설치하지 않고도 가상 트랜잭션을 수동으로 실행할 수도 있습니다. 비즈니스용 Skype 서버 배포의 크기에 따라 가상 트랜잭션은 많은 양의 컴퓨터 메모리와 프로세서 시간을 사용할 수 있습니다. 따라서 전용 컴퓨터를 감시자 노드로 사용하는 것이 좋습니다. 예를 들어 감시자 노드 역할을 하도록 비즈니스용 Skype 서버 프런트 엔드 서버를 구성하면 안 됩니다. 감시자 노드는 비즈니스용 Skype 서버 토폴로지의 다른 컴퓨터와 동일한 기본 하드웨어 요구 사항을 충족해야 합니다. 
  
> [!NOTE]
> Lync Server 2013 및 비즈니스용 Skype 서버 2015의 핵심 시스템 파일을 동일한 컴퓨터에 설치할 수 없는 경우 레거시 Lync Server 2013 감시자 노드를 비즈니스용 Skype 서버 2015 감시자 노드와 동일한 컴퓨터에 함께 설치할 수 없습니다. 그러나 비즈니스용 Skype 서버 2015 감시자 노드는 비즈니스용 Skype 서버 2015 및 Lync Server 2013을 동시에 모니터링할 수 있습니다. 기본 가상 트랜잭션은 두 제품 버전에서 모두 지원됩니다. 
  
Lync Server 2013 감시자 노드는 다음을 확인하기 위해 엔터프라이즈 내부 또는 외부에 배포될 수 있습니다.
  
- 기업 내부의 사용자 풀에 대한 연결
    
- 엔터프라이즈 외부에서 작업하는 원격 사용자를 위한 경계 네트워크를 통한 연결
    
- 지점 사무소 기기에 대한 연결
    
- 엔터프라이즈 내부 및 경계 네트워크를 통해 Lync Server 2013에 연결합니다.
    
관리를 간소화하기 위해 기업 내부 및 외부에서 다양한 인증 옵션을 사용할 수 있습니다. 자세한 내용은 가상 트랜잭션을 [실행하도록 감시자 노드 구성을 참조합니다.](watcher-nodes.md#enable_synthetic_trans)
  
컴퓨터가 감시자 노드 역할을 하도록 구성하려면 먼저 다음의 선행 작업을 완료해야 합니다. 
  
- System Center Operations Manager를 설치하고 비즈니스용 Skype 서버 2015 관리 팩을 가져올 수 있습니다. 또한 먼저 감시자 노드 컴퓨터가 비즈니스용 Skype 서버 2015 설치를 위한 모든 선행 요구 사항을 충족하는지 확인해야 합니다.
    
- 감시자 노드 컴퓨터에 다음 항목을 설치합니다.
    
  - .NET Framework 4.5의 정식 버전
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
선행 구성이 충족되면 다음 단계에 따라 감시자 노드를 구성할 수 있습니다.
  
1. 감시자 노드 컴퓨터에 비즈니스용 Skype 서버 2015 핵심 파일을 설치합니다.
    
2. 감시자 노드 컴퓨터에 System Center Operations Manager 에이전트를 설치합니다.
    
3. 실행 Watchernode.msi 실행 파일을 실행합니다.
    
4. **New-CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드에서 사용할 테스트 사용자 계정을 구성합니다.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>비즈니스용 Skype 서버 2015 핵심 파일 및 RTCLocal 데이터베이스 설치

컴퓨터에 비즈니스용 Skype 서버 2015 핵심 파일을 설치하려면 다음 절차를 완료합니다. 핵심 파일을 설치할 때 RTCLocal 데이터베이스가 자동으로 설치됩니다. 감시자 노드에 SQL Server 설치할 필요가 없습니다. SQL Server Express가 자동으로 설치됩니다.
  
비즈니스용 Skype 서버 2015 핵심 파일 및 RTCLocal 데이터베이스를 설치하려면
  
1. 감시자 노드 컴퓨터에서 시작, 모든 프로그램,  보조 프로그램을 차례로 클릭하고 명령 프롬프트를 마우스 오른쪽 단추로 클릭한 후 관리자로 실행을 클릭합니다.
    
2. 콘솔 창에서 다음 명령을 입력하고 Enter를 클릭합니다. 비즈니스용 Skype 서버 설치 파일에 대한 적절한 경로를 입력해야 합니다. D:\Setup.exe /BootstrapLocalMgmtTo는 핵심 비즈니스용 Skype 서버 구성 요소가 성공적으로 설치되어 있는지 확인하고 시작, 모든 프로그램, 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 **Skype** 서버 관리 셸을 클릭합니다. 비즈니스용 Skype 서버 관리 셸에서 다음 Windows PowerShell 입력하고 Enter를 누르고 있습니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 이 명령을 처음 실행할 때 감시자 노드 컴퓨터를 아직 구성하지 않았기 때문에 데이터가 반환되지 않습니다. 명령이 오류를 반환하지 않고 실행되는 경우 비즈니스용 Skype 서버 설치가 완료된 것으로 가정할 수 있습니다. 
  
감시자 노드 컴퓨터가 경계 네트워크 내부에 있는 경우 다음 명령을 실행하여 비즈니스용 Skype 서버 2015의 설치를 확인할 수 있습니다.
  
Get-CsPinPolicyYou 사용하도록 구성된 PIN 정책의 수에 따라 이와 유사한 정보가 수신됩니다.
  
ID : Global
  
설명 :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
PIN 정책에 대한 정보가 표시되면 핵심 구성 요소가 성공적으로 설치되었습니다.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>감시자 노드에 Operation Manager 에이전트 파일 설치

구성 요소 경고를 보고하기 위한 비즈니스용 Skype 서버 설정과 마찬가지로 비즈니스용 Skype 서버 2015 감시자 노드를 사용하려면 System Center Operations Manager 에이전트 파일을 설치해야 합니다. 이렇게 하면 가상 트랜잭션을 실행하고 경고를 System Center Operations Manager 루트 관리 서버에 보고할 수 있습니다.
  
에이전트 파일을 설치하려면 모니터링할 비즈니스용 Skype 서버 컴퓨터 구성에 나열된 절차를 [수행하십시오.](configure-computers-to-monitor.md)
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>가상 트랜잭션을 실행하도록 감시자 노드 구성
<a name="enable_synthetic_trans"> </a>

System Center Operations Manager 에이전트 파일을 설치한 후 감시자 노드 자체를 구성해야 합니다. 이를 위해 수행되는 단계는 감시자 노드 컴퓨터가 경계 네트워크 내부에 있는지 또는 경계 네트워크 외부에 있는지에 따라 달라집니다. 
  
감시자 노드를 구성할 때 해당 노드에서 사용할 인증 방법 유형도 선택해야 합니다. 비즈니스용 Skype 서버 2015에서는 신뢰할 수 있는 서버 또는 자격 증명 인증의 두 가지 인증 방법 중 하나를 선택할 수 있습니다. 다음 표에서는 이러한 두 방법 간의 차이점을 보여 주었다.
  
||**설명**|**지원되는 위치**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |인증서를 사용하여 내부 서버를 가장하고 인증 챌린지 무시  <br/> 각 감시자 노드에서 여러 사용자 암호 대신 단일 인증서를 관리하고자 하는 관리자에게 유용합니다.  <br/> |엔터프라이즈 내부.  <br/> 이 방법을 사용하면 감시자 노드가 모니터링되는 풀과 동일한 도메인에 있어야 합니다. 감시자 노드와 풀이 서로 다른 도메인에 있는 경우 자격 증명 인증을 대신 사용합니다.  <br/> |
|협상  <br/> |각 감시자 노드의 Windows 자격 증명 관리자에 사용자 이름과 암호를 안전하게 저장합니다.  <br/> 이 모드에서는 더 많은 암호 관리가 필요하지만 엔터프라이즈 외부의 감시자 노드에 대한 유일한 옵션입니다. 이러한 감시자 노드는 인증에 대해 신뢰할 수 있는 끝점으로 취급될 수 없습니다.  <br/> |엔터프라이즈 외부.  <br/> 엔터프라이즈 내부.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>신뢰할 수 있는 서버 인증을 사용하도록 감시자 노드 구성
<a name="enable_synthetic_trans"> </a>

감시자 노드 컴퓨터가 경계 네트워크 내부에 있는 경우 신뢰할 수 있는 서버 인증을 사용하는 경우 많은 사용자 계정 암호를 사용하는 대신 단일 인증서를 유지 관리하여 관리 작업을 크게 줄일 수 있습니다.
  
신뢰할 수 있는 서버 인증을 구성하려면 먼저 감시자 노드 컴퓨터를 호스트할 신뢰할 수 있는 응용 프로그램 풀을 만들어야 합니다. 신뢰할 수 있는 응용 프로그램 풀을 만든 후 해당 감시자 노드에서 가상 트랜잭션을 신뢰할 수 있는 응용 프로그램으로 실행하도록 구성해야 합니다.
  
> [!NOTE]
> 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버 2015의 일부로 실행하기 위한 신뢰할 수 있는 상태가 제공되지만 제품의 기본 제공 부분이 아닌 응용 프로그램입니다. 신뢰 상태란 응용 프로그램이 실행될 때마다 응용 프로그램에 인증을 요청하지 않는 상태를 의미합니다.
  
신뢰할 수 있는 응용 프로그램 풀을 만들 경우 비즈니스용 Skype 서버 관리 셸을 열고 다음 명령을 실행합니다.
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 위의 명령의 매개 변수에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 프롬프트에 다음을 입력합니다. 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

신뢰할 수 있는 응용 프로그램 풀을 만들고 나면 **New-CsTrustedApplication** cmdlet 및 이와 유사한 명령을 사용하여 가상 트랜잭션을 신뢰할 수 있는 응용 프로그램으로 실행하도록 감시자 노드 컴퓨터를 구성할 수 있습니다.
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

이 명령이 완료되면 신뢰할 수 있는 응용 프로그램을 만들 때 **Enable-CsTopology** cmdlet을 실행하여 변경 내용이 적용될 수 있도록 해야 합니다.
  
```PowerShell
Enable-CsTopology
```

감시자 노드 컴퓨터 계정은 일부 가상 트랜잭션에 대해 CMS를 쿼리하는 기능을 필요로 합니다. 이 기능을 허용하려면 감시자 노드의 컴퓨터 계정을 RTCUniversalReadOnlyAdmins 보안 그룹에 추가합니다. AD 복제가 발생한 후 컴퓨터를 다시 시작합니다.
  
신뢰할 수 있는 새 응용 프로그램이 만들어졌습니다. 비즈니스용 Skype 서버 관리 셸 프롬프트에 다음을 입력합니다.
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>감시자 노드에서 기본 인증서 구성
<a name="enable_synthetic_trans"> </a>

TrustedServer 인증을 사용하는 각 감시자 노드에는 비즈니스용 Skype 서버 배포 마법사를 사용하여 기본 인증서가 할당되어 있어야 합니다. 
  
기본 인증서를 할당합니다.
  
1. 시작, 모든 프로그램, 비즈니스용 Skype 서버 2015, 비즈니스용 Skype 서버 배포 마법사를 클릭합니다. 
    
2. 비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 Skype 서버 시스템 설치 또는 업데이트를 클릭한 다음 제목의 인증서 요청, 설치 또는 할당에서 실행을 클릭합니다. 
    
> [!NOTE]
> 실행 단추가 해제된 경우 로컬 구성 저장소 설치 아래에서 먼저 실행을 클릭해야 할 수 있습니다. 
  
다음 중 하나를 수행합니다.
  
- 기본 인증서로 사용할 수 있는 인증서가 이미 있는 경우 인증서 마법사에서 기본값을 클릭한 다음 할당을 클릭합니다. 인증서 지정 마법사의 단계에 따라 해당 인증서를 지정합니다.
    
- 기본 인증서를 사용하기 위해 인증서를 요청해야 하는 경우 요청을 클릭한 다음 인증서 요청 마법사의 단계에 따라 해당 인증서를 요청합니다. 웹 서버 인증서에 대한 기본값을 사용하면 기본 인증서로 지정할 수 있는 인증서가 표시됩니다.
    
## <a name="install-and-configure-a-watcher-node"></a>감시자 노드 설치 및 구성
<a name="enable_synthetic_trans"> </a>

감시자 노드 컴퓨터를 다시 시작하고 인증서를 구성한 후 이 파일을 실행해야 Watchernode.msi. Operations Manager Watchernode.msi 및 비즈니스용 Skype 서버 2015 핵심 구성 요소가 모두 설치된 모든 컴퓨터에서 이 파일을 실행해야 합니다. 
  
감시자 노드를 설치하고 구성하려면
  
1. 시작, 모든 프로그램, 비즈니스용 Skype 서버 2015, 비즈니스용 Skype 서버 관리 셸을 클릭하여 비즈니스용 Skype 서버 관리 셸을 열 수 있습니다. 
    
2. 관리 셸에서 다음 명령을 입력한 다음 Enter를 누를 수 있습니다(데이터베이스 복사본에 대한 실제 경로를 지정해야 Watchernode.msi.
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> 명령 창에서 Watchernode.msi n을 실행할 수도 있습니다. 명령 창을 열려면 시작을 클릭하고 명령 프롬프트를 마우스 오른쪽 단추로 클릭한 후 관리자로 실행을 클릭합니다. 명령 창이 열리면 위의 2단계에 표시된 동일한 명령을 입력합니다. 
  
> [!IMPORTANT]
> 위의 명령에서 이름/값 쌍 Authentication=TrustedServer는 대/소문자 구분을 합니다. 표시된 그대로 입력해야 합니다. 예를 들어 다음 명령은 올바른 문자 대/소문자를 사용하지 못하기 때문에 실패합니다. 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

TrustedServer 모드는 경계 네트워크 내부에 있는 컴퓨터에서만 사용할 수 있습니다. 감시자 노드가 TrustedServer 모드에서 실행되는 경우 관리자는 컴퓨터에서 테스트 사용자 암호를 유지 관리하지 않습니다.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>협상을 사용하도록 감시자 노드 구성
<a name="enable_synthetic_trans"> </a>

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 감시자 노드가 가상 트랜잭션을 실행하도록 구성하려면 약간 다른 절차를 따라야 합니다. 특히 신뢰할 수 있는 응용 프로그램 풀 또는 신뢰할 수 있는 응용 프로그램을 만들면 안 됩니다. 즉, 다음 두 작업을 완료해야 합니다.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC Local Read-Only Administrators 그룹의 구성원 업데이트

감시자 노드가 경계 네트워크 외부에 있는 경우 감시자 노드에서 다음 절차를 완료하여 감시자 노드 컴퓨터의 RTC 로컬 읽기 전용 Administrators 그룹에 네트워크 서비스 계정을 추가해야 합니다.
  
1. 시작을 클릭하고 컴퓨터를 마우스 오른쪽 단추로 클릭한 다음 관리를 클릭합니다.
    
2. 서버 관리자에서 구성, 로컬 사용자 및 그룹을 차례로 확장한 다음 그룹을 클릭합니다.
    
3. 그룹 창에서 RTC Local Read-only Administrators를 두 번 클릭합니다.
    
4. RTC Local Read-only Administrators 속성 대화 상자에서 추가를 클릭합니다.
    
5. 사용자, 컴퓨터, 서비스 계정 또는 그룹 선택 대화 상자에서 위치를 클릭합니다.
    
6. 위치 대화 상자에서 감시자 노드 컴퓨터의 이름을 선택하고 확인을 클릭합니다.
    
7. 선택할 개체 이름을 입력하십시오. 상자에 네트워크 서비스를 입력하고 확인을 클릭합니다.
    
8. RTC Local Read-only Administrators 속성 대화 상자에서 확인를 클릭하고 서버 관리자를 닫습니다.
    
9. 감시자 노드 컴퓨터를 다시 시작합니다.
    
### <a name="install-the-watcher-node-configuration-files"></a>감시자 노드 구성 파일 설치

다음 단계에서는 다음을 통해 파일을 Watchernode.msi. 
  
1. Microsoft 비즈니스용 Skype 서버 2015 관리 셸을 열 수 있습니다. 시작, 모든 프로그램, Microsoft 비즈니스용 Skype 서버 2015를 클릭한 다음 비즈니스용 Skype 서버 관리 셸을 클릭합니다. 
    
2. 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누르고(데이터베이스 복사본에 대한 실제 경로를 지정해야 Watchernode.msi.
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 앞서 설명한 Watchernode.msi 창에서 실행될 수도 있습니다. 명령 창을 열려면 **시작** 을 클릭하고 **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행** 을 클릭합니다. 명령 창이 열리면 위의 2단계에 표시된 동일한 명령을 입력합니다. 
  
감시자 노드를 신뢰할 수 있는 응용 프로그램 풀로 설정할 수 없는 경우에는 항상 협상 모드가 사용됩니다. 이 모드에서는 관리자가 감시자 노드에 대한 테스트 사용자 암호를 관리해야 합니다.
  

