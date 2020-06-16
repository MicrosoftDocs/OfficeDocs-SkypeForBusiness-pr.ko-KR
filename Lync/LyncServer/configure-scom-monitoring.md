---
title: SCOM 모니터링 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>SCOM 모니터링 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

Microsoft Lync Server 2013로 마이그레이션한 후에는 몇 가지 작업을 완료 하 여 Lync Server 2013에서 System Center Operations Manager와 함께 작동 하도록 구성 해야 합니다.

  - 중앙 검색 논리를 관리 하도록 선택한 서버에 Lync Server 2010 업데이트를 적용 합니다.

  - 중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.

  - 기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 노드를 재정의 합니다.

이러한 각 작업의 수행 지침은 아래에 제공되어 있습니다.

**중앙 검색 논리를 관리 하도록 선택한 서버에 Lync Server 2010 업데이트를 적용 합니다.**

1.  System Center Operations Manager 에이전트 파일을 설치하고 후보 검색 노드로 구성할 서버를 선택합니다.

2.  Lync Server 2010 업데이트를이 서버에 적용 합니다. [Lync Server 2010 업데이트 적용](apply-lync-server-2010-updates.md)항목을 참조 하십시오.

**중앙 검색 후보 서버 레지스트리 키를 업데이트합니다.**

1.  중앙 검색 논리를 관리 하도록 선택한 서버에서 Windows PowerShell 명령 창을 엽니다.

2.  명령줄에 다음을 입력합니다.
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.

    
    </div>

**기본 System Center Operations Manager 관리 서버를 구성 하 여 후보 중앙 검색 감시자 노드를 재정의 합니다.**

1.  System Center Operations Manager 콘솔이 설치된 컴퓨터에서 **관리 팩 개체**를 확장한 후 **개체 검색**을 선택합니다.

2.  **범위 변경...** 을 클릭합니다.

3.  **관리 팩 개체 범위 지정** 페이지에서 **LS 검색 후보**를 선택합니다.

4.  **LS 검색 후보 유효 값**을 이전 절차에서 선택한 후보 서버의 이름으로 바꿉니다.

마지막으로 변경 내용을 마무리하기 위해 System Center Operations Manager 루트 관리 서버에서 상태 관리 서비스를 다시 시작합니다.

</div>

<span> </span>

</div>

</div>

</div>

