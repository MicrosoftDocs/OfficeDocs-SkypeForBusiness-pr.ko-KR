---
title: 'Lync Server 2013: 비공개 전화선에 대 한 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0df93d8a8de73a3119e7ca9a1a7abd76e9157a17
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>Lync Server 2013에서 비공개 전화선에 대 한 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-11_

Lync Server 2013에는 사용자에 게 기본 전화선 외에 또 다른 사설 전화선을 제공할 수 있는 기능이 도입 되었습니다. 개인 전화선은 일반적으로 임원 및 다른 사람에 게 할당 되어 있으며, 목록에 없는 전화 번호를 직접 받을 수 있습니다.

개인 전화선은 Lync Server Management Shell을 사용해 서만 구성할 수 있습니다. Lync Server 제어판을 사용 하 여 개인 전화선을 구성할 수 없습니다. 개인 전화선은 혼합 배포에서는 사용할 수 없으며 Lync Server의 배포 에서만 구성 되어야 합니다.

<div>

## <a name="characteristics-of-private-telephone-lines"></a>개인 전화선의 특성

두 번째 사설 전화선 이라는 개념은 기본적으로 간단 하지만, 비공개 회선의 특징 및 사용자의 기본 전화선과 유사 하거나 다른 방법에 대 한 방법을 이해 하는 것이 중요 합니다.

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>개인 전화선의 일반 특징

  - 사용자는 개인 전화선을 하나만 가질 수 있습니다.

  - 개인 전화선이 있는 사용자에 게는 하나의 음성 사서함만 있으며 단일 전자 메일 주소에서 부재 중 전화 알림을 받습니다.

  - 개인 전화선을 사용 하는 사용자에 게 두 번째 SIP 주소가 없으며 두 번째 개인 전화선이 네트워크에서 사용자에 게 두 번째 현재 상태 (예: 두 번째 인스턴트 메시징 id)를 제공 하지 않습니다.

  - 개인 전화선은 온-프레미스 배포에만 사용할 수 있습니다. Lync Server의 호스팅된 배포에서는 사용할 수 없습니다.

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>개인 전화선이 기본 전화선과 어떻게 다른 지에 대 한 자세한 내용

  - 개인 전화선의 전화 번호는 Active Directory 도메인 서비스에서 파생 된 전화 디렉터리 또는 연락처 목록에 표시 되지 않습니다.

  - 개인 전화선 (착신 전환, 팀 통화, 위임, 팀 링, 그룹 통화 픽업 및 응답 그룹 응용 프로그램)에서는 다음 기능을 사용할 수 없습니다.

  - 개인 전화선으로 거는 통화에는 특별 한 전화가 있으며, 통화에 대 한 시스템 알림은 사용자에 게 수신 전화의 비공개 회선을 알립니다.

  - 개인 전화선으로 거는 통화는 항상 전화를 통과 합니다. "방해 금지" 규칙을 따르지 않습니다.

  - 개인 전화선은 인바운드만을 가지 며 발신 전화를 거는 데 사용할 수 없습니다. 개인 전화선을 사용 하는 사용자가 전화를 거는 경우, 통화는 사용자의 기본 전화선에서 발생 하며 사용자의 이름이 나 사용자의 기본 전화 번호는 표시 되지 않습니다.

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>개인 전화선이 기본 전화선과 비슷한 정도

  - 개인 전화선으로의 응답 하지 않는 통화는 기본 전화선에 대 한 것과 동일한 음성 메일 받은 편지 함으로 라우팅됩니다 (음성 메일을 사용 하는 경우).

  - 통화 대기 및 통화 픽업 사용자의 기본 전화선을 사용 하는 것과 동일한 방식으로 개인 전화선으로 작업할 수 있습니다.

  - 사용자의 기본 전화선에 동시 신호음을 사용할 수 있는 경우에도 개인 전화선에서 사용할 수 있습니다.

  - 개인 전화선의 전화 번호는 사용자의 기본 전화선에 대 한 전화 번호와 같은 방식으로 통화 정보 레코드에 기록 되지만, 개인 전화 번호 임을 나타냅니다.

  - 사용자가 개인 전화선에서 전화를 받는 경우 통화가 사용자의 기본 전화선에 대 한 통화와 동일 하 게 처리 됩니다. 예를 들어 개인 전화선에서 전화를 받는 사용자가 통화를 전달 하거나 다른 사람을 전화 회의에 초대 하는 경우 Lync 2013에 사용자의 이름이 표시 되 고 사용자의 기본 전화선에 대 한 전화 번호가 발신자 ID에 표시 됩니다.

  - 사용자는 전화를 deflect 수 있습니다 (응답 하기 전에 휴대폰 이나 집 전화기와 같은 다른 목적지로 전화를 걸어 기본 전화선과 같은 방식으로 개인 전화선에서 전화를 겁니다.
    
    <div>
    

    > [!NOTE]  
    > 개인 회선에 대 한 호출이 대체 전화 번호로 라우트되는 경우, 개인 전화선의 전화 번호는 대체 전화 번호로 사용할 수 있으며 해당 번호의 로그에 표시 될 수 있습니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 전화 회의에서 비공개 전화선으로 전화를 걸 때에는 수신 시스템 알림에서 <EM>비공개 회선</EM> 표시가 없습니다.

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>개인 전화선 관리

개인 전화선을 만들고 관리 하는 기술 측면 외에도 해당 회선 관리 절차를 설정 해야 합니다. 여기에는 조직에서 비공개 회선을 사용할 수 있는 정책을 결정 하 고, 사람 및 전화선 목록을 만들고 유지 관리 하 고, 임원에 대 한 사설 전화 디렉터리를 만들고, 사용자 교육을 위해 정렬 하는 것이 포함 됩니다. 관련 작업입니다.

<div>


> [!NOTE]  
> 개인 전화선은 Active Directory에 사용자 개체의 msRTCSIP-PrivateLine 특성으로 저장 됩니다. 기본적으로 인증 된 사용자 그룹의 모든 구성원에 게는이 특성에 대 한 읽기 권한이 있습니다.



</div>

<div>

## <a name="assigning-telephone-numbers"></a>전화 번호 할당

개인 전화선이 필요한 신규 사용자의 계정은 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 개인 전화선이 없는 계정과 같은 방식으로 만들어집니다.

Lync Server Management Shell의 **set-csuser** cmdlet을 사용 하 여 사용자의 개인 전화선에 전화 번호를 지정 합니다 (예: **Set-Csuser-id "Sip:joe@contoso.com"-PrivateLine "Tel: + 14255551212"**).

개인 전화선의 전화 번호는 3 ~ 15 개 사이의 숫자로 입력할 수 있으며 "TEL:" 접두사를 사용 하 여 앞에와 야 합니다. 조직에서 해당 지역 번호와 국가/지역 코드에 대 한 직접 전화 접속을 사용 하는 경우 모든 지역 번호와 국가/지역 코드를 가질 수 있습니다.

Cmdlet 및 Lync Server 관리 셸에 대 한 자세한 내용은 [Lync server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하세요.

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>혼합 배포의 개인 전화 회선

개인 전화선은 Lync Server의 배포에 대해서만 구성 되어야 합니다. Lync Server와 Office Communications server 2007 또는 Office Communications Server 2007 R2 서버가 둘 다 있는 배포의 경우 이전 버전의 사용자가 개인 전화선을 호출 하려고 시도 하는 경우 서버에서 호출 라우팅이 실패 함 개인 전화선에서 역방향 번호 조회를 수행 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

