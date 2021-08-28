---
title: 2016년 8월에 응답 그룹 응용 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 사용자 그룹에 비즈니스용 Skype 서버 Enterprise Voice 라우팅을 설정할 수 있도록 하여 2016년 8월에 응답 그룹을 계획합니다. 오디오 파일 요구 사항을 포함합니다.
ms.openlocfilehash: 41decf3e61e32867dd6b1d726bb551f8c2ae38f0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631582"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>2016년 8월에 응답 그룹 응용 비즈니스용 Skype 서버

사용자 그룹에 비즈니스용 Skype 서버 Enterprise Voice 라우팅을 설정할 수 있도록 하여 2016년 8월에 응답 그룹을 계획합니다. 오디오 파일 요구 사항을 포함합니다.

조직에 고객 서비스, 내부 지원 센터 또는 부서의 일반 전화 지원과 같은 특정 유형의 통화에 응답하고 관리하는 사용자 그룹이 있는 경우 응답 그룹 응용 프로그램을 배포하여 이러한 유형의 통화를 관리할 수 있습니다. 응답 그룹 응용 프로그램은 수신 전화를 에이전트라고 하는 지정된 사람으로 라우팅하고 대기합니다. 응답 그룹을 사용하여 전화 지원 서비스 사용을 늘리고 이러한 서비스를 실행하는 오버헤드를 줄일 수 있습니다.

발신자 통화가 응답 그룹에 전화를 걸면 헌트 그룹 또는 IVR(대화형 음성 응답) 질문에 대한 발신자 응답에 따라 에이전트로 통화가 라우팅됩니다. 응답 그룹 응용 프로그램은 표준 응답 그룹 라우팅 방법을 사용하여 통화를 사용 가능한 다음 에이전트로 라우팅합니다. 지원되는 통화 라우팅 방법에는 직렬, 가장 긴 유휴, 병렬, 라운드 로빈 및 Attendant 라우팅이 포함됩니다(즉, 모든 수신 전화에 대해 현재 상태와 관계없이 모든 에이전트가 동시에 호출됩니다).

사용할 수 있는 에이전트가 없는 경우 에이전트를 사용할 수 있는 때까지 통화가 큐에 대기됩니다. 큐에 있는 동안 발신자 는 사용 가능한 에이전트가 통화를 수락할 때까지 음악을 듣습니다. 큐가 가득 겼거나 큐에 있는 동안 통화가 시간 종료되는 경우 발신자에 메시지가 듣게 되거나 연결이 끊어지거나 다른 대상(예: 다른 전화 번호 또는 음성 메일)으로 전송될 수 있습니다. 에이전트가 통화를 수락하면 관리자가 응답 그룹을 구성하는 방법에 따라 발신자에 에이전트의 ID가 표시되거나 확인되지 않을 수 있습니다. 에이전트는 공식적인 에이전트일 수 있습니다. 즉, 그룹으로 라우팅된 통화를 수락하려면 먼저 그룹에 로그인해야 합니다. 즉, 비공식적으로 그룹에 로그인하여 전화를 수락하지 않습니다.

> [!NOTE]
> 온-프레미스 사용자만 에이전트가 될 수 있습니다. 에이전트를 온-프레미스에서 온라인으로 이동하면 응답 그룹 통화가 해당 에이전트에게 라우팅되지 않습니다.

> [!NOTE]
> 응답 그룹 응용 프로그램은 일치하는 만들기라는 내부 서비스를 사용하여 통화를 큐에 대기하고 사용 가능한 에이전트를 검색합니다. 응답 그룹 응용 프로그램을 실행하는 각 컴퓨터는 일치하는 만들기 서비스를 실행하지만 풀당 한 번의 일치 서비스만 활성화됩니다. 다른 컴퓨터는 수동적입니다. 계획되지 않은 중단 중에 활성 일치 만들기 서비스를 사용할 수 없게 되는 경우 수동 일치 만들기 서비스 중 하나가 활성화됩니다. 응답 그룹 응용 프로그램은 통화 라우팅 및 큐가 무중단으로 계속 진행될 수 있도록 최선을 다합니다. 그러나 일치하는 서비스 전환이 발생하면 당시 전송되는 모든 호출이 손실됩니다. 예를 들어 전환이 프런트 엔드 서버 다운으로 인해 진행되는 경우 해당 프런트 엔드 서버의 활성 Match Making 서비스에서 현재 처리 중인 호출도 손실됩니다.

## <a name="response-group-workflows"></a>응답 그룹 워크플로

