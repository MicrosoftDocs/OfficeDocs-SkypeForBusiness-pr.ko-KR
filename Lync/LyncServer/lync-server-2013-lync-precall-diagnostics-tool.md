---
title: 'Lync Server 2013: Lync PreCall Diagnostics 도구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0377460340e1b639a7fca5862dcd85aed399b94a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync Server 2013의 lync PreCall 진단 도구

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-11-04_

.PCD (Lync PreCall Diagnostics Tool)는 네트워크의 현재 상태가 예정 된 Enterprise Voice 통화에서 오디오 품질에 어떤 영향을 줄 수 있는지 확인할 수 있도록 하는 클라이언트 기반 응용 프로그램입니다.

.PCD는 네트워크의 마지막 홉이 가장 취약 한 상황 (예: 공용 WiFi 네트워크 또는 가정 사용자에 대 한 랩톱) 일 때 매우 유용 합니다. .PCD는 네트워크의 마지막 다리를 통과 하는 작은 패킷 스트림을 만듭니다. 그런 다음이 도구는 패킷 스트림을 분석 하 여이 레그에 따른 지터 및 손실이 통화 품질에 영향을 줄 수 있는 방식을 예측 하 고 보고서를 제공 합니다. 호출이 발생 하는 동안에도 클라이언트에서 .PCD를 계속 실행할 수 있습니다. 패킷 스트림은 대역폭에 큰 영향을 주지 않습니다.

**.PCD 버전 1.1의 최신 릴리스에는 다음과 같은 향상 된 기능이 포함 되어 있습니다.**

  - 더 긴 암호 지원 (이제 최대 127 자까지 가능)

  - 인증 로그인 문제에 대 한 추가 진단

  - Lync 하이브리드 배포에 대 한 향상 된 지원

  - 자격 증명 선택에 대 한 업데이트

  - 향상 된 안정성

의견을 보내주셔서 감사 합니다. 모든 지원 질문이 나 문제를의 [.Pcd 피드백](mailto:pcdfb@microsoft.com) 별칭으로 보내 주시기 <pcdfb@microsoft.com>바랍니다.

이 항목에는 다음 섹션이 포함 되어 있습니다.

  - Lync .PCD 버전

  - Lync .PCD 시스템 요구 사항

  - Lync .PCD 기능

  - Lync .PCD 실행

  - Lync .PCD 제거

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync .PCD 버전

이 항목에서는 무료 다운로드에 사용할 수 있는 도구의 다음 버전에 대해 설명 합니다.

  - Windows 데스크톱 앱 ([https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914))

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync .PCD 시스템 요구 사항

<div>


> [!NOTE]  
> .PCD를 사용 하려면 Lync Server 배포에서 모바일 클라이언트를 지원 하기 위해 통합 커뮤니케이션 웹 API (c)를 설치 하 고 구성 해야 합니다. 이 경우 Lync Server와 함께 설치 됩니다.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows 데스크톱 앱 요구 사항

  - 모든 버전의 Windows 7 또는 Windows 8 운영 체제

  - Microsoft .NET Framework 4.5는 다음 위치에서 제공 됩니다.[https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync .PCD 기능

Lync .PCD에는 다음과 같은 기능이 포함 되어 있습니다.

  - 필요할 때 기본값으로 실행 (2 분 버스트)

  - Always On에서 실행 (맞춰진 보기에서 최대 24 시간) 모드

  - 테스트 실행의 기록 보기

  - 로그인 실패 진단 (Windows 8 용 Lync .PCD)

![Lync .PCD features 로그인 진행 스크린샷](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync .PCD features 로그인 진행 스크린샷")

  - 네트워크 메트릭의 그래픽 보기-네트워크 MOS, 패킷 손실 및 인터 도착 지터 (전체 화면 및 맞춰진 보기)입니다.

**전체 화면 보기**

![PreCall 진단 도구 테스트 결과 그래프](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall 진단 도구 테스트 결과 그래프")

**맞춰진 보기**

![PreCall 진단 도구 사용률 테스트 결과](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall 진단 도구 사용률 테스트 결과")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Lync .PCD 실행

<div>

## <a name="running-windows-desktop-app"></a>Windows 데스크톱 앱 실행

1.  Windows 7 시스템에서 .PCD을 시작 하려면 **시작** 메뉴에서 **PreCall 진단을** 선택 합니다.
    
    Windows 8 시스템에서 .PCD을 시작 하려면 시작 화면에서 아이콘을 선택 하거나 "PreCall 진단"을 검색 합니다.
    
    ![PreCall 진단 도구 아이콘](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall 진단 도구 아이콘")

2.  도구가 시작 되 면 기본 자격 증명을 제공 하는 방법을 선택 하 고 **PreCall 진단 도구 옵션** 대화 상자에서 네트워크 운영 모드를 선택한 다음 **확인**을 선택 합니다.

3.  **테스트 시작** 단추를 선택 하 여 진단 실행을 시작 합니다.
    
    **네트워크 자격 증명 사용** 옵션을 선택한 경우 테스트가 즉시 시작 됩니다.
    
    **내 자격 증명 입력** 옵션을 선택한 경우 **Windows 보안** 대화 상자가 열립니다. 자격 증명을 입력 하면 테스트가 시작 됩니다.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Lync .PCD 제거

Lync .PCD을 제거 하려면 운영 체제에 대 한 절차를 따르세요.

  - Windows 7 시스템에서 **제어판**을 열고 **프로그램 및 기능**을 선택한 다음 **Lync 2013 PreCall Diagnostics**를 두 번 클릭 합니다.

  - Windows 8 시스템에서 .PCD 타일을 마우스 오른쪽 단추로 클릭 하 고 시작 화면 아래쪽의 앱 표시줄에서 **제거** 를 클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

