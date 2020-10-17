---
title: 'Lync Server 2013: 보관에 대 한 글로벌 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589c249f772b130eeed80abb97e272b8053dfdc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532385"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Lync Server 2013에서 보관에 대 한 글로벌 정책 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

프런트 엔드 서버를 배포할 때 Lync Server에서는 보관용 글로벌 정책을 만듭니다. 기본적으로 보관은 글로벌 정책에서 사용하지 않도록 설정됩니다. 전역 정책은 전체 배포에 대 한 내부 및 외부 통신에 대해 보관을 사용할지 여부를 제어 합니다 (사이트 또는 사용자 정책을 설정 하거나, 전역 정책을 재정의 하거나, 일부 또는 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하는 경우) Microsoft Exchange 통합을 사용 하는 경우 글로벌 정책은 Exchange 2013에 있는 모든 사용자에 게 적용 되지 않으며 사서함이 보류 In-Place 됩니다.

전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 작업 설명서 [에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하세요.

<div>


> [!NOTE]  
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정 하 고 해당 사서함을 In-Place 보류에 넣을지 여부를 제어 In-Place 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.<BR>보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Lync Server 보관 데이터베이스를 사용할 때 보관에 대한 글로벌 정책을 구성하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 지정된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다. Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 정책**을 클릭합니다.

4.  **보관 정책** 페이지에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **보관 정책 편집 - 전역**에서 다음을 수행합니다.
    
      - **이름**에서 기본 이름으로 "전역"을 사용하지 않으려는 경우 글로벌 정책에 대해 새 이름을 지정합니다.
    
      - **설명**에서 해당 정책에 대한 정보를 입력합니다(예: *divisionName*용 글로벌 정책).
    
      - 사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 내부 통신 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.
    
      - 사이트 정책 또는 사용자 정책을 통해 제어되지 않는 모든 사이트 및 사용자에 대한 외부 통신 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

