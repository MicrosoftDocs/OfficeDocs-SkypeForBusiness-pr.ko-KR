---
title: 감시자 노드 설치 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버 가상 트랜잭션에 대 한 감시자 노드를 설치 및 구성 합니다.'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2020
ms.locfileid: "48599920"
---
# <a name="install-and-configure-watcher-nodes"></a>감시자 노드 설치 및 구성
 
**요약:** 비즈니스용 Skype 서버 가상 트랜잭션에 대 한 감시자 노드를 설치 및 구성 합니다.
  
감시자 노드는 비즈니스용 Skype 서버 가상 트랜잭션을 주기적으로 실행 하는 컴퓨터입니다. 가상 트랜잭션은 로그인 또는 exchange 인스턴트 메시지와 같은 주요 사용자 시나리오가 예상 대로 작동 하는지 확인 하는 Windows PowerShell cmdlet입니다. 비즈니스용 Skype 서버 2015의 경우 System Center Operations Manager는 세 가지 가상 트랜잭션 유형이 포함 된 다음 표에 표시 된 가상 트랜잭션을 실행할 수 있습니다.
  
- **기본** 감시자 노드가 기본적으로 실행 하는 가상 트랜잭션입니다. 새 감시자 노드를 만들 때 해당 노드가 실행 될 가상 트랜잭션을 지정할 수 있습니다. 이는 New-CsWatcherNodeConfiguration cmdlet에서 사용 되는 테스트 매개 변수의 용도입니다. 감시자 노드를 만들 때 테스트 매개 변수를 사용 하지 않으면 기본 가상 트랜잭션이 모두 자동으로 실행 되며 비기본 가상 트랜잭션이 실행 되지 않습니다. 예를 들어 감시자 노드가 Test-CsAddressBookService 테스트를 실행 하도록 구성 되지만 Test-CsExumConnectivity 테스트를 실행 하도록 구성 되지는 않습니다.
    
