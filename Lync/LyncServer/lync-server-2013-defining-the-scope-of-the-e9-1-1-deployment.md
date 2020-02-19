---
title: 'Lync Server 2013: E9-1-1 배포 범위 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c84c6519ab561fef034fbe0990854087f22b2e41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>Lync Server 2013에서 E9-1-1 배포 범위 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-06_

E9-1-1에 대해 Microsoft Lync Server 2013을 구성 하기 전에 E9-1-1 배포를 계획 해야 합니다. 이때 고려할 몇 가지 사항은 다음과 같습니다.

  - **E9-1-1과 관련한 조직의 정책 및 법적 의무**  
    PBX에 대한 E9-1-1 법적 요구 사항(E9-1-1 용어로는 MLTS(Multi-line Telephone Systems)라고 함)은 지역마다 다릅니다. 해당 지역에서 Lync Server 배포에 적용할 수 있는 의무를 이해 하려면 법률 팀과 상의 해야 합니다.

<!-- end list -->

  - **엔터프라이즈 내에서 E9-1-1을 사용하도록 설정할 영역**  
    선택한 위치에서 또는 전체 엔터프라이즈에서 E9-1-1을 사용하도록 설정할 수 있습니다. 예를 들어 각 지역의 지점에 대해 서로 다른 E9-1-1 요구 사항을 지정할 수도 있고 다른 국가의 사이트는 제외할 수도 있습니다.

<!-- end list -->

  - **분기 사이트에 E9-1-1을 배포할 방법**  
    분기 사이트에 E9-1-1을 배포할 때 이해해야 하는 중요한 개념은 음성 탄성입니다. 중앙 집중식 E-9-1-1 SIP 트렁크이 있고 WAN 중단이 발생 하는 경우 로그인 하는 클라이언트에서 위치 정보 서비스 로부터 위치를 얻지 못하거나 응급 서비스 서비스 공급자에 연결 하지 못할 수 있습니다. Lync Server에서는 복구 가능한 데이터 네트워크를 포함 하거나, 각 분기에서 SIP 트렁크를 배포 하거나, 중단 시 로컬 게이트웨이로 긴급 통화를 푸시하는 등 지사의 음성 복구를 처리 하기 위한 몇 가지 전략을 제공 합니다. 자세한 내용은 [Lync Server 2013에서 분기 사이트 음성 복구 계획](lync-server-2013-planning-for-branch-site-voice-resiliency.md)을 참조 하십시오.

<!-- end list -->

  - **네트워크 외부에서 작업하는 사용자에 대해 E9-1-1을 사용하도록 설정할지 여부**  
    자동 위치 가져오기는 조직 네트워크 내에 있는 클라이언트만 사용 가능하므로 조직은 오프-프레미스 상태에서 Lync 클라이언트가 거는 E9-1-1 통화를 지원할지 여부를 결정해야 합니다. 예를 들어 사용자가 재택 근무 중이거나 고객 사이트에서 작업 중일 때 긴급 통화를 할 수 있도록 설정할지를 고려해야 합니다. 클라이언트가 엔터프라이즈 네트워크 외부에 있는 경우 사용자에게 위치를 선택하라는 메시지를 표시하도록 클라이언트를 구성할 수 있습니다. 그러나 사용자가 제공하는 위치는 MSAG(마스터 주소 가이드)와 비교하여 미리 유효성을 검사할 수 없기 때문에 응급 서비스 서비스 공급자 발송자는 통화를 PSAP(Public Safety Answering Point)로 라우팅하기 전에 구두로 발신자에게 위치의 유효성을 확인받아야 합니다.
    
    <div>
    

    > [!NOTE]  
    > VPN을 사용 하 여 조직의 네트워크에 연결 하는 사용자의 Lync 클라이언트는 내부 IP 주소 정보를 선택할 수 있지만, 이러한 주소는 사용자의 실제 위치를 식별 하는 데 사용할 수 없기 때문에, VPN 서브넷은 위치 정보 서비스

    
    </div>

<!-- end list -->

  - **해외 사이트에 대해 긴급 통화 라우팅을 제공할지 여부**  
    응급 서비스 서비스 공급자가 서비스를 제공하지 않는 회사 지역(예: 다른 국가)에 대해 긴급 통화 라우팅 기능을 제공하려는 경우가 있을 수 있습니다. 이렇게 하려면 새 사이트를 만든 다음, 로컬 PSTN 게이트웨이를 통해 통화를 라우팅하는 PSTN 사용을 참조하는 음성 정책을 사이트에 할당합니다.

</div>

<span> </span>

</div>

</div>

</div>

