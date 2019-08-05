---
title: 비즈니스용 Skype 서버에서의 회의 하드웨어 및 소프트웨어 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: '요약: 비즈니스용 Skype 서버에서 회의를 위한 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용을 보려면이 항목을 읽으십시오.'
ms.openlocfilehash: c4efb85c7ae1674cab7ee123833df779a835e14c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187827"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서의 회의 하드웨어 및 소프트웨어 요구 사항

**요약:** 비즈니스용 Skype 서버에서의 회의 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은이 항목을 참조 하세요.

이 섹션에서는 웹 회의, 오디오 및 비디오 (A/V) 회의, 전화 접속 회의, IM (인스턴트 메시징) 회의에 대 한 하드웨어 및 소프트웨어 요구 사항에 대해 설명 합니다. 모든 회의 기능은 프런트 엔드 서버에서 실행 됩니다. 다음 다이어그램에 표시 된 것 처럼 다양 한 유형의 회의에 대 한 추가 요구 사항이 있습니다.

예를 들어 전화 접속 회의를 허용 하려는 경우, PSTN (공용 전환 통신 네트워크)에 연결 하기 위해 중재 서버와 게이트웨이를 배포 해야 합니다. 웹 회의를 허용 하려는 경우 비즈니스용 Skype 서버가 Office Web Apps 서버에 연결할 수 있는지 확인 해야 합니다. 외부 사용자가 회의에 참가할 수 있도록 허용 하려면 Edge 서버를 배포 해야 합니다.

**회의 기능 및 요구 사항**

![회의 구성 요소](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 토폴로지 고려 사항에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 회의 토폴로지 계획](conferencing-topology.md)을 참조 하세요.

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>프런트 엔드 서버에 대 한 하드웨어 및 소프트웨어 요구 사항

