---
title: 'Lync Server 2013: cmdlet을 사용 하 여 포리스트 준비를 되돌리는 중'
description: 'Lync Server 2013: cmdlet을 사용 하 여 포리스트 준비를 취소 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acac87bdaeb7e730f93401fa62ea2678a713bb8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580394"
---
# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Cmdlet을 사용 하 여 Lync Server 2013에 대 한 포리스트 준비 되돌리기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-06-19_

**Disable-CsAdForest** cmdlet를 사용하여 포리스트 준비 단계를 되돌릴 수 있습니다.

<div>


> [!WARNING]  
> 이전 버전의 Lync Server도 배포 된 환경에서 <STRONG>Disable-CsAdForest</STRONG> cmdlet을 실행 하는 경우 이전 버전에 대 한 전역 설정도 삭제 됩니다.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>cmdlet를 사용하여 포리스트 준비를 되돌리려면

1.  포리스트 루트 도메인에서 Domain Admins 그룹의 구성원으로 도메인에 가입한 컴퓨터에 로그인합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  을 실행합니다.
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    예를 들면 다음과 같습니다.
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    Force 매개 변수는 작업을 강제로 실행할지 여부를 지정합니다. 이 매개 변수가 없으면 포리스트의 한 도메인 이라도 여전히 Lync Server 2013에 대 한 준비가 된 경우 명령이 실행 되지 않습니다. 반면 Force 매개 변수가 지정된 경우에는 포리스트의 다른 도메인 상태에 상관없이 동작이 계속됩니다.
    
    GroupDomain 매개 변수를 지정하지 않을 경우 기본값은 로컬 도메인입니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 포리스트 준비 실행](lync-server-2013-running-forest-preparation.md)  


[Lync Server 2013에 대 한 포리스트 준비](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

