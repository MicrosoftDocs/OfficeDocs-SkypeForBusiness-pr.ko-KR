---
title: 'Lync Server 2013: 사용자에 게 보관 정책 적용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0128d17f3089207eccd94b175057bcbcb5d467f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Lync Server 2013의 사용자에 게 보관 정책 적용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

사용자가 Lync Server 2013를 사용할 수 있도록 설정 되어 있고 Lync Server 2013에 있는 사용자에 대해 보관 하기 위한 사용자 정책을 하나 이상 만든 경우 해당 사용자 또는 사용자 그룹에 적절 한 정책을 적용 하 여 특정 사용자에 대 한 보관 지원을 구현할 수 있습니다. 예를 들어 내부 통신 보관을 지원 하기 위한 정책을 만드는 경우 사용자의 Lync Server 2013 통신 보관을 지원 하기 위해 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.

<div>


> [!NOTE]  
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정 하 고 해당 사서함을 원본 위치 유지 상태로 전환 하는지 여부를 제어 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.<BR>보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다. 자세한 내용은 작업 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하십시오.



</div>

이 항목의 절차를 사용하여 이전에 만든 보관 사용자 정책을 하나 이상의 사용자 계정 또는 사용자 그룹에 적용합니다.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>사용자 계정에 보관 사용자 정책을 적용하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성하려는 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **보관 정책**아래의 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 자동 설정은 기본 서버 설치 설정을 적용 합니다. <STRONG> &lt;&gt; </STRONG> 이러한 설정은 서버에 의해 자동으로 적용됩니다.

    
    </div>

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자별 보관 정책 할당

사용자 단위 보관 정책은 Windows PowerShell 및 **grant-csarchivingpolicy** cmdlet을 사용 하 여 할당할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>단일 사용자에 게 사용자별 보관 정책을 할당 하려면

  - 다음 명령은 사용자별 보관 정책 RedmondArchivingPolicy를 Ken Myer라는 사용자에게 지정합니다.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>사용자별 보관 정책을 여러 사용자에 게 할당 하려면

  - 이 명령은 사용자별 보관 정책 RedmondArchivingPolicy를 계정이 등록자 풀 atl-cs-001.litwareinc.com에 있는 모든 사용자에게 지정합니다. 이 명령에 사용 된 Filter 매개 변수에 대 한 자세한 내용은 [csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) c i c c i c c a c c-설명서를 참조 하십시오.
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>사용자별 보관 정책을 할당하려면

  - 다음 명령은 이전에 Ken Myer에게 지정되었던 사용자별 보관 정책의 지정을 해제합니다. 사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

자세한 내용은 [grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 설명서를 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 내부 및 외부 통신의 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Lync Server 2013에서 사용자별 정책 할당](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