웹 회의, A/V 회의, 전화 접속 회의, 메신저 회의는 모두 프런트 엔드 서버와 함께 collocated, 서버 하드웨어 및 소프트웨어 요구 사항은 프런트 엔드 서버와 동일 합니다. 이러한 요구 사항에 대 한 자세한 내용은 비즈니스용 skype [server 2015에 대 한 서버 요구 사항](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 및 비즈니스용 skype server 2015 또는 비즈니스용 skype [Server 2019의 서버 요구](../../../SfBServer2019/plan/system-requirements.md)사항에 대 한 [환경 요구](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 사항을 참조 하세요.

## <a name="requirements-for-web-conferencing"></a>웹 회의에 대 한 요구 사항

웹 회의를 사용 하도록 선택한 경우 다음을 계획 해야 합니다.

- 웹 회의 콘텐츠를 저장 하는 데 사용 되는 파일 저장소에 액세스할 수 있습니다.

- 전화 회의 중에 PowerPoint 파일을 공유 하기 위해 필요한 Office Web Apps 서버와 통합

### <a name="file-store"></a>파일 저장소

비즈니스용 Skype 서버 웹 회의 서비스는 파일 저장소의 모임 중에 공유 된 콘텐츠를 저장 합니다. 배포의 일부로 Standard Edition server 또는 Enterprise Edition 프런트 엔드 풀에 대 한 파일 저장소로 사용할 파일 공유를 지정 해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다. 자세한 내용은 비즈니스용 [Skype 서버에서 파일 공유 만들기](../../deploy/install/create-a-file-share.md)를 참조 하세요. 웹 회의 서비스는 콘텐츠를 파일 저장소에 저장 하기 전에 암호화 합니다.

비즈니스용 Skype 서버는 직접 연결 저장소 (DAS) 또는 파일 저장소에 대 한 독립 디스크 (RAID)의 중복 배열 (분산 파일 시스템)에 있는 파일 공유를 사용 하도록 지원 합니다. 비즈니스용 Skype 서버 배포 마법사에서 파일 공유 위치를 정의한 후에는 비즈니스용 Skype 서버에서 다음과 같은 파일 공유 내에 폴더 구조를 만듭니다.

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

그런 다음 웹 회의 서비스는 PowerPoint 슬라이드, 화이트 보드, 설문 조사, 첨부 파일 등의 콘텐츠를 WebServices 폴더에 있는 CollabContent 및 CollabMetadata 폴더에 저장 합니다.

### <a name="office-web-apps-server"></a>Office Web Apps 서버

웹 회의 기능을 사용 하려면 office Web Apps 서버를 설치 하 고 Office Web Apps 서버와 통신 하기 위해 비즈니스용 Skype 서버를 구성 해야 합니다.

비즈니스용 Skype Server, SQL Server 또는 기타 서버 응용 프로그램을 실행 하 고 있지 않은 독립 실행형 컴퓨터에 Office Web Apps 서버를 설치 해야 합니다. (해당 컴퓨터에 Office 버전이 설치 되어 있지 않아야 합니다.) Office Web Apps Server를 실행 하는 데 사용 되는 컴퓨터에는 .NET Framework 4.5 및 Windows PowerShell 3.0을 포함 하 여 특정 소프트웨어 집합도 설치 되어 있어야 합니다. 이러한 요구 사항은 인증서 및 IIS (인터넷 정보 서비스)를 구성 하는 방법에 대 한 정보와 함께 [Microsoft Office Web Apps 배포 웹 사이트](https://go.microsoft.com/fwlink/p/?linkid=257525)에서 자세히 설명 합니다.

Office Web Apps 서버에서 작동 하도록 비즈니스용 Skype 서버를 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 Office Web Apps 서버 통합 구성을](../../deploy/deploy-conferencing/office-web-app-server.md)참조 하세요.

## <a name="requirements-for-audio-and-video-conferencing"></a>오디오 및 비디오 회의에 대 한 요구 사항

A/V 회의를 계획 하려면 조직에 필요한 회의 미디어 유형에 필요한 네트워크 대역폭을 이해 해야 합니다. 여기에는 오디오, 비디오, 파노라마 비디오가 포함 될 수 있습니다. 네트워크 대역폭이 충분 하지 않으면 사용자 환경이 심각 하 게 저하 될 수 있습니다.

회의를 위한 오디오 및 비디오 용량 계획에 대 한 자세한 내용은 [비즈니스용 Skype에 대 한 네트워크 요구 사항 계획](../../plan-your-deployment/network-requirements/network-requirements.md)을 참조 하세요.

CAC (호출 허용 제어)를 사용 하 여 A/V 회의에 사용 되는 네트워크 대역폭을 관리할 수 있습니다. 이는 중앙 사이트와 지점 간 제한 된 대역폭 연결과 같은 제한 네트워크에 중요 합니다. 자세한 내용은 [비즈니스용 Skype 서버의 통화 허용 제어 계획](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)을 참조 하세요.

네트워크에 오디오 회의를 배포 하는 경우 헤드셋과 같은 오디오 장치가 있어야 오디오 회의에 참가할 수 있습니다. 비디오 회의를 배포 하는 경우 사용자 용 웹캠 등의 비디오 장치를 배포 해야 합니다. 오디오 및 비디오 장치 모두에 대해 디바이스 배포와 사용자 교육이 고려해 야 하는 중요 한 단계입니다. 자세한 내용은 [클라이언트 및 장치 계획](../../plan-your-deployment/clients-and-devices/clients-and-devices.md)을 참조 하세요. 최적의 사용자 환경을 위해 Microsoft에서 모든 디바이스 유형에 대해 인증 하는 UC (통합 통신) 장치를 사용 하는 것이 좋습니다. UC 인증 장치에 대 한 자세한 내용은 [비즈니스용 Skype의 전화 및 장치](https://go.microsoft.com/fwlink/?LinkId=619916)를 참조 하세요.

## <a name="requirements-for-dial-in-conferencing"></a>전화 접속 회의에 대 한 요구 사항

전화 접속 회의는 다양 한 구성 요소를 포함 하는 비즈니스용 Skype 서버 회의 작업 부하의 선택적 기능입니다. 일부 구성 요소는 전화 접속 회의 및 엔터프라이즈 음성 구성 요소에만 해당 됩니다. 이 섹션에서는 전화 접속 회의에 필요한 구성 요소의 요구 사항에 대해 설명 합니다. 중재 서버 및 PSTN (공용 전환 전화 네트워크) 게이트웨이 요구 사항에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 중재 서버 구성 요소](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md) 를 참조 하 고 [비즈니스용 Skype 서버의 토폴로지 작성기에서 중재 서버를 배포](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)합니다.

### <a name="required-components"></a>필수 구성 요소

전화 접속 회의를 구성 하려면 다음 비즈니스용 Skype 서버 구성 요소를 설치 해야 합니다.

- 통합 커뮤니케이션 응용 프로그램 서비스 (c) (응용 프로그램 서비스 라고 함)

- 회의 수행자 응용 프로그램

- 회의 알림 신청

- 전화 접속 회의 설정 웹 페이지

- 하나 이상의 중재 서버와 하나 이상의 PSTN 게이트웨이

전화 접속 회의의 경우 응용 프로그램 서비스, 회의 수행자 응용 프로그램, 회의 알림 응용 프로그램은 프런트 엔드 서버와 동일한 운영 체제 요구 사항을 가집니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)참조 하세요.

회의 수행자 응용 프로그램 및 회의 알림 응용 프로그램을 실행 하려면 Windows Media 형식 런타임이 프런트 엔드 서버에 설치 되어 있어야 합니다. 대기 중인 음악, 기록 된 이름 및 프롬프트에 사용 되는 WMA (Windows Media audio) 파일을 재생 하려면 windows Media 형식 런타임이 필요 합니다. Windows Server 2012 또는 Windows Server 2012 R2에 설치 하는 경우 Windows Media Foundation을 설치 해야 합니다 (권장). Windows 2012 이전 버전의 Windows Server에 설치 하는 경우 windows Media 형식 런타임을 가져오기 위해 Windows 데스크톱 환경이 설치 되어 있는지 확인 해야 합니다.

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>전화 접속 회의를 위한 오디오 파일 요구 사항

비즈니스용 Skype 서버는 전화 접속 회의를 위한 음성 프롬프트 및 음악 사용자 지정을 지원 하지 않습니다. 그러나 기본 오디오 파일을 변경 해야 하는 강력한 비즈니스 요구 사항이 있는 경우에는 Microsoft 기술 자료 문서 961177에서 [전화 접속 오디오 회의를 위한 음성 프롬프트 또는 음악 파일을 사용자 지정 하는 방법을](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)참조 하세요.

또한 관리자가 사용자 지정 프롬프트를 사용 하 여 전화 발신자가 비즈니스용 Skype 모임에 참가할 때 사용 하는 기본 음성 프롬프트를 바꿀 수 있는 [Microsoft Lync Server 회의 수행자 사용자 지정 음성 메시지](https://go.microsoft.com/fwlink/p/?LinkId=396880) 관리 유틸리티를 사용할 수도 있습니다. 다른 모임 입장 환경을 제공 합니다. 사용자 지정 음성 메시지는 Enterprise 또는 Standard Edition 서버에 설치할 수 있습니다.

회의 수행자 응용 프로그램 및 회의 알림 신청에는 대기 중인 음악, 기록 된 이름 및 오디오 프롬프트 파일에 대 한 다음과 같은 요구 사항이 있습니다.

- WMA (Windows Media Audio) 파일 형식

- 16 비트 모노

- 48 kbps 2-CBR 통과 (상수 비트 전송률)

- 음성 수준-24DB

### <a name="user-requirements-for-dial-in-conferencing"></a>전화 접속 회의에 대 한 사용자 요구 사항

전화 접속 회의 사용자는 자신의 계정에 고유한 전화번호 또는 내선 번호를 할당 해야 합니다. 이 요구 사항은 전화 접속 회의 중에 인증을 지원 합니다. 엔터프라이즈 사용자 (즉, 조직 내 Active Directory 도메인 서비스 자격 증명과 비즈니스용 Skype Server 계정이 있는 사용자)는 전화 번호 (또는 확장명)와 PIN (개인 식별 번호)을 입력 하 여 회의에 전화를 인증 된 사용자입니다.

## <a name="port-requirements-for-conferencing"></a>회의의 포트 요구 사항

회의 기능을 사용 하기 위해서는 비즈니스용 Skype Server에서 특정 포트가 열려 있어야 합니다. 다음 표에는 회의의 포트 요구 사항이 나와 있습니다. 모든 포트 요구 사항에 대 한 자세한 내용은 [서버의 포트 및 프로토콜 요구 사항](../../plan-your-deployment/network-requirements/ports-and-protocols.md)을 참조 하세요.

**필요한 서버 포트**


|**서버 역할**|**서비스 이름**|**포트**|**프로토콜별**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 메신저 대화 회의 서비스  <br/> |5062  <br/> |NET.TCP  <br/> |인스턴트 메시징 (IM) 회의에 들어오는 SIP 요청에 사용 됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 웹 회의 서비스  <br/> |8057  <br/> |TCP (TLS)  <br/> |클라이언트의 PSOM (영구 공유 개체 모델) 연결을 수신 대기 하는 데 사용 됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 웹 회의 호환성 서비스  <br/> |8058  <br/> |TCP (TLS)  <br/> |Live Meeting 클라이언트 및 이전 버전의 비즈니스용 Skype 서버에서 영구 공유 개체 모델 (PSOM) 연결을 수신 대기 하는 데 사용 됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 오디오/비디오 회의 서비스  <br/> |5063  <br/> |NET.TCP  <br/> |오디오/비디오 (A/V) 회의에 대 한 들어오는 SIP 요청에 사용 됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 오디오/비디오 회의 서비스  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |비디오 회의에 사용 되는 미디어 포트 범위  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 회의 수행자 서비스 (전화 접속 회의)  <br/> |5064  <br/> |NET.TCP  <br/> |전화 접속 회의에 대 한 수신 SIP 요청에 사용 됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 회의 수행자 서비스 (전화 접속 회의)  <br/> |5072  <br/> |NET.TCP  <br/> |전화 교환의 수신 SIP 요청에 사용 됨 (회의에 전화 걸기).  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |5065  <br/> |NET.TCP  <br/> |응용 프로그램 공유에 대 한 수신 SIP 수신 요청에 사용 됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |49152-65535  <br/> |NET.TCP  <br/> |응용 프로그램 공유에 사용 되는 미디어 포트 범위입니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 회의 알림 서비스  <br/> |5073  <br/> |NET.TCP  <br/> |비즈니스용 Skype 서버 회의 알림 서비스에 대 한 들어오는 SIP 요청에 사용 됩니다 (즉, 전화 접속 회의의 경우).  <br/> |
|모든 내부 서버  <br/> |다양 한  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |모든 내부 서버에서 오디오 회의에 사용 되는 미디어 포트 범위 오디오를 종료 하는 모든 서버 (비즈니스용 Skype 서버 회의 수행자 서비스, 비즈니스용 skype 서버 회의 알림 서비스, 비즈니스용 Skype Server 오디오/비디오 회의 서비스)에 사용 됩니다. 중재 서버.  <br/> |
|Office Web Apps 서버  <br/> ||443  <br/> ||비즈니스용 Skype 서버에서 Office Web Apps 서버에 연결 하는 데 사용 됩니다.  <br/> |

**필수 클라이언트 포트**


|**포트**|**프로토콜별**|**상속자**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |웹 회의 세션에 대 한 외부 사용자 액세스에 사용 됩니다.  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |A/V 세션 및 미디어 (TCP)에 대 한 외부 사용자 액세스에 사용 됩니다.  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |A/V 세션 및 미디어 (UDP)에 대 한 외부 사용자 액세스에 사용 됩니다.  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |오디오 포트 범위 (최소 20 개의 포트가 필요 함)  <br/> |
|1024-65535\*  <br/> |TCP/UDP  <br/> |비디오 포트 범위 (최소 20 개 포트 필요).  <br/> |
|1024-65535\*  <br/> |NET.TCP  <br/> |응용 프로그램 공유  <br/> |


