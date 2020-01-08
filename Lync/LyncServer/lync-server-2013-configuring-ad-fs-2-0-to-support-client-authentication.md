---
title: 'Lync Server 2013: 클라이언트 인증을 지원 하도록 AD FS 2.0 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>Lync Server 2013에서 클라이언트 인증을 지원 하도록 AD FS 2.0 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-03_

AD FS 2.0에서 스마트 카드를 사용 하 여 인증을 지원 하도록 구성할 수 있는 인증 유형에는 두 가지 가능 합니다.

  - FBA (양식 기반 인증)

  - 전송 계층 보안 클라이언트 인증

폼 기반 인증을 사용 하 여 사용자 이름/암호를 사용 하거나 스마트 카드 및 PIN을 사용 하 여 인증할 수 있는 웹 페이지를 개발할 수 있습니다. 이 항목에서는 AD FS 2.0를 사용 하 여 전송 계층 보안 클라이언트 인증을 구현 하는 방법에 대해 중점적으로 설명 합니다. AD FS 2.0 인증 형식에 대 한 자세한 내용은 AD FS 2.0:에서 [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)로컬 인증 유형을 변경 하는 방법을 참조 하세요.

<div>


**클라이언트 인증을 지원 하도록 AD FS 2.0를 구성 하려면**

1.  도메인 관리자 계정을 사용 하 여 AD FS 2.0 컴퓨터에 로그인 합니다.

2.  Windows 탐색기를 실행 합니다.

3.  C:\\inetpub\\adf\\ls로 이동

4.  기존 web.config 파일의 백업 복사본을 만듭니다.

5.  메모장을 사용 하 여 기존 web.config 파일을 엽니다.

6.  메뉴 모음에서 **편집** 을 선택 하 고 **찾기를**선택 합니다.

7.  ** \<Localauthenticationtypes\>** 를 검색 합니다.
    
    4 개의 인증 유형이 한 줄당 하나씩 나열 됩니다.

8.  TLSClient 인증 형식이 포함 된 줄을 섹션의 목록 맨 위로 이동 합니다.

9.  Web.config 파일을 저장 하 고 닫습니다.

10. 관리자 권한으로 명령 프롬프트를 실행 합니다.

11. 다음 명령을 실행 하 여 IIS를 다시 시작 합니다.
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

