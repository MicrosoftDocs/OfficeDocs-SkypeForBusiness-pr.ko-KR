---
title: 'Lync Server 2013: SEFAUtil 도구 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Lync Server 2013에서 SEFAUtil 도구 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-30_

그룹 통화 픽업을 배포 하 고 관리 하려면 SEFAUtil 리소스 키트 도구를 사용 해야 합니다. 이 도구는 Lync Server 2013 리소스 키트 도구의 일부입니다. SEFAUtil를 설치 하기 전에 토폴로지에 신뢰할 수 있는 응용 프로그램 풀이 있어야 하 고, SEFAUtil를 신뢰할 수 있는 응용 프로그램으로 지정 하 고, 토폴로지를 사용 하도록 설정 해야 합니다.

<div>


> [!IMPORTANT]  
> Microsoft 통합 커뮤니케이션 관리 API (c) 3.0 Core SDK는 SEFAUtil 도구를 실행할 컴퓨터에 설치 되어 있어야 합니다.



</div>

배포의 모든 프런트 엔드 풀에서 SEFAUtil를 실행할 수 있습니다.

<div>


> [!NOTE]  
> SEFAUtil를 실행 하는 방법에 대 한 자세한 내용은 Technet 블로그 문서 "SEFAutil 실행을 얻는 방법"을 참조 하세요. <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.



</div>

<div>

## <a name="to-deploy-sefautil"></a>SEFAUtil 배포

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  SEFAUtil 도구는 신뢰할 수 있는 응용 프로그램 풀의 일부인 컴퓨터 에서만 실행 됩니다. 필요한 경우 SEFAUtil를 실행할 계획의 프런트 엔드 풀에 대해 신뢰할 수 있는 응용 프로그램 풀을 정의 합니다. 명령줄에서 다음을 실행 합니다.
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  SEFAUtil 도구를 신뢰할 수 있는 응용 프로그램으로 정의 합니다. 명령줄에서 다음을 실행 합니다.
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 필요한 경우 다른 포트를 사용할 수 있습니다.

    
    </div>

5.  변경 내용이 포함 된 토폴로지를 사용 하도록 설정 합니다. 명령줄에서 다음을 실행 합니다.
    
        Enable-CsTopology

6.  3 단계에서 만든 신뢰할 수 있는 응용 프로그램 풀에 있는 프런트 엔드 서버에 Lync Server 2013 리소스 키트 도구를 설치 합니다.

7.  다음과 같이 SEFAUtil 도구가 올바르게 실행 되 고 있는지 확인 합니다.
    
    1.  Windows 명령 프롬프트에서 관리자 권한으로 도구를 실행 하 여 배포에 있는 사용자의 착신 전환 설정을 표시 합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 도구는 명령줄 \ Files\Microsoft Lync Server 2013 \ Reskit에 있습니다.

        
        </div>
    
    2.  사용자의 착신 전환 설정을 표시 합니다. 명령줄에서 다음을 실행 합니다.
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        사용자의 착신 전환 설정이 표시 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