워크플로는 전화가 울리는 시간부터 누군가가 전화를 받는 시간까지의 호출 동작을 정의합니다. 워크플로는 통화 대기에 사용할 큐와, 헌트 그룹에 사용할 라우팅 방법 또는 대화형 응답 그룹에 사용할 질문과 대답을 지정합니다. 또한 워크플로는 시작 메시지, 대기 음악, 업무 시간, 휴일 등의 설정도 정의합니다.

> [!NOTE]
> 에이전트 그룹 및 큐를 먼저 만든 후에 해당 그룹과 큐를 사용하는 워크플로를 만들어야 합니다.

## <a name="management-of-response-groups"></a>응답 그룹 관리

이 비즈니스용 Skype 서버 응답 그룹을 관리하는 데는 응답 그룹 관리자와 응답 그룹 관리자의 두 가지 관리 역할을 사용할 수 있습니다. 응답 그룹 관리자는 모든 응답 그룹의 모든 측면을 관리할 수 있습니다. 응답 그룹 관리자는 특정 측면만 관리할 수 있으며 소유한 응답 그룹에만 관리할 수 있습니다. 관리자 역할은 특정 응답 그룹에 대해 제한된 책임을 특정 응답 그룹에 대해 사용하도록 설정된 사용자에게 위임할 수 있기 때문에 관리 비용을 절감하는 데 도움이 Enterprise Voice. 사용자가 응답 그룹 관리자 및 응답 그룹 관리자일 수 있습니다.

관리자 역할을 수용하기 위해 응답 그룹 응용 프로그램은 관리 또는 **관리되지** 않는 워크플로 유형을 사용 합니다. 다음 표에서는 관리되는 응답 그룹과 관리되지 않는 응답 그룹에 대해 설명하고 있습니다.

**관리되는 응답 그룹 및 관리되지 않는 응답 그룹**

|**응답 그룹 유형**|**설명**|
|:-----|:-----|
|관리되지 않습니다.  <br/> | 관리되지 않는 응답 그룹에는 할당된 관리자가 없습니다. 응답 그룹 관리자만 이러한 응답 그룹을 구성할 수 있습니다. <br/>  관리되지 않는 여러 응답 그룹이 큐 또는 에이전트 그룹을 공유할 수 있습니다. <br/>  응답 그룹을 이전 버전에서 이전 버전으로 비즈니스용 Skype 서버 유형은 관리되지 않습니다.로 설정됩니다. <br/> |
|관리  <br/> | 응답 그룹 관리자는 관리되는 응답 그룹의 모든 측면을 구성할 수 있습니다. <br/>  응답 그룹 관리자는 명시적으로 할당되지 않은 응답 그룹을 보거나 수정할 수 없습니다. <br/>  응답 그룹 관리자는 응답 그룹에 명시적으로 할당된 일부 설정만 구성할 수 있습니다. <br/>  관리되는 응답 그룹은 관리되거나 관리되지 않는 다른 응답 그룹과 큐 또는 에이전트 그룹을 공유할 수 없습니다. <br/> |

다음 표에는 응답 그룹 관리자가 할당된 응답 그룹에 대해 수행할 수 있는 작업과 수행할 수 없는 작업이 설명되어 있습니다.

**응답 그룹 관리자 기능**

|**다음을 구성할 수 있습니다.**|**다음을 만들거나 삭제하거나 구성할 수 있습니다.**|**다음을 할 수 없습니다.**|
|:-----|:-----|:-----|
| Agents <br/>  환영 메시지 <br/>  응답 그룹 이름 <br/>  설명 <br/>  표시 번호 <br/>  업무 시간 <br/>  통화 대기음 <br/>  상태(활성/비활성) <br/>  헌트 그룹 워크플로 또는 IVR(대화형 음성 응답) 워크플로 <br/> | 에이전트 그룹 <br/>  큐 <br/>  휴일 집합 <br/> | 모든 유형의 워크플로 만들기 또는 삭제 <br/>  **SIP URI,** 전화 번호 또는 워크플로 유형과 같은 핵심 응답 그룹 **설정을 수정합니다.**  <br/> |

응답 그룹 관리자는 다음 도구를 사용하여 지정된 응답 그룹을 관리할 수 있습니다.

- 비즈니스용 Skype 서버 제어판

    > [!NOTE]
    > 응답 그룹 관리자는 이 도구를 사용하여 응답 그룹 설정만 관리할 수 있습니다. 다른 비즈니스용 Skype 서버 설정은 관리자가 사용할 수 없습니다.

- 응답 그룹 구성 도구

- 비즈니스용 Skype 서버 관리 쉘

