---
title: 'Lync Server 2013: 자격 증명 인증을 사용 하도록 감시자 노드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38a06c7ea40bd30f962484c8ce0d882c9633bf0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Lync Server 2013에서 자격 증명 인증을 사용 하도록 감시자 노드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우에는 감시자 노드가 가상 트랜잭션을 실행하도록 구성하기 위해 약간 다른 절차를 수행해야 합니다. 구체적으로는 신뢰할 수 있는 응용 프로그램 풀과 신뢰할 수 있는 응용 프로그램을 만들어서는 안 되며, 감시자 노드가 경계 네트워크 내의 컴퓨터로 알림을 보낼 수 있도록 설정하는 인증서를 설치해야 합니다. 즉, 다음의 두 개별 작업을 완료해야 합니다.

  - 컴퓨터의 RTC Local Read-only Administrators 그룹에서 구성원 자격 업데이트

  - 감시자 노드 구성 파일 설치

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>RTC Local Read-only Administrators 그룹에서 구성원 자격 업데이트

감시자 노드가 경계 네트워크 외부에 있는 경우에는 감시자 노드 컴퓨터에서 RTC 로컬 읽기 전용 Administrators 그룹에 네트워크 서비스 계정을 추가해야 합니다. 이렇게 하려면 감시자 노드에서 다음 절차를 완료합니다.

1.  **시작**을 클릭하고 **컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음 **관리**를 클릭합니다.

2.  서버 관리자에서 **구성**, **로컬 사용자 및 그룹**을 차례로 확장한 다음 **그룹**을 클릭합니다.

3.  그룹 창에서 **RTC Local Read-only Administrators**를 두 번 클릭합니다.

4.  **RTC Local Read-only Administrators 속성** 대화 상자에서 **추가**를 클릭합니다.

5.  **사용자, 컴퓨터, 서비스 계정 또는 그룹 선택** 대화 상자에서 **위치**를 클릭합니다.

6.  **위치** 대화 상자에서 감시자 노드 컴퓨터의 이름을 선택하고 **확인**을 클릭합니다.

7.  **선택할 개체 이름을 입력하십시오.** 상자에 **네트워크 서비스**를 입력하고 **확인**을 클릭합니다.

8.  **RTC Local Read-only Administrators 속성** 대화 상자에서 **확인**를 클릭하고 **서버 관리자**를 닫습니다.

감시자 노드 컴퓨터를 다시 시작합니다.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>감시자 노드 구성 파일 설치

감시자 노드 컴퓨터가 다시 시작되고 나면 다음 단계로 Watchernode.msi 파일을 실행합니다. 이 파일을 실행 하려면 **시작**, **모든 프로그램**, **lync server 2013**을 차례로 클릭 한 다음 **Lync Server 관리 셸을**클릭 하 여 lync server 2013 관리 셸을 엽니다. Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다 (Watchernode.msi executable 복사본의 실제 경로를 지정 하 고 있어야 합니다.).

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> 위에서 설명한 것처럼 Watchernode.msi는 명령 창에서도 실행할 수 있습니다. 명령 창을 열려면 <STRONG>시작</STRONG>을 클릭하고 <STRONG>명령 프롬프트</STRONG>를 마우스 오른쪽 단추로 클릭한 후에 <STRONG>관리자 권한으로 실행</STRONG>을 클릭합니다. 명령 창이 열리면 위에 나와 있는 것과 같은 명령을 입력합니다.



</div>

감시자 노드를 신뢰할 수 있는 응용 프로그램 풀로 설정할 수 없는 경우에는 항상 협상 모드가 사용됩니다. 이 모드에서는 관리자가 감시자 노드에 대한 테스트 사용자 암호를 관리해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

