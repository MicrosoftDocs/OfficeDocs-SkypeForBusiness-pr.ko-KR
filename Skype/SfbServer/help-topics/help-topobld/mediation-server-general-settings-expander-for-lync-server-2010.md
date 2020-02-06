---
title: Lync Server 2010용 중재 서버 일반 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 이 대화 상자에서 중재 서버의 속성을 편집 합니다. 왼쪽에는 일반 설정, 다음 홉 설정, PSTN 게이트웨이 설정에 대 한 설정으로 이동 하는 빠른 링크 집합이 있습니다. 각 섹션에는 다음 설정이 있습니다.
ms.openlocfilehash: 3f7dad61778f54fee7a9be984191bc21f5029502
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819620"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010용 중재 서버 일반 설정 확장기

이 대화 상자에서 중재 서버의 속성을 편집 합니다. 왼쪽에는 일반 설정, 다음 홉 설정, PSTN 게이트웨이 설정에 대 한 설정으로 이동 하는 빠른 링크 집합이 있습니다. 각 섹션에는 다음 설정이 있습니다.

 **일반**:

- **FQDN**: 중재 서버의 정규화 된 도메인 이름을 편집 합니다.

- **연결**: **edge 풀 연결 (미디어 구성 요소의 경우)** 확인란을 선택 하 고 중재 서버에 대 한 edge 서버 또는 edge 풀을 선택 하 여 외부 액세스를 위한 미디어 경로로 사용 합니다.

  **다음 홉**:

- **다음 홉 선택**: 목록에서 배포와 통신 하는 데 사용할 중재 서버의 경로로 사용할 프런트 엔드 서버 또는 프런트 엔드 풀을 선택 합니다.

  **PSTN 게이트웨이**:

  **중재 서버 PSTN 게이트웨이**:

- **수신 대기 포트**: 중재 서버가 수신 대기 하는 포트를 정의 합니다. **TLS** 또는 전송 계층 보안, **TCP**또는 전송 제어 프로토콜에 대 한 포트를 정의할 수 있습니다. TCP에 대 한 포트 항목을 사용 하려면 **tcp 포트 사용**확인란을 선택 해야 합니다.

    > [!IMPORTANT]
    > 포트 값 TLS, TCP 또는 둘 다를 사용 하도록 설정 하 고 정의 해야 하는지 여부는 공용 전환 통신 네트워크 (PSTN) 게이트웨이에 대 한 설명서 및 구성 설정을 참조 하세요. TLS는 중재 서버와 PSTN 게이트웨이 간의 트래픽을 암호화 하는 인증서를 사용 하 여 보다 안전한 프로토콜입니다. 일부 PSTN 게이트웨이가 TLS를 지원 하지는 않습니다.

- 배포에 대해 정의 되 고 구성 되는 SIP trunks 목록과 게이트웨이가 나열 됩니다. 항목이 없는 경우에는 배포에 대해 구성 된 SIP trunks 또는 PSTN 게이트웨이를 포함 하지 않습니다. 토폴로지 작성기에서 **공유 구성 요소** 아래에 trunks 및 게이트웨이를 정의 하 고 구성 합니다.

## <a name="see-also"></a>참고 항목

[SIP 트렁크 개요](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[PSTN 게이트웨이 배포 옵션](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
