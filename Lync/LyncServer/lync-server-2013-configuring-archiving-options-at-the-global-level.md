---
title: 'Lync Server 2013: 전역 수준의 보관 옵션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21653d38c7b56fa93395422a2e20906afd0cc3e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Lync Server 2013의 전역 수준에서 보관 옵션 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-10_

토폴로지에 보관을 추가 하 고 토폴로지를 게시 하면 Lync Server가 보관을 위한 전역 구성을 만듭니다. 기본적으로 전역 구성에서는 보관 옵션이 설정 되어 있지 않습니다. 전역 구성은 전역 구성을 재정의 하는 사이트 또는 풀 구성을 설정 하지 않는 한 전체 배포에 대해 사용할 수 있는 옵션을 제어 합니다.

전역, 사이트 및 풀 구성에 대 한 계층 구조를 포함 하 여 보관 구성이 작동 하는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.

<div>


> [!NOTE]  
> 보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>전역 수준에서 보관 옵션을 구성 하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 2013 제어판을 엽니다. Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.

4.  **보관 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **보관 설정 편집-Global**의 **보관 설정** 드롭다운 목록에서 다음 보관 옵션 중 하나를 선택 합니다.
    
      - **보관 사용 안 함**
    
      - **IM 세션 보관**
    
      - **IM 및 웹 회의 세션 보관**

6.  또한 **보관 설정 편집 – 전역** 페이지에서 다음을 수행 합니다.
    
      - 보관을 사용할 수 없는 경우 활동을 차단 하려면 **인스턴트 메시지 (IM) 또는 웹 회의 세션 (보관 실패 인 경우) 차단** 확인란을 선택 합니다.
    
      - Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.
    
      - 데이터 제거를 사용 하도록 설정 하려면 **데이터 보관 제거 사용** 확인란을 선택 하 고 다음 중 하나를 수행 합니다.
        
          - 특정 일 수 후 제거를 지정 하려면 **내보낸 데이터 보관 및 최대 기간 (일) 이후 저장 된 데이터 보관**을 클릭 한 다음 일 수를 지정 합니다.
        
          - 내보낸 데이터 보관을 위해 지우기를 제한 하려면 **내보낸 데이터 보관만**을 클릭 합니다.

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

