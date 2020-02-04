---
title: 'Lync Server 2013: 핵심 데이터 및 설정 백업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Lync Server 2013에서 핵심 데이터 및 설정 백업

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-04-23_

다음 절차에서는 Lync Server Management Shell cmdlet을 사용 하 여 설정 및 핵심 서비스의 데이터에 대 한 백업 파일을 만듭니다. 위치를 포함 하 여이 섹션에 사용 된 도구에 대 한 자세한 내용은 [Lync Server 2013의 백업 및 복원 요구 사항: 도구 및 사용 권한](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)을 참조 하세요. 보관 및 모니터링 데이터 백업에 대 한 자세한 내용은 [Lync Server 2013에서 보관 및 모니터링 데이터베이스 백업을](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)참조 하세요.

<div>


> [!NOTE]  
> 중앙 관리 저장소를 백업 하는이 섹션의 단계에서는 보관 및 모니터링에 대 한 설정 및 구성을 포함 합니다.



</div>

이 섹션에 설명 된 cmdlet을 로컬 또는 원격으로 실행할 수 있습니다.

<div>

## <a name="to-back-up-core-data-and-settings"></a>핵심 데이터 및 설정을 백업 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  다음 단계에서 만든 백업을 저장 하려면 새 공유 폴더를 만들고 **$Backup** 에서 참조 하는 경로를 새 공유 폴더로 업데이트 합니다.

3.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

4.  중앙 관리 저장소 구성 파일을 백업 합니다. 명령줄에 다음을 입력 합니다.
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    예를 들면 다음과 같습니다.
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > 이 단계에서는 Lync Server 토폴로지, 정책 및 구성 설정을 파일로 내보냅니다. 다른 단계는 토폴로지 데이터를 백업 하는 데 필요 하지 않습니다.

    
    </div>

5.  백업 된 중앙 관리 저장소 구성 파일을 $Backup\\에 복사 합니다.

6.  위치 정보 서비스 데이터를 백업 합니다. 명령줄에 다음을 입력 합니다.
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    예를 들면 다음과 같습니다.
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  $Backup\\에 백업 된 위치 정보 서비스 구성 파일을 복사 합니다.

8.  프런트 엔드 풀과 모든 Standard Edition 서버의 모든 백 엔드 데이터베이스에 있는 사용자 데이터를 백업 합니다. 명령줄에 다음을 입력 합니다.
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    예를 들면 다음과 같습니다.
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  $Backup\\에 백업 된 사용자 파일을 복사 합니다.

10. 응답 그룹 응용 프로그램을 실행 하는 모든 풀에서 응답 그룹 구성을 백업 합니다. 이렇게 하려면 다음을 수행합니다.
    
    1.  명령줄에 다음을 입력 합니다.
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        예를 들면 다음과 같습니다.
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. $Backup\\에 백업 된 응답 그룹 구성 파일을 복사 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

