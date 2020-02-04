---
title: 장치 구성 새로 만들기 또는 기존 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: 새 장치 구성 또는 장치 구성 편집 페이지에서 비즈니스용 Skype Phone 에디션을 관리 하는 데 사용 되는 설정 모음을 만들거나 수정할 수 있습니다. 이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.
ms.openlocfilehash: fce3ad1410dc16cc6a238823f11cdba0f4c4c391
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691483"
---
# <a name="device-configuration-create-new-or-edit-existing"></a>장치 구성: 새로 만들기 또는 기존 항목 편집
 
**새 장치 구성** 또는 **장치 구성 편집** 페이지에서 비즈니스용 Skype Phone 에디션을 관리 하는 데 사용 되는 설정 모음을 만들거나 수정할 수 있습니다. 이러한 설정을 사용하면 필수 보안 모드, 장치 로깅 수준, 음성 QoS(서비스 품질) 설정, 그리고 지정된 기간 동안 활동이 없으면 전화를 자동으로 잠글지 여부 등의 옵션을 구성할 수 있습니다.
  
## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 장치 구성** 또는 **장치 구성 편집** 페이지에서는 다음 작업을 수행할 수 있습니다.
  
- 새 장치 구성 추가
    
- 기존 장치 구성의 속성 수정
    
## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드, 속성에 대해 설명합니다.
  
- **범위** 장치 구성의 범위 (전역 또는 사이트)를 식별 합니다.
    
- **이름** 장치 구성의 이름을 추가 하거나 수정할 수 있습니다.
    
- **SIP 보안** 비즈니스용 Skype Phone Edition 장치에 대 한 전송 및 인증 요구 사항을 구성할 수 있습니다. 다음 옵션 중에서 선택할 수 있습니다.
    
  - **낮음입니다** 모든 유형의 권한 부여 또는 전송을 허용 합니다.
    
  - **Medium** 사용자 인증에 NTLM 또는 Kerberos가 필요 합니다.
    
  - **높음** 사용자 인증에는 NTLM 또는 Kerberos가 필요 하며 SIP 연결에는 TLS가 필요 합니다.
    
- **로깅 수준** UC 장치에서 로깅을 사용 하도록 설정할 수 있습니다. 사용할 수 있는 값은 사용 안 함, 낮음, 중간, 높음입니다. 기본값은 사용 안 함입니다.
    
- **보이스 서비스 품질 (QoS)** 비즈니스용 Skype Phone Edition 장치에서 음성 트래픽 emanating에 할당 된 DSCP 값을 지정할 수 있습니다. 기본값은 40입니다. 그러나 40는 일반적으로 오디오 트래픽에 사용 되는 값이 아닙니다. 대신 오디오 트래픽은 거의 항상 DSCP 코드 46으로 표시 됩니다. 네트워크 전체에서 일관성을 유지 하기 위해이 값을 46으로 변경 하는 것이 좋습니다.
    
- **전화 잠금** 지정 된 기간 동안 사용할 수 없는 경우 UC 전화기가 자동으로 잠길 지 여부를 지정할 수 있습니다. 다음은 구성할 수 있는 설정입니다.
    
  - **장치 잠금 적용** 이 확인란을 선택 하 여 장치 잠금을 적용할 수 있습니다.
    
  - **최소 PIN 길이** 휴대폰을 잠금 해제 하는 데 사용 되는 PIN (개인 식별 번호)의 최소 길이를 지정할 수 있습니다. PIN 길이의 범위는 4 ~ 15 자리입니다. 기본 길이는 6 자리입니다.
    
  - **전화 잠금 시간 초과** 전화가 잠기는 최소 시간을 지정할 수 있습니다. 시간 초과의 범위는 0 ~ 60 분입니다. 기본값은 10 분입니다. HH: MM: SS 형식으로 값을 입력 합니다.
    
## <a name="see-also"></a>참고 항목

[장치 구성](ms.lync.lscp.ClientDeviceCfgMain.md)

[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
