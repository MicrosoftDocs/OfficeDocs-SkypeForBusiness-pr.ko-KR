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
ms.openlocfilehash: 9d1cf0db76b888b9774a16f7a6353ccf1b399eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Lync Server 2013에서 사용자에 게 보관 정책 적용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

사용자가 Lync Server 2013을 사용 하도록 설정 되어 있고 Lync Server 2013에 속한 사용자에 대해 보관 하기 위해 하나 이상의 사용자 정책을 만든 경우 해당 사용자 또는 사용자 그룹에 적절 한 정책을 적용 하 여 특정 사용자에 대 한 보관 지원을 구현할 수 있습니다. 예를 들어 내부 통신 보관을 지원 하기 위한 정책을 만들면 사용자의 Lync Server 2013 통신 보관을 지원 하기 위해 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.

<div>


> [!NOTE]  
> 배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 Exchange 원본 위치 유지 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.<BR>보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 하는 모든 옵션을 지정 해야 합니다. 자세한 내용은 운영 설명서에서 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리</A> 를 참조 하세요.



</div>

이 항목의 절차를 사용 하 여 이전에 만든 보관 사용자 정책을 하나 이상의 사용자 계정 또는 사용자 그룹에 적용할 수 있습니다.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>사용자 계정에 보관 사용자 정책을 적용 하려면 다음을 사용 합니다.

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 구성 하려는 사용자 계정을 검색 합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

5.  **보관 정책**에서 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 자동 설정은 기본 서버 설치 설정을 적용 합니다. <STRONG> &lt;&gt; </STRONG> 이러한 설정은 서버에 의해 자동으로 적용됩니다.

    
    </div>

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자별 보관 정책 할당

사용자 단위 보관 정책은 Windows PowerShell 및 **CsArchivingPolicy** cmdlet을 사용 하 여 할당할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>단일 사용자에 게 사용자별 보관 정책을 할당 하려면

  - 다음 명령을 사용 하 여 사용자 단위 보관 정책을 RedmondArchivingPolicy: 진구 Myer에 할당 합니다.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>사용자 단위 보관 정책을 여러 사용자에 게 할당 하려면

  - 이 명령은 등록자 풀 atl-cs-001.litwareinc.com에 속한 계정이 있는 모든 사용자에 대해 사용자별 보관 정책 RedmondArchivingPolicy를 할당 합니다. 이 명령에 사용 된 필터 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 설명서를 참조 하세요.
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>사용자별 보관 정책을 할당 하려면

  - 다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 보관 정책을 할당 취소 합니다. 사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다. 사이트 정책이 전역 정책 보다 우선 합니다.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

자세한 내용은 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet 설명서를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Lync Server 2013에서 사용자별 정책 지정](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

