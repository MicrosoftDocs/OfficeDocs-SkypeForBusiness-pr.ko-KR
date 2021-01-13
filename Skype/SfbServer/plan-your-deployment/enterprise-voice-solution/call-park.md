---
title: 비즈니스용 Skype의 통화 파크 계획
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 비즈니스용 Skype 서버 Enterprise Voice 통화를 보류하고 부서로 통화를 전송할 수 있는 통화 파킹 계획 용량 계획, 지원되는 통화 및 지원되는 클라이언트를 포함합니다.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825928"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>비즈니스용 Skype의 통화 파크 계획
 
비즈니스용 Skype 서버 Enterprise Voice 통화를 보류하고 부서로 통화를 전송할 수 있는 통화 파킹 계획 용량 계획, 지원되는 통화 및 지원되는 클라이언트를 포함합니다.
  
통화 파크 응용 프로그램을 Enterprise Voice 사용자가 다음을 할 수 있습니다.
  
- 통화를 대기시킨 후에 같은 전화기 또는 다른 전화기에서 통화 재개
    
- 통화를 대기시키고 이 통화를 특정 부서나 일반 영역(예: 영업 부서 또는 공통 영역 전화가 있는 창고)으로 전송
    
- 통화를 대기시키고 처음에 응답한 전화기에서 다른 통화 수신
    
사용자가 통화를 파기하면 비즈니스용 Skype 서버가 통화를 파기할 때 통화가 재개되거나 통화가 시간 외일 때까지 통화가 보전되는 파기 번호라는 임시 번호로 통화를 전송합니다. 비즈니스용 Skype 서버가 통화를 시작한 사용자에게 파인 통화를 전송합니다. 사용자는 통화 번호로 전화를 걸거나 대화 창에서 파선 링크 또는 단추를 클릭할 수 있습니다. 
  
통화를 대기시킨 사용자는 IM(인스턴트 메시징) 또는 호출 시스템과 같은 외부 메커니즘을 사용하여 파킹된 통화 번호를 전달하는 방식으로 다른 사람에게 통화를 재개하도록 알릴 수 있습니다. 또한 통화를 대기시킨 사용자는 통화가 재개된 경우 알림을 받기 위해 대화 창을 열어 둘 수 있습니다.
  
파킹된 통화 번호 범위는 전역적으로 고유하기 때문에 라우팅이 적절하게 구성된 경우 비즈니스용 Skype 서버 사이트 또는 PBX 전화에서 통화를 검색할 수 있습니다. 구성 가능한 시간 내에 아무도 통화를 재개하지 않으면 통화를 대기시킨 사람에게 통화가 다시 연결됩니다. 그런 다음 통화를 대기시킨 사람이 다시 연결된 통화에 응답하지 않으면 통화가 교환원과 같은 대체 대상으로 전송됩니다(이렇게 구성된 경우). 이와 같이 통화가 전송되기 전에 통화가 다시 연결되는 횟수(1회~10회)를 구성할 수 있습니다. 전송된 통화에 아무도 응답하지 않으면 통화 연결이 끊어집니다. 통화가 재개되거나 끊긴 경우에는 파킹된 통화 번호가 비워집니다.
  
통화 대기를 배포할 때 통화 대기에 사용할 내선 번호(파킹된 통화 번호) 범위를 예약해야 합니다. 이러한 내선 번호는 가상 내선 번호, 즉 할당된 사용자 또는 전화가 없는 내선 번호여야 합니다. 그런 다음 파킹된 통화 번호 범위를 사용하여 통화 대기 파킹된 통화 번호 테이블을 구성하고 각 범위를 처리할 통화 대기 응용 프로그램을 호스팅하는 응용 프로그램 서비스를 지정합니다. 각 프런트 엔드 풀에는 해당 백 엔드 서버에 풀에서 대기 중인 통화를 관리하는 데 사용되는 통화 대기 테이블이 있습니다. 궤도 범위 목록은 중앙 관리 저장소에 저장되고 궤도는 대상 풀로 라우팅하는 데 사용됩니다. 통화 파크 응용 프로그램이 배포 및 구성된 각 비즈니스용 Skype 서버 풀에는 하나 이상의 파인트 범위가 있습니다. 궤도 범위는 비즈니스용 Skype 서버 배포에서 전역적으로 고유해야 합니다. 
  
또한 여러분은 시간 초과된 통화가 리디렉션되는 위치 및 통화 대기 중인 사용자에게 음악을 들려줄지 여부와 같은 다른 통화 대기 설정을 구성할 수 있으며, 통화 대기 중인 동안 재생할 음악 파일을 지정할 수도 있습니다.
  
> [!NOTE]
> 통화 파크에 대한 사용자 지정 보류 음악 파일은 비즈니스용 Skype 서버 재해 복구 프로세스의 일부로 백업되지 않습니다. 풀에 업로드된 파일이 손상되거나 삭제되면 손실됩니다. 통화 대기를 위해 업로드하는 사용자 지정 대기 음악 파일의 별도 백업 복사본을 항상 유지하십시오. 
  
