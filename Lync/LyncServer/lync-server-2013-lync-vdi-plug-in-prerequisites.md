---
title: 'Lync Server 2013: Lync VDI 플러그 인 필수 구성 요소'
description: 'Lync Server 2013: Lync VDI 플러그 인 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4389f776747426d07442e29418ab97e9609de7ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566544"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Lync Server 2013의 lync VDI 플러그 인 필수 구성 요소

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-03-07_

VDI (가상 데스크톱 인프라) 환경에서는 가상 컴퓨터와 사용자의 로컬 컴퓨터가이 섹션에 설명 된 요구 사항을 충족 해야 합니다.

<div>


> [!NOTE]  
> 가상화된 환경을 설치하고 배포하는 방법에 대한 자세한 내용은 가상화 솔루션 공급자에게 문의하십시오. Hyper-V와 원격 데스크톱 서비스에 기반을 둔 가상화된 환경 배포에 대한 자세한 내용은 Microsoft TechNet 라이브러리에서 다음 문서를 참조하십시오. 
> <UL>
> <LI>
> <P>Hyper-v 위치 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Windows Server &nbsp; 2008 R2의 원격 데스크톱 &nbsp; 서비스 <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

다음은 데이터 센터 컴퓨터에서 실행 중인 가상 컴퓨터에 대한 요구 사항입니다.

  - 가상 컴퓨터는 Windows 10, Windows 8.1, Windows 8, Windows 7 또는 Windows Server 2008 R2에서 최신 서비스 팩을 사용 하 여 구성 해야 합니다.

다음은 사용자와 사용자의 로컬 컴퓨터에 대 한 요구 사항입니다.

  - 사용자가 Lync Server 2013에 있어야 합니다.

  - 로컬 컴퓨터에 Windows Embedded Standard 7 SP1, windows 7 SP1, windows 8, Windows 8.1 Embedded 또는 Windows 8.1 (포함 되지 않음)가 실행 되 고 있어야 합니다.

  - 원격 데스크톱 서비스를 사용 하는 경우 Lync VDI 플러그 인 비트 (응용 프로그램이 32 비트 또는 64 비트 인지 여부)가 로컬 컴퓨터의 운영 체제 비트와 일치 해야 합니다. 로컬 컴퓨터의 운영 체제 비트 수와 가상 컴퓨터의 운영 체제 비트 수는 일치하지 않아도 됩니다. 다른 가상화 솔루션 또는 플랫폼을 사용하는 경우 해당 가상화 솔루션 공급자의 비트 수 요구 사항에 대한 지침을 참조하십시오.

  - 로컬 컴퓨터에서 최신 버전의 원격 데스크톱 클라이언트를 실행 중이어야 합니다. Microsoft에서 제공하는 원격 데스크톱 서비스 클라이언트의 최신 업데이트를 설치하거나 가상화 솔루션 공급자가 제공하는 최신 원격 데스크톱 클라이언트 소프트웨어를 설치합니다. 최신 원격 데스크톱 서비스 업데이트에 대해서는를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .

  - 로컬 컴퓨터에서 오디오가 재생되고 원격 녹음을 사용할 수 없도록 원격 데스크톱 클라이언트 설정을 구성해야 합니다. Windows에서 원격 데스크톱 연결에 대 한 이러한 설정을 구성 하려면 다음 섹션인 "원격 데스크톱 연결 설정을 구성 하려면"을 참조 하십시오.

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>원격 데스크톱 연결 설정을 구성하려면

Windows에서 Lync VDI 플러그 인의 원격 데스크톱 연결을 준비 하려면 다음 단계를 수행 합니다.

1.  로컬 컴퓨터에서 Windows 8을 실행 하는 경우이 단계를 건너뜁니다. 로컬 컴퓨터에서 s p 1을 사용 하 여 Windows 7을 실행 하는 경우에는에서 사용할 수 있는 최신 Windows 8 버전의 원격 데스크톱 서비스 클라이언트를 설치 [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) 합니다.

2.  **시작**을 클릭하고 **원격 데스크톱 연결**을 클릭하여 원격 데스크톱 서비스 클라이언트를 시작합니다.

3.  **옵션**을 클릭합니다.

4.  **로컬 자원** 탭을 클릭합니다. **원격 오디오**에서 **설정**을 클릭하고 다음을 수행합니다.
    
      - **원격 오디오 재생**에서 **이 컴퓨터에서 재생**을 선택합니다.
    
      - **원격 오디오 녹음**에서 **녹음 안 함**을 선택합니다.
    
      - **확인**을 클릭합니다.

5.  **작업 환경** 탭을 클릭합니다. **성능** 아래에서 **지속적인 비트맵 캐싱** 확인란의 선택을 취소합니다.

6.  **일반** 탭을 클릭합니다. **컴퓨터**에서 가상 컴퓨터 이름을 입력하고 **연결**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

