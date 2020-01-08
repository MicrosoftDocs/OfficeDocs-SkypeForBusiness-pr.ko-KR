---
title: 'Lync Server 2013: 조직, 사이트 및 풀에 대 한 보관 구성 옵션 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10efbf23a503364de7034651d94ced43a8d7b750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Lync Server 2013 제어판에서 보관 구성을 사용 하 여 보관을 구현 하는 방법을 지정 합니다. 여기에는 다음과 같은 보관 구성이 포함 됩니다.

  - Lync Server 2013을 배포할 때 기본적으로 만들어지는 전역 구성입니다.

  - 특정 사이트 또는 풀에 대해 보관을 구현 하는 방법을 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 풀 수준 구성입니다.

보관을 배포할 때 초기에 보관 구성을 설정 했지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다. Lync Server 2013 제어판에서 **보관 및 모니터링** 그룹의 **보관 구성** 페이지를 사용 하 여 전역 수준, 사이트 수준 및 풀 수준에서 구성을 관리할 수 있습니다. 지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.

<div>


> [!NOTE]  
> 보관을 사용 하려면 보관 정책을 구성 하 여 Lync Server 2013에 있는 모든 사용자에 대해 내부 통신, 외부 통신 또는 둘 다에 대해 보관을 사용할지 여부를 지정 해야 합니다. 기본적으로 내부 또는 외부 통신에 대해 보관을 사용할 수 없습니다. Microsoft Exchange 통합을 사용 하는 경우 exchange 2013에 속한 모든 사용자 (사서함이 원본 위치 유지에 배치 된 경우)에 대 한 보관을 지원 하도록 Exchange 2013를 설정 하 고 구성 해야 합니다.<BR>보관을 사용 하도록 설정 하기 전에이 섹션에서 설명 하는 대로 배포에 적절 한 보관 구성을 지정 하 고 필요에 따라 특정 사이트 및 풀에 대해 해당 하는 경우를 선택 해야 합니다. 보관을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> 을 참조 하세요.



</div>

**Windows PowerShell cmdlet을 사용 하 여 구성 정보 보관을 보려면**

  - Windows PowerShell 및 **CsArchivingConfiguration** cmdlet을 사용 하 여 보관 구성 정보를 볼 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.
    
    Lync Server 관리 셸에서 다음 명령을 사용 하 여 모든 보관 구성 설정에 대 한 정보를 확인 합니다.
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 보관 구성을 만들어 특정 사이트 또는 풀에 대 한 보관 관리](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Lync Server 2013에서 IM 또는 회의 세션 보관 사용 또는 사용 안 함](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Lync Server 2013에서 보관 된 데이터 제거 사용 또는 사용 안 함](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [보관에 실패 한 경우 Lync Server 2013에서 IM 및 웹 회의 세션을 차단 하거나 허용 하기 위해 중요 모드를 사용 하거나 사용 하지 않도록 설정](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Lync Server 2013에서 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Exchange 저장소와 함께 Lync Server 2013의 통합 사용 또는 사용 안 함](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Lync Server 2013에서 보관 구성 삭제](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 보관 관리](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

