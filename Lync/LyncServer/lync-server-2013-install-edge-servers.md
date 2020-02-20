---
title: Lync Server 2013:에 지 서버 설치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8060d72c6a5c727f0171d3082e7c17d0ed4ac5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Lync Server 2013에 대 한에 지 서버 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

Lync server 배포 마법사를 사용 하 여에 지 서버에 Lync Server 2013을 설치 합니다. 각 에지 서버에서 배포 마법사를 실행하면 에지 서버를 설정하는 데 필요한 대부분의 작업을 완료할 수 있습니다. 에 지 서버에 Lync Server 2013을 배포 하려면 토폴로지 작성기를 실행 하 여에 지 서버 토폴로지를 정의 하 고 게시 한 다음에 지 서버에서 사용할 수 있는 미디어로 내보내야 합니다. 자세한 내용은 [Lync server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md) , [lync Server 2013 토폴로지 내보내기 및 edge 설치를 위해 외부 미디어에 복사](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)를 참조 하세요.

배포 마법사를 사용 하 여 각에 지 서버를 설치 하 고, 필요한 인증서를 설치 및 할당 하 고, 필요한 서비스를 시작한 후에는 [Lync server 2013의 외부 사용자 액세스에 대 한 지원 구성](lync-server-2013-configuring-support-for-external-user-access.md) 의 정보를 사용 하 여 설치를 완료 하 고, 외부 사용자 액세스를 사용 하도록 설정 및 구성 하 고, [lync server 2013에서 Edge 배포를 확인](lync-server-2013-verifying-your-edge-deployment.md) 하 여 서버 및 클라이언트

<div>

## <a name="to-install-an-edge-server"></a>에지 서버를 설치하려면

1.  로컬 Administrators 그룹의 구성원 또는 그에 해당하는 사용자 권한이 있는 계정으로 에지 서버를 설치할 컴퓨터에 로그온합니다.

2.  토폴로지 작성기를 사용 하 여 만들고 내보낸 후 외부 미디어에 복사 된 토폴로지 구성 파일을에 지 서버 (예: 토폴로지 구성 파일을 복사한 USB 드라이브에 액세스)에서 사용할 수 있는지 확인 한 다음 확인을 클릭 합니다. 파일을 복사한 네트워크 공유에 대 한 액세스를 사용 합니다.

3.  배포 마법사를 시작합니다.
    
    <div>
    

    > [!NOTE]  
    > Microsoft Visual C++ 재배포 가능 파일을 설치해야 한다는 메시지가 표시되면 <STRONG>예</STRONG>를 클릭합니다. 다음 대화 상자에서 기본 <STRONG>설치 위치</STRONG>를 그대로 적용하거나 <STRONG>찾아보기</STRONG>를 클릭하여 다른 위치를 선택한 후에 <STRONG>설치</STRONG>를 클릭합니다. 그 다음 대화 상자에서 <STRONG>동의함</STRONG> 확인란을 선택하고 <STRONG>확인</STRONG>을 클릭합니다.

    
    </div>

4.  배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭합니다.

5.  마법사에서 배포 상태를 확인하고 나면 **1단계. 로컬 구성 저장소 설치**에서 **실행**을 클릭하고 다음을 수행합니다.
    
      - **중앙 관리 저장소의 로컬 복제본 구성** 대화 상자에서 **파일에서 가져오기(에지 서버에 권장)** 을 클릭하고 내보낸 토폴로지 파일이 있는 위치로 이동한 다음 .zip 파일을 선택하고 **열기**, **다음**을 차례로 클릭합니다.
    
      - 배포 마법사가 구성 파일에서 구성 정보를 읽고 XML 구성 파일을 로컬 컴퓨터에 씁니다.
    
      - **명령 실행** 프로세스가 완료되면 **마침**을 클릭합니다.

6.  배포 마법사에서 **2 단계: Lync Server 구성 요소 설치 또는 제거** 를 클릭 하 여 로컬 컴퓨터에 저장 된 XML 구성 파일에 지정 된 lync server 2013 edge 구성 요소를 설치 합니다.

7.  설치를 완료 한 후에 Edge 인증서 설정의 정보를 사용 하 여 서비스를 시작 하기 전에 [Lync Server 2013에 대 한](lync-server-2013-set-up-edge-certificates.md) 필수 인증서를 설치 및 할당 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

