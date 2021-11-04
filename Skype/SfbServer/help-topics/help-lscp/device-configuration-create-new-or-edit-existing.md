---
title: 장치 구성 새로 만들기 또는 기존 기능 편집
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: 새 장치 구성 또는 장치 구성 편집 페이지에서 비즈니스용 Skype 전화 버전 관리에 사용되는 설정 컬렉션을 만들거나 수정할 수 있습니다. 이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.
ms.openlocfilehash: 8211e31ddb4f28d72c50b90d982fbb1e16ab0f63
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758450"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>장치 구성: 새로 만들기 또는 기존 항목 편집
 
새 장치 구성  **또는** 장치 구성 편집 페이지에서 비즈니스용 Skype 전화 버전 관리에 사용되는 설정 컬렉션을 만들거나 수정할 수 있습니다. 이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.
  
## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 장치 구성** 또는 **장치 구성 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.
  
- 새 장치 구성 추가
    
- 기존 장치 구성의 속성 수정
    
## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.
  
- **범위** 장치 구성의 범위(전역 또는 사이트)를 식별합니다.
    
- **이름** 장치 구성의 이름을 추가하거나 수정할 수 있습니다.
    
- **SIP 보안** 비즈니스용 Skype 전화 버전 장치에 대한 전송 및 인증 요구 사항을 구성할 수 있습니다. 다음 옵션에서 선택할 수 있습니다.
    
  - **낮음** 모든 유형의 권한 부여 또는 전송을 허용합니다.
    
  - **보통** 사용자 인증에는 NTLM 또는 Kerberos가 필요합니다.
    
  - **높음** 사용자 인증에는 NTLM 또는 Kerberos가 필요하며 SIP 연결에는 TLS가 필요합니다.
    
- **로깅 수준** UC 장치에서 로깅을 사용하도록 설정할 수 있습니다. 사용할 수 있는 값은 사용 안 함, 낮음, 중간, 높음입니다. 기본값은 사용 안 함입니다.
    
- **음성 QoS(서비스 품질)** 비즈니스용 Skype 전화 버전 장치에서 발신되는 음성 트래픽에 할당된 DSCP 값을 지정할 수 있습니다. 기본값은 40입니다. 그러나 40은 일반적으로 오디오 트래픽에 사용되는 값이 아니며, 대신 오디오 트래픽은 거의 항상 DSCP 코드 46으로 표시됩니다. 네트워크 전체에서 일관성을 유지하기 위해 이 값을 46으로 변경할 수 있습니다.
    
- **전화 잠금** UC 전화가 지정된 기간 동안 비활성화된 후 자동으로 잠글지 여부를 지정할 수 있습니다. 구성할 수 있는 설정은 다음과 같습니다.
    
  - **장치 잠금 적용** 이 확인란을 선택하여 장치 잠금을 적용할 수 있습니다.
    
  - **최소 PIN 길이** 휴대폰 잠금을 해제하는 데 사용되는 개인식별번호(PIN)의 최소 길이를 지정할 수 있습니다. PIN 길이의 범위는 4-15자리입니다. 기본 길이는 6자리입니다.
    
  - **전화 시간제한 설정** 휴대폰 자체를 잠그기 전의 최소 시간을 지정할 수 있습니다. 시간 범위는 0~60분입니다. 기본값은 10분입니다. 값을 HH:MM:SS 형식으로 입력합니다.
    
## <a name="see-also"></a>참고 항목

[장치 구성](device-configuration.md)

[Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)