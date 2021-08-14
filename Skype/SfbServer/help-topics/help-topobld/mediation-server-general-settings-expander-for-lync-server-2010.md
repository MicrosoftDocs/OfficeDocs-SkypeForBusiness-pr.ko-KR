---
title: Lync Server 2010에 대한 중재 서버 일반 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 이 대화 상자에서 중재 서버의 속성을 편집합니다. 대화 상자 왼쪽에는 일반 설정, 다음 홉 설정 및 PSTN 게이트웨이 설정으로 이동할 수 있는 빠른 링크 집합이 있습니다. 각 섹션에는 다음과 같은 설정이 있습니다.
ms.openlocfilehash: 87eda891ae5c9e19a9a54e000b85b62e46c077d6a4c90318c9372fe6e887ecaa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344787"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010에 대한 중재 서버 일반 설정 확장기

이 대화 상자에서 중재 서버의 속성을 편집합니다. 대화 상자 왼쪽에는 일반 설정, 다음 홉 설정 및 PSTN 게이트웨이 설정으로 이동할 수 있는 빠른 링크 집합이 있습니다. 각 섹션에는 다음과 같은 설정이 있습니다.

 **일반**:

- **FQDN:** 중재 서버의 정식 도메인 이름을 편집합니다.

- **연결:** 에지 풀 연결(미디어 구성 **요소용)** 확인란을 선택하고 중재 서버가 외부 액세스에 대한 미디어 경로로 사용할 에지 서버 또는 에지 풀을 선택합니다.

  **다음 홉**:

- **다음 홉** 선택: 목록에서 배포와 통신하는 데 사용할 중재 서버의 경로로 사용할 프런트 엔드 서버 또는 프런트 엔드 풀을 선택합니다.

  **PSTN 게이트웨이**:

  **중재 서버 PSTN 게이트웨이**

- **수신 포트:** 중재 서버에서 수신할 포트를 정의합니다. **TLS**(전송 계층 보안) 또는 **TCP**(Transport Control Protocol)용 포트를 정의할 수 있습니다. TCP에 대한 포트 항목을 사용할 수 있도록 하려면 **TCP 포트 사용** 확인란을 선택해야 합니다.

    > [!IMPORTANT]
    > 공중 전화망(PSTN) 게이트웨이의 설명서 및 구성 설정을 참조하여 포트 값 TLS 또는 TCP나 둘 다를 사용하도록 설정하고 정의해야 하는지 여부를 확인하십시오. TLS는 인증서를 사용하여 중재 서버와 PSTN 게이트웨이 간의 트래픽을 암호화하는 보다 안전한 프로토콜입니다. 일부 PSTN 게이트웨이에서는 TLS가 지원되지 않습니다.

- 배포에 대해 정의 및 구성된 SIP 트렁크 및 게이트웨이 목록이 표시됩니다. 항목이 없는 경우에는 배포에 대해 구성된 SIP 트렁크 또는 PSTN 게이트웨이가 없는 것입니다. 토폴로지 작성기에서 공유 구성 요소 아래에 트렁크 및 **게이트웨이를** 정의하고 구성합니다.

## <a name="see-also"></a>참고 항목

[SIP 트렁크 개요](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[PSTN 게이트웨이 배포 옵션](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)