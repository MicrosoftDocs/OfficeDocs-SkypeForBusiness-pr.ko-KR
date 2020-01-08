---
title: 'Lync Server 2013: 보관이 실패 하는 경우 IM 및 웹 회의 세션을 차단 하거나 허용 하도록 중요 모드를 설정 또는 해제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a>보관에 실패 한 경우 Lync Server 2013에서 IM 및 웹 회의 세션을 차단 하거나 허용 하기 위해 중요 모드를 사용 하거나 사용 하지 않도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Lync Server 2013 제어판에서 보관 구성을 사용 하 여 중요 모드를 사용 하거나 사용 하지 않도록 설정 합니다. 여기에는 다음과 같은 보관 구성이 포함 됩니다.

  - Lync Server 2013을 배포할 때 기본적으로 만들어지는 전역 구성입니다.

  - 특정 사이트 또는 풀에 대해 보관을 구현 하는 방법을 지정 하기 위해 만들고 사용할 수 있는 선택적 사이트 수준 및 풀 수준 구성입니다.

보관을 배포할 때 초기에 보관 구성을 설정 했지만 배포 후 구성을 변경, 추가 및 삭제할 수 있습니다. 사용자가 지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성을 구현 하는 방법에 대 한 자세한 내용은 계획 문서, 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 보관을 작동 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.

<div>


> [!NOTE]  
> 보관을 사용 하려면 보관 정책을 구성 하 여 Lync Server 2013에 있는 사용자에 대해 내부 통신, 외부 통신 또는 둘 다에 대해 보관을 사용할지 여부를 지정 해야 합니다. 기본적으로 내부 또는 외부 통신에 대해 보관을 사용할 수 없습니다. 모든 정책에서 보관을 사용 하도록 설정 하기 전에이 섹션에서 설명 하는 대로 배포에 적절 한 보관 구성을 지정 하 고, 선택적으로 특정 사이트 및 풀에 대해 해당 하는 경우를 수행 해야 합니다. 보관을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> 을 참조 하세요.<BR>Exchange Server 통합을 사용 하 여 exchange 2013 서버에 보관 데이터와 파일을 저장 하 고 exchange 2013 서버에 모든 사용자가 있는 경우 보관을 배포 하는 것을 결정 한 경우에는 다음에서 SQL Server 데이터베이스 구성을 제거 해야 합니다. 토폴로지. 이 작업을 수행 하려면 토폴로지 작성기를 사용 해야 합니다. 자세한 내용은 운영 설명서의 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013에서 보관 데이터베이스 옵션 변경을</A> 참조 하세요.



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a>보관이 실패 하는 경우 IM 및 웹 회의 세션 차단 사용 또는 사용 안 함

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.

4.  보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성의 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.

5.  오류가 발생할 때 보관이 작동 하는 방식을 설정 하려면 **IM (인스턴트 메시징) 또는 웹 회의 세션 (보관 실패 시) 차단** 확인란을 선택 하거나 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 중요 모드 사용 및 사용 안 함

**Set-CsArchivingConfiguration** cmdlet을 사용 하 여 중요 한 모드를 사용 하도록 설정 하거나 해제할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-critical-mode"></a>중요 모드를 사용 하도록 설정 하려면

  - 중요 모드를 사용 하도록 설정 하려면 BlockOnArchiveFailure 속성 값을 True ($True)로 설정 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a>중요 모드를 비활성화 하려면

  - 중요 모드를 사용 하지 않도록 설정 하려면 BlockOnArchiveFailure 속성의 값을 False ($False)로 설정 합니다. 예를 들면 다음과 같습니다.
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

자세한 내용은 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 데이터베이스 보관 옵션 변경](lync-server-2013-changing-archiving-database-options.md)  


[Lync Server 2013에서 보관 하는 방식](lync-server-2013-how-archiving-works.md)  


[조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

