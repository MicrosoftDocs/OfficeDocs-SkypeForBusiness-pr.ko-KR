---
title: 비즈니스용 Skype 서버의 회의에 대한 하드웨어 및 소프트웨어 요구 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버의 회의에 대한 하드웨어 및 소프트웨어 요구 사항에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 59ad84cd0f4445709b236baecafeeab240e6ea65
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814018"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 회의에 대한 하드웨어 및 소프트웨어 요구 사항

**요약:** 이 항목을 읽고 비즈니스용 Skype 서버의 회의에 대한 하드웨어 및 소프트웨어 요구 사항에 대해 자세히 알아보습니다.

이 섹션에서는 웹 회의, A/V(오디오 및 비디오) 회의, 전화 접속 회의 및 IM(인스턴트 메시징) 회의에 대한 하드웨어 및 소프트웨어 요구 사항에 대해 설명합니다. 모든 회의 기능은 프런트 엔드 서버에서 실행됩니다. 다음 다이어그램과 같이 다양한 유형의 회의에 대한 추가 요구 사항이 있습니다.

예를 들어 전화 접속 회의를 허용하려면 중재 서버와 PSTN(Public Switched Telephone Network)에 연결하기 위한 게이트웨이를 배포해야 합니다. 웹 회의를 허용하려면 비즈니스용 Skype 서버가 Office Web Apps 서버에 연결할 수 있도록 해야 합니다. 외부 사용자가 회의에 참가하도록 허용하려면 에지 서버를 배포해야 합니다.

**회의 기능 및 요구 사항**

