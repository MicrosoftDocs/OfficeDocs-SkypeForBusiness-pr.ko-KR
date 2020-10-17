---
title: 'Lync Server 2013: 사용자에 게 Lync Server 보관 정책 적용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cad9784eb2c50662bfedc460cb0dbc8c892206c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504935"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Lync Server 2013의 사용자에 게 Lync Server 보관 정책 적용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-10_

Lync Server 사용자 정책을 만든 후에는 Lync Server 2013에 있는 특정 사용자 또는 사용자 그룹에 적용 하 여 적용 해야 합니다. 특정 사용자에 대 한 사용자 정책을 만드는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보관용 사용자 정책 만들기 및 구성을](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) 참조 하십시오.

전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.

<div>


> [!NOTE]  
> 보관을 구성 및 사용 하려면 먼저 보관을 배포 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-deploying-archiving.md">Lync Server 2013에서 보관 배포</A> 를 참조 하십시오.<BR>배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정 하 고 사서함을 In-Place 보류에 In-Place 여부를 제어 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.<BR>보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>사용자에 게 Lync Server 보관 정책을 적용 하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다. Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성하려는 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **보관 정책**아래의 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt; 자동 &gt; </STRONG> 설정은 기본 서버 설치 설정을 적용 합니다. 이러한 설정은 서버에 의해 자동으로 적용됩니다.

    
    </div>

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

