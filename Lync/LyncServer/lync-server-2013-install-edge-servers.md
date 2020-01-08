---
title: 'Lync Server 2013: 에지 서버 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 211baa13f80e89fa081b6bf65d4bd7e90d50d000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Lync Server 2013의 에지 서버 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

Lync Server 배포 마법사를 사용 하 여 Edge 서버에 Lync Server 2013을 설치 합니다. 각 Edge 서버에서 배포 마법사를 실행 하 여 Edge 서버를 설정 하는 데 필요한 대부분의 작업을 완료할 수 있습니다. Edge 서버에 Lync Server 2013을 배포 하려면 edge 서버 토폴로지를 정의 및 게시 하 고 Edge 서버에서 사용할 수 있는 미디어로 내보내야 하는 토폴로지 작성기를 이미 실행 해야 합니다. 자세한 내용은 [Lync server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) 를 참조 하 고 [lync server 2013 토폴로지를 내보낸 후 edge 설치를 위해 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)합니다.

배포 마법사를 사용 하 여 각 Edge 서버를 설치한 후 필요한 인증서를 설치 및 할당 하 고 필요한 서비스를 시작 하면 lync [server 2013에서 외부 사용자 액세스에 대 한 지원을 구성](lync-server-2013-configuring-support-for-external-user-access.md) 하는 정보를 사용 하 여 외부 사용자 액세스를 사용 하도록 설정 하 고 [lync server 2013에서 Edge 배포를 확인](lync-server-2013-verifying-your-edge-deployment.md) 하 여 서버 및 클라이언트 연결을 포함 하 여 설치의 유효성을 검사 하는 정보를

<div>

## <a name="to-install-an-edge-server"></a>Edge 서버를 설치 하려면

1.  Edge 서버를 설치 하려는 컴퓨터에 로컬 관리자 그룹의 구성원 또는 해당 사용자 권한 및 사용 권한이 있는 계정으로 로그온 합니다.

2.  토폴로지 작성기를 사용 하 여 만든 토폴로지 구성 파일을 Edge 서버에서 사용할 수 있는지 확인 (예: 토폴로지 구성 파일을 복사한 USB 드라이브에 액세스) 하거나 다음을 확인 합니다. 파일을 복사한 네트워크 공유에 대 한 액세스를 표시 합니다.

3.  배포 마법사를 시작 합니다.
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual c + + 재배포 가능 패키지를 설치 해야 한다는 메시지가 나타나면 <STRONG>예</STRONG>를 클릭 합니다. 다음 대화 상자에서 기본 <STRONG>설치 위치</STRONG> 를 그대로 사용 하거나 <STRONG>찾아보기를</STRONG> 클릭 하 여 대체 위치를 선택 하 고 <STRONG>설치</STRONG>를 클릭 합니다. 다음 대화 상자에서 <STRONG>사용권 계약에 동의</STRONG> 함 확인란을 선택 하 고 <STRONG>확인</STRONG>을 클릭 합니다.

    
    </div>

4.  배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 합니다.

5.  마법사에서 1 단계의 배포 상태를 확인 한 후 ** 로컬 구성 저장소를 설치**하 고 **실행** 을 클릭 한 후 다음을 수행 합니다.
    
      - **중앙 관리 저장소의 로컬 복제본 구성** 대화 상자에서 **파일에서 가져오기 (Edge 서버에 대해 권장)** 를 클릭 하 고 내보낸 토폴로지 구성 파일의 위치로 이동한 다음 .zip 파일을 선택 하 고 **열기**를 클릭 한 후 **다음**을 클릭 합니다.
    
      - 배포 마법사는 구성 파일에서 구성 정보를 읽고 XML 구성 파일을 로컬 컴퓨터에 씁니다.
    
      - **명령 실행** 프로세스가 완료 되 면 **마침을**클릭 합니다.

6.  배포 마법사에서 **2 단계: Lync Server 구성 요소 설정 또는 제거** 를 클릭 하 여 로컬 컴퓨터에 저장 된 XML 구성 파일에 지정 된 lync server 2013 edge 구성 요소를 설치 합니다.

7.  설치를 완료 한 후에는 [Lync Server 2013에 대 한 Edge 인증서 설정](lync-server-2013-set-up-edge-certificates.md) 의 정보를 사용 하 여 서비스를 시작 하기 전에 필요한 인증서를 설치 하 고 할당 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

