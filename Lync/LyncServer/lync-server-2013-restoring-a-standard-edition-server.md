---
title: 'Lync Server 2013: Standard Edition 서버 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 101cf0cb2fc4073e2b79aa008187465f84d2d439
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013에서 Standard Edition 서버 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

중앙 관리 저장소를 호스팅하지 않는 Standard Edition server가 실패 하는 경우이 섹션의 절차를 따르세요. 중앙 관리 저장소에 오류가 발생 하는 경우 [Lync server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요.

<div>


> [!TIP]  
> 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치한 후 이미지 복사본을 가져와 인증서를 복원 하거나 다시 등록할 수 있습니다.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>스탠더드 버전 서버를 복원 하려면

1.  실패 한 컴퓨터와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 새 서버를 사용 하 여 시작 하 고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.
    
    <div>
    

    > [!NOTE]  
    > 조직의 서버 배포 절차에 따라이 단계를 수행 합니다.

    
    </div>

2.  RTCUniversalServerAdmins 그룹 및 로컬 관리자 그룹의 구성원 인 사용자 계정에서 복원 하려는 서버에 로그온 합니다.

3.  적절 한 파일 저장소를 $Backup에서 서버의 파일 저장소 위치로 복사 하 여 파일 저장소를 복원 하 고 폴더를 공유 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 파일을 사용 하는 구성 요소에서 액세스할 수 있도록 복원 된 파일 저장소의 경로와 파일 이름이 백업 된 파일 저장소와 정확히 동일 해야 합니다.

    
    </div>

4.  토폴로지 작성기 실행:
    
    1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
    2.  **기존 배포에서 토폴로지 다운로드**를 클릭 한 다음 **확인**을 클릭 합니다.
    
    3.  토폴로지를 선택한 다음 **저장**을 클릭 합니다. **예** 를 클릭 하 여 선택 내용을 확인 합니다.

5.  Lync Server 설치 폴더 또는 미디어로 이동한 다음 설치 \\\\Amd64\\Setup.exe에 있는 lync server 배포 마법사를 시작 합니다. Lync Server 배포 마법사를 사용 하 여 다음을 수행 합니다.
    
    1.  **1 단계: 로컬 구성 저장소 설치** 를 실행 하 여 로컬 구성 파일을 설치 합니다.
    
    2.  **2 단계: lync Server 구성 요소 설치 또는 제거** 를 실행 하 여 lync server 서버 역할을 설치 합니다.
    
    3.  **3 단계: 인증서 요청, 설치 또는 할당** 을 실행 하 여 인증서를 할당 합니다.
    
    4.  서버에서 서비스를 시작 하려면 **4 단계: 서비스 시작** 을 실행 합니다.
    
    배포 마법사 실행에 대 한 자세한 내용은 복원 하는 서버 역할에 대 한 배포 설명서를 참조 하세요.

6.  다음을 수행 하 여 사용자 데이터를 복원 합니다.
    
    1.  $Backup\\ 에서 로컬 디렉터리로 ExportedUserData을 복사 합니다.
    
    2.  사용자 데이터를 복원 하기 전에 Lync 서비스를 중지 해야 합니다. 이렇게 하려면 다음을 입력 합니다.
        
            Stop-CsWindowsService
    
    3.  사용자 데이터를 복원 하려면 명령줄에 다음을 입력 합니다.
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        예를 들면 다음과 같습니다.
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  다음과 같이 입력 하 여 Lync 서비스를 다시 시작 합니다.
        
            Start-CsWindowsService

7.  이 Standard Edition 서버에 응답 그룹을 배포한 경우 응답 그룹 구성 데이터를 복원 합니다. 자세한 내용은 [Lync Server 2013에서 응답 그룹 설정 복원을](lync-server-2013-restoring-response-group-settings.md)참조 하세요.

8.  이 Standard Edition 서버에 영구 채팅을 배포한 경우에는 mgc .mdf (영구 채팅 데이터베이스)를 복원 합니다.
    
    SQL Server 백업을 사용 하 여 영구 채팅 데이터베이스를 백업한 경우 SQL Server restore 프로시저를 사용 하 여 복원 합니다.
    
    CsPersistentChatData cmdlet을 사용 하 여 백업한 경우 해당 가져오기-CsPersistentChatData를 사용 하 여 복원 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

