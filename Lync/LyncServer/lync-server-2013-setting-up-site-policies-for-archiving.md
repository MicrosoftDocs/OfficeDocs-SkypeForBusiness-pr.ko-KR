---
title: 'Lync Server 2013: 보관할 사이트 정책 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08a4ccd7f88f21aaf0c7e3d1575b9e4a887c31d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Lync Server 2013에서 보관할 사이트 정책 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-09_

해당 사이트 각각에 대해 보관 정책을 만들고 구성 하 여 특정 사이트의 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 사이트 정책은 전역 정책 보다 우선 하지만 사용자 정책은 사이트 정책 보다 우선 합니다. Microsoft Exchange 통합을 사용 하지 않는 경우 또는 Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013에 없고 사서함이 원본 위치 유지에 저장 되어 있는 사용자가 있는 경우에만 보관 정책이 적용 됩니다.

전역, 사이트 및 사용자 정책에 대 한 계층 구조를 포함 하 여 보관 정책이 작동 하는 방법에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 운영 설명서 [에서 보관을 사용 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.

<div>


> [!NOTE]  
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 원본 위치 유지 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.<BR>보관 정책에서 내부 또는 외부 통신의 보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 옵션을 모두 지정 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013에서 보관 옵션 구성을</A> 참조 하세요.



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>사이트에 대 한 보관 정책을 만들려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **보관 정책을**클릭 합니다.
    
    전역, 사이트 및 사용자 정책에 대 한 계층 구조를 포함 하 여 보관 정책이 작동 하는 방법에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 운영 설명서 [에서 보관을 사용 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.

4.  **새로 만들기**를 클릭하고 **사이트 정책**을 클릭합니다.

5.  **사이트 선택**에서 정책을 적용할 사이트를 클릭 합니다.

6.  **새 보관 정책**에서 다음을 수행 합니다.
    
      - **이름**에 사이트 정책의 이름을 지정 합니다.
    
      - **설명**에서 사이트 정책에 대 한 정보를 제공 합니다 (예: Redmond의 사이트 정책).
    
      - 지정 된 사이트에 대 한 내부 통신 보관을 제어 하려면 **내부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.
    
      - 지정 된 사이트에 대 한 외부 통신 보관을 제어 하려면 **외부 통신 보관** 확인란을 선택 하거나 선택을 취소 합니다.

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