응답 그룹은 부서 또는 작업 그룹 환경에 적합합니다(자세한 내용은 [Capacity Planning for Response Group](/previous-versions/office/lync-server-2013/lync-server-2013-capacity-planning-for-response-group)참조) 완전히 새로운 전화 통신 설치에 배포할 수 있습니다. 이 서비스에서는 배포 Enterprise Voice 통신사 네트워크에서 걸러진 수신 전화를 지원할 수 있습니다. 에이전트는 비즈니스용 Skype, Lync 2013, Lync 2010, Lync 2010 Attendant 또는 Lync 전화 Edition을 사용하여 통화를 라우팅할 수 있습니다.

## <a name="deployment-and-requirements"></a>배포 및 요구 사항

응답 그룹 응용 프로그램은 배포할 때 Enterprise Voice.

### <a name="hardware-and-software-requirements"></a>하드웨어 및 소프트웨어 요구 사항

응답 그룹 응용 프로그램에는 프런트 엔드 서버와 동일한 하드웨어 요구 사항, 운영 체제 요구 사항 및 소프트웨어 선행 조건이 있습니다.

응답 그룹 음악 및 공지에 Windows 미디어 오디오(.wma) 파일을 사용하는 경우 응답 그룹 응용 프로그램을 실행하는 모든 프런트 엔드 서버 또는 Standard Editions 서버에는 Windows Server 2008 R2를 실행하는 서버에 대해 Windows 미디어 형식 런타임이 설치되어 있어야 합니다. R2 또는 Windows Server 2012 또는 Windows Server 2012 R2를 실행하는 서버의 경우 Microsoft Media Foundation이 설치되어 있어야 합니다. Windows Server 2008 R2의 경우 Windows 데스크톱 환경의 일부로 Windows 미디어 형식 런타임이 설치됩니다.

응답 그룹은 언어 **팩을** 사용하여 텍스트 음성 음성 및 음성 인식을 지원합니다. 이러한 음성 기술은 시작 메시지나 기타 프롬프트, 그리고 IVR(대화형 음성 응답) 질문 및 대답과 같은 메시지를 구성할 때 사용됩니다. 기본적으로 지원되는 언어 팩 26개는 배포 시 비즈니스용 Skype 서버.

### <a name="port-requirements"></a>포트 요구 사항

응답 그룹 응용 프로그램은 다음 포트를 사용 합니다.

- SIP 수신 요청용 포트 **5071**

- 서비스 간 통신을 위한 포트 **8404**

    > [!NOTE]
    > 이 포트는 일치하는 만들기 서비스에 사용하며 프런트 엔드 서버가 두 개 이상 있는 풀에 응답 그룹 응용 프로그램을 배포할 때 필요합니다.

   > [!NOTE]
   > 이러한 포트는 **Set-CsApplicationServer** cmdlet을 사용하여 변경할 수 있는 기본 설정입니다. 이 cmdlet에 대한 자세한 내용은 비즈니스용 Skype 서버 관리 셸 설명서를 참조하십시오.

### <a name="audio-file-requirements"></a>오디오 파일 요구 사항

응답 그룹 응용 프로그램은 응답 그룹 메시지, 보류 음악 또는 IVR(대화형 음성 응답) 질문에 대한 웨이브(.wav) 파일 형식 및 Windows 미디어 오디오(.wma) 파일 형식을 지원합니다.

Windows 미디어 오디오 파일 형식을 사용하려면 Windows Server 2008 R2 및 Windows Server 2008을 실행하는 프런트 엔드 서버에 Windows 미디어 형식 런타임이 설치되어야 합니다. 자세한 내용은 이 섹션의 앞 부분에 있는 "소프트웨어 요구 사항"을 참조하십시오.

#### <a name="supported-wave-file-formats"></a>지원되는 웨이브 파일 형식

모든 웨이브 파일은 다음 요구 사항을 충족해야 합니다.

- 8비트 또는 16비트 파일

- LPCM(선형 펄스 부호 변조), A-Law 또는 mu-Law 형식

- 모노 또는 스테레오

- 4MB 이하

최상의 웨이브 파일 성능을 위해서는 16kHz/모노/16비트의 웨이브 파일을 사용하는 것이 좋습니다.

#### <a name="supported-windows-media-audio-file-formats"></a>지원되는 Windows Media 오디오 파일 형식

Windows Media 오디오 파일을 사용할 경우 낮은 비트 전송률을 사용하고 시스템 성능이 정상인지 확인합니다.

Microsoft Expression Encoder 4를 사용하여 파일을 Windows Media 오디오 형식으로 변환할 수 있습니다. 식 인코더 4를 다운로드하려면 을 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) 참조합니다.

### <a name="response-group-configuration-tool-requirements"></a>응답 그룹 구성 도구 요구 사항

