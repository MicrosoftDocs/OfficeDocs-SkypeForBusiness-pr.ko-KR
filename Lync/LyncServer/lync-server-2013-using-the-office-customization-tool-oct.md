---
title: 'Lync Server 2013: OCT (Office 사용자 지정 도구) 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd9c101b9098f9a5a6ac6088740c067039921b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Lync Server 2013에서 OCT (Office 사용자 지정 도구) 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

OCT (Office 사용자 지정 도구)는 설치 프로그램의 일부 이며 많은 사용자 지정에 권장 되는 도구입니다. OCT를 사용 하 여 Office를 사용자 지정 하 고 설치 사용자 지정 .msp 파일에 사용자 지정을 저장 합니다. 네트워크 설치 지점의 Updates 폴더에 파일을 배치 합니다. Office를 설치 하면 설치 프로그램이 Updates 폴더에서 설치 사용자 지정 파일을 찾고 사용자 지정을 적용 합니다. 업데이트 폴더는 Office 2013의 초기 설치 중에 소프트웨어 업데이트를 배포 하는 데에만 사용할 수 있습니다.

OCT는 설치 프로그램의 일부 이며, 제품의 볼륨 라이선스 버전에 포함 되어 있습니다. Office 2013 원본 파일을 포함 `setup.exe /admin` 하는 네트워크 설치 지점의 루트에서 명령줄을 입력 하 여 OCT를 실행 합니다. 예를 들어 다음을 사용 합니다.

`\\server\share\Office15\setup.exe /admin`

관리자는 OCT를 사용 하 여 설치 사용자 지정 .msp 파일을 만듭니다. Microsoft Office 2010 OCT와 같이 관리자는 다음 영역을 사용자 지정할 수 있습니다.

  - **설정** 클라이언트 및 기본 조직 이름, 추가 네트워크 설치 원본, 제품 키, 최종 사용자 사용권 계약, 표시 수준, 제거 하려는 Office 버전, 설치 중에 실행 되는 사용자 지정 프로그램, 보안 설정, 설치 속성에 대 한 기본 설치 위치를 지정 하는 데 사용 됩니다.

  - **기능** 사용자 설정을 구성 하 고 Office 기능을 설치 하는 방법을 사용자 지정 하는 데 사용 됩니다. 관리자는 OCT를 사용 하 여 사용자에 대 한 Office 응용 프로그램 설정의 초기 기본 값을 지정할 수 있습니다. 설치 후 사용자가 대부분의 설정을 수정할 수 있습니다.

  - **추가 콘텐츠** 파일을 추가 또는 제거 하 고, 레지스트리 항목을 추가 또는 제거 하 고, 바로 가기를 구성 하는 데 사용 됩니다.

  - **Outlook** 사용자의 기본 Outlook 프로필을 사용자 지정 하 고, Exchange 설정, 계정 추가, 계정 제거, 설정 내보내기, 전송 그룹 보내기를\\지정 하는 데 사용 됩니다.

OCT에 대 한 자세한 내용은을 <http://go.microsoft.com/fwlink/p/?linkid=267516>참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

