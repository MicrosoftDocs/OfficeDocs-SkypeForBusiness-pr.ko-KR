---
title: 통화 대기 응용 프로그램 설정 마이그레이션
description: 통화 대기 응용 프로그램 설정을 마이그레이션합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da90ca4ee4dd53451c29b8c39861dc76a17ca3c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579414"
---
# <a name="migrate-call-park-application-settings"></a>통화 대기 응용 프로그램 설정 마이그레이션

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

Lync server 2010에서 Lync Server 2013로의 통화 대기 응용 프로그램 마이그레이션에는 lync server 2010에 업로드 된 사용자 지정 음악을 포함 하 여 Lync Server 2013 풀을 프로 비전 하 고, 서비스 수준 설정을 복원 하 고 모든 통화 대기 궤도을 Lync Server 2013 풀로 다시 설정 하는 기능이 포함 되어 있습니다. Lync Server 2010 풀에 사용자 지정 된 음악 대기 파일을 구성한 경우 이러한 파일을 새 Lync Server 2013 풀로 복사 해야 합니다. 또한 통화 대기에 업로드 된 사용자 지정 된 모든 음악 준비 파일의 별도 백업 복사본을 유지 하기 위해 Lync Server 2010에서 모든 통화 보류 음악 파일을 다른 대상으로 백업 하는 것이 좋습니다. 통화 대기 응용 프로그램에 대 한 사용자 지정 된 음악 보존 파일은 해당 풀의 파일 저장소에 저장 됩니다. Lync Server 2010 풀 파일 저장소의 오디오 파일을 Lync Server 2013 파일 저장소에 복사 하려면 다음 매개 변수와 함께 **Xcopy** 명령을 사용 하십시오.

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

사용자 지정 된 모든 오디오 파일을 Lync Server 2013 파일 저장소로 복사한 후에는 Lync server 2013 풀의 통화 대기 응용 프로그램 설정을 구성 해야 하며 Lync server 2010 풀과 연결 된 통화 대기 번호 범위를 Lync Server 2013 풀에 다시 할당 해야 합니다.

통화 대기 응용 프로그램 설정에는 픽업 시간 제한 임계값이 포함 되며 보류 중인 음악을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. Lync Server 관리 셸을 사용 하 여 **new-cscpsconfiguration** cmdlet을 실행 하 여 통화 대기 응용 프로그램 설정을 관리 해야 합니다. Lync Server 제어판을 사용 하 여 통화 대기 응용 프로그램 설정을 관리할 수는 없습니다.

**통화 대기 서비스 설정 다시 구성**

1.  Lync Server 2013 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.

2.  명령줄에 다음을 입력합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 통화 대기 응용 프로그램 설정이 레거시 Lync Server 2010 설정과 동일한 경우이 단계를 건너뛸 수 있습니다. Lync Server 2013 및 Lync Server 2010 환경에 대해 통화 대기 응용 프로그램 설정이 다르면 아래 cmdlet을 서식 파일로 사용 하 여 해당 변경 내용을 업데이트 하십시오.

    
    </div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-enablemusiconhold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-ontimeouturi" <LS2010 CPS timeout URI> " ```

Lync server 2010 풀의 모든 통화 대기 번호 범위를 Lync Server 2013 풀로 다시 할당 하려면 Lync Server 제어판 또는 Lync Server 관리 셸을 사용할 수 있습니다.

**Lync Server 제어판을 사용 하 여 모든 통화 대기 궤도 범위 다시 할당**

1.  Lync Server 제어판을 엽니다.

2.  왼쪽 창에서 **음성 기능**을 선택 합니다.

3.  **통화** 대기 탭을 선택 합니다.

4.  Lync Server 2010 풀에 할당 된 각 통화 대기 번호 범위에 대해 **대상 서버 설정의 FQDN** 을 편집 하 고 통화 대기 요청을 처리할 Lync Server 2013 풀을 선택 합니다.

5.  **커밋을** 선택 하 여 변경 내용을 저장 합니다.

**Lync Server 관리 셸을 사용 하 여 모든 통화 대기 궤도 범위 다시 할당**

1.  Lync Server 관리 셸을 엽니다.

2.  명령줄에 다음을 입력합니다.
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    이 cmdlet은 배포의 모든 통화 대기 번호 범위를 나열 합니다. **CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수를 Lync Server 2010 Pool로 설정한 모든 통화 대기 궤도를 다시 할당 해야 합니다.
    
    Lync server 2010 통화 대기 번호 범위를 Lync Server 2013 풀에 다시 할당 하려면 명령줄에 다음을 입력 합니다.
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

모든 통화 대기 궤도 범위를 Lync Server 2013 풀에 다시 할당 하면 통화 대기 응용 프로그램에 대 한 마이그레이션 프로세스가 완료 되 고 Lync Server 2013 풀에서 이후의 모든 통화 대기 요청이 처리 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