응답 그룹 구성 도구는 다음 표에 설명된 운영 체제 및 웹 브라우저의 조합을 지원합니다.

> [!NOTE]
> 32비트 또는 64비트 버전의 운영 체제가 지원됩니다. 32비트 버전의 Internet Explorer만 지원됩니다.

**지원되는 운영 체제 및 웹 브라우저**

|**운영 체제**|**웹 브라우저**|
|:-----|:-----|
|Windows Vista SP(서비스 팩) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> |
|Windows 7  <br/> Windows 7 서비스 팩 1  <br/> |Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> |
|Windows Server 2008 서비스 팩 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 서비스 팩 1  <br/> |Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>응답 그룹 에이전트 콘솔

에이전트 콘솔은 다음 표에 설명된 운영 체제 및 웹 브라우저의 조합을 지원합니다.

> [!NOTE]
> 32비트 또는 64비트 버전의 운영 체제가 지원됩니다. 32비트 버전의 Internet Explorer만 지원됩니다.

**지원되는 운영 체제 및 웹 브라우저**

|**운영 체제**|**웹 브라우저**|
|:-----|:-----|
|Windows Vista SP(서비스 팩) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> |
|Windows 7  <br/> Windows 7 서비스 팩 1  <br/> |Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 서비스 팩 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 서비스 팩 1  <br/> |Internet Explorer 8(기본 모드)  <br/> Internet Explorer 9(기본 모드)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>클라이언트 지원

응답 그룹 응용 프로그램은 다음 클라이언트를 지원합니다.

- 비즈니스용 Skype 데스크톱 클라이언트

- Lync 2013 데스크톱 클라이언트

- Lync 2010 데스크톱 클라이언트

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> 응답 그룹 응용 프로그램은 Lync 모바일 클라이언트에서 지원되지 않습니다.

사용할 수 있는 특정 클라이언트는 사용자의 응답 그룹 사용자 유형에 따라 다릅니다.

- **발신자** 는 앞에 나열된 클라이언트와 PSTN(공중 전화망)을 통해 일반 전화기를 사용하여 응답 그룹에 전화를 걸 수 있습니다.

- **비공식** 에이전트(전화를 수락하기 위해 그룹에 로그인하거나 그룹에서 로그인하지 않는 에이전트)는 Attendant, Lync 또는 Lync 전화 Edition을 사용하여 전화를 수락할 수 있습니다. 비공식 에이전트는 이러한 클라이언트 중 하나를 사용하여 비즈니스용 Skype 서버 그룹에 자동으로 로그인됩니다.

- **전화에** 수락하기 위해 그룹에 로그인하여 그룹에서 로그인해야 하는 에이전트)는 비즈니스용 Skype 메뉴 항목에서 에이전트 콘솔에 액세스하거나, 전화 도우미를 사용하여 에이전트 콘솔에 직접 액세스하여 통화를 수락할 수 Internet Explorer.

## <a name="capacity-planning"></a>용량 계획

다음 표에서는 용량 계획 요구 사항을 기준으로 사용할 수 있는 응답 그룹 사용자 모델에 대해 설명하고 있습니다.

> [!NOTE]
> 다음 표의 숫자는 모든 응답 그룹 오디오 파일에 대해 16kHz, 모노, 16비트 Wave(.wav) 파일을 사용하고 있다는 가정을 바탕으로 합니다. Windows Media 오디오(.wma) 등과 같은 다른 파일 형식을 사용하는 경우에는 숫자가 달라질 수 있습니다.

> [!IMPORTANT]
> 재해 복구 용량 계획을 위해 한 쌍으로구성된 풀의 각 풀은 두 풀에 있는 모든 응답 그룹의 작업을 처리할 수 있어야 합니다.

**응답 그룹 사용자 모델**

|**메트릭**|**Enterprise Edition 풀당(프런트 엔드 <br/> 서버가 8대인 경우)**|**Standard Edition Server별**|
|:-----|:-----|:-----|
|초당 걸려오는 전화 수  <br/> |16   <br/> |2  <br/> |
|IVR 또는 MoH에 연결된 동시 통화 수  <br/> |480  <br/> |60  <br/> |
|동시 익명 세션 수(IM 포함 안 함)  <br/> |224  <br/> |28  <br/> |
|동시 익명 세션 수(IM 포함)  <br/> |64  <br/> |8   <br/> |
|활성 에이전트(공식 및 비공식)  <br/> |2400  <br/> |2400  <br/> |
|헌트 그룹 수  <br/> |800  <br/> |800  <br/> |
|IVR 그룹 수(음성 인식 사용)  <br/> |400  <br/> |400  <br/> |