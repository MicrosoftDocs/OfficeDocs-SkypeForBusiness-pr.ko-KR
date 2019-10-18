---
title: 알려진 문제점
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 이 문서에서는 Microsoft 팀 대화방에 대 한 알려진 문제점을 기능별로 설명 합니다.
ms.openlocfilehash: 79bebf69c0d4fc8dabff3e294166e7ab08b79166
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571392"
---
# <a name="known-issues"></a>알려진 문제점 
 
이 문서에는 Microsoft 팀 대화방의 알려진 문제점에 대 한 기능 영역별로 나와 있습니다.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Update 

| 발행 제목 |  동작 \/ 증상 | 알려진 해결 방법 | 기술 자료 문서 |
|  ---        |      ---             |   ---            | --- |
|  앱이 만료 되었습니다.         |    Microsoft 팀 회의실 콘솔에 "시스템 구성 오래 됨" 오류가 표시 됩니다.                |   [Microsoft 팀 대화방 복구 도구 사용](recovery-tool.md)             |  없음 |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>사용자 인터페이스 

| 발행 제목 |  동작 \/ 증상 | 알려진 해결 방법 | 기술 자료 문서 |
|  ---        |      ---             |   ---            | --- |
|가상 키보드가 없음   | Microsoft 팀 대화방에 정보를 입력 해야 하는 경우 가상 키보드가 표시 되지 않습니다. 이 문제는 Microsoft 팀 대화방이 실행 되는 Surface Pro 4에 Windows 10 크리에이터 업데이트 (버전 1703)가 설치 된 후에 발생 합니다. | 이 문제를 해결 하려면 가상 키보드를 수동으로 여십시오. 이렇게 하려면 다음 단계를 따르세요.<br><br> **1.** 작업 표시줄을 길게 탭 한 다음 **터치 키보드 단추 표시** 를 탭 합니다. 작업 표시줄의 오른쪽에 키보드 아이콘이 표시 됩니다. <br><br> **2.** 키보드 아이콘을 탭 하 여 가상 키보드를 엽니다. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>하드웨어

| 발행 제목 |  동작 \/ 증상 | 알려진 해결 방법 | 기술 자료 문서 |
|  ---        |      ---             |   ---            |   --- |
| 감지 되지 않은 모니터 | Surface Pro (모델 2017) 장치에서 Microsoft 팀 대화방을 실행 하면 모니터가 검색 되지 않습니다. |  Surface Pro 전원 단추를 20 초 이상 누르고 있습니다. 이렇게 하면 장치가 다시 시작 되 고 그래픽 캐시가 지워집니다. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>제한 사항 및 예상 동작

***

Microsoft 팀 대화방은 HDMI 수집 기능 (비디오, 오디오)에 문제가 발생 하는 데 관측 된 HDCP 입력을 지원 하지 않습니다. Microsoft 팀 대화방에 연결 된 스위치에 HDCP 옵션이 설정 되어 있는지 확인 합니다. 

***

원본에서 대기 모드를 해제할 때 자동으로 활성 비디오 원본 (예: MTR 콘솔)으로 전환 하려면 특정 조건이 충족 되어야 합니다. 이 기능은 선택 사항 이지만 Microsoft 팀 공간 소프트웨어에서 지원 되며, 기본 하드웨어에서 기능을 지 원하는 경우 제공 됩니다. 채팅방 표시로 사용 되는 소비자 TV는 HDMI의 CEC (소비자 전자 컨트롤) 기능을 지원 해야 합니다.  선택 된 dock 또는 console (CEC를 지원 하지 않을 수 있음) (제조업체 지원 문서 참조)에 따라 원하는 동작을 사용 하도록 설정 하려면 [HD CTL 100의 extron](https://www.extron.com/article/hdctl100ad) 작업 영역 컨트롤러가 필요할 수 있습니다. 

***

항상 유선 1 Gbps 네트워크 연결을 사용 하 여 필요한 대역폭을 보유 하 고 있는지 확인 합니다. 

***

Microsoft 팀 대화방 장치가 도메인에서 신뢰를 상실 한 경우에는 디바이스에 인증 하 고 설정을 열 수 없게 됩니다. 예를 들어 도메인에 가입한 후 도메인에서 Microsoft 팀 대화방을 제거 하면 신뢰가 손실 됩니다. 해결 방법은 로컬 관리자 계정으로 로그인 하는 것입니다. 
***
64 비트 버전의 Windows 10 Enterprise 기념일 edition (영어 버전 1607)은 Microsoft 팀 회의실 릴리스 3.0.12.0에서 더 이상 지원 되지 않습니다. 
***
Microsoft 팀 대화방은 다중 창 응용 프로그램 이므로 장치의 HDMI 포트에 연결 하 여 앱이 올바르게 작동 하도록 하는 방 디스플레이가 앞에 있어야 합니다. 테스트 하는 경우에는 HDMI 디스플레이가 연결 되어 있는지 확인 하 고, 아직 표시를 구매 하지 않은 경우에는 dummy HDMI 플러그를 사용 해야 합니다.
***
Windows 10 1903는 그래픽 드라이버 문제로 인해 Crestron의 Microsoft 팀 공간 장치에 아직 제공 되지 않습니다.

***
<a name="See"> </a>  
## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 도움말](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)