- **비기본** 감시자 노드가 기본적으로 실행 되지 않도록 테스트 합니다. 자세한 내용은 기본 유형의 설명을 참조 하십시오. 그러나 기본이 아닌 가상 트랜잭션을 실행 하도록 감시자 노드를 사용 하도록 설정할 수 있습니다. New-CsWatcherNodeConfiguration cmdlet을 사용 하 여 감시자 노드를 만들거나, 감시자 노드를 만든 후에는 언제 든 지이 작업을 수행할 수 있습니다. 대부분의 비기본 가상 트랜잭션에는 추가 설정 단계가 필요 합니다. 이러한 단계에 대 한 자세한 내용은 [가상 트랜잭션에 대 한 특별 설치 지침](test-users-and-settings.md#special_synthetictrans)을 참조 하십시오.
    
- **확장** 기본이 아닌 특별 한 가상 트랜잭션 유형 다른 가상 트랜잭션과 달리 확장 테스트는 한 번의 테스트 과정 중에 여러 번 실행할 수 있습니다. 이 기능은 풀에 대 한 여러 개의 PSTN (공중 전화망) 음성 경로와 같은 동작을 확인할 때 유용 합니다. 확장 테스트의 여러 인스턴스를 감시자 노드에 추가 하기만 하면이를 구성할 수 있습니다.
    
다른 가상 트랜잭션을 감시자 노드에 추가 하는 프로세스에 대 한 자세한 내용은 [가상 트랜잭션을 실행 하도록 감시자 노드 구성](watcher-nodes.md#enable_synthetic_trans)를 참조 하십시오. 비즈니스용 Skype 서버 관리 셸을 사용 하 여 감시자 노드에서 가상 트랜잭션을 제거할 수도 있습니다.
  
감시자 노드에서 사용할 수 있는 가상 트랜잭션에는 다음 항목이 포함됩니다.
  
|**Cmdlet 이름(테스트 이름)**|**설명**|
|:-----|:-----|
|Test-CsAddressBookService(ABS)  <br/> |사용자가 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인 합니다.  <br/> |
|Test-CsAddressBookWebQuery(ABWQ)  <br/> |사용자가 HTTP를 통해 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인 합니다.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |사용자가 오디오/비디오 회의를 만들고 참가할 수 있는지 확인합니다.  <br/> |
|Test-CsGroupIM (IM 회의)  <br/> |사용자가 회의 중 인스턴트 메시지를 보내고 3명 이상의 사용자가 포함된 인스턴트 메시지 대화에 참가할 수 있는지 확인합니다.  <br/> |
|Test-CsIM (P2P IM)  <br/> |사용자가 피어 투 피어 인스턴트 메시지를 보낼 수 있는지 확인합니다.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |사용자가 피어 투 피어 음성 통화를 걸 수 있는지 확인합니다(신호만).  <br/> |
|Test-CsPresence(Presence)  <br/> |사용자가 다른 사용자의 현재 상태를 볼 수 있는지 확인 합니다.  <br/> |
|Test-CsRegistration(Registration)  <br/> |사용자가 비즈니스용 Skype에 로그인 할 수 있는지 확인 합니다.  <br/> |
|Test-CsPstnPeerToPeerCall(PSTN)  <br/> |사용자가 기업 외부에 있는 사용자와 통화를 걸거나 받을 수 있는지 확인합니다(PSTN 번호).  <br/> |
|Test-CsASConference (ASConference)  <br/> |사용자가 응용 프로그램 공유 회의를 만들고 참가할 수 있는지 확인 합니다.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |오디오 비디오에 지 서버가 피어 투 피어 통화 및 전화 회의 통화에 대 한 연결을 허용할 수 있는지 확인 합니다.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |사용자가 데이터 공동 작업 회의 (예: 화이트 보드 및 설문 조사와 같은 활동을 포함 하는 온라인 모임)에 참가할 수 있는지 확인 합니다.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |사용자가 전화 회의에 참석할 수 있는 번호로 전화를 걸 수도 있는지 확인 합니다.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |사용자가 전화 회의에 참석할 수 있는 번호로 전화를 걸 수도 있는지 확인 합니다.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |사용자가 Exchange UM (통합 메시징)에 연결할 수 있는지 확인 합니다.  <br/> |
|Test-CsGroupIM-TestJoinLauncher 관리자 (Join시작 관리자)  <br/> |사용자가 웹 주소 링크를 통해 예약 된 모임을 만들고 참가할 수 있는지 확인 합니다.  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |모바일 장치 사용자가 등록하고 인스턴트 메시지를 보낼 수 있는지 확인합니다.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |비디오 Interop 서버가 작동 하 고 비디오 SIP 트렁크를 통해 들어오는 연결을 처리할 수 있는지 확인 합니다.  <br/> **참고:** 이전 모바일 클라이언트에 대 한 MCX 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |사용자가 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있는지 확인 합니다.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |사용자가 웹을 통해 회의에 참가할 수 있는지 확인 합니다.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |통합 연락처 저장소를 사용해서 사용자의 연락처에 액세스할 수 있는지 확인합니다. 통합 연락처 저장소는 비즈니스용 Skype 서버 2015, Outlook 메시징 및 공동 작업 클라이언트 및/또는 Outlook Web Access를 사용 하 여 액세스할 수 있는 단일 연락처 집합을 유지 관리 하는 방법을 제공 합니다.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |XMPP (Extensible Messaging and 거점 Protocol) 게이트웨이를 통해 인스턴트 메시지를 보낼 수 있는지 확인 합니다.  <br/> XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다.  |

System Center Operations Manager를 사용 하기 위해 감시자 노드를 설치할 필요가 없습니다. 이러한 노드를 설치 하지 않은 경우에도 문제가 발생할 때마다 비즈니스용 Skype 서버 2015 구성 요소에서 실시간 알림을 받을 수 있습니다. (구성 요소 및 사용자 관리 팩은 감시자 노드를 사용 하지 않습니다.) 그러나 활성 모니터링 관리 팩을 사용 하 여 종단 간 시나리오를 모니터링 하려는 경우에는 감시자 노드가 필요 합니다.
  
> [!NOTE]
> 관리자는 Operations Manager를 사용 하거나 설치 하지 않고 가상 트랜잭션을 수동으로 실행할 수도 있습니다. 비즈니스용 Skype 서버 배포의 크기에 따라 가상 트랜잭션은 많은 양의 컴퓨터 메모리와 프로세서 시간을 사용할 수 있습니다. 따라서 전용 컴퓨터를 감시자 노드로 사용 하는 것이 좋습니다. 예를 들어 감시자 노드로 작동 하도록 비즈니스용 Skype 서버 프런트 엔드 서버를 구성 해서는 안 됩니다. 감시자 노드는 비즈니스용 Skype 서버 토폴로지에 있는 다른 컴퓨터와 동일한 기본 하드웨어 요구 사항을 충족 해야 합니다. 
  
> [!NOTE]
> Lync Server 2013 및 비즈니스용 Skype 서버 2015에 대 한 핵심 시스템 파일은 동일한 컴퓨터에 설치할 수 없으므로 레거시 Lync Server 2013 감시자 노드를 비즈니스용 Skype 서버 2015 감시자 노드와 같은 컴퓨터에 배치 된 수 없습니다. 그러나 비즈니스용 Skype 서버 2015 감시자 노드는 비즈니스용 Skype 서버 2015 및 Lync Server 2013을 동시에 모니터링할 수 있습니다. 기본 가상 트랜잭션은 두 제품 버전에서 모두 지원 됩니다. 
  
Lync Server 2013의 확인을 돕기 위해 기업 내부 또는 외부에서 감시자 노드를 배포할 수 있습니다.
  
- 기업 내부의 사용자 풀에 대한 연결
    
- 기업 외부에서 작업 하는 원격 사용자에 대 한 경계 네트워크를 통한 연결
    
- 지점 사무소 기기에 대한 연결
    
- 기업 내부 및 경계 네트워크 내부의 Lync Server 2013에 대 한 연결
    
관리를 단순화 하기 위해 기업 내부 및 외부에서 다양 한 인증 옵션을 사용할 수 있습니다. 자세한 내용은 [가상 트랜잭션을 실행 하도록 감시자 노드 구성을](watcher-nodes.md#enable_synthetic_trans)참조 하십시오.
  
컴퓨터가 감시자 노드로 작동 하도록 구성 하려면 먼저 다음 필수 구성 요소를 완료 해야 합니다. 
  
- System Center Operations Manager를 설치 하 고 비즈니스용 Skype 서버 2015 관리 팩을 가져옵니다. 또한 먼저 감시자 노드 컴퓨터가 비즈니스용 Skype 서버 2015을 설치 하기 위한 모든 필수 구성 요소를 충족 하는지 확인 해야 합니다.
    
- 감시자 노드 컴퓨터에 다음 항목을 설치 합니다.
    
  - 전체 버전의 .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
필수 구성 요소를 충족 하 고 나면 다음 단계를 수행 하 여 감시자 노드를 구성할 수 있습니다.
  
1. 감시자 노드 컴퓨터에 비즈니스용 Skype 서버 2015 코어 파일을 설치 합니다.
    
2. 감시자 노드 컴퓨터에 System Center Operations Manager 에이전트를 설치 합니다.
    
3. Watchernode.msi 실행 파일을 실행 합니다.
    
4. **Get-cswatchernodeconfiguration** cmdlet을 사용 하 여 감시자 노드에서 사용할 테스트 사용자 계정을 구성 합니다.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>비즈니스용 Skype 서버 2015 핵심 파일 및 RTCLocal 데이터베이스 설치

컴퓨터에 비즈니스용 Skype 서버 2015 코어 파일을 설치 하려면 다음 절차를 수행 합니다. 핵심 파일을 설치 하면 RTCLocal 데이터베이스가 자동으로 설치 됩니다. 감시자 노드에는 SQL Server를 설치할 필요가 없습니다. SQL Server Express가 자동으로 설치 됩니다.
  
비즈니스용 Skype 서버 2015 코어 파일 및 RTCLocal 데이터베이스를 설치 하려면 다음을 수행 합니다.
  
1. 감시자 노드 컴퓨터에서 시작, 모든 프로그램,  보조 프로그램을 차례로 클릭하고 명령 프롬프트를 마우스 오른쪽 단추로 클릭한 후 관리자로 실행을 클릭합니다.
    
2. 콘솔 창에서 다음 명령을 입력 하 고 enter 키를 누릅니다. 비즈니스용 Skype 서버 설치 파일에 대 한 적절 한 경로를 입력 해야 합니다. D:\Setup.exe/BootstrapLocalMgmtTo에서 핵심 비즈니스용 Skype 서버 구성 요소가 설치 되어 있는지 확인 하 고, **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype 서버 관리 셸을**클릭 합니다. 비즈니스용 Skype 서버 관리 셸에서 다음 Windows PowerShell 명령을 입력 하 고 enter 키를 누릅니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> 이 명령을 처음 실행할 때 감시자 노드 컴퓨터를 아직 구성 하지 않았으므로 데이터가 반환 되지 않습니다. 오류를 반환 하지 않고 명령을 실행 하는 경우 비즈니스용 Skype 서버 설정이 완료 된 것으로 가정할 수 있습니다. 
  
감시자 노드 컴퓨터가 경계 네트워크 내에 있는 경우 다음 명령을 실행 하 여 비즈니스용 Skype 서버 2015의 설치를 확인할 수 있습니다.
  
Get-CsPinPolicyYou에서는 조직에서 사용 하도록 구성 된 PIN 정책의 수에 따라 다음과 같은 정보가 수신 됩니다.
  
Id: Global
  
설명이
  
MinPasswordLength: 5
  
으로: 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts 합니다.
  
PIN 정책에 대 한 정보가 표시 되 면 핵심 구성 요소가 성공적으로 설치 된 것입니다.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>감시자 노드에 Operation Manager 에이전트 파일 설치

비즈니스용 Skype 서버 설정과 마찬가지로 보고 구성 요소 경고의 경우에는 비즈니스용 Skype 서버 2015 감시자 노드를 설치 하려면 System Center Operations Manager 에이전트 파일이 필요 합니다. 이렇게 하면 가상 트랜잭션을 실행 하 고 System Center Operations Manager 루트 관리 서버에 대 한 알림을 보고할 수 있습니다.
  
에이전트 파일을 설치 하려면 [모니터링할 비즈니스용 Skype 서버 컴퓨터 구성](configure-computers-to-monitor.md)에 나열 된 절차를 수행 합니다.
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>가상 트랜잭션을 실행 하도록 감시자 노드 구성
<a name="enable_synthetic_trans"> </a>

System Center Operations Manager 에이전트 파일을 설치한 후에는 감시자 노드 자체를 구성 해야 합니다. 이 작업을 수행 하기 위해 수행 하는 단계는 감시자 노드 컴퓨터가 경계 네트워크 내부에 있는지 아니면 경계 네트워크 외부에 있는 경우에 따라 달라 집니다. 
  
감시자 노드를 구성할 때는 해당 노드에서 사용할 인증 방법의 유형도 선택 해야 합니다. 비즈니스용 Skype 서버 2015에서는 신뢰할 수 있는 서버 또는 자격 증명 인증 이라는 두 가지 인증 방법 중 하나를 선택할 수 있습니다. 다음 표에서는 이러한 두 가지 방법의 차이점을 보여 줍니다.
  
||**설명**|**지원 되는 위치**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |인증서를 사용 하 여 내부 서버를 가장 하 고 인증 문제를 무시 합니다.  <br/> 각 감시자 노드에 대 한 많은 사용자 암호 대신 단일 인증서를 관리 하려는 관리자에 게 유용 합니다.  <br/> |기업 내부  <br/> 이 방법을 사용 하는 경우 감시자 노드는 모니터링 되는 풀과 같은 도메인에 있어야 합니다. 감시자 노드와 풀이 서로 다른 도메인에 있는 경우 자격 증명 인증을 대신 사용 합니다.  <br/> |
|결정  <br/> |각 감시자 노드의 Windows 자격 증명 관리자에 사용자 이름과 암호를 안전 하 게 저장 합니다.  <br/> 이 모드는 더 많은 암호 관리가 필요 하지만, 엔터프라이즈 외부의 감시자 노드에 대해서는 유일한 옵션입니다. 이러한 감시자 노드는 인증에 대해 신뢰할 수 있는 끝점으로 취급할 수 없습니다.  <br/> |기업 외부  <br/> 기업 내부  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>신뢰할 수 있는 서버 인증을 사용 하도록 감시자 노드 구성
<a name="enable_synthetic_trans"> </a>

감시자 노드 컴퓨터가 경계 네트워크 내에 있는 경우 신뢰할 수 있는 서버 인증을 사용 하면 여러 사용자 계정 암호를 사용 하는 것이 아니라 단일 인증서를 유지 관리 하 여 관리 작업을 크게 줄일 수도 있습니다.
  
신뢰할 수 있는 서버 인증을 구성 하려면 먼저 감시자 노드 컴퓨터를 호스트 하는 신뢰할 수 있는 응용 프로그램 풀을 만들어야 합니다. 신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 해당 감시자 노드에서 가상 트랜잭션을 구성 하 여 신뢰할 수 있는 응용 프로그램으로 실행 해야 합니다.
  
> [!NOTE]
> 신뢰할 수 있는 응용 프로그램 이란 비즈니스용 Skype 서버 2015의 일부로 실행할 신뢰할 수 있는 상태가 제공 되는 응용 프로그램 이지만 제품의 기본 제공 부분은 아닙니다. 신뢰 상태란 응용 프로그램이 실행될 때마다 응용 프로그램에 인증을 요청하지 않는 상태를 의미합니다.
  
신뢰할 수 있는 응용 프로그램 풀을 만들려면 비즈니스용 Skype 서버 관리 셸을 열고 다음과 같은 명령을 실행 합니다.
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> 이전 명령의 매개 변수에 대 한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 프롬프트에서 다음을 입력 합니다. 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

신뢰할 수 있는 응용 프로그램 풀을 만든 후에는 **new-cstrustedapplication** cmdlet 및 다음과 같은 명령을 사용 하 여 감시자 노드 컴퓨터에서 신뢰할 수 있는 응용 프로그램으로 가상 트랜잭션을 실행 하도록 구성 하면 됩니다.
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

이 명령을 완료 하 고 신뢰할 수 있는 응용 프로그램을 만든 후에는 **enable-cstopology** cmdlet을 실행 하 여 변경 내용이 적용 되었는지 확인 해야 합니다.
  
```PowerShell
Enable-CsTopology
```

감시자 노드 컴퓨터 계정에는 일부 가상 트랜잭션에 대해 CMS를 쿼리할 수 있는 기능이 필요 합니다. 이 기능을 허용 하려면 감시자 노드의 컴퓨터 계정을 RTCUniversalReadOnlyAdmins 보안 그룹에 추가 합니다. AD 복제가 발생 한 후 컴퓨터를 다시 시작 합니다.
  
신뢰할 수 있는 새 응용 프로그램이 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸 프롬프트에서 다음을 입력 합니다.
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>감시자 노드에서 기본 인증서 구성
<a name="enable_synthetic_trans"> </a>

가을 수 있는 서버 인증을 사용 하는 각 감시자 노드는 비즈니스용 Skype 서버 배포 마법사를 사용 하 여 할당 된 기본 인증서를 포함 해야 합니다. 
  
기본 인증서를 할당 하려면 다음을 수행 합니다.
  
1. 시작, 모든 프로그램, 비즈니스용 Skype 서버 2015, 비즈니스용 Skype 서버 배포 마법사를 차례로 클릭 합니다. 
    
2. 비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 Skype 서버 시스템 설치 또는 업데이트를 클릭 한 다음 제목 요청, 설치 또는 할당에서 실행을 클릭 합니다. 
    
> [!NOTE]
> 실행 단추가 해제된 경우 로컬 구성 저장소 설치 아래에서 먼저 실행을 클릭해야 할 수 있습니다. 
  
다음 중 하나를 수행합니다.
  
- 기본 인증서로 사용할 수 있는 인증서가 이미 있는 경우 인증서 마법사에서 기본값을 클릭 하 고 할당을 클릭 합니다. 인증서 지정 마법사의 단계에 따라 해당 인증서를 지정합니다.
    
- 기본 인증서를 사용 하기 위해 인증서를 요청 해야 하는 경우 요청을 클릭 한 다음 인증서 요청 마법사의 단계에 따라 해당 인증서를 요청 합니다. 웹 서버 인증서에 대한 기본값을 사용하면 기본 인증서로 지정할 수 있는 인증서가 표시됩니다.
    
## <a name="install-and-configure-a-watcher-node"></a>감시자 노드 설치 및 구성
<a name="enable_synthetic_trans"> </a>

감시자 노드 컴퓨터를 다시 시작 하 고 인증서를 구성한 후에는 Watchernode.msi 파일을 실행 해야 합니다. Operations Manager 에이전트 파일 및 비즈니스용 Skype 서버 2015 핵심 구성 요소가 설치 된 모든 컴퓨터에서 Watchernode.msi를 실행 해야 합니다. 
  
감시자 노드를 설치 및 구성 하려면 다음을 수행 합니다.
  
1. 시작, 모든 프로그램, 비즈니스용 Skype 서버 2015을 차례로 클릭 한 다음 비즈니스용 Skype 서버 관리 셸을 클릭 하 여 비즈니스용 Skype 서버 관리 셸을 엽니다. 
    
2. 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다 (Watchernode.msi 복사본의 실제 경로를 지정 하 고 있어야 합니다.).
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> 명령 창에서 n Watchernode.msi를 실행할 수도 있습니다. 명령 창을 열려면 시작을 클릭하고 명령 프롬프트를 마우스 오른쪽 단추로 클릭한 후 관리자로 실행을 클릭합니다. 명령 창이 열리면 2 단계에 표시 된 것과 같은 명령을 입력 합니다. 
  
> [!IMPORTANT]
> 위 명령에서 이름/값 쌍 인증 =로 서버는 대/소문자를 구분 합니다. 표시 된 대로 정확 하 게 입력 해야 합니다. 예를 들어 다음 명령은 올바른 문자 대/소문자를 사용 하지 않으므로 실패 합니다. 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

외부 서버 모드는 경계 네트워크에 있는 컴퓨터 에서만 사용할 수 있습니다. 감시자 노드가 (가) 서버 모드에서 실행 되 면 관리자는 컴퓨터에서 테스트 사용자 암호를 유지 관리할 필요가 없습니다.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>협상을 사용 하도록 감시자 노드 구성
<a name="enable_synthetic_trans"> </a>

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 가상 트랜잭션을 실행 하도록 감시자 노드를 구성 하기 위해 약간 다른 절차를 따라야 합니다. 특히, 신뢰할 수 있는 응용 프로그램 풀이나 신뢰할 수 있는 응용 프로그램은 만들지 않아야 합니다. 즉, 다음 두 작업을 완료 해야 합니다.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC Local Read-Only Administrators 그룹의 구성원 자격 업데이트

감시자 노드가 경계 네트워크 외부에 있는 경우 감시자 노드에서 다음 절차를 완료 하 여 감시자 노드 컴퓨터의 RTC 로컬 읽기 전용 Administrators 그룹에 네트워크 서비스 계정을 추가 해야 합니다.
  
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

다음 단계에서는 Watchernode.msi 파일을 실행 합니다. 
  
1. Microsoft 비즈니스용 Skype 서버 2015 관리 셸을 엽니다. 시작, 모든 프로그램, Microsoft 비즈니스용 Skype 서버 2015을 차례로 클릭 한 다음 비즈니스용 Skype 서버 관리 셸을 클릭 합니다. 
    
2. 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다 (Watchernode.msi 복사본의 실제 경로를 지정 해야 합니다.).
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> 앞에서 설명한 것 처럼 명령 창 에서도 Watchernode.msi를 실행할 수 있습니다. 명령 창을 열려면 **시작**을 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다. 명령 창이 열리면 2 단계에 표시 된 것과 같은 명령을 입력 합니다. 
  
감시자 노드를 신뢰할 수 있는 응용 프로그램 풀로 설정할 수 없는 경우에는 항상 협상 모드가 사용됩니다. 이 모드에서는 관리자가 감시자 노드에 대한 테스트 사용자 암호를 관리해야 합니다.
  

