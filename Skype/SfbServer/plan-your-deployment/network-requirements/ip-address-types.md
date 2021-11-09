---
title: 2016에서 IP 주소 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: '요약: 다음을 구현하기 전에 아래의 IP 주소 유형 고려 사항을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 936857f79cf71328303e3a0a842b230694cf86c1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834996"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>2016에서 IP 주소 비즈니스용 Skype

**요약:** IP 주소 유형을 구현하기 전에 아래에서 IP 주소 유형 고려 사항을 비즈니스용 Skype 서버.

토폴로지 작성기에서 구성한 토폴로지 설정을 사용하여 IP 주소 유형을 배포합니다. 이 섹션에서는 프런트 엔드 서버, 중재 서버 및 에지 서버에 IP 주소 유형을 배포하는 방법에 대해 설명합니다.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>프런트 엔드 서버에 IP 주소 유형 배포

토폴로지 작성기에서 다음 절차의 단계를 수행하여 프런트 엔드 서버에 IP 주소 유형을 배포합니다.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>프런트 엔드 서버에 IP 주소 유형을 배포하려면

1. **Enterprise Edition 프런트 엔드 풀** 아래에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집** 을 선택합니다. 또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.

2. **속성 편집** 대화 상자에서 구성할 IP 주소 유형을 선택합니다. 이중 스택 구성의 경우 **IPv4** 사용 및 **IPv6 사용 을 선택합니다.**

   **프런트 엔드 서버 풀에 대한 속성 편집 대화 상자**

   - **구성된 모든 IP 주소**. 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있도록 하려면 이 옵션을 선택합니다.

     > [!NOTE]
     > 이것이 IP 버전 6(IPv6) 구성에서 권장되는 옵션입니다.

   - **선택한 IP 주소로 서비스 사용 제한**. 새 서버에서 사용할 특정 주소를 지정하려면 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 **기본 IP 주소** 의 값을 입력해야 합니다.

   - **기본 IP 주소**. 서버에서 PSTN(공중 전화망)을 제외한 모든 통신에 사용할 IP 주소를 입력합니다. 입력하는 IP 주소는 선택한 주소 유형의 형식과 일치해야 합니다.

   - **PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에 배치되는 경우 PSTN IP 주소를 정의합니다. 이 주소는 선택한 주소 유형의 형식과 일치해야 합니다.

> [!NOTE]
> 프런트 엔드 서버에서 PSTN IP 주소 구성을 지원하기 위한 추가 NI(네트워크 인터페이스 카드)의 설치는 지원되지 않습니다. Lync Server 2013에 대해 지원되는 NIC 비즈니스용 Skype 서버 대한 자세한 내용은 [Server hardware platforms for Lync Server 2013을 참조하십시오.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>중재 서버에 IP 주소 유형 배포

토폴로지 작성기에서 다음 절차의 단계를 수행하여 중재 서버에 IP 주소 유형을 배포합니다.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>중재 서버에 IP 주소 유형을 배포하는 경우

- 토폴로지 작성기의 중재 풀에서 **풀** 내의 서버를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집 을 선택합니다.** 또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.

- **속성 편집** 대화 상자에서 구성할 IP 주소 유형을 선택합니다. 이중 스택 구성의 경우 다음 그림과 같이 **IPv4 사용** 과 **IPv6 사용** 을 선택합니다.

   **중재 서버 풀의 속성 편집 대화 상자**

  - **구성된 모든 IP 주소**. 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있도록 하려면 이 옵션을 선택합니다.

    > [!NOTE]
    > 이것이 IP 버전 6(IPv6) 구성에서 권장되는 옵션입니다.

  - **선택한 IP 주소로 서비스 사용 제한**. 새 서버에서 사용할 특정 주소를 지정하려면 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 기본 IP 주소의 값을 입력해야 합니다.

  - **기본 IP 주소**. 서버에서 PSTN(공중 전화망)을 제외한 모든 통신에 사용할 IP 주소를 입력합니다. 입력하는 IP 주소는 선택한 주소 유형의 형식과 일치해야 합니다.

  - **PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에 배치되는 경우 PSTN IP 주소를 정의합니다. 이 주소는 선택한 주소 유형의 형식과 일치해야 합니다.
> [!IMPORTANT]
> 전용 중재 서버에서는  두 개의 네트워크 카드만 지원됩니다. 중재 Sserver 역할이 프런트 엔드에 함께 있는 경우 이중 네트워크 카드가 지원되지 않습니다. 

> [!NOTE]
> - 비즈니스용 Skype 서버 2015에 대해 지원되는 NIC 구성에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015용](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015) 하드웨어를 참조하세요.
> - 비즈니스용 Skype 서버 2019에 대해 지원되는 NIC 구성에 대한 자세한 내용은 [Hardware for 비즈니스용 Skype 서버 2019을 참조하십시오.](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>에지 서버에 IP 주소 유형 배포

토폴로지 작성기에서 다음 단계를 수행합니다.

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>에지 서버에 IP 주소 유형을 배포하는 경우

1. 토폴로지 작성기의 **에지** 풀에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 선택합니다.** 또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.

2. 속성 **편집 창에서** 지원할 IP 주소 구성을 선택합니다.

3. 선택한 각 주소 유형에 대해 적절한 내부 및 외부 주소를 제공해야 합니다.