통화 대기 응용 프로그램은 Enterprise Voice의 구성 요소입니다. Enterprise Voice를 배포하면 통화 대기 응용 프로그램이 자동으로 설치되고 활성화됩니다. 그러나 통화 대기를 사용하려면 먼저 Enterprise Voice 관리자가 통화 대기를 구성하고 음성 정책을 통해 사용자가 사용할 수 있도록 설정해야 합니다.
  
## <a name="deployment-and-requirements"></a>배포 및 요구 사항

통화 파크 응용 프로그램은 통화를 배포할 때 Enterprise Voice. 음성 정책을 구성하여 통화 파킹을 사용하도록 설정할 수 있습니다.
  
### <a name="software-requirements"></a>소프트웨어 요구 사항

통화 파운데이션이 배포된 모든 프런트 엔드 서버 및 Standard Edition Server에는 Windows Server 2008 R2를 실행하는 서버에 대해 Windows Media 형식 런타임이 설치되어 있어야 합니다. 또는 Windows Server 2012 또는 Windows Server 2012 R2를 실행하는 서버에는 Microsoft Media Foundation이 설치되어 있어야 합니다. Windows Server 2008 R2의 경우 Windows Media 형식 런타임은 Windows 데스크톱 환경의 일부로 설치됩니다. 통화 파운데이션이 재생하는 Windows Media 오디오(.wma) 파일에는 Windows Media 형식 런타임 또는 Microsoft Media Foundation이 필요합니다.
  
### <a name="port-requirements"></a>포트 요구 사항

통화 파크 응용 프로그램은 SIP **수신 요청에 포트 5075를**  사용 합니다.
    
> [!NOTE]
> 이 포트는 **Set-CsApplicationServer** cmdlet을 사용하여 변경할 수 있는 기본 설정입니다. 이 cmdlet에 대한 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.
  
### <a name="audio-file-requirements"></a>오디오 파일 요구 사항

통화 파크 응용 프로그램은 보류된 음악에 대해 Windows Media 오디오(.wma) 파일만 지원됩니다. Microsoft Expression Encoder 4를 사용하여 대기 음악용으로 파일을 사용자 지정할 수 있습니다. 식 인코더 4를 다운로드하려면 ["식 인코더 4"를 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=202843) 이 도구를 사용하여 파일을 .wma 형식으로 변환합니다. 통화 대기의 대기 음악 파일로 권장되는 형식은 Media 오디오 9, 44kHz, 16비트, 모노, CBR, 32kbps입니다.
  
> [!NOTE]
> 변환된 파일은 44kHz로 녹음되었더라도 전화에서는 16kHz로만 재생됩니다. 
  
## <a name="supported-clients-and-calls"></a>지원되는 클라이언트 및 통화

통화 파크에 대해 지원되는 클라이언트 및 통화 유형은 다음과 같습니다.
  
### <a name="clients-supported-for-parking-calls"></a>통화를 대기로 설정하는 데 지원되는 클라이언트

모든 IP, PBX(Private Branch Exchange), PSTN(공중 전화망) 또는 휴대폰의 통화를 대기로 설정할 수 있습니다.
  
> [!NOTE]
> 오디오 통화만 대기로 설정할 수 있습니다. 인스턴트 메시지 및 회의는 대기로 설정할 수 없습니다. 
  
다음 클라이언트는 통화 파크를 사용하여 통화를 파기할 수 있습니다.
  
- 비즈니스용 Skype
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> 휴대폰에서는 통화 파크를 사용하여 통화를 파기할 수 없습니다. 
  
### <a name="clients-supported-for-retrieving-calls"></a>통화를 재개하는 데 지원되는 클라이언트

파킹된 통화 번호 범위는 가상 내선 번호(사용자나 전화가 할당되지 않은 내선 번호) 블록으로 구성됩니다. 파킹된 통화 번호를 가상 내선 번호로 구성하면 휴대폰 및 PSTN 전화에서 대기로 설정된 통화를 재개할 수 없습니다.
  
페더레이션 사용자는 대기로 설정된 통화를 재개할 수 없습니다.
  
다음 클라이언트는 통화 파크에 대한 통화를 검색할 수 있습니다.
  
- 비즈니스용 Skype
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP 공통 영역 전화
    
- 공통 영역 전화 및 PBX(Private Branch Exchange) 전화를 포함하여 비즈니스용 Skype 서버 인프라에 연결된 비 IP 전화
    
## <a name="call-park-capacity-planning"></a>통화 파크 용량 계획

다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 통화 파크 사용자 모델에 대해 설명하고 있습니다.
  
> [!IMPORTANT]
> 재해 복구 용량 계획을 위해 페어링된 풀의 각 풀은 두 풀 모두에서 통화 파크 서비스에 대한 작업을 처리할 수 있습니다. 
  
**통화 대기 사용자 모델**

|**메트릭**|**프런트 엔드  <br/>  풀당(프런트 엔드 서버 8대)**|**Standard Edition Server별**|
|:-----|:-----|:-----|
|대기 속도  <br/> |분당 8개  <br/> |분당 1개  <br/> |
|대기 중인 통화 재개 속도  <br/> |분당 8개  <br/> |분당 1개  <br/> |
|평균 대기 시간  <br/> |60초  <br/> |60초  <br/> |
   

