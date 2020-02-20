---
title: 부하를 실행할 토폴로지 프로 비전
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9b81708cbd518b43247c4324ecc651a4089c3ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>부하를 실행할 토폴로지 프로 비전

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>부하를 실행할 토폴로지 프로 비전

기존 설정 및 Lync Server 2013의 구성에 따라 사용자 환경에서 다음과 같은 사항을 변경 해야 할 수 있습니다.

1.  Windows PowerShell 실행 정책을 무제한으로 설정 합니다. 실행 정책 설정을 확인 하려면 Lync Server 관리 셸을 열고 다음 명령을 실행 합니다.

    ``` powershell
        Get-ExecutionPolicy
    ```        

    이 명령이 무제한 값을 반환 하지 않으면 다음 명령을 실행 합니다.

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Lync Server 2013를 효과적으로 구성 하려면 다음을 수행 해야 합니다.
    
      - Lync Server 2013 토폴로지 (예: 컴퓨터 이름, 서비스 인스턴스, 사이트 이름 및 정책)에 익숙해져야 합니다.
    
      - 응답 그룹 헌트 그룹 (예: SIP Uri)과 같은 그룹에 만들어진 일부 사용자를 할당 합니다.

3.  명령줄에서 스크립트를 실행 하려면 다음을 사용할 수 있습니다.

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  일반적으로이 패키지의 스크립트 중 하나를 실행 하면 스크립트의 결과 추적은 scriptname \<\>$h $ m $ .txt 라는 스크립트를 호출한 경로에 있는 파일에 저장 됩니다. 예를 들어 오후 12:15 시에 ArchivingPolicy를 실행 합니다. ArchivingPolicy121500와 같은 로그 파일이 생성 됩니다.

5.  마지막으로 서버를 구성 하는 예제를 제공 했지만 부하를 모두 실행 한 후에 구성을 수정 하거나 삭제 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

