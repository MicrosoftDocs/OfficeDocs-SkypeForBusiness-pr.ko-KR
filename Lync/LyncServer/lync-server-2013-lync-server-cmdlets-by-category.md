---
title: 'Lync Server 2013: 범주별 Lync Server cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets by category
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398306(v=OCS.15)
ms:contentKeyID: 48184106
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68764952ebfe2a45895e480d923d76a108fdda8e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-by-category"></a>범주별 Lync Server 2013 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-09-20_

Microsoft Lync Server 2013에서는 관리자가 명령줄에서 Lync Server를 관리할 수 있도록 특별히 설계 된 거의 550 cmdlet이 제공 됩니다. Lync Server 관리 셸에서 cmdlet에 액세스 합니다. 명령줄에서 다음과 같은 명령을 입력 하 여 cmdlet에 대 한 도움말을 직접 검색할 수 있습니다.

    Get-Help New-CsVoicePolicy -Full

위 명령은 **set-csvoicepolicy** cmdlet에 사용할 수 있는 도움말을 모두 검색 합니다. **Set-csvoicepolicy** 에 대 한 참조를 도움말을 검색 하려는 cmdlet의 이름으로 바꿉니다.

Microsoft Lync Server 2013을 관리 하는 데 사용할 수 있는 전체 cmdlet 목록을 검색 하려면 Lync Server 관리 셸 명령 프롬프트에 다음을 입력 합니다.

    Get-Command * -Module Lync -CommandType cmdlet

필요한 cmdlet을 잘 모르는 경우에는 분류 된 cmdlet 및 도움말 항목도 제공 됩니다. 일부 cmdlet은 제품의 여러 영역에 적용 되는 의도적인 것으로, 둘 이상의 범주에 표시 됩니다. 다음은 범주 목록입니다.

<div>


> [!NOTE]
> 비즈니스용 Skype cmdlet 참조가 docs.microsoft.com로 이동 되었습니다. 아래 링크를 클릭 하면 새 docs.microsoft.com 페이지로 이동 합니다. 이제 콘텐츠가 사용 가능 하 게 열리고 GitHub를 통한 커뮤니티 기고에 사용할 수 있습니다. 참여에 관심이 있으십니까? 여기에 있는 리포지토리의 추가 정보를 확인 하세요.<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-user-management-cmdlets.md">Lync Server 2013의 사용자 관리 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">Lync Server 2013의 음성 응용 프로그램 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">Lync Server 2013의 클라이언트 관리 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">Lync Server 2013의 고급 Enterprise Voice cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">Lync Server 2013의 IM 및 현재 상태 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">Lync Server 2013의 PSTN 연결 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">Lync Server 2013의 회의 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">Lync Server 2013의 전화 및 장치 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">Lync Server 2013의 인프라 및 배포 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">Lync Server 2013의 마이그레이션 및 동시 사용 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">Lync Server 2013의 보안 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync server 2013의 lync Server 관리 셸 구성 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">Lync Server 2013의 서버 역할 및 서비스 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">Lync Server 2013의 모바일 기능 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">Lync Server 2013의 응용 프로그램 관리 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">Lync Server 2013의 영구 채팅 서버 cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">Lync Server 2013의 페더레이션 및 외부 액세스 cmdlet</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">Lync Server 2013의 중앙 로깅 cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">Lync Server 2013의 Enterprise Voice cmdlet</a></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server PowerShell 블로그](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

