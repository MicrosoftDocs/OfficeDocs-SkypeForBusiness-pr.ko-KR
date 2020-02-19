---
title: 'Lync Server 2013: OCT (Office 사용자 지정 도구) 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04cf51d16c27a75d65b1936f2f95e1e5865ad63e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Lync Server 2013의 OCT (Office 사용자 지정 도구) 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

OCT (Office 사용자 지정 도구)는 설치 프로그램의 일부 이며 많은 사용자 지정 작업에 권장 되는 도구입니다. OCT를 사용 하 여 Office를 사용자 지정 하 고 설치 사용자 지정 .msp 파일에 사용자 지정 내용을 저장 합니다. 이 파일은 네트워크 설치 지점의 Updates 폴더에 저장합니다. Office를 설치할 때 설치 프로그램은 Updates 폴더에서 설치 사용자 지정 파일을 찾아 사용자 지정 내용을 적용 합니다. Updates 폴더는 Office 2013의 초기 설치 중에 소프트웨어 업데이트를 배포 하는 데에만 사용할 수 있습니다.

OCT는 설치 프로그램의 일부로, 볼륨 라이선스 버전의 제품에 포함 되어 있습니다. Office 2013 원본 파일이 포함 된 `setup.exe /admin` 네트워크 설치 지점의 루트에서 명령줄에 입력 하 여 OCT를 실행 합니다. 예를 들어 다음을 사용 합니다.

`\\server\share\Office15\setup.exe /admin`

관리자는 OCT를 사용 하 여 설치 사용자 지정 .msp 파일을 만듭니다. Microsoft Office 2010 OCT에서와 마찬가지로 관리자는 다음 영역을 사용자 지정할 수 있습니다.

  - **설치 프로그램** 클라이언트 및 기본 조직 이름, 추가 네트워크 설치 원본, 제품 키, 최종 사용자 사용권 계약, 표시 수준, 제거할 이전 버전의 Office, 설치 중에 실행할 사용자 지정 프로그램, 보안 설정 및 설치 속성을 지정 하는 데 사용 됩니다.

  - **기능** 사용자 설정을 구성 하 고 Office 기능이 설치 되는 방식을 사용자 지정 하는 데 사용 됩니다. 관리자는 OCT를 사용 하 여 사용자에 대 한 Office 응용 프로그램 설정의 초기 기본값을 지정할 수 있습니다. 사용자는 설치 후 대부분의 설정을 수정할 수 있습니다.

  - **추가 콘텐츠** 파일을 추가 하거나 제거 하 고, 레지스트리 항목을 추가 또는 제거 하 고, 바로 가기를 구성 하는 데 사용 됩니다.

  - **Outlook** 사용자의 기본 Outlook 프로필을 사용자 지정 하 고, Exchange 설정을 지정 하 고, 계정을 추가 하 고, 계정을 제거 하 고\\, 설정을 내보내고, 보내기 수신 그룹을 지정 하는 데 사용 됩니다.

OCT에 대 한 자세한 내용은를 <https://go.microsoft.com/fwlink/p/?linkid=267516>참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