![회의 구성 요소](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 토폴로지 고려 사항과 관련한 자세한 내용은 비즈니스용 Skype 서버의 회의 토폴로지 [계획(Plan your conferencing topology)을 참조하십시오.](conferencing-topology.md)

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>프런트 엔드 서버에 대한 하드웨어 및 소프트웨어 요구 사항

웹 회의, A/V 회의, 전화 접속 회의 및 IM 회의는 모두 프런트 엔드 서버와 함께 제공될 것이기 때문에 서버 하드웨어 및 소프트웨어 요구 사항은 프런트 엔드 서버와 동일합니다. 이러한 요구 사항에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015의](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 서버 요구 사항 및 비즈니스용 [Skype 서버 2015의](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 환경 요구 사항 또는 비즈니스용 [Skype 서버 2019의](../../../SfBServer2019/plan/system-requirements.md)서버 요구 사항을 참조하세요.

## <a name="requirements-for-web-conferencing"></a>웹 회의 요구 사항

웹 회의를 사용하도록 설정한 경우에는 다음 사항을 계획해야 합니다.

- 웹 회의 콘텐츠를 저장하는 데 사용되는 파일 저장소 액세스

- 회의 중에 PowerPoint 파일을 공유하는 데 필요한 Office Web Apps 서버와의 통합

### <a name="file-store"></a>파일 저장소

비즈니스용 Skype 서버 웹 회의 서비스는 모임 중에 공유되는 콘텐츠를 파일 저장소에 저장합니다. 배포의 일부로 Standard Edition 서버 또는 Enterprise Edition 프런트 엔드 풀의 파일 저장소로 사용할 파일 공유를 지정해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버에서 파일 공유 [만들기를 참조하세요.](../../deploy/install/create-a-file-share.md) 웹 회의 서비스는 콘텐츠를 파일 저장소에 저장하기 전에 암호화합니다.

비즈니스용 Skype 서버는 DFS(분산 파일 시스템)를 비롯한 DAS(직접 연결된 저장소) 또는 SAN(저장 영역 네트워크)에서 파일 공유를 사용하고 파일 저장소에 대한 RAID(중복된 디스크) 배열에서 파일 공유를 사용할 수 있습니다. 비즈니스용 Skype 서버 배포 마법사에서 파일 공유의 위치를 정의한 후 비즈니스용 Skype 서버는 파일 공유 내에 다음과 같은 폴더 구조를 만듭니다.

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

그러면 웹 회의 서비스에서 PowerPoint 슬라이드, 화이트보드, 설문 조사, 첨부 파일 등의 콘텐츠를 WebServices 폴더에 있는 CollabContent 및 CollabMetadata 폴더에 저장합니다.

### <a name="office-web-apps-server"></a>Office Web Apps 서버

웹 회의 기능을 사용하려면 Office Web Apps 서버를 설치하고 Office Web Apps 서버와 통신하도록 비즈니스용 Skype 서버를 구성해야 합니다.

Office Web Apps 서버는 비즈니스용 Skype 서버, 비즈니스용 Skype 서버 또는 다른 서버 응용 프로그램을 SQL Server 독립 실행형 컴퓨터에 설치해야 합니다. (해당 컴퓨터에 설치된 Office 버전이 없습니다.) Office Web Apps 서버를 실행하기 위해 사용되는 컴퓨터에는 .NET Framework 4.5 및 Windows PowerShell 3.0을 비롯한 특정 소프트웨어 집합도 설치되어 있어야 합니다. 인증서 및 IIS(인터넷 정보 서비스) 구성에 대한 정보와 함께 이러한 요구 사항은 Microsoft Office Web Apps 배포 웹 [사이트에서 자세히 설명합니다.](https://go.microsoft.com/fwlink/p/?linkid=257525)

비즈니스용 Skype 서버가 Office Web Apps 서버와 작동하도록 구성하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버에서 Office Web Apps 서버와의 통합 구성을 [참조하세요.](../../deploy/deploy-conferencing/office-web-app-server.md)

## <a name="requirements-for-audio-and-video-conferencing"></a>오디오 및 비디오 회의 요구 사항

A/V 회의를 계획하려면 조직에서 사용할 회의 미디어 유형에 필요한 네트워크 대역폭을 이해해야 합니다. 이러한 미디어 유형으로는 오디오, 비디오, 파노라마 비디오 등이 있습니다. 네트워크 대역폭이 부족하면 최종 사용자의 환경이 크게 저하될 수 있습니다.

회의의 오디오 및 비디오 용량 계획에 대한 자세한 내용은 비즈니스용 Skype에 대한 네트워크 요구 사항 [계획을 참조하세요.](../../plan-your-deployment/network-requirements/network-requirements.md)

CAC(통화 제어)를 사용하여 A/V 회의에 사용되는 네트워크 대역폭을 관리할 수 있습니다. 이것은 중앙 사이트와 분기 사이트 간 제한된 대역폭 링크와 같은 제한적인 네트워크에서 중요합니다. 자세한 내용은 비즈니스용 Skype 서버의 통화 입력 제어 [계획(Plan for call admission control)을 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)

오디오 회의를 네트워크에 배포한 경우 사용자는 헤드셋과 같은 오디오 장치가 있어야 오디오 회의에 참가할 수 있습니다. 또한 비디오 회의를 배포한 경우 사용자를 위해 웹캠과 같은 비디오 장치를 배포해야 합니다. 오디오 및 비디오 장치의 경우 장치 배포 및 사용자 교육이 고려해야 하는 중요한 단계입니다. 자세한 내용은 클라이언트 및 [장치 계획을 참조하세요.](../../plan-your-deployment/clients-and-devices/clients-and-devices.md) 최적의 사용자 환경을 보장하려면 모든 장치 유형에 대해 Microsoft에서 인증한 UC(통합 통신) 장치를 사용하는 것이 좋습니다. UC 인증 장치에 대한 자세한 내용은 비즈니스용 Skype의 전화 및 [장치를 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=619916)

## <a name="requirements-for-dial-in-conferencing"></a>전화 접속 회의 요구 사항

전화 접속 회의는 다양한 구성 요소를 포함하는 비즈니스용 Skype 서버 회의 작업의 선택적 기능입니다. 일부 구성 요소는 전화 접속 회의와 관련되며 또 다른 일부 구성 요소는 Enterprise Voice 구성 요소입니다. 이 섹션에서는 전화 접속 회의에 필요한 구성 요소의 요구 사항에 대해 설명합니다. 중재 서버 및 PSTN(Public Switched Telephone Network) 게이트웨이 요구 사항에 대한 자세한 내용은 비즈니스용 [Skype](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) 서버의 중재 서버 구성 요소 및 비즈니스용 [Skype](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)서버의 토폴로지 작성기에서 중재 서버 배포를 참조하세요.

### <a name="required-components"></a>필수 구성 요소

전화 접속 회의를 구성하려면 먼저 다음 비즈니스용 Skype 서버 구성 요소를 설치해야 합니다.

- UCAS(Unified Communications Application Service)(응용 프로그램 서비스라고도 합니다.)

- 회의 길잡이 응용 프로그램

- 회의 알림 응용 프로그램

- 전화 접속 회의 설정 웹 페이지

- 하나 이상의 중재 서버 및 하나 이상의 PSTN 게이트웨이

전화 접속 회의, 응용 프로그램 서비스, 회의 전화자 응용 프로그램 및 회의 공지 사항 응용 프로그램의 경우 프런트 엔드 서버와 운영 체제 요구 사항이 동일합니다. 자세한 내용은 비즈니스용 [Skype 서버 2015에](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)대한 서버 요구 사항을 참조하세요.

회의 참석자 응용 프로그램 및 회의 공지 사항을 사용하려면 프런트 엔드 서버에 Windows Media 형식 런타임이 설치되어야 합니다. Windows Media 형식 런타임은 보류 음악, 녹음된 이름 및 음성 메시지에 사용되는 WMA(Windows Media 오디오) 파일을 재생하는 데 필요합니다. Windows Server 2012 R2 또는 Windows Server 2012(권장)에 설치하는 경우 Microsoft Media Foundation을 설치하여 Windows Media 형식 런타임이 제공됩니다. Windows 2012 이전 버전의 Windows Server에 설치하는 경우 Windows Media 형식 런타임이 필요하도록 Windows 데스크톱 환경이 설치되어 있는지 확인해야 합니다.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>전화 접속 회의에 대한 오디오 파일 요구 사항

비즈니스용 Skype 서버는 전화 접속 회의를 위한 음성 음성 프롬프트 및 음악 사용자 지정을 지원하지 않습니다. 그러나 기본 오디오 파일을 변경해야 하는 강력한 비즈니스 요구가 있는 경우 Microsoft 기술 자료 문서 [](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)961177, 전화 접속 오디오 회의를 위해 음성 음성 프롬프트 또는 음악 파일을 사용자 지정하는 방법을 참조하세요.

[또한 Microsoft Lync Server 회의](https://go.microsoft.com/fwlink/p/?LinkId=396880) 전화 교환 사용자 지정 음성 프롬프트 관리 유틸리티를 사용하여 전화 발신자에서 비즈니스용 Skype 모임에 참가할 때 사용되는 기본 음성 음성 프롬프트를 사용자 지정 음성 메시지로 바꾸어 다른 모임 입력 환경을 제공할 수 있습니다. 사용자 지정 음성 음성 프롬프트는 Enterprise 또는 Standard Edition 서버에 설치할 수 있습니다.

회의 참석자 응용 프로그램 및 회의 공지 사항 응용 프로그램에는 보류 음악, 녹음된 이름 및 오디오 음성 프롬프트 파일에 대한 다음 요구 사항이 있습니다.

- WMA(Windows Media 오디오) 파일 형식

- 16비트 모노

- 48kbps 2-pass CBR(상수 비트 전송률)

- -24DB의 음량 수준

### <a name="user-requirements-for-dial-in-conferencing"></a>전화 접속 회의에 대한 사용자 요구 사항

전화 접속 회의 사용자의 계정에 고유한 전화 번호나 내선 번호가 지정되어야 합니다. 이 요구 사항은 전화 접속 회의를 진행하는 동안 인증을 지원합니다. 엔터프라이즈 사용자(조직 내에서 Active Directory 도메인 서비스 자격 증명 및 비즈니스용 Skype 서버 계정이 있는 사용자)는 전화 번호(또는 내선 번호) 및 PIN(개인 식별 번호)을 입력하여 인증된 사용자로 전화 회의에 전화 접속합니다.

## <a name="port-requirements-for-conferencing"></a>회의에 대한 포트 요구 사항

회의 기능을 사용하려면 비즈니스용 Skype 서버에 특정 포트가 열려야 합니다. 다음 표에는 회의에 대한 포트 요구 사항이 나열되어 있습니다. 모든 포트 요구 사항에 대한 자세한 내용은 서버의 포트 및 [프로토콜 요구 사항을 참조하세요.](../../plan-your-deployment/network-requirements/ports-and-protocols.md)

**필수 서버 포트**


|**서버 역할**|**서비스 이름**|**Port(포트)**|**Protocol(프로토콜)**|**참고**|
|:-----|:-----|:-----|:-----|:-----|
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 IM 회의 서비스  <br/> |5062  <br/> |TCP  <br/> |IM(인스턴트 메시징) 회의의 받는 SIP 요청에 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 웹 회의 서비스  <br/> |8057  <br/> |TCP(TLS)  <br/> |클라이언트에서 PSOM(영구적 공유 개체 모델) 연결을 수신 대기하는 데 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 웹 회의 호환성 서비스  <br/> |8058  <br/> |TCP(TLS)  <br/> |Live Meeting 클라이언트 및 이전 버전의 비즈니스용 Skype 서버에서 PSOM(영구적 공유 개체 모델) 연결을 수신하는 데 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 오디오/비디오 회의 서비스  <br/> |5063  <br/> |TCP  <br/> |A/V(오디오/비디오) 회의의 받는 SIP 요청에 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 오디오/비디오 회의 서비스  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |비디오 회의에 사용되는 미디어 포트 범위입니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 회의 도우미 서비스(전화 접속 회의)  <br/> |5064  <br/> |TCP  <br/> |전화 접속 회의의 받는 SIP 요청에 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 회의 도우미 서비스(전화 접속 회의)  <br/> |5072  <br/> |TCP  <br/> |전화 접속 회의의 받는 SIP 요청에 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |5065  <br/> |TCP  <br/> |응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |49152-65535  <br/> |TCP  <br/> |응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 회의 공지 서비스  <br/> |5073  <br/> |TCP  <br/> |비즈니스용 Skype 서버 회의 알림 서비스의 받는 SIP 요청(즉, 전화 접속 회의용)에 사용됩니다.  <br/> |
|모든 내부 서버  <br/> |다양한  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |모든 내부 서버의 오디오 회의에 사용되는 미디어 포트 범위입니다. 오디오를 종료하는 모든 서버에서 사용됩니다. 프런트 엔드 서버(비즈니스용 Skype 서버 회의 전화자 서비스, 비즈니스용 Skype 서버 회의 공지 서비스 및 비즈니스용 Skype 서버 오디오/비디오 회의 서비스) 및 중재 서버.  <br/> |
|Office Web Apps 서버  <br/> ||443  <br/> ||비즈니스용 Skype 서버에서 Office Web Apps 서버에 연결하는 데 사용됩니다.  <br/> |

**필수 클라이언트 포트**


|**Port(포트)**|**Protocol(프로토콜)**|**참고**|
|:-----|:-----|:-----|
|443  <br/> |TCP(PSOM/TLS)  <br/> |웹 회의 세션에 대한 외부 사용자 액세스에 사용됩니다.  <br/> |
|443  <br/> |TCP(STUN/MSTURN)  <br/> |A/V 세션 및 미디어(TCP)에 대한 외부 사용자 액세스에 사용됩니다.  <br/> |
|3478  <br/> |UDP(STUN/MSTURN)  <br/> |A/V 세션 및 미디어(UDP)에 대한 외부 사용자 액세스에 사용됩니다.  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |오디오 포트 범위(최소 20개 포트 필요)  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |비디오 포트 범위(최소 20개 포트 필요)  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |응용 프로그램 공유  <br/> |


